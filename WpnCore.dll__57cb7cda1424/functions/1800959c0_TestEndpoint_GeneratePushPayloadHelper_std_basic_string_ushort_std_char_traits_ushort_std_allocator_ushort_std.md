# TestEndpoint::GeneratePushPayloadHelper(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800959c0`
- end: `0x180096096`
- name: `?GeneratePushPayloadHelper@TestEndpoint@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `1750`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d28e0`
- `0x1800d29b0`
- `0x1800d2a80`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011618`
- `0x1800117c0`
- `0x180017a6c`
- `0x180018238`
- `0x180018d24`
- `0x18001a3c8`
- `0x18001bf30`
- `0x1800299c0`
- `0x18002ab88`
- `0x18002bfbc`
- `0x18002df60`
- `0x180034624`
- `0x18003fe5c`
- `0x18004d6f0`
- `0x1800535d0`
- `0x180065b08`
- `0x18006e48c`
- `0x18006e4c4`
- `0x1800959c0`
- `0x18009609c`
- `0x1800961c8`
- `0x18009628c`
- `0x1800962c8`
- `0x1800963cc`
- `0x1800967bc`
- `0x1800b99f0`
- `0x1800ba0d0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180095b8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180095b8e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180095d18`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180095d4e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180095d18`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180095d4e`
- `msvcp_win!_Cnd_signal` at `0x180096049`
- `msvcp_win!_Cnd_signal` at `0x180096049`
- `msvcp_win!_Mtx_unlock` at `0x18009603a`
- `msvcp_win!_Mtx_unlock` at `0x18009603a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180095c24`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180095c24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TestEndpoint::GeneratePushPayloadHelper(__int64 a1, _QWORD *a2, void *a3, _QWORD *a4, _QWORD *a5)
{
  __int64 v8; // rbx
  int v9; // eax
  int v10; // r12d
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v13; // rdx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  unsigned int NotificationTrackingId; // ebx
  unsigned __int64 v19; // rcx
  int FutureTime; // eax
  _WORD *v21; // r8
  _WORD *i; // r9
  const BYTE *v23; // rcx
  IStream *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  int v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v34; // rdx
  int v35; // eax
  __int64 v36; // rbx
  __int64 v37; // rdi
  __int64 v38; // rsi
  __int64 v39; // r14
  void *v40; // rax
  __int64 v41; // rbx
  void *v42; // rax
  struct WorkItem *v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rdx
  ThreadPool *v46; // rcx
  int v47; // eax
  __int64 v48; // rdi
  __int64 v49; // rbx
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  struct _FILETIME v53; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  ThreadPool *v56; // [rsp+68h] [rbp-98h] BYREF
  __int64 v57; // [rsp+70h] [rbp-90h] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h] BYREF
  __int64 v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+90h] [rbp-70h] BYREF
  int v62; // [rsp+94h] [rbp-6Ch] BYREF
  int v63; // [rsp+98h] [rbp-68h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h] BYREF
  void *v70; // [rsp+D0h] [rbp-30h]
  void *v71; // [rsp+D8h] [rbp-28h]
  _DWORD v72[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v73; // [rsp+E8h] [rbp-18h]
  _QWORD *v74; // [rsp+F0h] [rbp-10h]
  _QWORD *v75; // [rsp+F8h] [rbp-8h]
  __int64 v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+110h] [rbp+10h]
  struct _FILETIME v79; // [rsp+118h] [rbp+18h]
  struct _FILETIME v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  __int64 LastBootTime; // [rsp+130h] [rbp+30h]
  char v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+139h] [rbp+39h]
  __int16 v85; // [rsp+13Dh] [rbp+3Dh]
  char v86; // [rsp+13Fh] [rbp+3Fh]
  __int64 v87; // [rsp+140h] [rbp+40h]
  GUID v88; // [rsp+148h] [rbp+48h]
  __int64 v89; // [rsp+158h] [rbp+58h]
  __int64 v90; // [rsp+160h] [rbp+60h]
  GUID v91; // [rsp+170h] [rbp+70h] BYREF
  GUID pguid; // [rsp+180h] [rbp+80h] BYREF
  BYTE *pInit[4]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v94[128]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v70 = a4;
  v71 = a5;
  Wns::NotificationPlatformHandle::Get(a1 + 24, &v54);
  if ( !v54 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)0x803E0105LL,
      v50);
  v55 = 0;
  v8 = *(_QWORD *)(v54 + 184);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v9 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v8 + 144))(
         *(_QWORD *)(v8 + 144),
         &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
         &v55);
  v10 = -2143420155;
  v11 = v55;
  if ( v9 >= 0 && !v55 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      v50);
    v9 = -2143420155;
    v11 = v55;
  }
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v9,
      v50);
  v60 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v11 + 272LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  if ( a2[3] <= 7u )
    v13 = a2;
  else
    v13 = (_QWORD *)*a2;
  v14 = v12(v11, v13, &v60);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v14,
      v50);
  v59 = 0;
  v15 = v60;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v59,
    0);
  v17 = v16(v15, &v59);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v17,
      v50);
  NotificationTrackingId = NotificationPlatform::GetNotificationTrackingId(*(NotificationPlatform **)(v54 + 184));
  v69 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v53 = 0;
  FutureTime = WpnGetFutureTime(v19, &v53);
  if ( FutureTime < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)FutureTime,
      v50);
  v65 = 0;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v94);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v21 = a3;
  else
    v21 = *(_WORD **)a3;
  for ( i = v21; *i; ++i )
    ;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v94,
    pInit,
    v21,
    i);
  v23 = (const BYTE *)pInit;
  if ( pInit[3] > (BYTE *)0xF )
    v23 = pInit[0];
  v24 = SHCreateMemStream(v23, *((_DWORD *)a3 + 4));
  Microsoft::WRL::ComPtr<WNSChannelDetails>::Attach(&v65, v24);
  v72[0] = NotificationTrackingId;
  v72[1] = 0;
  if ( a2[3] <= 7u )
    v25 = a2;
  else
    v25 = (_QWORD *)*a2;
  v73 = v25;
  if ( a4[3] <= 7u )
    v26 = a4;
  else
    v26 = (_QWORD *)*a4;
  v74 = v26;
  if ( a5[3] <= 7u )
    v27 = a5;
  else
    v27 = (_QWORD *)*a5;
  v75 = v27;
  v76 = v65;
  v77 = 0;
  v78 = 0;
  v79 = v53;
  v80 = SystemTimeAsFileTime;
  v81 = 0;
  LastBootTime = GetLastBootTime();
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = GUID_NULL;
  v89 = 1;
  v90 = 0;
  v64 = 0;
  v28 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(
          (__int64)&v64,
          (__int64)v72);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v28,
      v50);
  pguid = GUID_NULL;
  v29 = CoCreateGuid(&pguid);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v29,
      v50);
  v91 = GUID_NULL;
  v30 = CoCreateGuid(&v91);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v30,
      v50);
  v58 = 0;
  v66 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v53.dwLowDateTime = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v31 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,int,unsigned short const (&)[1],int,int,_GUID &,_GUID &,enum WpnToastNotificationPriority,char const (&)[1],std::nullptr_t>(
          (unsigned int)&v58,
          (unsigned int)&v53,
          (unsigned int)&word_180124798,
          (unsigned int)&v63,
          (__int64)&v62,
          (__int64)&pguid,
          (__int64)&v91,
          (__int64)&v61,
          (__int64)word_1801258B2,
          (__int64)&v66);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v31,
      v51);
  v57 = 0;
  v32 = v55;
  v33 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v55 + 192LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  if ( a2[3] <= 7u )
    v34 = a2;
  else
    v34 = (_QWORD *)*a2;
  v35 = v33(v32, v34, &v57);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v35,
      v51);
  ConvertUtf8ToUtf16(&v68, v59);
  v36 = v68;
  v37 = v58;
  v38 = v64;
  v39 = v57;
  v40 = operator new(0x78u);
  LOBYTE(v51) = 0;
  v53 = (struct _FILETIME)NotificationDeliveryTransaction::NotificationDeliveryTransaction(
                            v40,
                            v39,
                            v38,
                            v37,
                            v51,
                            0,
                            v36);
  v41 = *(_QWORD *)(v54 + 184);
  v42 = operator new(0xC8u);
  v43 = (struct WorkItem *)NotificationAvailableWork::NotificationAvailableWork(v42, &v53, v41);
  v56 = 0;
  v44 = *(_QWORD *)(v54 + 184);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IGlobalInterfaceTable>::InternalAddRef(v44 + 48, v45);
  v46 = *(ThreadPool **)(v44 + 48);
  v56 = v46;
  if ( v46 )
  {
    v10 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      v52);
    v46 = v56;
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v10,
      v52);
  v66 = 0;
  v47 = ThreadPool::Submit(v46, v43);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\testendpoint.cpp",
      (const char *)(unsigned int)v47,
      v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(&v66);
  std::unique_ptr<NotificationDeliveryTransaction>::~unique_ptr<NotificationDeliveryTransaction>(&v53);
  wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(&v68, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  std::string::_Tidy_deallocate(pInit);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v94);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v48 = _InterlockedExchange64(&v54, 0);
  if ( v48 )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)v48);
    v49 = --*(_QWORD *)(v48 + 152);
    _Mtx_unlock((_Mtx_t)v48);
    if ( !v49 )
      _Cnd_signal((_Cnd_t)(v48 + 80));
  }
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(a2);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(a3);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v70);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v71);
}

```

