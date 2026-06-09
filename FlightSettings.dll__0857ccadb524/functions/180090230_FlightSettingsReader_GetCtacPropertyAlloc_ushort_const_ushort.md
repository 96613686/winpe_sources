# FlightSettingsReader::GetCtacPropertyAlloc(ushort const *,ushort * *)

- ea: `0x180090230`
- end: `0x180090877`
- name: `?GetCtacPropertyAlloc@FlightSettingsReader@@UEAAJPEBGPEAPEAG@Z`
- size: `1607`
- prototype: `__int64 __fastcall(FlightSettingsReader *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18001ed3c`
- `0x18002035c`
- `0x180086e3c`
- `0x180086efc`
- `0x180087138`
- `0x18008bcb8`
- `0x18008ffe0`
- `0x180090230`
- `0x1800909a0`
- `0x1800913c0`
- `0x1800915b0`
- `0x180091680`
- `0x1800917a0`
- `0x180091840`
- `0x180091fa4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009026a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800902b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009030f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090358`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800903c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090477`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800904e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009064e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009069a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800906e7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090730`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009077c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800907e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009026a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800902b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009030f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090358`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800903c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090477`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800904e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009064e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009069a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800906e7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090730`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009077c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800907e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009051c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009051c`

## string_xrefs

- `0x180090772`: `SyncWNSUri`
- `0x18009052f`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090588`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090833`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x1800906dd`: `BranchReadinessLevelRaw`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FlightSettingsReader::GetCtacPropertyAlloc(
        FlightSettingsReader *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int RingNameAlloc; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // r9
  const wchar_t *v11; // rdx
  HRESULT v12; // eax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  FlightSettingsReader *v19; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  unsigned int v22; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v23; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h]
  __int64 v26; // [rsp+50h] [rbp-30h]
  __int64 v27; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-20h] BYREF
  int v29; // [rsp+64h] [rbp-1Ch] BYREF
  int v30; // [rsp+68h] [rbp-18h] BYREF
  int v31; // [rsp+6Ch] [rbp-14h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  unsigned int v34; // [rsp+B8h] [rbp+38h] BYREF

  v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightRing") )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
    v25 = -1;
    v26 = -1;
    RingNameAlloc = FlightSettingsReader::GetRingNameAlloc(this, &v24);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 543;
LABEL_79:
      v10 = (unsigned int)RingNameAlloc;
      goto LABEL_80;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightRingId") )
  {
    v28 = 0;
    RingNameAlloc = FlightSettingsReader::GetRingId(this, &v28);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 548;
      goto LABEL_79;
    }
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v28);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 549;
      goto LABEL_79;
    }
LABEL_53:
    v17 = v24;
    v24 = 0;
    v26 = 0;
    v25 = 0;
    *a3 = v17;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightingBranchName") )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
    v25 = -1;
    v26 = -1;
    RingNameAlloc = FlightSettingsReader::GetBranchNameAlloc(this, &v24);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 553;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"IsFlightingEnabled") )
  {
    LOWORD(v34) = 0;
    RingNameAlloc = FlightSettingsReader::IsFlightingEnabled(this, (__int16 *)&v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 558;
      goto LABEL_79;
    }
    v9 = L"1";
    if ( (_WORD)v34 != 0xFFFF )
      v9 = L"0";
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      &v24,
                      v9,
                      -1);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 559;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"PilotRing") )
  {
    v30 = 0;
    v29 = 4;
    RingNameAlloc = FlightSettingsReader::GetPilotInfo(this, (enum PilotInfoRing *)&v30, (enum PilotErrorState *)&v29);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 565;
      goto LABEL_79;
    }
    if ( v29 )
    {
      if ( v29 == 4 )
      {
        v7 = -2147467259;
      }
      else
      {
        if ( v29 != 2 )
        {
          v7 = v29 | 0x80041180;
          v10 = v29 | 0x80041180;
          v8 = 571;
LABEL_80:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v8,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
            (const char *)v10,
            ppv);
          goto LABEL_81;
        }
        v7 = -2146698715;
      }
LABEL_81:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
      return v7;
    }
    if ( v30 )
    {
      RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                        &v24,
                        L"%d");
      v7 = RingNameAlloc;
      if ( RingNameAlloc < 0 )
      {
        v8 = 578;
        goto LABEL_79;
      }
      goto LABEL_53;
    }
LABEL_29:
    v7 = -2147023728;
    goto LABEL_81;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"IsRetailOs") )
  {
    LOWORD(v34) = 0;
    RingNameAlloc = FlightSettingsReader::IsRetailOS(this, (__int16 *)&v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 583;
      goto LABEL_79;
    }
    v11 = L"1";
    if ( (_WORD)v34 != 0xFFFF )
      v11 = L"0";
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      &v24,
                      v11,
                      -1);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 584;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightIds") )
  {
    v23 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    v12 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v23);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v27 = 0;
      v13 = v23;
      v14 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v23 + 32LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
      v15 = v14(v13, &v27);
      v7 = v15;
      if ( v15 >= 0 )
      {
        v32 = 0;
        v31 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v27 + 32LL))(v27, &v32, &v31);
        v7 = v15;
        if ( v15 >= 0 )
        {
          if ( !v32 || !v31 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
            goto LABEL_29;
          }
          v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  &v24,
                  v32,
                  -1);
          v7 = v15;
          if ( v15 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
            goto LABEL_53;
          }
          v16 = 604;
        }
        else
        {
          v16 = 596;
        }
      }
      else
      {
        v16 = 592;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v15,
        ppva);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v12,
        ppva);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    goto LABEL_81;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightingPolicyValue") )
  {
    v34 = 3;
    FSPolicyReader::GetFlightingPolicyValue((enum FlightingPolicyValues *)&v34, (enum PolicyType *)&v22);
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 611;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"FlightingPolicySource") )
  {
    v34 = 0;
    FSPolicyReader::GetFlightingPolicyValue((enum FlightingPolicyValues *)&v22, (enum PolicyType *)&v34);
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 618;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"BranchReadinessLevelRaw") )
  {
    v34 = 0;
    FSPolicyReader::GetBranchReadinessLevelRaw(&v34);
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 624;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"ManagePreviewBuilds") )
  {
    v34 = 3;
    FSPolicyReader::GetManagePreviewBuildsPolicyValue((enum FlightingPolicyValues *)&v34);
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v34);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 631;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"SyncWNSUri") )
  {
    if ( FlightSettingsAPICommon::WNSChannelUriSynced() )
    {
      RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                        &v24,
                        L"%d",
                        1);
      v7 = RingNameAlloc;
      if ( RingNameAlloc < 0 )
      {
        v8 = 637;
        goto LABEL_79;
      }
    }
    else
    {
      RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeHelper<_lambda_fe718337787c493ce2d833414db25eba_>(
                        (__int64)&v24,
                        L"%d",
                        0);
      v7 = RingNameAlloc;
      if ( RingNameAlloc < 0 )
      {
        v8 = 641;
        goto LABEL_79;
      }
    }
    goto LABEL_53;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Flighting_PageV3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Flighting_PageV3>::GetImpl'::`2'::impl)
    && !(unsigned int)_o__wcsicmp(a2, L"FlightUpgradeTarget") )
  {
    v22 = 0;
    RingNameAlloc = FlightSettingsReader::GetFlightUpgradeTarget(v19, &v22);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 647;
      goto LABEL_79;
    }
    RingNameAlloc = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      &v24,
                      L"%d",
                      v22);
    v7 = RingNameAlloc;
    if ( RingNameAlloc < 0 )
    {
      v8 = 648;
      goto LABEL_79;
    }
    goto LABEL_53;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
  return 2147750178LL;
}

