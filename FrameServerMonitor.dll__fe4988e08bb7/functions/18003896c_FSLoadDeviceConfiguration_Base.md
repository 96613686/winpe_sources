# FSLoadDeviceConfiguration_Base

- ea: `0x18003896c`
- end: `0x180038f8e`
- name: `FSLoadDeviceConfiguration_Base`
- size: `1570`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *, struct _DEVPROPKEY *, bool)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038f94`
- `0x180039f6c`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000e25c`
- `0x18000e66c`
- `0x180011438`
- `0x18002fa3c`
- `0x18002fd04`
- `0x180036828`
- `0x180036cb8`
- `0x18003896c`
- `0x18003a48c`
- `0x18003beb0`
- `0x18003c178`
- `0x180042988`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038e84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ef3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038ef3`

## string_xrefs

- `0x180038a9a`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x180038b39`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadDeviceConfiguration_Base(
        struct IFSConfigurationKey *a1,
        struct _DEVPROPKEY *a2,
        bool a3,
        __int64 **a4)
{
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  const struct std::nothrow_t *unique; // rax
  struct IFSConfigurationKey *v16; // rcx
  unsigned __int16 *v17; // rax
  __int64 *v18; // rsi
  struct IFSConfiguration *v19; // rbx
  void *v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  void *v23; // rcx
  unsigned int i; // r14d
  const struct std::nothrow_t *v25; // rdx
  const char *String; // rax
  void *v27; // rcx
  __int64 v28; // rdx
  unsigned int v30; // [rsp+40h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-81h] BYREF
  struct IFSConfiguration *v32; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-71h] BYREF
  struct IFSConfigurationKey *v34; // [rsp+60h] [rbp-69h] BYREF
  struct IFSConfiguration *v35; // [rsp+68h] [rbp-61h] BYREF
  int v36; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int16 *v37; // [rsp+78h] [rbp-51h] BYREF
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v39; // [rsp+90h] [rbp-39h]
  _BYTE v40[32]; // [rsp+98h] [rbp-31h] BYREF
  struct _GUID v41; // [rsp+B8h] [rbp-11h] BYREF
  char v42; // [rsp+C8h] [rbp-1h]

  v32 = 0;
  v35 = 0;
  v34 = 0;
  v36 = 0;
  v33 = 0;
  v37 = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_69;
    v9 = 251;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    if ( g_wppLevels )
    {
      v9 = 252;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v8);
      goto LABEL_69;
    }
    goto LABEL_69;
  }
  *a4 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v10 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
    v11 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v12 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
    WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, v11, v10);
  }
  v30 = 0;
  v13 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v30);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_68;
    v14 = 254;
    goto LABEL_13;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&pv, v30);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v37, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pv);
  if ( !v37 )
  {
    v8 = -2147024882;
    if ( g_wppLevels )
    {
      v9 = 255;
      goto LABEL_4;
    }
LABEL_69:
    if ( byte_18005E5A5 )
    {
      v28 = 265;
LABEL_73:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v28,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        (unsigned int)v8);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  v13 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v37, v30, &v30);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v14 = 256;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v13);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  v16 = v34;
  v34 = 0;
  if ( v16 )
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
  v13 = FSCreateConfigurationKey(v17);
  v8 = v13;
  if ( v13 >= 0 )
  {
    if ( !(*(unsigned int (__fastcall **)(struct IFSConfigurationKey *, struct IFSConfigurationKey *))(*(_QWORD *)v34 + 24LL))(
            v34,
            a1) )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v32);
      v13 = FSLoadV1OrV2(a1, a2, a3, &v32);
      v8 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 258;
          goto LABEL_13;
        }
        goto LABEL_68;
      }
      goto LABEL_33;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v32);
    if ( (int)FSLoadV1OrV2(v34, a2, a3, &v32) < 0 )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v32);
      v13 = FSLoadV1OrV2(a1, a2, a3, &v32);
      v8 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels >= 8u )
        {
          v14 = 259;
          goto LABEL_13;
        }
        goto LABEL_68;
      }
LABEL_33:
      v18 = (__int64 *)v32;
