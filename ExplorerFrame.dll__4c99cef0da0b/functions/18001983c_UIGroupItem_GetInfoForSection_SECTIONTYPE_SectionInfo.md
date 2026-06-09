# UIGroupItem::_GetInfoForSection(SECTIONTYPE,SectionInfo *)

- ea: `0x18001983c`
- end: `0x180019c41`
- name: `?_GetInfoForSection@UIGroupItem@@IEAAXW4SECTIONTYPE@@PEAVSectionInfo@@@Z`
- size: `1029`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18001a8f0`
- `0x18001aaa0`
- `0x18001ab70`
- `0x18001f1c0`
- `0x1801e2f70`

## callees

- `0x180015640`
- `0x180016790`
- `0x180018030`
- `0x18001983c`
- `0x180019c48`
- `0x180019d4c`
- `0x18001a95c`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `USER32!SetRect` at `0x180019a57`
- `USER32!SetRect` at `0x180019b21`
- `USER32!SetRect` at `0x180019a57`
- `USER32!SetRect` at `0x180019b21`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180019895`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800198fa`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001997f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180019895`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800198fa`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001997f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180019887`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800198ef`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180019974`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180019887`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800198ef`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180019974`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001987b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800198e3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180019968`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001987b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800198e3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180019968`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800198a9`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180019a04`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800198a9`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180019a04`

## pseudocode

```c
unsigned __int64 __fastcall UIGroupItem::_GetInfoForSection(DirectUI::Element *a1, int a2, __int64 a3)
{
  DirectUI::Value *Value; // rbx
  int v7; // edi
  __int64 v8; // rbx
  unsigned __int64 result; // rax
  DirectUI::Value *v10; // rbx
  int v11; // edi
  int v12; // eax
  struct IVirtualizedUI *v13; // rax
  struct IVirtualizedUI *v14; // r13
  int v15; // esi
  DirectUI::Value *v16; // rdi
  int v17; // ebx
  BOOL v18; // eax
  int v19; // ebx
  int HeaderTickCount; // eax
  __int64 v21; // rax
  DirectUI::Element *v22; // rax
  DirectUI::Element *v23; // rsi
  __int64 v24; // rbx
  LONG top; // edi
  int v26; // r8d
  bool v27; // zf
  LONG left; // ecx
  unsigned int right; // edx
  LONG v30; // eax
  struct IVirtualizedUI *ChildVirtualizedUI; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  int xLeft[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v35; // [rsp+38h] [rbp-38h]
  int Int; // [rsp+40h] [rbp-30h]
  struct tagRECT v37; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+58h] [rbp-18h] BYREF

  Value = DirectUI::Element::GetValue(a1, UIGroupItem::VirtualDirectionProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  v7 = Int;
  DirectUI::Value::Release(Value);
  *(_QWORD *)xLeft = 0;
  v8 = (__int64)*DirectUI::Element::GetExtent(a1, (struct DirectUI::Value **)xLeft);
  v35 = v8;
  CValuePtr::~CValuePtr((CValuePtr *)xLeft);
  if ( a2 == 1 )
    goto LABEL_28;
  result = (unsigned int)(a2 - 3);
  if ( a2 != 3 )
  {
    if ( a2 != 6 )
      return result;
LABEL_28:
    *(_DWORD *)(a3 + 8) = a2;
    *(_DWORD *)(a3 + 24) = 0;
    *(_QWORD *)a3 = ((unsigned __int64)a1 + 288) & -(__int64)(a1 != 0);
    *(_DWORD *)(a3 + 64) = 0;
    *(_DWORD *)(a3 + 68) = 1;
    if ( (unsigned int)UIGroupItem::_IsHeaderFloating(a1) )
    {
      *(_DWORD *)(a3 + 76) = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)a1 + 36) + 56LL))((_QWORD *)a1 + 36);
      *(_DWORD *)(a3 + 72) = 0;
      *(_DWORD *)(a3 + 28) = -1;
    }
    else
    {
      *(_DWORD *)(a3 + 76) = UIGroupItem::GetHeaderTickCount(a1);
      *(_DWORD *)(a3 + 72) = 0;
    }
    if ( UIGroupItem::GetGroupCollection(a1)
      && (ChildVirtualizedUI = UIGroupItem::_GetChildVirtualizedUI(a1),
          (*(int (__fastcall **)(struct IVirtualizedUI *))(*(_QWORD *)ChildVirtualizedUI + 48LL))(ChildVirtualizedUI) > 0) )
    {
      v32 = *(_QWORD *)a1;
      v37 = 0;
      v33 = (*(__int64 (__fastcall **)(DirectUI::Element *))(v32 + 504))(a1);
      xLeft[0] = v37.left;
      xLeft[1] = v37.top;
      DUI_MapElementPoint(v33, a1, 0, xLeft, xLeft);
      SetRect(&v37, xLeft[0], xLeft[1], v37.right + xLeft[0] - v37.left, v37.bottom + xLeft[1] - v37.top);
      result = (unsigned int)v37.top;
      if ( v7 != 1 )
      {
        result = (unsigned int)v8;
        LODWORD(v8) = v37.top;
      }
    }
    else
    {
      result = HIDWORD(v35);
      if ( v7 != 1 )
      {
        result = (unsigned int)v8;
        LODWORD(v8) = HIDWORD(v35);
      }
    }
    *(_DWORD *)(a3 + 52) = v7;
    *(_DWORD *)(a3 + 48) = v8;
    *(_DWORD *)(a3 + 40) = 0;
    *(_QWORD *)(a3 + 32) = 1;
    goto LABEL_25;
  }
  v10 = DirectUI::Element::GetValue(a1, UIGroupItem::VirtualDirectionProp, 2, 0);
  v11 = DirectUI::Value::GetInt(v10);
  DirectUI::Value::Release(v10);
  if ( v11 != 1 || (v27 = UIGroupItem::_GetChildVirtualizedUI(a1) == 0, v12 = 0, v27) )
    v12 = 1;
  *(_DWORD *)(a3 + 24) = v12;
  *(_DWORD *)(a3 + 8) = 3;
  *(_QWORD *)a3 = ((unsigned __int64)a1 + 288) & -(__int64)(a1 != 0);
  v13 = UIGroupItem::_GetChildVirtualizedUI(a1);
  v14 = v13;
  if ( v13 )
    v15 = (*(__int64 (__fastcall **)(struct IVirtualizedUI *))(*(_QWORD *)v13 + 48LL))(v13);
  else
    v15 = 1;
  v16 = DirectUI::Element::GetValue(a1, UIGroupItem::VirtualDirectionProp, 2, 0);
  v17 = DirectUI::Value::GetInt(v16);
  DirectUI::Value::Release(v16);
  v18 = v17 != 1 || !UIGroupItem::_GetChildVirtualizedUI(a1);
  *(_DWORD *)(a3 + 64) = v18;
  *(_DWORD *)(a3 + 68) = v15 + v18;
  if ( v14 )
    v19 = (*(__int64 (__fastcall **)(struct IVirtualizedUI *))(*(_QWORD *)v14 + 56LL))(v14);
  else
    v19 = 1;
  HeaderTickCount = UIGroupItem::GetHeaderTickCount(a1);
  *(_DWORD *)(a3 + 72) = HeaderTickCount;
  *(_DWORD *)(a3 + 76) = v19 + HeaderTickCount;
  result = (unsigned __int64)UIGroupItem::GetGroupCollection(a1);
  if ( result )
  {
    v21 = *(_QWORD *)a1;
    rc = 0;
    v22 = (DirectUI::Element *)(*(__int64 (__fastcall **)(DirectUI::Element *))(v21 + 504))(a1);
    *(_QWORD *)xLeft = 0;
    v23 = v22;
    v24 = (__int64)*DirectUI::Element::GetExtent(v22, (struct DirectUI::Value **)xLeft);
    *(_QWORD *)&v37.left = v24;
    CValuePtr::~CValuePtr((CValuePtr *)xLeft);
    top = v37.top;
    *(_QWORD *)xLeft = 0;
    DUI_MapElementPoint(v23, a1, 0, xLeft, xLeft);
    SetRect(&rc, xLeft[0], xLeft[1], v24 + xLeft[0], top + xLeft[1]);
    v26 = Int;
    v27 = Int == 1;
    left = rc.left;
    right = rc.right;
    v30 = rc.top;
    if ( Int != 1 )
      v30 = rc.left;
    *(_DWORD *)(a3 + 32) = 1;
    if ( !v27 )
      left = rc.top;
    *(_DWORD *)(a3 + 36) = v30;
    result = HIDWORD(v35);
    if ( !v27 )
      result = right;
    *(_DWORD *)(a3 + 40) = left;
    if ( !v27 )
      right = HIDWORD(v35);
    *(_DWORD *)(a3 + 48) = right;
    *(_DWORD *)(a3 + 52) = v26;
    *(_QWORD *)(a3 + 16) = v14;
LABEL_25:
    *(_DWORD *)(a3 + 44) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18001983c  mov     [rsp-38h+arg_8], rbx
0x180019841  push    rbp
0x180019842  push    rsi
0x180019843  push    rdi
0x180019844  push    r12
0x180019846  push    r13
0x180019848  push    r14
0x18001984a  push    r15
0x18001984c  mov     rbp, rsp
0x18001984f  sub     rsp, 70h
0x180019853  mov     rax, cs:__security_cookie
0x18001985a  xor     rax, rsp
0x18001985d  mov     [rbp+var_8], rax
0x180019861  xor     r9d, r9d
0x180019864  mov     r14, r8
0x180019867  mov     r12d, edx
0x18001986a  mov     r15, rcx
0x18001986d  lea     rdx, ?VirtualDirectionProp@UIGroupItem@@SAPEBUPropertyInfo@DirectUI@@XZ; UIGroupItem::VirtualDirectionProp(void)
0x180019874  lea     esi, [r9+2]
0x180019878  mov     r8d, esi
0x18001987b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180019881  mov     rcx, rax
0x180019884  mov     rbx, rax
0x180019887  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001988d  mov     rcx, rbx
0x180019890  mov     [rbp+var_30], eax
0x180019893  mov     edi, eax
0x180019895  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001989b  xor     r13d, r13d
0x18001989e  lea     rdx, [rbp+xLeft]
0x1800198a2  mov     rcx, r15
0x1800198a5  mov     qword ptr [rbp+xLeft], r13
0x1800198a9  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x1800198af  lea     rcx, [rbp+xLeft]; this
0x1800198b3  mov     rbx, [rax]
0x1800198b6  mov     [rbp+var_38], rbx
0x1800198ba  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800198bf  mov     eax, r12d
0x1800198c2  sub     eax, 1
0x1800198c5  jz      loc_180019B71
0x1800198cb  sub     eax, esi
0x1800198cd  jnz     loc_180019B6C
0x1800198d3  xor     r9d, r9d
0x1800198d6  lea     rdx, ?VirtualDirectionProp@UIGroupItem@@SAPEBUPropertyInfo@DirectUI@@XZ; UIGroupItem::VirtualDirectionProp(void)
0x1800198dd  mov     r8d, esi
0x1800198e0  mov     rcx, r15
0x1800198e3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800198e9  mov     rcx, rax
0x1800198ec  mov     rbx, rax
0x1800198ef  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800198f5  mov     rcx, rbx
0x1800198f8  mov     edi, eax
0x1800198fa  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180019900  lea     r12d, [rsi-1]
0x180019904  cmp     edi, r12d
0x180019907  jz      loc_180019BDC
0x18001990d  mov     eax, r12d
0x180019910  mov     [r14+18h], eax
0x180019914  lea     rdx, [r15+120h]
0x18001991b  mov     dword ptr [r14+8], 3
0x180019923  mov     rax, r15
0x180019926  neg     rax
0x180019929  sbb     rcx, rcx
0x18001992c  and     rcx, rdx
0x18001992f  mov     [r14], rcx
0x180019932  mov     rcx, r15; this
0x180019935  call    ?_GetChildVirtualizedUI@UIGroupItem@@IEAAPEAUIVirtualizedUI@@XZ; UIGroupItem::_GetChildVirtualizedUI(void)
0x18001993a  mov     r13, rax
0x18001993d  test    rax, rax
0x180019940  jz      loc_180019C0D
0x180019946  mov     rcx, [rax]
0x180019949  mov     rax, [rcx+30h]
0x18001994d  mov     rcx, r13
0x180019950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019955  mov     esi, eax
0x180019957  xor     r9d, r9d
0x18001995a  lea     rdx, ?VirtualDirectionProp@UIGroupItem@@SAPEBUPropertyInfo@DirectUI@@XZ; UIGroupItem::VirtualDirectionProp(void)
0x180019961  mov     rcx, r15
0x180019964  lea     r8d, [r9+2]
0x180019968  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001996e  mov     rcx, rax
0x180019971  mov     rdi, rax
0x180019974  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001997a  mov     rcx, rdi
0x18001997d  mov     ebx, eax
0x18001997f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180019985  cmp     ebx, r12d
0x180019988  jz      loc_180019BF5
0x18001998e  mov     eax, r12d
0x180019991  mov     [r14+40h], eax
0x180019995  add     eax, esi
0x180019997  mov     [r14+44h], eax
0x18001999b  test    r13, r13
0x18001999e  jz      loc_180019C15
0x1800199a4  mov     rax, [r13+0]
0x1800199a8  mov     rcx, r13
0x1800199ab  mov     rax, [rax+38h]
0x1800199af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199b4  mov     ebx, eax
0x1800199b6  mov     rcx, r15; this
0x1800199b9  call    ?GetHeaderTickCount@UIGroupItem@@QEAAHXZ; UIGroupItem::GetHeaderTickCount(void)
0x1800199be  mov     [r14+48h], eax
0x1800199c2  mov     rcx, r15; this
0x1800199c5  add     eax, ebx
0x1800199c7  mov     [r14+4Ch], eax
0x1800199cb  call    ?GetGroupCollection@UIGroupItem@@QEAAPEAVUICollection@@XZ; UIGroupItem::GetGroupCollection(void)
0x1800199d0  test    rax, rax
0x1800199d3  jz      loc_180019B48
0x1800199d9  mov     rax, [r15]
0x1800199dc  xorps   xmm0, xmm0
0x1800199df  mov     rcx, r15
0x1800199e2  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800199e6  mov     rax, [rax+1F8h]
0x1800199ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199f2  lea     rdx, [rbp+xLeft]
0x1800199f6  mov     qword ptr [rbp+xLeft], 0
0x1800199fe  mov     rcx, rax
0x180019a01  mov     rsi, rax
0x180019a04  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180019a0a  lea     rcx, [rbp+xLeft]; this
0x180019a0e  mov     rbx, [rax]
0x180019a11  mov     qword ptr [rbp+var_28.left], rbx
0x180019a15  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180019a1a  mov     edi, [rbp+var_28.top]
0x180019a1d  lea     rax, [rbp+xLeft]
0x180019a21  lea     r9, [rbp+xLeft]
0x180019a25  mov     qword ptr [rsp+70h+yBottom], rax
0x180019a2a  xor     r8d, r8d
0x180019a2d  mov     qword ptr [rbp+xLeft], 0
0x180019a35  mov     rdx, r15
0x180019a38  mov     rcx, rsi
0x180019a3b  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x180019a40  mov     r8d, [rbp+xLeft+4]; yTop
0x180019a44  lea     rcx, [rbp+rc]; lprc
0x180019a48  mov     edx, [rbp+xLeft]; xLeft
0x180019a4b  lea     eax, [rdi+r8]
0x180019a4f  lea     r9d, [rbx+rdx]; xRight
0x180019a53  mov     [rsp+70h+yBottom], eax; yBottom
0x180019a57  call    cs:__imp_SetRect
0x180019a5d  mov     r8d, [rbp+var_30]
0x180019a61  cmp     r8d, r12d
0x180019a64  mov     ecx, [rbp+rc.left]
0x180019a67  mov     edx, [rbp+rc.right]
0x180019a6a  mov     eax, [rbp+rc.top]
0x180019a6d  cmovnz  eax, ecx
0x180019a70  mov     [r14+20h], r12d
0x180019a74  cmovnz  ecx, [rbp+rc.top]
0x180019a78  mov     [r14+24h], eax
0x180019a7c  mov     eax, dword ptr [rbp+var_38+4]
0x180019a7f  cmovnz  eax, edx
0x180019a82  mov     [r14+28h], ecx
0x180019a86  cmovnz  edx, dword ptr [rbp+var_38+4]
0x180019a8a  mov     [r14+30h], edx
0x180019a8e  mov     [r14+34h], r8d
0x180019a92  mov     [r14+10h], r13
0x180019a96  jmp     loc_180019B44
0x180019a9b  mov     rcx, r15; this
0x180019a9e  call    ?_GetChildVirtualizedUI@UIGroupItem@@IEAAPEAUIVirtualizedUI@@XZ; UIGroupItem::_GetChildVirtualizedUI(void)
0x180019aa3  mov     rdx, rax
0x180019aa6  mov     rcx, [rax]
0x180019aa9  mov     rax, [rcx+30h]
0x180019aad  mov     rcx, rdx
0x180019ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab5  test    eax, eax
0x180019ab7  jle     loc_180019BCA
0x180019abd  mov     rax, [r15]
0x180019ac0  xorps   xmm0, xmm0
0x180019ac3  mov     rcx, r15
0x180019ac6  movdqu  xmmword ptr [rbp+var_28.left], xmm0
0x180019acb  mov     rax, [rax+1F8h]
0x180019ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ad7  mov     ecx, [rbp+var_28.left]
0x180019ada  lea     r9, [rbp+xLeft]
0x180019ade  mov     [rbp+xLeft], ecx
0x180019ae1  xor     r8d, r8d
0x180019ae4  mov     ecx, [rbp+var_28.top]
0x180019ae7  mov     rdx, r15
0x180019aea  mov     [rbp+xLeft+4], ecx
0x180019aed  lea     rcx, [rbp+xLeft]
0x180019af1  mov     qword ptr [rsp+70h+yBottom], rcx
0x180019af6  mov     rcx, rax
0x180019af9  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x180019afe  mov     r8d, [rbp+xLeft+4]; yTop
0x180019b02  lea     rcx, [rbp+var_28]; lprc
0x180019b06  mov     edx, [rbp+xLeft]; xLeft
0x180019b09  mov     eax, r8d
0x180019b0c  sub     eax, [rbp+var_28.top]
0x180019b0f  mov     r9d, edx
0x180019b12  sub     r9d, [rbp+var_28.left]
0x180019b16  add     eax, [rbp+var_28.bottom]
0x180019b19  add     r9d, [rbp+var_28.right]; xRight
0x180019b1d  mov     [rsp+70h+yBottom], eax; yBottom
0x180019b21  call    cs:__imp_SetRect
0x180019b27  mov     eax, [rbp+var_28.top]
0x180019b2a  cmp     edi, r12d
0x180019b2d  cmovnz  eax, ebx
0x180019b30  cmovnz  ebx, [rbp+var_28.top]
0x180019b34  mov     [r14+34h], edi
0x180019b38  mov     [r14+30h], ebx
0x180019b3c  mov     [r14+28h], r13d
0x180019b40  mov     [r14+20h], r12
0x180019b44  mov     [r14+2Ch], eax
0x180019b48  mov     rcx, [rbp+var_8]
0x180019b4c  xor     rcx, rsp; StackCookie
0x180019b4f  call    __security_check_cookie
0x180019b54  mov     rbx, [rsp+70h+arg_8]
0x180019b5c  add     rsp, 70h
0x180019b60  pop     r15
0x180019b62  pop     r14
0x180019b64  pop     r13
0x180019b66  pop     r12
0x180019b68  pop     rdi
0x180019b69  pop     rsi
0x180019b6a  pop     rbp
0x180019b6b  retn
0x180019b6c  cmp     eax, 3
0x180019b6f  jnz     short loc_180019B48
0x180019b71  mov     [r14+8], r12d
0x180019b75  lea     rsi, [r15+120h]
0x180019b7c  mov     [r14+18h], r13d
0x180019b80  mov     rax, r15
0x180019b83  neg     rax
0x180019b86  mov     r12d, 1
0x180019b8c  sbb     rcx, rcx
0x180019b8f  and     rcx, rsi
0x180019b92  mov     [r14], rcx
0x180019b95  mov     rcx, r15; this
0x180019b98  mov     [r14+40h], r13d
0x180019b9c  mov     [r14+44h], r12d
0x180019ba0  call    ?_IsHeaderFloating@UIGroupItem@@IEAAHXZ; UIGroupItem::_IsHeaderFloating(void)
0x180019ba5  test    eax, eax
0x180019ba7  jnz     short loc_180019C1D
0x180019ba9  mov     rcx, r15; this
0x180019bac  call    ?GetHeaderTickCount@UIGroupItem@@QEAAHXZ; UIGroupItem::GetHeaderTickCount(void)
0x180019bb1  mov     [r14+4Ch], eax
0x180019bb5  mov     [r14+48h], r13d
0x180019bb9  mov     rcx, r15; this
0x180019bbc  call    ?GetGroupCollection@UIGroupItem@@QEAAPEAVUICollection@@XZ; UIGroupItem::GetGroupCollection(void)
0x180019bc1  test    rax, rax
0x180019bc4  jnz     loc_180019A9B
0x180019bca  mov     eax, dword ptr [rbp+var_38+4]
0x180019bcd  cmp     edi, r12d
0x180019bd0  cmovnz  eax, ebx
0x180019bd3  cmovnz  ebx, dword ptr [rbp+var_38+4]
0x180019bd7  jmp     loc_180019B34
0x180019bdc  mov     rcx, r15; this
0x180019bdf  call    ?_GetChildVirtualizedUI@UIGroupItem@@IEAAPEAUIVirtualizedUI@@XZ; UIGroupItem::_GetChildVirtualizedUI(void)
0x180019be4  test    rax, rax
0x180019be7  mov     eax, r13d
0x180019bea  jnz     loc_180019910
0x180019bf0  jmp     loc_18001990D
0x180019bf5  mov     rcx, r15; this
0x180019bf8  call    ?_GetChildVirtualizedUI@UIGroupItem@@IEAAPEAUIVirtualizedUI@@XZ; UIGroupItem::_GetChildVirtualizedUI(void)
0x180019bfd  test    rax, rax
0x180019c00  jz      loc_18001998E
0x180019c06  xor     eax, eax
0x180019c08  jmp     loc_180019991
0x180019c0d  mov     esi, r12d
0x180019c10  jmp     loc_180019957
0x180019c15  mov     ebx, r12d
0x180019c18  jmp     loc_1800199B6
0x180019c1d  mov     rax, [rsi]
0x180019c20  mov     rcx, rsi
0x180019c23  mov     rax, [rax+38h]
0x180019c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c2c  mov     [r14+4Ch], eax
0x180019c30  mov     [r14+48h], r13d
0x180019c34  mov     dword ptr [r14+1Ch], 0FFFFFFFFh
0x180019c3c  jmp     loc_180019BB9
```
