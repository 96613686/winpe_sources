# CChangeApplier::SaveChangeComplete(void)

- ea: `0x180044b90`
- end: `0x180044c77`
- name: `?SaveChangeComplete@CChangeApplier@@UEAAJXZ`
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
- `0x180044b90`
- `0x180046160`

## string_xrefs

- `0x180044bc5`: `CChangeApplier::SaveChangeComplete`
- `0x180044c49`: `CChangeApplier::SaveChangeComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveChangeComplete(CChangeApplier *this)
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
      41,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveChangeComplete");
  }
  v2 = (_CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v5 = (CChangeApplier *)((char *)this - 16);
  v6 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *(_DWORD *)v2 = 3;
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
      42,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveChangeComplete",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180044b90  mov     [rsp+arg_0], rbx
0x180044b95  mov     [rsp+arg_8], rsi
0x180044b9a  push    rdi
0x180044b9b  sub     rsp, 30h
0x180044b9f  mov     rdi, rcx
0x180044ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ba9  lea     rsi, WPP_GLOBAL_Control
0x180044bb0  cmp     rcx, rsi
0x180044bb3  jz      short loc_180044BDD
0x180044bb5  test    byte ptr [rcx+1Ch], 8
0x180044bb9  jz      short loc_180044BDD
0x180044bbb  cmp     byte ptr [rcx+19h], 5
0x180044bbf  jb      short loc_180044BDD
0x180044bc1  mov     rcx, [rcx+10h]
0x180044bc5  lea     r9, aCchangeapplier_36; "CChangeApplier::SaveChangeComplete"
0x180044bcc  mov     edx, 29h ; ')'
0x180044bd1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180044bd8  call    WPP_SF_s
0x180044bdd  mov     ecx, 18h; unsigned __int64
0x180044be2  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180044be7  lea     rcx, [rdi-10h]; this
0x180044beb  mov     rbx, rax
0x180044bee  test    rax, rax
0x180044bf1  jz      short loc_180044C20
0x180044bf3  mov     qword ptr [rax+8], 0
0x180044bfb  mov     rdx, rax; struct _CHANGE_APPLIER_WORK_ITEM *
0x180044bfe  mov     dword ptr [rax+10h], 0
0x180044c05  mov     dword ptr [rax], 3
0x180044c0b  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x180044c10  mov     edi, eax
0x180044c12  test    eax, eax
0x180044c14  jns     short loc_180044C2D
0x180044c16  mov     rcx, rbx; this
0x180044c19  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x180044c1e  jmp     short loc_180044C2D
0x180044c20  mov     r8d, 8007000Eh; int
0x180044c26  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180044c2b  mov     edi, eax
0x180044c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c34  cmp     rcx, rsi
0x180044c37  jz      short loc_180044C65
0x180044c39  test    byte ptr [rcx+1Ch], 8
0x180044c3d  jz      short loc_180044C65
0x180044c3f  cmp     byte ptr [rcx+19h], 5
0x180044c43  jb      short loc_180044C65
0x180044c45  mov     rcx, [rcx+10h]
0x180044c49  lea     r9, aCchangeapplier_36; "CChangeApplier::SaveChangeComplete"
0x180044c50  mov     edx, 2Ah ; '*'
0x180044c55  mov     [rsp+38h+var_18], edi
0x180044c59  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180044c60  call    WPP_SF_sD
0x180044c65  mov     rbx, [rsp+38h+arg_0]
0x180044c6a  mov     eax, edi
0x180044c6c  mov     rsi, [rsp+38h+arg_8]
0x180044c71  add     rsp, 30h
0x180044c75  pop     rdi
0x180044c76  retn
```
