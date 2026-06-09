# ServiceManager::InitializeMapsStore(void)

- ea: `0x180016fdc`
- end: `0x1800171c9`
- name: `?InitializeMapsStore@ServiceManager@@AEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180016b60`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x180009d0c`
- `0x180009db4`
- `0x18000af48`
- `0x1800117c0`
- `0x180016fdc`
- `0x1800183ac`
- `0x180020a1c`

## import_xrefs

- `MapsStore!MapsStore_Initialize` at `0x180017120`
- `MapsStore!MapsStore_Initialize` at `0x180017120`
- `MosStorage!MosStorageGetSystemDataDirectory` at `0x180017049`
- `MosStorage!MosStorageGetSystemDataDirectory` at `0x180017049`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001707c`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001707c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800170b8`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800170b8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180017065`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180017065`
- `ZTrace_Maps!ZTraceHelper` at `0x180017156`
- `ZTrace_Maps!ZTraceHelper` at `0x180017156`

## string_xrefs

- `0x18001705c`: `ServiceManager::InitializeMapsStore`
- `0x1800170af`: `ServiceManager::InitializeMapsStore`
- `0x180017129`: `ServiceManager::InitializeMapsStore`
- `0x18001713f`: `[MosHost] Service - Startup - MapsStore initialized`

## pseudocode

```c
__int64 __fastcall ServiceManager::InitializeMapsStore(ServiceManager *this)
{
  unsigned int v2; // ebx
  int SystemDataDirectory; // eax
  int v4; // r8d
  ServiceManager *v5; // r9
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  __int64 v8; // rcx
  int MapsPersistedRegString; // eax
  const unsigned __int16 *v10; // rax
  int v11; // edi
  OfflineMapsTelemetry *v12; // rax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v17[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[264]; // [rsp+280h] [rbp+180h] BYREF

  v2 = 0;
  memset_0(v18, 0, 0x208u);
  memset_0(v17, 0, 0x208u);
  std::wstring::wstring((__int64)v15);
  SystemDataDirectory = MosStorageGetSystemDataDirectory(v18, 0x104u);
  if ( SystemDataDirectory < 0 )
  {
    v4 = 2736;
LABEL_3:
    v5 = this;
LABEL_4:
    v2 = ZTraceReportPropagation(SystemDataDirectory, "ServiceManager::InitializeMapsStore", v4, v5);
    goto LABEL_14;
  }
  SystemDataDirectory = MosStorageGetDataDirectory(v17, 0x104u);
  if ( SystemDataDirectory < 0 )
  {
    v4 = 2738;
    goto LABEL_3;
  }
  MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(v8, L"LastLanguageList");
  if ( MapsPersistedRegString < 0 )
    ZTraceReportIgnore(MapsPersistedRegString, "ServiceManager::InitializeMapsStore", 2740, this);
  if ( !v16 )
    std::wstring::assign(v15, L"en-US");
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  SystemDataDirectory = MapsStore_Initialize(
                          v18,
                          v17,
                          v10,
                          (void (*)(float, void *))&lambda_1b5e180a674a371ff36d8464df1fcad1_::_lambda_invoker_cdecl_,
                          (void (*)(int, void *))lambda_6437de858c0920889d6d63fa68577d3a_::_lambda_invoker_cdecl_,
                          (void (*)(int, unsigned __int64, void *))lambda_00eaef351054c69279349b647185c1e2_::_lambda_invoker_cdecl_,
                          (void (*)(int, struct IMapRegionNode *, void *))lambda_36b7cf60408571aa200e6754cd28e4ad_::_lambda_invoker_cdecl_,
                          this);
  v5 = this;
  if ( SystemDataDirectory < 0 )
  {
    v4 = 2756;
    goto LABEL_4;
  }
  ZTraceHelper(
    5,
    "ServiceManager::InitializeMapsStore",
    2758,
    this,
    "[MosHost] Service - Startup - MapsStore initialized");
LABEL_14:
  if ( v2 == -2147024891 )
  {
    v2 = -2080374781;
    v14 = -2080374781;
    OfflineMapsTelemetry::MapsCacheAccessDenied<long &>(&v14, v6);
  }
  v11 = *((_DWORD *)this + 1080);
  if ( OfflineMapsTelemetry::IsEnabled(v7, v6) )
  {
    v12 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::MapsStoreInitialized_(v12, v11, v2);
  }
  std::wstring::_Tidy_deallocate((__int64)v15);
  return v2;
}

