# ATL::CAtlModule::Term(void)

- ea: `0x18000f744`
- end: `0x18000f7f6`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f000`

## callees

- `0x1800011d4`
- `0x18000f744`
- `0x180014010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000f784`
- `KERNEL32!RaiseException` at `0x18000f784`
- `KERNEL32!DeleteCriticalSection` at `0x18000f7dd`
- `KERNEL32!DeleteCriticalSection` at `0x18000f7dd`

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
0x18000f744  push    rbx
0x18000f746  push    rsi
0x18000f747  push    rdi
0x18000f748  push    r14
0x18000f74a  push    r15
0x18000f74c  sub     rsp, 20h
0x18000f750  mov     rdi, rcx
0x18000f753  lea     r14, [rcx+8]
0x18000f757  cmp     dword ptr [r14], 0
0x18000f75b  jz      loc_18000F7EA
0x18000f761  cmp     qword ptr [rcx+10h], 0
0x18000f766  jz      short loc_18000F7C4
0x18000f768  mov     rax, rcx
0x18000f76b  neg     rax
0x18000f76e  sbb     rsi, rsi
0x18000f771  and     rsi, r14
0x18000f774  jnz     short loc_18000F78B
0x18000f776  xor     r9d, r9d; lpArguments
0x18000f779  xor     r8d, r8d; nNumberOfArguments
0x18000f77c  lea     edx, [rsi+1]; dwExceptionFlags
0x18000f77f  mov     ecx, 0C0000005h; dwExceptionCode
0x18000f784  call    cs:__imp_RaiseException
0x18000f78a  int     3; Trap to Debugger
0x18000f78b  mov     r15, [rsi+8]
0x18000f78f  test    r15, r15
0x18000f792  jz      short loc_18000F7B4
0x18000f794  mov     rcx, [r15+8]
0x18000f798  mov     rax, [r15]
0x18000f79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7a0  mov     rbx, [r15+10h]
0x18000f7a4  mov     rcx, r15; Block
0x18000f7a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f7ac  mov     r15, rbx
0x18000f7af  test    rbx, rbx
0x18000f7b2  jnz     short loc_18000F794
0x18000f7b4  mov     qword ptr [rsi+8], 0
0x18000f7bc  mov     qword ptr [rdi+10h], 0
0x18000f7c4  mov     rcx, [rdi+40h]
0x18000f7c8  test    rcx, rcx
0x18000f7cb  jz      short loc_18000F7D9
0x18000f7cd  mov     rax, [rcx]
0x18000f7d0  mov     rax, [rax+10h]
0x18000f7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d9  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000f7dd  call    cs:__imp_DeleteCriticalSection
0x18000f7e3  mov     dword ptr [r14], 0
0x18000f7ea  add     rsp, 20h
0x18000f7ee  pop     r15
0x18000f7f0  pop     r14
0x18000f7f2  pop     rdi
0x18000f7f3  pop     rsi
0x18000f7f4  pop     rbx
0x18000f7f5  retn
```
