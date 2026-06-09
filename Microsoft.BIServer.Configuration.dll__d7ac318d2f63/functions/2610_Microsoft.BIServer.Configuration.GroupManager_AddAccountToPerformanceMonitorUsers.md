# Microsoft.BIServer.Configuration.GroupManager::AddAccountToPerformanceMonitorUsers

- ea: `0x2610`
- end: `0x2627`
- name: `Microsoft.BIServer.Configuration.GroupManager::AddAccountToPerformanceMonitorUsers`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2610`
- `0x2630`
- `0x2680`
- `0x2710`

## pseudocode

```c

```

## disassembly

```asm
0x2610  call     class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry Microsoft.BIServer.Configuration.GroupManager::GetPerfMonDirectoryEntry()
0x2615  stloc.0
0x2616  ldloc.0
0x2617  ldarg.0
0x2618  call     bool Microsoft.BIServer.Configuration.GroupManager::DoesGroupContainAccount(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry group, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x261d  brtrue.s loc_2626
0x261f  ldloc.0
0x2620  ldarg.0
0x2621  call     void Microsoft.BIServer.Configuration.GroupManager::AddUserToGroup(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry group, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x2626  ret
```
