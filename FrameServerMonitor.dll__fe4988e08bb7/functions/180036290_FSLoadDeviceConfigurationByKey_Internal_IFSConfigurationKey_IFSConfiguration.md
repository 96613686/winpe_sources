# FSLoadDeviceConfigurationByKey_Internal(IFSConfigurationKey *,IFSConfiguration * *)

- ea: `0x180036290`
- end: `0x180036821`
- name: `?FSLoadDeviceConfigurationByKey_Internal@@YAJPEAUIFSConfigurationKey@@PEAPEAUIFSConfiguration@@@Z`
- size: `1425`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *, LPVOID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038f94`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d024`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000e66c`
- `0x180034e88`
- `0x180036290`
- `0x180036828`
- `0x18003c178`
- `0x18003c32c`
- `0x18003c75c`
- `0x180040914`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800364d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800364d8`

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
  signed int Configuration; // eax
  __int64 v18; // rdx
  const struct std::nothrow_t *unique; // rax
  BYTE *v20; // rbx
  const WCHAR *v21; // rax
  __int64 v22; // rdx
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  bool v25; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v26; // [rsp+4Ch] [rbp-34h] BYREF
  PBYTE PropertyBuffer; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+60h] [rbp-20h] BYREF

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
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
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
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
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v28, v26);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
        (void **)&PropertyBuffer,
        unique);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v28);
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
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&PropertyBuffer);
LABEL_55:
        if ( byte_18005E5A5 )
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
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&pv);
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
            wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
            wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&PropertyBuffer);
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
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&PropertyBuffer);
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
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
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
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&pv);
  PropertyKey.pid = 2;
  PropertyKey.fmtid = FrameServerConfigurationFMTGUIDV2;
  v5 = FSLoadV1OrV2(a1, &PropertyKey, 0, (struct IFSConfiguration **)&pv);
  v4 = v5;
  if ( v5 >= 0 )
  {
    v6 = (struct IFSConfiguration *)pv;
    if ( pv )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&PropertyBuffer);
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
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
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
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
    goto LABEL_58;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&PropertyBuffer);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pv);
LABEL_54:
  if ( v4 != -1072875819 )
    goto LABEL_55;
LABEL_58:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v22 = 71;
    goto LABEL_60;
  }
  return v4;
}

