# FSLoadAllAppsDeviceConfiguration_Internal(ushort const *,IFSConfiguration * *)

- ea: `0x180070948`
- end: `0x180070f3e`
- name: `?FSLoadAllAppsDeviceConfiguration_Internal@@YAJPEBGPEAPEAUIFSConfiguration@@@Z`
- size: `1526`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, struct IFSConfiguration **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c55c`

## callees

- `0x1800049b0`
- `0x180005b90`
- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x180010914`
- `0x180016328`
- `0x18001635c`
- `0x18002c008`
- `0x18002d02c`
- `0x180036258`
- `0x18003d064`
- `0x180044b28`
- `0x180044f30`
- `0x180070948`
- `0x180071070`
- `0x180071e68`
- `0x18007225c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070ba4`

## string_xrefs

- `0x180070d48`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x180070df0`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadAllAppsDeviceConfiguration_Internal(LPCWSTR pszDeviceInterface, struct IFSConfiguration **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  struct IFSConfiguration *v8; // r12
  __int64 v9; // rax
  char v10; // di
  _DWORD *v11; // rdi
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  void **unique; // rax
  void *v17; // rcx
  WCHAR *v18; // rdi
  int v19; // eax
  __int64 v20; // rdx
  void **v21; // rax
  WCHAR *v22; // rcx
  unsigned __int16 *v23; // r14
  int v24; // eax
  __int64 v25; // rdx
  LPVOID v26; // rcx
  __int64 v27; // rdx
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v31[2]; // [rsp+50h] [rbp-19h] BYREF
  LPCWSTR pszDeviceInterfacea; // [rsp+58h] [rbp-11h] BYREF
  void *Block; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-1h] BYREF
  GUID v35; // [rsp+70h] [rbp+7h] BYREF
  int v36; // [rsp+80h] [rbp+17h]

  pv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)v31 = 0;
    if ( !pszDeviceInterface )
    {
      v4 = -2147024809;
      v5 = -2147024809;
      if ( !g_wppLevels )
      {
LABEL_6:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v31);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
        goto LABEL_77;
      }
      v6 = 73;
LABEL_5:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v4);
      goto LABEL_6;
    }
    if ( !a2 )
    {
      v4 = -2147467261;
      v5 = -2147467261;
      if ( !g_wppLevels )
        goto LABEL_6;
      v6 = 74;
      goto LABEL_5;
    }
    *a2 = 0;
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&pv);
    v36 = 2;
    v35 = FrameServerConfigurationFMTGUIDV2;
    v7 = FSLoadAllAppsDeviceConfiguration_Base(pszDeviceInterface);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v8 = (struct IFSConfiguration *)pv;
      if ( pv )
      {
        wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(v31);
        v36 = 2;
        v35 = FrameServerConfigurationPublicFMTGUID;
        if ( (int)FSLoadAllAppsDeviceConfiguration_Base(pszDeviceInterface) >= 0 )
        {
          pv = 0;
          v30 = 0;
          v9 = **(_QWORD **)v31;
          *(_QWORD *)&v35.Data1 = &pv;
          *(_QWORD *)v35.Data4 = 0;
          LOBYTE(v36) = 1;
          if ( (*(int (__fastcall **)(_QWORD, __int64 *, unsigned __int8 *, unsigned int *))(v9 + 128))(
                 *(_QWORD *)v31,
                 FSM_WSEOPTIN_CONFIGURATION_INFO,
                 v35.Data4,
                 &v30) < 0
            || (v10 = 1, v30 < 0x18) )
          {
            v10 = 0;
          }
          wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v35);
          if ( !v10 )
            goto LABEL_23;
          v11 = (char *)pv + 8;
          if ( (unsigned __int8)byte_18008D62D >= 8u )
            WPP_SF_ddddi(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              76,
              (*v11 >> 1) & 1,
              *(unsigned int *)pv,
              *((_DWORD *)pv + 1),
              *v11 & 1,
              (*v11 >> 1) & 1,
              *((_QWORD *)pv + 2));
          if ( (*(_BYTE *)v11 & 2) != 0 )
LABEL_23:
            (*(void (__fastcall **)(struct IFSConfiguration *, __int64 *))(*(_QWORD *)v8 + 152LL))(
              v8,
              MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS);
          v12 = pv;
          pv = 0;
          if ( v12 )
            CoTaskMemFree(v12);
        }
      }
      pv = 0;
      *a2 = v8;
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v31);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
      goto LABEL_84;
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v7);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v31);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
    goto LABEL_76;
  }
  pszDeviceInterfacea = 0;
  v31[0] = 0;
  v34 = 0;
  v30 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      77,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      pszDeviceInterface);
  if ( !a2 )
  {
    v13 = -2147467261;
    v5 = -2147467261;
    if ( !g_wppLevels )
    {
LABEL_33:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
      goto LABEL_77;
    }
    v14 = 78;
LABEL_32:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v13);
    goto LABEL_33;
  }
  *a2 = 0;
  if ( !pszDeviceInterface )
  {
    v13 = -2147024809;
    v5 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_33;
    v14 = 79;
    goto LABEL_32;
  }
  v15 = FSGetUniqueSymbolicName(pszDeviceInterface, 0, 0, v31);
  v5 = v15;
  if ( v15 >= 0 )
  {
    unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v31[0]);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
      (void **)&pszDeviceInterfacea,
      unique);
    v17 = Block;
    Block = 0;
    if ( v17 )
      operator delete(v17);
    v18 = (WCHAR *)pszDeviceInterfacea;
    if ( !pszDeviceInterfacea )
    {
      v13 = -2147024882;
      v5 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_33;
      v14 = (unsigned int)((_DWORD)pszDeviceInterfacea + 81);
      goto LABEL_32;
    }
    v19 = FSGetUniqueSymbolicName(pszDeviceInterface, (unsigned __int16 *)pszDeviceInterfacea, v31[0], v31);
    v5 = v19;
    if ( v19 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_73;
      v20 = 82;
      goto LABEL_48;
    }
    v19 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v30);
    v5 = v19;
    if ( v19 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_73:
        if ( v18 )
          operator delete(v18);
        goto LABEL_75;
      }
      v20 = 83;
LABEL_48:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v19);
      goto LABEL_73;
    }
    v21 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&pszDeviceInterfacea, v30);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v34, v21);
    v22 = (WCHAR *)pszDeviceInterfacea;
    pszDeviceInterfacea = 0;
    if ( v22 )
      operator delete(v22);
    v23 = v34;
    if ( !v34 )
    {
      v5 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)v34 + 84),
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -2147024882);
      if ( v18 )
        operator delete(v18);
      goto LABEL_33;
    }
    v24 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v34, v30, &v30);
    v5 = v24;
    if ( v24 >= 0 )
    {
      v26 = pv;
      pv = 0;
      if ( v26 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      v24 = FSCreateConfigurationKey(v18);
      v5 = v24;
      if ( v24 >= 0 )
      {
        v24 = FSLoadDeviceConfigurationByKey_Internal((struct IFSConfigurationKey *)pv, a2);
        v5 = v24;
        if ( v24 >= 0 )
        {
          if ( v23 )
            operator delete(v23);
          if ( v18 )
            operator delete(v18);
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
          goto LABEL_84;
        }
        if ( g_wppLevels < 8u )
          goto LABEL_71;
        v25 = 87;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_71;
        v25 = 86;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_71;
      v25 = 85;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v24);
LABEL_71:
    if ( v23 )
      operator delete(v23);
    goto LABEL_73;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v15);
LABEL_75:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
LABEL_76:
  if ( v5 != -1072875819 )
  {
LABEL_77:
    if ( byte_18008D62D )
    {
      v27 = 88;
LABEL_86:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v27, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v5);
      return v5;
    }
    return v5;
  }
LABEL_84:
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v27 = 89;
    goto LABEL_86;
  }
  return v5;
}

```

