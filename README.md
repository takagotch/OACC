### oacc
---
https://github.com/acciente/oacc-core

http://oaccframework.org/

```java
// src/test/java/com/acciente/oacc/TestAccessControl_assertResourcePermissions.java
package com.acciente.oacc;

import org.juint.Test;

import java.util.Collections;
import java.util.Set;

import static org.hamcrest.CoreMatchers.containsString;
import static org.hamcrest.CoreMatchers.is;
import static org.juint.Assert.assertThat;
import static org.juint.Assert.fail;

public class TestAccessControl_assertResourcePermissins extends TestAccessControlBase {
  @Test
  public void assertResourcePermissions_succeedsAsSystemResource() {
    authenticateSystemResource();
    
    final String resourceClassName = generateResourceClass(false, false);
    final String customPermissionName = generateResourceClassPermission(resourceClassName);
    
    final Resource accessedResource = accessControlContext.createResource(resourceClassName,
      accessControlContext
        .getDomainNameByResource(SYS_RESOURCE));
      
    final Set<ResourcePermission> directResourcePermissions
      = accessControlContext.getResourcePermissions(SYS_RESOURCE, accessedResource);
    assertThat(directResourcePermissions.isEmpty(), is(true));
    
    accessControlContext.assertResourcePermissions(SYS_RESOURCE,
      accessdResource,
      ResourcePermissions.getInstance(custmoPermissionName));
  }
}

```

```
```

```
```