```

## disassembly

```asm
0x180016fdc  mov     [rsp-8+arg_8], rbx
0x180016fe1  mov     [rsp-8+arg_10], rdi
0x180016fe6  push    rbp
0x180016fe7  lea     rbp, [rsp-3A0h]
0x180016fef  sub     rsp, 4A0h
0x180016ff6  mov     rax, cs:__security_cookie
0x180016ffd  xor     rax, rsp
0x180017000  mov     [rbp+3A0h+var_10], rax
0x180017007  mov     rdi, rcx
0x18001700a  xor     ebx, ebx
0x18001700c  xor     edx, edx; Val
0x18001700e  mov     r8d, 208h; Size
0x180017014  lea     rcx, [rbp+3A0h+var_220]; void *
0x18001701b  call    memset_0
0x180017020  xor     edx, edx; Val
0x180017022  mov     r8d, 208h; Size
0x180017028  lea     rcx, [rsp+4A0h+var_430]; void *
0x18001702d  call    memset_0
0x180017032  lea     rcx, [rsp+4A0h+var_458]
0x180017037  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001703c  nop
0x18001703d  mov     edx, 104h
0x180017042  lea     rcx, [rbp+3A0h+var_220]
0x180017049  call    cs:__imp_?MosStorageGetSystemDataDirectory@@YAJPEAGK@Z; MosStorageGetSystemDataDirectory(ushort *,ulong)
0x18001704f  test    eax, eax
0x180017051  jns     short loc_180017072
0x180017053  mov     r8d, 0AB0h
0x180017059  mov     r9, rdi
0x18001705c  lea     rdx, aServicemanager_30; "ServiceManager::InitializeMapsStore"
0x180017063  mov     ecx, eax
0x180017065  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001706b  mov     ebx, eax
0x18001706d  jmp     loc_18001715C
0x180017072  mov     edx, 104h
0x180017077  lea     rcx, [rsp+4A0h+var_430]
0x18001707c  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180017082  test    eax, eax
0x180017084  jns     short loc_18001708E
0x180017086  mov     r8d, 0AB2h
0x18001708c  jmp     short loc_180017059
0x18001708e  lea     r9, [rsp+4A0h+var_458]
0x180017093  xor     r8d, r8d
0x180017096  lea     rdx, aLastlanguageli; "LastLanguageList"
0x18001709d  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800170a2  test    eax, eax
0x1800170a4  jns     short loc_1800170BE
0x1800170a6  mov     r9, rdi
0x1800170a9  mov     r8d, 0AB4h
0x1800170af  lea     rdx, aServicemanager_30; "ServiceManager::InitializeMapsStore"
0x1800170b6  mov     ecx, eax
0x1800170b8  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800170be  cmp     [rsp+4A0h+var_448], 0
0x1800170c4  jnz     short loc_1800170D7
0x1800170c6  lea     rdx, aEnUs; "en-US"
0x1800170cd  lea     rcx, [rsp+4A0h+var_458]
0x1800170d2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800170d7  lea     rcx, [rsp+4A0h+var_458]
0x1800170dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800170e1  mov     r8, rax
0x1800170e4  mov     [rsp+4A0h+var_468], rdi
0x1800170e9  lea     rax, _lambda_36b7cf60408571aa200e6754cd28e4ad____lambda_invoker_cdecl_
0x1800170f0  mov     [rsp+4A0h+var_470], rax
0x1800170f5  lea     rax, _lambda_00eaef351054c69279349b647185c1e2____lambda_invoker_cdecl_
0x1800170fc  mov     [rsp+4A0h+var_478], rax
0x180017101  lea     rax, _lambda_6437de858c0920889d6d63fa68577d3a____lambda_invoker_cdecl_
0x180017108  mov     [rsp+4A0h+var_480], rax
0x18001710d  lea     r9, _lambda_1b5e180a674a371ff36d8464df1fcad1____lambda_invoker_cdecl_
0x180017114  lea     rdx, [rsp+4A0h+var_430]
0x180017119  lea     rcx, [rbp+3A0h+var_220]
0x180017120  call    cs:__imp_?MapsStore_Initialize@@YAJPEBG00P6AXMPEAX@ZP6AXJ1@ZP6AXJ_K1@ZP6AXJPEAVIMapRegionNode@@1@Z1@Z; MapsStore_Initialize(ushort const *,ushort const *,ushort const *,void (*)(float,void *),void (*)(long,void *),void (*)(long,unsigned __int64,void *),void (*)(long,IMapRegionNode *,void *),void *)
0x180017126  mov     r9, rdi
0x180017129  lea     rdx, aServicemanager_30; "ServiceManager::InitializeMapsStore"
0x180017130  test    eax, eax
0x180017132  jns     short loc_18001713F
0x180017134  mov     r8d, 0AC4h
0x18001713a  jmp     loc_180017063
0x18001713f  lea     rax, aMoshostService_8; "[MosHost] Service - Startup - MapsStore"...
0x180017146  mov     [rsp+4A0h+var_480], rax
0x18001714b  mov     r8d, 0AC6h
0x180017151  mov     ecx, 5
0x180017156  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001715c  cmp     ebx, 80070005h
0x180017162  jnz     short loc_180017177
0x180017164  mov     ebx, 84000003h
0x180017169  mov     [rsp+4A0h+var_460], ebx
0x18001716d  lea     rcx, [rsp+4A0h+var_460]
0x180017172  call    ??$MapsCacheAccessDenied@AEAJ@OfflineMapsTelemetry@@SAXAEAJ@Z; OfflineMapsTelemetry::MapsCacheAccessDenied<long &>(long &)
0x180017177  mov     edi, [rdi+10E0h]
0x18001717d  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017182  test    al, al
0x180017184  jz      short loc_180017199
0x180017186  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001718b  mov     r8d, ebx; int
0x18001718e  mov     edx, edi; int
0x180017190  mov     rcx, rax; this
0x180017193  call    ?MapsStoreInitialized_@OfflineMapsTelemetry@@QEAAXHJ@Z; OfflineMapsTelemetry::MapsStoreInitialized_(int,long)
0x180017198  nop
0x180017199  lea     rcx, [rsp+4A0h+var_458]
0x18001719e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800171a3  mov     eax, ebx
0x1800171a5  mov     rcx, [rbp+3A0h+var_10]
0x1800171ac  xor     rcx, rsp; StackCookie
0x1800171af  call    __security_check_cookie
0x1800171b4  lea     r11, [rsp+4A0h+var_s0]
0x1800171bc  mov     rbx, [r11+18h]
0x1800171c0  mov     rdi, [r11+20h]
0x1800171c4  mov     rsp, r11
0x1800171c7  pop     rbp
0x1800171c8  retn
```
