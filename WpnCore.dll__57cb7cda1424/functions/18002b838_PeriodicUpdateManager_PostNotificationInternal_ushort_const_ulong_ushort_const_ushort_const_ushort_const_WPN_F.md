# PeriodicUpdateManager::PostNotificationInternal(ushort const *,ulong,ushort const *,ushort const *,ushort const *,_WPN_FILE_TIME,_GUID const *,ulong *)

- ea: `0x18002b838`
- end: `0x18002bf5c`
- name: `?PostNotificationInternal@PeriodicUpdateManager@@AEAAXPEBGK000U_WPN_FILE_TIME@@PEBU_GUID@@PEAK@Z`
- size: `1828`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005f240`

## callees

- `0x180004e38`
- `0x18000c1cc`
- `0x18000e5f4`
- `0x18002ab88`
- `0x18002b838`
- `0x18002bf64`
- `0x18002bfbc`
- `0x18002bfd8`
- `0x18002c0d4`
- `0x18002c22c`
- `0x180063dcc`
- `0x18006e48c`
- `0x1800a4ac0`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800b9a44`
- `0x1800b9ea0`
- `0x1800bc31c`
- `0x1800bc384`
- `0x1800cc9d8`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b8b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b8b5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002ba5f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002ba5f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18002b943`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18002b943`

## string_xrefs

