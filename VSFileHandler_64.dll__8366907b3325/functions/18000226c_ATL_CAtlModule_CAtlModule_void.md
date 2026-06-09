# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000226c`
- end: `0x180002322`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800011b0`
- `0x180025350`

## callees

- `0x18000225c`
- `0x18000226c`
- `0x180007a90`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800022ed`
- `KERNEL32!DeleteCriticalSection` at `0x1800022ed`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // r14
  __int64 v3; // rsi
  _QWORD *v4; // rbp
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v1 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005, 1u);
        JUMPOUT(0x180002321LL);
      }
      v4 = *(_QWORD **)((v1 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000226c  mov     rax, rsp
0x18000226f  mov     [rax+8], rbx
0x180002273  mov     [rax+10h], rbp
0x180002277  mov     [rax+18h], rsi
0x18000227b  mov     [rax+20h], rdi
0x18000227f  push    r14
0x180002281  sub     rsp, 20h
0x180002285  lea     r14, [rcx+8]
0x180002289  mov     rdi, rcx
0x18000228c  cmp     dword ptr [r14], 0
0x180002290  jz      short loc_1800022F7
0x180002292  cmp     qword ptr [rcx+10h], 0
0x180002297  jz      short loc_1800022DA
0x180002299  mov     rax, rcx
0x18000229c  neg     rax
0x18000229f  sbb     rsi, rsi
0x1800022a2  and     rsi, r14
0x1800022a5  jz      short loc_180002312
0x1800022a7  mov     rbp, [rsi+8]
0x1800022ab  test    rbp, rbp
0x1800022ae  jz      short loc_1800022D0
0x1800022b0  mov     rcx, [rbp+8]
0x1800022b4  call    qword ptr [rbp+0]
0x1800022b7  mov     rbx, [rbp+10h]
0x1800022bb  mov     edx, 18h
0x1800022c0  mov     rcx, rbp; Block
0x1800022c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800022c8  mov     rbp, rbx
0x1800022cb  test    rbx, rbx
0x1800022ce  jnz     short loc_1800022B0
0x1800022d0  and     qword ptr [rsi+8], 0
0x1800022d5  and     qword ptr [rdi+10h], 0
0x1800022da  mov     rcx, [rdi+40h]
0x1800022de  test    rcx, rcx
0x1800022e1  jz      short loc_1800022E9
0x1800022e3  mov     rax, [rcx]
0x1800022e6  call    qword ptr [rax+10h]
0x1800022e9  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800022ed  call    cs:__imp_DeleteCriticalSection
0x1800022f3  and     dword ptr [r14], 0
0x1800022f7  mov     rbx, [rsp+28h+arg_0]
0x1800022fc  mov     rbp, [rsp+28h+arg_8]
0x180002301  mov     rsi, [rsp+28h+arg_10]
0x180002306  mov     rdi, [rsp+28h+arg_18]
0x18000230b  add     rsp, 20h
0x18000230f  pop     r14
0x180002311  retn
0x180002312  mov     edx, 1; unsigned int
0x180002317  mov     ecx, 0C0000005h; unsigned int
0x18000231c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
