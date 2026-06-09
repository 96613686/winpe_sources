# AppEndpoint::PostNotification2(ushort const *,ushort const *,ulong,__MIDL___MIDL_itf_wpnplatform_0000_0007_0004,ushort const *,ushort const *,ushort const *,_WPN_FILE_TIME,ulong,int,ushort const *,IWpnToastFeedback *,_GUID *,int,ulong,ushort const *,ulong *)

- ea: `0x1800cfe60`
- end: `0x1800d04fe`
- name: `?PostNotification2@AppEndpoint@@UEAAJPEBG0KW4__MIDL___MIDL_itf_wpnplatform_0000_0007_0004@@000U_WPN_FILE_TIME@@KH0PEAUIWpnToastFeedback@@PEAU_GUID@@HK0PEAK@Z`
- size: `1694`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011618`
- `0x1800173ac`
- `0x180017a6c`
- `0x180017c5c`
- `0x18002ab88`
- `0x18002bf64`
- `0x18002bfbc`
- `0x18002bfd8`
- `0x18005b250`
- `0x18005ba38`
- `0x180065b08`
- `0x180068c98`
- `0x18006cdfc`
- `0x18006e48c`
- `0x18006e4c4`
- `0x18009cabc`
- `0x18009f0a8`
- `0x1800a4ac0`
- `0x1800b99f0`
- `0x1800b9a44`
- `0x1800b9ea0`
- `0x1800bc31c`
- `0x1800bc384`
- `0x1800cc9d8`
- `0x1800cfe60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800cffa5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800cffa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d0019`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d0019`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800d01e9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800d01e9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800d008b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800d008b`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall AppEndpoint::PostNotification2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        char a10,
        char a11,
        __int64 a12,
        __int64 a13,
        __int128 *a14,
        int a15,
        __int64 a16,
        __int64 a17,
        unsigned int *a18)
{
  __int128 *v19; // r15
  unsigned int *v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 **v23; // rax
  __int64 v24; // rcx
  const char *v25; // r9
  __int64 result; // rax
  unsigned int NotificationTrackingId; // edi
  int v28; // esi
  int v29; // r14d
  int v30; // eax
  IStream *v31; // rax
  _QWORD *v32; // rax
  int v33; // eax
  HRESULT v34; // eax
  int v35; // eax
  int v36; // eax
  struct _Mtx_internal_imp_t *v37; // rcx
  int v38; // [rsp+20h] [rbp-1C8h]
  int v39; // [rsp+20h] [rbp-1C8h]
  int v40; // [rsp+20h] [rbp-1C8h]
  __int64 v41; // [rsp+40h] [rbp-1A8h]
  UINT cbInit[2]; // [rsp+50h] [rbp-198h] BYREF
  int v43; // [rsp+58h] [rbp-190h] BYREF
  __int64 v44; // [rsp+60h] [rbp-188h] BYREF
  __int64 v45; // [rsp+68h] [rbp-180h] BYREF
  __int64 v46; // [rsp+70h] [rbp-178h] BYREF
  __int64 v47; // [rsp+78h] [rbp-170h] BYREF
  BYTE *pInit; // [rsp+80h] [rbp-168h] BYREF
  __int64 v49; // [rsp+88h] [rbp-160h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-158h] BYREF
  _QWORD v51[2]; // [rsp+A0h] [rbp-148h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-138h] BYREF
  int v53[2]; // [rsp+B8h] [rbp-130h]
  __int64 v54; // [rsp+C0h] [rbp-128h]
  __int64 v55; // [rsp+C8h] [rbp-120h] BYREF
  __int128 v56; // [rsp+D8h] [rbp-110h] BYREF
  GUID pguid; // [rsp+E8h] [rbp-100h] BYREF
  _DWORD v58[2]; // [rsp+100h] [rbp-E8h] BYREF
  __int64 v59; // [rsp+108h] [rbp-E0h]
  _QWORD *v60; // [rsp+110h] [rbp-D8h]
  const wchar_t *v61; // [rsp+118h] [rbp-D0h]
  __int64 v62; // [rsp+120h] [rbp-C8h]
  _QWORD v63[2]; // [rsp+128h] [rbp-C0h] BYREF
  int v64; // [rsp+138h] [rbp-B0h]
  int v65; // [rsp+13Ch] [rbp-ACh]
  struct _FILETIME v66; // [rsp+140h] [rbp-A8h]
  __int64 v67; // [rsp+148h] [rbp-A0h]
  __int64 LastBootTime; // [rsp+150h] [rbp-98h] BYREF
  char v69; // [rsp+158h] [rbp-90h]
  int v70; // [rsp+159h] [rbp-8Fh]
  __int16 v71; // [rsp+15Dh] [rbp-8Bh]
  char v72; // [rsp+15Fh] [rbp-89h]
  __int64 v73; // [rsp+160h] [rbp-88h]
  GUID v74; // [rsp+168h] [rbp-80h]
  _QWORD v75[5]; // [rsp+178h] [rbp-70h] BYREF
  __int64 v76; // [rsp+1A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v55 = a3;
  v54 = a1;
  v43 = a4;
  *(_QWORD *)&v56 = a7;
  v49 = a8;
  v52 = a12;
  *(_QWORD *)v53 = a13;
  v19 = a14;
  v20 = a18;
  LOBYTE(a2) = 1;
  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_40444302>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_40444302>::GetImpl'::`2'::impl,
      a2);
    v21 = *(unsigned int *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
    if ( dword_18015E478 > (int)v21 )
    {
      Init_thread_header(&dword_18015E478);
      if ( dword_18015E478 == -1 )
      {
        cbInit[0] = 1;
        std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v58, cbInit, off_18011DDD8);
        cbInit[0] = 0;
        std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v63, cbInit, off_18011DDE0);
        cbInit[0] = 2;
        std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(
          &LastBootTime,
          cbInit,
          off_18011DDC8);
        cbInit[0] = 3;
        std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v75, cbInit, off_18011DDD0);
        v51[0] = v58;
        v51[1] = &v76;
        std::unordered_map<unsigned long,std::wstring>::unordered_map<unsigned long,std::wstring>(&qword_18015E480, v51);
        `eh vector destructor iterator'(
          v58,
          0x28u,
          4u,
          std::pair<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 const,std::wstring>::~pair<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 const,std::wstring>);
        atexit(AppEndpoint::PostNotification2_::_3_::_dynamic_atexit_destructor_for__typeMap__);
        Init_thread_footer(&dword_18015E478);
      }
    }
    v22 = std::_Uhash_compare<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005,std::hash<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>,std::equal_to<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>>::operator()<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(
            v21,
            (__int64)&v43);
    v23 = std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Find_last<unsigned long>(
            &qword_18015E480,
            (__int64 **)&pguid,
            &v43,
            v22);
    v24 = qword_18015E488;
    if ( v23[1] )
      v24 = (__int64)v23[1];
    if ( v24 == qword_18015E488 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)0x80070057LL,
        v38);
      result = 2147942487LL;
    }
    else
    {
      AcquireSRWLockShared(&Wns::s_platformLock);
      v51[0] = &Wns::s_platformLock;
      if ( Wns::s_platformShutdown )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)0x803E0105LL,
          v38);
      Wns::NotificationPlatformHandle::Get(a1 + 40, &v45);
      if ( !v45 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)0x803E0105LL,
          v38);
      NotificationTrackingId = *v20;
      if ( !*v20 )
        NotificationTrackingId = NotificationPlatform::GetNotificationTrackingId(*(NotificationPlatform **)(v45 + 184));
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v44 = 0;
      if ( *a9 == 1 )
      {
        v28 = a9[1];
        v29 = a9[2];
      }
      else
      {
        v29 = HIDWORD(v44);
        v28 = v44;
      }
      ConvertUtf16ToUtf8(&pInit, a6);
      *(_QWORD *)cbInit = 0;
      v30 = StringCchLengthA((const char *)pInit, 0x3000u, (unsigned __int64 *)cbInit);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3BF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v30,
          v38);
      v44 = 0;
      v31 = SHCreateMemStream(pInit, cbInit[0]);
      Microsoft::WRL::ComPtr<WNSChannelDetails>::Attach(&v44, v31);
      v58[0] = NotificationTrackingId;
      v58[1] = 0;
      v59 = v55;
      v32 = (_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Try_emplace<unsigned long const &,>(
                                    &qword_18015E480,
                                    (__int64)&v55,
                                    &v43)
                     + 24LL);
      if ( v32[3] > 7u )
        v32 = (_QWORD *)*v32;
      v60 = v32;
      v61 = L"Xml";
      v62 = v44;
      v63[0] = v56;
      v63[1] = v49;
      v64 = v28;
      v65 = v29;
      v66 = SystemTimeAsFileTime;
      v67 = 1;
      LastBootTime = GetLastBootTime();
      v69 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      v74 = GUID_NULL;
      v75[0] = 1;
      v75[1] = 0;
      v47 = 0;
      v33 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(
              (__int64)&v47,
              (__int64)v58);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D5,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v33,
          v38);
      pguid = 0;
      v34 = CoCreateGuid(&pguid);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v34,
          v38);
      v56 = 0;
      if ( v19 )
        v56 = *v19;
      v46 = 0;
      v49 = 0;
      cbInit[0] = 0;
      v35 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,unsigned long &,unsigned short const * &,int &,int &,_GUID &,_GUID &,enum WpnToastNotificationPriority,char const (&)[1],std::nullptr_t>(
              (__int64)&v46,
              (int)&a10,
              (int)&v52,
              (int)&a11,
              (__int64)&a15,
              (__int64)&v56,
              (__int64)&pguid,
              (__int64)cbInit,
              v41,
              (__int64)&v49);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v35,
          v39);
      v40 = v53[0];
      v36 = AppEndpoint::PostNotificationInternal(v54, v47, v46, a5);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3ED,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v36,
          v40);
      *v20 = NotificationTrackingId;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(&pInit, 0);
      v37 = (struct _Mtx_internal_imp_t *)_InterlockedExchange64(&v45, 0);
      if ( v37 )
        Wns::Owner<std::unique_ptr<NotificationPlatform>,std::chrono::duration<__int64,std::ratio<1,1>>>::DestroyShared(v37);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v51);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x437,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x1800cfe60  push    rbx
0x1800cfe62  push    rsi
0x1800cfe63  push    rdi
0x1800cfe64  push    r12
0x1800cfe66  push    r13
0x1800cfe68  push    r14
0x1800cfe6a  push    r15
0x1800cfe6c  sub     rsp, 1B0h
0x1800cfe73  mov     rax, cs:__security_cookie
0x1800cfe7a  xor     rax, rsp
0x1800cfe7d  mov     [rsp+1E8h+var_48], rax
0x1800cfe85  mov     [rsp+1E8h+var_120], r8
0x1800cfe8d  mov     rdi, rcx
0x1800cfe90  mov     [rsp+1E8h+var_128], rcx
0x1800cfe98  mov     r14, [rsp+1E8h+arg_40]
0x1800cfea0  mov     [rsp+1E8h+var_190], r9d
0x1800cfea5  mov     r12, [rsp+1E8h+arg_28]
0x1800cfead  mov     rax, [rsp+1E8h+arg_30]
0x1800cfeb5  mov     qword ptr [rsp+1E8h+var_110], rax
0x1800cfebd  mov     rax, [rsp+1E8h+arg_38]
0x1800cfec5  mov     [rsp+1E8h+var_160], rax
0x1800cfecd  mov     rax, [rsp+1E8h+arg_58]
0x1800cfed5  mov     [rsp+1E8h+var_138], rax
0x1800cfedd  mov     rax, [rsp+1E8h+arg_60]
0x1800cfee5  mov     qword ptr [rsp+1E8h+var_130], rax
0x1800cfeed  mov     r15, [rsp+1E8h+arg_68]
0x1800cfef5  mov     r13, [rsp+1E8h+arg_88]
0x1800cfefd  mov     dl, 1
0x1800cfeff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40444302@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40444302@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40444302> `wil::Feature<__WilFeatureTraits_Feature_40444302>::GetImpl(void)'::`2'::impl
0x1800cff06  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40444302@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40444302>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800cff0b  mov     ecx, cs:_tls_index
0x1800cff11  mov     rax, gs:58h
0x1800cff1a  mov     edx, 4
0x1800cff1f  mov     rax, [rax+rcx*8]
0x1800cff23  mov     ecx, [rdx+rax]
0x1800cff26  cmp     cs:dword_18015E478, ecx
0x1800cff2c  jg      loc_1800D0359
0x1800cff32  xor     ebx, ebx
0x1800cff34  lea     rdx, [rsp+1E8h+var_190]
0x1800cff39  call    ??$?RW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@?$_Uhash_compare@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@U?$hash@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@U?$equal_to@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@3@@std@@QEBA_KAEBW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@Z; std::_Uhash_compare<__MIDL___MIDL_itf_wpntypes_0000_0000_0005,std::hash<__MIDL___MIDL_itf_wpntypes_0000_0000_0005>,std::equal_to<__MIDL___MIDL_itf_wpntypes_0000_0000_0005>>::operator()<__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(__MIDL___MIDL_itf_wpntypes_0000_0000_0005 const &)
0x1800cff3e  mov     r9, rax
0x1800cff41  lea     r8, [rsp+1E8h+var_190]
0x1800cff46  lea     rdx, [rsp+1E8h+pguid]
0x1800cff4e  lea     rcx, qword_18015E480
0x1800cff55  call    ??$_Find_last@K@?$_Hash@V?$_Umap_traits@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@AEBK_K@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)
0x1800cff5a  mov     rcx, cs:qword_18015E488
0x1800cff61  cmp     [rax+8], rbx
0x1800cff65  cmovnz  rcx, [rax+8]
0x1800cff6a  cmp     rcx, cs:qword_18015E488
0x1800cff71  jnz     short loc_1800CFF9B
0x1800cff73  mov     rcx, [rsp+1E8h]; this
0x1800cff7b  mov     ebx, 80070057h
0x1800cff80  mov     r9d, ebx; char *
0x1800cff83  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cff8a  mov     edx, 3A8h; void *
0x1800cff8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cff94  mov     eax, ebx
0x1800cff96  jmp     loc_1800D0336
0x1800cff9b  lea     rsi, ?s_platformLock@Wns@@3Vsrwlock@wil@@A; wil::srwlock Wns::s_platformLock
0x1800cffa2  mov     rcx, rsi; SRWLock
0x1800cffa5  call    cs:__imp_AcquireSRWLockShared
0x1800cffab  mov     [rsp+1E8h+var_148], rsi
0x1800cffb3  mov     rcx, [rsp+1E8h]; this
0x1800cffbb  cmp     cs:?s_platformShutdown@Wns@@3_NA, bl; bool Wns::s_platformShutdown
0x1800cffc1  jnz     loc_1800D0466
0x1800cffc7  lea     rcx, [rdi+28h]
0x1800cffcb  lea     rdx, [rsp+1E8h+var_180]
0x1800cffd0  call    ?Get@NotificationPlatformHandle@Wns@@QEAA?AVNotificationPlatformPtr@2@XZ; Wns::NotificationPlatformHandle::Get(void)
0x1800cffd5  nop
0x1800cffd6  mov     rax, [rsp+1E8h+var_180]
0x1800cffdb  nop
0x1800cffdc  mov     rcx, [rsp+1E8h]; this
0x1800cffe4  test    rax, rax
0x1800cffe7  jz      loc_1800D047E
0x1800cffed  mov     edi, [r13+0]
0x1800cfff1  test    edi, edi
0x1800cfff3  jnz     short loc_1800D0009
0x1800cfff5  mov     rcx, [rsp+1E8h+var_180]
0x1800cfffa  nop
0x1800cfffb  mov     rcx, [rcx+0B8h]; this
0x1800d0002  call    ?GetNotificationTrackingId@NotificationPlatform@@QEAAKXZ; NotificationPlatform::GetNotificationTrackingId(void)
0x1800d0007  mov     edi, eax
0x1800d0009  mov     qword ptr [rsp+1E8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800d0011  lea     rcx, [rsp+1E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800d0019  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d001f  mov     [rsp+1E8h+var_188], rbx
0x1800d0024  cmp     dword ptr [r14], 1
0x1800d0028  jnz     short loc_1800D0034
0x1800d002a  mov     esi, [r14+4]
0x1800d002e  mov     r14d, [r14+8]
0x1800d0032  jmp     short loc_1800D003D
0x1800d0034  mov     r14d, dword ptr [rsp+1E8h+var_188+4]
0x1800d0039  mov     esi, dword ptr [rsp+1E8h+var_188]
0x1800d003d  mov     rdx, r12
0x1800d0040  lea     rcx, [rsp+1E8h+pInit]
0x1800d0048  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x1800d004d  nop
0x1800d004e  mov     qword ptr [rsp+1E8h+cbInit], rbx
0x1800d0053  lea     r8, [rsp+1E8h+cbInit]; unsigned __int64 *
0x1800d0058  mov     edx, 3000h; unsigned __int64
0x1800d005d  mov     rcx, [rsp+1E8h+pInit]; char *
0x1800d0065  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800d006a  mov     rcx, [rsp+1E8h]; this
0x1800d0072  test    eax, eax
0x1800d0074  js      loc_1800D0496
0x1800d007a  mov     [rsp+1E8h+var_188], rbx
0x1800d007f  mov     edx, [rsp+1E8h+cbInit]; cbInit
0x1800d0083  mov     rcx, [rsp+1E8h+pInit]; pInit
0x1800d008b  call    cs:__imp_SHCreateMemStream
0x1800d0091  mov     rdx, rax
0x1800d0094  lea     rcx, [rsp+1E8h+var_188]
0x1800d0099  call    ?Attach@?$ComPtr@VWNSChannelDetails@@@WRL@Microsoft@@QEAAXPEAVWNSChannelDetails@@@Z; Microsoft::WRL::ComPtr<WNSChannelDetails>::Attach(WNSChannelDetails *)
0x1800d009e  mov     [rsp+1E8h+var_E8], edi
0x1800d00a5  xor     eax, eax
0x1800d00a7  mov     [rsp+1E8h+var_E4], eax
0x1800d00ae  mov     rax, [rsp+1E8h+var_120]
0x1800d00b6  mov     [rsp+1E8h+var_E0], rax
0x1800d00be  lea     r8, [rsp+1E8h+var_190]
0x1800d00c3  lea     rdx, [rsp+1E8h+var_120]
0x1800d00cb  lea     rcx, qword_18015E480
0x1800d00d2  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800d00d7  mov     rax, [rax]
0x1800d00da  add     rax, 18h
0x1800d00de  cmp     qword ptr [rax+18h], 7
0x1800d00e3  jbe     short loc_1800D00E8
0x1800d00e5  mov     rax, [rax]
0x1800d00e8  mov     [rsp+1E8h+var_D8], rax
0x1800d00f0  lea     rax, aXml; "Xml"
0x1800d00f7  mov     [rsp+1E8h+var_D0], rax
0x1800d00ff  mov     rax, [rsp+1E8h+var_188]
0x1800d0104  mov     [rsp+1E8h+var_C8], rax
0x1800d010c  mov     rax, qword ptr [rsp+1E8h+var_110]
0x1800d0114  mov     [rsp+1E8h+var_C0], rax
0x1800d011c  mov     rax, [rsp+1E8h+var_160]
0x1800d0124  mov     [rsp+1E8h+var_B8], rax
0x1800d012c  mov     [rsp+1E8h+var_B0], esi
0x1800d0133  mov     [rsp+1E8h+var_AC], r14d
0x1800d013b  mov     rax, qword ptr [rsp+1E8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800d0143  mov     [rsp+1E8h+var_A8], rax
0x1800d014b  mov     [rsp+1E8h+var_A0], 1
0x1800d0157  call    ?GetLastBootTime@@YA_JXZ; GetLastBootTime(void)
0x1800d015c  mov     [rsp+1E8h+var_98], rax
0x1800d0164  mov     [rsp+1E8h+var_90], bl
0x1800d016b  xor     eax, eax
0x1800d016d  mov     [rsp+1E8h+var_8F], eax
0x1800d0174  mov     [rsp+1E8h+var_8B], ax
0x1800d017c  mov     [rsp+1E8h+var_89], al
0x1800d0183  mov     [rsp+1E8h+var_88], rax
0x1800d018b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d0192  movdqu  [rsp+1E8h+var_80], xmm0
0x1800d019b  mov     [rsp+1E8h+var_70], 1
0x1800d01a7  mov     [rsp+1E8h+var_68], rbx
0x1800d01af  mov     [rsp+1E8h+var_170], rbx
0x1800d01b4  lea     rdx, [rsp+1E8h+var_E8]
0x1800d01bc  lea     rcx, [rsp+1E8h+var_170]
0x1800d01c1  call    ??$MakeAndInitialize@VNotification@@V1@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VNotification@@@WRL@Microsoft@@@012@AEAUInitializer@Notification@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Notification>>,Notification::Initializer &)
0x1800d01c6  mov     rcx, [rsp+1E8h]; this
0x1800d01ce  test    eax, eax
0x1800d01d0  js      loc_1800D04AB
0x1800d01d6  xorps   xmm0, xmm0
0x1800d01d9  movups  xmmword ptr [rsp+1E8h+pguid.Data1], xmm0
0x1800d01e1  lea     rcx, [rsp+1E8h+pguid]; pguid
0x1800d01e9  call    cs:__imp_CoCreateGuid
0x1800d01ef  mov     rcx, [rsp+1E8h]; this
0x1800d01f7  test    eax, eax
0x1800d01f9  js      loc_1800D04BF
0x1800d01ff  xorps   xmm0, xmm0
0x1800d0202  movups  [rsp+1E8h+var_110], xmm0
0x1800d020a  test    r15, r15
0x1800d020d  jz      short loc_1800D021C
0x1800d020f  movups  xmm0, xmmword ptr [r15]
0x1800d0213  movdqu  [rsp+1E8h+var_110], xmm0
0x1800d021c  mov     [rsp+1E8h+var_178], rbx
0x1800d0221  mov     [rsp+1E8h+var_160], rbx
0x1800d0229  mov     [rsp+1E8h+cbInit], ebx
0x1800d022d  lea     rax, [rsp+1E8h+var_160]
0x1800d0235  mov     [rsp+1E8h+var_1A0], rax
0x1800d023a  lea     rax, [rsp+1E8h+cbInit]
0x1800d023f  mov     [rsp+1E8h+var_1B0], rax
0x1800d0244  lea     rax, [rsp+1E8h+pguid]
0x1800d024c  mov     [rsp+1E8h+var_1B8], rax
0x1800d0251  lea     rax, [rsp+1E8h+var_110]
0x1800d0259  mov     [rsp+1E8h+var_1C0], rax
0x1800d025e  lea     rax, [rsp+1E8h+arg_70]
0x1800d0266  mov     qword ptr [rsp+1E8h+var_1C8], rax; int
0x1800d026b  lea     r9, [rsp+1E8h+arg_50]
0x1800d0273  lea     r8, [rsp+1E8h+var_138]
0x1800d027b  lea     rdx, [rsp+1E8h+arg_48]
0x1800d0283  lea     rcx, [rsp+1E8h+var_178]
0x1800d0288  call    ??$MakeAndInitialize@VTransientNotificationDetails@@V1@AEAKAEAPEBGAEAHAEAHAEAU_GUID@@AEAU2@W4WpnToastNotificationPriority@@AEAY00$$CBD$$T@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VTransientNotificationDetails@@@WRL@Microsoft@@@012@AEAKAEAPEBGAEAH3AEAU_GUID@@4$$QEAW4WpnToastNotificationPriority@@AEAY00$$CBD$$QEA$$T@Z
0x1800d028d  mov     rcx, [rsp+1E8h]; this
0x1800d0295  test    eax, eax
0x1800d0297  js      loc_1800D04D4
0x1800d029d  mov     rax, qword ptr [rsp+1E8h+var_130]
0x1800d02a5  mov     qword ptr [rsp+1E8h+var_1C8], rax; int
0x1800d02aa  mov     r9d, [rsp+1E8h+arg_20]
0x1800d02b2  mov     r8, [rsp+1E8h+var_178]
0x1800d02b7  mov     rdx, [rsp+1E8h+var_170]
0x1800d02bc  mov     rcx, [rsp+1E8h+var_128]
0x1800d02c4  call    ?PostNotificationInternal@AppEndpoint@@AEAAJPEAVNotification@@PEAVTransientNotificationDetails@@W4__MIDL___MIDL_itf_wpnplatform_0000_0007_0004@@PEAUIWpnToastFeedback@@@Z; AppEndpoint::PostNotificationInternal(Notification *,TransientNotificationDetails *,__MIDL___MIDL_itf_wpnplatform_0000_0007_0004,IWpnToastFeedback *)
0x1800d02c9  mov     rcx, [rsp+1E8h]; this
0x1800d02d1  test    eax, eax
0x1800d02d3  js      loc_1800D04E8
0x1800d02d9  mov     [r13+0], edi
0x1800d02dd  lea     rcx, [rsp+1E8h+var_178]
0x1800d02e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d02e7  nop
0x1800d02e8  lea     rcx, [rsp+1E8h+var_170]
0x1800d02ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d02f2  nop
0x1800d02f3  lea     rcx, [rsp+1E8h+var_188]
0x1800d02f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d02fd  nop
0x1800d02fe  xor     edx, edx
0x1800d0300  lea     rcx, [rsp+1E8h+pInit]
0x1800d0308  call    ?reset@?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@QEAAXPEAU_GUID@@@Z; wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(_GUID *)
0x1800d030d  nop
0x1800d030e  mov     rcx, rbx
0x1800d0311  xchg    rcx, [rsp+1E8h+var_180]; _Mtx_t
0x1800d0316  test    rcx, rcx
0x1800d0319  jz      short loc_1800D0321
0x1800d031b  call    ?DestroyShared@?$Owner@V?$unique_ptr@VNotificationPlatform@@U?$default_delete@VNotificationPlatform@@@std@@@std@@V?$duration@_JU?$ratio@$00$00@std@@@chrono@2@@Wns@@AEAAXXZ; Wns::Owner<std::unique_ptr<NotificationPlatform>,std::chrono::duration<__int64,std::ratio<1,1>>>::DestroyShared(void)
0x1800d0320  nop
0x1800d0321  lea     rcx, [rsp+1E8h+var_148]
0x1800d0329  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d032e  xor     eax, eax
0x1800d0330  jmp     short loc_1800D0336
0x1800d0332  mov     eax, [rsp+1E8h+cbInit]
0x1800d0336  mov     rcx, [rsp+1E8h+var_48]
0x1800d033e  xor     rcx, rsp; StackCookie
0x1800d0341  call    __security_check_cookie
0x1800d0346  add     rsp, 1B0h
0x1800d034d  pop     r15
0x1800d034f  pop     r14
0x1800d0351  pop     r13
0x1800d0353  pop     r12
0x1800d0355  pop     rdi
0x1800d0356  pop     rsi
0x1800d0357  pop     rbx
0x1800d0358  retn
0x1800d0359  lea     rcx, dword_18015E478
0x1800d0360  call    _Init_thread_header
0x1800d0365  cmp     cs:dword_18015E478, 0FFFFFFFFh
0x1800d036c  jnz     loc_1800CFF32
0x1800d0372  mov     [rsp+1E8h+cbInit], 1
0x1800d037a  lea     r8, off_18011DDD8; "tile"
0x1800d0381  lea     rdx, [rsp+1E8h+cbInit]
0x1800d0386  lea     rcx, [rsp+1E8h+var_E8]
0x1800d038e  call    ??$?0W4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG$0A@@?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG@Z; std::pair<ulong const,std::wstring>::pair<ulong const,std::wstring>(Windows::Networking::PushNotifications::PushNotificationType &&,ushort const * const &)
0x1800d0393  nop
0x1800d0394  xor     ebx, ebx
0x1800d0396  mov     [rsp+1E8h+cbInit], ebx
0x1800d039a  lea     r8, off_18011DDE0; "toast"
0x1800d03a1  lea     rdx, [rsp+1E8h+cbInit]
0x1800d03a6  lea     rcx, [rsp+1E8h+var_C0]
0x1800d03ae  call    ??$?0W4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG$0A@@?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG@Z; std::pair<ulong const,std::wstring>::pair<ulong const,std::wstring>(Windows::Networking::PushNotifications::PushNotificationType &&,ushort const * const &)
0x1800d03b3  nop
0x1800d03b4  mov     [rsp+1E8h+cbInit], 2
0x1800d03bc  lea     r8, off_18011DDC8; "badge"
0x1800d03c3  lea     rdx, [rsp+1E8h+cbInit]
0x1800d03c8  lea     rcx, [rsp+1E8h+var_98]
0x1800d03d0  call    ??$?0W4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG$0A@@?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG@Z; std::pair<ulong const,std::wstring>::pair<ulong const,std::wstring>(Windows::Networking::PushNotifications::PushNotificationType &&,ushort const * const &)
0x1800d03d5  nop
0x1800d03d6  mov     [rsp+1E8h+cbInit], 3
0x1800d03de  lea     r8, off_18011DDD0; "raw"
0x1800d03e5  lea     rdx, [rsp+1E8h+cbInit]
0x1800d03ea  lea     rcx, [rsp+1E8h+var_70]
0x1800d03f2  call    ??$?0W4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG$0A@@?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4PushNotificationType@PushNotifications@Networking@Windows@@AEBQEBG@Z; std::pair<ulong const,std::wstring>::pair<ulong const,std::wstring>(Windows::Networking::PushNotifications::PushNotificationType &&,ushort const * const &)
0x1800d03f7  nop
0x1800d03f8  lea     rax, [rsp+1E8h+var_E8]
0x1800d0400  mov     [rsp+1E8h+var_148], rax
0x1800d0408  lea     rax, [rsp+1E8h+var_48]
0x1800d0410  mov     [rsp+1E8h+var_140], rax
0x1800d0418  lea     rdx, [rsp+1E8h+var_148]
0x1800d0420  lea     rcx, qword_18015E480
0x1800d0427  call    ??0?$unordered_map@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@1@@Z; std::unordered_map<ulong,std::wstring>::unordered_map<ulong,std::wstring>(std::initializer_list<std::pair<ulong const,std::wstring>>)
0x1800d042c  nop
0x1800d042d  lea     r9, ??1?$pair@$$CBW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; void (*)(void *)
0x1800d0434  lea     edx, [rbx+28h]; unsigned __int64
0x1800d0437  lea     r8d, [rbx+4]; unsigned __int64
0x1800d043b  lea     rcx, [rsp+1E8h+var_E8]; void *
0x1800d0443  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800d0448  lea     rcx, _AppEndpoint__PostNotification2____3____dynamic_atexit_destructor_for__typeMap__; void (__cdecl *)()
0x1800d044f  call    atexit
0x1800d0454  nop
0x1800d0455  lea     rcx, dword_18015E478
0x1800d045c  call    _Init_thread_footer
0x1800d0461  jmp     loc_1800CFF34
0x1800d0466  mov     r9d, 803E0105h; char *
0x1800d046c  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d0473  mov     edx, 3ADh; void *
0x1800d0478  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d047e  mov     r9d, 803E0105h; char *
0x1800d0484  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d048b  mov     edx, 3B0h; void *
0x1800d0490  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d0496  mov     r9d, eax; char *
0x1800d0499  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d04a0  mov     edx, 3BFh; void *
0x1800d04a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
