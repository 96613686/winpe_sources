# CDsmCore::_WaitForCtaUpdateSettings(bool *,bool *)

- ea: `0x180024814`
- end: `0x180024b7b`
- name: `?_WaitForCtaUpdateSettings@CDsmCore@@AEAAJPEA_N0@Z`
- size: `871`
- prototype: `__int64 __fastcall(CDsmCore *__hidden this, bool *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800238e8`

## callees

- `0x180010b08`
- `0x180010eb8`
- `0x1800112a4`
- `0x180021790`
- `0x180022b24`
- `0x18002380c`
- `0x180024814`
- `0x180024d58`
- `0x180025074`
- `0x18003ee58`
- `0x18003ef40`
- `0x18003f098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249c7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002495a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002495a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800249ab`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800249ab`

## string_xrefs

- `0x180024850`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x180024884`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x1800248cc`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x1800249e4`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x180024a9e`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x180024abd`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`
- `0x1800249d5`: `Failed to wait for CTA auto update settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDsmCore::_WaitForCtaUpdateSettings(CDsmCore *this, bool *a2, bool *a3)
{
  int StoreWuKey; // eax
  unsigned int v6; // ebx
  int WuSettingsKey; // eax
  int v8; // eax
  HANDLE v9; // rbx
  PVOID *v10; // rcx
  int v11; // eax
  int v12; // edi
  unsigned int v13; // eax
  DWORD v14; // eax
  DWORD LastError; // eax
  unsigned int v16; // eax
  bool v18; // bl
  bool v19; // di
  const wchar_t *v20; // r9
  const wchar_t *v21; // rax
  unsigned int fAsynchronous; // [rsp+20h] [rbp-40h]
  const char *v23; // [rsp+28h] [rbp-38h]
  HKEY phkResult; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hEvent; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  CDsmCore *v29; // [rsp+90h] [rbp+30h] BYREF
  bool v30; // [rsp+A8h] [rbp+48h] BYREF

  v29 = this;
  hKey = 0;
  StoreWuKey = GetStoreWuKey(&hKey);
  v6 = StoreWuKey;
  if ( StoreWuKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
      (const char *)(unsigned int)StoreWuKey,
      fAsynchronous);
LABEL_36:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  phkResult = 0;
  WuSettingsKey = GetWuSettingsKey(&phkResult);
  v6 = WuSettingsKey;
  if ( WuSettingsKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x359,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
      (const char *)(unsigned int)WuSettingsKey,
      fAsynchronous);
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    goto LABEL_36;
  }
  LOBYTE(v29) = 0;
  v30 = 0;
  hEvent = 0;
  v8 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hEvent,
         0);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
      (const char *)(unsigned int)v8,
      fAsynchronous);
LABEL_8:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
    goto LABEL_5;
  }
  v9 = hEvent;
LABEL_10:
  while ( 2 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_(v10[2], 34, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
    while ( 1 )
    {
      v11 = QueryCtaAutoUpdatesEnabled(hKey, (bool *)&v29, phkResult, &v30);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v18 = (char)v29;
        v19 = v30;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = L"is";
          v21 = L"is";
          if ( !v30 )
            v21 = L"is NOT";
          if ( !(_BYTE)v29 )
            v20 = L"is NOT";
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
            (_DWORD)v20,
            (__int64)v21);
        }
        *a2 = v18;
        *a3 = v19;
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      if ( v11 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36E,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
          (const char *)(unsigned int)v11,
          fAsynchronous);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v6 = v12;
        goto LABEL_36;
      }
      v13 = RegNotifyChangeKeyValue(hKey, 0, 4u, v9, 1);
      if ( v13 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x378,
                (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
                (const char *)v13,
                fAsynchronous);
LABEL_34:
        v6 = v16;
        goto LABEL_8;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
      Handles[0] = v9;
      Handles[1] = hHandle;
      v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v14 )
        break;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
        goto LABEL_10;
      }
    }
    if ( v14 != 1 )
    {
      if ( v14 != -1 )
        continue;
      LastError = GetLastError();
      if ( !LastError )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v6 = 0;
        goto LABEL_36;
      }
      v16 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x38C,
              (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
              (const char *)LastError,
              (unsigned int)"Failed to wait for CTA auto update settings",
              v23);
      goto LABEL_34;
    }
    break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 2147500036LL;
}