## disassembly

```asm
0x1800959c0  push    rbp
0x1800959c2  push    rbx
0x1800959c3  push    rsi
0x1800959c4  push    rdi
0x1800959c5  push    r12
0x1800959c7  push    r13
0x1800959c9  push    r14
0x1800959cb  push    r15
0x1800959cd  lea     rbp, [rsp-148h]
0x1800959d5  sub     rsp, 248h
0x1800959dc  mov     rax, cs:__security_cookie
0x1800959e3  xor     rax, rsp
0x1800959e6  mov     [rbp+180h+var_50], rax
0x1800959ed  mov     rsi, r9
0x1800959f0  mov     [rbp+180h+var_1B0], r9
0x1800959f4  mov     r13, r8
0x1800959f7  mov     r15, rdx
0x1800959fa  mov     r14, [rbp+180h+arg_20]
0x180095a01  mov     [rbp+180h+var_1A8], r14
0x180095a05  add     rcx, 18h
0x180095a09  lea     rdx, [rsp+280h+var_228]
0x180095a0e  call    ?Get@NotificationPlatformHandle@Wns@@QEAA?AVNotificationPlatformPtr@2@XZ
0x180095a13  mov     rax, [rsp+280h+var_228]
0x180095a18  nop
0x180095a19  mov     rcx, [rbp+188h]; this
0x180095a20  xor     edi, edi
0x180095a22  test    rax, rax
0x180095a25  jnz     short loc_180095A3D
0x180095a27  mov     r9d, 803E0105h; char *
0x180095a2d  lea     r8, aOnecoreuapBase_118
0x180095a34  lea     edx, [rdi+55h]; void *
0x180095a37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095a3d  mov     [rsp+280h+var_220], rdi
0x180095a42  mov     rax, [rsp+280h+var_228]
0x180095a47  nop
0x180095a48  mov     rbx, [rax+0B8h]
0x180095a4f  lea     rcx, [rsp+280h+var_220]
0x180095a54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x180095a59  nop
0x180095a5a  mov     rcx, [rbx+90h]
0x180095a61  mov     rax, [rcx]
0x180095a64  lea     r8, [rsp+280h+var_220]
0x180095a69  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x180095a70  mov     rax, [rax]
0x180095a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a78  nop
0x180095a79  mov     r12d, 803E0105h
0x180095a7f  mov     rbx, [rsp+280h+var_220]
0x180095a84  test    eax, eax
0x180095a86  js      short loc_180095AB0
0x180095a88  test    rbx, rbx
0x180095a8b  jnz     short loc_180095AB0
0x180095a8d  mov     rcx, [rbp+188h]; this
0x180095a94  mov     r9d, r12d; char *
0x180095a97  lea     r8, aOnecoreuapBase_161
0x180095a9e  mov     edx, 400h; void *
0x180095aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095aa8  mov     eax, r12d
0x180095aab  mov     rbx, [rsp+280h+var_220]
0x180095ab0  mov     rcx, [rbp+188h]; this
0x180095ab7  test    eax, eax
0x180095ab9  jns     short loc_180095AD0
0x180095abb  mov     r9d, eax; char *
0x180095abe  lea     r8, aOnecoreuapBase_118
0x180095ac5  mov     edx, 57h ; 'W'; void *
0x180095aca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095ad0  mov     [rbp+180h+var_1F8], rdi
0x180095ad4  mov     rax, [rbx]
0x180095ad7  mov     rdi, [rax+110h]
0x180095ade  lea     rcx, [rbp+180h+var_1F8]
0x180095ae2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x180095ae7  cmp     qword ptr [r15+18h], 7
0x180095aec  jbe     short loc_180095AF3
0x180095aee  mov     rdx, [r15]
0x180095af1  jmp     short loc_180095AF6
0x180095af3  mov     rdx, r15
0x180095af6  lea     r8, [rbp+180h+var_1F8]
0x180095afa  mov     rcx, rbx
0x180095afd  mov     rax, rdi
0x180095b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b05  mov     rcx, [rbp+188h]; this
0x180095b0c  xor     edx, edx
0x180095b0e  test    eax, eax
0x180095b10  jns     short loc_180095B27
0x180095b12  mov     r9d, eax; char *
0x180095b15  lea     r8, aOnecoreuapBase_118
0x180095b1c  mov     edx, 59h ; 'Y'; void *
0x180095b21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095b27  mov     [rbp+180h+var_200], rdx
0x180095b2b  mov     rdi, [rbp+180h+var_1F8]
0x180095b2f  mov     rax, [rdi]
0x180095b32  mov     rbx, [rax+20h]
0x180095b36  lea     rcx, [rbp+180h+var_200]
0x180095b3a  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z
0x180095b3f  lea     rdx, [rbp+180h+var_200]
0x180095b43  mov     rcx, rdi
0x180095b46  mov     rax, rbx
0x180095b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b4e  mov     rcx, [rbp+188h]; this
0x180095b55  xor     edi, edi
0x180095b57  test    eax, eax
0x180095b59  jns     short loc_180095B6E
0x180095b5b  mov     r9d, eax; char *
0x180095b5e  lea     r8, aOnecoreuapBase_118
0x180095b65  lea     edx, [rdi+5Bh]; void *
0x180095b68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095b6e  mov     rcx, [rsp+280h+var_228]
0x180095b73  nop
0x180095b74  mov     rcx, [rcx+0B8h]; this
0x180095b7b  call    ?GetNotificationTrackingId@NotificationPlatform@@QEAAKXZ
0x180095b80  mov     ebx, eax
0x180095b82  mov     [rbp+180h+var_1B8], rdi
0x180095b86  mov     qword ptr [rbp+180h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180095b8a  lea     rcx, [rbp+180h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180095b8e  call    cs:__imp_GetSystemTimeAsFileTime
0x180095b94  mov     qword ptr [rsp+280h+var_230.dwLowDateTime], rdi
0x180095b99  lea     rdx, [rsp+280h+var_230]; struct _FILETIME *
0x180095b9e  call    ?WpnGetFutureTime@@YAJ_KPEAU_FILETIME@@@Z
0x180095ba3  mov     rcx, [rbp+188h]; this
0x180095baa  test    eax, eax
0x180095bac  jns     short loc_180095BC3
0x180095bae  mov     r9d, eax; char *
0x180095bb1  lea     r8, aOnecoreuapBase_118
0x180095bb8  mov     edx, 63h ; 'c'; void *
0x180095bbd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095bc3  mov     [rbp+180h+var_1D8], rdi
0x180095bc7  lea     rcx, [rbp+180h+var_D0]
0x180095bce  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ
0x180095bd3  cmp     qword ptr [r13+18h], 7
0x180095bd8  jbe     short loc_180095BE0
0x180095bda  mov     r8, [r13+0]
0x180095bde  jmp     short loc_180095BE3
0x180095be0  mov     r8, r13
0x180095be3  mov     r9, r8
0x180095be6  cmp     [r8], di
0x180095bea  jz      short loc_180095BF6
0x180095bec  add     r9, 2
0x180095bf0  cmp     [r9], di
0x180095bf4  jnz     short loc_180095BEC
0x180095bf6  lea     rdx, [rbp+180h+pInit]
0x180095bfd  lea     rcx, [rbp+180h+var_D0]
0x180095c04  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z
0x180095c09  lea     rcx, [rbp+180h+pInit]
0x180095c10  cmp     [rbp+180h+var_D8], 0Fh
0x180095c18  cmova   rcx, [rbp+180h+pInit]; pInit
0x180095c20  mov     edx, [r13+10h]; cbInit
0x180095c24  call    cs:__imp_SHCreateMemStream
0x180095c2a  mov     rdx, rax
0x180095c2d  lea     rcx, [rbp+180h+var_1D8]
0x180095c31  call    ?Attach@?$ComPtr@VWNSChannelDetails@@@WRL@Microsoft@@QEAAXPEAVWNSChannelDetails@@@Z
0x180095c36  mov     [rbp+180h+var_1A0], ebx
0x180095c39  xor     eax, eax
0x180095c3b  mov     [rbp+180h+var_19C], eax
0x180095c3e  cmp     qword ptr [r15+18h], 7
0x180095c43  jbe     short loc_180095C4A
0x180095c45  mov     rax, [r15]
0x180095c48  jmp     short loc_180095C4D
0x180095c4a  mov     rax, r15
0x180095c4d  mov     [rbp+180h+var_198], rax
0x180095c51  cmp     qword ptr [rsi+18h], 7
0x180095c56  jbe     short loc_180095C5D
0x180095c58  mov     rax, [rsi]
0x180095c5b  jmp     short loc_180095C60
0x180095c5d  mov     rax, rsi
0x180095c60  mov     [rbp+180h+var_190], rax
0x180095c64  cmp     qword ptr [r14+18h], 7
0x180095c69  jbe     short loc_180095C70
0x180095c6b  mov     rax, [r14]
0x180095c6e  jmp     short loc_180095C73
0x180095c70  mov     rax, r14
0x180095c73  mov     [rbp+180h+var_188], rax
0x180095c77  mov     rax, [rbp+180h+var_1D8]
0x180095c7b  mov     [rbp+180h+var_180], rax
0x180095c7f  mov     [rbp+180h+var_178], rdi
0x180095c83  mov     [rbp+180h+var_170], rdi
0x180095c87  mov     rax, qword ptr [rsp+280h+var_230.dwLowDateTime]
0x180095c8c  mov     [rbp+180h+var_168], rax
0x180095c90  mov     rax, qword ptr [rbp+180h+SystemTimeAsFileTime.dwLowDateTime]
0x180095c94  mov     [rbp+180h+var_160], rax
0x180095c98  mov     [rbp+180h+var_158], rdi
0x180095c9c  call    ?GetLastBootTime@@YA_JXZ
0x180095ca1  mov     [rbp+180h+var_150], rax
0x180095ca5  mov     [rbp+180h+var_148], dil
0x180095ca9  xor     eax, eax
0x180095cab  mov     [rbp+180h+var_147], eax
0x180095cae  mov     [rbp+180h+var_143], ax
0x180095cb2  mov     [rbp+180h+var_141], al
0x180095cb5  mov     [rbp+180h+var_140], rdi
0x180095cb9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180095cc0  movdqu  [rbp+180h+var_138], xmm0
0x180095cc5  mov     [rbp+180h+var_128], 1
0x180095ccd  mov     [rbp+180h+var_120], rdi
0x180095cd1  mov     [rbp+180h+var_1E0], rdi
0x180095cd5  lea     rdx, [rbp+180h+var_1A0]
0x180095cd9  lea     rcx, [rbp+180h+var_1E0]
0x180095cdd  call    ??$MakeAndInitialize@VNotification@@V1@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VNotification@@@WRL@Microsoft@@@012@AEAUInitializer@Notification@@@Z
0x180095ce2  mov     rcx, [rbp+188h]; this
0x180095ce9  test    eax, eax
0x180095ceb  jns     short loc_180095D02
0x180095ced  mov     r9d, eax; char *
0x180095cf0  lea     r8, aOnecoreuapBase_118
0x180095cf7  mov     edx, 7Dh ; '}'; void *
0x180095cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095d02  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180095d09  movdqu  xmmword ptr [rbp+180h+pguid.Data1], xmm0
0x180095d11  lea     rcx, [rbp+180h+pguid]; pguid
0x180095d18  call    cs:__imp_CoCreateGuid
0x180095d1e  mov     rcx, [rbp+188h]; this
0x180095d25  test    eax, eax
0x180095d27  jns     short loc_180095D3E
0x180095d29  mov     r9d, eax; char *
0x180095d2c  lea     r8, aOnecoreuapBase_118
0x180095d33  mov     edx, 81h; void *
0x180095d38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095d3e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180095d45  movdqu  xmmword ptr [rbp+180h+var_110.Data1], xmm0
0x180095d4a  lea     rcx, [rbp+180h+var_110]; pguid
0x180095d4e  call    cs:__imp_CoCreateGuid
0x180095d54  mov     rcx, [rbp+188h]; this
0x180095d5b  test    eax, eax
0x180095d5d  jns     short loc_180095D74
0x180095d5f  mov     r9d, eax; char *
0x180095d62  lea     r8, aOnecoreuapBase_118
0x180095d69  mov     edx, 84h; void *
0x180095d6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095d74  mov     [rsp+280h+var_208], rdi
0x180095d79  mov     [rbp+180h+var_1D0], rdi
0x180095d7d  mov     [rbp+180h+var_1F0], edi
0x180095d80  mov     [rbp+180h+var_1EC], edi
0x180095d83  mov     [rbp+180h+var_1E8], edi
0x180095d86  mov     [rsp+280h+var_230.dwLowDateTime], edi
0x180095d8a  lea     rcx, [rsp+280h+var_208]
0x180095d8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x180095d94  lea     rax, [rbp+180h+var_1D0]
0x180095d98  mov     [rsp+280h+var_238], rax
0x180095d9d  lea     rax, word_1801258B2
0x180095da4  mov     [rsp+280h+var_240], rax
0x180095da9  lea     rax, [rbp+180h+var_1F0]
0x180095dad  mov     [rsp+280h+var_248], rax
0x180095db2  lea     rax, [rbp+180h+var_110]
0x180095db6  mov     [rsp+280h+var_250], rax
0x180095dbb  lea     rax, [rbp+180h+pguid]
0x180095dc2  mov     [rsp+280h+var_258], rax
0x180095dc7  lea     rax, [rbp+180h+var_1EC]
0x180095dcb  mov     qword ptr [rsp+280h+var_260], rax; int
0x180095dd0  lea     r9, [rbp+180h+var_1E8]
0x180095dd4  lea     r8, word_180124798
0x180095ddb  lea     rdx, [rsp+280h+var_230]
0x180095de0  lea     rcx, [rsp+280h+var_208]
0x180095de5  call    ??$MakeAndInitialize@VTransientNotificationDetails@@V1@HAEAY00$$CBGHHAEAU_GUID@@AEAU2@W4WpnToastNotificationPriority@@AEAY00$$CBD$$T@Details@WRL@Microsoft@@YAJPEAPEAVTransientNotificationDetails@@$$QEAHAEAY00$$CBG11AEAU_GUID@@3$$QEAW4WpnToastNotificationPriority@@AEAY00$$CBD$$QEA$$T@Z
0x180095dea  mov     rcx, [rbp+188h]; this
0x180095df1  test    eax, eax
0x180095df3  jns     short loc_180095E0A
0x180095df5  mov     r9d, eax; char *
0x180095df8  lea     r8, aOnecoreuapBase_118
0x180095dff  mov     edx, 92h; void *
0x180095e04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095e0a  mov     [rsp+280h+var_210], rdi
0x180095e0f  mov     rbx, [rsp+280h+var_220]
0x180095e14  mov     rax, [rbx]
0x180095e17  mov     rdi, [rax+0C0h]
0x180095e1e  lea     rcx, [rsp+280h+var_210]
0x180095e23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x180095e28  cmp     qword ptr [r15+18h], 7
0x180095e2d  jbe     short loc_180095E34
0x180095e2f  mov     rdx, [r15]
0x180095e32  jmp     short loc_180095E37
0x180095e34  mov     rdx, r15
0x180095e37  lea     r8, [rsp+280h+var_210]
0x180095e3c  mov     rcx, rbx
0x180095e3f  mov     rax, rdi
0x180095e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e47  mov     rcx, [rbp+188h]; this
0x180095e4e  test    eax, eax
0x180095e50  jns     short loc_180095E67
0x180095e52  mov     r9d, eax; char *
0x180095e55  lea     r8, aOnecoreuapBase_118
0x180095e5c  mov     edx, 95h; void *
0x180095e61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180095e67  mov     rdx, [rbp+180h+var_200]
0x180095e6b  lea     rcx, [rbp+180h+var_1C0]
0x180095e6f  call    ?ConvertUtf8ToUtf16@@YA?AV?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@PEBD@Z
0x180095e74  mov     rbx, [rbp+180h+var_1C0]
0x180095e78  mov     rdi, [rsp+280h+var_208]
0x180095e7d  mov     rsi, [rbp+180h+var_1E0]
0x180095e81  mov     r14, [rsp+280h+var_210]
0x180095e86  mov     ecx, 78h ; 'x'; Size
0x180095e8b  call    ??2@YAPEAX_K@Z
0x180095e90  mov     [rsp+280h+var_250], rbx
0x180095e95  xor     ecx, ecx
0x180095e97  mov     dword ptr [rsp+280h+var_258], ecx
0x180095e9b  mov     byte ptr [rsp+280h+var_260], cl; int
0x180095e9f  mov     r9, rdi
0x180095ea2  mov     r8, rsi
0x180095ea5  mov     rdx, r14
0x180095ea8  mov     rcx, rax
0x180095eab  call    ??0NotificationDeliveryTransaction@@QEAA@PEAUINotificationHandler@@PEAVNotification@@PEAVTransientNotificationDetails@@_NW4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@PEBG@Z
0x180095eb0  mov     qword ptr [rsp+280h+var_230.dwLowDateTime], rax
0x180095eb5  mov     rax, [rsp+280h+var_228]
0x180095eba  nop
  ... truncated ...
```
