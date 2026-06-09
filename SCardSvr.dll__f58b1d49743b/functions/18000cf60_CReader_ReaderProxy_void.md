# CReader::ReaderProxy(void)

- ea: `0x18000cf60`
- end: `0x18000d188`
- name: `?ReaderProxy@CReader@@QEAAPEAVCReaderProxy@@XZ`
- size: `552`
- prototype: `struct CReaderProxy *__fastcall(CReader *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007910`
- `0x180009da0`
- `0x18000a310`

## callees

- `0x18000c870`
- `0x18000cf60`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d010`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d010`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d099`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d16c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cf97`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cfc1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d111`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cf97`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cfc1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d111`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CReaderProxy *__fastcall CReader::ReaderProxy(CReader *this)
{
  char *v2; // rbx
  __int64 v3; // rdi
  LPVOID Value; // rsi
  unsigned int v5; // eax
  __int64 v6; // rdi
  __int64 v7; // rdi
  bool v8; // zf
  char *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  char *v11; // [rsp+48h] [rbp+10h]
  char *v12; // [rsp+50h] [rbp+18h]

  v2 = (char *)this + 56;
  v11 = (char *)this + 56;
  pExceptionObject = (char *)this + 56;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 7))((char *)this + 56, 0, 0);
  if ( *((LPVOID *)v2 + 13) == TlsGetValue(dwTlsIndex) )
  {
    ++*((_DWORD *)v2 + 14);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
      v3 = *((_QWORD *)v2 + 11);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v5 = WaitForAnyObject(0xFFFFFFFF, v3, Value, 0);
        if ( v5 == 1 )
          break;
        if ( v5 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v12 = v2;
      (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)(v2, 0, 0);
    }
    while ( *((_DWORD *)v2 + 15) && *((LPVOID *)v2 + 13) != TlsGetValue(dwTlsIndex) );
    ++*((_DWORD *)v2 + 14);
    if ( !ResetEvent(*((HANDLE *)v2 + 9)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  v6 = *((_QWORD *)this + 6);
  if ( !v6 )
  {
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v6 + 8))(v6 + 8, 0, 0);
  ++*(_DWORD *)(v6 + 64);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v6 + 8) + 8LL))(v6 + 8);
  v7 = *((_QWORD *)this + 6);
  if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)(v2, 0, 0);
    v8 = (*((_DWORD *)v2 + 14))-- == 1;
    if ( v8 && !SetEvent(*((HANDLE *)v2 + 9)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return (struct CReaderProxy *)v7;
}

```

## disassembly

