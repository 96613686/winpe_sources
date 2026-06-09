# LineScroller::_UpdateScrollTips(void)

- ea: `0x1801e9960`
- end: `0x1801e9c69`
- name: `?_UpdateScrollTips@LineScroller@@AEAAXXZ`
- size: `777`
- prototype: `void __fastcall(LineScroller *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18007c460`

## callees

- `0x180013898`
- `0x180018030`
- `0x18001b774`
- `0x180040de0`
- `0x18004a54c`
- `0x18004b868`
- `0x18005790c`
- `0x18007ea30`
- `0x1800a071c`
- `0x1800afaac`
- `0x1800b0290`
- `0x1801406ec`
- `0x1801e9188`
- `0x1801e9960`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e9c37`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1801e99f8`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1801e99f8`
- `DUI70!StrToID` at `0x1801e999c`
- `DUI70!StrToID` at `0x1801e99bb`
- `DUI70!StrToID` at `0x1801e999c`
- `DUI70!StrToID` at `0x1801e99bb`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9b66`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9ba5`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9c1d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9c2d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9b66`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9ba5`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9c1d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801e9c2d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1801e9a19`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1801e9a19`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1801e9bb9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1801e9bb9`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1801e9b5a`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1801e9b5a`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1801e9a06`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1801e9a06`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LineScroller::_UpdateScrollTips(struct DirectUI::Element **this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *ChildWithID; // r15
  unsigned __int16 v4; // ax
  struct DirectUI::Element *v5; // rax
  DirectUI::Element *v6; // rsi
  int v7; // ebx
  LineScrollbarBase *v8; // rbx
  float v9; // xmm6_4
  int MaxScrollPosition; // eax
  int v11; // r9d
  struct UIBase *ParentElement; // rax
  UIGroupItem *Ancestor; // rbx
  __int64 v14; // rax
  struct UIItem *v15; // r14
  struct UICollection *GroupCollection; // rax
  __int64 v17; // rax
  const unsigned __int16 *AccName; // rax
  unsigned __int16 *v19; // rdx
  DirectUI::Value *v20; // rcx
  void *v21; // rcx
  __int64 v22; // rax
  struct UIItem *v23; // rbx
  const unsigned __int16 *v24; // rdx
  DirectUI::Element *v25; // [rsp+28h] [rbp-79h] BYREF
  unsigned int v26; // [rsp+30h] [rbp-71h] BYREF
  _BYTE v27[4]; // [rsp+38h] [rbp-69h] BYREF
  int v28; // [rsp+3Ch] [rbp-65h]
  _QWORD v29[3]; // [rsp+48h] [rbp-59h] BYREF
  int v30; // [rsp+60h] [rbp-41h]
  unsigned int v31; // [rsp+98h] [rbp-9h]
  int v32; // [rsp+A0h] [rbp-1h]
  __int64 v33; // [rsp+A4h] [rbp+3h]
  LPVOID pv; // [rsp+108h] [rbp+67h] BYREF
  unsigned __int16 *v35; // [rsp+110h] [rbp+6Fh] BYREF

  if ( this[50] )
  {
    v2 = StrToID(L"ScrollTipLine1");
    ChildWithID = DUI_FindChildWithID(this[50], v2);
    v4 = StrToID(L"ScrollTipLine2");
    v5 = DUI_FindChildWithID(this[50], v4);
    v6 = v5;
    if ( ChildWithID )
    {
      if ( v5 )
      {
        v25 = this[50];
        v26 = 0;
        DirectUI::Element::StartDefer(v25, &v26);
        if ( !DirectUI::Element::GetVisible(this[50]) )
          DirectUI::Element::SetVisible(this[50], 1);
        v7 = 0;
        if ( (int)LineScrollbarBase::GetMaxScrollPosition(this[42]) > 0 )
        {
          LineScroller::GetViewerSize(this, v27);
          v8 = this[42];
          v9 = (float)(*(int (__fastcall **)(_QWORD *))(*((_QWORD *)v8 + 44) + 8LL))((_QWORD *)v8 + 44);
          MaxScrollPosition = LineScrollbarBase::GetMaxScrollPosition(v8);
          v7 = (int)(float)((float)(v9 / (float)MaxScrollPosition) * (float)v28);
        }
        memset_0(v29, 0, 0x58u);
        v30 = -1;
        v33 = 0;
        v32 = -1;
        if ( LineScroller::GetRowFromYPosition((LineScroller *)this, v7, (struct RowInfo *)v29, v11) < 0 )
          goto LABEL_27;
        if ( *((_DWORD *)this + 145) )
        {
          ParentElement = SectionInfo::GetParentElement((SectionInfo *)v29);
          Ancestor = (UIGroupItem *)FindAncestorElement<UIGroupItem>(ParentElement);
          if ( !Ancestor )
          {
LABEL_27:
            DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v25);
            return;
          }
          v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v29[0] + 160LL))(v29[0], v31);
          v15 = (struct UIItem *)FindAncestorElement<UIItem>(v14);
          if ( !v15 )
          {
            GroupCollection = UIGroupItem::GetGroupCollection(Ancestor);
            if ( GroupCollection )
            {
              v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)GroupCollection + 27) + 160LL))(
                      (__int64)GroupCollection + 216,
                      0);
              v15 = (struct UIItem *)element_cast<UIItem>(v17);
            }
          }
          v35 = 0;
          CoTaskMemFree(0);
          LineScroller::_GetScrollTipValue((LineScroller *)this, v15, &v35);
          pv = 0;
          AccName = DirectUI::Element::GetAccName(Ancestor, (struct DirectUI::Value **)&pv);
          DirectUI::Element::SetContentString(ChildWithID, AccName);
          if ( (unsigned int)operator==((char *)this + 588, &PKEY_Null) )
          {
            v19 = (unsigned __int16 *)&WindowName;
          }
          else
          {
            v19 = v35;
            if ( !v35 || !*v35 )
              v19 = L" ";
          }
          DirectUI::Element::SetContentString(v6, v19);
          v20 = (DirectUI::Value *)pv;
          if ( pv )
          {
            pv = 0;
            DirectUI::Value::Release(v20);
          }
          v21 = v35;
        }
        else
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v29[0] + 160LL))(v29[0], v31);
          v23 = (struct UIItem *)FindAncestorElement<UIItem>(v22);
          pv = 0;
          CoTaskMemFree(0);
          LineScroller::_GetScrollTipValue((LineScroller *)this, v23, (unsigned __int16 **)&pv);
          v21 = pv;
          if ( pv )
          {
            v24 = L" ";
            if ( *(_WORD *)pv )
              v24 = (const unsigned __int16 *)pv;
            DirectUI::Element::SetContentString(ChildWithID, v24);
            DirectUI::Element::SetContentString(v6, &WindowName);
            v21 = pv;
          }
        }
        CoTaskMemFree(v21);
        goto LABEL_27;
      }
    }
  }
}

