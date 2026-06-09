# UICollection::_ReuseAndDestroyExistingChildren(ItemLayout *)

- ea: `0x180080360`
- end: `0x1800807e3`
- name: `?_ReuseAndDestroyExistingChildren@UICollection@@IEAAXPEAVItemLayout@@@Z`
- size: `1155`
- prototype: `void __fastcall(UICollection *__hidden this, struct ItemLayout *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b1a8`

## callees

- `0x18001b65c`
- `0x18001b8d0`
- `0x18001b8dc`
- `0x18001c560`
- `0x18001c7c4`
- `0x180033370`
- `0x18005b3f0`
- `0x18007ea30`
- `0x180080360`
- `0x1800807ec`
- `0x180080b80`
- `0x1800a6364`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080642`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800806ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800806ac`
- `DUI70!StrToID` at `0x1800805b2`
- `DUI70!StrToID` at `0x1800805b2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180080795`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180080795`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800803b9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800804ee`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800803b9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800804ee`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800804e3`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x1800804e3`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180080396`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180080396`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800804d7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800804d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall UICollection::_ReuseAndDestroyExistingChildren(UICollection *this, struct ItemLayout *a2)
{
  struct ItemLayout *v2; // r15
  _DWORD *Children; // rax
  _DWORD *v5; // rbx
  DirectUI::Value *v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // r15
  __int64 v13; // r12
  __int64 v14; // r15
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rbx
  _QWORD *v18; // rax
  DirectUI::Value *Value; // rdi
  bool Bool; // bl
  unsigned __int16 *v21; // rbx
  int UIItemResId; // eax
  __int16 v23; // di
  struct IItem *v24; // rdi
  __int64 v25; // rdx
  int (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rcx
  UIItemsView *UIItemsView; // rax
  int v28; // eax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rbx
  UIItem *v32; // rax
  struct UIItem *v33; // rdi
  unsigned int v34; // [rsp+30h] [rbp-49h]
  _QWORD *v35; // [rsp+38h] [rbp-41h] BYREF
  __int64 v36; // [rsp+40h] [rbp-39h]
  __int64 v37; // [rsp+48h] [rbp-31h]
  __int64 v38; // [rsp+50h] [rbp-29h]
  struct IItem *v39; // [rsp+58h] [rbp-21h] BYREF
  unsigned int ItemCountFromCollection; // [rsp+60h] [rbp-19h]
  __int64 v41; // [rsp+68h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-9h] BYREF
  DirectUI::Value *v43; // [rsp+78h] [rbp-1h] BYREF
  char v44[8]; // [rsp+80h] [rbp+7h] BYREF
  _DWORD *v45; // [rsp+88h] [rbp+Fh]
  _QWORD *v46; // [rsp+90h] [rbp+17h]
  unsigned int v48; // [rsp+F0h] [rbp+77h]
  int v49; // [rsp+F8h] [rbp+7Fh]

  v2 = a2;
  v43 = 0;
  Children = (_DWORD *)DirectUI::Element::GetChildren(a2, &v43);
  v5 = Children;
  v45 = Children;
  if ( !Children )
    goto LABEL_2;
  v7 = 0;
  v35 = 0;
  v8 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v9 = *Children & 0xFFFFFFF;
  v48 = v9;
  ItemCountFromCollection = UICollection::_GetItemCountFromCollection(this);
  v49 = 1;
  v10 = 0;
  v34 = 0;
  if ( !v9 )
    goto LABEL_36;
  v11 = v5 + 2;
  v46 = v5 + 2;
  do
  {
    if ( (*v5 & 0x10000000) != 0 )
      v12 = (_QWORD *)*v11;
    else
      v12 = v11;
    v13 = (unsigned int)v10;
    v14 = v12[v10];
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 280LL))(v14);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v15 + 80LL))(
              v15,
              UIItem::Class) )
      {
        v11 = v5 + 2;
        goto LABEL_12;
      }
      Value = DirectUI::Element::GetValue((DirectUI::Element *)v14, UIItem::ModelProp, 2, 0);
      Bool = DirectUI::Value::GetBool(Value);
      DirectUI::Value::Release(Value);
      if ( !Bool )
      {
        if ( v49 )
        {
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(v44);
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v39);
          v21 = 0;
          pv = 0;
          if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 440LL))(v14, v44) >= 0
            && v34 < ItemCountFromCollection
            && (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *, struct IItem **))(**((_QWORD **)this + 30) + 56LL))(
                 *((_QWORD *)this + 30),
                 *((unsigned int *)this + 68),
                 *(unsigned int *)(v14 + 200),
                 &GUID_aecc1438_059c_44ad_a2b4_e87f4d3a4987,
                 &v39) >= 0 )
          {
            CoTaskMemFree(0);
            UIItemResId = UICollection::_GetUIItemResId(this, (WCHAR *)v39, (unsigned __int16 **)&pv);
            v21 = (unsigned __int16 *)pv;
            if ( UIItemResId >= 0 )
            {
              v23 = *(_WORD *)(v14 + 208);
              if ( (unsigned __int16)StrToID(pv) == v23 )
              {
                v24 = v39;
                if ( GetUIItemsView(this) )
                {
                  ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v41);
                  v26 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v25 + 328);
                  if ( v26 && (**v26)(v26, &GUID_204e242d_3780_4a3e_bcd2_a8b39537f66c, &v41) >= 0 )
                    *(_DWORD *)(v14 + 240) = (*(__int64 (__fastcall **)(__int64, struct IItem *))(*(_QWORD *)v41 + 24LL))(
                                               v41,
                                               v24);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v41);
                }
                (*(void (__fastcall **)(__int64, struct IItem *))(*(_QWORD *)v14 + 432LL))(v14, v39);
                goto LABEL_32;
              }
              if ( (int)UICollection::_RecreateUIItem(this, (struct UIItem *)v14, v39, v21) >= 0 )
                goto LABEL_32;
            }
          }
          if ( v8 != v38
            || (v28 = CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(
                        &v35,
                        v8 + 1),
                v7 = v35,
                v8 = v36,
                v28 >= 0) )
          {
            v29 = &v7[v8++];
            v36 = v8;
            if ( v29 )
              *v29 = v14;
          }
          v49 = 0;
LABEL_32:
          CoTaskMemFree(v21);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v39);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v44);
LABEL_33:
          v9 = v48;
          goto LABEL_34;
        }
        if ( v8 == v38 )
        {
          if ( (int)CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(
                      &v35,
                      v8 + 1) < 0 )
          {
LABEL_46:
            v8 = v36;
            v7 = v35;
            goto LABEL_33;
          }
          v8 = v36;
          v7 = v35;
        }
        v36 = ++v8;
        v30 = &v7[v8 - 1];
        if ( v30 )
          *v30 = v14;
        goto LABEL_33;
      }
      v5 = v45;
      v11 = v46;
      v9 = v48;
    }
LABEL_12:
    if ( (*v5 & 0x10000000) != 0 )
      v16 = (_QWORD *)*v11;
    else
      v16 = v11;
    v17 = v16[v13];
    if ( v8 == v38 )
    {
      if ( (int)CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(
                  &v35,
                  v8 + 1) < 0 )
        goto LABEL_46;
      v8 = v36;
      v7 = v35;
    }
    v36 = ++v8;
    v18 = &v7[v8 - 1];
    if ( v18 )
      *v18 = v17;
LABEL_34:
    v10 = v34 + 1;
    v34 = v10;
    v5 = v45;
    v11 = v45 + 2;
  }
  while ( (unsigned int)v10 < v9 );
  v2 = a2;
LABEL_36:
  if ( GetUIItemsView(this) )
  {
    UIItemsView = GetUIItemsView(this);
    UIItemsView::OnItemsReused(UIItemsView);
  }
  if ( (_DWORD)v8
    && (*(int (__fastcall **)(struct ItemLayout *, _QWORD *, _QWORD))(*(_QWORD *)v2 + 144LL))(v2, v7, (unsigned int)v8) >= 0 )
  {
    v31 = 0;
    do
    {
      v32 = (UIItem *)element_cast<UIItem>(v7[v31]);
      v33 = v32;
      if ( v32 && !UIItem::GetModel(v32) )
        UICollection::_UnrealizeItem(this, v33);
      DirectUI::Element::Destroy((DirectUI::Element *)v7[v31], 1);
      v31 = (unsigned int)(v31 + 1);
    }
    while ( (unsigned int)v31 < (unsigned int)v8 );
  }
  if ( v7 )
    LocalFree(v7);
LABEL_2:
  v6 = v43;
  if ( v43 )
  {
    v43 = 0;
    DirectUI::Value::Release(v6);
  }
}

```

