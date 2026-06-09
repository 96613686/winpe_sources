# AgentAccountHelpers::DoesUserConsentToProvisionAgentUsers_NoLock(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Windows::UI::WindowId,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x180043484`
- end: `0x180043eae`
- name: `?DoesUserConsentToProvisionAgentUsers_NoLock@AgentAccountHelpers@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00UWindowId@UI@Windows@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAV73@@Z`
- size: `2602`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013b04`

## callees

- `0x18000302e`
- `0x1800030d0`
- `0x180003458`
- `0x1800034ac`
- `0x1800050c1`
- `0x18001045c`
- `0x180011e18`
- `0x180032b58`
- `0x18003537c`
- `0x1800356e0`
- `0x18003e548`
- `0x18003ef60`
- `0x18003f32c`
- `0x1800400c8`
- `0x1800402c0`
- `0x180040460`
- `0x180043484`
- `0x1800454d4`
- `0x180046a40`
- `0x18004768c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043b64`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e4d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e58`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043b64`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e4d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e58`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043e82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043513`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043556`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004387f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800438b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043513`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043556`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004387f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800438b1`

## string_xrefs

- `0x1800434ed`: `DoesUserConsent: Beginning CheckAccessForUserSID calls:`
- `0x180043569`: `AgentSession`
- `0x1800438c4`: `AgentSession`
- `0x1800437a1`: ` - CheckAccess Op='%s' Res='%s' => %d (%s)`
- `0x180043aff`: ` - CheckAccess Op='%s' Res='%s' => %d (%s)`
- `0x180043b88`: `DoesUserConsent: Array of size %u sent to RequestAccessForUserSIDAsync:`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AgentAccountHelpers::DoesUserConsentToProvisionAgentUsers_NoLock(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4,
        struct winrt::impl::shared_hstring_header ***a5,
        char ***a6)
{
  __int64 v8; // r14
  char **v9; // rsi
  char **v10; // rbx
  struct winrt::impl::shared_hstring_header *v11; // r15
  unsigned int v12; // edx
  __int64 v13; // rdx
  struct winrt::impl::shared_hstring_header *v14; // rbx
  _OWORD *v15; // rcx
  struct winrt::impl::shared_hstring_header *v16; // rax
  __int64 v17; // rdx
  struct winrt::impl::shared_hstring_header *v18; // rbx
  _OWORD *v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  void (__fastcall ***v25)(_QWORD, __int64 *, __int64 **); // rcx
  int v26; // ebx
  const wchar_t *v27; // rax
  const WCHAR *v28; // r9
  const WCHAR *v29; // r8
  __int64 v30; // rcx
  const char *v31; // r9
  __int64 result; // rax
  __int64 v33; // rdx
  struct winrt::impl::shared_hstring_header **v34; // rcx
  struct winrt::impl::shared_hstring_header *v35; // rax
  int v36; // ebx
  struct winrt::impl::shared_hstring_header *v37; // r14
  struct winrt::impl::shared_hstring_header *v38; // rsi
  struct winrt::impl::shared_hstring_header *v39; // rax
  size_t v40; // r8
  void *v41; // rcx
  struct winrt::impl::shared_hstring_header *v42; // rax
  __int64 v43; // rdx
  struct winrt::impl::shared_hstring_header *v44; // rsi
  _OWORD *v45; // rcx
  __int64 v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // rdx
  _QWORD *v49; // rax
  __int64 v50; // rdx
  void (__fastcall ***v51)(_QWORD, __int64 *, __int64 **); // rcx
  int v52; // esi
  const wchar_t *v53; // rcx
  const WCHAR *v54; // r9
  const WCHAR *v55; // r8
  __int64 v56; // rcx
  int *v57; // r15
  __int64 v58; // rsi
  _QWORD *i; // rbx
  _QWORD *v60; // r14
  __int64 v61; // rax
  const WCHAR *v62; // r9
  const WCHAR *v63; // r8
  const wchar_t *v64; // rax
  __int64 v65; // rax
  _QWORD *v66; // rcx
  __int64 v67; // rdx
  _QWORD *v68; // rcx
  __int64 v69; // rdx
  void (__fastcall **v70)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v71; // rcx
  int v72; // edi
  void *v73; // rbx
  int v74; // eax
  HANDLE ProcessHeap; // rax
  unsigned int GrantedCapabilities; // ebx
  __int64 v77; // [rsp+20h] [rbp-168h]
  struct winrt::impl::shared_hstring_header *v78; // [rsp+50h] [rbp-138h] BYREF
  struct winrt::impl::shared_hstring_header *v79; // [rsp+58h] [rbp-130h]
  __int128 v80; // [rsp+60h] [rbp-128h] BYREF
  __int64 v81; // [rsp+70h] [rbp-118h]
  struct winrt::impl::shared_hstring_header **v82; // [rsp+80h] [rbp-108h] BYREF
  int v83; // [rsp+88h] [rbp-100h]
  int v84; // [rsp+8Ch] [rbp-FCh]
  int *v85; // [rsp+90h] [rbp-F8h] BYREF
  int v86; // [rsp+98h] [rbp-F0h] BYREF
  int v87; // [rsp+9Ch] [rbp-ECh]
  void (__fastcall ***v88)(_QWORD, __int64 *, __int64 **); // [rsp+A8h] [rbp-E0h]
  int **v89; // [rsp+B0h] [rbp-D8h] BYREF
  _QWORD v90[2]; // [rsp+B8h] [rbp-D0h] BYREF
  struct winrt::impl::shared_hstring_header ***v91; // [rsp+C8h] [rbp-C0h]
  struct winrt::impl::shared_hstring_header *v92; // [rsp+D0h] [rbp-B8h] BYREF
  _QWORD v93[3]; // [rsp+D8h] [rbp-B0h] BYREF
  int *v94; // [rsp+F0h] [rbp-98h] BYREF
  int v95; // [rsp+F8h] [rbp-90h] BYREF
  int v96; // [rsp+FCh] [rbp-8Ch]
  void (__fastcall ***v97)(_QWORD, __int64 *, __int64 **); // [rsp+108h] [rbp-80h]
  LPVOID lpMem; // [rsp+110h] [rbp-78h] BYREF
  int *v99; // [rsp+118h] [rbp-70h] BYREF
  int v100; // [rsp+120h] [rbp-68h] BYREF
  int v101; // [rsp+124h] [rbp-64h]
  _QWORD *v102; // [rsp+130h] [rbp-58h]
  _QWORD v103[5]; // [rsp+138h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v8 = a1;
  v9 = a6[1];
  v10 = *a6;
  if ( *a6 != v9 )
  {
    do
    {
      std::wstring::~wstring(v10);
      v10 += 4;
    }
    while ( v10 != v9 );
    a6[1] = *a6;
  }
  v80 = 0;
  v11 = 0;
  v81 = 0;
  try
  {
    Log(4u, L"DoesUserConsent: Beginning CheckAccessForUserSID calls:");
    v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)9, v12);
    v15 = (_OWORD *)((char *)v14 + 28);
    if ( v14 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *(_DWORD *)_o__errno(v15, v13) = 22;
      invalid_parameter_noinfo();
    }
    else
    {
      *v15 = *(_OWORD *)L"Provision";
      *((_WORD *)v14 + 22) = aProvision[8];
    }
    v78 = v14;
    v16 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xC, v13);
    v18 = v16;
    v19 = (_OWORD *)((char *)v16 + 28);
    if ( v16 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *(_DWORD *)_o__errno(v19, v17) = 22;
      invalid_parameter_noinfo();
    }
    else
    {
      *v19 = *(_OWORD *)L"AgentSession";
      *(_QWORD *)((char *)v16 + 44) = *(_QWORD *)L"sion";
    }
    v79 = v18;
    v20 = a2[2];
    v21 = a2;
    if ( a2[3] > 7u )
      v21 = (_QWORD *)*a2;
    if ( (_DWORD)v20 )
    {
      v22 = (unsigned int)v20;
      if ( *((_WORD *)v21 + (unsigned int)v20) )
        goto LABEL_151;
      v86 = 1;
      v87 = v20;
      v88 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v21;
      v85 = &v86;
    }
    else
    {
      v85 = 0;
      v22 = 0;
    }
    if ( a2[3] <= 7u )
      v23 = a2;
    else
      v23 = (_QWORD *)*a2;
    if ( (_DWORD)v20 )
    {
      if ( *((_WORD *)v23 + v22) )
        goto LABEL_151;
      LODWORD(v93[0]) = 1;
      HIDWORD(v93[0]) = v20;
      v93[2] = v23;
      v92 = (struct winrt::impl::shared_hstring_header *)v93;
    }
    else
    {
      v92 = 0;
    }
    v24 = *(_QWORD *)(v8 + 16);
    if ( *(_QWORD *)(v8 + 24) <= 7u )
      v25 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v8;
    else
      v25 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 **))v8;
    if ( !(_DWORD)v24 )
    {
      v94 = 0;
      goto LABEL_31;
    }
    if ( !*((_WORD *)v25 + (unsigned int)v24) )
    {
      v95 = 1;
      v96 = v24;
      v97 = v25;
      v94 = &v95;
LABEL_31:
      v82 = &v78;
      v83 = 1;
      v84 = v96;
      v89 = &v94;
      v90[0] = &v92;
      v90[1] = &v85;
      v91 = &v82;
      lpMem = &qword_1800B9028;
      _InterlockedAdd64(&qword_1800B9028, 1u);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics> )
      {
        v26 = `winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager::CheckAccessForUserSID'::`2'::_lambda_1_::operator()(
                &v89,
                (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>);
        _InterlockedDecrement64(&qword_1800B9028);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800B9028);
        v26 = ___call_AEAV_lambda_1___1__CheckAccessForUserSID_McpAccessManager_Mcp_Agents_AI_Internal_Windows_winrt__SA_AEBUhstring_param_9_00U__array_view___CBUMcpResourceRequestInfo_Mcp_Agents_AI_Internal_Windows_winrt___9__Z____factory_cache_entry_UMcpAccessManager_Mcp_Agents_AI_Internal_Windows_winrt__UIMcpAccessManagerStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CheckAccessForUserSID_McpAccessManager_Mcp_Agents_AI_Internal_Windows_2_SA_AEBUhstring_param_2_00U__array_view___CBUMcpResourceRequestInfo_Mcp_Agents_AI_Internal_Windows_winrt___2__Z__Z(
                v25,
                (__int64)&v89);
      }
      if ( v26 )
      {
        v27 = L"UserPromptRequired";
        if ( v26 != 1 )
          v27 = L"Denied";
      }
      else
      {
        v27 = L"Allowed";
      }
      if ( v79 )
        v28 = (const WCHAR *)*((_QWORD *)v79 + 2);
      else
        v28 = &word_180096C4C;
      if ( v78 )
        v29 = (const WCHAR *)*((_QWORD *)v78 + 2);
      else
        v29 = &word_180096C4C;
      Log(4u, L" - CheckAccess Op='%s' Res='%s' => %d (%s)", v29, v28, v26, v27);
      if ( v26 == 1 )
      {
        if ( *((_QWORD *)&v80 + 1) == v81 )
        {
          std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::_Emplace_reallocate<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(
            (winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo **)&v80,
            *((char **)&v80 + 1),
            (__int64)&v78);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>>::construct<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(
            v30,
            *((struct winrt::impl::shared_hstring_header ***)&v80 + 1),
            &v78);
          *((_QWORD *)&v80 + 1) += 16LL;
        }
      }
      else if ( v26 )
      {
        winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo::~McpResourceRequestInfo((winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo *)&v78);
        std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::~vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>((__int64)&v80);
        return 2147942405LL;
      }
      winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo::~McpResourceRequestInfo((winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo *)&v78);
      v34 = *a5;
      v35 = (struct winrt::impl::shared_hstring_header *)a5[1];
      v78 = v35;
      v36 = v96;
      while ( 1 )
      {
        v82 = v34;
        if ( v34 == (struct winrt::impl::shared_hstring_header **)v35 )
          break;
        if ( (unsigned __int64)v34[3] <= 7 )
          v37 = (struct winrt::impl::shared_hstring_header *)v34;
        else
          v37 = *v34;
        v38 = v34[2];
        if ( (_DWORD)v38 )
        {
          v39 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v38, v33);
          v11 = v39;
          v40 = 2LL * (unsigned int)v38;
          if ( v40 )
          {
            v41 = (char *)v39 + 28;
            if ( v39 != (struct winrt::impl::shared_hstring_header *)-28LL )
            {
              if ( v37 )
              {
                memcpy_0(v41, v37, v40);
                goto LABEL_62;
              }
              memset_0(v41, 0, v40);
            }
            *(_DWORD *)_o__errno(v41, v33) = 22;
            invalid_parameter_noinfo();
          }
        }