LABEL_66:
      v32 = 0;
      *a4 = v18;
      goto LABEL_67;
    }
    v18 = (__int64 *)v32;
    v13 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, int *))(*(_QWORD *)v32 + 240LL))(v32, &v36);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 260;
        goto LABEL_13;
      }
      goto LABEL_68;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v35);
    if ( (int)FSLoadV1OrV2(a1, a2, a3, &v35) < 0 )
      goto LABEL_66;
    v19 = v35;
    v30 = 0;
    pv = 0;
    *(_QWORD *)&v41.Data1 = &pv;
    *(_QWORD *)v41.Data4 = 0;
    v42 = 1;
    v8 = FSMergeCameraControlConfigurations(v18, (__int64 *)v35, (LPVOID *)v41.Data4, &v30);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v41);
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v8);
      v20 = pv;
      pv = 0;
      if ( v20 )
        CoTaskMemFree(v20);
LABEL_67:
      if ( v8 >= 0 )
        goto LABEL_71;
      goto LABEL_68;
    }
    v21 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, unsigned int *))(*(_QWORD *)v19 + 240LL))(v19, &v33);
    v8 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_47;
      v22 = 262;
      goto LABEL_46;
    }
    for ( i = 0; i < v33; ++i )
    {
      v39 = 0;
      v41 = GUID_00000000_0000_0000_0000_000000000000;
      *(_OWORD *)pvar = 0;
      if ( (*(int (__fastcall **)(struct IFSConfiguration *, _QWORD, struct _GUID *, PROPVARIANT *))(*(_QWORD *)v19 + 248LL))(
             v19,
             i,
             &v41,
             pvar) >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, PROPVARIANT *))(*v18 + 144))(v18, &v41, pvar);
        if ( v8 < 0 )
        {
          if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
          {
            GuidTrace::GuidTrace((GuidTrace *)v40, &v41);
            if ( byte_18005E5A5 )
            {
              String = GuidTrace::GetString((GuidTrace *)v40);
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                263,
                (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                v8,
                (__int64)String);
            }
            FSString::~FSString((FSString *)v40, v25);
          }
          v8 = 0;
        }
      }
      PropVariantClear(pvar);
    }
    v27 = pv;
    if ( pv && v30 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, LPVOID))(*v18 + 208))(
              v18,
              FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
              pv);
      v8 = v21;
      if ( v21 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_47:
          v23 = pv;
          pv = 0;
          if ( v23 )
            CoTaskMemFree(v23);
          goto LABEL_68;
        }
        v22 = 264;
LABEL_46:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v21);
        goto LABEL_47;
      }
      v27 = pv;
    }
    pv = 0;
    if ( v27 )
      CoTaskMemFree(v27);
    goto LABEL_66;
  }
  if ( g_wppLevels )
  {
    v14 = 257;
    goto LABEL_13;
  }
LABEL_68:
  if ( v8 != -1072875819 )
    goto LABEL_69;
LABEL_71:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v28 = 266;
    goto LABEL_73;
  }
