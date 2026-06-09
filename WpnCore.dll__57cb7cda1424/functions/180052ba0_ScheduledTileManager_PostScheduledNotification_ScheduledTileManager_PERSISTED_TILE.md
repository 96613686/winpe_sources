# ScheduledTileManager::PostScheduledNotification(ScheduledTileManager::_PERSISTED_TILE *)

- ea: `0x180052ba0`
- end: `0x1800532a1`
- name: `?PostScheduledNotification@ScheduledTileManager@@AEAAJPEAU_PERSISTED_TILE@1@@Z`
- size: `1793`
- prototype: `__int64 __fastcall(ScheduledTileManager *__hidden this, struct ScheduledTileManager::_PERSISTED_TILE *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008ef00`

## callees

- `0x180004e38`
- `0x18000c1cc`
- `0x18000e5f4`
- `0x180011618`
- `0x180018d24`
- `0x18001a40c`
- `0x18002ab88`
- `0x18002bfbc`
- `0x18002d6f0`
- `0x180052ba0`
- `0x1800533e4`
- `0x1800967bc`
- `0x18009cf0c`
- `0x1800b99f0`
- `0x1800ba0d0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180052cde`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180052cde`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180052e16`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180052e16`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180052ca8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180052ca8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180052d04`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180052d04`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180052e73`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180052e73`

## string_xrefs

- `0x180052c2e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052c53`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052cb2`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052d0e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052d94`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052df2`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052e5e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180052f94`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180053064`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18005309d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180053147`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180053176`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall ScheduledTileManager::PostScheduledNotification(
        NotificationPlatform **this,
        struct ScheduledTileManager::_PERSISTED_TILE *a2)
{
  char *v4; // r15
  __int64 v5; // rdx
  _WORD *v6; // rcx
  int v7; // esi
  __int64 v8; // r9
  unsigned __int64 v9; // rax
  const char *v10; // r9
  const char *v11; // r9
  NotificationPlatform *v12; // rbx
  int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, char *, __int64 *); // rbx
  int v16; // r12d
  int v17; // eax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  UINT v20; // edx
  IStream *v21; // rdi
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rsi
  __int64 v27; // r14
  __int64 v28; // rbx
  int v29; // eax
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v37; // [rsp+20h] [rbp-188h]
  int v38; // [rsp+20h] [rbp-188h]
  int v39; // [rsp+20h] [rbp-188h]
  __int64 v40; // [rsp+50h] [rbp-158h] BYREF
  __int64 v41; // [rsp+58h] [rbp-150h] BYREF
  __int64 v42; // [rsp+60h] [rbp-148h] BYREF
  unsigned int NotificationTrackingId; // [rsp+68h] [rbp-140h]
  FILETIME FileTime; // [rsp+70h] [rbp-138h] BYREF
  __int64 v45; // [rsp+78h] [rbp-130h] BYREF
  __int64 v46; // [rsp+80h] [rbp-128h] BYREF
  void *v47; // [rsp+88h] [rbp-120h] BYREF
  int v48; // [rsp+90h] [rbp-118h] BYREF
  int v49; // [rsp+94h] [rbp-114h] BYREF
  int v50; // [rsp+98h] [rbp-110h] BYREF
  struct _FILETIME v51; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-100h] BYREF
  _QWORD v53[2]; // [rsp+B0h] [rbp-F8h] BYREF
  _DWORD v54[2]; // [rsp+C0h] [rbp-E8h] BYREF
  char *v55; // [rsp+C8h] [rbp-E0h]
  const wchar_t *v56; // [rsp+D0h] [rbp-D8h]
  const wchar_t *v57; // [rsp+D8h] [rbp-D0h]
  IStream *v58; // [rsp+E0h] [rbp-C8h]
  char *v59; // [rsp+E8h] [rbp-C0h]
  __int64 v60; // [rsp+F0h] [rbp-B8h]
  FILETIME v61; // [rsp+F8h] [rbp-B0h]
  struct _FILETIME v62; // [rsp+100h] [rbp-A8h]
  __int64 v63; // [rsp+108h] [rbp-A0h]
  __int64 LastBootTime; // [rsp+110h] [rbp-98h]
  char v65; // [rsp+118h] [rbp-90h]
  int v66; // [rsp+119h] [rbp-8Fh]
  __int16 v67; // [rsp+11Dh] [rbp-8Bh]
  char v68; // [rsp+11Fh] [rbp-89h]
  __int64 v69; // [rsp+120h] [rbp-88h]
  GUID v70; // [rsp+128h] [rbp-80h]
  __int64 v71; // [rsp+138h] [rbp-70h]
  __int64 v72; // [rsp+140h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+150h] [rbp-58h] BYREF
  GUID pguid; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v4 = (char *)a2 + 5774;
  if ( a2 == (struct ScheduledTileManager::_PERSISTED_TILE *)-5774LL )
  {
    v7 = -2147024809;
    v8 = 2147942487LL;
LABEL_10:
    v9 = 0;
    goto LABEL_11;
  }
  v5 = 65;
  v6 = v4;
  while ( *v6 )
  {
    ++v6;
    if ( !--v5 )
    {
      v7 = -2147024809;
      v8 = 2147942487LL;
      v9 = 0;
      goto LABEL_7;
    }
  }
  v8 = 0;
  v9 = 65 - v5;
  v7 = -2147024809;
