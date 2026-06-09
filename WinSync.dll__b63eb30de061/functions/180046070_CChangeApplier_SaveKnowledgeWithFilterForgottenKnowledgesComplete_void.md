# CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete(void)

- ea: `0x180046070`
- end: `0x180046157`
- name: `?SaveKnowledgeWithFilterForgottenKnowledgesComplete@CChangeApplier@@UEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x180046070`
- `0x180046160`

## string_xrefs

- `0x1800460a5`: `CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete`
- `0x180046129`: `CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete(CChangeApplier *this)
{
  _CHANGE_APPLIER_WORK_ITEM *v2; // rax
  struct ISyncCallback *v3; // rdx
  int v4; // r8d
  CChangeApplier *v5; // rcx
  _CHANGE_APPLIER_WORK_ITEM *v6; // rbx
  unsigned int v7; // edx
  int v8; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete");
  }
  v2 = (_CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v5 = (CChangeApplier *)((char *)this - 72);
  v6 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *(_DWORD *)v2 = 6;
    v8 = CChangeApplier::AddWorkItemToWorkQueue(v5, v2, v4);
    if ( v8 < 0 )
      _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v6, v7);
  }
  else
  {
    v8 = CChangeApplier::SetError(v5, v3, -2147024882);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveKnowledgeWithFilterForgottenKnowledgesComplete",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180046070  mov     [rsp+arg_0], rbx
0x180046075  mov     [rsp+arg_8], rsi
0x18004607a  push    rdi
0x18004607b  sub     rsp, 30h
0x18004607f  mov     rdi, rcx
0x180046082  mov     rcx, cs:WPP_GLOBAL_Control
0x180046089  lea     rsi, WPP_GLOBAL_Control
0x180046090  cmp     rcx, rsi
0x180046093  jz      short loc_1800460BD
0x180046095  test    byte ptr [rcx+1Ch], 8
0x180046099  jz      short loc_1800460BD
0x18004609b  cmp     byte ptr [rcx+19h], 5
0x18004609f  jb      short loc_1800460BD
0x1800460a1  mov     rcx, [rcx+10h]
0x1800460a5  lea     r9, aCchangeapplier_82; "CChangeApplier::SaveKnowledgeWithFilter"...
0x1800460ac  mov     edx, 35h ; '5'
0x1800460b1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800460b8  call    WPP_SF_s
0x1800460bd  mov     ecx, 18h; unsigned __int64
0x1800460c2  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800460c7  lea     rcx, [rdi-48h]; this
0x1800460cb  mov     rbx, rax
0x1800460ce  test    rax, rax
0x1800460d1  jz      short loc_180046100
0x1800460d3  mov     qword ptr [rax+8], 0
0x1800460db  mov     rdx, rax; struct _CHANGE_APPLIER_WORK_ITEM *
0x1800460de  mov     dword ptr [rax+10h], 0
0x1800460e5  mov     dword ptr [rax], 6
0x1800460eb  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x1800460f0  mov     edi, eax
0x1800460f2  test    eax, eax
0x1800460f4  jns     short loc_18004610D
0x1800460f6  mov     rcx, rbx; this
0x1800460f9  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x1800460fe  jmp     short loc_18004610D
0x180046100  mov     r8d, 8007000Eh; int
0x180046106  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18004610b  mov     edi, eax
0x18004610d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046114  cmp     rcx, rsi
0x180046117  jz      short loc_180046145
0x180046119  test    byte ptr [rcx+1Ch], 8
0x18004611d  jz      short loc_180046145
0x18004611f  cmp     byte ptr [rcx+19h], 5
0x180046123  jb      short loc_180046145
0x180046125  mov     rcx, [rcx+10h]
0x180046129  lea     r9, aCchangeapplier_82; "CChangeApplier::SaveKnowledgeWithFilter"...
0x180046130  mov     edx, 36h ; '6'
0x180046135  mov     [rsp+38h+var_18], edi
0x180046139  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180046140  call    WPP_SF_sD
0x180046145  mov     rbx, [rsp+38h+arg_0]
0x18004614a  mov     eax, edi
0x18004614c  mov     rsi, [rsp+38h+arg_8]
0x180046151  add     rsp, 30h
0x180046155  pop     rdi
0x180046156  retn
```
