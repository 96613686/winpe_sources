# UICollection::_CreateAndInsertItems(ItemLayout *,uint,uint,uint)

- ea: `0x18007f8e8`
- end: `0x18008035a`
- name: `?_CreateAndInsertItems@UICollection@@IEAAJPEAVItemLayout@@III@Z`
- size: `2674`
- prototype: `__int64 __usercall@<rax>(UICollection *__hidden this@<rcx>, struct ItemLayout *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f1fc`
- `0x18007f640`

## callees

- `0x180010fc8`
- `0x1800173a0`
- `0x18001a1e0`
- `0x18001b7dc`
- `0x18001b8d0`
- `0x18001c560`
- `0x18001e344`
- `0x1800266fc`
- `0x1800340a0`
- `0x180055e64`
- `0x18007b380`
- `0x18007f8e8`
- `0x1800899cc`
- `0x1800a611c`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180192040`
- `0x180210010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18007fcdb`
- `SHLWAPI!StrChrW` at `0x18007fcdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd2e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180080220`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180080220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007febb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800801e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008024a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008025f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007febb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800801e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008024a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008025f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007fb89`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007fb89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008003c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008004a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008003c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008004a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f964`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f9a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f964`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f9a6`
- `KERNEL32!AddAtomW` at `0x18007fe6b`
- `KERNEL32!AddAtomW` at `0x18007fe6b`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800801f3`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800801f3`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18008018e`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18008018e`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18007fbbd`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18007fbbd`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fc17`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fc30`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fcba`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007ff13`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18008029e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800802b5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180080306`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fc17`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fc30`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007fcba`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18007ff13`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18008029e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800802b5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180080306`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fae8`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fb25`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fae8`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fb25`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007fadf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007fb42`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007fadf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007fb42`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18007fac8`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18007fac8`
- `DUI70!?GetStringNull@Value@DirectUI@@SAPEAV12@XZ` at `0x18007fa95`
- `DUI70!?GetStringNull@Value@DirectUI@@SAPEAV12@XZ` at `0x18007fa95`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007fab8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007fab8`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fc48`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007ffd5`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007fc48`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007ffd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall UICollection::_CreateAndInsertItems(
        UICollection *this,
        struct ItemLayout *a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  UICollection *v5; // rbx
  unsigned __int64 v6; // rdi
  char *v7; // r14
  HRESULT ValueFromMap; // esi
  char *v9; // r13
  __int64 v10; // rax
  _QWORD *v11; // r12
  char *v12; // r15
  DirectUI::Element *v13; // rbx
  unsigned int v14; // edx
  unsigned __int16 *v15; // r14
  __int64 StringNull; // rsi
  DirectUI::Value *Value; // rdi
  const WCHAR *String; // r15
  struct DirectUI::Element *Parent; // rax
  struct DirectUI::IClassInfo *v20; // rdi
  __int64 v21; // rax
  DirectUI::Value *v22; // rcx
  WCHAR *v23; // r15
  PWSTR v24; // rbx
  DirectUI::DUIXmlParser **v25; // rax
  DirectUI::Element *v26; // rcx
  __int64 v27; // rax
  DirectUI::Element *v28; // rcx
  struct DirectUI::Element *v29; // rax
  struct DirectUI::Element *v30; // rdi
  __int64 v31; // rax
  DirectUI::Element *v32; // rcx
  PWSTR v33; // rax
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rdx
  unsigned __int16 *v37; // rax
  __int64 v38; // rcx
  WCHAR v39; // r8
  __int64 v40; // r9
  unsigned __int16 *v41; // rcx
  __int64 v42; // rbx
  bool v43; // cf
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // rcx
  PWSTR v45; // rbx
  ATOM v46; // ax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  unsigned int v50; // ebx
  char *v51; // r12
  DirectUI::Element *v52; // rcx
  struct DirectUI::Element *v53; // rbx
  unsigned int v54; // r14d
  DirectUI::Element *v55; // rsi
  __int64 v56; // rcx
  struct DirectUI::Element *TopLevel; // rax
  UIItemsView *v58; // rbx
  __int64 v59; // rax
  unsigned int j; // ebx
  struct ItemLayout *ItemLayout; // rax
  unsigned __int64 v63; // rbx
  unsigned __int64 i; // rax
  __int64 v65; // rbx
  WCHAR *v66; // rbx
  WCHAR *v67; // rdi
  int v68; // eax
  DirectUI::Element *v69; // rcx
  DirectUI::Element *v70; // rcx
  int Error; // eax
  DirectUI::Element *v72; // rcx
  WCHAR **v73; // [rsp+20h] [rbp-E0h]
  PWSTR v74; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v76; // [rsp+40h] [rbp-C0h]
  unsigned int v77; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v78; // [rsp+50h] [rbp-B0h] BYREF
  int v79; // [rsp+58h] [rbp-A8h]
  WCHAR *v80; // [rsp+60h] [rbp-A0h] BYREF
  DirectUI::Element *v81; // [rsp+68h] [rbp-98h]
  char *v82; // [rsp+70h] [rbp-90h]
  int v83; // [rsp+78h] [rbp-88h]
  int v84; // [rsp+7Ch] [rbp-84h]
  __int64 v85; // [rsp+80h] [rbp-80h] BYREF
  struct DirectUI::Element *v86; // [rsp+88h] [rbp-78h]
  __int64 *v87; // [rsp+90h] [rbp-70h]
  PWSTR *v88; // [rsp+98h] [rbp-68h]
  _QWORD *v89; // [rsp+A0h] [rbp-60h]
  PWSTR v90; // [rsp+A8h] [rbp-58h]
  PROPVARIANT propvar[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+C0h] [rbp-40h]
  WCHAR *v93; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v94; // [rsp+D0h] [rbp-30h]
  __int64 v95; // [rsp+D8h] [rbp-28h]
  DirectUI::Value *v96; // [rsp+E0h] [rbp-20h]
  PCWSTR pszName[3]; // [rsp+E8h] [rbp-18h] BYREF
  PROPERTYKEY ppropkey; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  unsigned int v100; // [rsp+190h] [rbp+90h]

  v83 = a4;
  v77 = a3;
  v86 = a2;
  v5 = this;
  v81 = this;
  *((_DWORD *)this + 70) = 1;
  v6 = a5 - a4;
  v100 = v6;
  v87 = 0;
  if ( !is_mul_ok((unsigned int)v6, 8u) )
  {
    ValueFromMap = -2147024362;
    goto LABEL_86;
  }
  v7 = (char *)LocalAlloc(0x40u, 8LL * (unsigned int)v6);
  v82 = v7;
  ValueFromMap = v7 == 0 ? 0x8007000E : 0;
  if ( v7 )
  {
    v87 = 0;
    if ( is_mul_ok((unsigned int)v6, 8u) )
    {
      v9 = (char *)LocalAlloc(0x40u, 8LL * (unsigned int)v6);
      ValueFromMap = v9 == 0 ? 0x8007000E : 0;
      if ( v9 )
      {
        memset_0(v7, 0, 8 * v6);
        memset_0(v9, 0, 8 * v6);
        v10 = 0;
        v79 = 0;
        v11 = v7;
        v89 = v7;
        v12 = v9;
        v76 = v9;
        while ( 1 )
        {
          if ( (unsigned int)v10 >= (unsigned int)v6 )
          {
            v53 = v86;
            ValueFromMap = (*(__int64 (__fastcall **)(struct DirectUI::Element *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v86 + 136LL))(
                             v86,
                             v11,
                             (unsigned int)v6,
                             v77);
            v77 = ValueFromMap;
            if ( ValueFromMap < 0 )
            {
              v63 = 0;
              for ( i = (unsigned int)v6; v63 < i; ++v63 )
              {
                v70 = *(DirectUI::Element **)&v7[8 * v63];
                if ( v70 )
                {
                  DirectUI::Element::Destroy(v70, 1);
                  i = (unsigned int)v6;
                }
              }
            }
            else
            {
              v54 = 0;
              if ( (_DWORD)v6 )
              {
                v76 = v12;
                v55 = v81;
                do
                {
                  v56 = v11[v54];
                  if ( *((_QWORD *)v55 + 37) )
                  {
                    v6 = element_cast<UIGroupItem>(v56, 0);
                    v65 = *(_QWORD *)(*(_QWORD *)(element_cast<ItemRowLayout>(v53) + 216) + 8LL * *(int *)(v6 + 200));
                    (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v65 + 168LL))(v65, v6);
                    ATL::CComPtr<IShellSearchTarget>::operator=(v6 + 304, v65);
                    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v11[v54] + 432LL))(
                      v11[v54],
                      *(_QWORD *)&v9[8 * v54]);
                    UIGroupItem::SynchronizeWithIVirtualUIGroupItem((UIGroupItem *)v6);
                    LODWORD(v6) = v100;
                    v53 = v86;
                  }
                  else
                  {
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 432LL))(v56, *(_QWORD *)&v9[8 * v54]);
                  }
                  ++v54;
                }
                while ( v54 < (unsigned int)v6 );
                ValueFromMap = v77;
                v12 = v76;
              }
              (*(void (__fastcall **)(struct DirectUI::Element *, _QWORD *, _QWORD))(*(_QWORD *)v53 + 512LL))(
                v53,
                v11,
                (unsigned int)v6);
              TopLevel = DirectUI::Element::GetTopLevel(v81);
              v58 = TopLevel;
              if ( TopLevel )
              {
                v59 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
                if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v59 + 80LL))(
                       v59,
                       UIItemsView::Class) )
                {
                  UIItemsView::OnItemsInserted(v58);
                }
              }
            }
            for ( j = 0; j < (unsigned int)v6; ++j )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v9[8 * j] + 16LL))(*(_QWORD *)&v9[8 * j]);
LABEL_84:
            LocalFree(v12);
            v5 = v81;
LABEL_85:
            LocalFree(v11);
            goto LABEL_86;
          }
          v84 = v10 + v83;
          v88 = (PWSTR *)&v7[8 * v10];
          *v88 = 0;
          v87 = (__int64 *)&v9[8 * v10];
          *v87 = 0;
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v80);
          v13 = v81;
          v73 = &v80;
          ValueFromMap = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *))(**((_QWORD **)v81 + 30) + 56LL))(
                           *((_QWORD *)v81 + 30),
                           *((unsigned int *)v81 + 68),
                           v14,
                           &GUID_aecc1438_059c_44ad_a2b4_e87f4d3a4987);
          if ( ValueFromMap >= 0 )
            break;
LABEL_65:
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v80);
          v10 = (unsigned int)++v79;
          v49 = 0;
          if ( ValueFromMap < 0 )
          {
            v50 = 0;
            if ( (_DWORD)v6 )
            {
              v51 = v82;
              do
              {
                v52 = *(DirectUI::Element **)&v51[8 * v50];
                if ( v52 )
                {
                  *(_QWORD *)&v51[8 * v50] = 0;
                  DirectUI::Element::Destroy(v52, 1);
                }
                SafeRelease<ILinguisticAlternativeGenerator>(&v12[8 * v50++], v48, v49);
                v49 = 0;
              }
              while ( v50 < v100 );
              v11 = v89;
            }
            goto LABEL_84;
          }
        }
        v15 = 0;
        v78 = 0;
        CoTaskMemFree(0);
        ppszOut = v80;
        StringNull = DirectUI::Value::GetStringNull();
        while ( 1 )
        {
          if ( !v13 )
          {
            v22 = (DirectUI::Value *)StringNull;
            ValueFromMap = -2147467259;
            goto LABEL_17;
          }
          Value = DirectUI::Element::GetValue(v13, UICollection::UIItemCreationPropMapProp, 2, 0);
          v96 = Value;
          String = DirectUI::Value::GetString(Value);
          if ( String )
            break;
          DirectUI::Value::Release(Value);
          Parent = DirectUI::Element::GetParent(v13);
          v20 = UICollection::Class;
          while ( 1 )
          {
            v13 = Parent;
            if ( !Parent )
              break;
            v21 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Parent + 280LL))(Parent);
            if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v21 + 80LL))(
                   v21,
                   v20) )
            {
              break;
            }
            Parent = DirectUI::Element::GetParent(v13);
          }
        }
        v15 = 0;
        v78 = 0;
        v33 = StrChrW(String, 0x3Au);
        v90 = v33;
        if ( v33 )
        {
          v66 = 0;
          v93 = 0;
          v94 = 0;
          v95 = 0;
          memset(pszName, 0, sizeof(pszName));
          ValueFromMap = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                           pszName,
                           String,
                           v33 - String);
          v67 = (WCHAR *)pszName[0];
          if ( ValueFromMap >= 0 )
          {
            memset(&ppropkey, 0, sizeof(ppropkey));
            ValueFromMap = PSGetPropertyKeyFromName(pszName[0], &ppropkey);
            if ( ValueFromMap >= 0 )
            {
              *(_OWORD *)propvar = 0;
              v92 = 0;
              LODWORD(v74) = 0;
              v73 = &v74;
              v68 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppszOut + 24LL))(
                      ppszOut,
                      0,
                      &ppropkey,
                      propvar);
              if ( v68 < 0 )
              {
                if ( v68 == -2147483638 )
                {
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v93,
                    L"~",
                    -1);
                  v66 = v93;
                }
              }
              else
              {
                ppszOut = 0;
                CoTaskMemFree(0);
                PropVariantToStringAlloc(propvar, &ppszOut);
                v66 = ppszOut;
                ppszOut = 0;
                v93 = v66;
                v95 = -1;
                v94 = -1;
                CoTaskMemFree(0);
              }
              PropVariantClear(propvar);
              ValueFromMap = GetValueFromMap(v90 + 1, v66, &v78);
              v15 = v78;
            }
          }
          if ( v67 )
            CoTaskMemFree(v67);
          if ( v66 )
            CoTaskMemFree(v66);
          goto LABEL_56;
        }
        v34 = -1;
        do
          ++v34;
        while ( String[v34] );
        v78 = 0;
        v35 = v34 + 1;
        if ( v34 + 1 >= v34 && (v78 = 0, v90 = 0, is_mul_ok(v35, 2u)) )
        {
          v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v35);
          v78 = v15;
          ValueFromMap = v15 == 0 ? 0x8007000E : 0;
          if ( v15 )
          {
            if ( v35 > 0x7FFFFFFF )
              goto LABEL_115;
            if ( v34 < 0x7FFFFFFF )
            {
              v36 = v34 + 1;
              v37 = v15;
              v38 = 0;
              do
              {
                if ( !v34 )
                  break;
                v39 = *String;
                if ( !*String )
                  break;
                ++String;
                *v37++ = v39;
                --v34;
                ++v38;
                --v36;
              }
              while ( v36 );
              v40 = v38 - 1;
              if ( v36 )
                v40 = v38;
              v41 = v37 - 1;
              if ( v36 )
                v41 = v37;
              *v41 = 0;
              if ( v36 )
              {
                v43 = v35 == v40;
                v42 = v35 - v40;
                if ( !v43 && v42 != 1 && (unsigned __int64)(2 * v42) > 2 )
                  memset_0(&v15[v40 + 1], 0, 2 * v42 - 2);
              }
              goto LABEL_56;
            }
            if ( v34 != -1 )
LABEL_115:
              *v15 = 0;
          }
        }
        else
        {
          ValueFromMap = -2147024362;
        }
LABEL_56:
        v22 = v96;
LABEL_17:
        DirectUI::Value::Release(v22);
        if ( ValueFromMap < 0 )
          goto LABEL_34;
        v23 = v80;
        *v88 = 0;
        v74 = 0;
        propvar[0] = &v74;
        v24 = 0;
        propvar[1] = 0;
        LOBYTE(v92) = 1;
        ppszOut = 0;
        if ( dwTlsIndex != -1 && (v25 = (DirectUI::DUIXmlParser **)TlsGetValue(dwTlsIndex)) != 0 && *v25 )
        {
          ValueFromMap = DirectUI::DUIXmlParser::CreateElement(
                           *v25,
                           v15,
                           0,
                           v86,
                           0,
                           (struct DirectUI::Element **)&ppszOut);
          if ( ValueFromMap < 0 )
            goto LABEL_26;
          v26 = (DirectUI::Element *)ppszOut;
          v24 = ppszOut;
          ValueFromMap = 0;
          if ( ppszOut )
          {
            v27 = (*(__int64 (__fastcall **)(PWSTR))(*(_QWORD *)ppszOut + 280LL))(ppszOut);
            if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v27 + 80LL))(
                   v27,
                   UIItem::Class) )
            {
              goto LABEL_26;
            }
            v26 = (DirectUI::Element *)ppszOut;
          }
          v24 = 0;
          propvar[1] = 0;
          ValueFromMap = -2147467259;
          DirectUI::Element::Destroy(v26, 1);
        }
        else
        {
          ValueFromMap = -2147467259;
        }
LABEL_26:
        v28 = (DirectUI::Element *)v74;
        v74 = v24;
        if ( v28 )
        {
          DirectUI::Element::Destroy(v28, 1);
          v24 = v74;
        }
        if ( ValueFromMap < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4AF,
            (unsigned int)"shell\\explorerframe\\itemsview\\uicollection.cpp",
            (const char *)(unsigned int)ValueFromMap,
            (int)v73);
          v69 = (DirectUI::Element *)v74;
          v74 = 0;
          if ( v69 )
            DirectUI::Element::Destroy(v69, 1);
          goto LABEL_34;
        }
        v29 = DirectUI::Element::GetTopLevel(v81);
        v30 = v29;
        if ( v29
          && (v31 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v29 + 280LL))(v29),
              (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v31 + 80LL))(
                v31,
                UIItemsView::Class)) )
        {
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v85);
          ValueFromMap = -2147467259;
          v44 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v30 + 41);
          if ( v44 )
            ValueFromMap = (**v44)(v44, &GUID_204e242d_3780_4a3e_bcd2_a8b39537f66c, &v85);
          if ( ValueFromMap >= 0 )
            *((_DWORD *)v24 + 60) = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v85 + 24LL))(v85, v23);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v85);
          if ( ValueFromMap >= 0 )
          {
            *((_DWORD *)v74 + 50) = v84;
            v45 = v74;
            v46 = AddAtomW(v15);
            v45[104] = v46;
            if ( v46 || (Error = ResultFromKnownLastError(), ValueFromMap = Error, Error >= 0) )
            {
              v89 = v11;
              v12 = v76;
              *v88 = v74;
              v47 = ATL::CComPtrBase<IImageList>::Detach(&v80);
              *v87 = v47;
              ValueFromMap = 0;
              goto LABEL_64;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4B4,
              (unsigned int)"shell\\explorerframe\\itemsview\\uicollection.cpp",
              (const char *)(unsigned int)Error,
              (int)v73);
            v72 = (DirectUI::Element *)v74;
            v74 = 0;
            if ( v72 )
              DirectUI::Element::Destroy(v72, 1);
LABEL_34:
            v12 = v76;
LABEL_64:
            CoTaskMemFree(v15);
            LODWORD(v6) = v100;
            v7 = v82;
            goto LABEL_65;
          }
        }
        else
        {
          ValueFromMap = -2147467259;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B1,
          (unsigned int)"shell\\explorerframe\\itemsview\\uicollection.cpp",
          (const char *)(unsigned int)ValueFromMap,
          (int)v73);
        v32 = (DirectUI::Element *)v74;
        v74 = 0;
        if ( v32 )
          DirectUI::Element::Destroy(v32, 1);
        goto LABEL_34;
      }
    }
    else
    {
      ValueFromMap = -2147024362;
    }
    v11 = v7;
    goto LABEL_85;
  }
LABEL_86:
  *((_DWORD *)v5 + 70) = 0;
  ItemLayout = UICollection::GetItemLayout(v5);
  (*(void (__fastcall **)(struct ItemLayout *, _QWORD, __int64))(*(_QWORD *)ItemLayout + 376LL))(ItemLayout, 0, 1);
  return (unsigned int)ValueFromMap;
}

```

