# AgentAccountRegistry::GetOrCreateOwningUserRegistry(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18003ca08`
- end: `0x18003cc03`
- name: `?GetOrCreateOwningUserRegistry@AgentAccountRegistry@@QEAAAEAVOwningUserRegistry@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `507`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c4a4`
- `0x180041b64`
- `0x180049750`
- `0x18004b28c`
- `0x1800507a8`
- `0x18005469c`
- `0x180059200`
- `0x18005efe0`
- `0x18005f33c`

## callees

- `0x1800029cc`
- `0x180002ee8`
- `0x1800075e4`
- `0x18001045c`
- `0x1800158dc`
- `0x18002030c`
- `0x18002083c`
- `0x18003b734`
- `0x18003b968`
- `0x18003ca08`
- `0x18003dce4`
- `0x18003e03c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ca95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ca95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cbad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cbad`

## string_xrefs

- `0x18003cbd8`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18003cbf1`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AgentAccountRegistry::GetOrCreateOwningUserRegistry(HKEY a1, _QWORD *a2, const wchar_t *a3)
{
  _QWORD *v4; // rdi
  __int64 v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // r9
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // ebx
  const char *v11; // r9
  int v12; // ebx
  const char *v13; // r9
  _QWORD *v14; // r8
  const wchar_t *v15; // r9
  const wchar_t *v16; // r8
  HKEY v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rsi
  _QWORD v21[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  HKEY v24; // [rsp+68h] [rbp+38h] BYREF
  void *v25; // [rsp+78h] [rbp+48h]

  hKey = a1;
  v4 = a2;
  v5 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v6 = 0;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 2 * v5;
  if ( v8 )
  {
    do
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)a2 + v6++) ^ (unsigned __int64)v7);
    while ( v6 < v8 );
  }
  v9 = ____Find_last_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std______Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEBA_AU___Hash_find_last_result_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__K_Z(
         &dword_1800B9468,
         v21,
         (__int64)v4,
         v7)[1];
  if ( !v9 || v9 == qword_1800B9470 )
  {
    v12 = dword_1800B9160;
    if ( v12 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v13);
    if ( v4[3] <= 7u )
      v14 = v4;
    else
      v14 = (_QWORD *)*v4;
    wil::reg::create_unique_key(&hKey, g_agentAccountRegistry, v14);
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v16 = a3;
    else
      v16 = *(const wchar_t **)a3;
    wil::reg::set_value_string((wil::reg *)hKey, (HKEY)&stru_18009E3F8, v16, v15);
    v25 = operator new(0xA8u);
    v24 = hKey;
    hKey = 0;
    v17 = (HKEY)OwningUserRegistry::OwningUserRegistry((__int64)v25, &v24, (__int64)a3);
    v24 = v17;
    v18 = std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(
            (float *)&dword_1800B9468,
            (__int64)v21,
            v4);
    v19 = *(_QWORD *)(*(_QWORD *)v18 + 48LL);
    *(_QWORD *)(*(_QWORD *)v18 + 48LL) = v17;
    if ( v19 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>((char **)(v19 + 128));
      std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v19 + 112);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>((char **)(v19 + 64));
      std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v19 + 48);
      std::wstring::~wstring((char **)(v19 + 8));
      if ( *(_QWORD *)v19 )
        RegCloseKey(*(HKEY *)v19);
      operator delete((void *)v19, (const struct std::nothrow_t *)0xA8);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else if ( dword_1800B9164 <= 0 )
  {
    v10 = dword_1800B9160;
    if ( v10 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v11);
  }
  return *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(
                                  (float *)&dword_1800B9468,
                                  (__int64)v21,
                                  v4)
                   + 48LL);
}

```

## disassembly

