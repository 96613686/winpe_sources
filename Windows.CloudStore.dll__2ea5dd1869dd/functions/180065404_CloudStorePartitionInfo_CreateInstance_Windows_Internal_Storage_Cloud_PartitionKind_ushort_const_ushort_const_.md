# CloudStorePartitionInfo_CreateInstance(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::Partitioning::IPartitionMetadata *,_GUID const &,void * *)

- ea: `0x180065404`
- end: `0x18006560d`
- name: `?CloudStorePartitionInfo_CreateInstance@@YAJW4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1PEAUIPartitionMetadata@Partitioning@2345@AEBU_GUID@@PEAPEAX@Z`
- size: `521`
- prototype: `int __high(enum Windows::Internal::Storage::Cloud::PartitionKind, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::Storage::Cloud::Partitioning::IPartitionMetadata *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064900`
- `0x18010bb30`

## callees

- `0x180065404`
- `0x180065614`
- `0x180065670`
- `0x1800657ec`
- `0x1800658c0`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1801236bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180065464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800654da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180065464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800654da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006549a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006555a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006549a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006555a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800655f9`

## pseudocode

```c
__int64 __fastcall CloudStorePartitionInfo_CreateInstance(
        int a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const char *a4,
        __int64 a5,
        HSTRING a6)
{
  HSTRING v6; // r14
  __int64 v11; // rbx
  __int64 v12; // rdx
  HRESULT v13; // edi
  HRESULT v15; // ebx
  void *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-38h]
  HSTRING *v22; // [rsp+30h] [rbp-28h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF
  char v24; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HSTRING v26; // [rsp+A8h] [rbp+50h] BYREF

  v6 = a6;
  *(_QWORD *)a6 = 0;
  if ( !*a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitioninfo.cpp",
      a4);
  a6 = 0;
  v11 = -1;
  v22 = &a6;
  v12 = -1;
  string = 0;
  v24 = 1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = WindowsCreateString(a2, v12, &string);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v22);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitioninfo.cpp",
      (const char *)(unsigned int)v13,
      v21);
LABEL_6:
    if ( a6 )
      WindowsDeleteString(a6);
    return (unsigned int)v13;
  }
  v26 = 0;
  v22 = &v26;
  string = 0;
  v24 = 1;
  do
    ++v11;
  while ( a3[v11] );
  v15 = WindowsCreateString(a3, v11, &string);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v22);
  if ( v15 < 0 )
  {
    v20 = 58;
    goto LABEL_24;
  }
  v16 = operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v16
    || (v17 = Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionInfo::CloudStorePartitionInfo(
                (_DWORD)v16,
                a1,
                (unsigned int)&a6,
                (unsigned int)&v26,
                (__int64)a4),
        (v18 = v17) == 0) )
  {
    v15 = -2147024882;
    v20 = 61;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitioninfo.cpp",
      (const char *)(unsigned int)v15,
      v21);
    if ( v26 )
      WindowsDeleteString(v26);
    if ( a6 )
      WindowsDeleteString(a6);
    return (unsigned int)v15;
  }
  v19 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>>(
          v17,
          &GUID_cd223c7d_d51a_43ba_ab88_c40f5d3885aa,
          v6);
  v13 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitioninfo.cpp",
      (const char *)(unsigned int)v19,
      v21);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>::Release(v18);
    if ( v26 )
      WindowsDeleteString(v26);
    goto LABEL_6;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>::Release(v18);
  if ( v26 )
    WindowsDeleteString(v26);
  if ( a6 )
    WindowsDeleteString(a6);
  return 0;
}