## disassembly

```asm
0x18007f8e8  push    rbp
0x18007f8ea  push    rbx
0x18007f8eb  push    rsi
0x18007f8ec  push    rdi
0x18007f8ed  push    r12
0x18007f8ef  push    r13
0x18007f8f1  push    r14
0x18007f8f3  push    r15
0x18007f8f5  lea     rbp, [rsp-28h]
0x18007f8fa  sub     rsp, 128h
0x18007f901  mov     rax, cs:__security_cookie
0x18007f908  xor     rax, rsp
0x18007f90b  mov     [rbp+60h+var_48], rax
0x18007f90f  mov     [rsp+160h+var_E8], r9d
0x18007f914  mov     [rsp+160h+var_118], r8d
0x18007f919  mov     [rbp+60h+var_D8], rdx
0x18007f91d  mov     rbx, rcx
0x18007f920  mov     [rsp+160h+var_F8], rcx
0x18007f925  mov     dword ptr [rcx+118h], 1
0x18007f92f  mov     edi, [rbp+60h+arg_20]
0x18007f935  sub     edi, r9d
0x18007f938  mov     [rbp+60h+arg_20], edi
0x18007f93e  xor     r12d, r12d
0x18007f941  mov     [rbp+60h+var_D0], r12
0x18007f945  mov     r15d, edi
0x18007f948  lea     eax, [r12+8]
0x18007f94d  mul     r15
0x18007f950  test    rdx, rdx
0x18007f953  jnz     loc_18008009F
0x18007f959  mov     rdx, rax; uBytes
0x18007f95c  lea     r13d, [r12+40h]
0x18007f961  mov     ecx, r13d; uFlags
0x18007f964  call    cs:__imp_LocalAlloc
0x18007f96a  mov     r14, rax
0x18007f96d  mov     [rsp+160h+var_F0], rax
0x18007f972  mov     rcx, rax
0x18007f975  neg     rcx
0x18007f978  sbb     esi, esi
0x18007f97a  not     esi
0x18007f97c  and     esi, 8007000Eh
0x18007f982  test    rax, rax
0x18007f985  jz      loc_180080053
0x18007f98b  mov     [rbp+60h+var_D0], r12
0x18007f98f  lea     eax, [r12+8]
0x18007f994  mul     r15
0x18007f997  test    rdx, rdx
0x18007f99a  jnz     loc_1800800A6
0x18007f9a0  mov     rdx, rax; uBytes
0x18007f9a3  mov     ecx, r13d; uFlags
0x18007f9a6  call    cs:__imp_LocalAlloc
0x18007f9ac  mov     r13, rax
0x18007f9af  mov     rcx, rax
0x18007f9b2  neg     rcx
0x18007f9b5  sbb     esi, esi
0x18007f9b7  not     esi
0x18007f9b9  and     esi, 8007000Eh
0x18007f9bf  test    rax, rax
0x18007f9c2  jz      loc_1800800AB
0x18007f9c8  lea     rbx, ds:0[rdi*8]
0x18007f9d0  mov     r8, rbx; Size
0x18007f9d3  xor     edx, edx; Val
0x18007f9d5  mov     rcx, r14; void *
0x18007f9d8  call    memset_0
0x18007f9dd  mov     r8, rbx; Size
0x18007f9e0  xor     edx, edx; Val
0x18007f9e2  mov     rcx, r13; void *
0x18007f9e5  call    memset_0
0x18007f9ea  mov     eax, r12d
0x18007f9ed  mov     [rsp+160h+var_108], eax
0x18007f9f1  mov     r12, r14
0x18007f9f4  mov     [rbp+60h+var_C0], r14
0x18007f9f8  mov     r15, r13
0x18007f9fb  mov     [rsp+160h+var_120], r13
0x18007fa00  xor     r8d, r8d
0x18007fa03  cmp     eax, edi
0x18007fa05  jnb     loc_18007FF38
0x18007fa0b  mov     edx, [rsp+160h+var_E8]
0x18007fa0f  add     edx, eax
0x18007fa11  mov     [rsp+160h+var_E4], edx
0x18007fa15  lea     rcx, [r14+rax*8]
0x18007fa19  mov     [rbp+60h+var_C8], rcx
0x18007fa1d  mov     [rcx], r8
0x18007fa20  lea     rax, ds:0[rax*8]
0x18007fa28  add     rax, r13
0x18007fa2b  mov     [rbp+60h+var_D0], rax
0x18007fa2f  mov     [rax], r8
0x18007fa32  lea     rcx, [rsp+160h+var_100]; void *
0x18007fa37  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18007fa3c  nop
0x18007fa3d  mov     rbx, [rsp+160h+var_F8]
0x18007fa42  mov     rcx, [rbx+0F0h]
0x18007fa49  mov     rax, [rcx]
0x18007fa4c  lea     r8, [rsp+160h+var_100]
0x18007fa51  mov     qword ptr [rsp+160h+var_140], r8
0x18007fa56  lea     r9, _GUID_aecc1438_059c_44ad_a2b4_e87f4d3a4987
0x18007fa5d  mov     r8d, edx
0x18007fa60  mov     edx, [rbx+110h]
0x18007fa66  mov     rax, [rax+38h]
0x18007fa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fa6f  mov     esi, eax
0x18007fa71  test    eax, eax
0x18007fa73  js      loc_18007FECC
0x18007fa79  xor     edi, edi
0x18007fa7b  mov     r14d, edi
0x18007fa7e  mov     [rsp+160h+var_110], rdi
0x18007fa83  xor     ecx, ecx; pv
0x18007fa85  call    cs:__imp_CoTaskMemFree
0x18007fa8b  mov     rax, [rsp+160h+var_100]
0x18007fa90  mov     [rsp+160h+ppszOut], rax
0x18007fa95  call    cs:__imp_?GetStringNull@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetStringNull(void)
0x18007fa9b  mov     rsi, rax
0x18007fa9e  test    rbx, rbx
0x18007faa1  jz      loc_18007FB3A
0x18007faa7  xor     r9d, r9d
0x18007faaa  lea     r8d, [r9+2]
0x18007faae  lea     rdx, ?UIItemCreationPropMapProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::UIItemCreationPropMapProp(void)
0x18007fab5  mov     rcx, rbx
0x18007fab8  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007fabe  mov     rdi, rax
0x18007fac1  mov     [rbp+60h+var_80], rax
0x18007fac5  mov     rcx, rax
0x18007fac8  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18007face  mov     r15, rax
0x18007fad1  xor     eax, eax
0x18007fad3  test    r15, r15
0x18007fad6  jnz     loc_18007FCCB
0x18007fadc  mov     rcx, rdi
0x18007fadf  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007fae5  mov     rcx, rbx
0x18007fae8  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18007faee  mov     rdi, cs:?Class@UICollection@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UICollection::Class
0x18007faf5  jmp     short loc_18007FB2B
0x18007faf7  mov     rax, [rbx]
0x18007fafa  mov     rcx, rbx
0x18007fafd  mov     rax, [rax+118h]
0x18007fb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fb09  mov     r8, rax
0x18007fb0c  mov     rcx, [rax]
0x18007fb0f  mov     rax, [rcx+50h]
0x18007fb13  mov     rdx, rdi
0x18007fb16  mov     rcx, r8
0x18007fb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fb1e  test    al, al
0x18007fb20  jnz     short loc_18007FB33
0x18007fb22  mov     rcx, rbx
0x18007fb25  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18007fb2b  test    rax, rax
0x18007fb2e  mov     rbx, rax
0x18007fb31  jnz     short loc_18007FAF7
0x18007fb33  xor     edi, edi
0x18007fb35  jmp     loc_18007FA9E
0x18007fb3a  mov     rcx, rsi
0x18007fb3d  mov     esi, 80004005h
0x18007fb42  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007fb48  test    esi, esi
0x18007fb4a  js      loc_18007FCC1
0x18007fb50  mov     r15, [rsp+160h+var_100]
0x18007fb55  mov     rax, [rbp+60h+var_C8]
0x18007fb59  mov     [rax], rdi
0x18007fb5c  mov     [rsp+160h+var_130], rdi
0x18007fb61  lea     rax, [rsp+160h+var_130]
0x18007fb66  mov     [rbp+60h+propvar], rax
0x18007fb6a  mov     rbx, rdi
0x18007fb6d  mov     [rbp+60h+propvar+8], rbx
0x18007fb71  mov     byte ptr [rbp+60h+var_A0], 1
0x18007fb75  mov     [rsp+160h+ppszOut], rdi
0x18007fb7a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18007fb80  cmp     ecx, 0FFFFFFFFh
0x18007fb83  jz      loc_18008026A
0x18007fb89  call    cs:__imp_TlsGetValue
0x18007fb8f  test    rax, rax
0x18007fb92  jz      loc_18008026A
0x18007fb98  mov     rcx, [rax]
0x18007fb9b  test    rcx, rcx
0x18007fb9e  jz      loc_18008026A
0x18007fba4  lea     rax, [rsp+160h+ppszOut]
0x18007fba9  mov     [rsp+160h+var_138], rax
0x18007fbae  mov     qword ptr [rsp+160h+var_140], rdi; int
0x18007fbb3  mov     r9, [rbp+60h+var_D8]
0x18007fbb7  xor     r8d, r8d
0x18007fbba  mov     rdx, r14
0x18007fbbd  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18007fbc3  mov     esi, eax
0x18007fbc5  test    eax, eax
0x18007fbc7  js      short loc_18007FC1F
0x18007fbc9  mov     rcx, [rsp+160h+ppszOut]
0x18007fbce  mov     rbx, rcx
0x18007fbd1  xor     esi, esi
0x18007fbd3  test    rcx, rcx
0x18007fbd6  jz      short loc_18007FC09
0x18007fbd8  mov     rax, [rcx]
0x18007fbdb  mov     rax, [rax+118h]
0x18007fbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fbe7  mov     r8, rax
0x18007fbea  mov     rcx, [rax]
0x18007fbed  mov     rax, [rcx+50h]
0x18007fbf1  mov     rdx, cs:?Class@UIItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItem::Class
0x18007fbf8  mov     rcx, r8
0x18007fbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc00  test    al, al
0x18007fc02  jnz     short loc_18007FC1D
0x18007fc04  mov     rcx, [rsp+160h+ppszOut]
0x18007fc09  mov     rbx, rdi
0x18007fc0c  mov     [rbp+60h+propvar+8], rbx
0x18007fc10  mov     esi, 80004005h
0x18007fc15  mov     dl, 1
0x18007fc17  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18007fc1d  xor     edi, edi
0x18007fc1f  mov     rcx, [rsp+160h+var_130]
0x18007fc24  mov     [rsp+160h+var_130], rbx
0x18007fc29  test    rcx, rcx
0x18007fc2c  jz      short loc_18007FC3B
0x18007fc2e  mov     dl, 1
0x18007fc30  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18007fc36  mov     rbx, [rsp+160h+var_130]
0x18007fc3b  test    esi, esi
0x18007fc3d  js      loc_180080274
0x18007fc43  mov     rcx, [rsp+160h+var_F8]
0x18007fc48  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x18007fc4e  mov     rdi, rax
0x18007fc51  test    rax, rax
0x18007fc54  jz      short loc_18007FC89
0x18007fc56  mov     rcx, [rax]
0x18007fc59  mov     rax, [rcx+118h]
0x18007fc60  mov     rcx, rdi
0x18007fc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc68  mov     r8, rax
0x18007fc6b  mov     rcx, [rax]
0x18007fc6e  mov     rax, [rcx+50h]
0x18007fc72  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x18007fc79  mov     rcx, r8
0x18007fc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc81  test    al, al
0x18007fc83  jnz     loc_18007FDF1
0x18007fc89  mov     esi, 80004005h
0x18007fc8e  xor     edi, edi
0x18007fc90  mov     rcx, [rbp+68h]; this
0x18007fc94  mov     r9d, esi; char *
0x18007fc97  lea     r8, aShellExplorerf_13; "shell\\explorerframe\\itemsview\\uicoll"...
0x18007fc9e  mov     edx, 4B1h; void *
0x18007fca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fca8  nop
0x18007fca9  mov     rcx, [rsp+160h+var_130]
0x18007fcae  mov     [rsp+160h+var_130], rdi
0x18007fcb3  test    rcx, rcx
0x18007fcb6  jz      short loc_18007FCC1
0x18007fcb8  mov     dl, 1
0x18007fcba  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18007fcc0  nop
0x18007fcc1  mov     r15, [rsp+160h+var_120]
0x18007fcc6  jmp     loc_18007FEB8
0x18007fccb  mov     r14, rax
0x18007fcce  mov     [rsp+160h+var_110], rax
0x18007fcd3  mov     edx, 3Ah ; ':'; wMatch
0x18007fcd8  mov     rcx, r15; pszStart
0x18007fcdb  call    cs:__imp_StrChrW
0x18007fce1  mov     [rbp+60h+var_B8], rax
0x18007fce5  xor     r10d, r10d
0x18007fce8  test    rax, rax
0x18007fceb  jnz     loc_18008013A
0x18007fcf1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007fcf5  inc     rdi
0x18007fcf8  cmp     [r15+rdi*2], r10w
0x18007fcfd  jnz     short loc_18007FCF5
0x18007fcff  mov     [rsp+160h+var_110], r10
0x18007fd04  lea     rbx, [rdi+1]
0x18007fd08  cmp     rbx, rdi
0x18007fd0b  jb      loc_18007FDE1
0x18007fd11  mov     [rsp+160h+var_110], r10
0x18007fd16  mov     [rbp+60h+var_B8], r10
0x18007fd1a  mov     eax, 2
0x18007fd1f  mul     rbx
0x18007fd22  test    rdx, rdx
0x18007fd25  jnz     loc_18007FDE1
0x18007fd2b  mov     rcx, rax; cb
0x18007fd2e  call    cs:__imp_CoTaskMemAlloc
0x18007fd34  mov     r14, rax
0x18007fd37  mov     [rsp+160h+var_110], rax
0x18007fd3c  neg     rax
0x18007fd3f  sbb     esi, esi
0x18007fd41  not     esi
0x18007fd43  and     esi, 8007000Eh
0x18007fd49  xor     r10d, r10d
0x18007fd4c  test    r14, r14
0x18007fd4f  jz      loc_18007FDE6
0x18007fd55  mov     eax, 7FFFFFFFh
0x18007fd5a  cmp     rbx, rax
0x18007fd5d  ja      loc_180080328
0x18007fd63  cmp     rdi, rax
0x18007fd66  jnb     loc_18008031F
0x18007fd6c  test    rbx, rbx
0x18007fd6f  jz      short loc_18007FDE6
0x18007fd71  mov     rdx, rbx
0x18007fd74  mov     rax, r14
0x18007fd77  mov     ecx, r10d
0x18007fd7a  test    rdi, rdi
0x18007fd7d  jz      short loc_18007FDA1
0x18007fd7f  movzx   r8d, word ptr [r15]
0x18007fd83  test    r8w, r8w
0x18007fd87  jz      short loc_18007FDA1
  ... truncated ...
```
