# CServiceMonitor::Stop(void)

- ea: `0x180016b94`
- end: `0x180016c00`
- name: `?Stop@CServiceMonitor@@QEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001239c`
- `0x180012a80`
- `0x180013fd0`

## callees

- `0x180016b94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bde`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016bcd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016bcd`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180016bc0`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180016bc0`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::Stop(CServiceMonitor *this)
{
  unsigned int v3; // ebx
  BOOL v4; // eax
  signed int LastError; // eax

  if ( !*((_QWORD *)this + 67) )
    return 2147500037LL;
  v3 = 0;
  if ( *((_QWORD *)this + 69) )
    UnsubscribeServiceChangeNotifications();
  v4 = CloseServiceHandle(*((SC_HANDLE *)this + 67));
  *((_QWORD *)this + 67) = 0;
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180016b94  mov     [rsp+arg_0], rbx
0x180016b99  push    rdi
0x180016b9a  sub     rsp, 20h
0x180016b9e  cmp     qword ptr [rcx+218h], 0
0x180016ba6  mov     rdi, rcx
0x180016ba9  jnz     short loc_180016BB2
0x180016bab  mov     eax, 80004005h
0x180016bb0  jmp     short loc_180016BF5
0x180016bb2  mov     rcx, [rcx+228h]
0x180016bb9  xor     ebx, ebx
0x180016bbb  test    rcx, rcx
0x180016bbe  jz      short loc_180016BC6
0x180016bc0  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180016bc6  mov     rcx, [rdi+218h]; hSCObject
0x180016bcd  call    cs:__imp_CloseServiceHandle
0x180016bd3  mov     [rdi+218h], rbx
0x180016bda  test    eax, eax
0x180016bdc  jnz     short loc_180016BF3
0x180016bde  call    cs:__imp_GetLastError
0x180016be4  mov     ebx, eax
0x180016be6  test    eax, eax
0x180016be8  jle     short loc_180016BF3
0x180016bea  movzx   ebx, ax
0x180016bed  or      ebx, 80070000h
0x180016bf3  mov     eax, ebx
0x180016bf5  mov     rbx, [rsp+28h+arg_0]
0x180016bfa  add     rsp, 20h
0x180016bfe  pop     rdi
0x180016bff  retn
```
