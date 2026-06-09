# FSLoadDeviceConfiguration_Base

- ea: `0x180033458`
- end: `0x180033aa8`
- name: `FSLoadDeviceConfiguration_Base`
- size: `1616`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *, struct _DEVPROPKEY *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180033ab0`

## callees

- `0x180003e20`
- `0x1800041f0`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180009fac`
- `0x18000a91c`
- `0x1800269b0`
- `0x18002a920`
- `0x18002db74`
- `0x18002fbe0`
- `0x180030f00`
- `0x180033458`
- `0x180034a84`
- `0x180036ca4`
- `0x18004d714`
- `0x18004da70`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003383f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003383f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033977`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033977`

## string_xrefs

- `0x180033597`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x18003363c`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadDeviceConfiguration_Base(
        struct IFSConfigurationKey *a1,
        struct _DEVPROPKEY *a2,
        bool a3,
        __int64 **a4)
{
  unsigned __int16 *v7; // r15
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 unique; // rax
  void *v16; // rcx
  unsigned __int16 *v17; // rax
  __int64 *v18; // rsi
  struct IFSConfiguration *v19; // rbx
  void *v20; // rcx
  int v21; // eax
  void *v22; // rcx
  unsigned int i; // r14d
  const char *String; // rax
  void *v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  unsigned int v29; // [rsp+40h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-81h] BYREF
  struct IFSConfiguration *v31; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-71h] BYREF
  struct IFSConfigurationKey *v33; // [rsp+60h] [rbp-69h] BYREF
  struct IFSConfiguration *v34; // [rsp+68h] [rbp-61h] BYREF
  int v35; // [rsp+70h] [rbp-59h] BYREF
  __int64 **v36; // [rsp+78h] [rbp-51h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v38; // [rsp+90h] [rbp-39h]
  _BYTE v39[32]; // [rsp+98h] [rbp-31h] BYREF
  struct _GUID v40; // [rsp+B8h] [rbp-11h] BYREF
  char v41; // [rsp+C8h] [rbp-1h]

  v31 = 0;
  v36 = a4;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v7 = 0;
  v32 = 0;
  *(_QWORD *)&v40.Data1 = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_68:
      if ( !byte_18010EC4D )
        goto LABEL_73;
      v27 = 265;
      goto LABEL_72;
    }
    v9 = 251;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v8);
    goto LABEL_68;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_68;
    v9 = 252;
    goto LABEL_4;
  }
  *a4 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
    v11 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v12 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
    WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, v11, v10);
  }
  v29 = 0;
  v13 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v29);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_67;
    v14 = 254;
    goto LABEL_13;
  }
  unique = wil::make_unique_nothrow<unsigned short [0]>(&pv, v29);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v40, unique);
  v16 = pv;
  pv = 0;
  if ( v16 )
    operator delete(v16, (const struct std::nothrow_t *)a2);
  v7 = *(unsigned __int16 **)&v40.Data1;
  if ( !*(_QWORD *)&v40.Data1 )
  {
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_68;
    v9 = 255;
    goto LABEL_4;
  }
  v13 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", *(unsigned __int16 **)&v40.Data1, v29, &v29);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v14 = 256;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v13);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v33);
  v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
  v13 = FSCreateConfigurationKey(v17, 0, v7, &v33);
  v8 = v13;
  if ( v13 >= 0 )
  {
    if ( !(*(unsigned int (__fastcall **)(struct IFSConfigurationKey *, struct IFSConfigurationKey *))(*(_QWORD *)v33 + 24LL))(
            v33,
            a1) )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v31);
      v13 = FSLoadV1OrV2(a1, a2, a3, &v31);
      v8 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 258;
          goto LABEL_13;
        }
        goto LABEL_67;
      }
      goto LABEL_33;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v31);
    if ( (int)FSLoadV1OrV2(v33, a2, a3, &v31) < 0 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v31);
      v13 = FSLoadV1OrV2(a1, a2, a3, &v31);
      v8 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels >= 8u )
        {
          v14 = 259;
          goto LABEL_13;
        }
        goto LABEL_67;
      }
LABEL_33:
      v18 = (__int64 *)v31;
LABEL_65:
      v31 = 0;
      *v36 = v18;
      goto LABEL_66;
    }
    v18 = (__int64 *)v31;
    v13 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, int *))(*(_QWORD *)v31 + 240LL))(v31, &v35);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 260;
        goto LABEL_13;
      }
      goto LABEL_67;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v34);
    if ( (int)FSLoadV1OrV2(a1, a2, a3, &v34) < 0 )
      goto LABEL_65;
    v29 = 0;
    pv = 0;
    *(_QWORD *)v40.Data4 = 0;
    v19 = v34;
    *(_QWORD *)&v40.Data1 = &pv;
    v41 = 1;
    v8 = FSMergeCameraControlConfigurations(v18, (__int64 *)v34, (LPVOID *)v40.Data4, &v29);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v40);
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v8);
      v20 = pv;
      pv = 0;
      if ( v20 )
        CoTaskMemFree(v20);
LABEL_66:
      if ( v8 >= 0 )
        goto LABEL_70;
      goto LABEL_67;
    }
    v21 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, unsigned int *))(*(_QWORD *)v19 + 240LL))(v19, &v32);
    v8 = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v21);
LABEL_46:
      v22 = pv;
      pv = 0;
      if ( v22 )
        CoTaskMemFree(v22);
      goto LABEL_67;
    }
    for ( i = 0; i < v32; ++i )
    {
      v38 = 0;
      v40 = GUID_00000000_0000_0000_0000_000000000000;
      *(_OWORD *)pvar = 0;
      if ( (*(int (__fastcall **)(struct IFSConfiguration *, _QWORD, struct _GUID *, PROPVARIANT *))(*(_QWORD *)v19 + 248LL))(
             v19,
             i,
             &v40,
             pvar) >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, PROPVARIANT *))(*v18 + 144))(v18, &v40, pvar);
        if ( v8 < 0 )
        {
          if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
          {
            GuidTrace::GuidTrace((GuidTrace *)v39, &v40);
            if ( byte_18010EC4D )
            {
              String = GuidTrace::GetString((GuidTrace *)v39);
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                263,
                (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                v8,
                (__int64)String);
            }
            FSString::~FSString((FSString *)v39);
          }
          v8 = 0;
        }
      }
      PropVariantClear(pvar);
    }
    v25 = pv;
    if ( pv && v29 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64 *, void *, LPVOID))(*v18 + 208))(
              v18,
              &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
              pv);
      v8 = v26;
      if ( v26 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v26);
        goto LABEL_46;
      }
      v25 = pv;
    }
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    goto LABEL_65;
  }
  if ( g_wppLevels )
  {
    v14 = 257;
    goto LABEL_13;
  }
LABEL_67:
  if ( v8 != -1072875819 )
    goto LABEL_68;
LABEL_70:
  if ( (unsigned __int8)byte_18010EC4D < 8u )
    goto LABEL_73;
  v27 = 266;
LABEL_72:
  WPP_SF_d(
    *((_QWORD *)WPP_GLOBAL_Control + 27),
    v27,
    &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
    (unsigned int)v8);
LABEL_73:
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)a2);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033458  push    rbp
0x18003345a  push    rbx
0x18003345b  push    rsi
0x18003345c  push    rdi
0x18003345d  push    r12
0x18003345f  push    r13
0x180033461  push    r14
0x180033463  push    r15
0x180033465  lea     rbp, [rsp-1Fh]
0x18003346a  sub     rsp, 0E8h
0x180033471  mov     rax, cs:__security_cookie
0x180033478  xor     rax, rsp
0x18003347b  mov     [rbp+57h+var_50], rax
0x18003347f  xor     ebx, ebx
0x180033481  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033488  mov     [rbp+57h+var_D0], rbx
0x18003348c  mov     rax, r9
0x18003348f  mov     [rbp+57h+var_A8], rax
0x180033493  mov     r13b, r8b
0x180033496  mov     [rbp+57h+var_B8], rbx
0x18003349a  mov     r12, rdx
0x18003349d  mov     [rbp+57h+var_C0], rbx
0x1800334a1  mov     r14, rcx
0x1800334a4  mov     [rbp+57h+var_B0], ebx
0x1800334a7  mov     r15d, ebx
0x1800334aa  mov     [rbp+57h+var_C8], ebx
0x1800334ad  mov     qword ptr [rbp+57h+var_68.Data1], rbx
0x1800334b1  test    rcx, rcx
0x1800334b4  jnz     short loc_1800334EC
0x1800334b6  mov     edi, 80070057h
0x1800334bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800334c2  jb      loc_180033A23
0x1800334c8  mov     edx, 0FBh
0x1800334cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334d4  xor     r9d, r9d
0x1800334d7  mov     r8, rsi
0x1800334da  mov     dword ptr [rsp+120h+var_100], edi
0x1800334de  mov     rcx, [rcx+10h]
0x1800334e2  call    WPP_SF_qD
0x1800334e7  jmp     loc_180033A23
0x1800334ec  test    rax, rax
0x1800334ef  jnz     short loc_18003350A
0x1800334f1  mov     edi, 80004003h
0x1800334f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800334fd  jb      loc_180033A23
0x180033503  mov     edx, 0FCh
0x180033508  jmp     short loc_1800334CD
0x18003350a  mov     [r9], rbx
0x18003350d  cmp     cs:byte_18010EC4D, 8
0x180033514  jb      short loc_18003358B
0x180033516  mov     rax, [rcx]
0x180033519  mov     rax, [rax+48h]
0x18003351d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033522  mov     rsi, rax
0x180033525  mov     rcx, r14
0x180033528  mov     rax, [r14]
0x18003352b  mov     rax, [rax+38h]
0x18003352f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033534  mov     rdi, rax
0x180033537  mov     rcx, r14
0x18003353a  mov     rax, [r14]
0x18003353d  mov     rax, [rax+40h]
0x180033541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033546  mov     rbx, rax
0x180033549  mov     rcx, r14
0x18003354c  mov     rax, [r14]
0x18003354f  mov     rax, [rax+30h]
0x180033553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033558  mov     rcx, cs:WPP_GLOBAL_Control
0x18003355f  mov     edx, 0FDh
0x180033564  mov     [rsp+120h+var_F0], rsi; __int64
0x180033569  mov     r9, rax
0x18003356c  mov     [rsp+120h+var_F8], rdi; __int64
0x180033571  mov     [rsp+120h+var_100], rbx; __int64
0x180033576  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003357d  call    WPP_SF_SSSS
0x180033582  xor     ebx, ebx
0x180033584  lea     rsi, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003358b  lea     r9, [rsp+120h+var_E0]; unsigned int *
0x180033590  mov     [rsp+120h+var_E0], ebx
0x180033594  xor     r8d, r8d; unsigned int
0x180033597  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x18003359e  xor     edx, edx; unsigned __int16 *
0x1800335a0  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x1800335a5  mov     edi, eax
0x1800335a7  test    eax, eax
0x1800335a9  jns     short loc_1800335DC
0x1800335ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800335b2  jb      loc_180033A1B
0x1800335b8  mov     edx, 0FEh
0x1800335bd  mov     r8, rsi
0x1800335c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335c7  xor     r9d, r9d
0x1800335ca  mov     dword ptr [rsp+120h+var_100], eax
0x1800335ce  mov     rcx, [rcx+10h]
0x1800335d2  call    WPP_SF_qD
0x1800335d7  jmp     loc_180033A1B
0x1800335dc  mov     edx, [rsp+120h+var_E0]
0x1800335e0  lea     rcx, [rsp+120h+pv]
0x1800335e5  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800335ea  mov     rdx, rax
0x1800335ed  lea     rcx, [rbp+57h+var_68]
0x1800335f1  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x1800335f6  mov     rcx, [rsp+120h+pv]; void *
0x1800335fb  mov     [rsp+120h+pv], rbx
0x180033600  test    rcx, rcx
0x180033603  jz      short loc_18003360A
0x180033605  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003360a  mov     r15, qword ptr [rbp+57h+var_68.Data1]
0x18003360e  test    r15, r15
0x180033611  jnz     short loc_18003362F
0x180033613  mov     edi, 8007000Eh
0x180033618  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003361f  jb      loc_180033A23
0x180033625  mov     edx, 0FFh
0x18003362a  jmp     loc_1800334CD
0x18003362f  mov     r8d, [rsp+120h+var_E0]; unsigned int
0x180033634  lea     r9, [rsp+120h+var_E0]; unsigned int *
0x180033639  mov     rdx, r15; unsigned __int16 *
0x18003363c  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x180033643  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180033648  mov     edi, eax
0x18003364a  test    eax, eax
0x18003364c  jns     short loc_180033665
0x18003364e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033655  jb      loc_180033A1B
0x18003365b  mov     edx, 100h
0x180033660  jmp     loc_1800335BD
0x180033665  lea     rcx, [rbp+57h+var_C0]
0x180033669  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003366e  mov     rax, [r14]
0x180033671  mov     rcx, r14
0x180033674  mov     rax, [rax+38h]
0x180033678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003367d  lea     r9, [rbp+57h+var_C0]; struct IFSConfigurationKey **
0x180033681  mov     r8, r15; unsigned __int16 *
0x180033684  xor     edx, edx; unsigned __int16 *
0x180033686  mov     rcx, rax; unsigned __int16 *
0x180033689  call    FSCreateConfigurationKey
0x18003368e  mov     edi, eax
0x180033690  test    eax, eax
0x180033692  jns     short loc_1800336AB
0x180033694  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003369b  jb      loc_180033A1B
0x1800336a1  mov     edx, 101h
0x1800336a6  jmp     loc_1800335BD
0x1800336ab  mov     rcx, [rbp+57h+var_C0]
0x1800336af  mov     rdx, r14
0x1800336b2  mov     rax, [rcx]
0x1800336b5  mov     rax, [rax+18h]
0x1800336b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336be  lea     rcx, [rbp+57h+var_D0]
0x1800336c2  test    eax, eax
0x1800336c4  jnz     short loc_1800336FA
0x1800336c6  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800336cb  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x1800336cf  mov     r8b, r13b; bool
0x1800336d2  mov     rdx, r12; struct _DEVPROPKEY *
0x1800336d5  mov     rcx, r14; struct IFSConfigurationKey *
0x1800336d8  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x1800336dd  mov     edi, eax
0x1800336df  test    eax, eax
0x1800336e1  jns     short loc_18003374E
0x1800336e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800336ea  jb      loc_180033A1B
0x1800336f0  mov     edx, 102h
0x1800336f5  jmp     loc_1800335BD
0x1800336fa  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800336ff  mov     rcx, [rbp+57h+var_C0]; struct IFSConfigurationKey *
0x180033703  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x180033707  mov     r8b, r13b; bool
0x18003370a  mov     rdx, r12; struct _DEVPROPKEY *
0x18003370d  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180033712  test    eax, eax
0x180033714  jns     short loc_180033757
0x180033716  lea     rcx, [rbp+57h+var_D0]
0x18003371a  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003371f  lea     r9, [rbp+57h+var_D0]; struct IFSConfiguration **
0x180033723  mov     r8b, r13b; bool
0x180033726  mov     rdx, r12; struct _DEVPROPKEY *
0x180033729  mov     rcx, r14; struct IFSConfigurationKey *
0x18003372c  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x180033731  mov     edi, eax
0x180033733  test    eax, eax
0x180033735  jns     short loc_18003374E
0x180033737  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18003373e  jb      loc_180033A1B
0x180033744  mov     edx, 103h
0x180033749  jmp     loc_1800335BD
0x18003374e  mov     rsi, [rbp+57h+var_D0]
0x180033752  jmp     loc_180033A0C
0x180033757  mov     rsi, [rbp+57h+var_D0]
0x18003375b  lea     rdx, [rbp+57h+var_B0]
0x18003375f  mov     rcx, rsi
0x180033762  mov     rax, [rsi]
0x180033765  mov     rax, [rax+0F0h]
0x18003376c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033771  mov     edi, eax
0x180033773  test    eax, eax
0x180033775  jns     short loc_180033795
0x180033777  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003377e  jb      loc_180033A1B
0x180033784  mov     edx, 104h
0x180033789  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033790  jmp     loc_1800335C0
0x180033795  lea     rcx, [rbp+57h+var_B8]
0x180033799  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003379e  lea     r9, [rbp+57h+var_B8]; struct IFSConfiguration **
0x1800337a2  mov     r8b, r13b; bool
0x1800337a5  mov     rdx, r12; struct _DEVPROPKEY *
0x1800337a8  mov     rcx, r14; struct IFSConfigurationKey *
0x1800337ab  call    ?FSLoadV1OrV2@@YAJPEAUIFSConfigurationKey@@AEBU_DEVPROPKEY@@_NPEAPEAUIFSConfiguration@@@Z; FSLoadV1OrV2(IFSConfigurationKey *,_DEVPROPKEY const &,bool,IFSConfiguration * *)
0x1800337b0  test    eax, eax
0x1800337b2  js      loc_180033A0C
0x1800337b8  mov     [rsp+120h+var_E0], ebx
0x1800337bc  lea     rax, [rsp+120h+pv]
0x1800337c1  mov     [rsp+120h+pv], rbx
0x1800337c6  lea     r9, [rsp+120h+var_E0]
0x1800337cb  mov     qword ptr [rbp+57h+var_68.Data4], rbx
0x1800337cf  lea     r8, [rbp+57h+var_68.Data4]
0x1800337d3  mov     rbx, [rbp+57h+var_B8]
0x1800337d7  mov     rcx, rsi
0x1800337da  mov     rdx, rbx
0x1800337dd  mov     qword ptr [rbp+57h+var_68.Data1], rax
0x1800337e1  mov     [rbp+57h+var_58], 1
0x1800337e5  call    FSMergeCameraControlConfigurations
0x1800337ea  lea     rcx, [rbp+57h+var_68]
0x1800337ee  mov     edi, eax
0x1800337f0  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800337f5  mov     eax, edi
0x1800337f7  shr     eax, 1Fh
0x1800337fa  test    al, al
0x1800337fc  jz      short loc_18003384A
0x1800337fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033805  jb      short loc_18003382A
0x180033807  mov     rcx, cs:WPP_GLOBAL_Control
0x18003380e  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033815  mov     edx, 105h
0x18003381a  mov     dword ptr [rsp+120h+var_100], edi
0x18003381e  xor     r9d, r9d
0x180033821  mov     rcx, [rcx+10h]
0x180033825  call    WPP_SF_qD
0x18003382a  mov     rcx, [rsp+120h+pv]; pv
0x18003382f  xor     ebx, ebx
0x180033831  mov     [rsp+120h+pv], rbx
0x180033836  test    rcx, rcx
0x180033839  jz      loc_180033A17
0x18003383f  call    cs:__imp_CoTaskMemFree
0x180033845  jmp     loc_180033A17
0x18003384a  mov     rax, [rbx]
0x18003384d  lea     rdx, [rbp+57h+var_C8]
0x180033851  mov     rcx, rbx
0x180033854  mov     rax, [rax+0F0h]
0x18003385b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033860  mov     edi, eax
0x180033862  test    eax, eax
0x180033864  jns     short loc_1800338B2
0x180033866  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003386d  jb      short loc_180033892
0x18003386f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033876  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003387d  mov     edx, 106h
0x180033882  mov     dword ptr [rsp+120h+var_100], eax
0x180033886  xor     r9d, r9d
0x180033889  mov     rcx, [rcx+10h]
0x18003388d  call    WPP_SF_qD
0x180033892  xor     ebx, ebx
0x180033894  mov     rcx, [rsp+120h+pv]; pv
0x180033899  mov     [rsp+120h+pv], rbx
0x18003389e  test    rcx, rcx
0x1800338a1  jz      loc_180033A1B
0x1800338a7  call    cs:__imp_CoTaskMemFree
0x1800338ad  jmp     loc_180033A1B
0x1800338b2  xor     r14d, r14d
0x1800338b5  cmp     [rbp+57h+var_C8], r14d
0x1800338b9  jbe     loc_18003398A
0x1800338bf  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800338c6  lea     r9, [rbp+57h+pvar]
0x1800338ca  xor     eax, eax
0x1800338cc  lea     r8, [rbp+57h+var_68]
0x1800338d0  mov     [rbp+57h+var_90], rax
0x1800338d4  xorps   xmm1, xmm1
0x1800338d7  movdqu  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x1800338dc  mov     edx, r14d
0x1800338df  mov     rcx, rbx
0x1800338e2  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x1800338e6  mov     rax, [rbx]
0x1800338e9  mov     rax, [rax+0F8h]
0x1800338f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338f5  test    eax, eax
0x1800338f7  js      short loc_180033973
0x1800338f9  mov     rax, [rsi]
0x1800338fc  lea     r8, [rbp+57h+pvar]
0x180033900  lea     rdx, [rbp+57h+var_68]
0x180033904  mov     rcx, rsi
0x180033907  mov     rax, [rax+90h]
0x18003390e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033913  mov     edi, eax
0x180033915  test    eax, eax
0x180033917  jns     short loc_180033973
  ... truncated ...
```