LABEL_62:
        v92 = v11;
        v42 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xC, v33);
        v44 = v42;
        v45 = (_OWORD *)((char *)v42 + 28);
        v11 = 0;
        if ( v42 == (struct winrt::impl::shared_hstring_header *)-28LL )
        {
          *(_DWORD *)_o__errno(v45, v43) = 22;
          invalid_parameter_noinfo();
        }
        else
        {
          *v45 = *(_OWORD *)L"AgentSession";
          *(_QWORD *)((char *)v42 + 44) = *(_QWORD *)L"sion";
        }
        v93[0] = v44;
        v46 = a2[2];
        v47 = a2;
        if ( a2[3] > 7u )
          v47 = (_QWORD *)*a2;
        if ( (_DWORD)v46 )
        {
          v48 = (unsigned int)v46;
          if ( *((_WORD *)v47 + (unsigned int)v46) )
            goto LABEL_103;
          LODWORD(v90[0]) = 1;
          HIDWORD(v90[0]) = v46;
          v91 = (struct winrt::impl::shared_hstring_header ***)v47;
          v89 = (int **)v90;
        }
        else
        {
          v89 = 0;
          v48 = 0;
        }
        if ( a2[3] <= 7u )
          v49 = a2;
        else
          v49 = (_QWORD *)*a2;
        if ( (_DWORD)v46 )
        {
          if ( *((_WORD *)v49 + v48) )
            goto LABEL_103;
          v100 = 1;
          v101 = v46;
          v102 = v49;
          v99 = &v100;
        }
        else
        {
          v99 = 0;
        }
        v8 = a1;
        v50 = *(_QWORD *)(a1 + 16);
        if ( *(_QWORD *)(a1 + 24) <= 7u )
          v51 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))a1;
        else
          v51 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 **))a1;
        if ( (_DWORD)v50 )
        {
          if ( *((_WORD *)v51 + (unsigned int)v50) )
LABEL_103:
            abort();
          v86 = 1;
          v87 = v50;
          v88 = v51;
          v85 = &v86;
        }
        else
        {
          v85 = 0;
        }
        v94 = (int *)&v92;
        v95 = 1;
        v96 = v36;
        v103[0] = &v85;
        v103[1] = &v99;
        v103[2] = &v89;
        v103[3] = &v94;
        lpMem = &qword_1800B9028;
        _InterlockedAdd64(&qword_1800B9028, 1u);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics> )
        {
          v52 = `winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager::CheckAccessForUserSID'::`2'::_lambda_1_::operator()(
                  v103,
                  (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>);
          _InterlockedDecrement64(&qword_1800B9028);
        }
        else
        {
          _InterlockedDecrement64(&qword_1800B9028);
          v52 = ___call_AEAV_lambda_1___1__CheckAccessForUserSID_McpAccessManager_Mcp_Agents_AI_Internal_Windows_winrt__SA_AEBUhstring_param_9_00U__array_view___CBUMcpResourceRequestInfo_Mcp_Agents_AI_Internal_Windows_winrt___9__Z____factory_cache_entry_UMcpAccessManager_Mcp_Agents_AI_Internal_Windows_winrt__UIMcpAccessManagerStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CheckAccessForUserSID_McpAccessManager_Mcp_Agents_AI_Internal_Windows_2_SA_AEBUhstring_param_2_00U__array_view___CBUMcpResourceRequestInfo_Mcp_Agents_AI_Internal_Windows_winrt___2__Z__Z(
                  v51,
                  (__int64)v103);
        }
        if ( v52 )
        {
          v53 = L"UserPromptRequired";
          if ( v52 != 1 )
            v53 = L"Denied";
        }
        else
        {
          v53 = L"Allowed";
        }
        if ( v93[0] )
          v54 = *(const WCHAR **)(v93[0] + 16LL);
        else
          v54 = &word_180096C4C;
        if ( v92 )
          v55 = (const WCHAR *)*((_QWORD *)v92 + 2);
        else
          v55 = &word_180096C4C;
        LODWORD(v77) = v52;
        Log(4u, L" - CheckAccess Op='%s' Res='%s' => %d (%s)", v55, v54, v77, v53);
        if ( v52 == 1 )
        {
          if ( *((_QWORD *)&v80 + 1) == v81 )
          {
            std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::_Emplace_reallocate<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(
              (winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo **)&v80,
              *((char **)&v80 + 1),
              (__int64)&v92);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>>::construct<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(
              v56,
              *((struct winrt::impl::shared_hstring_header ***)&v80 + 1),
              &v92);
            *((_QWORD *)&v80 + 1) += 16LL;
          }
        }
        winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo::~McpResourceRequestInfo((winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo *)&v92);
        v34 = v82 + 4;
        v35 = v78;
      }
      v57 = (int *)v80;
      if ( (_QWORD)v80 == *((_QWORD *)&v80 + 1) )
        goto LABEL_150;
      v58 = (__int64)(*((_QWORD *)&v80 + 1) - v80) >> 4;
      Log(4u, L"DoesUserConsent: Array of size %u sent to RequestAccessForUserSIDAsync:", (unsigned int)v58);
      v60 = (_QWORD *)*((_QWORD *)&v80 + 1);
      for ( i = (_QWORD *)v80; i != v60; i += 2 )
      {
        v61 = i[1];
        if ( v61 )
          v62 = *(const WCHAR **)(v61 + 16);
        else
          v62 = &word_180096C4C;
        if ( *i )
          v63 = *(const WCHAR **)(*i + 16LL);
        else
          v63 = &word_180096C4C;
        Log(4u, L" - Capability Op='%s' Res='%s'", v63, v62);
      }
      v64 = (const wchar_t *)a3;
      if ( *(_QWORD *)(a3 + 24) > 7u )
        v64 = *(const wchar_t **)a3;
      v103[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&lpMem, v64);
      v82 = 0;
      v92 = 0;
      v65 = a2[2];
      v66 = a2;
      if ( a2[3] > 7u )
        v66 = (_QWORD *)*a2;
      if ( !(_DWORD)v65 )
      {
        v89 = 0;
        v67 = 0;
        goto LABEL_122;
      }
      v67 = (unsigned int)v65;
      if ( *((_WORD *)v66 + (unsigned int)v65) )
        goto LABEL_147;
      LODWORD(v90[0]) = 1;
      HIDWORD(v90[0]) = v65;
      v91 = (struct winrt::impl::shared_hstring_header ***)v66;
      v89 = (int **)v90;
