# CReaderProxy::ActivityHash(void)

- ea: `0x180009b30`
- end: `0x180009d7a`
- name: `?ActivityHash@CReaderProxy@@QEAAGXZ`
- size: `586`
- prototype: `__int64 __fastcall(CReaderProxy *this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180007910`
- `0x18000a310`

## callees

- `0x180009230`
- `0x180009b30`
- `0x18000c870`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009c0a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009c0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009c74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009b91`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009bbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009cf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009b91`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009bbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009cf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReaderProxy::ActivityHash(CReaderProxy *this)
{
  __int64 v2; // rbx
  __int64 v3; // rbp
  LPVOID Value; // r14
  unsigned int v5; // eax
  unsigned __int16 v6; // di
  bool v7; // zf
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h]

  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v2 = *(_QWORD *)this + 512LL;
  pExceptionObject = v2;
  v10 = v2;
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
      v10 = v2;
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
  v6 = CReader::ActivityHash(*(CReader **)this);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    v7 = (*(_DWORD *)(v2 + 56))-- == 1;
    if ( v7 && !SetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x180009b30  mov     [rsp+arg_10], rbx
0x180009b35  mov     [rsp+arg_18], rbp
0x180009b3a  push    rsi
0x180009b3b  push    rdi
0x180009b3c  push    r14
0x180009b3e  sub     rsp, 20h
0x180009b42  mov     rsi, rcx
0x180009b45  mov     rax, [rcx+8]
0x180009b49  xor     r8d, r8d
0x180009b4c  xor     edx, edx
0x180009b4e  add     rcx, 8
0x180009b52  mov     rax, [rax]
0x180009b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5a  mov     rbx, [rsi]
0x180009b5d  test    rbx, rbx
0x180009b60  jz      loc_180009D17
0x180009b66  add     rbx, 200h
0x180009b6d  mov     [rsp+38h+pExceptionObject], rbx
0x180009b72  mov     [rsp+38h+arg_8], rbx
0x180009b77  mov     rax, [rbx]
0x180009b7a  xor     r8d, r8d
0x180009b7d  xor     edx, edx
0x180009b7f  mov     rcx, rbx
0x180009b82  mov     rax, [rax]
0x180009b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b8a  nop
0x180009b8b  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009b91  call    cs:__imp_TlsGetValue
0x180009b97  cmp     [rbx+68h], rax
0x180009b9b  jz      loc_180009CCB
0x180009ba1  mov     rax, [rbx]
0x180009ba4  mov     rcx, rbx
0x180009ba7  mov     rax, [rax+8]
0x180009bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb0  nop
0x180009bb1  mov     rbp, [rbx+58h]
0x180009bb5  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x180009bbb  call    cs:__imp_TlsGetValue
0x180009bc1  mov     r14, rax
0x180009bc4  xor     r9d, r9d
0x180009bc7  mov     r8, r14
0x180009bca  mov     rdx, rbp
0x180009bcd  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x180009bd2  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x180009bd7  cmp     eax, 1
0x180009bda  jnz     loc_180009CA8
0x180009be0  mov     [rsp+38h+arg_8], rbx
0x180009be5  mov     rax, [rbx]
0x180009be8  xor     r8d, r8d
0x180009beb  xor     edx, edx
0x180009bed  mov     rcx, rbx
0x180009bf0  mov     rax, [rax]
0x180009bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf8  nop
0x180009bf9  cmp     dword ptr [rbx+3Ch], 0
0x180009bfd  jnz     loc_180009CEC
0x180009c03  inc     dword ptr [rbx+38h]
0x180009c06  mov     rcx, [rbx+48h]; hEvent
0x180009c0a  call    cs:__imp_ResetEvent
0x180009c10  test    eax, eax
0x180009c12  jz      loc_180009D42
0x180009c18  mov     rax, [rbx]
0x180009c1b  mov     rcx, rbx
0x180009c1e  mov     rax, [rax+8]
0x180009c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c27  nop
0x180009c28  mov     rax, [rsi+8]
0x180009c2c  lea     rcx, [rsi+8]
0x180009c30  mov     rax, [rax+8]
0x180009c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c39  mov     rcx, [rsi]; this
0x180009c3c  call    ?ActivityHash@CReader@@QEAAGXZ; CReader::ActivityHash(void)
0x180009c41  movzx   edi, ax
0x180009c44  mov     rcx, [rbx]
0x180009c47  mov     rax, [rcx+10h]
0x180009c4b  mov     rcx, rbx
0x180009c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c53  test    eax, eax
0x180009c55  jnz     short loc_180009C92
0x180009c57  mov     rcx, [rbx]
0x180009c5a  mov     rax, [rcx]
0x180009c5d  xor     r8d, r8d
0x180009c60  xor     edx, edx
0x180009c62  mov     rcx, rbx
0x180009c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6a  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180009c6e  jnz     short loc_180009C82
0x180009c70  mov     rcx, [rbx+48h]; hEvent
0x180009c74  call    cs:__imp_SetEvent
0x180009c7a  test    eax, eax
0x180009c7c  jz      loc_180009D5E
0x180009c82  mov     rax, [rbx]
0x180009c85  mov     rcx, rbx
0x180009c88  mov     rax, [rax+8]
0x180009c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c91  nop
0x180009c92  movzx   eax, di
0x180009c95  mov     rbx, [rsp+38h+arg_10]
0x180009c9a  mov     rbp, [rsp+38h+arg_18]
0x180009c9f  add     rsp, 20h
0x180009ca3  pop     r14
0x180009ca5  pop     rdi
0x180009ca6  pop     rsi
0x180009ca7  retn
0x180009ca8  cmp     eax, 2
0x180009cab  jnz     loc_180009BC4
0x180009cb1  mov     dword ptr [rsp+38h+pExceptionObject], 80100002h
0x180009cb9  lea     rdx, _TI1K; pThrowInfo
0x180009cc0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009cc5  call    _CxxThrowException_0
0x180009ccb  inc     dword ptr [rbx+38h]
0x180009cce  mov     rcx, rbx; this
0x180009cd1  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180009cd6  nop
0x180009cd7  mov     rax, [rbx]
0x180009cda  mov     rcx, rbx
0x180009cdd  mov     rax, [rax+8]
0x180009ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ce6  nop
0x180009ce7  jmp     loc_180009C28
0x180009cec  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009cf2  call    cs:__imp_TlsGetValue
0x180009cf8  cmp     [rbx+68h], rax
0x180009cfc  jz      loc_180009C03
0x180009d02  mov     rax, [rbx]
0x180009d05  mov     rcx, rbx
0x180009d08  mov     rax, [rax+8]
0x180009d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d11  nop
0x180009d12  jmp     loc_180009BB1
0x180009d17  mov     rax, [rsi+8]
0x180009d1b  lea     rcx, [rsi+8]
0x180009d1f  mov     rax, [rax+8]
0x180009d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d28  mov     dword ptr [rsp+38h+pExceptionObject], 80100017h
0x180009d30  lea     rdx, _TI1K; pThrowInfo
0x180009d37  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009d3c  call    _CxxThrowException_0
0x180009d42  call    cs:__imp_GetLastError
0x180009d48  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x180009d4c  lea     rdx, _TI1K; pThrowInfo
0x180009d53  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009d58  call    _CxxThrowException_0
0x180009d5e  call    cs:__imp_GetLastError
0x180009d64  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x180009d68  lea     rdx, _TI1K; pThrowInfo
0x180009d6f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009d74  call    _CxxThrowException_0
```