LABEL_7:
  if ( (int)v8 < 0 )
    goto LABEL_10;
LABEL_11:
  if ( (int)v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)v8,
      v37);
  if ( v9 > 0x40 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x803E0116LL,
      v37);
  FileTime = 0;
  SystemTime = 0;
  if ( *((_DWORD *)a2 + 152) )
  {
    FileTime = *(FILETIME *)((char *)a2 + 612);
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        v10);
  }
  NotificationTrackingId = NotificationPlatform::GetNotificationTrackingId(this[16]);
  GetSystemTime(&SystemTime);
  v51 = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &v51) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      v11);
  v42 = 0;
  v12 = this[16];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  v13 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v12 + 18))(
          *((_QWORD *)v12 + 18),
          &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
          &v42);
  if ( v13 >= 0 && !v42 )
  {
    v13 = -2143420155;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      v37);
  }
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v13,
      v37);
  v46 = 0;
  v14 = v42;
  v15 = *(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v42 + 192LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  v16 = (_DWORD)a2 + 84;
  v17 = v15(v14, (char *)a2 + 84, &v46);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v17,
      v37);
  pguid = 0;
  CoCreateGuid(&pguid);
  if ( a2 == (struct ScheduledTileManager::_PERSISTED_TILE *)-654LL )
    goto LABEL_34;
  v18 = 5120;
  v19 = (char *)a2 + 654;
  while ( *v19 )
  {
    ++v19;
    if ( !--v18 )
    {
      v20 = 0;
      goto LABEL_33;
    }
  }
  v7 = 0;
  v20 = 5120 - v18;
LABEL_33:
  if ( v7 < 0 )
LABEL_34:
    v20 = 0;
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v7,
      v37);
  v21 = SHCreateMemStream((const BYTE *)a2 + 654, v20);
  v53[1] = v21;
  v54[0] = NotificationTrackingId;
  v54[1] = 0;
  v55 = (char *)a2 + 84;
  v56 = L"tile";
  v57 = L"Xml";
  v58 = v21;
  v59 = v4;
  v60 = 0;
  v61 = FileTime;
  v62 = v51;
  v63 = 3;
  LastBootTime = GetLastBootTime();
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = GUID_NULL;
  v71 = 1;
  v72 = 0;
  v45 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  v22 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(&v45, v54);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v22,
      v37);
  v41 = 0;
  v52 = 0;
  v53[0] = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  LODWORD(v40) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  v23 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,unsigned long &,unsigned short * &,int &,int &,_GUID &,_GUID &,enum WpnToastNotificationPriority,std::nullptr_t,std::nullptr_t>(
          (unsigned int)&v41,
          (unsigned int)&v40,
          (unsigned int)&v47,
          (unsigned int)&v50,
          (__int64)&v49,
          (__int64)&GUID_NULL,
          (__int64)&pguid,
          (__int64)&v48,
          (__int64)v53,
          (__int64)&v52);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v23,
      v38);
  v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)(v41 + 32) + 88LL))(v41 + 32, (char *)a2 + 4);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x218,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v24,
      v38);
  v25 = v41;
  v26 = v45;
  v27 = v46;
  v47 = operator new(0x78u);
  LOBYTE(v38) = 0;
  v40 = NotificationDeliveryTransaction::NotificationDeliveryTransaction(v47, v27, v26, v25, v38, 0, 0);
  v47 = operator new(0xC8u);
  v28 = NotificationAvailableWork::NotificationAvailableWork(v47, &v40, this[16]);
  v47 = (void *)v28;
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v29,
      v39);
  v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  v31 = retaddr;
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v30,
      v39);
  if ( (byte_18015DE45 & 0x10) != 0 )
    McTemplateU0zzqq_EventWriteTransfer(
      (_DWORD)retaddr,
      (unsigned int)WPNEND_LOCAL_NOTIFICATION,
      v16,
      (unsigned int)L"tile",
      NotificationTrackingId,
      2);
  if ( v28 )
    (**(void (__fastcall ***)(__int64, __int64))v28)(v28, 1);
  if ( v40 )
    std::default_delete<NotificationDeliveryTransaction>::operator()(v31);
  v32 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  if ( v21 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v21 + 16LL))(v21);
  v34 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return 0;
}

