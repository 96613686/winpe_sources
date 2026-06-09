# _anonymous_namespace_::_dynamic_initializer_for__tls_threadInfo__

- ea: `0x180002590`
- end: `0x1800025e5`
- name: `_anonymous_namespace_::_dynamic_initializer_for__tls_threadInfo__`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002590`
- `0x1800036b8`
- `0x180003d20`
- `0x1800195c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b5`
- `KERNEL32!TlsAlloc` at `0x180002594`
- `KERNEL32!TlsAlloc` at `0x180002594`

## pseudocode

```c
int anonymous_namespace_::_dynamic_initializer_for__tls_threadInfo__()
{
  signed int LastError; // eax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  dword_18004A6D8 = TlsAlloc();
  if ( dword_18004A6D8 == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, LastError);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return atexit((void (__cdecl *)())anonymous_namespace_::_dynamic_atexit_destructor_for__tls_threadInfo__);
}

```

## disassembly

```asm
0x180002590  sub     rsp, 58h
0x180002594  call    cs:__imp_TlsAlloc
0x18000259a  mov     cs:dword_18004A6D8, eax
0x1800025a0  cmp     eax, 0FFFFFFFFh
0x1800025a3  jz      short loc_1800025B5
0x1800025a5  lea     rcx, _anonymous_namespace____dynamic_atexit_destructor_for__tls_threadInfo__
0x1800025ac  add     rsp, 58h
0x1800025b0  jmp     atexit
0x1800025b5  call    cs:__imp_GetLastError
0x1800025bb  test    eax, eax
0x1800025bd  jle     short loc_1800025C7
0x1800025bf  movzx   eax, ax
0x1800025c2  or      eax, 80070000h
0x1800025c7  mov     edx, eax; int
0x1800025c9  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800025ce  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800025d3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800025da  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800025df  call    _CxxThrowException_0
```
