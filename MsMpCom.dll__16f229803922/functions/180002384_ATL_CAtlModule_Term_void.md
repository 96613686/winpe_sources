# ATL::CAtlModule::Term(void)

- ea: `0x180002384`
- end: `0x180002429`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002200`
- `0x1800025d8`
- `0x180009c10`

## callees

- `0x180002384`
- `0x180002444`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800023ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800023ce`
- `KERNEL32!DeleteCriticalSection` at `0x180002405`
- `KERNEL32!DeleteCriticalSection` at `0x180002405`

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
        JUMPOUT(0x180002428LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
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
0x180002384  push    rbx
0x180002386  push    rsi
0x180002387  push    rdi
0x180002388  push    r14
0x18000238a  push    r15
0x18000238c  sub     rsp, 20h
0x180002390  mov     rdi, rcx
0x180002393  lea     r14, [rcx+8]
0x180002397  cmp     dword ptr [r14], 0
0x18000239b  jz      short loc_180002412
0x18000239d  cmp     qword ptr [rcx+10h], 0
0x1800023a2  jz      short loc_1800023EC
0x1800023a4  mov     rax, rcx
0x1800023a7  neg     rax
0x1800023aa  sbb     rsi, rsi
0x1800023ad  and     rsi, r14
0x1800023b0  jz      short loc_18000241E
0x1800023b2  mov     r15, [rsi+8]
0x1800023b6  test    r15, r15
0x1800023b9  jz      short loc_1800023DC
0x1800023bb  mov     rcx, [r15+8]
0x1800023bf  mov     rax, [r15]
0x1800023c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c7  mov     rbx, [r15+10h]
0x1800023cb  mov     rcx, r15
0x1800023ce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800023d4  mov     r15, rbx
0x1800023d7  test    rbx, rbx
0x1800023da  jnz     short loc_1800023BB
0x1800023dc  mov     qword ptr [rsi+8], 0
0x1800023e4  mov     qword ptr [rdi+10h], 0
0x1800023ec  mov     rcx, [rdi+40h]
0x1800023f0  test    rcx, rcx
0x1800023f3  jz      short loc_180002401
0x1800023f5  mov     rax, [rcx]
0x1800023f8  mov     rax, [rax+10h]
0x1800023fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002401  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002405  call    cs:__imp_DeleteCriticalSection
0x18000240b  mov     dword ptr [r14], 0
0x180002412  add     rsp, 20h
0x180002416  pop     r15
0x180002418  pop     r14
0x18000241a  pop     rdi
0x18000241b  pop     rsi
0x18000241c  pop     rbx
0x18000241d  retn
0x18000241e  mov     ecx, 0C0000005h; unsigned int
0x180002423  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
