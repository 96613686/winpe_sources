# ATL::CAtlModule::Term(void)

- ea: `0x140029fc4`
- end: `0x14002a084`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `192`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140010fe0`
- `0x14006fa00`

## callees

- `0x140005264`
- `0x140029fc4`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002a06b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002a06b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14002a00d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14002a00d`

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
0x140029fc4  push    rbx
0x140029fc6  push    rsi
0x140029fc7  push    rdi
0x140029fc8  push    r14
0x140029fca  push    r15
0x140029fcc  sub     rsp, 30h
0x140029fd0  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140029fd9  mov     rdi, rcx
0x140029fdc  lea     r14, [rcx+8]
0x140029fe0  cmp     dword ptr [r14], 0
0x140029fe4  jz      loc_14002A078
0x140029fea  cmp     qword ptr [rcx+10h], 0
0x140029fef  jz      short loc_14002A052
0x140029ff1  mov     rax, rcx
0x140029ff4  neg     rax
0x140029ff7  sbb     rsi, rsi
0x140029ffa  and     rsi, r14
0x140029ffd  jnz     short loc_14002A014
0x140029fff  xor     r9d, r9d; lpArguments
0x14002a002  xor     r8d, r8d; nNumberOfArguments
0x14002a005  lea     edx, [rsi+1]; dwExceptionFlags
0x14002a008  mov     ecx, 0C0000005h; dwExceptionCode
0x14002a00d  call    cs:__imp_RaiseException
0x14002a013  int     3; Trap to Debugger
0x14002a014  mov     r15, [rsi+8]
0x14002a018  test    r15, r15
0x14002a01b  jz      short loc_14002A042
0x14002a01d  mov     rcx, [r15+8]
0x14002a021  mov     rax, [r15]
0x14002a024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a029  mov     rbx, [r15+10h]
0x14002a02d  mov     edx, 18h
0x14002a032  mov     rcx, r15; Block
0x14002a035  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002a03a  mov     r15, rbx
0x14002a03d  test    rbx, rbx
0x14002a040  jnz     short loc_14002A01D
0x14002a042  mov     qword ptr [rsi+8], 0
0x14002a04a  mov     qword ptr [rdi+10h], 0
0x14002a052  mov     rcx, [rdi+40h]
0x14002a056  test    rcx, rcx
0x14002a059  jz      short loc_14002A067
0x14002a05b  mov     rax, [rcx]
0x14002a05e  mov     rax, [rax+10h]
0x14002a062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a067  lea     rcx, [rdi+18h]; lpCriticalSection
0x14002a06b  call    cs:__imp_DeleteCriticalSection
0x14002a071  mov     dword ptr [r14], 0
0x14002a078  add     rsp, 30h
0x14002a07c  pop     r15
0x14002a07e  pop     r14
0x14002a080  pop     rdi
0x14002a081  pop     rsi
0x14002a082  pop     rbx
0x14002a083  retn
```
