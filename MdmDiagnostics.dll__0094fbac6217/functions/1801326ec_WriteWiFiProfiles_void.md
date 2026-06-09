# WriteWiFiProfiles(void)

- ea: `0x1801326ec`
- end: `0x180132cba`
- name: `?WriteWiFiProfiles@@YAJXZ`
- size: `1486`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180104270`
- `0x180104460`
- `0x1801044a8`
- `0x18010589c`
- `0x180105b28`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x1801271ec`
- `0x180127820`
- `0x1801278d0`
- `0x180127908`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012a4fc`
- `0x1801312d0`
- `0x1801326ec`
- `0x1801373b8`
- `0x18013826c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801327a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013283e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013297a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132a02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132b45`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132c58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801327a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013283e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013297a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132a02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132b45`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132c58`

## string_xrefs

- `0x180132758`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801328fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132aa9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132bb1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 WriteWiFiProfiles(void)
{
  __int64 v0; // rcx
  int v1; // eax
  unsigned int v2; // edi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *i; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rax
  WCHAR *v22; // rax
  int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // esi
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-138h]
  int v33; // [rsp+20h] [rbp-138h]
  int v34; // [rsp+30h] [rbp-128h] BYREF
  int v35; // [rsp+34h] [rbp-124h] BYREF
  void *v36[2]; // [rsp+38h] [rbp-120h] BYREF
  void *v37[2]; // [rsp+48h] [rbp-110h] BYREF
  int v38[2]; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v39[8]; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-E8h]
  __int64 v41; // [rsp+78h] [rbp-E0h]
  const wchar_t *v42; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v43[8]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v44[32]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v45[32]; // [rsp+B0h] [rbp-A8h] BYREF
  _QWORD v46[10]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v47[32]; // [rsp+120h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources((Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources *)&v34);
  std::list<std::wstring>::list<std::wstring>(v38);
  std::list<std::wstring>::list<std::wstring>(v37);
  v1 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
         v0,
         (__int64)L"WiFi",
         (int)v37,
         (int)v38);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x937,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v1,
      v32);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v3,
      v37[0]);
    std::_Deallocate<16>(v37[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v4,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(void **)v38, 0x30u);
    if ( v34 )
      CoUninitialize();
    return v2;
  }
  std::list<std::wstring>::list<std::wstring>(v36, v37);
  std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(
    (unsigned int)v36,
    (unsigned int)v43,
    v36[0],
    **(_QWORD **)v38,
    *(__int64 *)v38);
  if ( !v36[1] )
  {
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v6,
      v36[0]);
    std::_Deallocate<16>(v36[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v7,
      v37[0]);
    std::_Deallocate<16>(v37[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v8,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(void **)v38, 0x30u);
    if ( v34 )
      CoUninitialize();
    return 0;
  }
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v46,
    L"WiFi profiles",
    L"WifiProfilesTable");
  v42 = L"Profile";
  v35 = 40;
  v9 = std::vector<int>::vector<int>(v44, &v35, v36);
  v10 = std::vector<std::wstring>::vector<std::wstring>(v39, &v42, v43);
  v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
          v46,
          L"Only profiles managed by this MDM connection are displayed",
          v10,
          v9);
  std::vector<std::wstring>::_Tidy(v39);
  std::vector<enum TpmCapabilityPT>::_Tidy(v44);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x947,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v11,
      v33);
    v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v12,
      v36[0]);
    std::_Deallocate<16>(v36[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v13,
      v37[0]);
    std::_Deallocate<16>(v37[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v14,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(void **)v38, 0x30u);
    if ( v34 )
      CoUninitialize();
    return (unsigned int)v11;
  }
  v15 = v36[0];
  for ( i = *(_QWORD **)v36[0]; ; i = (_QWORD *)*i )
  {
    if ( i == v15 )
    {
      v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v17,
        v36[0]);
      std::_Deallocate<16>(v36[0], 0x30u);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v18,
        v37[0]);
      std::_Deallocate<16>(v37[0], 0x30u);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v19,
        *(_QWORD *)v38);
      std::_Deallocate<16>(*(void **)v38, 0x30u);
      if ( v34 )
        CoUninitialize();
      return 0;
    }
    std::wstring::wstring(v45, i + 2);
    v20 = std::wstring::rfind(v45, 47, -1);
    if ( v20 != -1 )
      break;
LABEL_31:
    std::wstring::_Tidy_deallocate(v45);
  }
  std::wstring::wstring(v44);
  v21 = std::wstring::substr(v45, v47, v20 + 1, -1);
  v22 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  v23 = UrlUnEscapeWrapper(v22);
  std::wstring::_Tidy_deallocate(v47);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v23,
      v33);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v45);
    v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v24,
      v36[0]);
    std::_Deallocate<16>(v36[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v25,
      v37[0]);
    std::_Deallocate<16>(v37[0], 0x30u);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v26,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(void **)v38, 0x30u);
    if ( v34 )
      CoUninitialize();
    return (unsigned int)v23;
  }
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v39);
  if ( v40 == v41 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v39, v40, v44);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v39, v44);
  v27 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v46, v39);
  v28 = v27;
  if ( v27 >= 0 )
  {
    std::vector<std::wstring>::_Tidy(v39);
    std::wstring::_Tidy_deallocate(v44);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x953,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
    (const char *)(unsigned int)v27,
    v33);
  std::vector<std::wstring>::_Tidy(v39);
  std::wstring::_Tidy_deallocate(v44);
  std::wstring::_Tidy_deallocate(v45);
  v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v29,
    v36[0]);
  std::_Deallocate<16>(v36[0], 0x30u);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v30,
    v37[0]);
  std::_Deallocate<16>(v37[0], 0x30u);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v31,
    *(_QWORD *)v38);
  std::_Deallocate<16>(*(void **)v38, 0x30u);
  if ( v34 )
    CoUninitialize();
  return v28;
}

```