```

## disassembly

```asm
0x1801e9960  mov     rax, rsp
0x1801e9963  mov     [rax+18h], rbx
0x1801e9967  mov     [rax+20h], rsi
0x1801e996b  push    rbp
0x1801e996c  push    rdi
0x1801e996d  push    r12
0x1801e996f  push    r14
0x1801e9971  push    r15
0x1801e9973  lea     rbp, [rax-5Fh]
0x1801e9977  sub     rsp, 0D0h
0x1801e997e  movaps  xmmword ptr [rax-38h], xmm6
0x1801e9982  mov     rdi, rcx
0x1801e9985  xor     r12d, r12d
0x1801e9988  cmp     [rcx+190h], r12
0x1801e998f  jz      loc_1801E9C48
0x1801e9995  lea     rcx, aScrolltipline1; "ScrollTipLine1"
0x1801e999c  call    cs:__imp_StrToID
0x1801e99a2  movzx   edx, ax; unsigned __int16
0x1801e99a5  mov     rcx, [rdi+190h]; struct DirectUI::Element *
0x1801e99ac  call    ?DUI_FindChildWithID@@YAPEAVElement@DirectUI@@PEAV12@G@Z; DUI_FindChildWithID(DirectUI::Element *,ushort)
0x1801e99b1  mov     r15, rax
0x1801e99b4  lea     rcx, aScrolltipline2; "ScrollTipLine2"
0x1801e99bb  call    cs:__imp_StrToID
0x1801e99c1  movzx   edx, ax; unsigned __int16
0x1801e99c4  mov     rcx, [rdi+190h]; struct DirectUI::Element *
0x1801e99cb  call    ?DUI_FindChildWithID@@YAPEAVElement@DirectUI@@PEAV12@G@Z; DUI_FindChildWithID(DirectUI::Element *,ushort)
0x1801e99d0  mov     rsi, rax
0x1801e99d3  test    r15, r15
0x1801e99d6  jz      loc_1801E9C48
0x1801e99dc  test    rax, rax
0x1801e99df  jz      loc_1801E9C48
0x1801e99e5  mov     rcx, [rdi+190h]
0x1801e99ec  mov     [rbp+57h+var_D0], rcx
0x1801e99f0  mov     [rbp+57h+var_C8], r12d
0x1801e99f4  lea     rdx, [rbp+57h+var_C8]
0x1801e99f8  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1801e99fe  nop
0x1801e99ff  mov     rcx, [rdi+190h]
0x1801e9a06  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1801e9a0c  test    al, al
0x1801e9a0e  jnz     short loc_1801E9A1F
0x1801e9a10  mov     dl, 1
0x1801e9a12  mov     rcx, [rdi+190h]
0x1801e9a19  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1801e9a1f  mov     ebx, r12d
0x1801e9a22  mov     rcx, [rdi+150h]; this
0x1801e9a29  call    ?GetMaxScrollPosition@LineScrollbarBase@@QEAAHXZ; LineScrollbarBase::GetMaxScrollPosition(void)
0x1801e9a2e  test    eax, eax
0x1801e9a30  jle     short loc_1801E9A82
0x1801e9a32  lea     rdx, [rbp+57h+var_C0]
0x1801e9a36  mov     rcx, rdi
0x1801e9a39  call    ?GetViewerSize@LineScroller@@QEAA?AUSIZEV@@XZ; LineScroller::GetViewerSize(void)
0x1801e9a3e  mov     rbx, [rdi+150h]
0x1801e9a45  lea     rcx, [rbx+160h]
0x1801e9a4c  mov     rax, [rcx]
0x1801e9a4f  mov     rax, [rax+8]
0x1801e9a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9a58  movd    xmm6, eax
0x1801e9a5c  cvtdq2ps xmm6, xmm6
0x1801e9a5f  mov     rcx, rbx; this
0x1801e9a62  call    ?GetMaxScrollPosition@LineScrollbarBase@@QEAAHXZ; LineScrollbarBase::GetMaxScrollPosition(void)
0x1801e9a67  movd    xmm0, eax
0x1801e9a6b  cvtdq2ps xmm0, xmm0
0x1801e9a6e  divss   xmm6, xmm0
0x1801e9a72  movd    xmm1, [rbp+57h+var_BC]
0x1801e9a77  cvtdq2ps xmm1, xmm1
0x1801e9a7a  mulss   xmm6, xmm1
0x1801e9a7e  cvttss2si ebx, xmm6
0x1801e9a82  xor     edx, edx; Val
0x1801e9a84  lea     r8d, [rdx+58h]; Size
0x1801e9a88  lea     rcx, [rbp+57h+var_B0]; void *
0x1801e9a8c  call    memset_0
0x1801e9a91  or      eax, 0FFFFFFFFh
0x1801e9a94  mov     [rbp+57h+var_98], eax
0x1801e9a97  mov     [rbp+57h+var_54], r12
0x1801e9a9b  mov     [rbp+57h+var_58], eax
0x1801e9a9e  lea     r8, [rbp+57h+var_B0]; struct RowInfo *
0x1801e9aa2  mov     edx, ebx; int
0x1801e9aa4  mov     rcx, rdi; this
0x1801e9aa7  call    ?GetRowFromYPosition@LineScroller@@QEAAJHPEAVRowInfo@@H@Z; LineScroller::GetRowFromYPosition(int,RowInfo *,int)
0x1801e9aac  test    eax, eax
0x1801e9aae  js      loc_1801E9C3E
0x1801e9ab4  cmp     [rdi+244h], r12d
0x1801e9abb  jz      loc_1801E9BC6
0x1801e9ac1  lea     rcx, [rbp+57h+var_B0]; this
0x1801e9ac5  call    ?GetParentElement@SectionInfo@@QEBAPEAVUIBase@@XZ; SectionInfo::GetParentElement(void)
0x1801e9aca  mov     rcx, rax
0x1801e9acd  call    ??$FindAncestorElement@VUIGroupItem@@@@YAPEAVUIGroupItem@@PEAVElement@DirectUI@@@Z; FindAncestorElement<UIGroupItem>(DirectUI::Element *)
0x1801e9ad2  mov     rbx, rax
0x1801e9ad5  test    rax, rax
0x1801e9ad8  jz      loc_1801E9C3E
0x1801e9ade  mov     rcx, [rbp+57h+var_B0]
0x1801e9ae2  mov     rdx, [rcx]
0x1801e9ae5  mov     rax, [rdx+0A0h]
0x1801e9aec  mov     edx, [rbp+57h+var_60]
0x1801e9aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9af4  mov     rcx, rax
0x1801e9af7  call    ??$FindAncestorElement@VUIItem@@@@YAPEAVUIItem@@PEAVElement@DirectUI@@@Z; FindAncestorElement<UIItem>(DirectUI::Element *)
0x1801e9afc  mov     r14, rax
0x1801e9aff  test    rax, rax
0x1801e9b02  jnz     short loc_1801E9B34
0x1801e9b04  mov     rcx, rbx; this
0x1801e9b07  call    ?GetGroupCollection@UIGroupItem@@QEAAPEAVUICollection@@XZ; UIGroupItem::GetGroupCollection(void)
0x1801e9b0c  test    rax, rax
0x1801e9b0f  jz      short loc_1801E9B34
0x1801e9b11  lea     rcx, [rax+0D8h]
0x1801e9b18  mov     rax, [rcx]
0x1801e9b1b  xor     edx, edx
0x1801e9b1d  mov     rax, [rax+0A0h]
0x1801e9b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9b29  mov     rcx, rax
0x1801e9b2c  call    ??$element_cast@VUIItem@@@@YAPEAVUIItem@@PEAVElement@DirectUI@@@Z; element_cast<UIItem>(DirectUI::Element *)
0x1801e9b31  mov     r14, rax
0x1801e9b34  mov     [rbp+57h+arg_8], r12
0x1801e9b38  xor     ecx, ecx; pv
0x1801e9b3a  call    cs:__imp_CoTaskMemFree
0x1801e9b40  lea     r8, [rbp+57h+arg_8]; unsigned __int16 **
0x1801e9b44  mov     rdx, r14; struct UIItem *
0x1801e9b47  mov     rcx, rdi; this
0x1801e9b4a  call    ?_GetScrollTipValue@LineScroller@@AEAAXPEAVUIItem@@PEAPEAG@Z; LineScroller::_GetScrollTipValue(UIItem *,ushort * *)
0x1801e9b4f  mov     [rbp+57h+pv], r12
0x1801e9b53  lea     rdx, [rbp+57h+pv]
0x1801e9b57  mov     rcx, rbx
0x1801e9b5a  call    cs:__imp_?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetAccName(DirectUI::Value * *)
0x1801e9b60  mov     rdx, rax
0x1801e9b63  mov     rcx, r15
0x1801e9b66  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1801e9b6c  lea     rcx, [rdi+24Ch]
0x1801e9b73  lea     rdx, PKEY_Null
0x1801e9b7a  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1801e9b7f  test    eax, eax
0x1801e9b81  jz      short loc_1801E9B8C
0x1801e9b83  lea     rdx, WindowName
0x1801e9b8a  jmp     short loc_1801E9BA2
0x1801e9b8c  mov     rdx, [rbp+57h+arg_8]
0x1801e9b90  test    rdx, rdx
0x1801e9b93  jz      short loc_1801E9B9B
0x1801e9b95  cmp     [rdx], r12w
0x1801e9b99  jnz     short loc_1801E9BA2
0x1801e9b9b  lea     rdx, asc_18024E0E0; " "
0x1801e9ba2  mov     rcx, rsi
0x1801e9ba5  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1801e9bab  nop
0x1801e9bac  mov     rcx, [rbp+57h+pv]
0x1801e9bb0  test    rcx, rcx
0x1801e9bb3  jz      short loc_1801E9BC0
0x1801e9bb5  mov     [rbp+57h+pv], r12
0x1801e9bb9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1801e9bbf  nop
0x1801e9bc0  mov     rcx, [rbp+57h+arg_8]
0x1801e9bc4  jmp     short loc_1801E9C37
0x1801e9bc6  mov     rcx, [rbp+57h+var_B0]
0x1801e9bca  mov     rax, [rcx]
0x1801e9bcd  mov     edx, [rbp+57h+var_60]
0x1801e9bd0  mov     rax, [rax+0A0h]
0x1801e9bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9bdc  mov     rcx, rax
0x1801e9bdf  call    ??$FindAncestorElement@VUIItem@@@@YAPEAVUIItem@@PEAVElement@DirectUI@@@Z; FindAncestorElement<UIItem>(DirectUI::Element *)
0x1801e9be4  mov     rbx, rax
0x1801e9be7  mov     [rbp+57h+pv], r12
0x1801e9beb  xor     ecx, ecx; pv
0x1801e9bed  call    cs:__imp_CoTaskMemFree
0x1801e9bf3  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x1801e9bf7  mov     rdx, rbx; struct UIItem *
0x1801e9bfa  mov     rcx, rdi; this
0x1801e9bfd  call    ?_GetScrollTipValue@LineScroller@@AEAAXPEAVUIItem@@PEAPEAG@Z; LineScroller::_GetScrollTipValue(UIItem *,ushort * *)
0x1801e9c02  mov     rcx, [rbp+57h+pv]
0x1801e9c06  test    rcx, rcx
0x1801e9c09  jz      short loc_1801E9C37
0x1801e9c0b  lea     rdx, asc_18024E0E0; " "
0x1801e9c12  cmp     [rcx], r12w
0x1801e9c16  cmovnz  rdx, rcx
0x1801e9c1a  mov     rcx, r15
0x1801e9c1d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1801e9c23  lea     rdx, WindowName
0x1801e9c2a  mov     rcx, rsi
0x1801e9c2d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1801e9c33  mov     rcx, [rbp+57h+pv]; pv
0x1801e9c37  call    cs:__imp_CoTaskMemFree
0x1801e9c3d  nop
0x1801e9c3e  lea     rcx, [rbp+57h+var_D0]; this
0x1801e9c42  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x1801e9c47  nop
0x1801e9c48  lea     r11, [rsp+0F0h+var_20]
0x1801e9c50  mov     rbx, [r11+40h]
0x1801e9c54  mov     rsi, [r11+48h]
0x1801e9c58  movaps  xmm6, xmmword ptr [r11-10h]
0x1801e9c5d  mov     rsp, r11
0x1801e9c60  pop     r15
0x1801e9c62  pop     r14
0x1801e9c64  pop     r12
0x1801e9c66  pop     rdi
0x1801e9c67  pop     rbp
0x1801e9c68  retn
```
