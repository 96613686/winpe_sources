# CServiceMonitor::Stop(void)

- ea: `0x180031278`
- end: `0x1800312e4`
- name: `?Stop@CServiceMonitor@@QEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800289ac`
- `0x180029db0`
- `0x180032c90`

## callees

- `0x180031278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800312b1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800312b1`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800312a4`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800312a4`

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
0x180031278  mov     [rsp+arg_0], rbx
0x18003127d  push    rdi
0x18003127e  sub     rsp, 20h
0x180031282  cmp     qword ptr [rcx+218h], 0
0x18003128a  mov     rdi, rcx
0x18003128d  jnz     short loc_180031296
0x18003128f  mov     eax, 80004005h
0x180031294  jmp     short loc_1800312D9
0x180031296  mov     rcx, [rcx+228h]
0x18003129d  xor     ebx, ebx
0x18003129f  test    rcx, rcx
0x1800312a2  jz      short loc_1800312AA
0x1800312a4  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800312aa  mov     rcx, [rdi+218h]; hSCObject
0x1800312b1  call    cs:__imp_CloseServiceHandle
0x1800312b7  mov     [rdi+218h], rbx
0x1800312be  test    eax, eax
0x1800312c0  jnz     short loc_1800312D7
0x1800312c2  call    cs:__imp_GetLastError
0x1800312c8  mov     ebx, eax
0x1800312ca  test    eax, eax
0x1800312cc  jle     short loc_1800312D7
0x1800312ce  movzx   ebx, ax
0x1800312d1  or      ebx, 80070000h
0x1800312d7  mov     eax, ebx
0x1800312d9  mov     rbx, [rsp+28h+arg_0]
0x1800312de  add     rsp, 20h
0x1800312e2  pop     rdi
0x1800312e3  retn
```
