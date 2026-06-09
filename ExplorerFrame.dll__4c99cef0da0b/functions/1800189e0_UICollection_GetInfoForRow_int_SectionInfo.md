# UICollection::GetInfoForRow(int,SectionInfo *)

- ea: `0x1800189e0`
- end: `0x180018e6d`
- name: `?GetInfoForRow@UICollection@@UEAAXHPEAVSectionInfo@@@Z`
- size: `1165`
- prototype: `void(UICollection *__hidden this, int, struct SectionInfo *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180015640`
- `0x180016790`
- `0x18001743c`
- `0x1800174e8`
- `0x1800189e0`
- `0x18001a65c`
- `0x18001ab28`
- `0x18001ae40`
- `0x18001b610`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `USER32!SetRect` at `0x180018d01`
- `USER32!SetRect` at `0x180018d01`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018ae4`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018b69`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018c6b`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018d95`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018ae4`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018b69`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018c6b`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018d95`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018a90`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018b1e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018bb0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018bf9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018a90`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018b1e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018bb0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018bf9`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018a85`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018b13`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018ba5`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018bee`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018a85`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018b13`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018ba5`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180018bee`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018a79`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018b07`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018b99`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018be2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018a79`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018b07`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018b99`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180018be2`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180018e18`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180018e18`

## pseudocode

```c
void __fastcall UICollection::GetInfoForRow(UICollection *this, int a2, LONG *a3)
{
  char *v6; // r15
  DirectUI::Value *Value; // rbx
  int Int; // edi
  int v9; // esi
  DirectUI::Element *DescendentElement; // rdi
  DirectUI::Value *v11; // rdi
  int v12; // ebx
  DirectUI::Element *v13; // rdi
  __int64 v14; // r14
  void (__fastcall *v15)(__int64, _QWORD, LONG *); // rsi
  DirectUI::Value *v16; // rbx
  int v17; // edi
  DirectUI::Value *v18; // rbx
  int v19; // edi
  __int64 v20; // rdi
  bool v21; // zf
  LONG *v22; // r14
  DirectUI::Element *v23; // r13
  __int64 v24; // rax
  LONG v25; // r8d
  LONG *v26; // rax
  LONG v27; // ecx
  LONG v28; // edx
  LONG v29; // eax
  __int64 v30; // rcx
  LONG bottom; // eax
  LONG left; // edx
  LONG v33; // r13d
  LONG right; // ecx
  LONG v35; // ebx
  LONG top; // eax
  DirectUI::Element *v37; // rdi
  int v38; // eax
  __int64 v39; // rbx
  unsigned int v40; // esi
  int VirtualDirection; // eax
  int v42; // edi
  int HeaderRowCount; // ebx
  int HeaderScrollTicks; // eax
  int xLeft[2]; // [rsp+30h] [rbp-30h] BYREF
  struct DirectUI::Value *v46; // [rsp+38h] [rbp-28h] BYREF
  LONG v47; // [rsp+40h] [rbp-20h]
  LONG v48; // [rsp+44h] [rbp-1Ch]
  struct tagRECT rc; // [rsp+48h] [rbp-18h] BYREF

  *(_QWORD *)xLeft = this;
  memset_0(a3, 0, 0x58u);
  a3[6] = -1;
  if ( a2 >= (*(int (__fastcall **)(UICollection *))(*(_QWORD *)this + 48LL))(this) )
    return;
  v6 = (char *)this - 216;
  Value = DirectUI::Element::GetValue((UICollection *)((char *)this - 216), UICollection::HeaderScrollTicksProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  v9 = Int != 0;
  if ( a2 < v9 )
  {
    v40 = 1;
    goto LABEL_42;
  }
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
  v11 = DirectUI::Element::GetValue(*((DirectUI::Element **)v6 + 29), ItemLayout::RowCountProp, 2, 0);
  v12 = DirectUI::Value::GetInt(v11);
  DirectUI::Value::Release(v11);
  if ( a2 >= v9 + v12 )
  {
    v40 = 4;
LABEL_42:
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
  v15 = *(void (__fastcall **)(__int64, _QWORD, LONG *))(*(_QWORD *)v14 + 424LL);
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
    LODWORD(v46) = right;
    if ( v33 != 1 )
      left = rc.top;
    v47 = top;
    v48 = v35 != 0 ? left : 0;
    if ( v35 + 1 >= (*(int (__fastcall **)(__int64))(*(_QWORD *)v20 + 40LL))(v20) )
    {
      VirtualDirection = UICollection::GetVirtualDirection(v6);
      v46 = 0;
      v42 = VirtualDirection;
      v39 = (__int64)*DirectUI::Element::GetExtent((DirectUI::Element *)v6, &v46);
      *(_QWORD *)&rc.left = v39;
      CValuePtr::~CValuePtr((CValuePtr *)&v46);
      if ( v42 != 1 )
        LODWORD(v39) = rc.top;
    }
    else
    {
      if ( !*((_QWORD *)v6 + 29) )
      {
        v37 = _FindDescendentElement((struct DirectUI::Element *)v6, ItemLayout::Class);
        CSafeElementPtr<ItemRowLayout>::Unassign(v6 + 224);
        if ( v37 )
        {
          *((_QWORD *)v6 + 29) = v37;
          if ( (int)DirectUI::Element::AddListener(v37, (struct DirectUI::IElementListener *)(v6 + 224)) < 0 )
            *((_QWORD *)v6 + 29) = 0;
        }
      }
      v38 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 29) + 528LL))(*((_QWORD *)v6 + 29));
      LODWORD(v39) = (_DWORD)v46 + v38;
    }
    *v22 = v47;
    a3[10] = v48;
    a3[11] = xLeft[0];
    a3[8] = 1;
    a3[12] = v39;
    a3[13] = v33;
  }
}

```

