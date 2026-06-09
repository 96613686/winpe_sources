# OOBE::Health::details::OOBEScenarioEvents::~OOBEScenarioEvents(void)

- ea: `0x180007278`
- end: `0x18000755d`
- name: `??1OOBEScenarioEvents@details@Health@OOBE@@QEAA@XZ`
- size: `741`
- prototype: `void __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006f10`

## callees

- `0x180007278`
- `0x180012408`
- `0x180018be8`
- `0x18001a980`
- `0x18002253c`
- `0x180024614`
- `0x18002646c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007340`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000742c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007518`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007340`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000742c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007518`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000730e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000730e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074df`

## pseudocode

```c
void __fastcall OOBE::Health::details::OOBEScenarioEvents::~OOBEScenarioEvents(BYTE *lpData)
{
  int RedirectionKeyPath; // eax
  unsigned int v3; // eax
  unsigned int v4; // r8d
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  if ( lpData[201] && lpData[200] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    RedirectionKeyPath = GetRedirectionKeyPath(
                           L"OOBEHealth",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
                           (unsigned __int16 **)&lpSubKey);
    if ( RedirectionKeyPath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        phkResult);
LABEL_11:
      lpData[200] = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      goto LABEL_12;
    }
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v3 )
    {
      v5 = 1074;
    }
    else
    {
      v3 = RegSetValueExW(hKey, L"Health", 0, 3u, lpData, 0xACu);
      if ( !v3 )
      {
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_11;
      }
      v5 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)v5, v4, (const char *)v3, phkResult);
    goto LABEL_10;
  }
LABEL_12:
  if ( lpData[203] && lpData[202] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    v6 = GetRedirectionKeyPath(
           L"OOBEHealth",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
           (unsigned __int16 **)&lpSubKey);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)v6,
        phkResult);
LABEL_22:
      lpData[202] = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      goto LABEL_23;
    }
    hKey = 0;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v7 )
    {
      v9 = 1074;
    }
    else
    {
      v7 = RegSetValueExW(hKey, L"Census", 0, 3u, lpData + 172, 0x10u);
      if ( !v7 )
      {
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_22;
      }
      v9 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)v9, v8, (const char *)v7, phkResult);
    goto LABEL_21;
  }
LABEL_23:
  if ( lpData[205] && lpData[204] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    v10 = GetRedirectionKeyPath(
            L"OOBEHealth",
            L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
            (unsigned __int16 **)&lpSubKey);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)v10,
        phkResult);
LABEL_33:
      lpData[204] = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      return;
    }
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v11 )
    {
      v13 = 1074;
    }
    else
    {
      v11 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, lpData + 188, 0xCu);
      if ( !v11 )
      {
LABEL_32:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_33;
      }
      v13 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)v13, v12, (const char *)v11, phkResulta);
    goto LABEL_32;
  }
}

```

## disassembly

