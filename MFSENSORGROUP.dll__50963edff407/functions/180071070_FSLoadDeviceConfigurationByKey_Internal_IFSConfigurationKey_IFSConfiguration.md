# FSLoadDeviceConfigurationByKey_Internal(IFSConfigurationKey *,IFSConfiguration * *)

- ea: `0x180071070`
- end: `0x180071601`
- name: `?FSLoadDeviceConfigurationByKey_Internal@@YAJPEAUIFSConfigurationKey@@PEAPEAUIFSConfiguration@@@Z`
- size: `1425`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *, LPVOID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180070948`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x18000f5a0`
- `0x1800133fc`
- `0x180025d70`
- `0x180028eb4`
- `0x18002c008`
- `0x180036258`
- `0x18003660c`
- `0x18003d064`
- `0x18003e1a0`
- `0x180044f30`
- `0x180071070`
- `0x180071608`
- `0x18007225c`
- `0x180073e9c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800712b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800712b8`

## pseudocode

```c
__int64 __fastcall FSLoadDeviceConfigurationByKey_Internal(struct IFSConfigurationKey *a1, LPVOID *a2)
{
  unsigned int v4; // edi
  int v5; // eax
  struct IFSConfiguration *v6; // rsi
  __int64 v7; // rax
  char v8; // bl
  _DWORD *v9; // rbx
  void *v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  const WCHAR *v16; // rax
  int Configuration; // eax
  __int64 v18; // rdx
  void **unique; // rax
  BYTE *v20; // rbx
  const WCHAR *v21; // rax
  __int64 v22; // rdx
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  bool v25; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v26; // [rsp+4Ch] [rbp-34h] BYREF
  PBYTE PropertyBuffer; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+60h] [rbp-20h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v25 = 0;
    memset(&PropertyKey, 0, sizeof(PropertyKey));
    if ( !a1 )
    {
      v4 = -2147024809;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -2147024809);
      goto LABEL_55;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v11 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
      v12 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
      v13 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
      (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
      WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v12, v11);
    }
    v14 = FSFindConfigurationPropertyId(a1, &PropertyKey, &v25);
    v4 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v14);
      goto LABEL_54;
    }
    if ( !v25 )
    {
      v4 = -1072875819;
      goto LABEL_58;
    }
    v15 = *(_QWORD *)a1;
    PropertyBuffer = 0;
    v26 = 0;
    pv = 0;
    v16 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(v15 + 56))(a1);
    Configuration = FSGetDeviceInterfaceProperty(v16, &PropertyKey, 0, 0, &v26);
    v4 = Configuration;
    if ( Configuration >= 0 )
    {
      unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v28, v26);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
        (void **)&PropertyBuffer,
        unique);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v28);
      v20 = PropertyBuffer;
      if ( !PropertyBuffer )
      {
        v4 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)((_DWORD)PropertyBuffer + 66),
            &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
            0,
            -2147024882);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&PropertyBuffer);
LABEL_55:
        if ( byte_18008D62D )
        {
          v22 = 70;
LABEL_60:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v22, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v4);
          return v4;
        }
        return v4;
      }
      v21 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
      Configuration = FSGetDeviceInterfaceProperty(v21, &PropertyKey, v20, v26, &v26);
      v4 = Configuration;
      if ( Configuration >= 0 )
      {
        wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&pv);
        Configuration = FSConfiguration::CreateConfiguration(a1, (struct IFSConfiguration **)&pv);
        v4 = Configuration;
        if ( Configuration >= 0 )
        {
          Configuration = (*(__int64 (__fastcall **)(LPVOID, BYTE *, _QWORD))(*(_QWORD *)pv + 288LL))(pv, v20, v26);
          v4 = Configuration;
          if ( Configuration >= 0 )
          {
            *a2 = pv;
            pv = 0;
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
            wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&PropertyBuffer);
            goto LABEL_58;
          }
          if ( !g_wppLevels )
            goto LABEL_53;
          v18 = 69;
          goto LABEL_52;
        }
        if ( g_wppLevels )
        {
          v18 = 68;
          goto LABEL_52;
        }
      }
      else if ( g_wppLevels )
      {
        v18 = 67;
        goto LABEL_52;
      }
    }
    else if ( g_wppLevels )
    {
      v18 = 65;
LABEL_52:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        Configuration);
    }
LABEL_53:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&PropertyBuffer);
    goto LABEL_54;
  }
  pv = 0;
  PropertyBuffer = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        -2147024809);
LABEL_5:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
    goto LABEL_55;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        -2147467261);
    goto LABEL_5;
  }
  *a2 = 0;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&pv);
  PropertyKey.pid = 2;
  PropertyKey.fmtid = FrameServerConfigurationFMTGUIDV2;
  v5 = FSLoadV1OrV2(a1, &PropertyKey, 0, (struct IFSConfiguration **)&pv);
  v4 = v5;
  if ( v5 >= 0 )
  {
    v6 = (struct IFSConfiguration *)pv;
    if ( pv )
    {
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&PropertyBuffer);
      PropertyKey.pid = 2;
      PropertyKey.fmtid = FrameServerConfigurationPublicFMTGUID;
      if ( (int)FSLoadV1OrV2(a1, &PropertyKey, 1, (struct IFSConfiguration **)&PropertyBuffer) >= 0 )
      {
        pv = 0;
        v26 = 0;
        v7 = *(_QWORD *)PropertyBuffer;
        *(_QWORD *)&PropertyKey.fmtid.Data1 = &pv;
        *(_QWORD *)PropertyKey.fmtid.Data4 = 0;
        LOBYTE(PropertyKey.pid) = 1;
        if ( (*(int (__fastcall **)(PBYTE, __int64 *, unsigned __int8 *, unsigned int *))(v7 + 128))(
               PropertyBuffer,
               FSM_WSEOPTIN_CONFIGURATION_INFO,
               PropertyKey.fmtid.Data4,
               &v26) < 0
          || (v8 = 1, v26 < 0x18) )
        {
          v8 = 0;
        }
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&PropertyKey);
        if ( !v8 )
          goto LABEL_22;
        v9 = (char *)pv + 8;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_ddddi(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            61,
            (*v9 >> 1) & 1,
            *(unsigned int *)pv,
            *((_DWORD *)pv + 1),
            *v9 & 1,
            (*v9 >> 1) & 1,
            *((_QWORD *)pv + 2));
        if ( (*(_BYTE *)v9 & 2) != 0 )
LABEL_22:
          (*(void (__fastcall **)(struct IFSConfiguration *, __int64 *))(*(_QWORD *)v6 + 152LL))(
            v6,
            MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS);
        v10 = pv;
        pv = 0;
        if ( v10 )
          CoTaskMemFree(v10);
      }
    }
    pv = 0;
    *a2 = v6;
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
    goto LABEL_58;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pv);
LABEL_54:
  if ( v4 != -1072875819 )
    goto LABEL_55;
LABEL_58:
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v22 = 71;
    goto LABEL_60;
  }
  return v4;
}

```

