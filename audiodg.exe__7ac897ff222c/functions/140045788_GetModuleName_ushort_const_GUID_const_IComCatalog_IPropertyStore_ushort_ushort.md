# GetModuleName(ushort const *,_GUID const &,IComCatalog *,IPropertyStore *,ushort * *,ushort * *)

- ea: `0x140045788`
- end: `0x140045a6d`
- name: `?GetModuleName@@YAXPEBGAEBU_GUID@@PEAUIComCatalog@@PEAUIPropertyStore@@PEAPEAG4@Z`
- size: `741`
- prototype: `void __fastcall(const unsigned __int16 *, const struct _GUID *, struct IComCatalog *, struct IPropertyStore *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140054f5c`

## callees

- `0x140008124`
- `0x14000f3f8`
- `0x140016f68`
- `0x140022368`
- `0x140022930`
- `0x140031a68`
- `0x140035554`
- `0x140035794`
- `0x140045788`
- `0x140045a74`
- `0x140045b80`
- `0x140051f2c`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045a32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045a26`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140045a10`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140045a43`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140045a10`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x140045a43`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045833`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045906`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045833`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x140045906`

## pseudocode

```c
void __fastcall GetModuleName(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        struct IComCatalog *a3,
        struct IPropertyStore *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  __int64 v9; // rax
  int v10; // eax
  int *v11; // rdx
  unsigned __int16 *v12; // rax
  int DeviceInstanceId; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  int *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  unsigned __int16 *v21; // rax
  void *v22; // rcx
  const char *v23; // r9
  int N; // [rsp+20h] [rbp-F8h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-E8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+70h] [rbp-A8h]
  int v33[2]; // [rsp+78h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+80h] [rbp-98h] BYREF
  int v35[2]; // [rsp+88h] [rbp-90h]
  unsigned __int64 v36; // [rsp+90h] [rbp-88h]
  __int128 v37; // [rsp+98h] [rbp-80h]
  int v38; // [rsp+A8h] [rbp-70h]
  _BYTE v39[32]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v37 = 0u;
  v37 = (__int128)*a2;
  v38 = 100;
  v30 = 0;
  *(_OWORD *)pvar = 0;
  v32 = 0;
  try
  {
    if ( ((int (*)(void))a4->lpVtbl->GetValue)() >= 0 && LOWORD(pvar[0]) == 31 )
    {
      v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&long CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(&v30);
      v10 = CoRegisterDeviceCatalog(pvar[1], v9);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
          (const char *)(unsigned int)v10,
          N);
      std::wstring::wstring(v33, pvar[1]);
      v11 = v33;
      if ( v36 > 7 )
        v11 = *(int **)v33;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v25,
        v11);
      v12 = v25;
      if ( v25 )
      {
        v25 = 0;
        *a6 = v12;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      std::wstring::~wstring(v33);
    }
    pv = 0;
    v29 = 0;
    *(_QWORD *)v33 = &pv;
    v34 = 0;
    LOBYTE(v35[0]) = 1;
    DeviceInstanceId = GetDeviceInstanceId(a1, &v34);
    wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v33);
    if ( DeviceInstanceId >= 0 )
    {
      v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&long CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(&v29);
      CoRegisterDeviceCatalog(pv, v14);
    }
    v28 = 0;
    v15 = *(_QWORD *)a3;
    v27 = 0;
    if ( (*(int (__fastcall **)(struct IComCatalog *, const struct _GUID *, GUID *, __int64 *))(v15 + 24))(
           a3,
           a2,
           &GUID_000001e2_0000_0000_c000_000000000046,
           &v27) >= 0
      && (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, 1, &v28) >= 0 )
    {
      std::wstring::wstring(v33, v28);
      v18 = v33;
      if ( v36 > 7 )
        LODWORD(v18) = v33[0];
      v19 = std::_Traits_find_last_of<std::char_traits<unsigned short>>((int)v18, v35[0], v16, v17, 2u);
      v20 = (_QWORD *)std::wstring::substr(v33, v39, v19 + 1);
      if ( v20[3] > 7u )
        v20 = (_QWORD *)*v20;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v25,
        v20);
      std::wstring::~wstring(v39);
      v21 = v25;
      if ( v25 )
      {
        v25 = 0;
        *a5 = v21;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      std::wstring::~wstring(v33);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    if ( v29 )
      CoRevokeDeviceCatalog();
    v22 = pv;
    pv = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    PropVariantClear(pvar);
    if ( v30 )
      CoRevokeDeviceCatalog();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6D,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      v23);
  }
}