## disassembly

```asm
0x1800189e0  mov     [rsp-38h+arg_18], rbx
0x1800189e5  push    rbp
0x1800189e6  push    rsi
0x1800189e7  push    rdi
0x1800189e8  push    r12
0x1800189ea  push    r13
0x1800189ec  push    r14
0x1800189ee  push    r15
0x1800189f0  mov     rbp, rsp
0x1800189f3  sub     rsp, 60h
0x1800189f7  mov     rax, cs:__security_cookie
0x1800189fe  xor     rax, rsp
0x180018a01  mov     [rbp+var_8], rax
0x180018a05  mov     r12, r8
0x180018a08  mov     qword ptr [rbp+xLeft], rcx
0x180018a0c  mov     r13d, edx
0x180018a0f  mov     rbx, rcx
0x180018a12  xor     edx, edx; Val
0x180018a14  mov     rcx, r12; void *
0x180018a17  lea     r8d, [rdx+58h]; Size
0x180018a1b  call    memset_0
0x180018a20  mov     dword ptr [r12+18h], 0FFFFFFFFh
0x180018a29  mov     rcx, rbx
0x180018a2c  mov     rax, [rbx]
0x180018a2f  mov     rax, [rax+30h]
0x180018a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a38  cmp     r13d, eax
0x180018a3b  jl      short loc_180018A61
0x180018a3d  mov     rcx, [rbp+var_8]
0x180018a41  xor     rcx, rsp; StackCookie
0x180018a44  call    __security_check_cookie
0x180018a49  mov     rbx, [rsp+60h+arg_18]
0x180018a51  add     rsp, 60h
0x180018a55  pop     r15
0x180018a57  pop     r14
0x180018a59  pop     r13
0x180018a5b  pop     r12
0x180018a5d  pop     rdi
0x180018a5e  pop     rsi
0x180018a5f  pop     rbp
0x180018a60  retn
0x180018a61  xor     r9d, r9d
0x180018a64  lea     r15, [rbx-0D8h]
0x180018a6b  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x180018a72  mov     rcx, r15
0x180018a75  lea     r8d, [r9+2]
0x180018a79  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180018a7f  mov     rcx, rax
0x180018a82  mov     rbx, rax
0x180018a85  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180018a8b  mov     rcx, rbx
0x180018a8e  mov     edi, eax
0x180018a90  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018a96  xor     r14d, r14d
0x180018a99  test    edi, edi
0x180018a9b  mov     esi, r14d
0x180018a9e  setnz   sil
0x180018aa2  cmp     r13d, esi
0x180018aa5  jl      loc_180018E36
0x180018aab  cmp     [r15+0E8h], r14
0x180018ab2  jnz     short loc_180018AF2
0x180018ab4  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180018abb  lea     rbx, [r15+0E0h]
0x180018ac2  mov     rcx, r15; struct DirectUI::Element *
0x180018ac5  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180018aca  mov     rcx, rbx
0x180018acd  mov     rdi, rax
0x180018ad0  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018ad5  test    rdi, rdi
0x180018ad8  jz      short loc_180018AF2
0x180018ada  mov     rdx, rbx
0x180018add  mov     [rbx+8], rdi
0x180018ae1  mov     rcx, rdi
0x180018ae4  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018aea  test    eax, eax
0x180018aec  jns     short loc_180018AF2
0x180018aee  mov     [rbx+8], r14
0x180018af2  mov     rcx, [r15+0E8h]
0x180018af9  lea     rdx, ?RowCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::RowCountProp(void)
0x180018b00  xor     r9d, r9d
0x180018b03  lea     r8d, [r9+2]
0x180018b07  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180018b0d  mov     rcx, rax
0x180018b10  mov     rdi, rax
0x180018b13  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180018b19  mov     rcx, rdi
0x180018b1c  mov     ebx, eax
0x180018b1e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018b24  lea     eax, [rsi+rbx]
0x180018b27  cmp     r13d, eax
0x180018b2a  jge     loc_180018DE8
0x180018b30  cmp     [r15+0E8h], r14
0x180018b37  jnz     short loc_180018B77
0x180018b39  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180018b40  lea     rbx, [r15+0E0h]
0x180018b47  mov     rcx, r15; struct DirectUI::Element *
0x180018b4a  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180018b4f  mov     rcx, rbx
0x180018b52  mov     rdi, rax
0x180018b55  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018b5a  test    rdi, rdi
0x180018b5d  jz      short loc_180018B77
0x180018b5f  mov     rdx, rbx
0x180018b62  mov     [rbx+8], rdi
0x180018b66  mov     rcx, rdi
0x180018b69  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018b6f  test    eax, eax
0x180018b71  jns     short loc_180018B77
0x180018b73  mov     [rbx+8], r14
0x180018b77  mov     r14, [r15+0E8h]
0x180018b7e  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x180018b85  xor     r9d, r9d
0x180018b88  mov     rcx, r15
0x180018b8b  mov     rax, [r14]
0x180018b8e  lea     r8d, [r9+2]
0x180018b92  mov     rsi, [rax+1A8h]
0x180018b99  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180018b9f  mov     rcx, rax
0x180018ba2  mov     rbx, rax
0x180018ba5  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180018bab  mov     rcx, rbx
0x180018bae  mov     edi, eax
0x180018bb0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018bb6  xor     ecx, ecx
0x180018bb8  mov     r8, r12
0x180018bbb  test    edi, edi
0x180018bbd  mov     rax, rsi
0x180018bc0  setnz   cl
0x180018bc3  sub     r13d, ecx
0x180018bc6  mov     rcx, r14
0x180018bc9  mov     edx, r13d
0x180018bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bd1  xor     r9d, r9d
0x180018bd4  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x180018bdb  mov     rcx, r15
0x180018bde  lea     r8d, [r9+2]
0x180018be2  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180018be8  mov     rcx, rax
0x180018beb  mov     rbx, rax
0x180018bee  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180018bf4  mov     rcx, rbx
0x180018bf7  mov     edi, eax
0x180018bf9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018bff  mov     esi, 1
0x180018c04  test    edi, edi
0x180018c06  jnz     loc_180018E3D
0x180018c0c  mov     rdi, qword ptr [rbp+xLeft]
0x180018c10  mov     rax, r15
0x180018c13  neg     rax
0x180018c16  sbb     rcx, rcx
0x180018c19  and     rcx, rdi
0x180018c1c  cmp     dword ptr [r12+20h], 0
0x180018c22  mov     [r12], rcx
0x180018c26  jz      loc_180018A3D
0x180018c2c  cmp     qword ptr [r15+0E8h], 0
0x180018c34  lea     r14, [r12+24h]
0x180018c39  jnz     short loc_180018C7D
0x180018c3b  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180018c42  lea     rbx, [r15+0E0h]
0x180018c49  mov     rcx, r15; struct DirectUI::Element *
0x180018c4c  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180018c51  mov     rcx, rbx
0x180018c54  mov     r13, rax
0x180018c57  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018c5c  test    r13, r13
0x180018c5f  jz      short loc_180018C7D
0x180018c61  mov     rdx, rbx
0x180018c64  mov     [rbx+8], r13
0x180018c68  mov     rcx, r13
0x180018c6b  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018c71  test    eax, eax
0x180018c73  jns     short loc_180018C7D
0x180018c75  mov     qword ptr [rbx+8], 0
0x180018c7d  cmp     [r14+10h], esi
0x180018c81  lea     rcx, [r14+4]
0x180018c85  mov     eax, 8
0x180018c8a  lea     r9, [rbp+xLeft]
0x180018c8e  lea     edx, [rax+4]
0x180018c91  cmovnz  eax, edx
0x180018c94  mov     r8d, [rax+r14]
0x180018c98  mov     rax, r14
0x180018c9b  cmovnz  rax, rcx
0x180018c9f  mov     ecx, [rcx]
0x180018ca1  cmovnz  ecx, [r14]
0x180018ca5  mov     edx, [rax]
0x180018ca7  mov     eax, [r14+0Ch]
0x180018cab  cmovnz  eax, [r14+8]
0x180018cb0  mov     [rbp+rc.right], eax
0x180018cb3  lea     rax, [rbp+xLeft]
0x180018cb7  mov     [rbp+rc.left], ecx
0x180018cba  mov     [rbp+rc.top], edx
0x180018cbd  mov     [rbp+rc.bottom], r8d
0x180018cc1  xor     r8d, r8d
0x180018cc4  mov     [rbp+xLeft], ecx
0x180018cc7  mov     rcx, [r15+0E8h]
0x180018cce  mov     [rbp+xLeft+4], edx
0x180018cd1  mov     rdx, r15
0x180018cd4  mov     qword ptr [rsp+60h+yBottom], rax
0x180018cd9  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x180018cde  mov     eax, [rbp+rc.bottom]
0x180018ce1  lea     rcx, [rbp+rc]; lprc
0x180018ce5  mov     r9d, [rbp+rc.right]
0x180018ce9  sub     eax, [rbp+rc.top]
0x180018cec  mov     r8d, [rbp+xLeft+4]; yTop
0x180018cf0  add     eax, r8d
0x180018cf3  sub     r9d, [rbp+rc.left]
0x180018cf7  mov     edx, [rbp+xLeft]; xLeft
0x180018cfa  add     r9d, edx; xRight
0x180018cfd  mov     [rsp+60h+yBottom], eax; yBottom
0x180018d01  call    cs:__imp_SetRect
0x180018d07  mov     eax, [rbp+rc.bottom]
0x180018d0a  mov     edx, [rbp+rc.left]
0x180018d0d  mov     r13d, [r14+10h]
0x180018d11  cmp     r13d, esi
0x180018d14  mov     ecx, [rbp+rc.right]
0x180018d17  mov     ebx, [r12+18h]
0x180018d1c  cmovnz  ecx, eax
0x180018d1f  cmovnz  eax, [rbp+rc.right]
0x180018d23  mov     [rbp+xLeft], eax
0x180018d26  mov     eax, [rbp+rc.top]
0x180018d29  cmovnz  eax, edx
0x180018d2c  mov     dword ptr [rbp+var_28], ecx
0x180018d2f  cmovnz  edx, [rbp+rc.top]
0x180018d33  mov     rcx, rdi
0x180018d36  mov     [rbp+var_20], eax
0x180018d39  mov     eax, ebx
0x180018d3b  neg     eax
0x180018d3d  sbb     eax, eax
0x180018d3f  and     eax, edx
0x180018d41  mov     [rbp+var_1C], eax
0x180018d44  mov     rax, [rdi]
0x180018d47  mov     rax, [rax+28h]
0x180018d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d50  lea     ecx, [rbx+1]
0x180018d53  cmp     ecx, eax
0x180018d55  jge     loc_180018DFF
0x180018d5b  cmp     qword ptr [r15+0E8h], 0
0x180018d63  jnz     short loc_180018DA7
0x180018d65  mov     rdx, cs:?Class@ItemLayout@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180018d6c  lea     rbx, [r15+0E0h]
0x180018d73  mov     rcx, r15; struct DirectUI::Element *
0x180018d76  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180018d7b  mov     rcx, rbx
0x180018d7e  mov     rdi, rax
0x180018d81  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018d86  test    rdi, rdi
0x180018d89  jz      short loc_180018DA7
0x180018d8b  mov     rdx, rbx
0x180018d8e  mov     [rbx+8], rdi
0x180018d92  mov     rcx, rdi
0x180018d95  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018d9b  test    eax, eax
0x180018d9d  jns     short loc_180018DA7
0x180018d9f  mov     qword ptr [rbx+8], 0
0x180018da7  mov     rcx, [r15+0E8h]
0x180018dae  mov     rax, [rcx]
0x180018db1  mov     rax, [rax+210h]
0x180018db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dbd  mov     ebx, eax
0x180018dbf  add     ebx, dword ptr [rbp+var_28]
0x180018dc2  mov     eax, [rbp+var_20]
0x180018dc5  mov     [r14], eax
0x180018dc8  mov     eax, [rbp+var_1C]
0x180018dcb  mov     [r14+4], eax
0x180018dcf  mov     eax, [rbp+xLeft]
0x180018dd2  mov     [r14+8], eax
0x180018dd6  mov     [r12+20h], esi
0x180018ddb  mov     [r14+0Ch], ebx
0x180018ddf  mov     [r14+10h], r13d
0x180018de3  jmp     loc_180018A3D
0x180018de8  mov     esi, 4
0x180018ded  mov     r8, r12
0x180018df0  mov     edx, esi
0x180018df2  mov     rcx, r15
0x180018df5  call    ?_GetHeaderFooterSectionInfo@UICollection@@IEAAXW4SECTIONTYPE@@PEAVSectionInfo@@@Z; UICollection::_GetHeaderFooterSectionInfo(SECTIONTYPE,SectionInfo *)
0x180018dfa  jmp     loc_180018A3D
0x180018dff  mov     rcx, r15
0x180018e02  call    ?GetVirtualDirection@UICollection@@QEAA?AW4VIRTUALDIRECTION@@XZ; UICollection::GetVirtualDirection(void)
0x180018e07  lea     rdx, [rbp+var_28]
0x180018e0b  mov     [rbp+var_28], 0
0x180018e13  mov     rcx, r15
0x180018e16  mov     edi, eax
0x180018e18  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180018e1e  lea     rcx, [rbp+var_28]; this
0x180018e22  mov     rbx, [rax]
0x180018e25  mov     qword ptr [rbp+rc.left], rbx
0x180018e29  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180018e2e  cmp     edi, esi
0x180018e30  cmovnz  ebx, [rbp+rc.top]
0x180018e34  jmp     short loc_180018DC2
0x180018e36  mov     esi, 1
0x180018e3b  jmp     short loc_180018DED
0x180018e3d  mov     rcx, r15; this
0x180018e40  call    ?_GetHeaderRowCount@UICollection@@IEAAHXZ; UICollection::_GetHeaderRowCount(void)
0x180018e45  mov     rcx, r15; this
0x180018e48  mov     ebx, eax
0x180018e4a  call    ?GetHeaderScrollTicks@UICollection@@QEAAHXZ; UICollection::GetHeaderScrollTicks(void)
0x180018e4f  add     [r12+48h], eax
0x180018e54  add     [r12+4Ch], eax
0x180018e59  add     [r12+40h], esi
  ... truncated ...
```