LABEL_122:
      if ( a2[3] <= 7u )
        v68 = a2;
      else
        v68 = (_QWORD *)*a2;
      if ( !(_DWORD)v65 )
      {
        v99 = 0;
        goto LABEL_129;
      }
      if ( *((_WORD *)v68 + v67) )
        goto LABEL_147;
      v100 = 1;
      v101 = v65;
      v102 = v68;
      v99 = &v100;
LABEL_129:
      v8 = a1;
      v69 = *(_QWORD *)(a1 + 16);
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v70 = (void (__fastcall **)(_QWORD, __int64 *, __int64 **))a1;
      else
        v70 = *(void (__fastcall ***)(_QWORD, __int64 *, __int64 **))a1;
      if ( !(_DWORD)v69 )
      {
        v85 = 0;
        goto LABEL_136;
      }
      if ( *((_WORD *)v70 + (unsigned int)v69) )
LABEL_147:
        abort();
      v86 = 1;
      v87 = v69;
      v88 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v70;
      v85 = &v86;
LABEL_136:
      v94 = v57;
      v95 = v58;
      v71 = winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager::RequestAccessForUserSIDAsync(
              (unsigned int)&v78,
              a4,
              (unsigned int)&v85,
              (unsigned int)&v99,
              (__int64)&v89,
              (__int64)&v92,
              (__int64)&v82,
              (__int64)v103,
              (__int64)&v94);
      v72 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,enum winrt::Windows::Internal::AI::Agents::Mcp::McpAccessStatus>::get(v71);
      if ( v78 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
      if ( v92 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
      if ( v82 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
      v73 = lpMem;
      if ( lpMem )
      {
        v74 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v74 )
        {
          if ( v74 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v73);
        }
      }
      if ( !v72 )
      {
LABEL_150:
        GrantedCapabilities = AgentAccountHelpers::QueryGrantedCapabilities(v8, a2, a6);
        std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::~vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>((__int64)&v80);
        return GrantedCapabilities;
      }
      else
      {
        AgentAccountHelpers::QueryGrantedCapabilities(a1, a2, a6);
        std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::~vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>((__int64)&v80);
        return 2147942405LL;
      }
    }
LABEL_151:
    abort();
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x370,
                           (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x180043484  mov     rax, rsp
0x180043487  mov     [rax+10h], rbx
0x18004348b  mov     [rax+20h], rsi
0x18004348f  mov     [rax+18h], r8
0x180043493  mov     [rax+8], rcx
0x180043497  push    rdi
0x180043498  push    r12
0x18004349a  push    r13
0x18004349c  push    r14
0x18004349e  push    r15
0x1800434a0  sub     rsp, 160h
0x1800434a7  mov     rdi, r9
0x1800434aa  mov     r12, rdx
0x1800434ad  mov     r14, rcx
0x1800434b0  mov     r15, [rsp+188h+arg_28]
0x1800434b8  mov     rsi, [r15+8]
0x1800434bc  mov     rbx, [r15]
0x1800434bf  cmp     rbx, rsi
0x1800434c2  jz      short loc_1800434DC
0x1800434c4  mov     rcx, rbx
0x1800434c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800434cc  add     rbx, 20h ; ' '
0x1800434d0  cmp     rbx, rsi
0x1800434d3  jnz     short loc_1800434C4
0x1800434d5  mov     rax, [r15]
0x1800434d8  mov     [r15+8], rax
0x1800434dc  xorps   xmm0, xmm0
0x1800434df  movdqu  [rsp+188h+var_128], xmm0
0x1800434e5  xor     r15d, r15d
0x1800434e8  mov     [rsp+188h+var_118], r15
0x1800434ed  lea     rdx, aDoesuserconsen; "DoesUserConsent: Beginning CheckAccessF"...
0x1800434f4  lea     esi, [r15+4]
0x1800434f8  mov     ecx, esi; unsigned __int8
0x1800434fa  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800434ff  lea     ecx, [rsi+5]; this
0x180043502  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180043507  mov     rbx, rax
0x18004350a  lea     rcx, [rax+1Ch]
0x18004350e  test    rcx, rcx
0x180043511  jnz     short loc_180043526
0x180043513  call    cs:__imp__o__errno
0x180043519  mov     dword ptr [rax], 16h
0x18004351f  call    _invalid_parameter_noinfo
0x180043524  jmp     short loc_18004353B
0x180043526  movups  xmm0, xmmword ptr cs:aProvision; "Provision"
0x18004352d  movups  xmmword ptr [rcx], xmm0
0x180043530  movzx   eax, word ptr cs:aProvision+10h; "n"
0x180043537  mov     [rcx+10h], ax
0x18004353b  mov     [rsp+188h+var_138], rbx
0x180043540  mov     ecx, 0Ch; this
0x180043545  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004354a  mov     rbx, rax
0x18004354d  lea     rcx, [rax+1Ch]
0x180043551  test    rcx, rcx
0x180043554  jnz     short loc_180043569
0x180043556  call    cs:__imp__o__errno
0x18004355c  mov     dword ptr [rax], 16h
0x180043562  call    _invalid_parameter_noinfo
0x180043567  jmp     short loc_180043580
0x180043569  movaps  xmm0, xmmword ptr cs:aAgentsession; "AgentSession"
0x180043570  movups  xmmword ptr [rcx], xmm0
0x180043573  movsd   xmm1, qword ptr cs:aAgentsession+10h; "sion"
0x18004357b  movsd   qword ptr [rcx+10h], xmm1
0x180043580  mov     [rsp+188h+var_130], rbx
0x180043585  mov     rax, [r12+10h]
0x18004358a  mov     rcx, r12
0x18004358d  cmp     qword ptr [r12+18h], 7
0x180043593  jbe     short loc_180043599
0x180043595  mov     rcx, [r12]
0x180043599  test    eax, eax
0x18004359b  jnz     short loc_1800435AE
0x18004359d  mov     [rsp+188h+var_F8], r15
0x1800435a5  mov     rdx, r15
0x1800435a8  lea     r13d, [rax+1]
0x1800435ac  jmp     short loc_1800435E8
0x1800435ae  mov     edx, eax
0x1800435b0  cmp     [rcx+rdx*2], r15w
0x1800435b5  jnz     loc_180043E82
0x1800435bb  mov     r13d, 1
0x1800435c1  mov     [rsp+188h+var_F0], r13d
0x1800435c9  mov     [rsp+188h+var_EC], eax
0x1800435d0  mov     [rsp+188h+var_E0], rcx
0x1800435d8  lea     rcx, [rsp+188h+var_F0]
0x1800435e0  mov     [rsp+188h+var_F8], rcx
0x1800435e8  cmp     qword ptr [r12+18h], 7
0x1800435ee  jbe     short loc_1800435F6
0x1800435f0  mov     rcx, [r12]
0x1800435f4  jmp     short loc_1800435F9
0x1800435f6  mov     rcx, r12
0x1800435f9  test    eax, eax
0x1800435fb  jnz     short loc_180043607
0x1800435fd  mov     [rsp+188h+var_B8], r15
0x180043605  jmp     short loc_180043639
0x180043607  cmp     [rcx+rdx*2], r15w
0x18004360c  jnz     loc_180043E82
0x180043612  mov     dword ptr [rsp+188h+var_B0], r13d
0x18004361a  mov     dword ptr [rsp+188h+var_B0+4], eax
0x180043621  mov     [rsp+188h+var_A0], rcx
0x180043629  lea     rax, [rsp+188h+var_B0]
0x180043631  mov     [rsp+188h+var_B8], rax
0x180043639  mov     rdx, [r14+10h]
0x18004363d  cmp     qword ptr [r14+18h], 7
0x180043642  jbe     short loc_180043649
0x180043644  mov     rcx, [r14]
0x180043647  jmp     short loc_18004364C
0x180043649  mov     rcx, r14
0x18004364c  test    edx, edx
0x18004364e  jnz     short loc_18004365A
0x180043650  mov     [rsp+188h+var_98], r15
0x180043658  jmp     short loc_18004368E
0x18004365a  mov     eax, edx
0x18004365c  cmp     [rcx+rax*2], r15w
0x180043661  jnz     loc_180043E82
0x180043667  mov     [rsp+188h+var_90], r13d
0x18004366f  mov     [rsp+188h+var_8C], edx
0x180043676  mov     [rsp+188h+var_80], rcx
0x18004367e  lea     rax, [rsp+188h+var_90]
0x180043686  mov     [rsp+188h+var_98], rax
0x18004368e  lea     rax, [rsp+188h+var_138]
0x180043693  mov     [rsp+188h+var_108], rax
0x18004369b  mov     [rsp+188h+var_100], r13d
0x1800436a3  mov     eax, [rsp+188h+var_8C]
0x1800436aa  mov     [rsp+188h+var_FC], eax
0x1800436b1  lea     rax, [rsp+188h+var_98]
0x1800436b9  mov     [rsp+188h+var_D8], rax
0x1800436c1  lea     rax, [rsp+188h+var_B8]
0x1800436c9  mov     [rsp+188h+var_D0], rax
0x1800436d1  lea     rax, [rsp+188h+var_F8]
0x1800436d9  mov     [rsp+188h+var_C8], rax
0x1800436e1  lea     rax, [rsp+188h+var_108]
0x1800436e9  mov     [rsp+188h+var_C0], rax
0x1800436f1  lea     rax, qword_1800B9028
0x1800436f8  mov     [rsp+188h+lpMem], rax
0x180043700  lock add cs:qword_1800B9028, r13
0x180043708  cmp     cs:??$factory_cache_entry_v@UMcpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@UIMcpAccessManagerStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UMcpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@UIMcpAccessManagerStatics@234567@@12@A, r15; factory_cache_entry<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>
0x18004370f  jz      short loc_180043731
0x180043711  lea     rdx, ??$factory_cache_entry_v@UMcpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@UIMcpAccessManagerStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UMcpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@UIMcpAccessManagerStatics@234567@@12@A; factory_cache_entry<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager,winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics>
0x180043718  lea     rcx, [rsp+188h+var_D8]
0x180043720  call    ??R_lambda_1_@?1??CheckAccessForUserSID@McpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@SA@AEBUhstring@param@8@00U?$array_view@$$CBUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@8@@Z@QEBA@AEBUIMcpAccessManagerStatics@345678@@Z; `winrt::Windows::Internal::AI::Agents::Mcp::McpAccessManager::CheckAccessForUserSID(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::array_view<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const>)'::`2'::_lambda_1_::operator()(winrt::Windows::Internal::AI::Agents::Mcp::IMcpAccessManagerStatics const &)
0x180043725  mov     ebx, eax
0x180043727  lock dec cs:qword_1800B9028
0x18004372f  jmp     short loc_180043748
0x180043731  lock dec cs:qword_1800B9028
0x180043739  lea     rdx, [rsp+188h+var_D8]
0x180043741  call    ??$call@AEAV_lambda_1_@?1??CheckAccessForUserSID@McpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@SA@AEBUhstring@param@9@00U?$array_view@$$CBUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@9@@Z@@?$factory_cache_entry@UMcpAccessManager@Mcp@Agents@AI@Internal@Windows@winrt@@UIMcpAccessManagerStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CheckAccessForUserSID@McpAccessManager@Mcp@Agents@AI@Internal@Windows@2@SA@AEBUhstring@param@2@00U?$array_view@$$CBUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@2@@Z@@Z
0x180043746  mov     ebx, eax
0x180043748  test    ebx, ebx
0x18004374a  jnz     short loc_180043755
0x18004374c  lea     rax, aAllowed; "Allowed"
0x180043753  jmp     short loc_18004376A
0x180043755  lea     rax, aUserpromptrequ; "UserPromptRequired"
0x18004375c  lea     rdx, aDenied; "Denied"
0x180043763  cmp     ebx, r13d
0x180043766  cmovnz  rax, rdx
0x18004376a  mov     rcx, [rsp+188h+var_130]
0x18004376f  test    rcx, rcx
0x180043772  jz      short loc_18004377A
0x180043774  mov     r9, [rcx+10h]
0x180043778  jmp     short loc_180043781
0x18004377a  lea     r9, word_180096C4C
0x180043781  mov     rcx, [rsp+188h+var_138]
0x180043786  test    rcx, rcx
0x180043789  jz      short loc_180043791
0x18004378b  mov     r8, [rcx+10h]
0x18004378f  jmp     short loc_180043798
0x180043791  lea     r8, word_180096C4C
0x180043798  mov     [rsp+188h+var_160], rax
0x18004379d  mov     dword ptr [rsp+188h+var_168], ebx
0x1800437a1  lea     rdx, aCheckaccessOpS; " - CheckAccess Op='%s' Res='%s' => %d ("...
0x1800437a8  mov     ecx, esi; unsigned __int8
0x1800437aa  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800437af  cmp     ebx, r13d
0x1800437b2  jnz     short loc_1800437DE
0x1800437b4  mov     rdx, qword ptr [rsp+188h+var_128+8]
0x1800437b9  lea     r8, [rsp+188h+var_138]
0x1800437be  cmp     rdx, [rsp+188h+var_118]
0x1800437c3  jz      short loc_1800437D2
0x1800437c5  call    ??$construct@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@AEBU1234567@@?$_Default_allocator_traits@V?$allocator@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@std@@@std@@SAXAEAV?$allocator@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@1@QEAUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@AEBU3456789@@Z; std::_Default_allocator_traits<std::allocator<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>>::construct<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(std::allocator<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo> &,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo * const,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &)
0x1800437ca  add     qword ptr [rsp+188h+var_128+8], 10h
0x1800437d0  jmp     short loc_180043801
0x1800437d2  lea     rcx, [rsp+188h+var_128]
0x1800437d7  call    ??$_Emplace_reallocate@AEBUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@?$vector@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@V?$allocator@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@std@@@std@@AEAAPEAUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@QEAU2345678@AEBU2345678@@Z; std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::_Emplace_reallocate<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &>(winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo * const,winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo const &)
0x1800437dc  jmp     short loc_180043801
0x1800437de  test    ebx, ebx
0x1800437e0  jz      short loc_180043801
0x1800437e2  lea     rcx, [rsp+188h+var_138]; this
0x1800437e7  call    ??1McpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo::~McpResourceRequestInfo(void)
0x1800437ec  nop
0x1800437ed  lea     rcx, [rsp+188h+var_128]
0x1800437f2  call    ??1?$vector@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@V?$allocator@UMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>::~vector<winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo>(void)
0x1800437f7  mov     eax, 80070005h
0x1800437fc  jmp     loc_180043E90
0x180043801  lea     rcx, [rsp+188h+var_138]; this
0x180043806  call    ??1McpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo::~McpResourceRequestInfo(void)
0x18004380b  mov     rax, [rsp+188h+arg_20]
0x180043813  mov     rcx, [rax]
0x180043816  mov     rax, [rax+8]
0x18004381a  mov     [rsp+188h+var_138], rax
0x18004381f  mov     ebx, [rsp+188h+var_8C]
0x180043826  mov     [rsp+188h+var_108], rcx
0x18004382e  cmp     rcx, rax
0x180043831  jz      loc_180043B6B
0x180043837  cmp     qword ptr [rcx+18h], 7
0x18004383c  jbe     short loc_180043843
0x18004383e  mov     r14, [rcx]
0x180043841  jmp     short loc_180043846
0x180043843  mov     r14, rcx
0x180043846  mov     rsi, [rcx+10h]
0x18004384a  test    esi, esi
0x18004384c  jz      short loc_180043890
0x18004384e  mov     ecx, esi; this
0x180043850  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180043855  mov     r15, rax
0x180043858  mov     r8d, esi
0x18004385b  add     r8, r8; Size
0x18004385e  jz      short loc_180043890
0x180043860  lea     rcx, [rax+1Ch]; void *
0x180043864  test    rcx, rcx
0x180043867  jz      short loc_18004387F
0x180043869  test    r14, r14
0x18004386c  jz      short loc_180043878
0x18004386e  mov     rdx, r14; Src
0x180043871  call    memcpy_0
0x180043876  jmp     short loc_180043890
0x180043878  xor     edx, edx; Val
0x18004387a  call    memset_0
0x18004387f  call    cs:__imp__o__errno
0x180043885  mov     dword ptr [rax], 16h
0x18004388b  call    _invalid_parameter_noinfo
0x180043890  mov     [rsp+188h+var_B8], r15
0x180043898  mov     ecx, 0Ch; this
0x18004389d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800438a2  mov     rsi, rax
0x1800438a5  lea     rcx, [rax+1Ch]
0x1800438a9  xor     r15d, r15d
0x1800438ac  test    rcx, rcx
0x1800438af  jnz     short loc_1800438C4
0x1800438b1  call    cs:__imp__o__errno
0x1800438b7  mov     dword ptr [rax], 16h
0x1800438bd  call    _invalid_parameter_noinfo
0x1800438c2  jmp     short loc_1800438DB
0x1800438c4  movaps  xmm0, xmmword ptr cs:aAgentsession; "AgentSession"
0x1800438cb  movups  xmmword ptr [rcx], xmm0
0x1800438ce  movsd   xmm1, qword ptr cs:aAgentsession+10h; "sion"
0x1800438d6  movsd   qword ptr [rcx+10h], xmm1
0x1800438db  mov     [rsp+188h+var_B0], rsi
0x1800438e3  mov     rcx, [r12+10h]
0x1800438e8  mov     rax, r12
0x1800438eb  cmp     qword ptr [r12+18h], 7
0x1800438f1  jbe     short loc_1800438F7
0x1800438f3  mov     rax, [r12]
0x1800438f7  test    ecx, ecx
0x1800438f9  jnz     short loc_180043908
0x1800438fb  mov     [rsp+188h+var_D8], r15
0x180043903  mov     rdx, r15
0x180043906  jmp     short loc_18004393C
0x180043908  mov     edx, ecx
0x18004390a  cmp     [rax+rdx*2], r15w
0x18004390f  jnz     loc_180043B64
0x180043915  mov     dword ptr [rsp+188h+var_D0], r13d
0x18004391d  mov     dword ptr [rsp+188h+var_D0+4], ecx
0x180043924  mov     [rsp+188h+var_C0], rax
0x18004392c  lea     rax, [rsp+188h+var_D0]
0x180043934  mov     [rsp+188h+var_D8], rax
0x18004393c  cmp     qword ptr [r12+18h], 7
0x180043942  jbe     short loc_18004394A
0x180043944  mov     rax, [r12]
0x180043948  jmp     short loc_18004394D
0x18004394a  mov     rax, r12
0x18004394d  test    ecx, ecx
0x18004394f  jnz     short loc_18004395B
0x180043951  mov     [rsp+188h+var_70], r15
0x180043959  jmp     short loc_18004398D
0x18004395b  cmp     [rax+rdx*2], r15w
0x180043960  jnz     loc_180043B64
0x180043966  mov     [rsp+188h+var_68], r13d
0x18004396e  mov     [rsp+188h+var_64], ecx
0x180043975  mov     [rsp+188h+var_58], rax
0x18004397d  lea     rax, [rsp+188h+var_68]
0x180043985  mov     [rsp+188h+var_70], rax
0x18004398d  mov     r14, [rsp+188h+arg_0]
0x180043995  mov     rdx, [r14+10h]
0x180043999  cmp     qword ptr [r14+18h], 7
0x18004399e  jbe     short loc_1800439A5
0x1800439a0  mov     rcx, [r14]
0x1800439a3  jmp     short loc_1800439A8
0x1800439a5  mov     rcx, r14
0x1800439a8  test    edx, edx
0x1800439aa  jnz     short loc_1800439B6
0x1800439ac  mov     [rsp+188h+var_F8], r15
0x1800439b4  jmp     short loc_1800439EA
0x1800439b6  mov     eax, edx
0x1800439b8  cmp     [rcx+rax*2], r15w
0x1800439bd  jnz     loc_180043B64
0x1800439c3  mov     [rsp+188h+var_F0], r13d
0x1800439cb  mov     [rsp+188h+var_EC], edx
0x1800439d2  mov     [rsp+188h+var_E0], rcx
0x1800439da  lea     rax, [rsp+188h+var_F0]
0x1800439e2  mov     [rsp+188h+var_F8], rax
0x1800439ea  lea     rax, [rsp+188h+var_B8]
  ... truncated ...
```
