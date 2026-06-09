# UICollection::GetInfoForScrollTick(int,SectionInfo *)

- ea: `0x18001a250`
- end: `0x18001a653`
- name: `?GetInfoForScrollTick@UICollection@@UEAAXHPEAVSectionInfo@@@Z`
- size: `1027`
- prototype: `void(UICollection *__hidden this, int, struct SectionInfo *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x180015640`
- `0x180015fe0`
- `0x1800173a0`
- `0x18001743c`
- `0x1800174e8`
- `0x18001a250`
- `0x18001a65c`
- `0x18001ab28`
- `0x18001ae40`
- `0x18001b610`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `USER32!SetRect` at `0x18001a537`
- `USER32!SetRect` at `0x18001a537`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a313`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a39f`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a4a5`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a313`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a39f`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001a4a5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a2c9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a352`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a3ea`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a433`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a2c9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a352`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a3ea`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001a433`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a2bd`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a347`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a3df`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a428`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a2bd`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a347`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a3df`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001a428`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a2b1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a33b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a3d3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a41c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a2b1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a33b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a3d3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001a41c`

## pseudocode

```c
void __fastcall UICollection::GetInfoForScrollTick(UICollection *this, int a2, LONG *a3)
{
  char *v6; // r15
  DirectUI::Value *Value; // rbx
  int Int; // r14d
  int v9; // esi
  DirectUI::Element *DescendentElement; // rdi
  DirectUI::Element *v11; // rcx
  DirectUI::Value *v12; // rbx
  DirectUI::Element *v13; // rdi
  __int64 v14; // r14
  void (__fastcall *v15)(__int64, _QWORD, LONG *); // rsi
  DirectUI::Value *v16; // rbx
  int v17; // edi
  DirectUI::Value *v18; // rbx
  int v19; // edi
  __int64 v20; // r13
  bool v21; // zf
  LONG *v22; // rdi
  DirectUI::Element *v23; // r14
  __int64 v24; // rax
  LONG v25; // r8d
  LONG *v26; // rax
  LONG v27; // ecx
  LONG v28; // edx
  LONG v29; // eax
  __int64 v30; // rcx
  LONG bottom; // eax
  LONG left; // edx
  LONG v33; // r14d
  LONG right; // ecx
  LONG v35; // ebx
  LONG top; // eax
  struct ItemLayout *ItemLayout; // rax
  struct tagSIZE ElementExtent; // rax
  LONG v39; // ecx
  unsigned int v40; // esi
  int VirtualDirection; // ebx
  int HeaderRowCount; // ebx
  int HeaderScrollTicks; // eax
  int xLeft[2]; // [rsp+30h] [rbp-30h] BYREF
  LONG v45; // [rsp+38h] [rbp-28h]
  LONG v46; // [rsp+3Ch] [rbp-24h]
  LONG v47; // [rsp+40h] [rbp-20h]
  struct tagRECT rc; // [rsp+48h] [rbp-18h] BYREF

  *(_QWORD *)xLeft = this;
  memset_0(a3, 0, 0x58u);
  a3[6] = -1;
  v6 = (char *)this - 216;
  Value = DirectUI::Element::GetValue((UICollection *)((char *)this - 216), UICollection::HeaderScrollTicksProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  if ( a2 < Int )
  {
    v40 = 1;
    goto LABEL_38;
  }
  v9 = 0;
  if ( !*((_QWORD *)v6 + 29) )
  {
    DescendentElement = _FindDescendentElement((struct DirectUI::Element *)v6, ItemLayout::Class);
    CSafeElementPtr<ItemRowLayout>::Unassign(v6 + 224);
    if ( DescendentElement )
    {
      *((_QWORD *)v6 + 29) = DescendentElement;
      if ( (int)DirectUI::Element::AddListener(DescendentElement, (struct DirectUI::IElementListener *)(v6 + 224)) < 0 )
        *((_QWORD *)v6 + 29) = 0;
    }
  }
  v11 = (DirectUI::Element *)*((_QWORD *)v6 + 29);
  if ( v11 )
  {
    v12 = DirectUI::Element::GetValue(v11, ItemLayout::ScrollTickCountProp, 2, 0);
    v9 = DirectUI::Value::GetInt(v12);
    DirectUI::Value::Release(v12);
  }
  if ( a2 >= v9 + Int )
  {
    v40 = 4;
LABEL_38:
    UICollection::_GetHeaderFooterSectionInfo(v6, v40, a3);
    return;
  }
  if ( !*((_QWORD *)v6 + 29) )
  {
    v13 = _FindDescendentElement((struct DirectUI::Element *)v6, ItemLayout::Class);
    CSafeElementPtr<ItemRowLayout>::Unassign(v6 + 224);
    if ( v13 )
    {
      *((_QWORD *)v6 + 29) = v13;
      if ( (int)DirectUI::Element::AddListener(v13, (struct DirectUI::IElementListener *)(v6 + 224)) < 0 )
        *((_QWORD *)v6 + 29) = 0;
    }
  }
  v14 = *((_QWORD *)v6 + 29);
  v15 = *(void (__fastcall **)(__int64, _QWORD, LONG *))(*(_QWORD *)v14 + 432LL);
  v16 = DirectUI::Element::GetValue((DirectUI::Element *)v6, UICollection::HeaderScrollTicksProp, 2, 0);
  v17 = DirectUI::Value::GetInt(v16);
  DirectUI::Value::Release(v16);
  v15(v14, a2 - (unsigned int)(v17 != 0), a3);
  v18 = DirectUI::Element::GetValue((DirectUI::Element *)v6, UICollection::HeaderScrollTicksProp, 2, 0);
  v19 = DirectUI::Value::GetInt(v18);
  DirectUI::Value::Release(v18);
  if ( v19 )
  {
    HeaderRowCount = UICollection::_GetHeaderRowCount((UICollection *)v6);
    HeaderScrollTicks = UICollection::GetHeaderScrollTicks((UICollection *)v6);
    a3[18] += HeaderScrollTicks;
    a3[19] += HeaderScrollTicks;
    ++a3[16];
    ++a3[17];
    a3[6] += HeaderRowCount;
  }
  v20 = *(_QWORD *)xLeft;
  v21 = a3[8] == 0;
  *(_QWORD *)a3 = *(_QWORD *)xLeft & -(__int64)(v6 != 0);
  if ( !v21 )
  {
    v22 = a3 + 9;
    if ( !*((_QWORD *)v6 + 29) )
    {
      v23 = _FindDescendentElement((struct DirectUI::Element *)v6, ItemLayout::Class);
      CSafeElementPtr<ItemRowLayout>::Unassign(v6 + 224);
      if ( v23 )
      {
        *((_QWORD *)v6 + 29) = v23;
        if ( (int)DirectUI::Element::AddListener(v23, (struct DirectUI::IElementListener *)(v6 + 224)) < 0 )
          *((_QWORD *)v6 + 29) = 0;
      }
    }
    v24 = 2;
    if ( a3[13] != 1 )
      v24 = 3;
    v25 = v22[v24];
    v26 = a3 + 9;
    if ( a3[13] != 1 )
      v26 = a3 + 10;
    v27 = a3[10];
    if ( a3[13] != 1 )
      v27 = *v22;
    v28 = *v26;
    v29 = a3[12];
    if ( a3[13] != 1 )
      v29 = a3[11];
    rc.right = v29;
    rc.left = v27;
    rc.top = v28;
    rc.bottom = v25;
    xLeft[0] = v27;
    v30 = *((_QWORD *)v6 + 29);
    xLeft[1] = v28;
    DUI_MapElementPoint(v30, v6, 0, xLeft, xLeft);
    SetRect(&rc, xLeft[0], xLeft[1], xLeft[0] + rc.right - rc.left, xLeft[1] + rc.bottom - rc.top);
    bottom = rc.bottom;
    left = rc.left;
    v33 = a3[13];
    right = rc.right;
    v35 = a3[6];
    if ( v33 != 1 )
    {
      right = rc.bottom;
      bottom = rc.right;
    }
    xLeft[0] = bottom;
    top = rc.top;
    if ( v33 != 1 )
      top = rc.left;
    v45 = right;
    if ( v33 != 1 )
      left = rc.top;
    v46 = top;
    v47 = v35 != 0 ? left : 0;
    if ( v35 + 1 >= (*(int (__fastcall **)(__int64))(*(_QWORD *)v20 + 40LL))(v20) )
    {
      VirtualDirection = UICollection::GetVirtualDirection(v6);
      ElementExtent = DUI_GetElementExtent((struct DirectUI::Element *)v6);
      if ( VirtualDirection != 1 )
        ElementExtent = (struct tagSIZE)HIDWORD(*(unsigned __int64 *)&ElementExtent);
    }
    else
    {
      ItemLayout = UICollection::GetItemLayout((UICollection *)v6);
      ElementExtent.cx = (*(__int64 (__fastcall **)(struct ItemLayout *))(*(_QWORD *)ItemLayout + 528LL))(ItemLayout);
      ElementExtent.cx += v45;
    }
    v39 = v46;
    a3[8] = 1;
    *v22 = v39;
    a3[10] = v47;
    a3[11] = xLeft[0];
    a3[12] = ElementExtent.cx;
    a3[13] = v33;
  }
}

```

