# ATL::CAtlModule::Term(void)

- ea: `0x14002487c`
- end: `0x14002493c`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `192`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001c530`
- `0x14004e3f0`

## callees

- `0x140003448`
- `0x14002487c`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140024923`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140024923`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400248c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400248c5`

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
0x14002487c  push    rbx
0x14002487e  push    rsi
0x14002487f  push    rdi
0x140024880  push    r14
0x140024882  push    r15
0x140024884  sub     rsp, 30h
0x140024888  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140024891  mov     rdi, rcx
0x140024894  lea     r14, [rcx+8]
0x140024898  cmp     dword ptr [r14], 0
0x14002489c  jz      loc_140024930
0x1400248a2  cmp     qword ptr [rcx+10h], 0
0x1400248a7  jz      short loc_14002490A
0x1400248a9  mov     rax, rcx
0x1400248ac  neg     rax
0x1400248af  sbb     rsi, rsi
0x1400248b2  and     rsi, r14
0x1400248b5  jnz     short loc_1400248CC
0x1400248b7  xor     r9d, r9d; lpArguments
0x1400248ba  xor     r8d, r8d; nNumberOfArguments
0x1400248bd  lea     edx, [rsi+1]; dwExceptionFlags
0x1400248c0  mov     ecx, 0C0000005h; dwExceptionCode
0x1400248c5  call    cs:__imp_RaiseException
0x1400248cb  int     3; Trap to Debugger
0x1400248cc  mov     r15, [rsi+8]
0x1400248d0  test    r15, r15
0x1400248d3  jz      short loc_1400248FA
0x1400248d5  mov     rcx, [r15+8]
0x1400248d9  mov     rax, [r15]
0x1400248dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400248e1  mov     rbx, [r15+10h]
0x1400248e5  mov     edx, 18h
0x1400248ea  mov     rcx, r15; Block
0x1400248ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400248f2  mov     r15, rbx
0x1400248f5  test    rbx, rbx
0x1400248f8  jnz     short loc_1400248D5
0x1400248fa  mov     qword ptr [rsi+8], 0
0x140024902  mov     qword ptr [rdi+10h], 0
0x14002490a  mov     rcx, [rdi+40h]
0x14002490e  test    rcx, rcx
0x140024911  jz      short loc_14002491F
0x140024913  mov     rax, [rcx]
0x140024916  mov     rax, [rax+10h]
0x14002491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002491f  lea     rcx, [rdi+18h]; lpCriticalSection
0x140024923  call    cs:__imp_DeleteCriticalSection
0x140024929  mov     dword ptr [r14], 0
0x140024930  add     rsp, 30h
0x140024934  pop     r15
0x140024936  pop     r14
0x140024938  pop     rdi
0x140024939  pop     rsi
0x14002493a  pop     rbx
0x14002493b  retn
```
