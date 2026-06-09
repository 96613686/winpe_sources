# PublishSensorProfiles(ushort const *,IMFSensorProfileCollection *)

- ea: `0x18005baa8`
- end: `0x18005c2af`
- name: `?PublishSensorProfiles@@YAJPEBGPEAUIMFSensorProfileCollection@@@Z`
- size: `2055`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, struct IMFSensorProfileCollection *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800582c0`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000d1f0`
- `0x18000f518`
- `0x18003f1dc`
- `0x180044f30`
- `0x180045900`
- `0x18005b3d8`
- `0x18005baa8`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bb9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bb9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005bb5c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005bb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bd7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c24e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c27d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bd7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c24e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c27d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005bdc8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005bdc8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005bc1d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005be3b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005bebc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005c04f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005bc1d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005be3b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005bebc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005c04f`

## pseudocode

```c
__int64 __fastcall PublishSensorProfiles(LPCWSTR pszDeviceInterface, struct IMFSensorProfileCollection *a2)
{
  int v4; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  __int64 v8; // rdx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  unsigned int v11; // eax
  unsigned int i; // r13d
  __int64 v13; // rax
  int ProfileName; // eax
  unsigned int v15; // r8d
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  unsigned int v19; // r15d
  unsigned int v20; // eax
  unsigned int v21; // esi
  int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+88h] [rbp-78h] BYREF
  int Data; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v41; // [rsp+94h] [rbp-6Ch]
  unsigned int v42; // [rsp+98h] [rbp-68h]
  unsigned int v43; // [rsp+9Ch] [rbp-64h]
  unsigned int v44; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v45; // [rsp+A8h] [rbp-58h] BYREF
  IID rclsid; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h]
  WCHAR ValueName[20]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD lpData[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v50[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR SubKey[264]; // [rsp+510h] [rbp+410h] BYREF

  hKey = 0;
  v39 = 0;
  phkResult = 0;
  Data = 2;
  if ( !a2 )
  {
    v4 = FSOpenDeviceInterfaceRegistryKey(pszDeviceInterface, 0, 0x2001Fu, &hKey);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_109;
      v6 = 194;
      goto LABEL_5;
    }
    v7 = RegDeleteValueW(hKey, L"OEMCameraProfileVersion");
    if ( v7 )
    {
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      else
        v5 = v7;
      if ( !g_wppLevels )
        goto LABEL_109;
      v8 = 195;
    }
    else
    {
      v9 = RegDeleteTreeW(hKey, L"Profiles");
      if ( !v9 )
        goto LABEL_109;
      v5 = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
      if ( !g_wppLevels )
        goto LABEL_109;
      v8 = 196;
    }
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v5);
    goto LABEL_109;
  }
  v4 = FSOpenDeviceInterfaceRegistryKey(pszDeviceInterface, 0, 0x20006u, &hKey);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_109;
    v6 = 197;
    goto LABEL_5;
  }
  v10 = RegSetKeyValueW(hKey, 0, L"OEMCameraProfileVersion", 4u, &Data, 4u);
  v5 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_109;
      v8 = 198;
      goto LABEL_12;
    }
  }
  v4 = FSOpenDeviceInterfaceRegistryKey(pszDeviceInterface, L"Profiles", 0x20006u, &v39);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_109;
    v6 = 199;