```asm
0x18003ca08  mov     [rsp-28h+hKey], rcx
0x18003ca0d  push    rbp
0x18003ca0e  push    rbx
0x18003ca0f  push    rsi
0x18003ca10  push    rdi
0x18003ca11  push    r14
0x18003ca13  mov     rbp, rsp
0x18003ca16  sub     rsp, 30h
0x18003ca1a  mov     rsi, r8
0x18003ca1d  mov     rdi, rdx
0x18003ca20  mov     r8, [rdx+10h]
0x18003ca24  cmp     qword ptr [rdx+18h], 7
0x18003ca29  jbe     short loc_18003CA2E
0x18003ca2b  mov     rdx, [rdx]
0x18003ca2e  xor     ecx, ecx
0x18003ca30  mov     r9, 0CBF29CE484222325h
0x18003ca3a  add     r8, r8
0x18003ca3d  jz      short loc_18003CA5C
0x18003ca3f  movzx   eax, byte ptr [rdx+rcx]
0x18003ca43  xor     r9, rax
0x18003ca46  mov     r10, 100000001B3h
0x18003ca50  imul    r9, r10
0x18003ca54  inc     rcx
0x18003ca57  cmp     rcx, r8
0x18003ca5a  jb      short loc_18003CA3F
0x18003ca5c  mov     r8, rdi
0x18003ca5f  lea     rdx, [rbp+var_10]
0x18003ca63  lea     rcx, dword_1800B9468
0x18003ca6a  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,`MopUpMemUserProfiles(void)'::`3'::ProfileData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`MopUpMemUserProfiles(void)'::`3'::ProfileData>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18003ca6f  mov     rcx, [rax+8]
0x18003ca73  test    rcx, rcx
0x18003ca76  jz      short loc_18003CAA8
0x18003ca78  cmp     rcx, cs:qword_1800B9470
0x18003ca7f  jz      short loc_18003CAA8
0x18003ca81  mov     eax, cs:dword_1800B9164
0x18003ca87  test    eax, eax
0x18003ca89  jg      loc_18003CBB3
0x18003ca8f  mov     ebx, cs:dword_1800B9160
0x18003ca95  call    cs:__imp_GetCurrentThreadId
0x18003ca9b  cmp     ebx, eax
0x18003ca9d  jnz     loc_18003CBED
0x18003caa3  jmp     loc_18003CBB3
0x18003caa8  mov     ebx, cs:dword_1800B9160
0x18003caae  mov     r14, [rbp+28h]
0x18003cab2  call    cs:__imp_GetCurrentThreadId
0x18003cab8  cmp     ebx, eax
0x18003caba  jnz     loc_18003CBD8
0x18003cac0  cmp     qword ptr [rdi+18h], 7
0x18003cac5  jbe     short loc_18003CACC
0x18003cac7  mov     r8, [rdi]
0x18003caca  jmp     short loc_18003CACF
0x18003cacc  mov     r8, rdi
0x18003cacf  mov     rdx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x18003cad6  lea     rcx, [rbp+hKey]
0x18003cada  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18003cadf  nop
0x18003cae0  cmp     qword ptr [rsi+18h], 7
0x18003cae5  jbe     short loc_18003CAEC
0x18003cae7  mov     r8, [rsi]
0x18003caea  jmp     short loc_18003CAEF
0x18003caec  mov     r8, rsi; wchar_t *
0x18003caef  lea     rdx, stru_18009E3F8; HKEY
0x18003caf6  mov     rcx, [rbp+hKey]; this
0x18003cafa  call    ?set_value_string@reg@wil@@YAXPEAUHKEY__@@PEB_W1@Z; wil::reg::set_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x18003caff  mov     r14d, 0A8h
0x18003cb05  mov     ecx, r14d; Size
0x18003cb08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cb0d  mov     [rbp+arg_18], rax
0x18003cb11  mov     rcx, [rbp+hKey]
0x18003cb15  mov     [rbp+arg_8], rcx
0x18003cb19  mov     [rbp+hKey], 0
0x18003cb21  mov     r8, rsi
0x18003cb24  lea     rdx, [rbp+arg_8]
0x18003cb28  mov     rcx, rax
0x18003cb2b  call    ??0OwningUserRegistry@@QEAA@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OwningUserRegistry::OwningUserRegistry(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,std::wstring const &)
0x18003cb30  mov     rbx, rax
0x18003cb33  mov     [rbp+arg_8], rax
0x18003cb37  mov     r8, rdi
0x18003cb3a  lea     rdx, [rbp+var_10]
0x18003cb3e  lea     rcx, dword_1800B9468
0x18003cb45  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003cb4a  mov     rcx, [rax]
0x18003cb4d  mov     rsi, [rcx+30h]
0x18003cb51  mov     [rcx+30h], rbx
0x18003cb55  test    rsi, rsi
0x18003cb58  jz      short loc_18003CBA4
0x18003cb5a  lea     rcx, [rsi+80h]
0x18003cb61  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(void)
0x18003cb66  lea     rcx, [rsi+70h]
0x18003cb6a  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x18003cb6f  lea     rcx, [rsi+40h]
0x18003cb73  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(void)
0x18003cb78  lea     rcx, [rsi+30h]
0x18003cb7c  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x18003cb81  lea     rcx, [rsi+8]
0x18003cb85  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cb8a  mov     rcx, [rsi]; hKey
0x18003cb8d  test    rcx, rcx
0x18003cb90  jz      short loc_18003CB98
0x18003cb92  call    cs:__imp_RegCloseKey
0x18003cb98  mov     rdx, r14; struct std::nothrow_t *
0x18003cb9b  mov     rcx, rsi; void *
0x18003cb9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cba3  nop
0x18003cba4  mov     rcx, [rbp+hKey]; hKey
0x18003cba8  test    rcx, rcx
0x18003cbab  jz      short loc_18003CBB3
0x18003cbad  call    cs:__imp_RegCloseKey
0x18003cbb3  mov     r8, rdi
0x18003cbb6  lea     rdx, [rbp+var_10]
0x18003cbba  lea     rcx, dword_1800B9468
0x18003cbc1  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<OwningUserRegistry>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003cbc6  mov     rax, [rax]
0x18003cbc9  mov     rax, [rax+30h]
0x18003cbcd  add     rsp, 30h
0x18003cbd1  pop     r14
0x18003cbd3  pop     rdi
0x18003cbd4  pop     rsi
0x18003cbd5  pop     rbx
0x18003cbd6  pop     rbp
0x18003cbd7  retn
0x18003cbd8  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003cbdf  mov     edx, 15Dh; void *
0x18003cbe4  mov     rcx, r14; this
0x18003cbe7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003cbed  mov     rcx, [rbp+28h]; this
0x18003cbf1  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003cbf8  mov     edx, 175h; void *
0x18003cbfd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