```

## disassembly

```asm
0x180090230  mov     [rsp-18h+arg_0], rbx
0x180090235  mov     [rsp-18h+arg_8], rsi
0x18009023a  push    rbp
0x18009023b  push    rdi
0x18009023c  push    r14
0x18009023e  mov     rbp, rsp
0x180090241  sub     rsp, 80h
0x180090248  mov     rsi, r8
0x18009024b  mov     rbx, rdx
0x18009024e  mov     rdi, rcx
0x180090251  xor     r14d, r14d
0x180090254  mov     [rbp+var_40], r14
0x180090258  mov     [rbp+var_38], r14
0x18009025c  mov     [rbp+var_30], r14
0x180090260  lea     rdx, aFlightring; "FlightRing"
0x180090267  mov     rcx, rbx
0x18009026a  call    cs:__imp__o__wcsicmp
0x180090270  test    eax, eax
0x180090272  jnz     short loc_1800902A9
0x180090274  lea     rcx, [rbp+var_40]
0x180090278  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009027d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180090281  mov     [rbp+var_38], r8
0x180090285  mov     [rbp+var_30], r8
0x180090289  lea     rdx, [rbp+var_40]; unsigned __int16 **
0x18009028d  mov     rcx, rdi; this
0x180090290  call    ?GetRingNameAlloc@FlightSettingsReader@@UEAAJPEAPEAG@Z; FlightSettingsReader::GetRingNameAlloc(ushort * *)
0x180090295  mov     ebx, eax
0x180090297  test    eax, eax
0x180090299  jns     loc_180090609
0x18009029f  mov     edx, 21Fh
0x1800902a4  jmp     loc_180090830
0x1800902a9  lea     rdx, aFlightringid; "FlightRingId"
0x1800902b0  mov     rcx, rbx
0x1800902b3  call    cs:__imp__o__wcsicmp
0x1800902b9  test    eax, eax
0x1800902bb  jnz     short loc_180090305
0x1800902bd  mov     [rbp+var_20], r14d
0x1800902c1  lea     rdx, [rbp+var_20]; unsigned int *
0x1800902c5  mov     rcx, rdi; this
0x1800902c8  call    ?GetRingId@FlightSettingsReader@@UEAAJPEAK@Z; FlightSettingsReader::GetRingId(ulong *)
0x1800902cd  mov     ebx, eax
0x1800902cf  test    eax, eax
0x1800902d1  jns     short loc_1800902DD
0x1800902d3  mov     edx, 224h
0x1800902d8  jmp     loc_180090830
0x1800902dd  mov     r8d, [rbp+var_20]
0x1800902e1  lea     rdx, aD; "%d"
0x1800902e8  lea     rcx, [rbp+var_40]
0x1800902ec  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800902f1  mov     ebx, eax
0x1800902f3  test    eax, eax
0x1800902f5  jns     loc_180090609
0x1800902fb  mov     edx, 225h
0x180090300  jmp     loc_180090830
0x180090305  lea     rdx, aFlightingbranc; "FlightingBranchName"
0x18009030c  mov     rcx, rbx
0x18009030f  call    cs:__imp__o__wcsicmp
0x180090315  test    eax, eax
0x180090317  jnz     short loc_18009034E
0x180090319  lea     rcx, [rbp+var_40]
0x18009031d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090322  or      r8, 0FFFFFFFFFFFFFFFFh
0x180090326  mov     [rbp+var_38], r8
0x18009032a  mov     [rbp+var_30], r8
0x18009032e  lea     rdx, [rbp+var_40]; unsigned __int16 **
0x180090332  mov     rcx, rdi; this
0x180090335  call    ?GetBranchNameAlloc@FlightSettingsReader@@UEAAJPEAPEAG@Z; FlightSettingsReader::GetBranchNameAlloc(ushort * *)
0x18009033a  mov     ebx, eax
0x18009033c  test    eax, eax
0x18009033e  jns     loc_180090609
0x180090344  mov     edx, 229h
0x180090349  jmp     loc_180090830
0x18009034e  lea     rdx, aIsflightingena; "IsFlightingEnabled"
0x180090355  mov     rcx, rbx
0x180090358  call    cs:__imp__o__wcsicmp
0x18009035e  test    eax, eax
0x180090360  jnz     short loc_1800903BB
0x180090362  mov     word ptr [rbp+arg_18], r14w
0x180090367  lea     rdx, [rbp+arg_18]; __int16 *
0x18009036b  mov     rcx, rdi; this
0x18009036e  call    ?IsFlightingEnabled@FlightSettingsReader@@UEAAJPEAF@Z; FlightSettingsReader::IsFlightingEnabled(short *)
0x180090373  mov     ebx, eax
0x180090375  test    eax, eax
0x180090377  jns     short loc_180090383
0x180090379  mov     edx, 22Eh
0x18009037e  jmp     loc_180090830
0x180090383  lea     rdx, a1; "1"
0x18009038a  lea     rax, a0; "0"
0x180090391  or      r8, 0FFFFFFFFFFFFFFFFh
0x180090395  cmp     word ptr [rbp+arg_18], r8w
0x18009039a  cmovnz  rdx, rax
0x18009039e  lea     rcx, [rbp+var_40]
0x1800903a2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800903a7  mov     ebx, eax
0x1800903a9  test    eax, eax
0x1800903ab  jns     loc_180090609
0x1800903b1  mov     edx, 22Fh
0x1800903b6  jmp     loc_180090830
0x1800903bb  lea     rdx, aPilotring; "PilotRing"
0x1800903c2  mov     rcx, rbx
0x1800903c5  call    cs:__imp__o__wcsicmp
0x1800903cb  test    eax, eax
0x1800903cd  jnz     loc_18009046D
0x1800903d3  mov     [rbp+var_18], r14d
0x1800903d7  mov     [rbp+var_1C], 4
0x1800903de  lea     r8, [rbp+var_1C]; enum PilotErrorState *
0x1800903e2  lea     rdx, [rbp+var_18]; enum PilotInfoRing *
0x1800903e6  mov     rcx, rdi; this
0x1800903e9  call    ?GetPilotInfo@FlightSettingsReader@@UEAAJPEAW4PilotInfoRing@@PEAW4PilotErrorState@@@Z; FlightSettingsReader::GetPilotInfo(PilotInfoRing *,PilotErrorState *)
0x1800903ee  mov     ebx, eax
0x1800903f0  test    eax, eax
0x1800903f2  jns     short loc_1800903FE
0x1800903f4  mov     edx, 235h
0x1800903f9  jmp     loc_180090830
0x1800903fe  mov     ebx, [rbp+var_1C]
0x180090401  test    ebx, ebx
0x180090403  jz      short loc_180090436
0x180090405  cmp     ebx, 4
0x180090408  jnz     short loc_180090414
0x18009040a  mov     ebx, 80004005h
0x18009040f  jmp     loc_180090844
0x180090414  cmp     ebx, 2
0x180090417  jnz     short loc_180090423
0x180090419  mov     ebx, 800BFA25h
0x18009041e  jmp     loc_180090844
0x180090423  or      ebx, 80041180h
0x180090429  mov     r9d, ebx
0x18009042c  mov     edx, 23Bh
0x180090431  jmp     loc_180090833
0x180090436  mov     r8d, [rbp+var_18]
0x18009043a  test    r8d, r8d
0x18009043d  jnz     short loc_180090449
0x18009043f  mov     ebx, 80070490h
0x180090444  jmp     loc_180090844
0x180090449  lea     rdx, aD; "%d"
0x180090450  lea     rcx, [rbp+var_40]
0x180090454  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180090459  mov     ebx, eax
0x18009045b  test    eax, eax
0x18009045d  jns     loc_180090609
0x180090463  mov     edx, 242h
0x180090468  jmp     loc_180090830
0x18009046d  lea     rdx, aIsretailos_0; "IsRetailOs"
0x180090474  mov     rcx, rbx
0x180090477  call    cs:__imp__o__wcsicmp
0x18009047d  test    eax, eax
0x18009047f  jnz     short loc_1800904DA
0x180090481  mov     word ptr [rbp+arg_18], r14w
0x180090486  lea     rdx, [rbp+arg_18]; __int16 *
0x18009048a  mov     rcx, rdi; this
0x18009048d  call    ?IsRetailOS@FlightSettingsReader@@UEAAJPEAF@Z; FlightSettingsReader::IsRetailOS(short *)
0x180090492  mov     ebx, eax
0x180090494  test    eax, eax
0x180090496  jns     short loc_1800904A2
0x180090498  mov     edx, 247h
0x18009049d  jmp     loc_180090830
0x1800904a2  lea     rdx, a1; "1"
0x1800904a9  lea     rax, a0; "0"
0x1800904b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800904b4  cmp     word ptr [rbp+arg_18], r8w
0x1800904b9  cmovnz  rdx, rax
0x1800904bd  lea     rcx, [rbp+var_40]
0x1800904c1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800904c6  mov     ebx, eax
0x1800904c8  test    eax, eax
0x1800904ca  jns     loc_180090609
0x1800904d0  mov     edx, 248h
0x1800904d5  jmp     loc_180090830
0x1800904da  lea     rdx, aFlightids; "FlightIds"
0x1800904e1  mov     rcx, rbx
0x1800904e4  call    cs:__imp__o__wcsicmp
0x1800904ea  test    eax, eax
0x1800904ec  jnz     loc_180090644
0x1800904f2  mov     [rbp+var_48], r14
0x1800904f6  lea     rcx, [rbp+var_48]
0x1800904fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800904ff  lea     rax, [rbp+var_48]
0x180090503  mov     qword ptr [rsp+80h+ppv], rax; int
0x180090508  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x18009050f  xor     edx, edx; pUnkOuter
0x180090511  lea     r8d, [rdx+1]; dwClsContext
0x180090515  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18009051c  call    cs:__imp_CoCreateInstance
0x180090522  mov     ebx, eax
0x180090524  test    eax, eax
0x180090526  jns     short loc_18009054F
0x180090528  mov     rcx, [rbp+18h]; this
0x18009052c  mov     r9d, eax; char *
0x18009052f  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090536  mov     edx, 24Dh; void *
0x18009053b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090540  nop
0x180090541  lea     rcx, [rbp+var_48]
0x180090545  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009054a  jmp     loc_180090844
0x18009054f  mov     [rbp+var_28], r14
0x180090553  mov     rdi, [rbp+var_48]
0x180090557  mov     rax, [rdi]
0x18009055a  mov     rbx, [rax+20h]
0x18009055e  lea     rcx, [rbp+var_28]
0x180090562  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090567  lea     rdx, [rbp+var_28]
0x18009056b  mov     rcx, rdi
0x18009056e  mov     rax, rbx
0x180090571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090576  mov     ebx, eax
0x180090578  test    eax, eax
0x18009057a  jns     short loc_1800905A0
0x18009057c  mov     edx, 250h; void *
0x180090581  mov     rcx, [rbp+18h]; this
0x180090585  mov     r9d, eax; char *
0x180090588  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x18009058f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090594  nop
0x180090595  lea     rcx, [rbp+var_28]
0x180090599  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009059e  jmp     short loc_180090541
0x1800905a0  mov     [rbp+var_10], r14
0x1800905a4  mov     [rbp+var_14], r14d
0x1800905a8  mov     rcx, [rbp+var_28]
0x1800905ac  mov     rax, [rcx]
0x1800905af  lea     r8, [rbp+var_14]
0x1800905b3  lea     rdx, [rbp+var_10]
0x1800905b7  mov     rax, [rax+20h]
0x1800905bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905c0  mov     ebx, eax
0x1800905c2  test    eax, eax
0x1800905c4  jns     short loc_1800905CD
0x1800905c6  mov     edx, 254h
0x1800905cb  jmp     short loc_180090581
0x1800905cd  mov     rdx, [rbp+var_10]
0x1800905d1  test    rdx, rdx
0x1800905d4  jz      short loc_18009062C
0x1800905d6  cmp     [rbp+var_14], r14d
0x1800905da  jz      short loc_18009062C
0x1800905dc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800905e0  lea     rcx, [rbp+var_40]
0x1800905e4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800905e9  mov     ebx, eax
0x1800905eb  test    eax, eax
0x1800905ed  jns     short loc_1800905F6
0x1800905ef  mov     edx, 25Ch
0x1800905f4  jmp     short loc_180090581
0x1800905f6  lea     rcx, [rbp+var_28]
0x1800905fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800905ff  nop
0x180090600  lea     rcx, [rbp+var_48]
0x180090604  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090609  mov     rax, [rbp+var_40]
0x18009060d  mov     [rbp+var_40], r14
0x180090611  mov     [rbp+var_30], r14
0x180090615  mov     [rbp+var_38], r14
0x180090619  mov     [rsi], rax
0x18009061c  lea     rcx, [rbp+var_40]
0x180090620  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090625  xor     eax, eax
0x180090627  jmp     loc_18009085F
0x18009062c  lea     rcx, [rbp+var_28]
0x180090630  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090635  nop
0x180090636  lea     rcx, [rbp+var_48]
0x18009063a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009063f  jmp     loc_18009043F
0x180090644  lea     rdx, aFlightingpolic; "FlightingPolicyValue"
0x18009064b  mov     rcx, rbx
0x18009064e  call    cs:__imp__o__wcsicmp
0x180090654  test    eax, eax
0x180090656  jnz     short loc_180090690
0x180090658  mov     [rbp+arg_18], 3
0x18009065f  lea     rdx, [rbp+var_50]; enum PolicyType *
0x180090663  lea     rcx, [rbp+arg_18]; enum FlightingPolicyValues *
0x180090667  call    ?GetFlightingPolicyValue@FSPolicyReader@@SAJPEAW4FlightingPolicyValues@@PEAW4PolicyType@@@Z; FSPolicyReader::GetFlightingPolicyValue(FlightingPolicyValues *,PolicyType *)
0x18009066c  mov     r8d, [rbp+arg_18]
0x180090670  lea     rdx, aD; "%d"
0x180090677  lea     rcx, [rbp+var_40]
0x18009067b  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180090680  mov     ebx, eax
0x180090682  test    eax, eax
0x180090684  jns     short loc_180090609
0x180090686  mov     edx, 263h
0x18009068b  jmp     loc_180090830
0x180090690  lea     rdx, aFlightingpolic_0; "FlightingPolicySource"
0x180090697  mov     rcx, rbx
0x18009069a  call    cs:__imp__o__wcsicmp
0x1800906a0  test    eax, eax
0x1800906a2  jnz     short loc_1800906DD
0x1800906a4  mov     [rbp+arg_18], r14d
0x1800906a8  lea     rdx, [rbp+arg_18]; enum PolicyType *
0x1800906ac  lea     rcx, [rbp+var_50]; enum FlightingPolicyValues *
0x1800906b0  call    ?GetFlightingPolicyValue@FSPolicyReader@@SAJPEAW4FlightingPolicyValues@@PEAW4PolicyType@@@Z; FSPolicyReader::GetFlightingPolicyValue(FlightingPolicyValues *,PolicyType *)
0x1800906b5  mov     r8d, [rbp+arg_18]
0x1800906b9  lea     rdx, aD; "%d"
0x1800906c0  lea     rcx, [rbp+var_40]
0x1800906c4  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800906c9  mov     ebx, eax
0x1800906cb  test    eax, eax
0x1800906cd  jns     loc_180090609
0x1800906d3  mov     edx, 26Ah
0x1800906d8  jmp     loc_180090830
  ... truncated ...
```
