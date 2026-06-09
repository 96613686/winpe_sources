# CChangeApplier::GetNewMoveinsComplete(ISyncKnowledge *,IEnumItemIds *)

- ea: `0x18003da10`
- end: `0x18003db2d`
- name: `?GetNewMoveinsComplete@CChangeApplier@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CChangeApplier *this, struct ISyncCallback *, struct IEnumItemIds *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x18003da10`
- `0x180046160`
- `0x180094010`

## string_xrefs

- `0x18003da45`: `CChangeApplier::GetNewMoveinsComplete`
- `0x18003db03`: `CChangeApplier::GetNewMoveinsComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetNewMoveinsComplete(
        CChangeApplier *this,
        struct ISyncCallback *a2,
        struct IEnumItemIds *a3)
{
  CChangeApplier *v5; // rdi
  int v6; // ebx
  struct _CHANGE_APPLIER_WORK_ITEM *v7; // rax
  struct ISyncCallback *v8; // rdx
  struct _CHANGE_APPLIER_WORK_ITEM *v9; // rsi
  int v10; // r8d
  unsigned int v11; // edx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetNewMoveinsComplete");
  }
  v5 = (CChangeApplier *)((char *)this - 72);
  if ( !*((_QWORD *)v5 + 33) || (v6 = CChangeApplier::SetError(v5, a2, -2147217379)) == 0 )
  {
    v7 = (struct _CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
    v9 = v7;
    if ( v7 )
    {
      *((_QWORD *)v7 + 1) = 0;
      *((_DWORD *)v7 + 4) = 0;
      *((_QWORD *)v5 + 33) = a3;
      ((void (__fastcall *)(struct IEnumItemIds *))a3->lpVtbl->AddRef)(a3);
      *(_DWORD *)v9 = 5;
      v6 = CChangeApplier::AddWorkItemToWorkQueue(v5, v9, v10);
      if ( v6 < 0 )
        _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v9, v11);
    }
    else
    {
      v6 = CChangeApplier::SetError(v5, v8, -2147024882);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetNewMoveinsComplete",
      v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003da10  push    rbx
0x18003da12  push    rsi
0x18003da13  push    rdi
0x18003da14  push    r14
0x18003da16  push    r15
0x18003da18  sub     rsp, 30h
0x18003da1c  mov     r14, r8
0x18003da1f  mov     rdi, rcx
0x18003da22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da29  lea     r15, WPP_GLOBAL_Control
0x18003da30  cmp     rcx, r15
0x18003da33  jz      short loc_18003DA5D
0x18003da35  test    byte ptr [rcx+1Ch], 8
0x18003da39  jz      short loc_18003DA5D
0x18003da3b  cmp     byte ptr [rcx+19h], 5
0x18003da3f  jb      short loc_18003DA5D
0x18003da41  mov     rcx, [rcx+10h]
0x18003da45  lea     r9, aCchangeapplier_112; "CChangeApplier::GetNewMoveinsComplete"
0x18003da4c  mov     edx, 37h ; '7'
0x18003da51  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003da58  call    WPP_SF_s
0x18003da5d  add     rdi, 0FFFFFFFFFFFFFFB8h
0x18003da61  cmp     qword ptr [rdi+108h], 0
0x18003da69  jz      short loc_18003DA7F
0x18003da6b  mov     r8d, 8004101Dh; int
0x18003da71  mov     rcx, rdi; this
0x18003da74  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003da79  mov     ebx, eax
0x18003da7b  test    eax, eax
0x18003da7d  jnz     short loc_18003DAE7
0x18003da7f  mov     ecx, 18h; unsigned __int64
0x18003da84  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18003da89  mov     rsi, rax
0x18003da8c  test    rax, rax
0x18003da8f  jz      short loc_18003DAD7
0x18003da91  mov     qword ptr [rax+8], 0
0x18003da99  mov     rcx, r14
0x18003da9c  mov     dword ptr [rax+10h], 0
0x18003daa3  mov     [rdi+108h], r14
0x18003daaa  mov     rdx, [r14]
0x18003daad  mov     rax, [rdx+8]
0x18003dab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dab6  mov     rdx, rsi; struct _CHANGE_APPLIER_WORK_ITEM *
0x18003dab9  mov     dword ptr [rsi], 5
0x18003dabf  mov     rcx, rdi; this
0x18003dac2  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x18003dac7  mov     ebx, eax
0x18003dac9  test    eax, eax
0x18003dacb  jns     short loc_18003DAE7
0x18003dacd  mov     rcx, rsi; this
0x18003dad0  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x18003dad5  jmp     short loc_18003DAE7
0x18003dad7  mov     r8d, 8007000Eh; int
0x18003dadd  mov     rcx, rdi; this
0x18003dae0  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003dae5  mov     ebx, eax
0x18003dae7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003daee  cmp     rcx, r15
0x18003daf1  jz      short loc_18003DB1F
0x18003daf3  test    byte ptr [rcx+1Ch], 8
0x18003daf7  jz      short loc_18003DB1F
0x18003daf9  cmp     byte ptr [rcx+19h], 5
0x18003dafd  jb      short loc_18003DB1F
0x18003daff  mov     rcx, [rcx+10h]
0x18003db03  lea     r9, aCchangeapplier_112; "CChangeApplier::GetNewMoveinsComplete"
0x18003db0a  mov     edx, 38h ; '8'
0x18003db0f  mov     [rsp+58h+var_38], ebx
0x18003db13  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003db1a  call    WPP_SF_sD
0x18003db1f  mov     eax, ebx
0x18003db21  add     rsp, 30h
0x18003db25  pop     r15
0x18003db27  pop     r14
0x18003db29  pop     rdi
0x18003db2a  pop     rsi
0x18003db2b  pop     rbx
0x18003db2c  retn
```
