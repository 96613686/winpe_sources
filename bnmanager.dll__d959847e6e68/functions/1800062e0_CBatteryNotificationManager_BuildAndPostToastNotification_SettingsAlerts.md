# CBatteryNotificationManager::BuildAndPostToastNotification(_SettingsAlerts)

- ea: `0x1800062e0`
- end: `0x180006917`
- name: `?BuildAndPostToastNotification@CBatteryNotificationManager@@CAJW4_SettingsAlerts@@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000af80`

## callees

- `0x1800017c0`
- `0x180002290`
- `0x18000355c`
- `0x1800038cc`
- `0x1800062e0`
- `0x180007250`
- `0x18000b040`
- `0x18000bde4`
- `0x18000c010`
- `0x18000ca80`
- `0x18000d010`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180006381`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006381`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000647a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800064b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800066fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000647a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800064b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800066fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800067b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800067b9`

## string_xrefs

- `0x18000641b`: `EnergySaverHeuristic`
- `0x18000684e`: `Windows.SystemToast.BackgroundAccess`
- `0x18000645d`: `http://go.microsoft.com/fwlink/?LinkId=626483`
- `0x180006412`: `https://go.microsoft.com/fwlink/?linkid=2290056`
- `0x180006879`: `<toast duration="long"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual><actions><action content="Learn more" arguments="%s" activationType="protocol"/></actions></toast>`
- `0x18000674a`: `<toast duration="long"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual><actions><action content="%s" arguments="%s" activationType="protocol"/></actions></toast>`
- `0x180006775`: `<toast launch="%s" activationType="protocol" duration="long"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall CBatteryNotificationManager::BuildAndPostToastNotification(int a1)
{
  int v2; // ebx
  char v3; // r13
  UINT v4; // r14d
  const wchar_t *v5; // r12
  UINT v6; // esi
  const wchar_t *v7; // rdi
  int v8; // eax
  signed int LastError; // eax
  int StringW; // eax
  signed int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, __int64 *, __int64 (__fastcall **)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *)); // rdi
  int v15; // eax
  __int64 (__fastcall *v16)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *); // rcx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  signed int v21; // eax
  int v22; // eax
  bool v24; // [rsp+90h] [rbp-80h]
  __int64 (__fastcall *v25)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *); // [rsp+98h] [rbp-78h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, __int64 *, __int64 (__fastcall **)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *)); // [rsp+A0h] [rbp-70h] BYREF
  int v27; // [rsp+A8h] [rbp-68h] BYREF
  __int64 (__fastcall *v28)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *); // [rsp+B0h] [rbp-60h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+C0h] [rbp-50h] BYREF
  int v31; // [rsp+C8h] [rbp-48h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-40h]
  LPVOID ppv; // [rsp+E0h] [rbp-30h] BYREF
  __int64 *v34; // [rsp+F0h] [rbp-20h] BYREF
  int v35; // [rsp+F8h] [rbp-18h]
  WCHAR v36[512]; // [rsp+100h] [rbp-10h] BYREF
  WCHAR Buffer[512]; // [rsp+500h] [rbp+3F0h] BYREF
  unsigned __int16 v38[512]; // [rsp+900h] [rbp+7F0h] BYREF
  WCHAR v39[512]; // [rsp+D00h] [rbp+BF0h] BYREF

  v30 = 0;
  v27 = 0;
  ppv = 0;
  v2 = 0;
  v3 = 0;
  v4 = 101;
  v5 = 0;
  v6 = 100;
  v7 = L"ms-settings:batterysaver";
  memset_0(v38, 0, sizeof(v38));
  v24 = 1;
  if ( a1 > 5 )
  {
    if ( a1 != 6 )
    {
      switch ( a1 )
      {
        case 7:
        case 8:
          v5 = L"BatterySaver";
          v6 = 112;
          v8 = 113;
          if ( a1 == 8 )
            v8 = 101;
          v4 = v8;
          v24 = a1 != 8;
          break;
        case 9:
          v5 = L"EnergySaverHeuristic";
          v6 = 128;
          v4 = 129;
          break;
        case 20:
          v5 = L"CleanEnergyCharging";
          v6 = 144;
          v4 = 145;
          v7 = L"https://go.microsoft.com/fwlink/?linkid=2290056";
          break;
      }
      goto LABEL_25;
    }
LABEL_24:
    v5 = L"BatterySlowCharging";
    v6 = 106;
    v4 = 109;
    v7 = L"http://go.microsoft.com/fwlink/?LinkId=626483";
    goto LABEL_25;
  }
  if ( a1 == 5 )
    goto LABEL_24;
  if ( a1 )
  {
    switch ( a1 )
    {
      case 1:
        v5 = L"SleepTimeout";
        v4 = 103;
        break;
      case 2:
        v5 = L"GenericToast";
        break;
      case 3:
        v5 = L"BatteryLevelLowCritical";
        v6 = 104;
        v4 = 107;
        break;
      case 4:
        if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
          goto LABEL_69;
        v6 = 105;
        v4 = 108;
        v3 = 1;
        break;
    }
  }
  else
  {
    v5 = L"DisplayBrightness";
    v4 = 102;
  }
LABEL_25:
  if ( LoadStringW(g_hInstance, v6, Buffer, 512) )
    goto LABEL_33;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_33:
    StringW = LoadStringW(g_hInstance, v4, v36, 512);
    if ( !v24 || StringW )
      goto LABEL_34;
    v11 = GetLastError();
    v2 = v11;
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_34:
      if ( v3 )
      {
        CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification(&v29, Buffer, v36);
        v25 = (__int64 (__fastcall *)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *))&v29;
        v34 = &qword_1800147C8;
        _InterlockedIncrement64(&qword_1800147C8);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> )
        {
          v26 = 0;
          v31 = 0;
          v32 = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
                                                                      + 48LL))(
                  winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>,
                  v29,
                  &v26);
          if ( v12 < 0 )
            winrt::throw_hresult((unsigned int)v12, &v31);
          v14 = v26;
          _InterlockedDecrement64(&qword_1800147C8);
        }
        else
        {
          _InterlockedDecrement64(&qword_1800147C8);
          winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
            0,
            &v26,
            &v25);
          v14 = v26;
        }
        v25 = 0;
        if ( v14 )
        {
          v15 = (**v14)(v14, winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotification6>, &v25);
          v16 = v25;
        }
        else
        {
          v15 = 0;
          v16 = 0;
        }
        v31 = 0;
        v32 = 0;
        if ( v15 < 0 )
          winrt::throw_hresult((unsigned int)v15, &v31);
        v31 = 0;
        v32 = 0;
        LOBYTE(v13) = 1;
        v17 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *), __int64))(*(_QWORD *)v16 + 56LL))(
                v16,
                v13);
        if ( v17 < 0 )
          winrt::throw_hresult((unsigned int)v17, &v31);
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v25);
        v34 = &qword_1800147A8;
        _InterlockedIncrement64(&qword_1800147A8);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> )
        {
          v25 = 0;
          v31 = 0;
          v32 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> + 48LL))(
                  winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>,
                  &v25);
          if ( v18 < 0 )
            winrt::throw_hresult((unsigned int)v18, &v31);
          v28 = v25;
          _InterlockedDecrement64(&qword_1800147A8);
        }
        else
        {
          _InterlockedDecrement64(&qword_1800147A8);
          v25 = _lambda_ff8c5332019ec05b76b7ea4a51425423_::_lambda_invoker_cdecl_;
          winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::call<winrt::Windows::UI::Notifications::ToastNotifier (*)(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)>(
            0,
            &v28,
            &v25);
        }
        v31 = 0;
        v32 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *), __int64 (__fastcall ***)(_QWORD, __int64 *, __int64 (__fastcall **)(const struct winrt::Windows::UI::Notifications::IToastNotificationManagerStatics *))))(*(_QWORD *)v28 + 48LL))(
                v28,
                v14);
        if ( v19 < 0 )
          winrt::throw_hresult((unsigned int)v19, &v31);
        if ( v28 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
        if ( v14 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v26);
        if ( v29 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
        goto LABEL_69;
      }
      if ( (unsigned int)(a1 - 5) <= 1 )
      {
        v22 = StringCchPrintfW(
                v38,
                0x200u,
                L"<toast duration=\"long\"><visual><binding template=\"ToastGeneric\"><text id=\"1\">%s</text><text id=\"2"
                 "\">%s</text></binding></visual><actions><action content=\"Learn more\" arguments=\"%s\" activationType="
                 "\"protocol\"/></actions></toast>",
                Buffer,
                v36,
                v7);
        goto LABEL_64;
      }
      if ( a1 != 9 )
      {
        v22 = StringCchPrintfW(
                v38,
                0x200u,
                L"<toast launch=\"%s\" activationType=\"protocol\" duration=\"long\"><visual><binding template=\"ToastGene"
                 "ric\"><text id=\"1\">%s</text><text id=\"2\">%s</text></binding></visual></toast>",
                v7,
                Buffer,
                v36);
        goto LABEL_64;
      }
      v20 = LoadStringW(g_hInstance, 0x82u, v39, 512);
      if ( !v24 || v20 )
        goto LABEL_62;
      v21 = GetLastError();
      v2 = v21;
      if ( v21 > 0 )
        v2 = (unsigned __int16)v21 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_62:
        v22 = StringCchPrintfW(
                v38,
                0x200u,
                L"<toast duration=\"long\"><visual><binding template=\"ToastGeneric\"><text id=\"1\">%s</text><text id=\"2"
                 "\">%s</text></binding></visual><actions><action content=\"%s\" arguments=\"%s\" activationType=\"protoc"
                 "ol\"/></actions></toast>",
                Buffer,
                v36,
                v39,
                v7);
LABEL_64:
        v2 = v22;
        if ( v22 >= 0 )
        {
          v2 = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 4u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 &ppv);
          if ( v2 >= 0 )
          {
            v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v30);
            if ( v2 >= 0 )
            {
              v34 = 0;
              v35 = 0;
              v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, unsigned __int16 *, const wchar_t *, const wchar_t *, __int64 **, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(*(_QWORD *)v30 + 64LL))(
                     v30,
                     L"NonImmersivePackage",
                     L"Windows.SystemToast.BackgroundAccess",
                     0,
                     1,
                     v38,
                     v5,
                     L"PowerToast",
                     &v34,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     &v27);
            }
          }
        }
      }
    }
  }
LABEL_69:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800062e0  push    rbp
0x1800062e2  push    rbx
0x1800062e3  push    rsi
0x1800062e4  push    rdi
0x1800062e5  push    r12
0x1800062e7  push    r13
0x1800062e9  push    r14
0x1800062eb  push    r15
0x1800062ed  lea     rbp, [rsp-1008h]
0x1800062f5  mov     eax, 1118h
0x1800062fa  call    _alloca_probe
0x1800062ff  sub     rsp, rax
0x180006302  mov     rax, cs:__security_cookie
0x180006309  xor     rax, rsp
0x18000630c  mov     [rbp+1040h+var_50], rax
0x180006313  mov     r15d, ecx
0x180006316  xor     eax, eax
0x180006318  mov     [rbp+1040h+var_1090], rax
0x18000631c  mov     [rbp+1040h+var_10A8], eax
0x18000631f  mov     [rbp+1040h+var_1070], rax
0x180006323  mov     ebx, eax
0x180006325  mov     r13b, al
0x180006328  lea     r14d, [rax+65h]
0x18000632c  mov     r12d, eax
0x18000632f  lea     esi, [rax+64h]
0x180006332  lea     rdi, aMsSettingsBatt; "ms-settings:batterysaver"
0x180006339  xor     edx, edx; Val
0x18000633b  mov     r8d, 400h; Size
0x180006341  lea     rcx, [rbp+1040h+var_850]; void *
0x180006348  call    memset_0
0x18000634d  mov     [rbp+1040h+var_10C0], 1
0x180006351  cmp     r15d, 5
0x180006355  jg      loc_1800063E6
0x18000635b  jz      loc_18000644D
0x180006361  mov     ecx, r15d
0x180006364  test    r15d, r15d
0x180006367  jz      short loc_1800063D7
0x180006369  sub     ecx, 1
0x18000636c  jz      short loc_1800063C5
0x18000636e  sub     ecx, 1
0x180006371  jz      short loc_1800063B9
0x180006373  sub     ecx, 1
0x180006376  jz      short loc_1800063A4
0x180006378  cmp     ecx, 1
0x18000637b  jnz     loc_180006464
0x180006381  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006387  xor     r14d, r14d
0x18000638a  test    al, al
0x18000638c  jz      loc_180006888
0x180006392  lea     esi, [r12+69h]
0x180006397  lea     r14d, [r12+6Ch]
0x18000639c  mov     r13b, 1
0x18000639f  jmp     loc_180006464
0x1800063a4  lea     r12, aBatterylevello; "BatteryLevelLowCritical"
0x1800063ab  mov     esi, 68h ; 'h'
0x1800063b0  lea     r14d, [rsi+3]
0x1800063b4  jmp     loc_180006464
0x1800063b9  lea     r12, aGenerictoast; "GenericToast"
0x1800063c0  jmp     loc_180006464
0x1800063c5  lea     r12, aSleeptimeout; "SleepTimeout"
0x1800063cc  mov     r14d, 67h ; 'g'
0x1800063d2  jmp     loc_180006464
0x1800063d7  lea     r12, aDisplaybrightn; "DisplayBrightness"
0x1800063de  mov     r14d, 66h ; 'f'
0x1800063e4  jmp     short loc_180006464
0x1800063e6  mov     ecx, r15d
0x1800063e9  sub     ecx, 6
0x1800063ec  jz      short loc_18000644D
0x1800063ee  sub     ecx, 1
0x1800063f1  jz      short loc_18000642D
0x1800063f3  sub     ecx, 1
0x1800063f6  jz      short loc_18000642D
0x1800063f8  sub     ecx, 1
0x1800063fb  jz      short loc_18000641B
0x1800063fd  cmp     ecx, 0Bh
0x180006400  jnz     short loc_180006464
0x180006402  lea     r12, aCleanenergycha; "CleanEnergyCharging"
0x180006409  mov     esi, 90h
0x18000640e  lea     r14d, [rsi+1]
0x180006412  lea     rdi, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?linkid"...
0x180006419  jmp     short loc_180006464
0x18000641b  lea     r12, aEnergysaverheu; "EnergySaverHeuristic"
0x180006422  mov     esi, 80h
0x180006427  lea     r14d, [rsi+1]
0x18000642b  jmp     short loc_180006464
0x18000642d  lea     r12, aBatterysaver; "BatterySaver"
0x180006434  mov     esi, 70h ; 'p'
0x180006439  lea     eax, [rsi+1]
0x18000643c  cmp     r15d, 8
0x180006440  cmovz   eax, r14d
0x180006444  mov     r14d, eax
0x180006447  setnz   [rbp+1040h+var_10C0]
0x18000644b  jmp     short loc_180006464
0x18000644d  lea     r12, aBatteryslowcha; "BatterySlowCharging"
0x180006454  mov     esi, 6Ah ; 'j'
0x180006459  lea     r14d, [rsi+3]
0x18000645d  lea     rdi, aHttpGoMicrosof; "http://go.microsoft.com/fwlink/?LinkId="...
0x180006464  mov     r9d, 200h; cchBufferMax
0x18000646a  lea     r8, [rbp+1040h+Buffer]; lpBuffer
0x180006471  mov     edx, esi; uID
0x180006473  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000647a  call    cs:__imp_LoadStringW
0x180006480  test    eax, eax
0x180006482  jnz     short loc_1800064A1
0x180006484  call    cs:__imp_GetLastError
0x18000648a  mov     ebx, eax
0x18000648c  test    eax, eax
0x18000648e  jle     short loc_180006499
0x180006490  movzx   ebx, ax
0x180006493  or      ebx, 80070000h
0x180006499  test    ebx, ebx
0x18000649b  js      loc_180006885
0x1800064a1  mov     r9d, 200h; cchBufferMax
0x1800064a7  lea     r8, [rbp+1040h+var_1050]; lpBuffer
0x1800064ab  mov     edx, r14d; uID
0x1800064ae  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800064b5  call    cs:__imp_LoadStringW
0x1800064bb  mov     sil, [rbp+1040h+var_10C0]
0x1800064bf  xor     r14d, r14d
0x1800064c2  test    sil, sil
0x1800064c5  jz      short loc_1800064E8
0x1800064c7  test    eax, eax
0x1800064c9  jnz     short loc_1800064E8
0x1800064cb  call    cs:__imp_GetLastError
0x1800064d1  mov     ebx, eax
0x1800064d3  test    eax, eax
0x1800064d5  jle     short loc_1800064E0
0x1800064d7  movzx   ebx, ax
0x1800064da  or      ebx, 80070000h
0x1800064e0  test    ebx, ebx
0x1800064e2  js      loc_180006888
0x1800064e8  test    r13b, r13b
0x1800064eb  jz      loc_1800066CA
0x1800064f1  lea     r8, [rbp+1040h+var_1050]
0x1800064f5  lea     rdx, [rbp+1040h+Buffer]
0x1800064fc  lea     rcx, [rbp+1040h+var_1098]
0x180006500  call    ?CreateToastXmlDocumentForBatteryNotification@CBatteryNotificationManager@@CA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@PEBG0@Z; CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification(ushort const *,ushort const *)
0x180006505  nop
0x180006506  lea     rax, [rbp+1040h+var_1098]
0x18000650a  mov     [rbp+1040h+var_10B8], rax
0x18000650e  lea     rax, qword_1800147C8
0x180006515  mov     [rbp+1040h+var_1060], rax
0x180006519  lock inc cs:qword_1800147C8
0x180006521  mov     rcx, cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x180006528  test    rcx, rcx
0x18000652b  jz      short loc_18000656B
0x18000652d  mov     [rbp+1040h+var_10B0], r14
0x180006531  mov     [rbp+1040h+var_1088], r14d
0x180006535  xorps   xmm0, xmm0
0x180006538  movdqu  [rbp+1040h+var_1080], xmm0
0x18000653d  mov     rax, [rcx]
0x180006540  lea     r8, [rbp+1040h+var_10B0]
0x180006544  mov     rdx, [rbp+1040h+var_1098]
0x180006548  mov     rax, [rax+30h]
0x18000654c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006551  test    eax, eax
0x180006553  js      loc_1800068E7
0x180006559  mov     rdi, [rbp+1040h+var_10B0]
0x18000655d  mov     [rbp+1040h+var_10B0], rdi
0x180006561  lock dec cs:qword_1800147C8
0x180006569  jmp     short loc_180006584
0x18000656b  lock dec cs:qword_1800147C8
0x180006573  lea     r8, [rbp+1040h+var_10B8]
0x180006577  lea     rdx, [rbp+1040h+var_10B0]
0x18000657b  call    ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z
0x180006580  mov     rdi, [rbp+1040h+var_10B0]
0x180006584  mov     [rbp+1040h+var_10B8], r14
0x180006588  test    rdi, rdi
0x18000658b  jnz     short loc_180006595
0x18000658d  mov     eax, r14d
0x180006590  mov     rcx, r14
0x180006593  jmp     short loc_1800065B6
0x180006595  mov     rax, [rdi]
0x180006598  lea     r8, [rbp+1040h+var_10B8]
0x18000659c  lea     rdx, ??$guid_v@UIToastNotification6@Notifications@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotification6>
0x1800065a3  mov     rcx, rdi
0x1800065a6  mov     rax, [rax]
0x1800065a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ae  mov     rcx, [rbp+1040h+var_10B8]
0x1800065b2  mov     [rbp+1040h+var_10B8], rcx
0x1800065b6  mov     [rbp+1040h+var_1088], r14d
0x1800065ba  xorps   xmm0, xmm0
0x1800065bd  movdqu  [rbp+1040h+var_1080], xmm0
0x1800065c2  test    eax, eax
0x1800065c4  js      loc_1800068F3
0x1800065ca  mov     [rbp+1040h+var_1088], r14d
0x1800065ce  movdqu  [rbp+1040h+var_1080], xmm0
0x1800065d3  mov     rax, [rcx]
0x1800065d6  mov     dl, 1
0x1800065d8  mov     rax, [rax+38h]
0x1800065dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e1  test    eax, eax
0x1800065e3  js      loc_1800068FF
0x1800065e9  lea     rcx, [rbp+1040h+var_10B8]
0x1800065ed  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800065f2  lea     rax, qword_1800147A8
0x1800065f9  mov     [rbp+1040h+var_1060], rax
0x1800065fd  lock inc cs:qword_1800147A8
0x180006605  mov     rcx, cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x18000660c  test    rcx, rcx
0x18000660f  jz      short loc_18000664B
0x180006611  mov     [rbp+1040h+var_10B8], r14
0x180006615  mov     [rbp+1040h+var_1088], r14d
0x180006619  xorps   xmm0, xmm0
0x18000661c  movdqu  [rbp+1040h+var_1080], xmm0
0x180006621  mov     rax, [rcx]
0x180006624  lea     rdx, [rbp+1040h+var_10B8]
0x180006628  mov     rax, [rax+30h]
0x18000662c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006631  test    eax, eax
0x180006633  js      loc_18000690B
0x180006639  mov     rax, [rbp+1040h+var_10B8]
0x18000663d  mov     [rbp+1040h+var_10A0], rax
0x180006641  lock dec cs:qword_1800147A8
0x180006649  jmp     short loc_18000666C
0x18000664b  lock dec cs:qword_1800147A8
0x180006653  lea     rax, ?_lambda_invoker_cdecl_@_lambda_ff8c5332019ec05b76b7ea4a51425423_@@CA@AEBUIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@Z; _lambda_ff8c5332019ec05b76b7ea4a51425423_::_lambda_invoker_cdecl_(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)
0x18000665a  mov     [rbp+1040h+var_10B8], rax
0x18000665e  lea     r8, [rbp+1040h+var_10B8]
0x180006662  lea     rdx, [rbp+1040h+var_10A0]
0x180006666  call    ??$call@P6A?AUToastNotifier@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotifier@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics@4562@@Z@Z
0x18000666b  nop
0x18000666c  mov     rcx, [rbp+1040h+var_10A0]
0x180006670  mov     [rbp+1040h+var_1088], r14d
0x180006674  xorps   xmm0, xmm0
0x180006677  movdqu  [rbp+1040h+var_1080], xmm0
0x18000667c  mov     rax, [rcx]
0x18000667f  mov     rdx, rdi
0x180006682  mov     rax, [rax+30h]
0x180006686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668b  test    eax, eax
0x18000668d  js      loc_1800068DB
0x180006693  cmp     [rbp+1040h+var_10A0], r14
0x180006697  jz      short loc_1800066A3
0x180006699  lea     rcx, [rbp+1040h+var_10A0]
0x18000669d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800066a2  nop
0x1800066a3  test    rdi, rdi
0x1800066a6  jz      short loc_1800066B2
0x1800066a8  lea     rcx, [rbp+1040h+var_10B0]
0x1800066ac  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800066b1  nop
0x1800066b2  cmp     [rbp+1040h+var_1098], r14
0x1800066b6  jz      loc_180006888
0x1800066bc  lea     rcx, [rbp+1040h+var_1098]
0x1800066c0  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800066c5  jmp     loc_180006888
0x1800066ca  lea     eax, [r15-5]
0x1800066ce  cmp     eax, 1
0x1800066d1  jbe     loc_180006869
0x1800066d7  cmp     r15d, 9
0x1800066db  jnz     loc_180006762
0x1800066e1  mov     r15d, 200h
0x1800066e7  mov     r9d, r15d; cchBufferMax
0x1800066ea  lea     r8, [rbp+1040h+var_450]; lpBuffer
0x1800066f1  mov     edx, 82h; uID
0x1800066f6  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800066fd  call    cs:__imp_LoadStringW
0x180006703  test    sil, sil
0x180006706  jz      short loc_180006729
0x180006708  test    eax, eax
0x18000670a  jnz     short loc_180006729
0x18000670c  call    cs:__imp_GetLastError
0x180006712  mov     ebx, eax
0x180006714  test    eax, eax
0x180006716  jle     short loc_180006721
0x180006718  movzx   ebx, ax
0x18000671b  or      ebx, 80070000h
0x180006721  test    ebx, ebx
0x180006723  js      loc_180006888
0x180006729  mov     [rsp+1150h+var_1120], rdi
0x18000672e  lea     rax, [rbp+1040h+var_450]
0x180006735  mov     [rsp+1150h+var_1128], rax
0x18000673a  lea     rax, [rbp+1040h+var_1050]
0x18000673e  mov     [rsp+1150h+ppv], rax
0x180006743  lea     r9, [rbp+1040h+Buffer]
0x18000674a  lea     r8, aToastDurationL; "<toast duration=\"long\"><visual><bindi"...
0x180006751  mov     rdx, r15; unsigned __int64
0x180006754  lea     rcx, [rbp+1040h+var_850]; unsigned __int16 *
0x18000675b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006760  jmp     short loc_180006792
0x180006762  lea     rax, [rbp+1040h+var_1050]
0x180006766  mov     [rsp+1150h+var_1128], rax
0x18000676b  lea     rax, [rbp+1040h+Buffer]
0x180006772  mov     r9, rdi
0x180006775  lea     r8, aToastLaunchSAc; "<toast launch=\"%s\" activationType=\"p"...
0x18000677c  mov     [rsp+1150h+ppv], rax
0x180006781  mov     edx, 200h; unsigned __int64
0x180006786  lea     rcx, [rbp+1040h+var_850]; unsigned __int16 *
0x18000678d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006792  mov     ebx, eax
0x180006794  test    eax, eax
0x180006796  js      loc_180006888
0x18000679c  lea     rax, [rbp+1040h+var_1070]
0x1800067a0  mov     [rsp+1150h+ppv], rax; ppv
0x1800067a5  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800067ac  xor     edx, edx; pUnkOuter
0x1800067ae  lea     r8d, [rdx+4]; dwClsContext
0x1800067b2  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x1800067b9  call    cs:__imp_CoCreateInstance
  ... truncated ...
```