## disassembly

```asm
0x1801326ec  mov     [rsp+arg_0], rbx
0x1801326f1  mov     [rsp+arg_8], rsi
0x1801326f6  push    rdi
0x1801326f7  sub     rsp, 150h
0x1801326fe  mov     rax, cs:__security_cookie
0x180132705  xor     rax, rsp
0x180132708  mov     [rsp+158h+var_18], rax
0x180132710  lea     rcx, [rsp+158h+var_128]; this
0x180132715  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x18013271a  nop
0x18013271b  lea     rcx, [rsp+158h+var_100]
0x180132720  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180132725  nop
0x180132726  lea     rcx, [rsp+158h+var_110]
0x18013272b  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180132730  nop
0x180132731  lea     r9, [rsp+158h+var_100]
0x180132736  lea     r8, [rsp+158h+var_110]
0x18013273b  lea     rdx, aWifi; "WiFi"
0x180132742  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x180132747  mov     edi, eax
0x180132749  test    eax, eax
0x18013274b  jns     short loc_1801327B1
0x18013274d  mov     rcx, [rsp+158h]; this
0x180132755  mov     r9d, eax; char *
0x180132758  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013275f  mov     edx, 937h; void *
0x180132764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132769  nop
0x18013276a  mov     rdx, [rsp+158h+var_110]
0x18013276f  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132774  mov     ebx, 30h ; '0'
0x180132779  mov     edx, ebx
0x18013277b  mov     rcx, [rsp+158h+var_110]
0x180132780  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132785  nop
0x180132786  mov     rdx, qword ptr [rsp+158h+var_100]
0x18013278b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132790  mov     edx, ebx
0x180132792  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132797  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013279c  nop
0x18013279d  cmp     [rsp+158h+var_128], 0
0x1801327a2  jz      short loc_1801327AA
0x1801327a4  call    cs:__imp_CoUninitialize
0x1801327aa  mov     eax, edi
0x1801327ac  jmp     loc_180132C94
0x1801327b1  lea     rdx, [rsp+158h+var_110]
0x1801327b6  lea     rcx, [rsp+158h+var_120]
0x1801327bb  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x1801327c0  nop
0x1801327c1  mov     r9, qword ptr [rsp+158h+var_100]
0x1801327c6  mov     qword ptr [rsp+158h+var_138], r9; int
0x1801327cb  mov     r9, [r9]
0x1801327ce  mov     r8, [rsp+158h+var_120]
0x1801327d3  lea     rdx, [rsp+158h+var_D0]
0x1801327db  lea     rcx, [rsp+158h+var_120]
0x1801327e0  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x1801327e5  cmp     [rsp+158h+var_118], 0
0x1801327eb  jnz     short loc_18013284B
0x1801327ed  mov     rdx, [rsp+158h+var_120]
0x1801327f2  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801327f7  mov     ebx, 30h ; '0'
0x1801327fc  mov     edx, ebx
0x1801327fe  mov     rcx, [rsp+158h+var_120]
0x180132803  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132808  nop
0x180132809  mov     rdx, [rsp+158h+var_110]
0x18013280e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132813  mov     edx, ebx
0x180132815  mov     rcx, [rsp+158h+var_110]
0x18013281a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013281f  nop
0x180132820  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132825  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013282a  mov     edx, ebx
0x18013282c  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132831  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132836  nop
0x180132837  cmp     [rsp+158h+var_128], 0
0x18013283c  jz      short loc_180132844
0x18013283e  call    cs:__imp_CoUninitialize
0x180132844  xor     eax, eax
0x180132846  jmp     loc_180132C94
0x18013284b  lea     r8, aWifiprofilesta; "WifiProfilesTable"
0x180132852  lea     rdx, aWifiProfiles; "WiFi profiles"
0x180132859  lea     rcx, [rsp+158h+var_88]; this
0x180132861  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180132866  nop
0x180132867  lea     rax, aProfile; "Profile"
0x18013286e  mov     [rsp+158h+var_D8], rax
0x180132876  mov     [rsp+158h+var_124], 28h ; '('
0x18013287e  lea     r8, [rsp+158h+var_120]
0x180132883  lea     rdx, [rsp+158h+var_124]
0x180132888  lea     rcx, [rsp+158h+var_C8]
0x180132890  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x180132895  mov     rbx, rax
0x180132898  lea     r8, [rsp+158h+var_D0]
0x1801328a0  lea     rdx, [rsp+158h+var_D8]
0x1801328a8  lea     rcx, [rsp+158h+var_F0]
0x1801328ad  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x1801328b2  nop
0x1801328b3  mov     r9, rbx
0x1801328b6  mov     r8, rax
0x1801328b9  lea     rdx, aOnlyProfilesMa; "Only profiles managed by this MDM conne"...
0x1801328c0  lea     rcx, [rsp+158h+var_88]
0x1801328c8  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x1801328cd  mov     edi, eax
0x1801328cf  lea     rcx, [rsp+158h+var_F0]
0x1801328d4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801328d9  nop
0x1801328da  lea     rcx, [rsp+158h+var_C8]
0x1801328e2  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x1801328e7  test    edi, edi
0x1801328e9  jns     loc_180132987
0x1801328ef  mov     rcx, [rsp+158h]; this
0x1801328f7  mov     r9d, edi; char *
0x1801328fa  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132901  mov     edx, 947h; void *
0x180132906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013290b  nop
0x18013290c  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180132913  mov     [rsp+158h+var_88], rax
0x18013291b  lea     rcx, [rsp+158h+var_88]; this
0x180132923  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180132928  nop
0x180132929  mov     rdx, [rsp+158h+var_120]
0x18013292e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132933  mov     ebx, 30h ; '0'
0x180132938  mov     edx, ebx
0x18013293a  mov     rcx, [rsp+158h+var_120]
0x18013293f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132944  nop
0x180132945  mov     rdx, [rsp+158h+var_110]
0x18013294a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013294f  mov     edx, ebx
0x180132951  mov     rcx, [rsp+158h+var_110]
0x180132956  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013295b  nop
0x18013295c  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132961  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132966  mov     edx, ebx
0x180132968  mov     rcx, qword ptr [rsp+158h+var_100]
0x18013296d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132972  nop
0x180132973  cmp     [rsp+158h+var_128], 0
0x180132978  jz      short loc_180132980
0x18013297a  call    cs:__imp_CoUninitialize
0x180132980  mov     eax, edi
0x180132982  jmp     loc_180132C94
0x180132987  mov     rdi, [rsp+158h+var_120]
0x18013298c  mov     rbx, [rdi]
0x18013298f  cmp     rbx, rdi
0x180132992  jnz     short loc_180132A0F
0x180132994  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013299b  mov     [rsp+158h+var_88], rax
0x1801329a3  lea     rcx, [rsp+158h+var_88]; this
0x1801329ab  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801329b0  nop
0x1801329b1  mov     rdx, [rsp+158h+var_120]
0x1801329b6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801329bb  mov     ebx, 30h ; '0'
0x1801329c0  mov     edx, ebx
0x1801329c2  mov     rcx, [rsp+158h+var_120]
0x1801329c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801329cc  nop
0x1801329cd  mov     rdx, [rsp+158h+var_110]
0x1801329d2  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801329d7  mov     edx, ebx
0x1801329d9  mov     rcx, [rsp+158h+var_110]
0x1801329de  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801329e3  nop
0x1801329e4  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801329e9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801329ee  mov     edx, ebx
0x1801329f0  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801329f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801329fa  nop
0x1801329fb  cmp     [rsp+158h+var_128], 0
0x180132a00  jz      short loc_180132A08
0x180132a02  call    cs:__imp_CoUninitialize
0x180132a08  xor     eax, eax
0x180132a0a  jmp     loc_180132C94
0x180132a0f  lea     rdx, [rbx+10h]
0x180132a13  lea     rcx, [rsp+158h+var_A8]
0x180132a1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180132a20  nop
0x180132a21  mov     edx, 2Fh ; '/'
0x180132a26  or      r8, 0FFFFFFFFFFFFFFFFh
0x180132a2a  lea     rcx, [rsp+158h+var_A8]
0x180132a32  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x180132a37  mov     rsi, rax
0x180132a3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180132a3e  jz      loc_180132C7B
0x180132a44  lea     rcx, [rsp+158h+var_C8]
0x180132a4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180132a51  nop
0x180132a52  lea     r8, [rsi+1]
0x180132a56  or      r9, 0FFFFFFFFFFFFFFFFh
0x180132a5a  lea     rdx, [rsp+158h+var_38]
0x180132a62  lea     rcx, [rsp+158h+var_A8]
0x180132a6a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180132a6f  mov     rcx, rax
0x180132a72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180132a77  lea     rdx, [rsp+158h+var_C8]
0x180132a7f  mov     rcx, rax; pszUrl
0x180132a82  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x180132a87  mov     esi, eax
0x180132a89  lea     rcx, [rsp+158h+var_38]
0x180132a91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132a96  test    esi, esi
0x180132a98  jns     loc_180132B52
0x180132a9e  mov     rcx, [rsp+158h]; this
0x180132aa6  mov     r9d, esi; char *
0x180132aa9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132ab0  mov     edx, 94Fh; void *
0x180132ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132aba  nop
0x180132abb  lea     rcx, [rsp+158h+var_C8]
0x180132ac3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132ac8  nop
0x180132ac9  lea     rcx, [rsp+158h+var_A8]
0x180132ad1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132ad6  nop
0x180132ad7  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180132ade  mov     [rsp+158h+var_88], rax
0x180132ae6  lea     rcx, [rsp+158h+var_88]; this
0x180132aee  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180132af3  nop
0x180132af4  mov     rdx, [rsp+158h+var_120]
0x180132af9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132afe  mov     ebx, 30h ; '0'
0x180132b03  mov     edx, ebx
0x180132b05  mov     rcx, [rsp+158h+var_120]
0x180132b0a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132b0f  nop
0x180132b10  mov     rdx, [rsp+158h+var_110]
0x180132b15  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132b1a  mov     edx, ebx
0x180132b1c  mov     rcx, [rsp+158h+var_110]
0x180132b21  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132b26  nop
0x180132b27  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132b2c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132b31  mov     edx, ebx
0x180132b33  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132b38  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132b3d  nop
0x180132b3e  cmp     [rsp+158h+var_128], 0
0x180132b43  jz      short loc_180132B4B
0x180132b45  call    cs:__imp_CoUninitialize
0x180132b4b  mov     eax, esi
0x180132b4d  jmp     loc_180132C94
0x180132b52  lea     rcx, [rsp+158h+var_F0]
0x180132b57  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180132b5c  nop
0x180132b5d  mov     rdx, [rsp+158h+var_E8]
0x180132b62  lea     rcx, [rsp+158h+var_F0]
0x180132b67  cmp     rdx, [rsp+158h+var_E0]
0x180132b6c  jz      short loc_180132B7D
0x180132b6e  lea     rdx, [rsp+158h+var_C8]
0x180132b76  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180132b7b  jmp     short loc_180132B8A
0x180132b7d  lea     r8, [rsp+158h+var_C8]
0x180132b85  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180132b8a  lea     rdx, [rsp+158h+var_F0]
0x180132b8f  lea     rcx, [rsp+158h+var_88]
0x180132b97  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x180132b9c  mov     esi, eax
0x180132b9e  test    eax, eax
0x180132ba0  jns     loc_180132C62
0x180132ba6  mov     rcx, [rsp+158h]; this
0x180132bae  mov     r9d, eax; char *
0x180132bb1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132bb8  mov     edx, 953h; void *
0x180132bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132bc2  nop
0x180132bc3  lea     rcx, [rsp+158h+var_F0]
0x180132bc8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180132bcd  nop
0x180132bce  lea     rcx, [rsp+158h+var_C8]
0x180132bd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132bdb  nop
0x180132bdc  lea     rcx, [rsp+158h+var_A8]
0x180132be4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132be9  nop
0x180132bea  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180132bf1  mov     [rsp+158h+var_88], rax
0x180132bf9  lea     rcx, [rsp+158h+var_88]; this
0x180132c01  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180132c06  nop
0x180132c07  mov     rdx, [rsp+158h+var_120]
0x180132c0c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132c11  mov     ebx, 30h ; '0'
0x180132c16  mov     edx, ebx
0x180132c18  mov     rcx, [rsp+158h+var_120]
0x180132c1d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132c22  nop
0x180132c23  mov     rdx, [rsp+158h+var_110]
0x180132c28  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
  ... truncated ...
```