- `0x18002bd67`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bd7c`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bd91`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bda6`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bdbb`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bdd0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bde5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bdfa`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002be0f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18002bf4a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall PeriodicUpdateManager::PostNotificationInternal(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        unsigned int *a9)
{
  int v11; // ebx
  int v12; // edi
  __int64 v13; // rcx
  BYTE *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  IStream *v17; // r14
  __int64 v18; // rax
  _QWORD *v19; // rcx
  int v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  PlatformFactory *v25; // rax
  __int64 (__fastcall *v26)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v32)(_QWORD, GUID *, __int64 *); // rsi
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rcx
  void *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rcx
  BYTE *v41; // rcx
  PlatformFactory *v42; // rax
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int NotificationTrackingId; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  int v53; // [rsp+90h] [rbp-70h] BYREF
  int v54[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  BYTE *pInit; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v58[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v60[3]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v61[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v62; // [rsp+F8h] [rbp-8h]
  _QWORD *v63; // [rsp+100h] [rbp+0h]
  const wchar_t *v64; // [rsp+108h] [rbp+8h]
  IStream *v65; // [rsp+110h] [rbp+10h]
  _QWORD v66[2]; // [rsp+118h] [rbp+18h] BYREF
  int v67; // [rsp+128h] [rbp+28h]
  int v68; // [rsp+12Ch] [rbp+2Ch]
  struct _FILETIME v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]
  __int64 LastBootTime; // [rsp+140h] [rbp+40h] BYREF
  char v72; // [rsp+148h] [rbp+48h]
  int v73; // [rsp+149h] [rbp+49h]
  __int16 v74; // [rsp+14Dh] [rbp+4Dh]
  char v75; // [rsp+14Fh] [rbp+4Fh]
  __int64 v76; // [rsp+150h] [rbp+50h]
  GUID v77; // [rsp+158h] [rbp+58h]
  _QWORD v78[5]; // [rsp+168h] [rbp+68h] BYREF
  GUID pguid; // [rsp+190h] [rbp+90h] BYREF
  __int128 v80; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v53 = a3;
  v55 = a5;
  *(_QWORD *)v54 = a6;
  *a9 = 0;
  NotificationTrackingId = NotificationPlatform::GetNotificationTrackingId(*(NotificationPlatform **)(a1 + 32));
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v46 = 0;
  if ( *a7 == 1 )
  {
    v12 = a7[1];
    v11 = a7[2];
  }
  else
  {
    v11 = HIDWORD(v46);
    v12 = 0;
  }
  ConvertUtf16ToUtf8(&pInit, a4);
  if ( !pInit )
  {
    v16 = 2147942487LL;
LABEL_49:
    LODWORD(v15) = 0;
    goto LABEL_8;
  }
  v13 = 5120;
  v14 = pInit;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = (5120 - v13) & -(__int64)(v13 != 0);
  v16 = v13 == 0 ? 0x80070057 : 0;
  if ( !v13 )
    goto LABEL_49;
LABEL_8:
  if ( (int)v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)v16,
      v43);
  v17 = SHCreateMemStream(pInit, v15);
  v60[1] = v17;
  if ( dword_18015E510 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18015E510);
    if ( dword_18015E510 == -1 )
    {
      v45 = 1;
      std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v61, &v45, off_18011DE20);
      v45 = 0;
      std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v66, &v45, off_18011DE10);
      v45 = 2;
      std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(
        &LastBootTime,
        &v45,
        off_18011DE18);
      v45 = 3;
      std::pair<unsigned long const,std::wstring>::pair<unsigned long const,std::wstring>(v78, &v45, off_18011DE08);
      v58[0] = v61;
      v58[1] = &pguid;
      std::unordered_map<unsigned long,std::wstring>::unordered_map<unsigned long,std::wstring>(qword_18015E520, v58);
      `eh vector destructor iterator'(
        v61,
        0x28u,
        4u,
        std::pair<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 const,std::wstring>::~pair<enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 const,std::wstring>);
      atexit(PeriodicUpdateManager::PostNotificationInternal_::_2_::_dynamic_atexit_destructor_for__typeMap__);
      Init_thread_footer(&dword_18015E510);
    }
  }
  v61[0] = NotificationTrackingId;
  v61[1] = 0;
  v62 = a2;
  v18 = std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Try_emplace<unsigned long const &,>(
          qword_18015E520,
          (__int64)&v80,
          &v53);
  v19 = (_QWORD *)(*(_QWORD *)v18 + 24LL);
  if ( *(_QWORD *)(*(_QWORD *)v18 + 48LL) > 7u )
    v19 = (_QWORD *)*v19;
  v63 = v19;
  v64 = L"Xml";
  v65 = v17;
  v66[0] = v55;
  v66[1] = *(_QWORD *)v54;
  v67 = v12;
  v68 = v11;
  v69 = SystemTimeAsFileTime;
  v70 = 4;
  LastBootTime = GetLastBootTime();
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = GUID_NULL;
  v78[0] = 1;
  v78[1] = 0;
  v52 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  v20 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(&v52, v61);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v20,
      v43);
  pguid = 0;
  v21 = CoCreateGuid(&pguid);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v21,
      v43);
  v80 = 0;
  v48 = 0;
  v59 = 0;
  v60[0] = 0;
  v45 = 0;
  v54[0] = 0;
  LODWORD(v55) = 0;
  v58[0] = 0;
  LODWORD(v46) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v22 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,int,std::nullptr_t,int,int,_GUID &,_GUID &,enum WpnToastNotificationPriority,std::nullptr_t,std::nullptr_t>(
          (unsigned int)&v48,
          (unsigned int)&v46,
          (unsigned int)v58,
          (unsigned int)&v55,
          (__int64)v54,
          (__int64)&v80,
          (__int64)&pguid,
          (__int64)&v45,
          (__int64)v60,
          (__int64)&v59);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v22,
      v44);
  v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v48 + 32) + 88LL))(v48 + 32, a8);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v23,
      v44);
  v24 = 0;
  v46 = 0;
  v25 = (PlatformFactory *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( v25 )
  {
    v42 = PlatformFactory::PlatformFactory(v25);
    Microsoft::WRL::ComPtr<WNSChannelDetails>::Attach(&v46, v42);
    v24 = v46;
  }
  v58[0] = v24;
  if ( !v24 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)0x8000FFFFLL,
      v44);
  v51 = 0;
  v26 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v24 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v27 = v26(v24, 0, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v51);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v27,
      v44);
  v50 = 0;
  v28 = v51;
  v29 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v51 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  v30 = v29(v28, &v50);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v30,
      v44);
  v49 = 0;
  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  v32 = **v50;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v33 = v32(v31, &GUID_926516e8_d891_45bc_9de5_6959fb8ecac5, &v49);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v33,
      v44);
  v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v49 + 328LL))(
          v49,
          (v52 + 32) & -(__int64)(v52 != 0),
          (v48 + 32) & -(__int64)(v48 != 0),
          4);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v34,
      0);
  *a9 = NotificationTrackingId;
  v35 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
  }
  v37 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v39 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  if ( v17 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v17 + 16LL))(v17);
  v41 = pInit;
  pInit = 0;
  if ( v41 )
    wil::details::FreeProcessHeap((wil::details *)v41, v38);
}

