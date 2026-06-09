# ATL::CAtlModule::Term(void)

- ea: `0x18000d980`
- end: `0x18000da37`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000aec0`
- `0x18000e134`
- `0x18003e360`

## callees

- `0x180002714`
- `0x18000d980`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d9c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d9c0`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18000d980  push    rbx
0x18000d982  push    rsi
0x18000d983  push    rdi
0x18000d984  push    r14
0x18000d986  push    r15
0x18000d988  sub     rsp, 20h
0x18000d98c  mov     rdi, rcx
0x18000d98f  lea     r14, [rcx+8]
0x18000d993  cmp     dword ptr [r14], 0
0x18000d997  jz      loc_18000DA2B
0x18000d99d  cmp     qword ptr [rcx+10h], 0
0x18000d9a2  jz      short loc_18000DA05
0x18000d9a4  mov     rax, rcx
0x18000d9a7  neg     rax
0x18000d9aa  sbb     rsi, rsi
0x18000d9ad  and     rsi, r14
0x18000d9b0  jnz     short loc_18000D9C7
0x18000d9b2  xor     r9d, r9d; lpArguments
0x18000d9b5  xor     r8d, r8d; nNumberOfArguments
0x18000d9b8  lea     edx, [rsi+1]; dwExceptionFlags
0x18000d9bb  mov     ecx, 0C0000005h; dwExceptionCode
0x18000d9c0  call    cs:__imp_RaiseException
0x18000d9c6  int     3; Trap to Debugger
0x18000d9c7  mov     r15, [rsi+8]
0x18000d9cb  test    r15, r15
0x18000d9ce  jz      short loc_18000D9F5
0x18000d9d0  mov     rcx, [r15+8]
0x18000d9d4  mov     rax, [r15]
0x18000d9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9dc  mov     rbx, [r15+10h]
0x18000d9e0  mov     edx, 18h
0x18000d9e5  mov     rcx, r15; Block
0x18000d9e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d9ed  mov     r15, rbx
0x18000d9f0  test    rbx, rbx
0x18000d9f3  jnz     short loc_18000D9D0
0x18000d9f5  mov     qword ptr [rsi+8], 0
0x18000d9fd  mov     qword ptr [rdi+10h], 0
0x18000da05  mov     rcx, [rdi+40h]
0x18000da09  test    rcx, rcx
0x18000da0c  jz      short loc_18000DA1A
0x18000da0e  mov     rax, [rcx]
0x18000da11  mov     rax, [rax+10h]
0x18000da15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da1a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000da1e  call    cs:__imp_DeleteCriticalSection
0x18000da24  mov     dword ptr [r14], 0
0x18000da2b  add     rsp, 20h
0x18000da2f  pop     r15
0x18000da31  pop     r14
0x18000da33  pop     rdi
0x18000da34  pop     rsi
0x18000da35  pop     rbx
0x18000da36  retn
```
