# TerminateConfigurationGlobals

- ea: `0x180003aa0`
- end: `0x180003ac6`
- name: `TerminateConfigurationGlobals`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000750c`

## callees

- `0x180003aa0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ab0`

## pseudocode

```c
BOOL TerminateConfigurationGlobals()
{
  BOOL result; // eax

  if ( g_ServiceCommChannelHandle )
  {
    result = CloseHandle(g_ServiceCommChannelHandle);
    g_ServiceCommChannelHandle = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003aa0  sub     rsp, 28h
0x180003aa4  mov     rcx, cs:g_ServiceCommChannelHandle; hObject
0x180003aab  test    rcx, rcx
0x180003aae  jz      short loc_180003AC1
0x180003ab0  call    cs:__imp_CloseHandle
0x180003ab6  mov     cs:g_ServiceCommChannelHandle, 0
0x180003ac1  add     rsp, 28h
0x180003ac5  retn
```