## disassembly

```asm
0x180080360  mov     [rsp-8+arg_0], rbx
0x180080365  mov     [rsp-8+arg_8], rdx
0x18008036a  push    rbp
0x18008036b  push    rsi
0x18008036c  push    rdi
0x18008036d  push    r12
0x18008036f  push    r13
0x180080371  push    r14
0x180080373  push    r15
0x180080375  lea     rbp, [rsp-27h]
0x18008037a  sub     rsp, 0A0h
0x180080381  mov     r15, rdx
0x180080384  mov     r13, rcx
0x180080387  mov     [rbp+57h+var_58], 0
0x18008038f  lea     rdx, [rbp+57h+var_58]
0x180080393  mov     rcx, r15
0x180080396  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18008039c  mov     rbx, rax
0x18008039f  mov     [rbp+57h+var_48], rax
0x1800803a3  test    rax, rax
0x1800803a6  jnz     short loc_1800803DB
0x1800803a8  mov     rcx, [rbp+57h+var_58]
0x1800803ac  test    rcx, rcx
0x1800803af  jz      short loc_1800803C0
0x1800803b1  mov     [rbp+57h+var_58], 0
0x1800803b9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800803bf  nop
0x1800803c0  mov     rbx, [rsp+0D0h+arg_0]
0x1800803c8  add     rsp, 0A0h
0x1800803cf  pop     r15
0x1800803d1  pop     r14
0x1800803d3  pop     r13
0x1800803d5  pop     r12
0x1800803d7  pop     rdi
0x1800803d8  pop     rsi
0x1800803d9  pop     rbp
0x1800803da  retn
0x1800803db  xor     r14d, r14d
0x1800803de  mov     [rbp+57h+var_98], r14
0x1800803e2  xor     esi, esi
0x1800803e4  mov     [rbp+57h+var_90], rsi
0x1800803e8  mov     [rbp+57h+var_88], rsi
0x1800803ec  mov     [rbp+57h+var_80], rsi
0x1800803f0  mov     edi, [rax]
0x1800803f2  and     edi, 0FFFFFFFh
0x1800803f8  mov     [rbp+57h+arg_10], edi
0x1800803fb  mov     rcx, r13; this
0x1800803fe  call    ?_GetItemCountFromCollection@UICollection@@IEAAIXZ; UICollection::_GetItemCountFromCollection(void)
0x180080403  mov     [rbp+57h+var_70], eax
0x180080406  mov     [rbp+57h+arg_18], 1
0x18008040d  xor     eax, eax
0x18008040f  mov     [rbp+57h+var_A0], eax
0x180080412  test    edi, edi
0x180080414  jz      loc_18008067B
0x18008041a  lea     rcx, [rbx+8]
0x18008041e  mov     [rbp+57h+var_40], rcx
0x180080422  test    dword ptr [rbx], 10000000h
0x180080428  jz      loc_1800807A6
0x18008042e  mov     r15, [rcx]
0x180080431  mov     r12d, eax
0x180080434  mov     r15, [r15+rax*8]
0x180080438  test    r15, r15
0x18008043b  jz      short loc_180080470
0x18008043d  mov     rax, [r15]
0x180080440  mov     rcx, r15
0x180080443  mov     rax, [rax+118h]
0x18008044a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008044f  mov     r8, rax
0x180080452  mov     rcx, [rax]
0x180080455  mov     rax, [rcx+50h]
0x180080459  mov     rdx, cs:?Class@UIItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItem::Class
0x180080460  mov     rcx, r8
0x180080463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080468  test    al, al
0x18008046a  jnz     short loc_1800804C6
0x18008046c  lea     rcx, [rbx+8]
0x180080470  test    dword ptr [rbx], 10000000h
0x180080476  jz      loc_1800807AE
0x18008047c  mov     rax, [rcx]
0x18008047f  mov     rbx, [rax+r12*8]
0x180080483  cmp     rsi, [rbp+57h+var_80]
0x180080487  jnz     short loc_1800804A6
0x180080489  lea     rdx, [rsi+1]
0x18008048d  lea     rcx, [rbp+57h+var_98]
0x180080491  call    ?_EnsureCapacity@?$CTSimpleArray@PEAVElement@DirectUI@@$0PPPPPPPO@V?$CTPolicyLocalMem@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardCompareHelper@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardMergeHelper@PEAVElement@DirectUI@@@@@@QEAAJ_K0@Z; CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180080496  test    eax, eax
0x180080498  js      loc_1800806F9
0x18008049e  mov     rsi, [rbp+57h+var_90]
0x1800804a2  mov     r14, [rbp+57h+var_98]
0x1800804a6  inc     rsi
0x1800804a9  mov     [rbp+57h+var_90], rsi
0x1800804ad  lea     rax, [rsi-1]
0x1800804b1  lea     rax, [r14+rax*8]
0x1800804b5  test    rax, rax
0x1800804b8  jz      loc_18008065F
0x1800804be  mov     [rax], rbx
0x1800804c1  jmp     loc_18008065F
0x1800804c6  xor     r9d, r9d
0x1800804c9  lea     r8d, [r9+2]
0x1800804cd  lea     rdx, ?ModelProp@UIItem@@SAPEBUPropertyInfo@DirectUI@@XZ; UIItem::ModelProp(void)
0x1800804d4  mov     rcx, r15
0x1800804d7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800804dd  mov     rdi, rax
0x1800804e0  mov     rcx, rax
0x1800804e3  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x1800804e9  mov     bl, al
0x1800804eb  mov     rcx, rdi
0x1800804ee  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800804f4  test    bl, bl
0x1800804f6  jnz     loc_1800807D2
0x1800804fc  cmp     [rbp+57h+arg_18], 0
0x180080500  jz      loc_180080706
0x180080506  lea     rcx, [rbp+57h+var_50]; void *
0x18008050a  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18008050f  nop
0x180080510  lea     rcx, [rbp+57h+var_78]; void *
0x180080514  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180080519  nop
0x18008051a  xor     ebx, ebx
0x18008051c  mov     [rbp+57h+pv], rbx
0x180080520  mov     rax, [r15]
0x180080523  lea     rdx, [rbp+57h+var_50]
0x180080527  mov     rcx, r15
0x18008052a  mov     rax, [rax+1B8h]
0x180080531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080536  test    eax, eax
0x180080538  js      loc_1800806B7
0x18008053e  mov     eax, [rbp+57h+var_70]
0x180080541  cmp     [rbp+57h+var_A0], eax
0x180080544  jnb     loc_1800806B7
0x18008054a  mov     rcx, [r13+0F0h]
0x180080551  mov     rax, [rcx]
0x180080554  lea     rdx, [rbp+57h+var_78]
0x180080558  mov     [rsp+0D0h+var_B0], rdx
0x18008055d  lea     r9, _GUID_aecc1438_059c_44ad_a2b4_e87f4d3a4987
0x180080564  mov     r8d, [r15+0C8h]
0x18008056b  mov     edx, [r13+110h]
0x180080572  mov     rax, [rax+38h]
0x180080576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008057b  test    eax, eax
0x18008057d  js      loc_1800806B7
0x180080583  xor     ecx, ecx; pv
0x180080585  call    cs:__imp_CoTaskMemFree
0x18008058b  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x18008058f  mov     rdx, [rbp+57h+var_78]; struct IItem *
0x180080593  mov     rcx, r13; this
0x180080596  call    ?_GetUIItemResId@UICollection@@IEAAJPEAUIItem@@PEAPEAG@Z; UICollection::_GetUIItemResId(IItem *,ushort * *)
0x18008059b  mov     rbx, [rbp+57h+pv]
0x18008059f  test    eax, eax
0x1800805a1  js      loc_1800806B7
0x1800805a7  movzx   edi, word ptr [r15+0D0h]
0x1800805af  mov     rcx, rbx
0x1800805b2  call    cs:__imp_StrToID
0x1800805b8  mov     rcx, r13; this
0x1800805bb  cmp     ax, di
0x1800805be  jnz     loc_1800807B6
0x1800805c4  mov     rdi, [rbp+57h+var_78]
0x1800805c8  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x1800805cd  mov     rdx, rax
0x1800805d0  test    rax, rax
0x1800805d3  jz      short loc_180080628
0x1800805d5  lea     rcx, [rbp+57h+var_68]; void *
0x1800805d9  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x1800805de  nop
0x1800805df  mov     rcx, [rdx+148h]
0x1800805e6  test    rcx, rcx
0x1800805e9  jz      short loc_18008061F
0x1800805eb  mov     rax, [rcx]
0x1800805ee  lea     r8, [rbp+57h+var_68]
0x1800805f2  lea     rdx, _GUID_204e242d_3780_4a3e_bcd2_a8b39537f66c
0x1800805f9  mov     rax, [rax]
0x1800805fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080601  test    eax, eax
0x180080603  js      short loc_18008061F
0x180080605  mov     rcx, [rbp+57h+var_68]
0x180080609  mov     rax, [rcx]
0x18008060c  mov     rdx, rdi
0x18008060f  mov     rax, [rax+18h]
0x180080613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080618  mov     [r15+0F0h], eax
0x18008061f  lea     rcx, [rbp+57h+var_68]; void *
0x180080623  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180080628  mov     rax, [r15]
0x18008062b  mov     rdx, [rbp+57h+var_78]
0x18008062f  mov     rcx, r15
0x180080632  mov     rax, [rax+1B0h]
0x180080639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008063e  nop
0x18008063f  mov     rcx, rbx; pv
0x180080642  call    cs:__imp_CoTaskMemFree
0x180080648  nop
0x180080649  lea     rcx, [rbp+57h+var_78]; void *
0x18008064d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180080652  nop
0x180080653  lea     rcx, [rbp+57h+var_50]; void *
0x180080657  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18008065c  mov     edi, [rbp+57h+arg_10]
0x18008065f  mov     eax, [rbp+57h+var_A0]
0x180080662  inc     eax
0x180080664  mov     [rbp+57h+var_A0], eax
0x180080667  cmp     eax, edi
0x180080669  mov     rbx, [rbp+57h+var_48]
0x18008066d  lea     rcx, [rbx+8]
0x180080671  jb      loc_180080422
0x180080677  mov     r15, [rbp+57h+arg_8]
0x18008067b  mov     rcx, r13; struct DirectUI::Element *
0x18008067e  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x180080683  test    rax, rax
0x180080686  jz      short loc_180080698
0x180080688  mov     rcx, r13; struct DirectUI::Element *
0x18008068b  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x180080690  mov     rcx, rax; this
0x180080693  call    ?OnItemsReused@UIItemsView@@QEAAXXZ; UIItemsView::OnItemsReused(void)
0x180080698  test    esi, esi
0x18008069a  jnz     loc_180080745
0x1800806a0  test    r14, r14
0x1800806a3  jz      loc_1800803A8
0x1800806a9  mov     rcx, r14; hMem
0x1800806ac  call    cs:__imp_LocalFree
0x1800806b2  jmp     loc_1800803A8
0x1800806b7  cmp     rsi, [rbp+57h+var_80]
0x1800806bb  jnz     short loc_1800806D6
0x1800806bd  lea     rdx, [rsi+1]
0x1800806c1  lea     rcx, [rbp+57h+var_98]
0x1800806c5  call    ?_EnsureCapacity@?$CTSimpleArray@PEAVElement@DirectUI@@$0PPPPPPPO@V?$CTPolicyLocalMem@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardCompareHelper@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardMergeHelper@PEAVElement@DirectUI@@@@@@QEAAJ_K0@Z; CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800806ca  test    eax, eax
0x1800806cc  mov     r14, [rbp+57h+var_98]
0x1800806d0  mov     rsi, [rbp+57h+var_90]
0x1800806d4  js      short loc_1800806ED
0x1800806d6  inc     rsi
0x1800806d9  lea     rax, [rsi-1]
0x1800806dd  lea     rax, [r14+rax*8]
0x1800806e1  test    rax, rax
0x1800806e4  mov     [rbp+57h+var_90], rsi
0x1800806e8  jz      short loc_1800806ED
0x1800806ea  mov     [rax], r15
0x1800806ed  mov     [rbp+57h+arg_18], 0
0x1800806f4  jmp     loc_18008063F
0x1800806f9  mov     rsi, [rbp+57h+var_90]
0x1800806fd  mov     r14, [rbp+57h+var_98]
0x180080701  jmp     loc_18008065C
0x180080706  cmp     rsi, [rbp+57h+var_80]
0x18008070a  jnz     short loc_180080725
0x18008070c  lea     rdx, [rsi+1]
0x180080710  lea     rcx, [rbp+57h+var_98]
0x180080714  call    ?_EnsureCapacity@?$CTSimpleArray@PEAVElement@DirectUI@@$0PPPPPPPO@V?$CTPolicyLocalMem@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardCompareHelper@PEAVElement@DirectUI@@@@V?$CSimpleArrayStandardMergeHelper@PEAVElement@DirectUI@@@@@@QEAAJ_K0@Z; CTSimpleArray<DirectUI::Element *,4294967294,CTPolicyLocalMem<DirectUI::Element *>,CSimpleArrayStandardCompareHelper<DirectUI::Element *>,CSimpleArrayStandardMergeHelper<DirectUI::Element *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180080719  test    eax, eax
0x18008071b  js      short loc_1800806F9
0x18008071d  mov     rsi, [rbp+57h+var_90]
0x180080721  mov     r14, [rbp+57h+var_98]
0x180080725  inc     rsi
0x180080728  mov     [rbp+57h+var_90], rsi
0x18008072c  lea     rax, [rsi-1]
0x180080730  lea     rax, [r14+rax*8]
0x180080734  test    rax, rax
0x180080737  jz      loc_18008065C
0x18008073d  mov     [rax], r15
0x180080740  jmp     loc_18008065C
0x180080745  mov     rax, [r15]
0x180080748  mov     r8d, esi
0x18008074b  mov     rdx, r14
0x18008074e  mov     rcx, r15
0x180080751  mov     rax, [rax+90h]
0x180080758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008075d  test    eax, eax
0x18008075f  js      loc_1800806A0
0x180080765  xor     ebx, ebx
0x180080767  mov     rcx, [r14+rbx*8]
0x18008076b  call    ??$element_cast@VUIItem@@@@YAPEAVUIItem@@PEAVElement@DirectUI@@@Z; element_cast<UIItem>(DirectUI::Element *)
0x180080770  mov     rdi, rax
0x180080773  test    rax, rax
0x180080776  jz      short loc_18008078F
0x180080778  mov     rcx, rax; this
0x18008077b  call    ?GetModel@UIItem@@QEAA_NXZ; UIItem::GetModel(void)
0x180080780  test    al, al
0x180080782  jnz     short loc_18008078F
0x180080784  mov     rdx, rdi; struct UIItem *
0x180080787  mov     rcx, r13; this
0x18008078a  call    ?_UnrealizeItem@UICollection@@IEAAXPEAVUIItem@@@Z; UICollection::_UnrealizeItem(UIItem *)
0x18008078f  mov     dl, 1
0x180080791  mov     rcx, [r14+rbx*8]
0x180080795  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18008079b  inc     ebx
0x18008079d  cmp     ebx, esi
0x18008079f  jb      short loc_180080767
0x1800807a1  jmp     loc_1800806A0
0x1800807a6  mov     r15, rcx
0x1800807a9  jmp     loc_180080431
0x1800807ae  mov     rax, rcx
0x1800807b1  jmp     loc_18008047F
0x1800807b6  mov     r9, rbx; unsigned __int16 *
0x1800807b9  mov     r8, [rbp+57h+var_78]; struct IItem *
0x1800807bd  mov     rdx, r15; struct UIItem *
0x1800807c0  call    ?_RecreateUIItem@UICollection@@IEAAJPEAVUIItem@@PEAUIItem@@PEBG@Z; UICollection::_RecreateUIItem(UIItem *,IItem *,ushort const *)
0x1800807c5  test    eax, eax
0x1800807c7  jns     loc_18008063F
0x1800807cd  jmp     loc_1800806B7
0x1800807d2  mov     rbx, [rbp+57h+var_48]
0x1800807d6  mov     rcx, [rbp+57h+var_40]
0x1800807da  mov     edi, [rbp+57h+arg_10]
  ... truncated ...
```