LABEL_5:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v4);
    goto LABEL_109;
  }
  v11 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)a2 + 24LL))(a2);
  v44 = v11;
  for ( i = 0; ; ++i )
  {
    if ( i >= v11 )
      goto LABEL_109;
    memset_0(SubKey, 0, 0x208u);
    v33 = 0;
    v32 = 0;
    v47 = 0;
    rclsid = 0;
    memset_0(lpData, 0, 0x208u);
    v13 = *(_QWORD *)a2;
    v34 = 0;
    ProfileName = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *, _QWORD, __int64 *))(v13 + 32))(
                    a2,
                    i,
                    &v33);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 200;
      goto LABEL_107;
    }
    ProfileName = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v33)(
                    v33,
                    &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d,
                    &v32);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 201;
      goto LABEL_107;
    }
    ProfileName = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v33 + 24LL))(v33, &rclsid);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 202;
      goto LABEL_107;
    }
    ProfileName = GetProfileName(&rclsid, SubKey, v15);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 203;
      goto LABEL_107;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v16 = RegCreateKeyExW(v39, SubKey, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    v5 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      if ( v5 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_108;
        v28 = 204;
        goto LABEL_75;
      }
    }
    ProfileName = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64, int *))(*(_QWORD *)v32 + 160LL))(
                    v32,
                    lpData,
                    260,
                    &v34);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 205;
      goto LABEL_107;
    }
    if ( v34 )
    {
      v17 = RegSetKeyValueW(phkResult, 0, L"Constraint", 1u, lpData, 2 * v34);
      v5 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v5 = (unsigned __int16)v17 | 0x80070000;
        if ( v5 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_108;
          v28 = 206;
          goto LABEL_75;
        }
      }
    }
    v34 = 0;
    lpData[0] = 0;
    ProfileName = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64, int *))(*(_QWORD *)v32 + 168LL))(
                    v32,
                    lpData,
                    260,
                    &v34);
    v5 = ProfileName;
    if ( ProfileName < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_108;
      v30 = 207;
LABEL_107:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
        0,
        ProfileName);
      goto LABEL_108;
    }
    if ( v34 )
    {
      v18 = RegSetKeyValueW(phkResult, 0, L"BlockedControls", 1u, lpData, 2 * v34);
      if ( v18 )
      {
        if ( v18 > 0 )
          v5 = (unsigned __int16)v18 | 0x80070000;
        else
          v5 = v18;
        if ( !g_wppLevels )
          goto LABEL_108;
        v28 = 208;
LABEL_75:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v5);
        goto LABEL_108;
      }
    }
    v19 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 88LL))(v32);
    v43 = v20;
    v21 = 0;
LABEL_57:
    if ( v21 < v20 )
      break;
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v33);
    v11 = v44;
  }
  v35 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 96LL))(v32, v21, &v35);
  v5 = v22;
  if ( v22 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v22);
    goto LABEL_83;
  }
  v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 40LL))(v35);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 88LL))(v35);
  v42 = v23;
  v24 = 0;
  while ( 2 )
  {
    if ( v24 >= v23 )
    {
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v35);
      v20 = v43;
      ++v21;
      goto LABEL_57;
    }
    v36 = 0;
    memset_0(v50, 0, 0x208u);
    v45 = 0;
    memset(ValueName, 0, 28);
    v25 = StringCchPrintfW(ValueName, 0xEu, L"MTF%u", v19);
    v5 = v25;
    if ( v25 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v29 = 210;
LABEL_86:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v25);
      goto LABEL_82;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 96LL))(v35, v24, &v36);
    v5 = v25;
    if ( v25 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v29 = 211;
      goto LABEL_86;
    }
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 56LL))(v36);
    v25 = StringCchPrintfW(v50, 0x104u, L"Pin%u:%s", v41, v26);
    v5 = v25;
    if ( v25 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v29 = 212;
      goto LABEL_86;
    }
    v25 = StringCchLengthW(v50, 0x104u, &v45);
    v5 = v25;
    if ( v25 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v29 = 213;
      goto LABEL_86;
    }
    v27 = RegSetKeyValueW(phkResult, 0, ValueName, 1u, v50, 2 * (v45 + 1));
    if ( !v27 )
    {
      ++v19;
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v36);
      v23 = v42;
      ++v24;
      continue;
    }
    break;
  }
  if ( v27 > 0 )
    v5 = (unsigned __int16)v27 | 0x80070000;
  else
    v5 = v27;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v5);