```

## disassembly

```asm
0x180036290  mov     [rsp-38h+arg_10], rbx
0x180036295  push    rbp
0x180036296  push    rsi
0x180036297  push    rdi
0x180036298  push    r12
0x18003629a  push    r13
0x18003629c  push    r14
0x18003629e  push    r15
0x1800362a0  mov     rbp, rsp
0x1800362a3  sub     rsp, 80h
0x1800362aa  mov     rax, cs:__security_cookie
0x1800362b1  xor     rax, rsp
0x1800362b4  mov     [rbp+var_8], rax
0x1800362b8  mov     r15, rdx
0x1800362bb  mov     r14, rcx
0x1800362be  xor     r12d, r12d
0x1800362c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x1800362c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x1800362cd  lea     r13, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800362d4  test    al, al
0x1800362d6  jz      loc_1800364FC
0x1800362dc  mov     [rbp+pv], r12
0x1800362e0  mov     [rbp+PropertyBuffer], r12
0x1800362e4  test    r14, r14
0x1800362e7  jnz     short loc_18003632F
0x1800362e9  mov     eax, 80070057h
0x1800362ee  mov     edi, eax
0x1800362f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800362f7  jb      short loc_180036318
0x1800362f9  lea     edx, [r12+3Ah]
0x1800362fe  mov     dword ptr [rsp+80h+var_60], eax
0x180036302  mov     rcx, cs:WPP_GLOBAL_Control
0x180036309  xor     r9d, r9d
0x18003630c  mov     r8, r13
0x18003630f  mov     rcx, [rcx+10h]
0x180036313  call    WPP_SF_qD
0x180036318  lea     rcx, [rbp+PropertyBuffer]
0x18003631c  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180036321  lea     rcx, [rbp+pv]
0x180036325  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003632a  jmp     loc_1800367A4
0x18003632f  test    r15, r15
0x180036332  jnz     short loc_18003634C
0x180036334  mov     edi, 80004003h
0x180036339  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036340  jb      short loc_180036318
0x180036342  lea     edx, [r15+3Bh]
0x180036346  mov     dword ptr [rsp+80h+var_60], edi
0x18003634a  jmp     short loc_180036302
0x18003634c  lea     rcx, [rbp+pv]
0x180036350  mov     [r15], r12
0x180036353  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180036358  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationFMTGUIDV2@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationFMTGUIDV2 ...
0x18003635f  mov     ebx, 2
0x180036364  lea     r9, [rbp+pv]; struct IFSConfiguration **
0x180036368  xor     r8d, r8d; bool
0x18003636b  mov     [rbp+PropertyKey.pid], ebx
0x18003636e  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x180036372  mov     rcx, r14; struct IFSConfigurationKey *
0x180036375  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18003637a  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x18003637f  mov     edi, eax
0x180036381  test    eax, eax
0x180036383  jns     short loc_1800363C2
0x180036385  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003638c  jb      short loc_1800363AB
0x18003638e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036395  lea     edx, [rbx+3Ah]
0x180036398  xor     r9d, r9d
0x18003639b  mov     dword ptr [rsp+80h+var_60], eax
0x18003639f  mov     r8, r13
0x1800363a2  mov     rcx, [rcx+10h]
0x1800363a6  call    WPP_SF_qD
0x1800363ab  lea     rcx, [rbp+PropertyBuffer]
0x1800363af  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800363b4  lea     rcx, [rbp+pv]
0x1800363b8  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800363bd  jmp     loc_18003679C
0x1800363c2  mov     rsi, [rbp+pv]
0x1800363c6  test    rsi, rsi
0x1800363c9  jz      loc_1800364DE
0x1800363cf  lea     rcx, [rbp+PropertyBuffer]
0x1800363d3  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x1800363d8  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationPublicFMTGUID@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationPublicFMTGUID ...
0x1800363df  lea     r9, [rbp+PropertyBuffer]; struct IFSConfiguration **
0x1800363e3  mov     [rbp+PropertyKey.pid], ebx
0x1800363e6  mov     r8b, 1; bool
0x1800363e9  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x1800363ed  mov     rcx, r14; struct IFSConfigurationKey *
0x1800363f0  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x1800363f5  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x1800363fa  test    eax, eax
0x1800363fc  js      loc_1800364DE
0x180036402  mov     rcx, [rbp+PropertyBuffer]
0x180036406  lea     rdx, [rbp+pv]
0x18003640a  mov     [rbp+pv], r12
0x18003640e  lea     r9, [rbp+var_34]
0x180036412  mov     [rbp+var_34], r12d
0x180036416  lea     r8, [rbp+PropertyKey.fmtid.Data4]
0x18003641a  mov     rax, [rcx]
0x18003641d  mov     qword ptr [rbp+PropertyKey.fmtid.Data1], rdx
0x180036421  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x180036428  mov     qword ptr [rbp+PropertyKey.fmtid.Data4], r12
0x18003642c  mov     byte ptr [rbp+PropertyKey.pid], 1
0x180036430  mov     rax, [rax+80h]
0x180036437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003643c  test    eax, eax
0x18003643e  js      short loc_180036448
0x180036440  cmp     [rbp+var_34], 18h
0x180036444  mov     bl, 1
0x180036446  jnb     short loc_18003644B
0x180036448  mov     bl, r12b
0x18003644b  lea     rcx, [rbp+PropertyKey]
0x18003644f  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180036454  test    bl, bl
0x180036456  jz      short loc_1800364B2
0x180036458  mov     r9, [rbp+pv]
0x18003645c  cmp     cs:byte_18005E5A5, 8
0x180036463  lea     rbx, [r9+8]
0x180036467  jb      short loc_1800364AD
0x180036469  mov     rax, [r9+10h]
0x18003646d  mov     edx, 3Dh ; '='
0x180036472  mov     ecx, [rbx]
0x180036474  mov     r8d, [rbx]
0x180036477  and     ecx, 1
0x18003647a  mov     [rsp+80h+var_48], rax
0x18003647f  mov     eax, [r9+4]
0x180036483  mov     r9d, [r9]
0x180036486  shr     r8, 1
0x180036489  and     r8d, 1
0x18003648d  mov     dword ptr [rsp+80h+var_50], r8d
0x180036492  mov     dword ptr [rsp+80h+var_58], ecx
0x180036496  mov     rcx, cs:WPP_GLOBAL_Control
0x18003649d  mov     dword ptr [rsp+80h+var_60], eax
0x1800364a1  mov     rcx, [rcx+0D8h]
0x1800364a8  call    WPP_SF_ddddi
0x1800364ad  test    byte ptr [rbx], 2
0x1800364b0  jz      short loc_1800364CB
0x1800364b2  mov     rax, [rsi]
0x1800364b5  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x1800364bc  mov     rcx, rsi
0x1800364bf  mov     rax, [rax+98h]
0x1800364c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364cb  mov     rcx, [rbp+pv]; pv
0x1800364cf  mov     [rbp+pv], r12
0x1800364d3  test    rcx, rcx
0x1800364d6  jz      short loc_1800364DE
0x1800364d8  call    cs:__imp_CoTaskMemFree
0x1800364de  lea     rcx, [rbp+PropertyBuffer]
0x1800364e2  mov     [rbp+pv], r12
0x1800364e6  mov     [r15], rsi
0x1800364e9  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800364ee  lea     rcx, [rbp+pv]
0x1800364f2  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800364f7  jmp     loc_1800367D1
0x1800364fc  xor     eax, eax
0x1800364fe  mov     [rbp+var_38], r12b
0x180036502  mov     [rbp+PropertyKey.pid], eax
0x180036505  xorps   xmm0, xmm0
0x180036508  movups  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18003650c  test    r14, r14
0x18003650f  jnz     short loc_180036548
0x180036511  mov     eax, 80070057h
0x180036516  mov     edi, eax
0x180036518  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003651f  jb      loc_1800367A4
0x180036525  mov     rcx, cs:WPP_GLOBAL_Control
0x18003652c  lea     edx, [r14+3Eh]
0x180036530  xor     r9d, r9d
0x180036533  mov     dword ptr [rsp+80h+var_60], eax
0x180036537  mov     r8, r13
0x18003653a  mov     rcx, [rcx+10h]
0x18003653e  call    WPP_SF_qD
0x180036543  jmp     loc_1800367A4
0x180036548  cmp     cs:byte_18005E5A5, 8
0x18003654f  jb      short loc_1800365C0
0x180036551  mov     rax, [r14]
0x180036554  mov     rcx, r14
0x180036557  mov     rax, [rax+48h]
0x18003655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036560  mov     rcx, [r14]
0x180036563  mov     rsi, rax
0x180036566  mov     rax, [rcx+38h]
0x18003656a  mov     rcx, r14
0x18003656d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036572  mov     rcx, [r14]
0x180036575  mov     rdi, rax
0x180036578  mov     rax, [rcx+40h]
0x18003657c  mov     rcx, r14
0x18003657f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036584  mov     rcx, [r14]
0x180036587  mov     rbx, rax
0x18003658a  mov     rax, [rcx+30h]
0x18003658e  mov     rcx, r14
0x180036591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036596  mov     rcx, cs:WPP_GLOBAL_Control
0x18003659d  mov     edx, 3Fh ; '?'
0x1800365a2  mov     [rsp+80h+var_50], rsi; __int64
0x1800365a7  mov     r9, rax
0x1800365aa  mov     [rsp+80h+var_58], rdi; __int64
0x1800365af  mov     [rsp+80h+var_60], rbx; __int64
0x1800365b4  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800365bb  call    WPP_SF_SSSS
0x1800365c0  lea     r8, [rbp+var_38]; bool *
0x1800365c4  mov     rcx, r14; struct IFSConfigurationKey *
0x1800365c7  lea     rdx, [rbp+PropertyKey]; struct _DEVPROPKEY *
0x1800365cb  call    ?FSFindConfigurationPropertyId@@YAJPEAUIFSConfigurationKey@@PEAU_DEVPROPKEY@@PEA_N@Z; FSFindConfigurationPropertyId(IFSConfigurationKey *,_DEVPROPKEY *,bool *)
0x1800365d0  mov     edi, eax
0x1800365d2  test    eax, eax
0x1800365d4  jns     short loc_180036607
0x1800365d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800365dd  jb      loc_18003679C
0x1800365e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365ea  mov     edx, 40h ; '@'
0x1800365ef  xor     r9d, r9d
0x1800365f2  mov     dword ptr [rsp+80h+var_60], eax
0x1800365f6  mov     r8, r13
0x1800365f9  mov     rcx, [rcx+10h]
0x1800365fd  call    WPP_SF_qD
0x180036602  jmp     loc_18003679C
0x180036607  cmp     [rbp+var_38], r12b
0x18003660b  jnz     short loc_180036617
0x18003660d  mov     edi, 0C00D36D5h
0x180036612  jmp     loc_1800367D1
0x180036617  mov     rax, [r14]
0x18003661a  mov     rcx, r14
0x18003661d  mov     [rbp+PropertyBuffer], r12
0x180036621  mov     [rbp+var_34], r12d
0x180036625  mov     [rbp+pv], r12
0x180036629  mov     rax, [rax+38h]
0x18003662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036632  mov     rcx, rax; pszDeviceInterface
0x180036635  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x180036639  lea     rax, [rbp+var_34]
0x18003663d  xor     r9d, r9d; unsigned int
0x180036640  xor     r8d, r8d; PropertyBuffer
0x180036643  mov     [rsp+80h+var_60], rax; unsigned int *
0x180036648  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18003664d  mov     edi, eax
0x18003664f  test    eax, eax
0x180036651  jns     short loc_18003666A
0x180036653  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003665a  jb      loc_18003678A
0x180036660  mov     edx, 41h ; 'A'
0x180036665  jmp     loc_180036770
0x18003666a  mov     edx, [rbp+var_34]
0x18003666d  lea     rcx, [rbp+var_28]
0x180036671  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180036676  mov     rdx, rax
0x180036679  lea     rcx, [rbp+PropertyBuffer]
0x18003667d  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180036682  lea     rcx, [rbp+var_28]
0x180036686  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003668b  mov     rbx, [rbp+PropertyBuffer]
0x18003668f  test    rbx, rbx
0x180036692  jnz     short loc_1800366D6
0x180036694  mov     edi, 8007000Eh
0x180036699  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800366a0  jb      short loc_1800366BF
0x1800366a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366a9  lea     edx, [rbx+42h]
0x1800366ac  xor     r9d, r9d
0x1800366af  mov     dword ptr [rsp+80h+var_60], edi
0x1800366b3  mov     r8, r13
0x1800366b6  mov     rcx, [rcx+10h]
0x1800366ba  call    WPP_SF_qD
0x1800366bf  lea     rcx, [rbp+pv]
0x1800366c3  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800366c8  lea     rcx, [rbp+PropertyBuffer]
0x1800366cc  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800366d1  jmp     loc_1800367A4
0x1800366d6  mov     rax, [r14]
0x1800366d9  mov     rcx, r14
0x1800366dc  mov     rax, [rax+38h]
0x1800366e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366e5  mov     r9d, [rbp+var_34]; unsigned int
0x1800366e9  lea     rcx, [rbp+var_34]
0x1800366ed  mov     [rsp+80h+var_60], rcx; unsigned int *
0x1800366f2  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x1800366f6  mov     rcx, rax; pszDeviceInterface
0x1800366f9  mov     r8, rbx; PropertyBuffer
0x1800366fc  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180036701  mov     edi, eax
0x180036703  test    eax, eax
0x180036705  jns     short loc_180036717
0x180036707  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003670e  jb      short loc_18003678A
0x180036710  mov     edx, 43h ; 'C'
0x180036715  jmp     short loc_180036770
0x180036717  lea     rcx, [rbp+pv]
0x18003671b  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180036720  lea     rdx, [rbp+pv]; struct IFSConfiguration **
0x180036724  mov     rcx, r14; struct IFSConfigurationKey *
0x180036727  call    ?CreateConfiguration@FSConfiguration@@SAJPEAUIFSConfigurationKey@@PEAPEAUIFSConfiguration@@@Z; FSConfiguration::CreateConfiguration(IFSConfigurationKey *,IFSConfiguration * *)
0x18003672c  mov     edi, eax
0x18003672e  test    eax, eax
0x180036730  jns     short loc_180036742
0x180036732  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036739  jb      short loc_18003678A
0x18003673b  mov     edx, 44h ; 'D'
  ... truncated ...
```