## disassembly

```asm
0x18001a250  mov     [rsp-38h+arg_18], rbx
0x18001a255  push    rbp
0x18001a256  push    rsi
0x18001a257  push    rdi
0x18001a258  push    r12
0x18001a25a  push    r13
0x18001a25c  push    r14
0x18001a25e  push    r15
0x18001a260  mov     rbp, rsp
0x18001a263  sub     rsp, 60h
0x18001a267  mov     rax, cs:__security_cookie
0x18001a26e  xor     rax, rsp
0x18001a271  mov     [rbp+var_8], rax
0x18001a275  mov     r12, r8
0x18001a278  mov     qword ptr [rbp+xLeft], rcx
0x18001a27c  mov     r13d, edx
0x18001a27f  mov     rbx, rcx
0x18001a282  xor     edx, edx; Val
0x18001a284  mov     rcx, r12; void *
0x18001a287  lea     r8d, [rdx+58h]; Size
0x18001a28b  call    memset_0
0x18001a290  xor     r9d, r9d
0x18001a293  mov     dword ptr [r12+18h], 0FFFFFFFFh
0x18001a29c  lea     r15, [rbx-0D8h]
0x18001a2a3  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x18001a2aa  mov     rcx, r15
0x18001a2ad  lea     r8d, [r9+2]
0x18001a2b1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001a2b7  mov     rcx, rax
0x18001a2ba  mov     rbx, rax
0x18001a2bd  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001a2c3  mov     rcx, rbx
0x18001a2c6  mov     r14d, eax
0x18001a2c9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001a2cf  cmp     r13d, r14d
0x18001a2d2  jl      loc_18001A61C
0x18001a2d8  xor     esi, esi
0x18001a2da  cmp     [r15+0E8h], rsi
0x18001a2e1  jnz     short loc_18001A321
0x18001a2e3  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x18001a2ea  lea     rbx, [r15+0E0h]
0x18001a2f1  mov     rcx, r15; struct DirectUI::Element *
0x18001a2f4  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x18001a2f9  mov     rcx, rbx
0x18001a2fc  mov     rdi, rax
0x18001a2ff  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x18001a304  test    rdi, rdi
0x18001a307  jz      short loc_18001A321
0x18001a309  mov     rdx, rbx
0x18001a30c  mov     [rbx+8], rdi
0x18001a310  mov     rcx, rdi
0x18001a313  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18001a319  test    eax, eax
0x18001a31b  jns     short loc_18001A321
0x18001a31d  mov     [rbx+8], rsi
0x18001a321  mov     rcx, [r15+0E8h]
0x18001a328  test    rcx, rcx
0x18001a32b  jz      short loc_18001A358
0x18001a32d  xor     r9d, r9d
0x18001a330  lea     rdx, ?ScrollTickCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ScrollTickCountProp(void)
0x18001a337  lea     r8d, [r9+2]
0x18001a33b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001a341  mov     rcx, rax
0x18001a344  mov     rbx, rax
0x18001a347  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001a34d  mov     rcx, rbx
0x18001a350  mov     esi, eax
0x18001a352  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001a358  lea     eax, [rsi+r14]
0x18001a35c  cmp     r13d, eax
0x18001a35f  jge     loc_18001A5CD
0x18001a365  cmp     qword ptr [r15+0E8h], 0
0x18001a36d  jnz     short loc_18001A3B1
0x18001a36f  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x18001a376  lea     rbx, [r15+0E0h]
0x18001a37d  mov     rcx, r15; struct DirectUI::Element *
0x18001a380  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x18001a385  mov     rcx, rbx
0x18001a388  mov     rdi, rax
0x18001a38b  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x18001a390  test    rdi, rdi
0x18001a393  jz      short loc_18001A3B1
0x18001a395  mov     rdx, rbx
0x18001a398  mov     [rbx+8], rdi
0x18001a39c  mov     rcx, rdi
0x18001a39f  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18001a3a5  test    eax, eax
0x18001a3a7  jns     short loc_18001A3B1
0x18001a3a9  mov     qword ptr [rbx+8], 0
0x18001a3b1  mov     r14, [r15+0E8h]
0x18001a3b8  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x18001a3bf  xor     r9d, r9d
0x18001a3c2  mov     rcx, r15
0x18001a3c5  mov     rax, [r14]
0x18001a3c8  lea     r8d, [r9+2]
0x18001a3cc  mov     rsi, [rax+1B0h]
0x18001a3d3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001a3d9  mov     rcx, rax
0x18001a3dc  mov     rbx, rax
0x18001a3df  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001a3e5  mov     rcx, rbx
0x18001a3e8  mov     edi, eax
0x18001a3ea  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001a3f0  xor     ecx, ecx
0x18001a3f2  mov     r8, r12
0x18001a3f5  test    edi, edi
0x18001a3f7  mov     rax, rsi
0x18001a3fa  setnz   cl
0x18001a3fd  sub     r13d, ecx
0x18001a400  mov     rcx, r14
0x18001a403  mov     edx, r13d
0x18001a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a40b  xor     r9d, r9d
0x18001a40e  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x18001a415  mov     rcx, r15
0x18001a418  lea     r8d, [r9+2]
0x18001a41c  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001a422  mov     rcx, rax
0x18001a425  mov     rbx, rax
0x18001a428  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001a42e  mov     rcx, rbx
0x18001a431  mov     edi, eax
0x18001a433  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001a439  mov     esi, 1
0x18001a43e  test    edi, edi
0x18001a440  jnz     loc_18001A623
0x18001a446  mov     r13, qword ptr [rbp+xLeft]
0x18001a44a  mov     rax, r15
0x18001a44d  neg     rax
0x18001a450  sbb     rcx, rcx
0x18001a453  and     rcx, r13
0x18001a456  cmp     dword ptr [r12+20h], 0
0x18001a45c  mov     [r12], rcx
0x18001a460  jz      loc_18001A5DF
0x18001a466  cmp     qword ptr [r15+0E8h], 0
0x18001a46e  lea     rdi, [r12+24h]
0x18001a473  jnz     short loc_18001A4B7
0x18001a475  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x18001a47c  lea     rbx, [r15+0E0h]
0x18001a483  mov     rcx, r15; struct DirectUI::Element *
0x18001a486  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x18001a48b  mov     rcx, rbx
0x18001a48e  mov     r14, rax
0x18001a491  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x18001a496  test    r14, r14
0x18001a499  jz      short loc_18001A4B7
0x18001a49b  mov     rdx, rbx
0x18001a49e  mov     [rbx+8], r14
0x18001a4a2  mov     rcx, r14
0x18001a4a5  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18001a4ab  test    eax, eax
0x18001a4ad  jns     short loc_18001A4B7
0x18001a4af  mov     qword ptr [rbx+8], 0
0x18001a4b7  cmp     [rdi+10h], esi
0x18001a4ba  lea     rcx, [rdi+4]
0x18001a4be  mov     eax, 8
0x18001a4c3  lea     r9, [rbp+xLeft]
0x18001a4c7  lea     edx, [rax+4]
0x18001a4ca  cmovnz  eax, edx
0x18001a4cd  mov     r8d, [rax+rdi]
0x18001a4d1  mov     rax, rdi
0x18001a4d4  cmovnz  rax, rcx
0x18001a4d8  mov     ecx, [rcx]
0x18001a4da  cmovnz  ecx, [rdi]
0x18001a4dd  mov     edx, [rax]
0x18001a4df  mov     eax, [rdi+0Ch]
0x18001a4e2  cmovnz  eax, [rdi+8]
0x18001a4e6  mov     [rbp+rc.right], eax
0x18001a4e9  lea     rax, [rbp+xLeft]
0x18001a4ed  mov     [rbp+rc.left], ecx
0x18001a4f0  mov     [rbp+rc.top], edx
0x18001a4f3  mov     [rbp+rc.bottom], r8d
0x18001a4f7  xor     r8d, r8d
0x18001a4fa  mov     [rbp+xLeft], ecx
0x18001a4fd  mov     rcx, [r15+0E8h]
0x18001a504  mov     [rbp+xLeft+4], edx
0x18001a507  mov     rdx, r15
0x18001a50a  mov     qword ptr [rsp+60h+yBottom], rax
0x18001a50f  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x18001a514  mov     eax, [rbp+rc.bottom]
0x18001a517  lea     rcx, [rbp+rc]; lprc
0x18001a51b  mov     r9d, [rbp+rc.right]
0x18001a51f  sub     eax, [rbp+rc.top]
0x18001a522  mov     r8d, [rbp+xLeft+4]; yTop
0x18001a526  add     eax, r8d
0x18001a529  sub     r9d, [rbp+rc.left]
0x18001a52d  mov     edx, [rbp+xLeft]; xLeft
0x18001a530  add     r9d, edx; xRight
0x18001a533  mov     [rsp+60h+yBottom], eax; yBottom
0x18001a537  call    cs:__imp_SetRect
0x18001a53d  mov     eax, [rbp+rc.bottom]
0x18001a540  mov     edx, [rbp+rc.left]
0x18001a543  mov     r14d, [rdi+10h]
0x18001a547  cmp     r14d, esi
0x18001a54a  mov     ecx, [rbp+rc.right]
0x18001a54d  mov     ebx, [r12+18h]
0x18001a552  cmovnz  ecx, eax
0x18001a555  cmovnz  eax, [rbp+rc.right]
0x18001a559  mov     [rbp+xLeft], eax
0x18001a55c  mov     eax, [rbp+rc.top]
0x18001a55f  cmovnz  eax, edx
0x18001a562  mov     [rbp+var_28], ecx
0x18001a565  cmovnz  edx, [rbp+rc.top]
0x18001a569  mov     rcx, r13
0x18001a56c  mov     [rbp+var_24], eax
0x18001a56f  mov     eax, ebx
0x18001a571  neg     eax
0x18001a573  sbb     eax, eax
0x18001a575  and     eax, edx
0x18001a577  mov     [rbp+var_20], eax
0x18001a57a  mov     rax, [r13+0]
0x18001a57e  mov     rax, [rax+28h]
0x18001a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a587  lea     ecx, [rbx+1]
0x18001a58a  cmp     ecx, eax
0x18001a58c  mov     rcx, r15; this
0x18001a58f  jge     short loc_18001A603
0x18001a591  call    ?GetItemLayout@UICollection@@QEAAPEAVItemLayout@@XZ; UICollection::GetItemLayout(void)
0x18001a596  mov     rdx, rax
0x18001a599  mov     rcx, [rax]
0x18001a59c  mov     rax, [rcx+210h]
0x18001a5a3  mov     rcx, rdx
0x18001a5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ab  add     eax, [rbp+var_28]
0x18001a5ae  mov     ecx, [rbp+var_24]
0x18001a5b1  mov     [r12+20h], esi
0x18001a5b6  mov     [rdi], ecx
0x18001a5b8  mov     ecx, [rbp+var_20]
0x18001a5bb  mov     [rdi+4], ecx
0x18001a5be  mov     ecx, [rbp+xLeft]
0x18001a5c1  mov     [rdi+8], ecx
0x18001a5c4  mov     [rdi+0Ch], eax
0x18001a5c7  mov     [rdi+10h], r14d
0x18001a5cb  jmp     short loc_18001A5DF
0x18001a5cd  mov     esi, 4
0x18001a5d2  mov     r8, r12
0x18001a5d5  mov     edx, esi
0x18001a5d7  mov     rcx, r15
0x18001a5da  call    ?_GetHeaderFooterSectionInfo@UICollection@@IEAAXW4SECTIONTYPE@@PEAVSectionInfo@@@Z; UICollection::_GetHeaderFooterSectionInfo(SECTIONTYPE,SectionInfo *)
0x18001a5df  mov     rcx, [rbp+var_8]
0x18001a5e3  xor     rcx, rsp; StackCookie
0x18001a5e6  call    __security_check_cookie
0x18001a5eb  mov     rbx, [rsp+60h+arg_18]
0x18001a5f3  add     rsp, 60h
0x18001a5f7  pop     r15
0x18001a5f9  pop     r14
0x18001a5fb  pop     r13
0x18001a5fd  pop     r12
0x18001a5ff  pop     rdi
0x18001a600  pop     rsi
0x18001a601  pop     rbp
0x18001a602  retn
0x18001a603  call    ?GetVirtualDirection@UICollection@@QEAA?AW4VIRTUALDIRECTION@@XZ; UICollection::GetVirtualDirection(void)
0x18001a608  mov     rcx, r15; struct DirectUI::Element *
0x18001a60b  mov     ebx, eax
0x18001a60d  call    ?DUI_GetElementExtent@@YA?AUtagSIZE@@PEAVElement@DirectUI@@@Z; DUI_GetElementExtent(DirectUI::Element *)
0x18001a612  cmp     ebx, esi
0x18001a614  jz      short loc_18001A5AE
0x18001a616  shr     rax, 20h
0x18001a61a  jmp     short loc_18001A5AE
0x18001a61c  mov     esi, 1
0x18001a621  jmp     short loc_18001A5D2
0x18001a623  mov     rcx, r15; this
0x18001a626  call    ?_GetHeaderRowCount@UICollection@@IEAAHXZ; UICollection::_GetHeaderRowCount(void)
0x18001a62b  mov     rcx, r15; this
0x18001a62e  mov     ebx, eax
0x18001a630  call    ?GetHeaderScrollTicks@UICollection@@QEAAHXZ; UICollection::GetHeaderScrollTicks(void)
0x18001a635  add     [r12+48h], eax
0x18001a63a  add     [r12+4Ch], eax
0x18001a63f  add     [r12+40h], esi
0x18001a644  add     [r12+44h], esi
0x18001a649  add     [r12+18h], ebx
0x18001a64e  jmp     loc_18001A446
```