LABEL_82:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v36);
LABEL_83:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v35);
LABEL_108:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v32);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v33);
LABEL_109:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v39 )
  {
    RegCloseKey(v39);
    v39 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005baa8  mov     [rsp-8+arg_10], rbx
0x18005baad  push    rbp
0x18005baae  push    rsi
0x18005baaf  push    rdi
0x18005bab0  push    r12
0x18005bab2  push    r13
0x18005bab4  push    r14
0x18005bab6  push    r15
0x18005bab8  lea     rbp, [rsp-630h]
0x18005bac0  sub     rsp, 730h
0x18005bac7  mov     rax, cs:__security_cookie
0x18005bace  xor     rax, rsp
0x18005bad1  mov     [rbp+660h+var_40], rax
0x18005bad8  mov     [rbp+660h+hKey], 0
0x18005bae0  mov     r12, rdx
0x18005bae3  mov     [rbp+660h+var_6D8], 0
0x18005baeb  mov     rsi, rcx
0x18005baee  mov     [rsp+760h+var_6E8], 0
0x18005baf7  lea     r9, [rbp+660h+hKey]; phkResult
0x18005bafb  mov     [rbp+660h+Data], 2
0x18005bb02  test    rdx, rdx
0x18005bb05  jnz     loc_18005BBD2
0x18005bb0b  mov     r8d, 2001Fh; samDesired
0x18005bb11  call    ?FSOpenDeviceInterfaceRegistryKey@@YAJPEBG0KPEAPEAUHKEY__@@@Z; FSOpenDeviceInterfaceRegistryKey(ushort const *,ushort const *,ulong,HKEY__ * *)
0x18005bb16  mov     ebx, eax
0x18005bb18  test    eax, eax
0x18005bb1a  jns     short loc_18005BB51
0x18005bb1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bb23  jb      loc_18005C244
0x18005bb29  mov     edx, 0C2h
0x18005bb2e  mov     dword ptr [rsp+760h+lpData], eax
0x18005bb32  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb39  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18005bb40  xor     r9d, r9d
0x18005bb43  mov     rcx, [rcx+10h]
0x18005bb47  call    WPP_SF_qD
0x18005bb4c  jmp     loc_18005C244
0x18005bb51  mov     rcx, [rbp+660h+hKey]; hKey
0x18005bb55  lea     rdx, aOemcameraprofi_0; "OEMCameraProfileVersion"
0x18005bb5c  call    cs:__imp_RegDeleteValueW
0x18005bb62  mov     edi, 80070000h
0x18005bb67  test    eax, eax
0x18005bb69  jz      short loc_18005BB92
0x18005bb6b  jg      short loc_18005BB71
0x18005bb6d  mov     ebx, eax
0x18005bb6f  jmp     short loc_18005BB76
0x18005bb71  movzx   ebx, ax
0x18005bb74  or      ebx, edi
0x18005bb76  test    ebx, ebx
0x18005bb78  jns     short loc_18005BB92
0x18005bb7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bb81  jb      loc_18005C244
0x18005bb87  mov     edx, 0C3h
0x18005bb8c  mov     dword ptr [rsp+760h+lpData], ebx
0x18005bb90  jmp     short loc_18005BB32
0x18005bb92  mov     rcx, [rbp+660h+hKey]; hKey
0x18005bb96  lea     rdx, aProfiles; "Profiles"
0x18005bb9d  call    cs:__imp_RegDeleteTreeW
0x18005bba3  test    eax, eax
0x18005bba5  jz      loc_18005C244
0x18005bbab  jg      short loc_18005BBB1
0x18005bbad  mov     ebx, eax
0x18005bbaf  jmp     short loc_18005BBB6
0x18005bbb1  movzx   ebx, ax
0x18005bbb4  or      ebx, edi
0x18005bbb6  test    ebx, ebx
0x18005bbb8  jns     loc_18005C244
0x18005bbbe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bbc5  jb      loc_18005C244
0x18005bbcb  mov     edx, 0C4h
0x18005bbd0  jmp     short loc_18005BB8C
0x18005bbd2  xor     edx, edx; lpSubKey
0x18005bbd4  mov     r8d, 20006h; samDesired
0x18005bbda  call    ?FSOpenDeviceInterfaceRegistryKey@@YAJPEBG0KPEAPEAUHKEY__@@@Z; FSOpenDeviceInterfaceRegistryKey(ushort const *,ushort const *,ulong,HKEY__ * *)
0x18005bbdf  mov     ebx, eax
0x18005bbe1  test    eax, eax
0x18005bbe3  jns     short loc_18005BBFC
0x18005bbe5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bbec  jb      loc_18005C244
0x18005bbf2  mov     edx, 0C5h
0x18005bbf7  jmp     loc_18005BB2E
0x18005bbfc  mov     rcx, [rbp+660h+hKey]; hKey
0x18005bc00  lea     rax, [rbp+660h+Data]
0x18005bc04  mov     r9d, 4; dwType
0x18005bc0a  lea     r8, aOemcameraprofi_0; "OEMCameraProfileVersion"
0x18005bc11  mov     [rsp+760h+cbData], r9d; cbData
0x18005bc16  xor     edx, edx; lpSubKey
0x18005bc18  mov     [rsp+760h+lpData], rax; lpData
0x18005bc1d  call    cs:__imp_RegSetKeyValueW
0x18005bc23  mov     ebx, eax
0x18005bc25  mov     edi, 80070000h
0x18005bc2a  test    eax, eax
0x18005bc2c  jz      short loc_18005BC50
0x18005bc2e  jle     short loc_18005BC35
0x18005bc30  movzx   ebx, ax
0x18005bc33  or      ebx, edi
0x18005bc35  test    ebx, ebx
0x18005bc37  jns     short loc_18005BC50
0x18005bc39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bc40  jb      loc_18005C244
0x18005bc46  mov     edx, 0C6h
0x18005bc4b  jmp     loc_18005BB8C
0x18005bc50  lea     r9, [rbp+660h+var_6D8]; phkResult
0x18005bc54  mov     r8d, 20006h; samDesired
0x18005bc5a  lea     rdx, aProfiles; "Profiles"
0x18005bc61  mov     rcx, rsi; pszDeviceInterface
0x18005bc64  call    ?FSOpenDeviceInterfaceRegistryKey@@YAJPEBG0KPEAPEAUHKEY__@@@Z; FSOpenDeviceInterfaceRegistryKey(ushort const *,ushort const *,ulong,HKEY__ * *)
0x18005bc69  mov     ebx, eax
0x18005bc6b  test    eax, eax
0x18005bc6d  jns     short loc_18005BC86
0x18005bc6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005bc76  jb      loc_18005C244
0x18005bc7c  mov     edx, 0C7h
0x18005bc81  jmp     loc_18005BB2E
0x18005bc86  mov     rax, [r12]
0x18005bc8a  mov     rcx, r12
0x18005bc8d  mov     rax, [rax+18h]
0x18005bc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc96  mov     [rbp+660h+var_6C0], eax
0x18005bc99  xor     r13d, r13d
0x18005bc9c  cmp     r13d, eax
0x18005bc9f  jnb     loc_18005C244
0x18005bca5  xor     edx, edx; Val
0x18005bca7  lea     rcx, [rbp+660h+SubKey]; void *
0x18005bcae  mov     r8d, 208h; Size
0x18005bcb4  call    memset_0
0x18005bcb9  xorps   xmm0, xmm0
0x18005bcbc  mov     [rsp+760h+var_708], 0
0x18005bcc5  xor     eax, eax
0x18005bcc7  mov     [rsp+760h+var_710], 0
0x18005bcd0  xor     edx, edx; Val
0x18005bcd2  mov     [rbp+660h+var_6A0], rax
0x18005bcd6  mov     r8d, 208h; Size
0x18005bcdc  lea     rcx, [rbp+660h+var_670]; void *
0x18005bce0  movups  xmmword ptr [rbp+660h+rclsid.Data1], xmm0
0x18005bce4  call    memset_0
0x18005bce9  mov     rax, [r12]
0x18005bced  lea     r8, [rsp+760h+var_708]
0x18005bcf2  mov     edx, r13d
0x18005bcf5  mov     [rsp+760h+var_700], 0
0x18005bcfd  mov     rcx, r12
0x18005bd00  mov     rax, [rax+20h]
0x18005bd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd09  mov     ebx, eax
0x18005bd0b  test    eax, eax
0x18005bd0d  js      loc_18005C204
0x18005bd13  mov     rcx, [rsp+760h+var_708]
0x18005bd18  lea     r8, [rsp+760h+var_710]
0x18005bd1d  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x18005bd24  mov     rax, [rcx]
0x18005bd27  mov     rax, [rax]
0x18005bd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd2f  mov     ebx, eax
0x18005bd31  test    eax, eax
0x18005bd33  js      loc_18005C1F4
0x18005bd39  mov     rcx, [rsp+760h+var_708]
0x18005bd3e  lea     rdx, [rbp+660h+rclsid]
0x18005bd42  mov     rax, [rcx]
0x18005bd45  mov     rax, [rax+18h]
0x18005bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd4e  mov     ebx, eax
0x18005bd50  test    eax, eax
0x18005bd52  js      loc_18005C1E4
0x18005bd58  lea     rdx, [rbp+660h+SubKey]; unsigned __int16 *
0x18005bd5f  lea     rcx, [rbp+660h+rclsid]; rclsid
0x18005bd63  call    ?GetProfileName@@YAJAEBU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@PEAGK@Z; GetProfileName(__MIDL___MIDL_itf_mfidl_0000_0114_0001 const &,ushort *,ulong)
0x18005bd68  mov     ebx, eax
0x18005bd6a  test    eax, eax
0x18005bd6c  js      loc_18005C1D4
0x18005bd72  mov     rcx, [rsp+760h+var_6E8]; hKey
0x18005bd77  test    rcx, rcx
0x18005bd7a  jz      short loc_18005BD8B
0x18005bd7c  call    cs:__imp_RegCloseKey
0x18005bd82  mov     [rsp+760h+var_6E8], 0
0x18005bd8b  mov     rcx, [rbp+660h+var_6D8]; hKey
0x18005bd8f  lea     rax, [rsp+760h+var_6E8]
0x18005bd94  mov     [rsp+760h+lpdwDisposition], 0; lpdwDisposition
0x18005bd9d  lea     rdx, [rbp+660h+SubKey]; lpSubKey
0x18005bda4  mov     [rsp+760h+phkResult], rax; phkResult
0x18005bda9  xor     r9d, r9d; lpClass
0x18005bdac  mov     [rsp+760h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005bdb5  xor     r8d, r8d; Reserved
0x18005bdb8  mov     [rsp+760h+cbData], 20006h; samDesired
0x18005bdc0  mov     dword ptr [rsp+760h+lpData], 0; dwOptions
0x18005bdc8  call    cs:__imp_RegCreateKeyExW
0x18005bdce  mov     ebx, eax
0x18005bdd0  test    eax, eax
0x18005bdd2  jz      short loc_18005BDE3
0x18005bdd4  jle     short loc_18005BDDB
0x18005bdd6  movzx   ebx, ax
0x18005bdd9  or      ebx, edi
0x18005bddb  test    ebx, ebx
0x18005bddd  js      loc_18005C0B7
0x18005bde3  mov     rcx, [rsp+760h+var_710]
0x18005bde8  lea     r9, [rsp+760h+var_700]
0x18005bded  mov     r8d, 104h
0x18005bdf3  lea     rdx, [rbp+660h+var_670]
0x18005bdf7  mov     rax, [rcx]
0x18005bdfa  mov     rax, [rax+0A0h]
0x18005be01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be06  mov     ebx, eax
0x18005be08  test    eax, eax
0x18005be0a  js      loc_18005C1C4
0x18005be10  mov     eax, [rsp+760h+var_700]
0x18005be14  test    eax, eax
0x18005be16  jz      short loc_18005BE56
0x18005be18  mov     rcx, [rsp+760h+var_6E8]; hKey
0x18005be1d  lea     r8, aConstraint; "Constraint"
0x18005be24  add     eax, eax
0x18005be26  mov     r9d, 1; dwType
0x18005be2c  mov     [rsp+760h+cbData], eax; cbData
0x18005be30  xor     edx, edx; lpSubKey
0x18005be32  lea     rax, [rbp+660h+var_670]
0x18005be36  mov     [rsp+760h+lpData], rax; lpData
0x18005be3b  call    cs:__imp_RegSetKeyValueW
0x18005be41  mov     ebx, eax
0x18005be43  test    eax, eax
0x18005be45  jz      short loc_18005BE56
0x18005be47  jle     short loc_18005BE4E
0x18005be49  movzx   ebx, ax
0x18005be4c  or      ebx, edi
0x18005be4e  test    ebx, ebx
0x18005be50  js      loc_18005C0D2
0x18005be56  mov     rcx, [rsp+760h+var_710]
0x18005be5b  lea     r9, [rsp+760h+var_700]
0x18005be60  xor     eax, eax
0x18005be62  mov     [rsp+760h+var_700], 0
0x18005be6a  mov     [rbp+660h+var_670], ax
0x18005be6e  lea     rdx, [rbp+660h+var_670]
0x18005be72  mov     r8d, 104h
0x18005be78  mov     rax, [rcx]
0x18005be7b  mov     rax, [rax+0A8h]
0x18005be82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be87  mov     ebx, eax
0x18005be89  test    eax, eax
0x18005be8b  js      loc_18005C1B4
0x18005be91  mov     eax, [rsp+760h+var_700]
0x18005be95  test    eax, eax
0x18005be97  jz      short loc_18005BED9
0x18005be99  mov     rcx, [rsp+760h+var_6E8]; hKey
0x18005be9e  lea     r8, aBlockedcontrol; "BlockedControls"
0x18005bea5  add     eax, eax
0x18005bea7  mov     r9d, 1; dwType
0x18005bead  mov     [rsp+760h+cbData], eax; cbData
0x18005beb1  xor     edx, edx; lpSubKey
0x18005beb3  lea     rax, [rbp+660h+var_670]
0x18005beb7  mov     [rsp+760h+lpData], rax; lpData
0x18005bebc  call    cs:__imp_RegSetKeyValueW
0x18005bec2  test    eax, eax
0x18005bec4  jz      short loc_18005BED9
0x18005bec6  jg      short loc_18005BECC
0x18005bec8  mov     ebx, eax
0x18005beca  jmp     short loc_18005BED1
0x18005becc  movzx   ebx, ax
0x18005becf  or      ebx, edi
0x18005bed1  test    ebx, ebx
0x18005bed3  js      loc_18005C0E6
0x18005bed9  mov     rcx, [rsp+760h+var_710]
0x18005bede  xor     r15d, r15d
0x18005bee1  mov     rax, [rcx]
0x18005bee4  mov     rax, [rax+58h]
0x18005bee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005beed  mov     [rbp+660h+var_6C4], eax
0x18005bef0  xor     esi, esi
0x18005bef2  cmp     esi, eax
0x18005bef4  jnb     loc_18005C098
0x18005befa  mov     rcx, [rsp+760h+var_710]
0x18005beff  lea     r8, [rsp+760h+var_6F8]
0x18005bf04  mov     [rsp+760h+var_6F8], 0
0x18005bf0d  mov     rdx, [rcx]
0x18005bf10  mov     rax, [rdx+60h]
0x18005bf14  mov     edx, esi
0x18005bf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf1b  mov     ebx, eax
0x18005bf1d  test    eax, eax
0x18005bf1f  js      loc_18005C183
0x18005bf25  mov     rcx, [rsp+760h+var_6F8]
0x18005bf2a  mov     rax, [rcx]
0x18005bf2d  mov     rax, [rax+28h]
0x18005bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf36  mov     rcx, [rsp+760h+var_6F8]
0x18005bf3b  mov     [rbp+660h+var_6CC], eax
0x18005bf3e  mov     rdx, [rcx]
0x18005bf41  mov     rax, [rdx+58h]
0x18005bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf4a  mov     [rbp+660h+var_6C8], eax
0x18005bf4d  xor     r14d, r14d
0x18005bf50  cmp     r14d, eax
0x18005bf53  jnb     loc_18005C084
0x18005bf59  xor     edx, edx; Val
0x18005bf5b  mov     [rsp+760h+var_6F0], 0
0x18005bf64  mov     r8d, 208h; Size
0x18005bf6a  lea     rcx, [rbp+660h+var_460]; void *
0x18005bf71  call    memset_0
0x18005bf76  xor     eax, eax
0x18005bf78  lea     r8, aMtfU; "MTF%u"
0x18005bf7f  xorps   xmm0, xmm0
0x18005bf82  mov     [rbp+660h+var_6B8], rax
0x18005bf86  movups  xmmword ptr [rbp+660h+ValueName], xmm0
0x18005bf8a  mov     r9d, r15d
  ... truncated ...
```
