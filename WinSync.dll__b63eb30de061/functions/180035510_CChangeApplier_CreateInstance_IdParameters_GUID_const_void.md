# CChangeApplier_CreateInstance(IdParameters *,_GUID const &,void * *)

- ea: `0x180035510`
- end: `0x1800355f7`
- name: `?CChangeApplier_CreateInstance@@YAJPEAVIdParameters@@AEBU_GUID@@PEAPEAX@Z`
- size: `231`
- prototype: `__int64 __fastcall(struct IdParameters *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002b020`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x1800318c8`
- `0x180035510`
- `0x180094010`

## string_xrefs

- `0x180035547`: `CChangeApplier_CreateInstance`
- `0x1800355ce`: `CChangeApplier_CreateInstance`

## pseudocode

```c
__int64 __fastcall CChangeApplier_CreateInstance(struct IdParameters *a1, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  CChangeApplier *v7; // rax
  CChangeApplier *v8; // rax
  CChangeApplier *v9; // rdi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      329,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier_CreateInstance");
  }
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CChangeApplier *)SeAlloc(0x2B0u);
  if ( v7 )
  {
    v8 = CChangeApplier::CChangeApplier(v7, a1);
    v9 = v8;
    if ( v8 )
    {
      v6 = (**(__int64 (__fastcall ***)(CChangeApplier *, const struct _GUID *, void **))v8)(v8, a2, a3);
      (*(void (__fastcall **)(CChangeApplier *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      330,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier_CreateInstance",
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180035510  push    rbx
0x180035512  push    rbp
0x180035513  push    rsi
0x180035514  push    rdi
0x180035515  push    r14
0x180035517  sub     rsp, 30h
0x18003551b  mov     rsi, r8
0x18003551e  mov     rbp, rdx
0x180035521  mov     rdi, rcx
0x180035524  mov     rcx, cs:WPP_GLOBAL_Control
0x18003552b  lea     r14, WPP_GLOBAL_Control
0x180035532  cmp     rcx, r14
0x180035535  jz      short loc_18003555F
0x180035537  test    byte ptr [rcx+1Ch], 8
0x18003553b  jz      short loc_18003555F
0x18003553d  cmp     byte ptr [rcx+19h], 5
0x180035541  jb      short loc_18003555F
0x180035543  mov     rcx, [rcx+10h]
0x180035547  lea     r9, aCchangeapplier_31; "CChangeApplier_CreateInstance"
0x18003554e  mov     edx, 149h
0x180035553  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003555a  call    WPP_SF_s
0x18003555f  mov     ecx, 2B0h; unsigned __int64
0x180035564  mov     qword ptr [rsi], 0
0x18003556b  mov     ebx, 8007000Eh
0x180035570  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180035575  test    rax, rax
0x180035578  jz      short loc_1800355B2
0x18003557a  mov     rdx, rdi; struct IdParameters *
0x18003557d  mov     rcx, rax; this
0x180035580  call    ??0CChangeApplier@@QEAA@PEAVIdParameters@@@Z; CChangeApplier::CChangeApplier(IdParameters *)
0x180035585  mov     rdi, rax
0x180035588  test    rax, rax
0x18003558b  jz      short loc_1800355B2
0x18003558d  mov     rax, [rax]
0x180035590  mov     r8, rsi
0x180035593  mov     rdx, rbp
0x180035596  mov     rcx, rdi
0x180035599  mov     rax, [rax]
0x18003559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355a1  mov     rcx, [rdi]
0x1800355a4  mov     ebx, eax
0x1800355a6  mov     rax, [rcx+10h]
0x1800355aa  mov     rcx, rdi
0x1800355ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355b9  cmp     rcx, r14
0x1800355bc  jz      short loc_1800355EA
0x1800355be  test    byte ptr [rcx+1Ch], 8
0x1800355c2  jz      short loc_1800355EA
0x1800355c4  cmp     byte ptr [rcx+19h], 5
0x1800355c8  jb      short loc_1800355EA
0x1800355ca  mov     rcx, [rcx+10h]
0x1800355ce  lea     r9, aCchangeapplier_31; "CChangeApplier_CreateInstance"
0x1800355d5  mov     edx, 14Ah
0x1800355da  mov     [rsp+58h+var_38], ebx
0x1800355de  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800355e5  call    WPP_SF_sD
0x1800355ea  mov     eax, ebx
0x1800355ec  add     rsp, 30h
0x1800355f0  pop     r14
0x1800355f2  pop     rdi
0x1800355f3  pop     rsi
0x1800355f4  pop     rbp
0x1800355f5  pop     rbx
0x1800355f6  retn
```
