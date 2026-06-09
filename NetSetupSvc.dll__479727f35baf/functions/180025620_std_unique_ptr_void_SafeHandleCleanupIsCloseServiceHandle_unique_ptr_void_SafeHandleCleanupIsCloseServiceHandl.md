# std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(void)

- ea: `0x180025620`
- end: `0x180025637`
- name: `??1?$unique_ptr@XUSafeHandleCleanupIsCloseServiceHandle@@@std@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(SC_HANDLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180025640`
- `0x180025680`

## callees

- `0x180025620`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002562c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002562c`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(
        SC_HANDLE *a1)
{
  SC_HANDLE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return CloseServiceHandle(v1);
  return result;
}

```

## disassembly

```asm
0x180025620  sub     rsp, 28h
0x180025624  mov     rcx, [rcx]; hSCObject
0x180025627  test    rcx, rcx
0x18002562a  jz      short loc_180025632
0x18002562c  call    cs:__imp_CloseServiceHandle
0x180025632  add     rsp, 28h
0x180025636  retn
```
