# ABO_NODE::ABO_NODE(ABO_TREE *,int)

- ea: `0x180006484`
- end: `0x180006562`
- name: `??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z`
- size: `222`
- prototype: `ABO_NODE *__fastcall(ABO_NODE *__hidden this, struct ABO_TREE *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f98`
- `0x180007148`
- `0x180008050`
- `0x180010880`
- `0x180011dd0`
- `0x180012cb0`
- `0x180014b90`
- `0x1800259c0`
- `0x18002ac00`

## callees

- `0x180006484`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800064c6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800064d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006526`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800064c6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800064d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006526`
- `iisutil!?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x18000654f`
- `iisutil!?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x18000654f`

## pseudocode

```c
ABO_NODE *__fastcall ABO_NODE::ABO_NODE(ABO_NODE *this, struct ABO_TREE *a2, int a3)
{
  BIG_REF_TRACE *v6; // rcx

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &ABO_NODE::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 8;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  STRU::STRU((ABO_NODE *)((char *)this + 56));
  *((_QWORD *)this + 14) = 0;
  STRU::STRU((ABO_NODE *)((char *)this + 120));
  *((_QWORD *)this + 22) = a2;
  *((_QWORD *)this + 23) = &PROPERTY_BAG::`vftable';
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = a3;
  *((_QWORD *)this + 29) = 0;
  *(_QWORD *)((char *)this + 244) = 0;
  STRU::STRU((ABO_NODE *)((char *)this + 256));
  v6 = (BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace;
  *((_DWORD *)this + 60) = _InterlockedIncrement(&ABO_NODE::sm_lCurrentDataSetNumber);
  if ( v6 )
    BIG_REF_TRACE::TraceCreate(v6, this);
  return this;
}

```

## disassembly

```asm
0x180006484  push    rbx
0x180006486  push    rsi
0x180006487  push    rdi
0x180006488  push    r14
0x18000648a  sub     rsp, 28h
0x18000648e  mov     dword ptr [rcx+8], 1
0x180006495  lea     rax, ??_7ABO_NODE@@6B@; const ABO_NODE::`vftable'
0x18000649c  mov     [rcx], rax
0x18000649f  xor     r14d, r14d
0x1800064a2  mov     [rcx+10h], r14
0x1800064a6  mov     rsi, rcx
0x1800064a9  mov     dword ptr [rcx+18h], 8
0x1800064b0  mov     edi, r8d
0x1800064b3  mov     [rcx+20h], r14
0x1800064b7  mov     rbx, rdx
0x1800064ba  mov     [rcx+28h], r14
0x1800064be  mov     [rcx+30h], r14
0x1800064c2  add     rcx, 38h ; '8'
0x1800064c6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800064cc  lea     rcx, [rsi+78h]
0x1800064d0  mov     [rsi+70h], r14
0x1800064d4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800064da  mov     [rsi+0B0h], rbx
0x1800064e1  lea     rax, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x1800064e8  mov     [rsi+0B8h], rax
0x1800064ef  lea     rcx, [rsi+100h]
0x1800064f6  mov     [rsi+0C0h], r14
0x1800064fd  mov     [rsi+0C8h], r14
0x180006504  mov     [rsi+0D0h], r14
0x18000650b  mov     [rsi+0D8h], r14
0x180006512  mov     [rsi+0E0h], edi
0x180006518  mov     [rsi+0E8h], r14
0x18000651f  mov     [rsi+0F4h], r14
0x180006526  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000652c  lea     eax, [r14+1]
0x180006530  lock xadd cs:?sm_lCurrentDataSetNumber@ABO_NODE@@0JA, eax; long ABO_NODE::sm_lCurrentDataSetNumber
0x180006538  mov     rcx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x18000653f  inc     eax
0x180006541  mov     [rsi+0F0h], eax
0x180006547  test    rcx, rcx
0x18000654a  jz      short loc_180006555
0x18000654c  mov     rdx, rsi
0x18000654f  call    cs:__imp_?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z; BIG_REF_TRACE::TraceCreate(void *)
0x180006555  mov     rax, rsi
0x180006558  add     rsp, 28h
0x18000655c  pop     r14
0x18000655e  pop     rdi
0x18000655f  pop     rsi
0x180006560  pop     rbx
0x180006561  retn
```