## disassembly

```asm
0x180071070  mov     [rsp-38h+arg_10], rbx
0x180071075  push    rbp
0x180071076  push    rsi
0x180071077  push    rdi
0x180071078  push    r12
0x18007107a  push    r13
0x18007107c  push    r14
0x18007107e  push    r15
0x180071080  mov     rbp, rsp
0x180071083  sub     rsp, 80h
0x18007108a  mov     rax, cs:__security_cookie
0x180071091  xor     rax, rsp
0x180071094  mov     [rbp+var_8], rax
0x180071098  mov     r15, rdx
0x18007109b  mov     r14, rcx
0x18007109e  xor     r12d, r12d
0x1800710a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x1800710a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x1800710ad  lea     r13, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800710b4  test    al, al
0x1800710b6  jz      loc_1800712DC
0x1800710bc  mov     [rbp+pv], r12
0x1800710c0  mov     [rbp+PropertyBuffer], r12
0x1800710c4  test    r14, r14
0x1800710c7  jnz     short loc_18007110F
0x1800710c9  mov     eax, 80070057h
0x1800710ce  mov     edi, eax
0x1800710d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800710d7  jb      short loc_1800710F8
0x1800710d9  lea     edx, [r12+3Ah]
0x1800710de  mov     dword ptr [rsp+80h+var_60], eax
0x1800710e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800710e9  xor     r9d, r9d
0x1800710ec  mov     r8, r13
0x1800710ef  mov     rcx, [rcx+10h]
0x1800710f3  call    WPP_SF_qD
0x1800710f8  lea     rcx, [rbp+PropertyBuffer]
0x1800710fc  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180071101  lea     rcx, [rbp+pv]
0x180071105  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18007110a  jmp     loc_180071584
0x18007110f  test    r15, r15
0x180071112  jnz     short loc_18007112C
0x180071114  mov     edi, 80004003h
0x180071119  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071120  jb      short loc_1800710F8
0x180071122  lea     edx, [r15+3Bh]
0x180071126  mov     dword ptr [rsp+80h+var_60], edi
0x18007112a  jmp     short loc_1800710E2
0x18007112c  lea     rcx, [rbp+pv]
0x180071130  mov     [r15], r12
0x180071133  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180071138  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationFMTGUIDV2@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationFMTGUIDV2 ...
0x18007113f  mov     ebx, 2
0x180071144  lea     r9, [rbp+pv]; struct IFSConfiguration **
0x180071148  xor     r8d, r8d; bool
0x18007114b  mov     [rbp+PropertyKey.pid], ebx
0x18007114e  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x180071152  mov     rcx, r14; struct IFSConfigurationKey *
0x180071155  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18007115a  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x18007115f  mov     edi, eax
0x180071161  test    eax, eax
0x180071163  jns     short loc_1800711A2
0x180071165  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007116c  jb      short loc_18007118B
0x18007116e  mov     rcx, cs:WPP_GLOBAL_Control
0x180071175  lea     edx, [rbx+3Ah]
0x180071178  xor     r9d, r9d
0x18007117b  mov     dword ptr [rsp+80h+var_60], eax
0x18007117f  mov     r8, r13
0x180071182  mov     rcx, [rcx+10h]
0x180071186  call    WPP_SF_qD
0x18007118b  lea     rcx, [rbp+PropertyBuffer]
0x18007118f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180071194  lea     rcx, [rbp+pv]
0x180071198  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18007119d  jmp     loc_18007157C
0x1800711a2  mov     rsi, [rbp+pv]
0x1800711a6  test    rsi, rsi
0x1800711a9  jz      loc_1800712BE
0x1800711af  lea     rcx, [rbp+PropertyBuffer]
0x1800711b3  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x1800711b8  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationPublicFMTGUID@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationPublicFMTGUID ...
0x1800711bf  lea     r9, [rbp+PropertyBuffer]; struct IFSConfiguration **
0x1800711c3  mov     [rbp+PropertyKey.pid], ebx
0x1800711c6  mov     r8b, 1; bool
0x1800711c9  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x1800711cd  mov     rcx, r14; struct IFSConfigurationKey *
0x1800711d0  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x1800711d5  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x1800711da  test    eax, eax
0x1800711dc  js      loc_1800712BE
0x1800711e2  mov     rcx, [rbp+PropertyBuffer]
0x1800711e6  lea     rdx, [rbp+pv]
0x1800711ea  mov     [rbp+pv], r12
0x1800711ee  lea     r9, [rbp+var_34]
0x1800711f2  mov     [rbp+var_34], r12d
0x1800711f6  lea     r8, [rbp+PropertyKey.fmtid.Data4]
0x1800711fa  mov     rax, [rcx]
0x1800711fd  mov     qword ptr [rbp+PropertyKey.fmtid.Data1], rdx
0x180071201  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x180071208  mov     qword ptr [rbp+PropertyKey.fmtid.Data4], r12
0x18007120c  mov     byte ptr [rbp+PropertyKey.pid], 1
0x180071210  mov     rax, [rax+80h]
0x180071217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007121c  test    eax, eax
0x18007121e  js      short loc_180071228
0x180071220  cmp     [rbp+var_34], 18h
0x180071224  mov     bl, 1
0x180071226  jnb     short loc_18007122B
0x180071228  mov     bl, r12b
0x18007122b  lea     rcx, [rbp+PropertyKey]
0x18007122f  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180071234  test    bl, bl
0x180071236  jz      short loc_180071292
0x180071238  mov     r9, [rbp+pv]
0x18007123c  cmp     cs:byte_18008D62D, 8
0x180071243  lea     rbx, [r9+8]
0x180071247  jb      short loc_18007128D
0x180071249  mov     rax, [r9+10h]
0x18007124d  mov     edx, 3Dh ; '='
0x180071252  mov     ecx, [rbx]
0x180071254  mov     r8d, [rbx]
0x180071257  and     ecx, 1
0x18007125a  mov     [rsp+80h+var_48], rax
0x18007125f  mov     eax, [r9+4]
0x180071263  mov     r9d, [r9]
0x180071266  shr     r8, 1
0x180071269  and     r8d, 1
0x18007126d  mov     dword ptr [rsp+80h+var_50], r8d
0x180071272  mov     dword ptr [rsp+80h+var_58], ecx
0x180071276  mov     rcx, cs:WPP_GLOBAL_Control
0x18007127d  mov     dword ptr [rsp+80h+var_60], eax
0x180071281  mov     rcx, [rcx+0D8h]
0x180071288  call    WPP_SF_ddddi
0x18007128d  test    byte ptr [rbx], 2
0x180071290  jz      short loc_1800712AB
0x180071292  mov     rax, [rsi]
0x180071295  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x18007129c  mov     rcx, rsi
0x18007129f  mov     rax, [rax+98h]
0x1800712a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712ab  mov     rcx, [rbp+pv]; pv
0x1800712af  mov     [rbp+pv], r12
0x1800712b3  test    rcx, rcx
0x1800712b6  jz      short loc_1800712BE
0x1800712b8  call    cs:__imp_CoTaskMemFree
0x1800712be  lea     rcx, [rbp+PropertyBuffer]
0x1800712c2  mov     [rbp+pv], r12
0x1800712c6  mov     [r15], rsi
0x1800712c9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800712ce  lea     rcx, [rbp+pv]
0x1800712d2  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800712d7  jmp     loc_1800715B1
0x1800712dc  xor     eax, eax
0x1800712de  mov     [rbp+var_38], r12b
0x1800712e2  mov     [rbp+PropertyKey.pid], eax
0x1800712e5  xorps   xmm0, xmm0
0x1800712e8  movups  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x1800712ec  test    r14, r14
0x1800712ef  jnz     short loc_180071328
0x1800712f1  mov     eax, 80070057h
0x1800712f6  mov     edi, eax
0x1800712f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800712ff  jb      loc_180071584
0x180071305  mov     rcx, cs:WPP_GLOBAL_Control
0x18007130c  lea     edx, [r14+3Eh]
0x180071310  xor     r9d, r9d
0x180071313  mov     dword ptr [rsp+80h+var_60], eax
0x180071317  mov     r8, r13
0x18007131a  mov     rcx, [rcx+10h]
0x18007131e  call    WPP_SF_qD
0x180071323  jmp     loc_180071584
0x180071328  cmp     cs:byte_18008D62D, 8
0x18007132f  jb      short loc_1800713A0
0x180071331  mov     rax, [r14]
0x180071334  mov     rcx, r14
0x180071337  mov     rax, [rax+48h]
0x18007133b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071340  mov     rcx, [r14]
0x180071343  mov     rsi, rax
0x180071346  mov     rax, [rcx+38h]
0x18007134a  mov     rcx, r14
0x18007134d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071352  mov     rcx, [r14]
0x180071355  mov     rdi, rax
0x180071358  mov     rax, [rcx+40h]
0x18007135c  mov     rcx, r14
0x18007135f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071364  mov     rcx, [r14]
0x180071367  mov     rbx, rax
0x18007136a  mov     rax, [rcx+30h]
0x18007136e  mov     rcx, r14
0x180071371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071376  mov     rcx, cs:WPP_GLOBAL_Control
0x18007137d  mov     edx, 3Fh ; '?'
0x180071382  mov     [rsp+80h+var_50], rsi; __int64
0x180071387  mov     r9, rax
0x18007138a  mov     [rsp+80h+var_58], rdi; __int64
0x18007138f  mov     [rsp+80h+var_60], rbx; __int64
0x180071394  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18007139b  call    WPP_SF_SSSS
0x1800713a0  lea     r8, [rbp+var_38]; bool *
0x1800713a4  mov     rcx, r14; struct IFSConfigurationKey *
0x1800713a7  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x1800713ab  call    ?FSFindConfigurationPropertyId@@YAJPEAUIFSConfigurationKey@@PEAU_DEVPROPKEY@@PEA_N@Z; FSFindConfigurationPropertyId(IFSConfigurationKey *,_DEVPROPKEY *,bool *)
0x1800713b0  mov     edi, eax
0x1800713b2  test    eax, eax
0x1800713b4  jns     short loc_1800713E7
0x1800713b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800713bd  jb      loc_18007157C
0x1800713c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713ca  mov     edx, 40h ; '@'
0x1800713cf  xor     r9d, r9d
0x1800713d2  mov     dword ptr [rsp+80h+var_60], eax
0x1800713d6  mov     r8, r13
0x1800713d9  mov     rcx, [rcx+10h]
0x1800713dd  call    WPP_SF_qD
0x1800713e2  jmp     loc_18007157C
0x1800713e7  cmp     [rbp+var_38], r12b
0x1800713eb  jnz     short loc_1800713F7
0x1800713ed  mov     edi, 0C00D36D5h
0x1800713f2  jmp     loc_1800715B1
0x1800713f7  mov     rax, [r14]
0x1800713fa  mov     rcx, r14
0x1800713fd  mov     [rbp+PropertyBuffer], r12
0x180071401  mov     [rbp+var_34], r12d
0x180071405  mov     [rbp+pv], r12
0x180071409  mov     rax, [rax+38h]
0x18007140d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071412  mov     rcx, rax; pszDeviceInterface
0x180071415  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x180071419  lea     rax, [rbp+var_34]
0x18007141d  xor     r9d, r9d; unsigned int
0x180071420  xor     r8d, r8d; PropertyBuffer
0x180071423  mov     [rsp+80h+var_60], rax; unsigned int *
0x180071428  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18007142d  mov     edi, eax
0x18007142f  test    eax, eax
0x180071431  jns     short loc_18007144A
0x180071433  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007143a  jb      loc_18007156A
0x180071440  mov     edx, 41h ; 'A'
0x180071445  jmp     loc_180071550
0x18007144a  mov     edx, [rbp+var_34]
0x18007144d  lea     rcx, [rbp+var_28]
0x180071451  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180071456  mov     rdx, rax
0x180071459  lea     rcx, [rbp+PropertyBuffer]
0x18007145d  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180071462  lea     rcx, [rbp+var_28]
0x180071466  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007146b  mov     rbx, [rbp+PropertyBuffer]
0x18007146f  test    rbx, rbx
0x180071472  jnz     short loc_1800714B6
0x180071474  mov     edi, 8007000Eh
0x180071479  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071480  jb      short loc_18007149F
0x180071482  mov     rcx, cs:WPP_GLOBAL_Control
0x180071489  lea     edx, [rbx+42h]
0x18007148c  xor     r9d, r9d
0x18007148f  mov     dword ptr [rsp+80h+var_60], edi
0x180071493  mov     r8, r13
0x180071496  mov     rcx, [rcx+10h]
0x18007149a  call    WPP_SF_qD
0x18007149f  lea     rcx, [rbp+pv]
0x1800714a3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800714a8  lea     rcx, [rbp+PropertyBuffer]
0x1800714ac  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800714b1  jmp     loc_180071584
0x1800714b6  mov     rax, [r14]
0x1800714b9  mov     rcx, r14
0x1800714bc  mov     rax, [rax+38h]
0x1800714c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714c5  mov     r9d, [rbp+var_34]; unsigned int
0x1800714c9  lea     rcx, [rbp+var_34]
0x1800714cd  mov     [rsp+80h+var_60], rcx; unsigned int *
0x1800714d2  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x1800714d6  mov     rcx, rax; pszDeviceInterface
0x1800714d9  mov     r8, rbx; PropertyBuffer
0x1800714dc  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x1800714e1  mov     edi, eax
0x1800714e3  test    eax, eax
0x1800714e5  jns     short loc_1800714F7
0x1800714e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800714ee  jb      short loc_18007156A
0x1800714f0  mov     edx, 43h ; 'C'
0x1800714f5  jmp     short loc_180071550
0x1800714f7  lea     rcx, [rbp+pv]
0x1800714fb  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180071500  lea     rdx, [rbp+pv]; struct IFSConfiguration **
0x180071504  mov     rcx, r14; struct IFSConfigurationKey *
0x180071507  call    ?CreateConfiguration@FSConfiguration@@SAJPEAUIFSConfigurationKey@@PEAPEAUIFSConfiguration@@@Z; FSConfiguration::CreateConfiguration(IFSConfigurationKey *,IFSConfiguration * *)
0x18007150c  mov     edi, eax
0x18007150e  test    eax, eax
0x180071510  jns     short loc_180071522
0x180071512  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071519  jb      short loc_18007156A
0x18007151b  mov     edx, 44h ; 'D'
  ... truncated ...
```