LABEL_74:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v37);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v34);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v35);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003896c  push    rbp
0x18003896e  push    rbx
0x18003896f  push    rsi
0x180038970  push    rdi
0x180038971  push    r12
0x180038973  push    r13
0x180038975  push    r14
0x180038977  push    r15
0x180038979  lea     rbp, [rsp-1Fh]
0x18003897e  sub     rsp, 0E8h
0x180038985  mov     rax, cs:__security_cookie
0x18003898c  xor     rax, rsp
0x18003898f  mov     [rbp+57h+var_50], rax
0x180038993  xor     esi, esi
0x180038995  mov     r13, r9
0x180038998  mov     [rbp+57h+var_D0], rsi
0x18003899c  mov     r12b, r8b
0x18003899f  mov     [rbp+57h+var_B8], rsi
0x1800389a3  mov     r15, rdx
0x1800389a6  mov     [rbp+57h+var_C0], rsi
0x1800389aa  mov     r14, rcx
0x1800389ad  mov     [rbp+57h+var_B0], esi
0x1800389b0  mov     [rbp+57h+var_C8], esi
0x1800389b3  mov     [rbp+57h+var_A8], rsi
0x1800389b7  test    rcx, rcx
0x1800389ba  jnz     short loc_1800389F6
0x1800389bc  mov     edi, 80070057h
0x1800389c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800389c8  jb      loc_180038F0D
0x1800389ce  mov     edx, 0FBh
0x1800389d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389da  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800389e1  xor     r9d, r9d
0x1800389e4  mov     dword ptr [rsp+120h+var_100], edi
0x1800389e8  mov     rcx, [rcx+10h]
0x1800389ec  call    WPP_SF_qD
0x1800389f1  jmp     loc_180038F0D
0x1800389f6  test    r13, r13
0x1800389f9  jnz     short loc_180038A14
0x1800389fb  mov     edi, 80004003h
0x180038a00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038a07  jb      loc_180038F0D
0x180038a0d  mov     edx, 0FCh
0x180038a12  jmp     short loc_1800389D3
0x180038a14  mov     [r9], rsi
0x180038a17  cmp     cs:byte_18005E5A5, 8
0x180038a1e  jb      short loc_180038A8E
0x180038a20  mov     rax, [rcx]
0x180038a23  mov     rax, [rax+48h]
0x180038a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a2c  mov     rsi, rax
0x180038a2f  mov     rcx, r14
0x180038a32  mov     rax, [r14]
0x180038a35  mov     rax, [rax+38h]
0x180038a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a3e  mov     rdi, rax
0x180038a41  mov     rcx, r14
0x180038a44  mov     rax, [r14]
0x180038a47  mov     rax, [rax+40h]
0x180038a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a50  mov     rbx, rax
0x180038a53  mov     rcx, r14
0x180038a56  mov     rax, [r14]
0x180038a59  mov     rax, [rax+30h]
0x180038a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a69  mov     edx, 0FDh
0x180038a6e  mov     [rsp+120h+var_F0], rsi; __int64
0x180038a73  mov     r9, rax
0x180038a76  mov     [rsp+120h+var_F8], rdi; __int64
0x180038a7b  mov     [rsp+120h+var_100], rbx; __int64
0x180038a80  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180038a87  call    WPP_SF_SSSS
0x180038a8c  xor     esi, esi
0x180038a8e  lea     r9, [rsp+120h+var_E0]; unsigned int *
0x180038a93  mov     [rsp+120h+var_E0], esi
0x180038a97  xor     r8d, r8d; unsigned int
0x180038a9a  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180038aa1  xor     edx, edx; unsigned __int16 *
0x180038aa3  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180038aa8  mov     edi, eax
0x180038aaa  test    eax, eax
0x180038aac  jns     short loc_180038AE3
0x180038aae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038ab5  jb      loc_180038F05
0x180038abb  mov     edx, 0FEh
0x180038ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ac7  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180038ace  xor     r9d, r9d
0x180038ad1  mov     dword ptr [rsp+120h+var_100], eax
0x180038ad5  mov     rcx, [rcx+10h]
0x180038ad9  call    WPP_SF_qD
0x180038ade  jmp     loc_180038F05
0x180038ae3  mov     edx, [rsp+120h+var_E0]
0x180038ae7  lea     rcx, [rsp+120h+pv]
0x180038aec  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180038af1  mov     rdx, rax
0x180038af4  lea     rcx, [rbp+57h+var_A8]
0x180038af8  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180038afd  lea     rcx, [rsp+120h+pv]
0x180038b02  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180038b07  mov     rbx, [rbp+57h+var_A8]
0x180038b0b  test    rbx, rbx
0x180038b0e  jnz     short loc_180038B2C
0x180038b10  mov     edi, 8007000Eh
0x180038b15  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038b1c  jb      loc_180038F0D
0x180038b22  mov     edx, 0FFh
0x180038b27  jmp     loc_1800389D3
0x180038b2c  mov     r8d, [rsp+120h+var_E0]; unsigned int
0x180038b31  lea     r9, [rsp+120h+var_E0]; unsigned int *
0x180038b36  mov     rdx, rbx; unsigned __int16 *
0x180038b39  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180038b40  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180038b45  mov     edi, eax
0x180038b47  test    eax, eax
0x180038b49  jns     short loc_180038B62
0x180038b4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038b52  jb      loc_180038F05
0x180038b58  mov     edx, 100h
0x180038b5d  jmp     loc_180038AC0
0x180038b62  mov     rcx, [rbp+57h+var_C0]
0x180038b66  mov     [rbp+57h+var_C0], rsi
0x180038b6a  test    rcx, rcx
0x180038b6d  jz      short loc_180038B7B
0x180038b6f  mov     rax, [rcx]
0x180038b72  mov     rax, [rax+10h]
0x180038b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b7b  mov     rax, [r14]
0x180038b7e  mov     rcx, r14
0x180038b81  mov     rax, [rax+38h]
0x180038b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b8a  lea     r9, [rbp+57h+var_C0]
0x180038b8e  mov     r8, rbx
0x180038b91  xor     edx, edx
0x180038b93  mov     rcx, rax; unsigned __int16 *
0x180038b96  call    FSCreateConfigurationKey
0x180038b9b  mov     edi, eax
0x180038b9d  test    eax, eax
0x180038b9f  jns     short loc_180038BB8
0x180038ba1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038ba8  jb      loc_180038F05
0x180038bae  mov     edx, 101h
0x180038bb3  jmp     loc_180038AC0
0x180038bb8  mov     rcx, [rbp+57h+var_C0]
0x180038bbc  mov     rdx, r14
0x180038bbf  mov     rax, [rcx]
0x180038bc2  mov     rax, [rax+18h]
0x180038bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bcb  lea     rcx, [rbp+57h+var_D0]
0x180038bcf  test    eax, eax
0x180038bd1  jnz     short loc_180038C0A
0x180038bd3  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180038bd8  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x180038bdc  mov     r8b, r12b; bool
0x180038bdf  mov     rdx, r15; struct _DEVPROPKEY *
0x180038be2  mov     rcx, r14; struct IFSConfigurationKey *
0x180038be5  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180038bea  xor     r15d, r15d
0x180038bed  mov     edi, eax
0x180038bef  test    eax, eax
0x180038bf1  jns     short loc_180038C61
0x180038bf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038bfa  jb      loc_180038F05
0x180038c00  mov     edx, 102h
0x180038c05  jmp     loc_180038AC0
0x180038c0a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180038c0f  mov     rcx, [rbp+57h+var_C0]; struct IFSConfigurationKey *
0x180038c13  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x180038c17  mov     r8b, r12b; bool
0x180038c1a  mov     rdx, r15; struct _DEVPROPKEY *
0x180038c1d  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180038c22  test    eax, eax
0x180038c24  jns     short loc_180038C6A
0x180038c26  lea     rcx, [rbp+57h+var_D0]
0x180038c2a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180038c2f  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x180038c33  mov     r8b, r12b; bool
0x180038c36  mov     rdx, r15; struct _DEVPROPKEY *
0x180038c39  mov     rcx, r14; struct IFSConfigurationKey *
0x180038c3c  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180038c41  xor     r15d, r15d
0x180038c44  mov     edi, eax
0x180038c46  test    eax, eax
0x180038c48  jns     short loc_180038C61
0x180038c4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180038c51  jb      loc_180038F05
0x180038c57  mov     edx, 103h
0x180038c5c  jmp     loc_180038AC0
0x180038c61  mov     rsi, [rbp+57h+var_D0]
0x180038c65  jmp     loc_180038EF9
0x180038c6a  mov     rsi, [rbp+57h+var_D0]
0x180038c6e  lea     rdx, [rbp+57h+var_B0]
0x180038c72  mov     rcx, rsi
0x180038c75  mov     rax, [rsi]
0x180038c78  mov     rax, [rax+0F0h]
0x180038c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c84  mov     edi, eax
0x180038c86  test    eax, eax
0x180038c88  jns     short loc_180038CA1
0x180038c8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038c91  jb      loc_180038F05
0x180038c97  mov     edx, 104h
0x180038c9c  jmp     loc_180038AC0
0x180038ca1  lea     rcx, [rbp+57h+var_B8]
0x180038ca5  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180038caa  lea     r9, [rbp+57h+var_B8]; struct IFSConfiguration **
0x180038cae  mov     r8b, r12b; bool
0x180038cb1  mov     rdx, r15; struct _DEVPROPKEY *
0x180038cb4  mov     rcx, r14; struct IFSConfigurationKey *
0x180038cb7  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180038cbc  xor     r15d, r15d
0x180038cbf  test    eax, eax
0x180038cc1  js      loc_180038EF9
0x180038cc7  mov     rbx, [rbp+57h+var_B8]
0x180038ccb  lea     rax, [rsp+120h+pv]
0x180038cd0  mov     rdx, rbx
0x180038cd3  mov     [rsp+120h+var_E0], r15d
0x180038cd8  lea     r9, [rsp+120h+var_E0]
0x180038cdd  mov     [rsp+120h+pv], r15
0x180038ce2  lea     r8, [rbp+57h+var_68.Data4]
0x180038ce6  mov     qword ptr [rbp+57h+var_68.Data1], rax
0x180038cea  mov     rcx, rsi
0x180038ced  mov     qword ptr [rbp+57h+var_68.Data4], r15
0x180038cf1  mov     [rbp+57h+var_58], 1
0x180038cf5  call    FSMergeCameraControlConfigurations
0x180038cfa  lea     rcx, [rbp+57h+var_68]
0x180038cfe  mov     edi, eax
0x180038d00  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180038d05  mov     eax, edi
0x180038d07  shr     eax, 1Fh
0x180038d0a  test    al, al
0x180038d0c  jz      short loc_180038D58
0x180038d0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038d15  jb      short loc_180038D3A
0x180038d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d1e  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180038d25  mov     edx, 105h
0x180038d2a  mov     dword ptr [rsp+120h+var_100], edi
0x180038d2e  xor     r9d, r9d
0x180038d31  mov     rcx, [rcx+10h]
0x180038d35  call    WPP_SF_qD
0x180038d3a  mov     rcx, [rsp+120h+pv]; pv
0x180038d3f  mov     [rsp+120h+pv], r15
0x180038d44  test    rcx, rcx
0x180038d47  jz      loc_180038F01
0x180038d4d  call    cs:__imp_CoTaskMemFree
0x180038d53  jmp     loc_180038F01
0x180038d58  mov     rax, [rbx]
0x180038d5b  lea     rdx, [rbp+57h+var_C8]
0x180038d5f  mov     rcx, rbx
0x180038d62  mov     rax, [rax+0F0h]
0x180038d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d6e  mov     edi, eax
0x180038d70  test    eax, eax
0x180038d72  jns     short loc_180038DBE
0x180038d74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038d7b  jb      short loc_180038DA0
0x180038d7d  mov     edx, 106h
0x180038d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d89  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180038d90  xor     r9d, r9d
0x180038d93  mov     dword ptr [rsp+120h+var_100], eax
0x180038d97  mov     rcx, [rcx+10h]
0x180038d9b  call    WPP_SF_qD
0x180038da0  mov     rcx, [rsp+120h+pv]; pv
0x180038da5  mov     [rsp+120h+pv], r15
0x180038daa  test    rcx, rcx
0x180038dad  jz      loc_180038F05
0x180038db3  call    cs:__imp_CoTaskMemFree
0x180038db9  jmp     loc_180038F05
0x180038dbe  mov     r14d, r15d
0x180038dc1  cmp     [rbp+57h+var_C8], r15d
0x180038dc5  jbe     loc_180038E97
0x180038dcb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180038dd2  xor     eax, eax
0x180038dd4  lea     r9, [rbp+57h+pvar]
0x180038dd8  mov     [rbp+57h+var_90], rax
0x180038ddc  lea     r8, [rbp+57h+var_68]
0x180038de0  xorps   xmm1, xmm1
0x180038de3  mov     edx, r14d
0x180038de6  movdqu  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x180038deb  mov     rcx, rbx
0x180038dee  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x180038df2  mov     rax, [rbx]
0x180038df5  mov     rax, [rax+0F8h]
0x180038dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e01  test    eax, eax
0x180038e03  js      short loc_180038E80
0x180038e05  mov     rax, [rsi]
0x180038e08  lea     r8, [rbp+57h+pvar]
0x180038e0c  lea     rdx, [rbp+57h+var_68]
0x180038e10  mov     rcx, rsi
0x180038e13  mov     rax, [rax+90h]
0x180038e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e1f  mov     edi, eax
0x180038e21  test    eax, eax
0x180038e23  jns     short loc_180038E80
0x180038e25  cmp     cs:byte_18005E5A5, 10h
0x180038e2c  jb      short loc_180038E7D
  ... truncated ...
```
