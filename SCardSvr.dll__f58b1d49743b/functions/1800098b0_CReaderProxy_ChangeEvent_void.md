# CReaderProxy::ChangeEvent(void)

- ea: `0x1800098b0`
- end: `0x180009b24`
- name: `?ChangeEvent@CReaderProxy@@QEAAPEAXXZ`
- size: `628`
- prototype: `__int64 __fastcall(CReaderProxy *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a310`

## callees

- `0x1800098b0`
- `0x18000c870`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000998a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000998a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009a1e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009911`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000993b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009a9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009911`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000993b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009a9c`

## pseudocode

```c
__int64 __fastcall CReaderProxy::ChangeEvent(CReaderProxy *this)
{
  __int64 v2; // rbx
  __int64 v3; // rbp
  LPVOID Value; // r14
  unsigned int v5; // eax
  unsigned int *v6; // rdi
  __int64 v7; // rsi
  bool v8; // zf
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h]

  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v2 = *(_QWORD *)this + 512LL;
  pExceptionObject = v2;
  v11 = v2;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
  if ( *(LPVOID *)(v2 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v2 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      v3 = *(_QWORD *)(v2 + 88);
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
      v11 = v2;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    }
    while ( *(_DWORD *)(v2 + 60) && *(LPVOID *)(v2 + 104) != TlsGetValue(dwTlsIndex) );
    ++*(_DWORD *)(v2 + 56);
    if ( !ResetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  v6 = (unsigned int *)(*(_QWORD *)this + 416LL);
  (**(void (__fastcall ***)(unsigned int *, _QWORD, _QWORD))v6)(v6, 0, 0);
  v7 = *(_QWORD *)&v6[2 * v6[22] + 14];
  (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    v8 = (*(_DWORD *)(v2 + 56))-- == 1;
    if ( v8 && !SetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return v7;
}

```

## disassembly

```asm
0x1800098b0  mov     [rsp+arg_10], rbx
0x1800098b5  mov     [rsp+arg_18], rbp
0x1800098ba  push    rsi
0x1800098bb  push    rdi
0x1800098bc  push    r14
0x1800098be  sub     rsp, 20h
0x1800098c2  mov     rsi, rcx
0x1800098c5  mov     rax, [rcx+8]
0x1800098c9  xor     r8d, r8d
0x1800098cc  xor     edx, edx
0x1800098ce  add     rcx, 8
0x1800098d2  mov     rax, [rax]
0x1800098d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098da  mov     rbx, [rsi]
0x1800098dd  test    rbx, rbx
0x1800098e0  jz      loc_180009AC1
0x1800098e6  add     rbx, 200h
0x1800098ed  mov     [rsp+38h+pExceptionObject], rbx
0x1800098f2  mov     [rsp+38h+arg_8], rbx
0x1800098f7  mov     rax, [rbx]
0x1800098fa  xor     r8d, r8d
0x1800098fd  xor     edx, edx
0x1800098ff  mov     rcx, rbx
0x180009902  mov     rax, [rax]
0x180009905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000990a  nop
0x18000990b  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009911  call    cs:__imp_TlsGetValue
0x180009917  cmp     [rbx+68h], rax
0x18000991b  jz      loc_180009A75
0x180009921  mov     rax, [rbx]
0x180009924  mov     rcx, rbx
0x180009927  mov     rax, [rax+8]
0x18000992b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009930  nop
0x180009931  mov     rbp, [rbx+58h]
0x180009935  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000993b  call    cs:__imp_TlsGetValue
0x180009941  mov     r14, rax
0x180009944  xor     r9d, r9d
0x180009947  mov     r8, r14
0x18000994a  mov     rdx, rbp
0x18000994d  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x180009952  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x180009957  cmp     eax, 1
0x18000995a  jnz     loc_180009A52
0x180009960  mov     [rsp+38h+arg_8], rbx
0x180009965  mov     rax, [rbx]
0x180009968  xor     r8d, r8d
0x18000996b  xor     edx, edx
0x18000996d  mov     rcx, rbx
0x180009970  mov     rax, [rax]
0x180009973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009978  nop
0x180009979  cmp     dword ptr [rbx+3Ch], 0
0x18000997d  jnz     loc_180009A96
0x180009983  inc     dword ptr [rbx+38h]
0x180009986  mov     rcx, [rbx+48h]; hEvent
0x18000998a  call    cs:__imp_ResetEvent
0x180009990  test    eax, eax
0x180009992  jz      loc_180009AEC
0x180009998  mov     rax, [rbx]
0x18000999b  mov     rcx, rbx
0x18000999e  mov     rax, [rax+8]
0x1800099a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a7  nop
0x1800099a8  mov     rax, [rsi+8]
0x1800099ac  lea     rcx, [rsi+8]
0x1800099b0  mov     rax, [rax+8]
0x1800099b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099b9  mov     rdi, [rsi]
0x1800099bc  add     rdi, 1A0h
0x1800099c3  mov     rax, [rdi]
0x1800099c6  xor     r8d, r8d
0x1800099c9  xor     edx, edx
0x1800099cb  mov     rcx, rdi
0x1800099ce  mov     rax, [rax]
0x1800099d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d6  mov     eax, [rdi+58h]
0x1800099d9  mov     rsi, [rdi+rax*8+38h]
0x1800099de  mov     rax, [rdi]
0x1800099e1  mov     rcx, rdi
0x1800099e4  mov     rax, [rax+8]
0x1800099e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ed  nop
0x1800099ee  mov     rax, [rbx]
0x1800099f1  mov     rcx, rbx
0x1800099f4  mov     rax, [rax+10h]
0x1800099f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fd  test    eax, eax
0x1800099ff  jnz     short loc_180009A3C
0x180009a01  mov     rax, [rbx]
0x180009a04  xor     r8d, r8d
0x180009a07  xor     edx, edx
0x180009a09  mov     rcx, rbx
0x180009a0c  mov     rax, [rax]
0x180009a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a14  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180009a18  jnz     short loc_180009A2C
0x180009a1a  mov     rcx, [rbx+48h]; hEvent
0x180009a1e  call    cs:__imp_SetEvent
0x180009a24  test    eax, eax
0x180009a26  jz      loc_180009B08
0x180009a2c  mov     rcx, [rbx]
0x180009a2f  mov     rax, [rcx+8]
0x180009a33  mov     rcx, rbx
0x180009a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a3b  nop
0x180009a3c  mov     rax, rsi
0x180009a3f  mov     rbx, [rsp+38h+arg_10]
0x180009a44  mov     rbp, [rsp+38h+arg_18]
0x180009a49  add     rsp, 20h
0x180009a4d  pop     r14
0x180009a4f  pop     rdi
0x180009a50  pop     rsi
0x180009a51  retn
0x180009a52  cmp     eax, 2
0x180009a55  jnz     loc_180009944
0x180009a5b  mov     dword ptr [rsp+38h+pExceptionObject], 80100002h
0x180009a63  lea     rdx, _TI1K; pThrowInfo
0x180009a6a  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009a6f  call    _CxxThrowException_0
0x180009a75  inc     dword ptr [rbx+38h]
0x180009a78  mov     rcx, rbx; this
0x180009a7b  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180009a80  nop
0x180009a81  mov     rax, [rbx]
0x180009a84  mov     rcx, rbx
0x180009a87  mov     rax, [rax+8]
0x180009a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a90  nop
0x180009a91  jmp     loc_1800099A8
0x180009a96  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009a9c  call    cs:__imp_TlsGetValue
0x180009aa2  cmp     [rbx+68h], rax
0x180009aa6  jz      loc_180009983
0x180009aac  mov     rax, [rbx]
0x180009aaf  mov     rcx, rbx
0x180009ab2  mov     rax, [rax+8]
0x180009ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009abb  nop
0x180009abc  jmp     loc_180009931
0x180009ac1  mov     rax, [rsi+8]
0x180009ac5  lea     rcx, [rsi+8]
0x180009ac9  mov     rax, [rax+8]
0x180009acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad2  mov     dword ptr [rsp+38h+pExceptionObject], 80100017h
0x180009ada  lea     rdx, _TI1K; pThrowInfo
0x180009ae1  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009ae6  call    _CxxThrowException_0
0x180009aec  call    cs:__imp_GetLastError
0x180009af2  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x180009af6  lea     rdx, _TI1K; pThrowInfo
0x180009afd  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009b02  call    _CxxThrowException_0
0x180009b08  call    cs:__imp_GetLastError
0x180009b0e  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x180009b12  lea     rdx, _TI1K; pThrowInfo
0x180009b19  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009b1e  call    _CxxThrowException_0
```