```

## disassembly

```asm
0x140045788  mov     r11, rsp
0x14004578b  push    rbx
0x14004578c  push    rsi
0x14004578d  push    rdi
0x14004578e  push    r12
0x140045790  push    r14
0x140045792  push    r15
0x140045794  sub     rsp, 0E8h
0x14004579b  mov     rax, cs:__security_cookie
0x1400457a2  xor     rax, rsp
0x1400457a5  mov     [rsp+118h+var_48], rax
0x1400457ad  mov     rdi, r8
0x1400457b0  mov     r14, rdx
0x1400457b3  mov     rsi, rcx
0x1400457b6  mov     r15, [rsp+118h+arg_20]
0x1400457be  mov     rbx, [rsp+118h+arg_28]
0x1400457c6  xor     r12d, r12d
0x1400457c9  mov     [r11-80h], r12
0x1400457cd  mov     [r11-78h], r12
0x1400457d1  movups  xmm0, xmmword ptr [rdx]
0x1400457d4  movups  xmmword ptr [r11-80h], xmm0
0x1400457d9  mov     dword ptr [r11-70h], 64h ; 'd'
0x1400457e1  mov     [rsp+118h+var_C0], r12
0x1400457e6  xorps   xmm0, xmm0
0x1400457e9  xor     eax, eax
0x1400457eb  movups  xmmword ptr [rsp+118h+pvar], xmm0
0x1400457f0  mov     [rsp+118h+var_A8], rax
0x1400457f5  mov     rax, [r9]
0x1400457f8  lea     r8, [rsp+118h+pvar]
0x1400457fd  lea     rdx, [r11-80h]
0x140045801  mov     rcx, r9
0x140045804  mov     rax, [rax+28h]
0x140045808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004580d  test    eax, eax
0x14004580f  js      loc_1400458AC
0x140045815  cmp     word ptr [rsp+118h+pvar], 1Fh
0x14004581b  jnz     loc_1400458AC
0x140045821  lea     rcx, [rsp+118h+var_C0]
0x140045826  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUCO_DEVICE_CATALOG_COOKIE__@@P6AJPEAU1@@Z$1?CoRevokeDeviceCatalog@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUCO_DEVICE_CATALOG_COOKIE__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(void)
0x14004582b  mov     rdx, rax
0x14004582e  mov     rcx, [rsp+118h+pvar+8]
0x140045833  call    cs:__imp_CoRegisterDeviceCatalog
0x140045839  mov     rcx, [rsp+118h]; this
0x140045841  test    eax, eax
0x140045843  jns     short loc_140045859
0x140045845  mov     r9d, eax; char *
0x140045848  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004584f  lea     edx, [r12+50h]; void *
0x140045854  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140045859  mov     rdx, [rsp+118h+pvar+8]
0x14004585e  lea     rcx, [rsp+118h+var_A0]
0x140045863  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140045868  lea     rdx, [rsp+118h+var_A0]
0x14004586d  cmp     [rsp+118h+var_88], 7
0x140045876  cmova   rdx, qword ptr [rsp+118h+var_A0]
0x14004587c  lea     rcx, [rsp+118h+var_E8]
0x140045881  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140045886  mov     rax, [rsp+118h+var_E8]
0x14004588b  test    rax, rax
0x14004588e  jz      short loc_140045898
0x140045890  mov     [rsp+118h+var_E8], r12
0x140045895  mov     [rbx], rax
0x140045898  lea     rcx, [rsp+118h+var_E8]
0x14004589d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400458a2  lea     rcx, [rsp+118h+var_A0]
0x1400458a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400458ac  mov     [rsp+118h+pv], r12
0x1400458b1  mov     [rsp+118h+var_C8], r12
0x1400458b6  lea     rax, [rsp+118h+pv]
0x1400458bb  mov     qword ptr [rsp+118h+var_A0], rax
0x1400458c0  mov     [rsp+118h+var_98], r12
0x1400458c8  mov     byte ptr [rsp+118h+var_90], 1
0x1400458d0  lea     rdx, [rsp+118h+var_98]; unsigned __int16 **
0x1400458d8  mov     rcx, rsi; unsigned __int16 *
0x1400458db  call    ?GetDeviceInstanceId@@YAJPEBGPEAPEAG@Z; GetDeviceInstanceId(ushort const *,ushort * *)
0x1400458e0  mov     ebx, eax
0x1400458e2  lea     rcx, [rsp+118h+var_A0]
0x1400458e7  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1400458ec  shr     ebx, 1Fh
0x1400458ef  xor     bl, 1
0x1400458f2  jz      short loc_14004590C
0x1400458f4  lea     rcx, [rsp+118h+var_C8]
0x1400458f9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUCO_DEVICE_CATALOG_COOKIE__@@P6AJPEAU1@@Z$1?CoRevokeDeviceCatalog@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUCO_DEVICE_CATALOG_COOKIE__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<CO_DEVICE_CATALOG_COOKIE__ *,long (*)(CO_DEVICE_CATALOG_COOKIE__ *),&CoRevokeDeviceCatalog(CO_DEVICE_CATALOG_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_DEVICE_CATALOG_COOKIE__ *,CO_DEVICE_CATALOG_COOKIE__ *,0,std::nullptr_t>>>::put(void)
0x1400458fe  mov     rdx, rax
0x140045901  mov     rcx, [rsp+118h+pv]
0x140045906  call    cs:__imp_CoRegisterDeviceCatalog
0x14004590c  mov     [rsp+118h+var_D0], r12
0x140045911  mov     rax, [rdi]
0x140045914  mov     [rsp+118h+var_D8], r12
0x140045919  lea     r9, [rsp+118h+var_D8]
0x14004591e  lea     r8, _GUID_000001e2_0000_0000_c000_000000000046
0x140045925  mov     rdx, r14
0x140045928  mov     rcx, rdi
0x14004592b  mov     rax, [rax+18h]
0x14004592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045934  test    eax, eax
0x140045936  js      loc_1400459FB
0x14004593c  mov     rcx, [rsp+118h+var_D8]
0x140045941  mov     rax, [rcx]
0x140045944  lea     r8, [rsp+118h+var_D0]
0x140045949  mov     edx, 1
0x14004594e  mov     rax, [rax+20h]
0x140045952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045957  test    eax, eax
0x140045959  js      loc_1400459FB
0x14004595f  mov     rdx, [rsp+118h+var_D0]
0x140045964  lea     rcx, [rsp+118h+var_A0]
0x140045969  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14004596e  nop
0x14004596f  lea     rcx, [rsp+118h+var_A0]
0x140045974  cmp     [rsp+118h+var_88], 7
0x14004597d  cmova   rcx, qword ptr [rsp+118h+var_A0]; int
0x140045983  mov     qword ptr [rsp+118h+N], 2; N
0x14004598c  mov     rdx, qword ptr [rsp+118h+var_90]; int
0x140045994  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x140045999  lea     r8, [rax+1]
0x14004599d  lea     rdx, [rsp+118h+var_68]
0x1400459a5  lea     rcx, [rsp+118h+var_A0]
0x1400459aa  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1400459af  cmp     qword ptr [rax+18h], 7
0x1400459b4  jbe     short loc_1400459B9
0x1400459b6  mov     rax, [rax]
0x1400459b9  mov     rdx, rax
0x1400459bc  lea     rcx, [rsp+118h+var_E8]
0x1400459c1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400459c6  lea     rcx, [rsp+118h+var_68]
0x1400459ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400459d3  mov     rax, [rsp+118h+var_E8]
0x1400459d8  test    rax, rax
0x1400459db  jz      short loc_1400459E5
0x1400459dd  mov     [rsp+118h+var_E8], r12
0x1400459e2  mov     [r15], rax
0x1400459e5  lea     rcx, [rsp+118h+var_E8]
0x1400459ea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400459ef  nop
0x1400459f0  lea     rcx, [rsp+118h+var_A0]
0x1400459f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400459fa  nop
0x1400459fb  lea     rcx, [rsp+118h+var_D8]
0x140045a00  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045a05  nop
0x140045a06  mov     rcx, [rsp+118h+var_C8]
0x140045a0b  test    rcx, rcx
0x140045a0e  jz      short loc_140045A17
0x140045a10  call    cs:__imp_CoRevokeDeviceCatalog
0x140045a16  nop
0x140045a17  mov     rcx, [rsp+118h+pv]; pv
0x140045a1c  mov     [rsp+118h+pv], r12
0x140045a21  test    rcx, rcx
0x140045a24  jz      short loc_140045A2D
0x140045a26  call    cs:__imp_CoTaskMemFree
0x140045a2c  nop
0x140045a2d  lea     rcx, [rsp+118h+pvar]; pvar
0x140045a32  call    cs:__imp_PropVariantClear
0x140045a38  nop
0x140045a39  mov     rcx, [rsp+118h+var_C0]
0x140045a3e  test    rcx, rcx
0x140045a41  jz      short loc_140045A4A
0x140045a43  call    cs:__imp_CoRevokeDeviceCatalog
0x140045a49  nop
0x140045a4a  jmp     short $+2
0x140045a4c  mov     rcx, [rsp+118h+var_48]
0x140045a54  xor     rcx, rsp; StackCookie
0x140045a57  call    __security_check_cookie
0x140045a5c  add     rsp, 0E8h
0x140045a63  pop     r15
0x140045a65  pop     r14
0x140045a67  pop     r12
0x140045a69  pop     rdi
0x140045a6a  pop     rsi
0x140045a6b  pop     rbx
0x140045a6c  retn
```