```

## disassembly

```asm
0x18002b838  push    rbp
0x18002b83a  push    rbx
0x18002b83b  push    rsi
0x18002b83c  push    rdi
0x18002b83d  push    r12
0x18002b83f  push    r13
0x18002b841  push    r14
0x18002b843  push    r15
0x18002b845  lea     rbp, [rsp-0C8h]
0x18002b84d  sub     rsp, 1C8h
0x18002b854  mov     rax, cs:__security_cookie
0x18002b85b  xor     rax, rsp
0x18002b85e  mov     [rbp+100h+var_50], rax
0x18002b865  mov     rsi, r9
0x18002b868  mov     r12, rdx
0x18002b86b  mov     rbx, [rbp+100h+arg_30]
0x18002b872  mov     [rbp+100h+var_170], r8d
0x18002b876  mov     rax, [rbp+100h+arg_20]
0x18002b87d  mov     [rbp+100h+var_160], rax
0x18002b881  mov     rax, [rbp+100h+arg_28]
0x18002b888  mov     qword ptr [rbp+100h+var_168], rax
0x18002b88c  mov     r13, [rbp+100h+arg_38]
0x18002b893  mov     r15, [rbp+100h+arg_40]
0x18002b89a  xor     r14d, r14d
0x18002b89d  mov     [r15], r14d
0x18002b8a0  mov     rcx, [rcx+20h]; this
0x18002b8a4  call    ?GetNotificationTrackingId@NotificationPlatform@@QEAAKXZ; NotificationPlatform::GetNotificationTrackingId(void)
0x18002b8a9  mov     [rsp+200h+var_1A0], eax
0x18002b8ad  mov     qword ptr [rbp+100h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18002b8b1  lea     rcx, [rbp+100h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002b8b5  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b8bb  mov     [rsp+200h+var_1A8], r14
0x18002b8c0  cmp     dword ptr [rbx], 1
0x18002b8c3  jz      loc_18002BE21
0x18002b8c9  mov     ebx, dword ptr [rsp+200h+var_1A8+4]
0x18002b8cd  mov     edi, r14d
0x18002b8d0  mov     rdx, rsi
0x18002b8d3  lea     rcx, [rbp+100h+pInit]
0x18002b8d7  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x18002b8dc  nop
0x18002b8dd  mov     r10, [rbp+100h+pInit]
0x18002b8e1  test    r10, r10
0x18002b8e4  jz      loc_18002BE2C
0x18002b8ea  mov     edx, 1400h
0x18002b8ef  mov     ecx, edx
0x18002b8f1  mov     rax, r10
0x18002b8f4  cmp     [rax], r14b
0x18002b8f7  jz      short loc_18002B902
0x18002b8f9  inc     rax
0x18002b8fc  sub     rcx, 1
0x18002b900  jnz     short loc_18002B8F4
0x18002b902  mov     rax, rcx
0x18002b905  sub     rdx, rcx
0x18002b908  neg     rax
0x18002b90b  sbb     r8, r8
0x18002b90e  and     r8, rdx
0x18002b911  mov     rax, rcx
0x18002b914  neg     rax
0x18002b917  sbb     r9d, r9d
0x18002b91a  not     r9d
0x18002b91d  and     r9d, 80070057h; char *
0x18002b924  test    rcx, rcx
0x18002b927  jz      loc_18002BE32
0x18002b92d  mov     rcx, [rbp+108h]; this
0x18002b934  test    r9d, r9d
0x18002b937  js      loc_18002BD67
0x18002b93d  mov     edx, r8d; cbInit
0x18002b940  mov     rcx, r10; pInit
0x18002b943  call    cs:__imp_SHCreateMemStream
0x18002b949  mov     r14, rax
0x18002b94c  mov     [rbp+100h+var_120], rax
0x18002b950  mov     edx, cs:_tls_index
0x18002b956  mov     rcx, gs:58h
0x18002b95f  mov     eax, 4
0x18002b964  mov     rcx, [rcx+rdx*8]
0x18002b968  mov     esi, 4
0x18002b96d  mov     ecx, [rax+rcx]
0x18002b970  cmp     cs:dword_18015E510, ecx
0x18002b976  jg      loc_18002BE3A
0x18002b97c  mov     eax, [rsp+200h+var_1A0]
0x18002b980  mov     [rbp+100h+var_110], eax
0x18002b983  xor     eax, eax
0x18002b985  mov     [rbp+100h+var_10C], eax
0x18002b988  mov     [rbp+100h+var_108], r12
0x18002b98c  lea     r8, [rbp+100h+var_170]
0x18002b990  lea     rdx, [rbp+100h+var_60]
0x18002b997  lea     rcx, qword_18015E520
0x18002b99e  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18002b9a3  mov     rcx, [rax]
0x18002b9a6  add     rcx, 18h
0x18002b9aa  cmp     qword ptr [rcx+18h], 7
0x18002b9af  jbe     short loc_18002B9B4
0x18002b9b1  mov     rcx, [rcx]
0x18002b9b4  mov     [rbp+100h+var_100], rcx
0x18002b9b8  lea     rax, aXml; "Xml"
0x18002b9bf  mov     [rbp+100h+var_F8], rax
0x18002b9c3  mov     [rbp+100h+var_F0], r14
0x18002b9c7  mov     rax, [rbp+100h+var_160]
0x18002b9cb  mov     [rbp+100h+var_E8], rax
0x18002b9cf  mov     rax, qword ptr [rbp+100h+var_168]
0x18002b9d3  mov     [rbp+100h+var_E0], rax
0x18002b9d7  mov     [rbp+100h+var_D8], edi
0x18002b9da  mov     [rbp+100h+var_D4], ebx
0x18002b9dd  mov     rax, qword ptr [rbp+100h+SystemTimeAsFileTime.dwLowDateTime]
0x18002b9e1  mov     [rbp+100h+var_D0], rax
0x18002b9e5  mov     [rbp+100h+var_C8], 4
0x18002b9ed  call    ?GetLastBootTime@@YA_JXZ; GetLastBootTime(void)
0x18002b9f2  mov     [rbp+100h+var_C0], rax
0x18002b9f6  xor     r12d, r12d
0x18002b9f9  mov     [rbp+100h+var_B8], r12b
0x18002b9fd  xor     eax, eax
0x18002b9ff  mov     [rbp+100h+var_B7], eax
0x18002ba02  mov     [rbp+100h+var_B3], ax
0x18002ba06  mov     [rbp+100h+var_B1], al
0x18002ba09  mov     [rbp+100h+var_B0], rax
0x18002ba0d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002ba14  movdqu  [rbp+100h+var_A8], xmm0
0x18002ba19  mov     [rbp+100h+var_98], 1
0x18002ba21  mov     [rbp+100h+var_90], r12
0x18002ba25  mov     [rbp+100h+var_178], r12
0x18002ba29  lea     rcx, [rbp+100h+var_178]
0x18002ba2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ba32  lea     rdx, [rbp+100h+var_110]
0x18002ba36  lea     rcx, [rbp+100h+var_178]
0x18002ba3a  call    ??$MakeAndInitialize@VNotification@@V1@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJPEAPEAVNotification@@AEAUInitializer@3@@Z; Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(Notification * *,Notification::Initializer &)
0x18002ba3f  mov     rcx, [rbp+108h]; this
0x18002ba46  test    eax, eax
0x18002ba48  js      loc_18002BD79
0x18002ba4e  xorps   xmm0, xmm0
0x18002ba51  movups  xmmword ptr [rbp+100h+pguid.Data1], xmm0
0x18002ba58  lea     rcx, [rbp+100h+pguid]; pguid
0x18002ba5f  call    cs:__imp_CoCreateGuid
0x18002ba65  mov     rcx, [rbp+108h]; this
0x18002ba6c  test    eax, eax
0x18002ba6e  js      loc_18002BD8E
0x18002ba74  xorps   xmm0, xmm0
0x18002ba77  movups  [rbp+100h+var_60], xmm0
0x18002ba7e  mov     [rsp+200h+var_198], r12
0x18002ba83  mov     [rbp+100h+var_130], r12
0x18002ba87  mov     [rbp+100h+var_128], r12
0x18002ba8b  mov     [rsp+200h+var_1B0], r12d
0x18002ba90  mov     [rbp+100h+var_168], r12d
0x18002ba94  mov     dword ptr [rbp+100h+var_160], r12d
0x18002ba98  mov     [rbp+100h+var_140], r12
0x18002ba9c  mov     dword ptr [rsp+200h+var_1A8], r12d
0x18002baa1  lea     rcx, [rsp+200h+var_198]
0x18002baa6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002baab  lea     rax, [rbp+100h+var_130]
0x18002baaf  mov     [rsp+200h+var_1B8], rax
0x18002bab4  lea     rax, [rbp+100h+var_128]
0x18002bab8  mov     [rsp+200h+var_1C0], rax
0x18002babd  lea     rax, [rsp+200h+var_1B0]
0x18002bac2  mov     [rsp+200h+var_1C8], rax
0x18002bac7  lea     rax, [rbp+100h+pguid]
0x18002bace  mov     [rsp+200h+var_1D0], rax
0x18002bad3  lea     rax, [rbp+100h+var_60]
0x18002bada  mov     [rsp+200h+var_1D8], rax
0x18002badf  lea     rax, [rbp+100h+var_168]
0x18002bae3  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x18002bae8  lea     r9, [rbp+100h+var_160]
0x18002baec  lea     r8, [rbp+100h+var_140]
0x18002baf0  lea     rdx, [rsp+200h+var_1A8]
0x18002baf5  lea     rcx, [rsp+200h+var_198]
0x18002bafa  call    ??$MakeAndInitialize@VTransientNotificationDetails@@V1@H$$THHAEAU_GUID@@AEAU2@W4WpnToastNotificationPriority@@$$T$$T@Details@WRL@Microsoft@@YAJPEAPEAVTransientNotificationDetails@@$$QEAH$$QEA$$T11AEAU_GUID@@3$$QEAW4WpnToastNotificationPriority@@22@Z
0x18002baff  mov     rcx, [rbp+108h]; this
0x18002bb06  test    eax, eax
0x18002bb08  js      loc_18002BDA3
0x18002bb0e  mov     rcx, [rsp+200h+var_198]
0x18002bb13  add     rcx, 20h ; ' '
0x18002bb17  mov     rax, [rcx]
0x18002bb1a  mov     rdx, r13
0x18002bb1d  mov     rax, [rax+58h]
0x18002bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb26  mov     rcx, [rbp+108h]; this
0x18002bb2d  test    eax, eax
0x18002bb2f  js      loc_18002BDB8
0x18002bb35  mov     edi, r12d
0x18002bb38  mov     [rsp+200h+var_1A8], r12
0x18002bb3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002bb44  lea     ecx, [r12+18h]; unsigned __int64
0x18002bb49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002bb4e  test    rax, rax
0x18002bb51  jnz     loc_18002BF25
0x18002bb57  mov     [rbp+100h+var_140], rdi
0x18002bb5b  mov     rcx, [rbp+108h]; this
0x18002bb62  test    rdi, rdi
0x18002bb65  jz      loc_18002BF44
0x18002bb6b  mov     [rbp+100h+var_180], r12
0x18002bb6f  mov     rax, [rdi]
0x18002bb72  mov     rbx, [rax+18h]
0x18002bb76  lea     rcx, [rbp+100h+var_180]
0x18002bb7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bb7f  lea     r9, [rbp+100h+var_180]
0x18002bb83  lea     r8, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18002bb8a  xor     edx, edx
0x18002bb8c  mov     rcx, rdi
0x18002bb8f  mov     rax, rbx
0x18002bb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb97  mov     rcx, [rbp+108h]; this
0x18002bb9e  test    eax, eax
0x18002bba0  js      loc_18002BDCD
0x18002bba6  mov     [rsp+200h+var_188], r12
0x18002bbab  mov     rsi, [rbp+100h+var_180]
0x18002bbaf  mov     rax, [rsi]
0x18002bbb2  mov     rbx, [rax+18h]
0x18002bbb6  lea     rcx, [rsp+200h+var_188]
0x18002bbbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bbc0  lea     rdx, [rsp+200h+var_188]
0x18002bbc5  mov     rcx, rsi
0x18002bbc8  mov     rax, rbx
0x18002bbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbd0  mov     rcx, [rbp+108h]; this
0x18002bbd7  test    eax, eax
0x18002bbd9  js      loc_18002BDE2
0x18002bbdf  mov     [rsp+200h+var_190], r12
0x18002bbe4  mov     rbx, [rsp+200h+var_188]
0x18002bbe9  mov     rax, [rbx]
0x18002bbec  mov     rsi, [rax]
0x18002bbef  lea     rcx, [rsp+200h+var_190]
0x18002bbf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bbf9  lea     r8, [rsp+200h+var_190]
0x18002bbfe  lea     rdx, _GUID_926516e8_d891_45bc_9de5_6959fb8ecac5
0x18002bc05  mov     rcx, rbx
0x18002bc08  mov     rax, rsi
0x18002bc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc10  nop
0x18002bc11  mov     rcx, [rbp+108h]; this
0x18002bc18  test    eax, eax
0x18002bc1a  js      loc_18002BDF7
0x18002bc20  mov     r11, [rsp+200h+var_190]
0x18002bc25  mov     rcx, [rsp+200h+var_198]
0x18002bc2a  mov     rdx, [rbp+100h+var_178]
0x18002bc2e  mov     r10, [r11]
0x18002bc31  lea     rax, [rcx+20h]
0x18002bc35  neg     rcx
0x18002bc38  sbb     r8, r8
0x18002bc3b  and     r8, rax
0x18002bc3e  lea     rax, [rdx+20h]
0x18002bc42  neg     rdx
0x18002bc45  sbb     rdx, rdx
0x18002bc48  and     rdx, rax
0x18002bc4b  lea     rax, [rsp+200h+var_1A0]
0x18002bc50  mov     [rsp+200h+var_1D8], rax
0x18002bc55  mov     qword ptr [rsp+200h+var_1E0], r12; int
0x18002bc5a  mov     r9d, 4
0x18002bc60  mov     rcx, r11
0x18002bc63  mov     rax, [r10+148h]
0x18002bc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc6f  mov     rcx, [rbp+108h]; this
0x18002bc76  test    eax, eax
0x18002bc78  js      loc_18002BE0C
0x18002bc7e  mov     eax, [rsp+200h+var_1A0]
0x18002bc82  mov     [r15], eax
0x18002bc85  mov     rcx, [rsp+200h+var_190]
0x18002bc8a  test    rcx, rcx
0x18002bc8d  jz      short loc_18002BCA1
0x18002bc8f  mov     [rsp+200h+var_190], r12
0x18002bc94  mov     rax, [rcx]
0x18002bc97  mov     rax, [rax+10h]
0x18002bc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bca0  nop
0x18002bca1  mov     rcx, [rsp+200h+var_188]
0x18002bca6  test    rcx, rcx
0x18002bca9  jz      short loc_18002BCBD
0x18002bcab  mov     [rsp+200h+var_188], r12
0x18002bcb0  mov     rax, [rcx]
0x18002bcb3  mov     rax, [rax+10h]
0x18002bcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcbc  nop
0x18002bcbd  mov     rcx, [rbp+100h+var_180]
0x18002bcc1  test    rcx, rcx
0x18002bcc4  jz      short loc_18002BCD7
0x18002bcc6  mov     [rbp+100h+var_180], r12
0x18002bcca  mov     rax, [rcx]
0x18002bccd  mov     rax, [rax+10h]
0x18002bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcd6  nop
0x18002bcd7  mov     rax, [rdi]
0x18002bcda  mov     rcx, rdi
0x18002bcdd  mov     rax, [rax+10h]
0x18002bce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bce6  nop
0x18002bce7  mov     rcx, [rsp+200h+var_198]
0x18002bcec  test    rcx, rcx
0x18002bcef  jz      short loc_18002BD03
0x18002bcf1  mov     [rsp+200h+var_198], r12
0x18002bcf6  mov     rax, [rcx]
0x18002bcf9  mov     rax, [rax+10h]
0x18002bcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd02  nop
0x18002bd03  mov     rcx, [rbp+100h+var_178]
0x18002bd07  test    rcx, rcx
0x18002bd0a  jz      short loc_18002BD1D
0x18002bd0c  mov     [rbp+100h+var_178], r12
0x18002bd10  mov     rax, [rcx]
0x18002bd13  mov     rax, [rax+10h]
0x18002bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd1c  nop
0x18002bd1d  test    r14, r14
0x18002bd20  jz      short loc_18002BD32
  ... truncated ...
```
