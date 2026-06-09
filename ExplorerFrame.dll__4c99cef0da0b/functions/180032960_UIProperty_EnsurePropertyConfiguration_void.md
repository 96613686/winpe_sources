# UIProperty::_EnsurePropertyConfiguration(void)

- ea: `0x180032960`
- end: `0x180032e5a`
- name: `?_EnsurePropertyConfiguration@UIProperty@@IEAAJXZ`
- size: `1274`
- prototype: `__int64 __fastcall(UIProperty *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fc50`
- `0x180031350`
- `0x180032260`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x180032960`
- `0x1800340a0`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d8c`
- `PROPSYS!PSGetPropertyDescription` at `0x180032a7a`
- `PROPSYS!PSGetPropertyDescription` at `0x180032a7a`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180032b76`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180032c86`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180032b76`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180032c86`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180032b97`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180032ca7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180032b97`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180032ca7`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180032d80`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180032e4e`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180032d80`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180032e4e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032ba0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032bd6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032cb0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032cdd`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032ba0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032bd6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032cb0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180032cdd`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x180032bca`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x180032bca`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180032bbe`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180032bbe`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180032cc3`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180032dad`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180032cc3`
- `DUI70!?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180032dad`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800329a2`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180032b17`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800329a2`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180032b17`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UIProperty::_EnsurePropertyConfiguration(UIProperty *this)
{
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rsi
  _QWORD *v6; // r14
  void *v7; // rsi
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, __int64); // r15
  struct DirectUI::Element *v10; // rax
  struct DirectUI::Element *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  struct DirectUI::Value *Bool; // rax
  DirectUI::Value *v15; // rdi
  int (__fastcall ***v16)(void *, GUID *, LPVOID *); // r15
  DirectUI::Value *Value; // rsi
  bool v18; // di
  int v19; // edi
  int v20; // eax
  __int64 v21; // rax
  struct DirectUI::Value *v22; // rax
  DirectUI::Value *v23; // rdi
  DirectUI::Value *v24; // rcx
  void *v26; // rsi
  int (__fastcall *v27)(void *, LPVOID *); // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  struct DirectUI::Value *v33; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v36[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( *((_DWORD *)this + 142) )
    return 0;
  TopLevel = DirectUI::Element::GetTopLevel(this);
  v3 = TopLevel;
  if ( TopLevel )
  {
    v4 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v4 + 80LL))(
           v4,
           UIItemsView::Class) )
    {
      *((_DWORD *)this + 142) = 1;
      v5 = *((_QWORD *)v3 + 50);
      v35 = v5;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = (_QWORD *)((char *)this + 572);
      if ( *((_QWORD *)v3 + 50) )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64, char *, int *))(*(_QWORD *)v5 + 256LL))(v5, (char *)this + 572, &v31);
        *((_DWORD *)this + 148) |= v31;
      }
      if ( *((_DWORD *)v3 + 113) == 4 )
        *((_DWORD *)this + 148) |= 0x10000000u;
      ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&ppv);
      if ( PSGetPropertyDescription(
             (const PROPERTYKEY *const)((char *)this + 572),
             &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
             &ppv) < 0 )
      {
        if ( !v5 )
        {
LABEL_39:
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ppv);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v35);
          return 0;
        }
        v33 = 0;
        if ( !DirectUI::Element::GetAccName(this, &v33)
          && (*(int (__fastcall **)(__int64, char *, unsigned __int16 *, __int64))(*(_QWORD *)v5 + 136LL))(
               v5,
               (char *)this + 572,
               v36,
               260) >= 0 )
        {
          DirectUI::Element::SetAccName(this, v36);
        }
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(UIProperty *, void *))(*(_QWORD *)this + 384LL))(this, ppv) )
        {
          v7 = (void *)*((_QWORD *)v3 + 50);
          pv = v7;
          if ( v7 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
          if ( *((_QWORD *)v3 + 50)
            && (*(int (__fastcall **)(void *, char *, __int64, GUID *, char *))(*(_QWORD *)v7 + 248LL))(
                 v7,
                 (char *)this + 572,
                 1,
                 &GUID_1572dd51_443c_44b0_ace4_38a005fc697e,
                 (char *)this + 600) >= 0 )
          {
            v8 = *((_QWORD *)this + 75);
            v9 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 168LL);
            v10 = DirectUI::Element::GetTopLevel(this);
            v11 = v10;
            if ( v10
              && (v12 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v10 + 280LL))(v10),
                  (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v12 + 80LL))(
                    v12,
                    UIItemsView::Class)) )
            {
              v13 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v11 + 360LL))(v11);
            }
            else
            {
              v13 = 0;
            }
            v9(v8, v13);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&pv);
          Bool = DirectUI::Value::CreateBool(0);
          v15 = Bool;
          if ( Bool )
          {
            DirectUI::Element::SetValue(this, UIProperty::EnableHitHighlightingProp, 1, Bool);
            DirectUI::Value::Release(v15);
          }
        }
        v16 = (int (__fastcall ***)(void *, GUID *, LPVOID *))ppv;
        Value = DirectUI::Element::GetValue(this, UIProperty::EnableHitHighlightingProp, 2, 0);
        v18 = DirectUI::Value::GetBool(Value);
        DirectUI::Value::Release(Value);
        if ( !v18 )
          goto LABEL_34;
        v19 = 0;
        ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&pv);
        if ( (**v16)(v16, &GUID_078f91bd_29a2_440f_924e_46a291524520, &pv) >= 0 )
        {
          v31 = 0;
          if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 192LL))(pv, &v31) >= 0 )
          {
            if ( (v31 & 1) != 0 )
              goto LABEL_32;
            v20 = *((_DWORD *)this + 147);
            if ( v20 == 3 )
            {
              v28 = *v6 - *(_QWORD *)&PKEY_Search_QueryFocusedSummary.fmtid.Data1;
              if ( *v6 == *(_QWORD *)&PKEY_Search_QueryFocusedSummary.fmtid.Data1 )
                v28 = *(_QWORD *)((char *)this + 580) - *(_QWORD *)PKEY_Search_QueryFocusedSummary.fmtid.Data4;
              if ( !v28 )
                goto LABEL_32;
            }
            if ( v20 == 4 )
            {
              v29 = *v6 - *(_QWORD *)&PKEY_Search_QueryFocusedSummaryWithFallback.fmtid.Data1;
              if ( *v6 == *(_QWORD *)&PKEY_Search_QueryFocusedSummaryWithFallback.fmtid.Data1 )
                v29 = *(_QWORD *)((char *)this + 580)
                    - *(_QWORD *)PKEY_Search_QueryFocusedSummaryWithFallback.fmtid.Data4;
              if ( !v29 )
                goto LABEL_32;
            }
            if ( v20 == 2 )
            {
              v21 = *v6 - *(_QWORD *)&PKEY_Search_AutoSummary.fmtid.Data1;
              if ( *v6 == *(_QWORD *)&PKEY_Search_AutoSummary.fmtid.Data1 )
                v21 = *(_QWORD *)((char *)this + 580) - *(_QWORD *)PKEY_Search_AutoSummary.fmtid.Data4;
              if ( !v21 )
LABEL_32:
                v19 = 1;
            }
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&pv);
        if ( !v19 )
        {
LABEL_34:
          v22 = DirectUI::Value::CreateBool(0);
          v23 = v22;
          if ( v22 )
          {
            DirectUI::Element::SetValue(this, UIProperty::EnableHitHighlightingProp, 1, v22);
            DirectUI::Value::Release(v23);
          }
        }
        v33 = 0;
        if ( !DirectUI::Element::GetAccName(this, &v33) )
        {
          pv = 0;
          v26 = ppv;
          v27 = *(int (__fastcall **)(void *, LPVOID *))(*(_QWORD *)ppv + 48LL);
          CoTaskMemFree(0);
          if ( v27(v26, &pv) >= 0 )
            DirectUI::Element::SetAccName(this, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
        }
      }
      v24 = v33;
      if ( v33 )
      {
        v33 = 0;
        DirectUI::Value::Release(v24);
      }
      goto LABEL_39;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x914,
    (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
    (const char *)0x80004005LL,
    v30);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180032960  mov     [rsp-8+arg_8], rbx
0x180032965  mov     [rsp-8+arg_10], rsi
0x18003296a  push    rbp
0x18003296b  push    rdi
0x18003296c  push    r12
0x18003296e  push    r14
0x180032970  push    r15
0x180032972  lea     rbp, [rsp-180h]
0x18003297a  sub     rsp, 280h
0x180032981  mov     rax, cs:__security_cookie
0x180032988  xor     rax, rsp
0x18003298b  mov     [rbp+1A0h+var_30], rax
0x180032992  mov     rbx, rcx
0x180032995  cmp     dword ptr [rcx+238h], 0
0x18003299c  jnz     loc_180032CF9
0x1800329a2  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x1800329a8  mov     rdi, rax
0x1800329ab  test    rax, rax
0x1800329ae  jz      loc_180032D26
0x1800329b4  mov     rcx, [rax]
0x1800329b7  mov     rax, [rcx+118h]
0x1800329be  mov     rcx, rdi
0x1800329c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329c6  mov     r8, rax
0x1800329c9  mov     rcx, [rax]
0x1800329cc  mov     rax, [rcx+50h]
0x1800329d0  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x1800329d7  mov     rcx, r8
0x1800329da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329df  test    al, al
0x1800329e1  jz      loc_180032D26
0x1800329e7  mov     dword ptr [rbx+238h], 1
0x1800329f1  mov     rsi, [rdi+190h]
0x1800329f8  mov     [rsp+2A0h+var_250], rsi
0x1800329fd  test    rsi, rsi
0x180032a00  jz      short loc_180032A11
0x180032a02  mov     rax, [rsi]
0x180032a05  mov     rcx, rsi
0x180032a08  mov     rax, [rax+8]
0x180032a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a11  lea     r14, [rbx+23Ch]
0x180032a18  xor     r12d, r12d
0x180032a1b  cmp     [rdi+190h], r12
0x180032a22  jz      short loc_180032A4D
0x180032a24  mov     [rsp+2A0h+var_270], r12d
0x180032a29  mov     rax, [rsi]
0x180032a2c  lea     r8, [rsp+2A0h+var_270]
0x180032a31  mov     rdx, r14
0x180032a34  mov     rcx, rsi
0x180032a37  mov     rax, [rax+100h]
0x180032a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a43  mov     eax, [rsp+2A0h+var_270]
0x180032a47  or      [rbx+250h], eax
0x180032a4d  cmp     dword ptr [rdi+1C4h], 4
0x180032a54  jnz     short loc_180032A60
0x180032a56  or      dword ptr [rbx+250h], 10000000h
0x180032a60  lea     rcx, [rsp+2A0h+ppv]; void *
0x180032a65  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180032a6a  nop
0x180032a6b  lea     r8, [rsp+2A0h+ppv]; ppv
0x180032a70  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x180032a77  mov     rcx, r14; propkey
0x180032a7a  call    cs:__imp_PSGetPropertyDescription
0x180032a80  test    eax, eax
0x180032a82  js      loc_180032D97
0x180032a88  mov     rax, [rbx]
0x180032a8b  mov     rdx, [rsp+2A0h+ppv]
0x180032a90  mov     rcx, rbx
0x180032a93  mov     rax, [rax+180h]
0x180032a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a9f  test    eax, eax
0x180032aa1  jz      loc_180032BA6
0x180032aa7  mov     rsi, [rdi+190h]
0x180032aae  mov     [rsp+2A0h+pv], rsi
0x180032ab3  test    rsi, rsi
0x180032ab6  jz      short loc_180032AC7
0x180032ab8  mov     rax, [rsi]
0x180032abb  mov     rcx, rsi
0x180032abe  mov     rax, [rax+8]
0x180032ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ac7  cmp     qword ptr [rdi+190h], 0
0x180032acf  jz      loc_180032B6A
0x180032ad5  lea     rdi, [rbx+258h]
0x180032adc  mov     rax, [rsi]
0x180032adf  mov     qword ptr [rsp+2A0h+var_280], rdi
0x180032ae4  lea     r9, _GUID_1572dd51_443c_44b0_ace4_38a005fc697e
0x180032aeb  mov     r8d, 1
0x180032af1  mov     rdx, r14
0x180032af4  mov     rcx, rsi
0x180032af7  mov     rax, [rax+0F8h]
0x180032afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b03  test    eax, eax
0x180032b05  js      short loc_180032B6A
0x180032b07  mov     rdi, [rdi]
0x180032b0a  mov     rax, [rdi]
0x180032b0d  mov     r15, [rax+0A8h]
0x180032b14  mov     rcx, rbx
0x180032b17  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x180032b1d  mov     rsi, rax
0x180032b20  test    rax, rax
0x180032b23  jz      short loc_180032B58
0x180032b25  mov     rcx, [rax]
0x180032b28  mov     rax, [rcx+118h]
0x180032b2f  mov     rcx, rsi
0x180032b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b37  mov     r8, rax
0x180032b3a  mov     rcx, [rax]
0x180032b3d  mov     rax, [rcx+50h]
0x180032b41  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x180032b48  mov     rcx, r8
0x180032b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b50  test    al, al
0x180032b52  jnz     loc_180032E07
0x180032b58  mov     rax, r12
0x180032b5b  mov     rdx, rax
0x180032b5e  mov     rcx, rdi
0x180032b61  mov     rax, r15
0x180032b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b69  nop
0x180032b6a  lea     rcx, [rsp+2A0h+pv]; void *
0x180032b6f  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032b74  xor     ecx, ecx
0x180032b76  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x180032b7c  mov     rdi, rax
0x180032b7f  test    rax, rax
0x180032b82  jz      short loc_180032BA6
0x180032b84  mov     r9, rax
0x180032b87  mov     r8d, 1
0x180032b8d  lea     rdx, ?EnableHitHighlightingProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::EnableHitHighlightingProp(void)
0x180032b94  mov     rcx, rbx
0x180032b97  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180032b9d  mov     rcx, rdi
0x180032ba0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180032ba6  mov     r15, [rsp+2A0h+ppv]
0x180032bab  xor     r9d, r9d
0x180032bae  mov     r8d, 2
0x180032bb4  lea     rdx, ?EnableHitHighlightingProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::EnableHitHighlightingProp(void)
0x180032bbb  mov     rcx, rbx
0x180032bbe  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180032bc4  mov     rsi, rax
0x180032bc7  mov     rcx, rax
0x180032bca  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x180032bd0  movzx   edi, al
0x180032bd3  mov     rcx, rsi
0x180032bd6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180032bdc  test    dil, dil
0x180032bdf  jz      loc_180032C84
0x180032be5  mov     edi, r12d
0x180032be8  lea     rcx, [rsp+2A0h+pv]; void *
0x180032bed  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180032bf2  nop
0x180032bf3  mov     rax, [r15]
0x180032bf6  lea     r8, [rsp+2A0h+pv]
0x180032bfb  lea     rdx, _GUID_078f91bd_29a2_440f_924e_46a291524520
0x180032c02  mov     rcx, r15
0x180032c05  mov     rax, [rax]
0x180032c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c0d  test    eax, eax
0x180032c0f  js      short loc_180032C76
0x180032c11  mov     [rsp+2A0h+var_270], r12d
0x180032c16  mov     rcx, [rsp+2A0h+pv]
0x180032c1b  mov     rax, [rcx]
0x180032c1e  lea     rdx, [rsp+2A0h+var_270]
0x180032c23  mov     rax, [rax+0C0h]
0x180032c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c2f  test    eax, eax
0x180032c31  js      short loc_180032C76
0x180032c33  test    byte ptr [rsp+2A0h+var_270], 1
0x180032c38  jnz     short loc_180032C71
0x180032c3a  mov     eax, [r14+10h]
0x180032c3e  cmp     eax, 3
0x180032c41  jz      loc_180032DBD
0x180032c47  cmp     eax, 4
0x180032c4a  jz      loc_180032DE2
0x180032c50  cmp     eax, 2
0x180032c53  jnz     short loc_180032C76
0x180032c55  mov     rax, [r14]
0x180032c58  sub     rax, qword ptr cs:PKEY_Search_AutoSummary.fmtid.Data1
0x180032c5f  jnz     short loc_180032C6C
0x180032c61  mov     rax, [r14+8]
0x180032c65  sub     rax, qword ptr cs:PKEY_Search_AutoSummary.fmtid.Data4
0x180032c6c  test    rax, rax
0x180032c6f  jnz     short loc_180032C76
0x180032c71  mov     edi, 1
0x180032c76  lea     rcx, [rsp+2A0h+pv]; void *
0x180032c7b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032c80  test    edi, edi
0x180032c82  jnz     short loc_180032CB6
0x180032c84  xor     ecx, ecx
0x180032c86  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x180032c8c  mov     rdi, rax
0x180032c8f  test    rax, rax
0x180032c92  jz      short loc_180032CB6
0x180032c94  mov     r9, rax
0x180032c97  mov     r8d, 1
0x180032c9d  lea     rdx, ?EnableHitHighlightingProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::EnableHitHighlightingProp(void)
0x180032ca4  mov     rcx, rbx
0x180032ca7  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180032cad  mov     rcx, rdi
0x180032cb0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180032cb6  mov     [rsp+2A0h+var_260], r12
0x180032cbb  lea     rdx, [rsp+2A0h+var_260]
0x180032cc0  mov     rcx, rbx
0x180032cc3  call    cs:__imp_?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetAccName(DirectUI::Value * *)
0x180032cc9  test    rax, rax
0x180032ccc  jz      short loc_180032D4B
0x180032cce  mov     rcx, [rsp+2A0h+var_260]
0x180032cd3  test    rcx, rcx
0x180032cd6  jz      short loc_180032CE4
0x180032cd8  mov     [rsp+2A0h+var_260], r12
0x180032cdd  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180032ce3  nop
0x180032ce4  lea     rcx, [rsp+2A0h+ppv]; void *
0x180032ce9  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032cee  nop
0x180032cef  lea     rcx, [rsp+2A0h+var_250]; void *
0x180032cf4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032cf9  xor     eax, eax
0x180032cfb  mov     rcx, [rbp+1A0h+var_30]
0x180032d02  xor     rcx, rsp; StackCookie
0x180032d05  call    __security_check_cookie
0x180032d0a  lea     r11, [rsp+2A0h+var_20]
0x180032d12  mov     rbx, [r11+38h]
0x180032d16  mov     rsi, [r11+40h]
0x180032d1a  mov     rsp, r11
0x180032d1d  pop     r15
0x180032d1f  pop     r14
0x180032d21  pop     r12
0x180032d23  pop     rdi
0x180032d24  pop     rbp
0x180032d25  retn
0x180032d26  mov     rcx, [rbp+1A8h]; this
0x180032d2d  mov     r9d, 80004005h; char *
0x180032d33  lea     r8, aShellExplorerf_0; "shell\\explorerframe\\itemsview\\uiprop"...
0x180032d3a  mov     edx, 914h; void *
0x180032d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d44  mov     eax, 80004005h
0x180032d49  jmp     short loc_180032CFB
0x180032d4b  mov     [rsp+2A0h+pv], r12
0x180032d50  mov     rsi, [rsp+2A0h+ppv]
0x180032d55  mov     rax, [rsi]
0x180032d58  mov     rdi, [rax+30h]
0x180032d5c  xor     ecx, ecx; pv
0x180032d5e  call    cs:__imp_CoTaskMemFree
0x180032d64  lea     rdx, [rsp+2A0h+pv]
0x180032d69  mov     rcx, rsi
0x180032d6c  mov     rax, rdi
0x180032d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d74  test    eax, eax
0x180032d76  js      short loc_180032D87
0x180032d78  mov     rdx, [rsp+2A0h+pv]
0x180032d7d  mov     rcx, rbx
0x180032d80  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180032d86  nop
0x180032d87  mov     rcx, [rsp+2A0h+pv]; pv
0x180032d8c  call    cs:__imp_CoTaskMemFree
0x180032d92  jmp     loc_180032CCE
0x180032d97  test    rsi, rsi
0x180032d9a  jz      loc_180032CE4
0x180032da0  mov     [rsp+2A0h+var_260], r12
0x180032da5  lea     rdx, [rsp+2A0h+var_260]
0x180032daa  mov     rcx, rbx
0x180032dad  call    cs:__imp_?GetAccName@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetAccName(DirectUI::Value * *)
0x180032db3  test    rax, rax
0x180032db6  jz      short loc_180032E1E
0x180032db8  jmp     loc_180032CCE
0x180032dbd  mov     rcx, [r14]
0x180032dc0  sub     rcx, qword ptr cs:PKEY_Search_QueryFocusedSummary.fmtid.Data1
0x180032dc7  jnz     short loc_180032DD4
0x180032dc9  mov     rcx, [r14+8]
0x180032dcd  sub     rcx, qword ptr cs:PKEY_Search_QueryFocusedSummary.fmtid.Data4
0x180032dd4  test    rcx, rcx
0x180032dd7  jnz     loc_180032C47
0x180032ddd  jmp     loc_180032C71
0x180032de2  mov     rcx, [r14]
0x180032de5  sub     rcx, qword ptr cs:PKEY_Search_QueryFocusedSummaryWithFallback.fmtid.Data1
0x180032dec  jnz     short loc_180032DF9
0x180032dee  mov     rcx, [r14+8]
0x180032df2  sub     rcx, qword ptr cs:PKEY_Search_QueryFocusedSummaryWithFallback.fmtid.Data4
0x180032df9  test    rcx, rcx
0x180032dfc  jnz     loc_180032C50
0x180032e02  jmp     loc_180032C71
0x180032e07  mov     rax, [rsi]
0x180032e0a  mov     rcx, rsi
0x180032e0d  mov     rax, [rax+168h]
0x180032e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e19  jmp     loc_180032B5B
0x180032e1e  mov     rax, [rsi]
0x180032e21  mov     r9d, 104h
0x180032e27  lea     r8, [rsp+2A0h+var_240]
0x180032e2c  mov     rdx, r14
0x180032e2f  mov     rcx, rsi
0x180032e32  mov     rax, [rax+88h]
0x180032e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e3e  test    eax, eax
0x180032e40  js      loc_180032DB8
0x180032e46  lea     rdx, [rsp+2A0h+var_240]
0x180032e4b  mov     rcx, rbx
0x180032e4e  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180032e54  jmp     loc_180032DB8
  ... truncated ...
```