```

## disassembly

```asm
0x180024814  mov     [rsp-28h+arg_8], rbx
0x180024819  mov     [rsp-28h+arg_0], rcx
0x18002481e  push    rbp
0x18002481f  push    rsi
0x180024820  push    rdi
0x180024821  push    r13
0x180024823  push    r14
0x180024825  mov     rbp, rsp
0x180024828  sub     rsp, 60h
0x18002482c  mov     rsi, r8
0x18002482f  mov     r14, rdx
0x180024832  mov     [rbp+hKey], 0
0x18002483a  lea     rcx, [rbp+hKey]; phkResult
0x18002483e  call    ?GetStoreWuKey@@YAJPEAPEAUHKEY__@@@Z; GetStoreWuKey(HKEY__ * *)
0x180024843  mov     ebx, eax
0x180024845  test    eax, eax
0x180024847  jns     short loc_180024866
0x180024849  mov     rcx, [rbp+28h]; this
0x18002484d  mov     r9d, eax; char *
0x180024850  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180024857  mov     edx, 357h; void *
0x18002485c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024861  jmp     loc_180024AE4
0x180024866  mov     [rbp+phkResult], 0
0x18002486e  lea     rcx, [rbp+phkResult]; phkResult
0x180024872  call    ?GetWuSettingsKey@@YAJPEAPEAUHKEY__@@@Z; GetWuSettingsKey(HKEY__ * *)
0x180024877  mov     ebx, eax
0x180024879  test    eax, eax
0x18002487b  jns     short loc_1800248A4
0x18002487d  mov     rcx, [rbp+28h]; this
0x180024881  mov     r9d, eax; char *
0x180024884  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002488b  mov     edx, 359h; void *
0x180024890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024895  nop
0x180024896  lea     rcx, [rbp+phkResult]
0x18002489a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002489f  jmp     loc_180024AE4
0x1800248a4  mov     byte ptr [rbp+arg_0], 0
0x1800248a8  mov     [rbp+arg_18], 0
0x1800248ac  mov     [rbp+hEvent], 0
0x1800248b4  xor     edx, edx
0x1800248b6  lea     rcx, [rbp+hEvent]
0x1800248ba  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800248bf  mov     ebx, eax
0x1800248c1  test    eax, eax
0x1800248c3  jns     short loc_1800248E9
0x1800248c5  mov     rcx, [rbp+28h]; this
0x1800248c9  mov     r9d, eax; char *
0x1800248cc  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800248d3  mov     edx, 35Eh; void *
0x1800248d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248dd  nop
0x1800248de  lea     rcx, [rbp+hEvent]
0x1800248e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800248e7  jmp     short loc_180024896
0x1800248e9  lea     r13, WPP_GLOBAL_Control
0x1800248f0  mov     rbx, [rbp+hEvent]
0x1800248f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248fb  cmp     rcx, r13
0x1800248fe  jz      short loc_18002491B
0x180024900  test    byte ptr [rcx+1Ch], 1
0x180024904  jz      short loc_18002491B
0x180024906  mov     edx, 22h ; '"'
0x18002490b  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024912  mov     rcx, [rcx+10h]
0x180024916  call    WPP_SF_
0x18002491b  lea     r9, [rbp+arg_18]; bool *
0x18002491f  mov     r8, [rbp+phkResult]; HKEY
0x180024923  lea     rdx, [rbp+arg_0]; bool *
0x180024927  mov     rcx, [rbp+hKey]; HKEY
0x18002492b  call    ?QueryCtaAutoUpdatesEnabled@@YAJPEAUHKEY__@@PEA_N01@Z; QueryCtaAutoUpdatesEnabled(HKEY__ *,bool *,HKEY__ *,bool *)
0x180024930  mov     edi, eax
0x180024932  test    eax, eax
0x180024934  jns     loc_180024AF1
0x18002493a  cmp     eax, 80070002h
0x18002493f  jnz     loc_180024AB6
0x180024945  mov     [rsp+60h+fAsynchronous], 1; unsigned int
0x18002494d  mov     r9, rbx; hEvent
0x180024950  xor     edx, edx; bWatchSubtree
0x180024952  lea     r8d, [rdx+4]; dwNotifyFilter
0x180024956  mov     rcx, [rbp+hKey]; hKey
0x18002495a  call    cs:__imp_RegNotifyChangeKeyValue
0x180024960  test    eax, eax
0x180024962  jnz     loc_180024A97
0x180024968  mov     rcx, cs:WPP_GLOBAL_Control
0x18002496f  cmp     rcx, r13
0x180024972  jz      short loc_18002498D
0x180024974  test    byte ptr [rcx+1Ch], 1
0x180024978  jz      short loc_18002498D
0x18002497a  lea     edx, [rax+23h]
0x18002497d  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024984  mov     rcx, [rcx+10h]
0x180024988  call    WPP_SF_
0x18002498d  mov     [rbp+Handles], rbx
0x180024991  mov     rax, cs:hHandle
0x180024998  mov     [rbp+var_10], rax
0x18002499c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800249a0  xor     r8d, r8d; bWaitAll
0x1800249a3  lea     rdx, [rbp+Handles]; lpHandles
0x1800249a7  lea     ecx, [r8+2]; nCount
0x1800249ab  call    cs:__imp_WaitForMultipleObjects
0x1800249b1  test    eax, eax
0x1800249b3  jz      short loc_1800249FA
0x1800249b5  cmp     eax, 1
0x1800249b8  jz      loc_180024A48
0x1800249be  cmp     eax, 0FFFFFFFFh
0x1800249c1  jnz     loc_1800248F4
0x1800249c7  call    cs:__imp_GetLastError
0x1800249cd  test    eax, eax
0x1800249cf  jz      short loc_180024A2E
0x1800249d1  mov     rcx, [rbp+28h]; this
0x1800249d5  lea     rdx, aFailedToWaitFo; "Failed to wait for CTA auto update sett"...
0x1800249dc  mov     qword ptr [rsp+60h+fAsynchronous], rdx; unsigned int
0x1800249e1  mov     r9d, eax; char *
0x1800249e4  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800249eb  mov     edx, 38Ch; void *
0x1800249f0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800249f5  jmp     loc_180024AAF
0x1800249fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a01  cmp     rcx, r13
0x180024a04  jz      loc_18002491B
0x180024a0a  test    byte ptr [rcx+1Ch], 1
0x180024a0e  jz      loc_1800248FB
0x180024a14  mov     edx, 24h ; '$'
0x180024a19  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024a20  mov     rcx, [rcx+10h]
0x180024a24  call    WPP_SF_
0x180024a29  jmp     loc_1800248F4
0x180024a2e  lea     rcx, [rbp+hEvent]
0x180024a32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024a37  nop
0x180024a38  lea     rcx, [rbp+phkResult]
0x180024a3c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024a41  xor     ebx, ebx
0x180024a43  jmp     loc_180024AE4
0x180024a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a4f  cmp     rcx, r13
0x180024a52  jz      short loc_180024A70
0x180024a54  test    byte ptr [rcx+1Ch], 4
0x180024a58  jz      short loc_180024A70
0x180024a5a  mov     edx, 25h ; '%'
0x180024a5f  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024a66  mov     rcx, [rcx+10h]
0x180024a6a  call    WPP_SF_
0x180024a6f  nop
0x180024a70  lea     rcx, [rbp+hEvent]
0x180024a74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024a79  nop
0x180024a7a  lea     rcx, [rbp+phkResult]
0x180024a7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024a83  nop
0x180024a84  lea     rcx, [rbp+hKey]
0x180024a88  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024a8d  mov     eax, 80004004h
0x180024a92  jmp     loc_180024B67
0x180024a97  mov     rcx, [rbp+28h]; this
0x180024a9b  mov     r9d, eax; char *
0x180024a9e  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180024aa5  mov     edx, 378h; void *
0x180024aaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180024aaf  mov     ebx, eax
0x180024ab1  jmp     loc_1800248DE
0x180024ab6  mov     rcx, [rbp+28h]; this
0x180024aba  mov     r9d, edi; char *
0x180024abd  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180024ac4  mov     edx, 36Eh; void *
0x180024ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024ace  nop
0x180024acf  lea     rcx, [rbp+hEvent]
0x180024ad3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024ad8  nop
0x180024ad9  lea     rcx, [rbp+phkResult]
0x180024add  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024ae2  mov     ebx, edi
0x180024ae4  lea     rcx, [rbp+hKey]
0x180024ae8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024aed  mov     eax, ebx
0x180024aef  jmp     short loc_180024B67
0x180024af1  mov     bl, byte ptr [rbp+arg_0]
0x180024af4  mov     dil, [rbp+arg_18]
0x180024af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aff  cmp     rcx, r13
0x180024b02  jz      short loc_180024B42
0x180024b04  test    byte ptr [rcx+1Ch], 1
0x180024b08  jz      short loc_180024B42
0x180024b0a  lea     r9, aIs; "is"
0x180024b11  mov     rax, r9
0x180024b14  lea     rdx, aIsNot; "is NOT"
0x180024b1b  test    dil, dil
0x180024b1e  cmovz   rax, rdx
0x180024b22  test    bl, bl
0x180024b24  cmovz   r9, rdx
0x180024b28  mov     edx, 26h ; '&'
0x180024b2d  mov     qword ptr [rsp+60h+fAsynchronous], rax
0x180024b32  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024b39  mov     rcx, [rcx+10h]
0x180024b3d  call    WPP_SF_SS
0x180024b42  mov     [r14], bl
0x180024b45  mov     [rsi], dil
0x180024b48  lea     rcx, [rbp+hEvent]
0x180024b4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024b51  nop
0x180024b52  lea     rcx, [rbp+phkResult]
0x180024b56  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024b5b  nop
0x180024b5c  lea     rcx, [rbp+hKey]
0x180024b60  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024b65  xor     eax, eax
0x180024b67  mov     rbx, [rsp+60h+arg_8]
0x180024b6f  add     rsp, 60h
0x180024b73  pop     r14
0x180024b75  pop     r13
0x180024b77  pop     rdi
0x180024b78  pop     rsi
0x180024b79  pop     rbp
0x180024b7a  retn
```