```

## disassembly

```asm
0x180052ba0  mov     [rsp+arg_10], rbx
0x180052ba5  mov     [rsp+arg_18], rsi
0x180052baa  push    rdi
0x180052bab  push    r12
0x180052bad  push    r13
0x180052baf  push    r14
0x180052bb1  push    r15
0x180052bb3  sub     rsp, 180h
0x180052bba  mov     rax, cs:__security_cookie
0x180052bc1  xor     rax, rsp
0x180052bc4  mov     [rsp+1A8h+var_38], rax
0x180052bcc  mov     r14, rdx
0x180052bcf  mov     r13, rcx
0x180052bd2  xor     edi, edi
0x180052bd4  lea     r15, [rdx+168Eh]
0x180052bdb  test    r15, r15
0x180052bde  jz      short loc_180052C16
0x180052be0  lea     eax, [rdi+41h]
0x180052be3  mov     edx, eax
0x180052be5  mov     rcx, r15
0x180052be8  cmp     [rcx], di
0x180052beb  jz      short loc_180052C04
0x180052bed  add     rcx, 2
0x180052bf1  sub     rdx, 1
0x180052bf5  jnz     short loc_180052BE8
0x180052bf7  mov     esi, 80070057h
0x180052bfc  mov     r9d, esi
0x180052bff  mov     rax, rdi
0x180052c02  jmp     short loc_180052C0F
0x180052c04  mov     r9d, edi
0x180052c07  sub     rax, rdx
0x180052c0a  mov     esi, 80070057h
0x180052c0f  test    r9d, r9d
0x180052c12  js      short loc_180052C1E
0x180052c14  jmp     short loc_180052C21
0x180052c16  mov     esi, 80070057h
0x180052c1b  mov     r9d, esi; char *
0x180052c1e  mov     rax, rdi
0x180052c21  mov     rcx, [rsp+1A8h]; this
0x180052c29  test    r9d, r9d
0x180052c2c  jns     short loc_180052C3F
0x180052c2e  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052c35  mov     edx, 1D7h; void *
0x180052c3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052c3f  mov     rcx, [rsp+1A8h]; this
0x180052c47  cmp     rax, 40h ; '@'
0x180052c4b  jbe     short loc_180052C64
0x180052c4d  mov     r9d, 803E0116h; char *
0x180052c53  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052c5a  mov     edx, 1D9h; void *
0x180052c5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052c64  mov     qword ptr [rsp+1A8h+FileTime.dwLowDateTime], rdi
0x180052c69  xorps   xmm0, xmm0
0x180052c6c  movups  xmmword ptr [rsp+1A8h+SystemTime.wYear], xmm0
0x180052c74  cmp     [r14+260h], edi
0x180052c7b  jz      short loc_180052CC6
0x180052c7d  mov     eax, [r14+264h]
0x180052c84  mov     [rsp+1A8h+FileTime.dwLowDateTime], eax
0x180052c88  mov     eax, [r14+268h]
0x180052c8f  mov     [rsp+1A8h+FileTime.dwHighDateTime], eax
0x180052c93  mov     rbx, [rsp+1A8h]
0x180052c9b  lea     rdx, [rsp+1A8h+SystemTime]; lpSystemTime
0x180052ca3  lea     rcx, [rsp+1A8h+FileTime]; lpFileTime
0x180052ca8  call    cs:__imp_FileTimeToSystemTime
0x180052cae  test    eax, eax
0x180052cb0  jnz     short loc_180052CC6
0x180052cb2  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052cb9  mov     edx, 1E3h; void *
0x180052cbe  mov     rcx, rbx; this
0x180052cc1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180052cc6  mov     rcx, [r13+80h]; this
0x180052ccd  call    ?GetNotificationTrackingId@NotificationPlatform@@QEAAKXZ; NotificationPlatform::GetNotificationTrackingId(void)
0x180052cd2  mov     [rsp+1A8h+var_140], eax
0x180052cd6  lea     rcx, [rsp+1A8h+SystemTime]; lpSystemTime
0x180052cde  call    cs:__imp_GetSystemTime
0x180052ce4  mov     qword ptr [rsp+1A8h+var_108.dwLowDateTime], rdi
0x180052cec  mov     rbx, [rsp+1A8h]
0x180052cf4  lea     rdx, [rsp+1A8h+var_108]; lpFileTime
0x180052cfc  lea     rcx, [rsp+1A8h+SystemTime]; lpSystemTime
0x180052d04  call    cs:__imp_SystemTimeToFileTime
0x180052d0a  test    eax, eax
0x180052d0c  jnz     short loc_180052D22
0x180052d0e  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052d15  mov     edx, 1E9h; void *
0x180052d1a  mov     rcx, rbx; this
0x180052d1d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180052d22  mov     [rsp+1A8h+var_148], rdi
0x180052d27  mov     rbx, [r13+80h]
0x180052d2e  lea     rcx, [rsp+1A8h+var_148]
0x180052d33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052d38  nop
0x180052d39  mov     rcx, [rbx+90h]
0x180052d40  mov     rax, [rcx]
0x180052d43  lea     r8, [rsp+1A8h+var_148]
0x180052d48  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x180052d4f  mov     rax, [rax]
0x180052d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d57  mov     ebx, eax
0x180052d59  test    eax, eax
0x180052d5b  js      short loc_180052D85
0x180052d5d  cmp     [rsp+1A8h+var_148], rdi
0x180052d62  jnz     short loc_180052D85
0x180052d64  mov     rcx, [rsp+1A8h]; this
0x180052d6c  mov     ebx, 803E0105h
0x180052d71  mov     r9d, ebx; char *
0x180052d74  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052d7b  mov     edx, 400h; void *
0x180052d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d85  mov     rcx, [rsp+1A8h]; this
0x180052d8d  test    ebx, ebx
0x180052d8f  jns     short loc_180052DA5
0x180052d91  mov     r9d, ebx; char *
0x180052d94  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052d9b  mov     edx, 1ECh; void *
0x180052da0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052da5  mov     [rsp+1A8h+var_128], rdi
0x180052dad  mov     rdi, [rsp+1A8h+var_148]
0x180052db2  mov     rax, [rdi]
0x180052db5  mov     rbx, [rax+0C0h]
0x180052dbc  lea     rcx, [rsp+1A8h+var_128]
0x180052dc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052dc9  lea     r12, [r14+54h]
0x180052dcd  lea     r8, [rsp+1A8h+var_128]
0x180052dd5  mov     rdx, r12
0x180052dd8  mov     rcx, rdi
0x180052ddb  mov     rax, rbx
0x180052dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052de3  mov     rcx, [rsp+1A8h]; this
0x180052deb  test    eax, eax
0x180052ded  jns     short loc_180052E03
0x180052def  mov     r9d, eax; char *
0x180052df2  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052df9  mov     edx, 1EFh; void *
0x180052dfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052e03  xorps   xmm0, xmm0
0x180052e06  movups  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x180052e0e  lea     rcx, [rsp+1A8h+pguid]; pguid
0x180052e16  call    cs:__imp_CoCreateGuid
0x180052e1c  lea     r8, [r14+28Eh]
0x180052e23  test    r8, r8
0x180052e26  jz      short loc_180052E4D
0x180052e28  mov     edx, 1400h
0x180052e2d  mov     ecx, edx
0x180052e2f  mov     rax, r8
0x180052e32  cmp     byte ptr [rax], 0
0x180052e35  jz      short loc_180052E44
0x180052e37  inc     rax
0x180052e3a  sub     rcx, 1
0x180052e3e  jnz     short loc_180052E32
0x180052e40  xor     edx, edx
0x180052e42  jmp     short loc_180052E49
0x180052e44  xor     esi, esi
0x180052e46  sub     rdx, rcx
0x180052e49  test    esi, esi
0x180052e4b  jns     short loc_180052E4F
0x180052e4d  xor     edx, edx; cbInit
0x180052e4f  mov     rcx, [rsp+1A8h]; this
0x180052e57  test    esi, esi
0x180052e59  jns     short loc_180052E70
0x180052e5b  mov     r9d, esi; char *
0x180052e5e  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052e65  mov     edx, 1F4h; void *
0x180052e6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052e70  mov     rcx, r8; pInit
0x180052e73  call    cs:__imp_SHCreateMemStream
0x180052e79  mov     rdi, rax
0x180052e7c  mov     [rsp+1A8h+var_F0], rax
0x180052e84  mov     eax, [rsp+1A8h+var_140]
0x180052e88  mov     [rsp+1A8h+var_E8], eax
0x180052e8f  xor     eax, eax
0x180052e91  mov     [rsp+1A8h+var_E4], eax
0x180052e98  mov     [rsp+1A8h+var_E0], r12
0x180052ea0  lea     rax, aTile; "tile"
0x180052ea7  mov     [rsp+1A8h+var_D8], rax
0x180052eaf  lea     rax, aXml; "Xml"
0x180052eb6  mov     [rsp+1A8h+var_D0], rax
0x180052ebe  mov     [rsp+1A8h+var_C8], rdi
0x180052ec6  mov     [rsp+1A8h+var_C0], r15
0x180052ece  xor     r15d, r15d
0x180052ed1  mov     [rsp+1A8h+var_B8], r15
0x180052ed9  mov     eax, [rsp+1A8h+FileTime.dwLowDateTime]
0x180052edd  mov     [rsp+1A8h+var_B0], eax
0x180052ee4  mov     eax, [rsp+1A8h+FileTime.dwHighDateTime]
0x180052ee8  mov     [rsp+1A8h+var_AC], eax
0x180052eef  mov     rax, qword ptr [rsp+1A8h+var_108.dwLowDateTime]
0x180052ef7  mov     [rsp+1A8h+var_A8], rax
0x180052eff  mov     [rsp+1A8h+var_A0], 3
0x180052f0b  call    ?GetLastBootTime@@YA_JXZ; GetLastBootTime(void)
0x180052f10  mov     [rsp+1A8h+var_98], rax
0x180052f18  mov     [rsp+1A8h+var_90], r15b
0x180052f20  xor     eax, eax
0x180052f22  mov     [rsp+1A8h+var_8F], eax
0x180052f29  mov     [rsp+1A8h+var_8B], ax
0x180052f31  mov     [rsp+1A8h+var_89], al
0x180052f38  mov     [rsp+1A8h+var_88], rax
0x180052f40  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180052f47  movdqu  [rsp+1A8h+var_80], xmm0
0x180052f50  mov     [rsp+1A8h+var_70], 1
0x180052f5c  mov     [rsp+1A8h+var_68], r15
0x180052f64  mov     [rsp+1A8h+var_130], r15
0x180052f69  lea     rcx, [rsp+1A8h+var_130]
0x180052f6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052f73  lea     rdx, [rsp+1A8h+var_E8]
0x180052f7b  lea     rcx, [rsp+1A8h+var_130]
0x180052f80  call    ??$MakeAndInitialize@VNotification@@V1@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJPEAPEAVNotification@@AEAUInitializer@3@@Z; Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(Notification * *,Notification::Initializer &)
0x180052f85  mov     rcx, [rsp+1A8h]; this
0x180052f8d  test    eax, eax
0x180052f8f  jns     short loc_180052FA5
0x180052f91  mov     r9d, eax; char *
0x180052f94  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180052f9b  mov     edx, 209h; void *
0x180052fa0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052fa5  mov     [rsp+1A8h+var_150], r15
0x180052faa  mov     [rsp+1A8h+var_100], r15
0x180052fb2  mov     [rsp+1A8h+var_F8], r15
0x180052fba  mov     [rsp+1A8h+var_118], r15d
0x180052fc2  mov     [rsp+1A8h+var_114], r15d
0x180052fca  mov     [rsp+1A8h+var_110], r15d
0x180052fd2  mov     [rsp+1A8h+var_120], r15
0x180052fda  mov     dword ptr [rsp+1A8h+var_158], r15d
0x180052fdf  lea     rcx, [rsp+1A8h+var_150]
0x180052fe4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052fe9  lea     rax, [rsp+1A8h+var_100]
0x180052ff1  mov     [rsp+1A8h+var_160], rax
0x180052ff6  lea     rax, [rsp+1A8h+var_F8]
0x180052ffe  mov     [rsp+1A8h+var_168], rax
0x180053003  lea     rax, [rsp+1A8h+var_118]
0x18005300b  mov     [rsp+1A8h+var_170], rax
0x180053010  lea     rax, [rsp+1A8h+pguid]
0x180053018  mov     [rsp+1A8h+var_178], rax
0x18005301d  lea     rax, GUID_NULL
0x180053024  mov     [rsp+1A8h+var_180], rax
0x180053029  lea     rax, [rsp+1A8h+var_114]
0x180053031  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x180053036  lea     r9, [rsp+1A8h+var_110]
0x18005303e  lea     r8, [rsp+1A8h+var_120]
0x180053046  lea     rdx, [rsp+1A8h+var_158]
0x18005304b  lea     rcx, [rsp+1A8h+var_150]
0x180053050  call    ??$MakeAndInitialize@VTransientNotificationDetails@@V1@AEAKAEAPEAGAEAHAEAHAEAU_GUID@@AEAU2@W4WpnToastNotificationPriority@@$$T$$T@Details@WRL@Microsoft@@YAJPEAPEAVTransientNotificationDetails@@AEAKAEAPEAGAEAH3AEAU_GUID@@4$$QEAW4WpnToastNotificationPriority@@$$QEA$$T6@Z
0x180053055  mov     rcx, [rsp+1A8h]; this
0x18005305d  test    eax, eax
0x18005305f  jns     short loc_180053075
0x180053061  mov     r9d, eax; char *
0x180053064  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005306b  mov     edx, 216h; void *
0x180053070  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053075  mov     rcx, [rsp+1A8h+var_150]
0x18005307a  add     rcx, 20h ; ' '
0x18005307e  mov     rax, [rcx]
0x180053081  lea     rdx, [r14+4]
0x180053085  mov     rax, [rax+58h]
0x180053089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005308e  mov     rcx, [rsp+1A8h]; this
0x180053096  test    eax, eax
0x180053098  jns     short loc_1800530AE
0x18005309a  mov     r9d, eax; char *
0x18005309d  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800530a4  mov     edx, 218h; void *
0x1800530a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800530ae  mov     rbx, [rsp+1A8h+var_150]
0x1800530b3  mov     rsi, [rsp+1A8h+var_130]
0x1800530b8  mov     r14, [rsp+1A8h+var_128]
0x1800530c0  mov     ecx, 78h ; 'x'; Size
0x1800530c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800530ca  mov     [rsp+1A8h+var_120], rax
0x1800530d2  mov     [rsp+1A8h+var_178], r15
0x1800530d7  mov     dword ptr [rsp+1A8h+var_180], r15d
0x1800530dc  mov     byte ptr [rsp+1A8h+var_188], r15b; int
0x1800530e1  mov     r9, rbx
0x1800530e4  mov     r8, rsi
0x1800530e7  mov     rdx, r14
0x1800530ea  mov     rcx, rax
0x1800530ed  call    ??0NotificationDeliveryTransaction@@QEAA@PEAUINotificationHandler@@PEAVNotification@@PEAVTransientNotificationDetails@@_NW4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@PEBG@Z; NotificationDeliveryTransaction::NotificationDeliveryTransaction(INotificationHandler *,Notification *,TransientNotificationDetails *,bool,__MIDL___MIDL_itf_wpntypes_0000_0000_0007,ushort const *)
0x1800530f2  nop
0x1800530f3  mov     [rsp+1A8h+var_158], rax
0x1800530f8  mov     ecx, 0C8h; Size
0x1800530fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053102  mov     [rsp+1A8h+var_120], rax
0x18005310a  mov     r8, [r13+80h]
0x180053111  lea     rdx, [rsp+1A8h+var_158]
0x180053116  mov     rcx, rax
0x180053119  call    ??0NotificationAvailableWork@@QEAA@AEAV?$unique_ptr@VNotificationDeliveryTransaction@@U?$default_delete@VNotificationDeliveryTransaction@@@std@@@std@@PEAVNotificationPlatform@@@Z; NotificationAvailableWork::NotificationAvailableWork(std::unique_ptr<NotificationDeliveryTransaction> &,NotificationPlatform *)
0x18005311e  mov     rbx, rax
0x180053121  mov     [rsp+1A8h+var_120], rax
0x180053129  mov     rcx, [rax]
0x18005312c  mov     rax, [rcx+10h]
0x180053130  mov     rcx, rbx
0x180053133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053138  mov     rcx, [rsp+1A8h]; this
0x180053140  test    eax, eax
0x180053142  jns     short loc_180053158
0x180053144  mov     r9d, eax; char *
0x180053147  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005314e  mov     edx, 223h; void *
0x180053153  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053158  mov     rax, [rbx]
0x18005315b  mov     rcx, rbx
0x18005315e  mov     rax, [rax+8]
0x180053162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053167  mov     rcx, [rsp+1A8h]; this
  ... truncated ...
```