```

## disassembly

```asm
0x180065404  push    rbp
0x180065406  push    rbx
0x180065407  push    rsi
0x180065408  push    rdi
0x180065409  push    r12
0x18006540b  push    r13
0x18006540d  push    r14
0x18006540f  push    r15
0x180065411  mov     rbp, rsp
0x180065414  sub     rsp, 58h
0x180065418  mov     r14, [rbp+arg_28]
0x18006541c  xor     r13d, r13d
0x18006541f  mov     r15, r9
0x180065422  mov     rsi, r8
0x180065425  mov     rax, rdx
0x180065428  mov     r12d, ecx
0x18006542b  mov     [r14], r13
0x18006542e  cmp     [rdx], r13w
0x180065432  jz      loc_1800655AE
0x180065438  lea     rcx, [rbp+arg_28]
0x18006543c  mov     [rbp+arg_28], r13
0x180065440  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180065444  mov     [rbp+var_28], rcx
0x180065448  mov     rdx, rbx
0x18006544b  mov     [rbp+string], r13
0x18006544f  mov     [rbp+var_18], 1
0x180065453  inc     rdx; length
0x180065456  cmp     [rax+rdx*2], r13w
0x18006545b  jnz     short loc_180065453
0x18006545d  lea     r8, [rbp+string]; string
0x180065461  mov     rcx, rax; sourceString
0x180065464  call    cs:__imp_WindowsCreateString
0x18006546a  lea     rcx, [rbp+var_28]
0x18006546e  mov     edi, eax
0x180065470  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180065475  test    edi, edi
0x180065477  jns     short loc_1800654B3
0x180065479  mov     rcx, [rbp+40h]; this
0x18006547d  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180065484  mov     r9d, edi; char *
0x180065487  mov     edx, 37h ; '7'; void *
0x18006548c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065491  mov     rcx, [rbp+arg_28]; string
0x180065495  test    rcx, rcx
0x180065498  jz      short loc_1800654A0
0x18006549a  call    cs:__imp_WindowsDeleteString
0x1800654a0  mov     eax, edi
0x1800654a2  add     rsp, 58h
0x1800654a6  pop     r15
0x1800654a8  pop     r14
0x1800654aa  pop     r13
0x1800654ac  pop     r12
0x1800654ae  pop     rdi
0x1800654af  pop     rsi
0x1800654b0  pop     rbx
0x1800654b1  pop     rbp
0x1800654b2  retn
0x1800654b3  lea     rax, [rbp+arg_8]
0x1800654b7  mov     [rbp+arg_8], r13
0x1800654bb  mov     [rbp+var_28], rax
0x1800654bf  mov     [rbp+string], r13
0x1800654c3  mov     [rbp+var_18], 1
0x1800654c7  inc     rbx
0x1800654ca  cmp     [rsi+rbx*2], r13w
0x1800654cf  jnz     short loc_1800654C7
0x1800654d1  lea     r8, [rbp+string]; string
0x1800654d5  mov     edx, ebx; length
0x1800654d7  mov     rcx, rsi; sourceString
0x1800654da  call    cs:__imp_WindowsCreateString
0x1800654e0  lea     rcx, [rbp+var_28]
0x1800654e4  mov     ebx, eax
0x1800654e6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800654eb  test    ebx, ebx
0x1800654ed  js      loc_180065606
0x1800654f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800654fa  mov     ecx, 60h ; '`'; unsigned __int64
0x1800654ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180065504  test    rax, rax
0x180065507  jz      loc_1800655C4
0x18006550d  lea     r9, [rbp+arg_8]
0x180065511  mov     qword ptr [rsp+58h+var_38], r15; int
0x180065516  lea     r8, [rbp+arg_28]
0x18006551a  mov     edx, r12d
0x18006551d  mov     rcx, rax
0x180065520  call    ??0CloudStorePartitionInfo@Partitioning@Cloud@Storage@Internal@Windows@@QEAA@W4PartitionKind@2345@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@1PEAUIPartitionMetadata@12345@@Z; Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionInfo::CloudStorePartitionInfo(Windows::Internal::Storage::Cloud::PartitionKind,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,Windows::Internal::Storage::Cloud::Partitioning::IPartitionMetadata *)
0x180065525  mov     rbx, rax
0x180065528  test    rax, rax
0x18006552b  jz      loc_1800655C4
0x180065531  mov     r8, r14
0x180065534  lea     rdx, _GUID_cd223c7d_d51a_43ba_ab88_c40f5d3885aa
0x18006553b  mov     rcx, rax
0x18006553e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICloudStorePartitionInfo@Partitioning@Cloud@Storage@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICloudStorePartitionInfo@Partitioning@Cloud@Storage@Internal@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180065543  mov     edi, eax
0x180065545  test    eax, eax
0x180065547  js      short loc_180065576
0x180065549  mov     rcx, rbx
0x18006554c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICloudStorePartitionInfo@Partitioning@Cloud@Storage@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>::Release(void)
0x180065551  mov     rcx, [rbp+arg_8]; string
0x180065555  test    rcx, rcx
0x180065558  jz      short loc_180065560
0x18006555a  call    cs:__imp_WindowsDeleteString
0x180065560  mov     rcx, [rbp+arg_28]; string
0x180065564  test    rcx, rcx
0x180065567  jz      short loc_18006556F
0x180065569  call    cs:__imp_WindowsDeleteString
0x18006556f  xor     eax, eax
0x180065571  jmp     loc_1800654A2
0x180065576  mov     rcx, [rbp+40h]; this
0x18006557a  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180065581  mov     r9d, edi; char *
0x180065584  mov     edx, 3Eh ; '>'; void *
0x180065589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006558e  mov     rcx, rbx
0x180065591  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICloudStorePartitionInfo@Partitioning@Cloud@Storage@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::Cloud::Partitioning::ICloudStorePartitionInfo,Microsoft::WRL::FtmBase>::Release(void)
0x180065596  mov     rcx, [rbp+arg_8]; string
0x18006559a  test    rcx, rcx
0x18006559d  jz      loc_180065491
0x1800655a3  call    cs:__imp_WindowsDeleteString
0x1800655a9  jmp     loc_180065491
0x1800655ae  mov     rcx, [rbp+40h]; this
0x1800655b2  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800655b9  mov     edx, 34h ; '4'; void *
0x1800655be  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800655c4  mov     ebx, 8007000Eh
0x1800655c9  mov     edx, 3Dh ; '='; void *
0x1800655ce  mov     rcx, [rbp+40h]; this
0x1800655d2  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800655d9  mov     r9d, ebx; char *
0x1800655dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800655e1  mov     rcx, [rbp+arg_8]; string
0x1800655e5  test    rcx, rcx
0x1800655e8  jz      short loc_1800655F0
0x1800655ea  call    cs:__imp_WindowsDeleteString
0x1800655f0  mov     rcx, [rbp+arg_28]; string
0x1800655f4  test    rcx, rcx
0x1800655f7  jz      short loc_1800655FF
0x1800655f9  call    cs:__imp_WindowsDeleteString
0x1800655ff  mov     eax, ebx
0x180065601  jmp     loc_1800654A2
0x180065606  mov     edx, 3Ah ; ':'
0x18006560b  jmp     short loc_1800655CE
```