```asm
0x180007278  mov     [rsp-8+arg_10], rbx
0x18000727d  mov     [rsp-8+arg_18], rdi
0x180007282  push    rbp
0x180007283  mov     rbp, rsp
0x180007286  sub     rsp, 30h
0x18000728a  mov     rbx, rcx
0x18000728d  xor     edi, edi
0x18000728f  cmp     [rcx+0C9h], dil
0x180007296  jz      loc_180007374
0x18000729c  cmp     [rcx+0C8h], dil
0x1800072a3  jz      loc_180007374
0x1800072a9  mov     [rbp+lpSubKey], rdi
0x1800072ad  xor     edx, edx
0x1800072af  lea     rcx, [rbp+lpSubKey]
0x1800072b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800072b8  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x1800072bc  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800072c3  lea     rcx, aOobehealth; "OOBEHealth"
0x1800072ca  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800072cf  test    eax, eax
0x1800072d1  jns     short loc_1800072ED
0x1800072d3  mov     rcx, [rbp+8]; this
0x1800072d7  mov     r9d, eax; char *
0x1800072da  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800072e1  mov     edx, 42Fh; void *
0x1800072e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800072eb  jmp     short loc_180007364
0x1800072ed  mov     [rbp+hKey], rdi
0x1800072f1  lea     rax, [rbp+hKey]
0x1800072f5  mov     [rsp+30h+phkResult], rax; phkResult
0x1800072fa  mov     r9d, 0F003Fh; samDesired
0x180007300  xor     r8d, r8d; ulOptions
0x180007303  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180007307  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000730e  call    cs:__imp_RegOpenKeyExW
0x180007314  test    eax, eax
0x180007316  jz      short loc_18000731F
0x180007318  mov     edx, 432h
0x18000731d  jmp     short loc_18000734F
0x18000731f  mov     [rsp+30h+cbData], 0ACh; cbData
0x180007327  mov     [rsp+30h+phkResult], rbx; int
0x18000732c  mov     r9d, 3; dwType
0x180007332  xor     r8d, r8d; Reserved
0x180007335  lea     rdx, ValueName; "Health"
0x18000733c  mov     rcx, [rbp+hKey]; hKey
0x180007340  call    cs:__imp_RegSetValueExW
0x180007346  test    eax, eax
0x180007348  jz      short loc_18000735B
0x18000734a  mov     edx, 435h; void *
0x18000734f  mov     r9d, eax; char *
0x180007352  mov     rcx, [rbp+8]; this
0x180007356  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000735b  lea     rcx, [rbp+hKey]
0x18000735f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007364  mov     [rbx+0C8h], dil
0x18000736b  lea     rcx, [rbp+lpSubKey]
0x18000736f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007374  cmp     [rbx+0CBh], dil
0x18000737b  jz      loc_180007460
0x180007381  cmp     [rbx+0CAh], dil
0x180007388  jz      loc_180007460
0x18000738e  mov     [rbp+lpSubKey], rdi
0x180007392  xor     edx, edx
0x180007394  lea     rcx, [rbp+lpSubKey]
0x180007398  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000739d  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x1800073a1  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800073a8  lea     rcx, aOobehealth; "OOBEHealth"
0x1800073af  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800073b4  test    eax, eax
0x1800073b6  jns     short loc_1800073D2
0x1800073b8  mov     rcx, [rbp+8]; this
0x1800073bc  mov     r9d, eax; char *
0x1800073bf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800073c6  mov     edx, 42Fh; void *
0x1800073cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800073d0  jmp     short loc_180007450
0x1800073d2  mov     [rbp+hKey], rdi
0x1800073d6  lea     rax, [rbp+hKey]
0x1800073da  mov     [rsp+30h+phkResult], rax; phkResult
0x1800073df  mov     r9d, 0F003Fh; samDesired
0x1800073e5  xor     r8d, r8d; ulOptions
0x1800073e8  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800073ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800073f3  call    cs:__imp_RegOpenKeyExW
0x1800073f9  test    eax, eax
0x1800073fb  jz      short loc_180007404
0x1800073fd  mov     edx, 432h
0x180007402  jmp     short loc_18000743B
0x180007404  lea     rax, [rbx+0ACh]
0x18000740b  mov     [rsp+30h+cbData], 10h; cbData
0x180007413  mov     [rsp+30h+phkResult], rax; int
0x180007418  mov     r9d, 3; dwType
0x18000741e  xor     r8d, r8d; Reserved
0x180007421  lea     rdx, aCensus; "Census"
0x180007428  mov     rcx, [rbp+hKey]; hKey
0x18000742c  call    cs:__imp_RegSetValueExW
0x180007432  test    eax, eax
0x180007434  jz      short loc_180007447
0x180007436  mov     edx, 435h; void *
0x18000743b  mov     r9d, eax; char *
0x18000743e  mov     rcx, [rbp+8]; this
0x180007442  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180007447  lea     rcx, [rbp+hKey]
0x18000744b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007450  mov     [rbx+0CAh], dil
0x180007457  lea     rcx, [rbp+lpSubKey]
0x18000745b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007460  cmp     [rbx+0CDh], dil
0x180007467  jz      loc_18000754D
0x18000746d  cmp     [rbx+0CCh], dil
0x180007474  jz      loc_18000754D
0x18000747a  mov     [rbp+lpSubKey], rdi
0x18000747e  xor     edx, edx
0x180007480  lea     rcx, [rbp+lpSubKey]
0x180007484  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180007489  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18000748d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007494  lea     rcx, aOobehealth; "OOBEHealth"
0x18000749b  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800074a0  test    eax, eax
0x1800074a2  jns     short loc_1800074BE
0x1800074a4  mov     rcx, [rbp+8]; this
0x1800074a8  mov     r9d, eax; char *
0x1800074ab  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800074b2  mov     edx, 42Fh; void *
0x1800074b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800074bc  jmp     short loc_18000753C
0x1800074be  mov     [rbp+hKey], rdi
0x1800074c2  lea     rax, [rbp+hKey]
0x1800074c6  mov     [rsp+30h+phkResult], rax; phkResult
0x1800074cb  mov     r9d, 0F003Fh; samDesired
0x1800074d1  xor     r8d, r8d; ulOptions
0x1800074d4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800074d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800074df  call    cs:__imp_RegOpenKeyExW
0x1800074e5  test    eax, eax
0x1800074e7  jz      short loc_1800074F0
0x1800074e9  mov     edx, 432h
0x1800074ee  jmp     short loc_180007527
0x1800074f0  lea     rax, [rbx+0BCh]
0x1800074f7  mov     [rsp+30h+cbData], 0Ch; cbData
0x1800074ff  mov     [rsp+30h+phkResult], rax; unsigned int
0x180007504  mov     r9d, 3; dwType
0x18000750a  xor     r8d, r8d; Reserved
0x18000750d  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x180007514  mov     rcx, [rbp+hKey]; hKey
0x180007518  call    cs:__imp_RegSetValueExW
0x18000751e  test    eax, eax
0x180007520  jz      short loc_180007533
0x180007522  mov     edx, 435h; void *
0x180007527  mov     r9d, eax; char *
0x18000752a  mov     rcx, [rbp+8]; this
0x18000752e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180007533  lea     rcx, [rbp+hKey]
0x180007537  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000753c  mov     [rbx+0CCh], dil
0x180007543  lea     rcx, [rbp+lpSubKey]
0x180007547  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000754c  nop
0x18000754d  mov     rbx, [rsp+30h+arg_10]
0x180007552  mov     rdi, [rsp+30h+arg_18]
0x180007557  add     rsp, 30h
0x18000755b  pop     rbp
0x18000755c  retn
```
