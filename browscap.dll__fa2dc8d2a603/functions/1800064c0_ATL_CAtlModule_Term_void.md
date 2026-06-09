# ATL::CAtlModule::Term(void)

- ea: `0x1800064c0`
- end: `0x180006565`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800024d8`
- `0x1800026a0`
- `0x1800026f0`
- `0x18000656c`
- `0x18000c160`

## callees

- `0x1800064c0`
- `0x18000701c`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x18000650a`
- `msvcrt!free` at `0x18000650a`
- `KERNEL32!DeleteCriticalSection` at `0x180006541`
- `KERNEL32!DeleteCriticalSection` at `0x180006541`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180006564LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          free(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x1800064c0  push    rbx
0x1800064c2  push    rsi
0x1800064c3  push    rdi
0x1800064c4  push    r14
0x1800064c6  push    r15
0x1800064c8  sub     rsp, 20h
0x1800064cc  mov     rdi, rcx
0x1800064cf  lea     r14, [rcx+8]
0x1800064d3  cmp     dword ptr [r14], 0
0x1800064d7  jz      short loc_18000654E
0x1800064d9  cmp     qword ptr [rcx+10h], 0
0x1800064de  jz      short loc_180006528
0x1800064e0  mov     rax, rcx
0x1800064e3  neg     rax
0x1800064e6  sbb     rsi, rsi
0x1800064e9  and     rsi, r14
0x1800064ec  jz      short loc_18000655A
0x1800064ee  mov     r15, [rsi+8]
0x1800064f2  test    r15, r15
0x1800064f5  jz      short loc_180006518
0x1800064f7  mov     rcx, [r15+8]
0x1800064fb  mov     rax, [r15]
0x1800064fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006503  mov     rbx, [r15+10h]
0x180006507  mov     rcx, r15; Block
0x18000650a  call    cs:__imp_free
0x180006510  mov     r15, rbx
0x180006513  test    rbx, rbx
0x180006516  jnz     short loc_1800064F7
0x180006518  mov     qword ptr [rsi+8], 0
0x180006520  mov     qword ptr [rdi+10h], 0
0x180006528  mov     rcx, [rdi+40h]
0x18000652c  test    rcx, rcx
0x18000652f  jz      short loc_18000653D
0x180006531  mov     rax, [rcx]
0x180006534  mov     rax, [rax+10h]
0x180006538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006541  call    cs:__imp_DeleteCriticalSection
0x180006547  mov     dword ptr [r14], 0
0x18000654e  add     rsp, 20h
0x180006552  pop     r15
0x180006554  pop     r14
0x180006556  pop     rdi
0x180006557  pop     rsi
0x180006558  pop     rbx
0x180006559  retn
0x18000655a  mov     ecx, 0C0000005h; unsigned int
0x18000655f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