```asm
0x18000cf60  mov     [rsp+arg_18], rbx
0x18000cf65  push    rbp
0x18000cf66  push    rsi
0x18000cf67  push    rdi
0x18000cf68  sub     rsp, 20h
0x18000cf6c  mov     rbp, rcx
0x18000cf6f  lea     rbx, [rcx+38h]
0x18000cf73  mov     [rsp+38h+arg_8], rbx
0x18000cf78  mov     [rsp+38h+pExceptionObject], rbx
0x18000cf7d  mov     rax, [rbx]
0x18000cf80  xor     r8d, r8d
0x18000cf83  xor     edx, edx
0x18000cf85  mov     rcx, rbx
0x18000cf88  mov     rax, [rax]
0x18000cf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf90  nop
0x18000cf91  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000cf97  call    cs:__imp_TlsGetValue
0x18000cf9d  cmp     [rbx+68h], rax
0x18000cfa1  jz      loc_18000D0EA
0x18000cfa7  mov     rax, [rbx]
0x18000cfaa  mov     rcx, rbx
0x18000cfad  mov     rax, [rax+8]
0x18000cfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb6  nop
0x18000cfb7  mov     rdi, [rbx+58h]
0x18000cfbb  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000cfc1  call    cs:__imp_TlsGetValue
0x18000cfc7  mov     rsi, rax
0x18000cfca  xor     r9d, r9d
0x18000cfcd  mov     r8, rsi
0x18000cfd0  mov     rdx, rdi
0x18000cfd3  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000cfd8  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000cfdd  cmp     eax, 1
0x18000cfe0  jnz     loc_18000D0C7
0x18000cfe6  mov     [rsp+38h+arg_10], rbx
0x18000cfeb  mov     rax, [rbx]
0x18000cfee  xor     r8d, r8d
0x18000cff1  xor     edx, edx
0x18000cff3  mov     rcx, rbx
0x18000cff6  mov     rax, [rax]
0x18000cff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cffe  nop
0x18000cfff  cmp     dword ptr [rbx+3Ch], 0
0x18000d003  jnz     loc_18000D10B
0x18000d009  inc     dword ptr [rbx+38h]
0x18000d00c  mov     rcx, [rbx+48h]; hEvent
0x18000d010  call    cs:__imp_ResetEvent
0x18000d016  test    eax, eax
0x18000d018  jz      loc_18000D136
0x18000d01e  mov     rax, [rbx]
0x18000d021  mov     rcx, rbx
0x18000d024  mov     rax, [rax+8]
0x18000d028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02d  nop
0x18000d02e  mov     rdi, [rbp+30h]
0x18000d032  test    rdi, rdi
0x18000d035  jz      loc_18000D152
0x18000d03b  mov     rax, [rdi+8]
0x18000d03f  xor     r8d, r8d
0x18000d042  xor     edx, edx
0x18000d044  lea     rcx, [rdi+8]
0x18000d048  mov     rax, [rax]
0x18000d04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d050  inc     dword ptr [rdi+40h]
0x18000d053  mov     rax, [rdi+8]
0x18000d057  lea     rcx, [rdi+8]
0x18000d05b  mov     rax, [rax+8]
0x18000d05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d064  nop
0x18000d065  mov     rdi, [rbp+30h]
0x18000d069  mov     rax, [rbx]
0x18000d06c  mov     rcx, rbx
0x18000d06f  mov     rax, [rax+10h]
0x18000d073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d078  test    eax, eax
0x18000d07a  jnz     short loc_18000D0B7
0x18000d07c  mov     rax, [rbx]
0x18000d07f  xor     r8d, r8d
0x18000d082  xor     edx, edx
0x18000d084  mov     rcx, rbx
0x18000d087  mov     rax, [rax]
0x18000d08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08f  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000d093  jnz     short loc_18000D0A7
0x18000d095  mov     rcx, [rbx+48h]; hEvent
0x18000d099  call    cs:__imp_SetEvent
0x18000d09f  test    eax, eax
0x18000d0a1  jz      loc_18000D16C
0x18000d0a7  mov     rcx, [rbx]
0x18000d0aa  mov     rax, [rcx+8]
0x18000d0ae  mov     rcx, rbx
0x18000d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b6  nop
0x18000d0b7  mov     rax, rdi
0x18000d0ba  mov     rbx, [rsp+38h+arg_18]
0x18000d0bf  add     rsp, 20h
0x18000d0c3  pop     rdi
0x18000d0c4  pop     rsi
0x18000d0c5  pop     rbp
0x18000d0c6  retn
0x18000d0c7  cmp     eax, 2
0x18000d0ca  jnz     loc_18000CFCA
0x18000d0d0  mov     dword ptr [rsp+38h+pExceptionObject], 80100002h
0x18000d0d8  lea     rdx, _TI1K; pThrowInfo
0x18000d0df  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d0e4  call    _CxxThrowException_0
0x18000d0ea  inc     dword ptr [rbx+38h]
0x18000d0ed  mov     rcx, rbx; this
0x18000d0f0  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000d0f5  nop
0x18000d0f6  mov     rax, [rbx]
0x18000d0f9  mov     rcx, rbx
0x18000d0fc  mov     rax, [rax+8]
0x18000d100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d105  nop
0x18000d106  jmp     loc_18000D02E
0x18000d10b  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d111  call    cs:__imp_TlsGetValue
0x18000d117  cmp     [rbx+68h], rax
0x18000d11b  jz      loc_18000D009
0x18000d121  mov     rax, [rbx]
0x18000d124  mov     rcx, rbx
0x18000d127  mov     rax, [rax+8]
0x18000d12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d130  nop
0x18000d131  jmp     loc_18000CFB7
0x18000d136  call    cs:__imp_GetLastError
0x18000d13c  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000d140  lea     rdx, _TI1K; pThrowInfo
0x18000d147  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d14c  call    _CxxThrowException_0
0x18000d152  mov     dword ptr [rsp+38h+pExceptionObject], 80100017h
0x18000d15a  lea     rdx, _TI1K; pThrowInfo
0x18000d161  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d166  call    _CxxThrowException_0
0x18000d16c  call    cs:__imp_GetLastError
0x18000d172  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000d176  lea     rdx, _TI1K; pThrowInfo
0x18000d17d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d182  call    _CxxThrowException_0
```