## disassembly

```asm
0x180070948  mov     [rsp-8+arg_10], rbx
0x18007094d  push    rbp
0x18007094e  push    rsi
0x18007094f  push    rdi
0x180070950  push    r12
0x180070952  push    r13
0x180070954  push    r14
0x180070956  push    r15
0x180070958  lea     rbp, [rsp-27h]
0x18007095d  sub     rsp, 90h
0x180070964  mov     rax, cs:__security_cookie
0x18007096b  xor     rax, rsp
0x18007096e  mov     [rbp+57h+var_38], rax
0x180070972  mov     r15, rdx
0x180070975  mov     r14, rcx
0x180070978  xor     r13d, r13d
0x18007097b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x180070982  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x180070987  mov     [rbp+57h+pv], r13
0x18007098b  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180070992  lea     r12d, [r13+1]
0x180070996  test    al, al
0x180070998  jz      loc_180070BC8
0x18007099e  mov     qword ptr [rbp+57h+var_70], r13
0x1800709a2  test    r14, r14
0x1800709a5  jnz     short loc_1800709F3
0x1800709a7  mov     eax, 80070057h
0x1800709ac  mov     ebx, eax
0x1800709ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800709b5  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800709bc  jb      short loc_1800709DC
0x1800709be  lea     edx, [r13+49h]
0x1800709c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800709c9  xor     r9d, r9d
0x1800709cc  mov     r8, rsi
0x1800709cf  mov     [rsp+0C0h+var_A0], eax
0x1800709d3  mov     rcx, [rcx+10h]
0x1800709d7  call    WPP_SF_qD
0x1800709dc  lea     rcx, [rbp+57h+var_70]
0x1800709e0  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800709e5  lea     rcx, [rbp+57h+pv]
0x1800709e9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800709ee  jmp     loc_180070EBB
0x1800709f3  test    r15, r15
0x1800709f6  jnz     short loc_180070A15
0x1800709f8  mov     eax, 80004003h
0x1800709fd  mov     ebx, eax
0x1800709ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070a06  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180070a0d  jb      short loc_1800709DC
0x180070a0f  lea     edx, [r15+4Ah]
0x180070a13  jmp     short loc_1800709C2
0x180070a15  lea     rcx, [rbp+57h+pv]
0x180070a19  mov     [r15], r13
0x180070a1c  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180070a21  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationFMTGUIDV2@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationFMTGUIDV2 ...
0x180070a28  mov     edi, 2
0x180070a2d  lea     r9, [rbp+57h+pv]
0x180070a31  xor     r8d, r8d
0x180070a34  mov     [rbp+57h+var_40], edi
0x180070a37  lea     rdx, [rbp+57h+var_50]
0x180070a3b  mov     rcx, r14; pszDeviceInterface
0x180070a3e  movdqu  [rbp+57h+var_50], xmm0
0x180070a43  call    FSLoadAllAppsDeviceConfiguration_Base
0x180070a48  mov     ebx, eax
0x180070a4a  test    eax, eax
0x180070a4c  jns     short loc_180070A8B
0x180070a4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070a55  jb      short loc_180070A74
0x180070a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a5e  lea     edx, [rdi+49h]
0x180070a61  xor     r9d, r9d
0x180070a64  mov     [rsp+0C0h+var_A0], eax
0x180070a68  mov     r8, rsi
0x180070a6b  mov     rcx, [rcx+10h]
0x180070a6f  call    WPP_SF_qD
0x180070a74  lea     rcx, [rbp+57h+var_70]
0x180070a78  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180070a7d  lea     rcx, [rbp+57h+pv]
0x180070a81  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180070a86  jmp     loc_180070EB3
0x180070a8b  mov     r12, [rbp+57h+pv]
0x180070a8f  test    r12, r12
0x180070a92  jz      loc_180070BAA
0x180070a98  lea     rcx, [rbp+57h+var_70]
0x180070a9c  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180070aa1  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationPublicFMTGUID@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationPublicFMTGUID ...
0x180070aa8  lea     r9, [rbp+57h+var_70]
0x180070aac  mov     [rbp+57h+var_40], edi
0x180070aaf  mov     r8b, 1
0x180070ab2  lea     rdx, [rbp+57h+var_50]
0x180070ab6  mov     rcx, r14; pszDeviceInterface
0x180070ab9  movdqu  [rbp+57h+var_50], xmm0
0x180070abe  call    FSLoadAllAppsDeviceConfiguration_Base
0x180070ac3  test    eax, eax
0x180070ac5  js      loc_180070BAA
0x180070acb  mov     rcx, qword ptr [rbp+57h+var_70]
0x180070acf  lea     rdx, [rbp+57h+pv]
0x180070ad3  mov     [rbp+57h+pv], r13
0x180070ad7  lea     r9, [rbp+57h+var_78]
0x180070adb  mov     [rbp+57h+var_78], r13d
0x180070adf  lea     r8, [rbp+57h+var_50+8]
0x180070ae3  mov     rax, [rcx]
0x180070ae6  mov     qword ptr [rbp+57h+var_50], rdx
0x180070aea  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x180070af1  mov     qword ptr [rbp+57h+var_50+8], r13
0x180070af5  mov     byte ptr [rbp+57h+var_40], 1
0x180070af9  mov     rax, [rax+80h]
0x180070b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b05  test    eax, eax
0x180070b07  js      short loc_180070B12
0x180070b09  cmp     [rbp+57h+var_78], 18h
0x180070b0d  mov     dil, 1
0x180070b10  jnb     short loc_180070B15
0x180070b12  mov     dil, r13b
0x180070b15  lea     rcx, [rbp+57h+var_50]
0x180070b19  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180070b1e  test    dil, dil
0x180070b21  jz      short loc_180070B7D
0x180070b23  mov     r9, [rbp+57h+pv]
0x180070b27  cmp     cs:byte_18008D62D, 8
0x180070b2e  lea     rdi, [r9+8]
0x180070b32  jb      short loc_180070B78
0x180070b34  mov     rax, [r9+10h]
0x180070b38  mov     edx, 4Ch ; 'L'
0x180070b3d  mov     ecx, [rdi]
0x180070b3f  mov     r8d, [rdi]
0x180070b42  and     ecx, 1
0x180070b45  mov     [rsp+0C0h+var_88], rax
0x180070b4a  mov     eax, [r9+4]
0x180070b4e  mov     r9d, [r9]
0x180070b51  shr     r8, 1
0x180070b54  and     r8d, 1
0x180070b58  mov     [rsp+0C0h+var_90], r8d
0x180070b5d  mov     [rsp+0C0h+var_98], ecx
0x180070b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180070b68  mov     [rsp+0C0h+var_A0], eax
0x180070b6c  mov     rcx, [rcx+0D8h]
0x180070b73  call    WPP_SF_ddddi
0x180070b78  test    byte ptr [rdi], 2
0x180070b7b  jz      short loc_180070B97
0x180070b7d  mov     rax, [r12]
0x180070b81  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x180070b88  mov     rcx, r12
0x180070b8b  mov     rax, [rax+98h]
0x180070b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b97  mov     rcx, [rbp+57h+pv]; pv
0x180070b9b  mov     [rbp+57h+pv], r13
0x180070b9f  test    rcx, rcx
0x180070ba2  jz      short loc_180070BAA
0x180070ba4  call    cs:__imp_CoTaskMemFree
0x180070baa  lea     rcx, [rbp+57h+var_70]
0x180070bae  mov     [rbp+57h+pv], r13
0x180070bb2  mov     [r15], r12
0x180070bb5  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180070bba  lea     rcx, [rbp+57h+pv]
0x180070bbe  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180070bc3  jmp     loc_180070EEE
0x180070bc8  mov     [rbp+57h+pszDeviceInterface], r13
0x180070bcc  mov     [rbp+57h+var_70], r13d
0x180070bd0  mov     [rbp+57h+var_58], r13
0x180070bd4  mov     [rbp+57h+var_78], r13d
0x180070bd8  cmp     cs:byte_18008D62D, 8
0x180070bdf  jb      short loc_180070BFF
0x180070be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180070be8  mov     edx, 4Dh ; 'M'
0x180070bed  mov     r9, r14
0x180070bf0  mov     r8, rsi
0x180070bf3  mov     rcx, [rcx+0D8h]
0x180070bfa  call    WPP_SF_S
0x180070bff  test    r15, r15
0x180070c02  jnz     short loc_180070C40
0x180070c04  mov     eax, 80004003h
0x180070c09  mov     ebx, eax
0x180070c0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070c12  jb      short loc_180070C32
0x180070c14  lea     edx, [r15+4Eh]
0x180070c18  mov     rcx, cs:WPP_GLOBAL_Control
0x180070c1f  xor     r9d, r9d
0x180070c22  mov     r8, rsi
0x180070c25  mov     [rsp+0C0h+var_A0], eax
0x180070c29  mov     rcx, [rcx+10h]
0x180070c2d  call    WPP_SF_qD
0x180070c32  lea     rcx, [rbp+57h+pv]
0x180070c36  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180070c3b  jmp     loc_180070EBB
0x180070c40  mov     [r15], r13
0x180070c43  test    r14, r14
0x180070c46  jnz     short loc_180070C5E
0x180070c48  mov     eax, 80070057h
0x180070c4d  mov     ebx, eax
0x180070c4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070c56  jb      short loc_180070C32
0x180070c58  lea     edx, [r14+4Fh]
0x180070c5c  jmp     short loc_180070C18
0x180070c5e  lea     r9, [rbp+57h+var_70]; unsigned int *
0x180070c62  xor     r8d, r8d; unsigned int
0x180070c65  xor     edx, edx; unsigned __int16 *
0x180070c67  mov     rcx, r14; pszDeviceInterface
0x180070c6a  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180070c6f  mov     ebx, eax
0x180070c71  test    eax, eax
0x180070c73  jns     short loc_180070CA6
0x180070c75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070c7c  jb      loc_180070EAA
0x180070c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180070c89  mov     edx, 50h ; 'P'
0x180070c8e  xor     r9d, r9d
0x180070c91  mov     [rsp+0C0h+var_A0], eax
0x180070c95  mov     r8, rsi
0x180070c98  mov     rcx, [rcx+10h]
0x180070c9c  call    WPP_SF_qD
0x180070ca1  jmp     loc_180070EAA
0x180070ca6  mov     edx, [rbp+57h+var_70]
0x180070ca9  lea     rcx, [rbp+57h+Block]
0x180070cad  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180070cb2  mov     rdx, rax
0x180070cb5  lea     rcx, [rbp+57h+pszDeviceInterface]
0x180070cb9  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180070cbe  mov     rcx, [rbp+57h+Block]; Block
0x180070cc2  mov     [rbp+57h+Block], r13
0x180070cc6  test    rcx, rcx
0x180070cc9  jz      short loc_180070CD0
0x180070ccb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070cd0  mov     rdi, [rbp+57h+pszDeviceInterface]
0x180070cd4  test    rdi, rdi
0x180070cd7  jnz     short loc_180070CF5
0x180070cd9  mov     eax, 8007000Eh
0x180070cde  mov     ebx, eax
0x180070ce0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070ce7  jb      loc_180070C32
0x180070ced  lea     edx, [rdi+51h]
0x180070cf0  jmp     loc_180070C18
0x180070cf5  mov     r8d, [rbp+57h+var_70]; unsigned int
0x180070cf9  lea     r9, [rbp+57h+var_70]; unsigned int *
0x180070cfd  mov     rdx, rdi; unsigned __int16 *
0x180070d00  mov     rcx, r14; pszDeviceInterface
0x180070d03  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180070d08  mov     ebx, eax
0x180070d0a  test    eax, eax
0x180070d0c  jns     short loc_180070D3F
0x180070d0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070d15  jb      loc_180070E9D
0x180070d1b  mov     edx, 52h ; 'R'
0x180070d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d27  xor     r9d, r9d
0x180070d2a  mov     r8, rsi
0x180070d2d  mov     [rsp+0C0h+var_A0], eax
0x180070d31  mov     rcx, [rcx+10h]
0x180070d35  call    WPP_SF_qD
0x180070d3a  jmp     loc_180070E9D
0x180070d3f  lea     r9, [rbp+57h+var_78]; unsigned int *
0x180070d43  xor     r8d, r8d; unsigned int
0x180070d46  xor     edx, edx; unsigned __int16 *
0x180070d48  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180070d4f  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180070d54  mov     ebx, eax
0x180070d56  test    eax, eax
0x180070d58  jns     short loc_180070D6E
0x180070d5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070d61  jb      loc_180070E9D
0x180070d67  mov     edx, 53h ; 'S'
0x180070d6c  jmp     short loc_180070D20
0x180070d6e  mov     edx, [rbp+57h+var_78]
0x180070d71  lea     rcx, [rbp+57h+pszDeviceInterface]
0x180070d75  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180070d7a  mov     rdx, rax
0x180070d7d  lea     rcx, [rbp+57h+var_58]
0x180070d81  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180070d86  mov     rcx, [rbp+57h+pszDeviceInterface]; Block
0x180070d8a  mov     [rbp+57h+pszDeviceInterface], r13
0x180070d8e  test    rcx, rcx
0x180070d91  jz      short loc_180070D98
0x180070d93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070d98  mov     r14, [rbp+57h+var_58]
0x180070d9c  test    r14, r14
0x180070d9f  jnz     short loc_180070DE5
0x180070da1  mov     eax, 8007000Eh
0x180070da6  mov     ebx, eax
0x180070da8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180070daf  jb      short loc_180070DCF
0x180070db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180070db8  lea     edx, [r14+54h]
0x180070dbc  xor     r9d, r9d
0x180070dbf  mov     [rsp+0C0h+var_A0], eax
0x180070dc3  mov     r8, rsi
0x180070dc6  mov     rcx, [rcx+10h]
0x180070dca  call    WPP_SF_qD
0x180070dcf  test    rdi, rdi
0x180070dd2  jz      loc_180070C32
0x180070dd8  mov     rcx, rdi; Block
0x180070ddb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070de0  jmp     loc_180070C32
0x180070de5  mov     r8d, [rbp+57h+var_78]; unsigned int
0x180070de9  lea     r9, [rbp+57h+var_78]; unsigned int *
0x180070ded  mov     rdx, r14; unsigned __int16 *
0x180070df0  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180070df7  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180070dfc  mov     ebx, eax
0x180070dfe  test    eax, eax
  ... truncated ...
```
