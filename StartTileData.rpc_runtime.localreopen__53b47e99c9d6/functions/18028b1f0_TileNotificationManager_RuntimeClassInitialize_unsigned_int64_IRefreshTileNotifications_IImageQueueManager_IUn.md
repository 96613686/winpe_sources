# TileNotificationManager::RuntimeClassInitialize(unsigned __int64,IRefreshTileNotifications *,IImageQueueManager *,IUnknown *,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched *,INotificationPresenter *)

- ea: `0x18028b1f0`
- end: `0x18028b689`
- name: `?RuntimeClassInitialize@TileNotificationManager@@QEAAJ_KPEAUIRefreshTileNotifications@@PEAUIImageQueueManager@@PEAUIUnknown@@PEAUICDSTilePropertiesBatched@CDSProperties@Shell@WindowsInternal@@PEAUINotificationPresenter@@@Z`
- size: `1177`
- prototype: `__int64 __usercall@<rax>(TileNotificationManager *__hidden this@<rcx>, unsigned __int64@<rdx>, struct IRefreshTileNotifications *@<r8>, struct IImageQueueManager *@<r9>, struct IUnknown *, struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched *, struct INotificationPresenter *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18027ee9c`

## callees

- `0x18000ce94`
- `0x180015960`
- `0x18001aca4`
- `0x180021b78`
- `0x180037d34`
- `0x18004a468`
- `0x1800db6b0`
- `0x180192a18`
- `0x1801d8ef4`
- `0x1802771e0`
- `0x18027e37c`
- `0x180289584`
- `0x180289640`
- `0x18028a790`
- `0x18028a8d0`
- `0x18028b1f0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b315`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b417`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b48c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b4b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b52a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b5c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b315`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b417`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b48c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b4b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b52a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b5c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028b640`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18028b2b8`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18028b2b8`

## string_xrefs

- `0x18028b26d`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x18028b356`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x18028b3aa`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x18028b3e3`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x18028b50a`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x18028b58d`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall TileNotificationManager::RuntimeClassInitialize(
        TileNotificationManager *this,
        __int64 a2,
        struct IRefreshTileNotifications *a3,
        struct IImageQueueManager *a4,
        struct IUnknown *a5,
        struct WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched *a6,
        struct INotificationPresenter *a7)
{
  __int64 v10; // rax
  int AgileReference; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, char *); // rdi
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, char *); // rdi
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, char *); // rdi
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  struct INotificationPresenter *v32; // rbx
  int v33; // eax
  int v34; // edi
  struct INotificationPresenter *v35; // rbx
  __int64 v36; // rcx
  __int64 v38; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  char *v40; // [rsp+30h] [rbp-30h] BYREF
  __int64 v41; // [rsp+38h] [rbp-28h] BYREF
  struct INotificationPresenter *v42; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v43[24]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v45; // [rsp+90h] [rbp+30h] BYREF
  __int64 v46; // [rsp+98h] [rbp+38h] BYREF

  *((_QWORD *)this + 17) = a2;
  v41 = 0;
  v40 = (char *)&v41;
  v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v40);
  AgileReference = Microsoft::WRL::AsWeak<IRefreshTileNotifications>(a3, v10);
  v12 = AgileReference;
  if ( AgileReference < 0 )
  {
    v13 = 41;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
      (const char *)(unsigned int)AgileReference,
      v38);
    goto LABEL_43;
  }
  v40 = (char *)this + 224;
  v14 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v40);
  AgileReference = Microsoft::WRL::AsAgile<IWeakReference>(v41, v14);
  v12 = AgileReference;
  if ( AgileReference < 0 )
  {
    v13 = 42;
    goto LABEL_5;
  }
  v40 = (char *)this + 160;
  v15 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v40);
  v16 = v15;
  if ( a4 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v15);
    AgileReference = RoGetAgileReference(0, &GUID_f9e87849_b323_eefa_3204_8a2d2d2b4432, a4, v16);
    v12 = AgileReference;
    if ( AgileReference < 0 )
    {
      v13 = 44;
      goto LABEL_5;
    }
  }
  else
  {
    v42 = 0;
    v40 = (char *)*v15;
    *v15 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  }
  Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=((char *)this + 144, a5);
  Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=((char *)this + 152, a6);
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  AgileReference = TileNotificationManager::GetWNSId(*((struct IUnknown **)this + 18), (HSTRING *)this + 10);
  v12 = AgileReference;
  if ( AgileReference < 0 )
  {
    v13 = 49;
    goto LABEL_5;
  }
  v46 = 0;
  v17 = Microsoft::WRL::ComPtr<IUnknown>::As<WindowsInternal::Shell::UnifiedTile::IUnifiedTile>(
          (char *)this + 144,
          &v46);
  v12 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
      (const char *)(unsigned int)v17,
      v38);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_43;
  }
  v45 = 0;
  v18 = v46;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v20 = v19(v18, &v45);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
      (const char *)(unsigned int)v20,
      v38);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    goto LABEL_14;
  }
  v38 = 0;
  v21 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
          &v45,
          &v38);
  v12 = v21;
  if ( v21 < 0 )
  {
    v22 = 56;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
      (const char *)(unsigned int)v21,
      v38);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    goto LABEL_17;
  }
  v23 = v38;
  v24 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 48LL);
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  v21 = v24(v23, (char *)this + 168);
  v12 = v21;
  if ( v21 < 0 )
  {
    v22 = 58;
    goto LABEL_20;
  }
  v25 = v38;
  v26 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 56LL);
  WindowsDeleteString(*((HSTRING *)this + 22));
  *((_QWORD *)this + 22) = 0;
  v21 = v26(v25, (char *)this + 176);
  v12 = v21;
  if ( v21 < 0 )
  {
    v22 = 59;
    goto LABEL_20;
  }
  v27 = v45;
  v28 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v45 + 56LL);
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  v21 = v28(v27, (char *)this + 184);
  v12 = v21;
  if ( v21 < 0 )
  {
    v22 = 60;
    goto LABEL_20;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( TileNotificationManager::GetPackageFullName(this, &string) < 0 || !string )
  {
    v40 = 0;
    v42 = (struct INotificationPresenter *)&v40;
    v29 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v42);
    v30 = Microsoft::WRL::AsWeak<TileNotificationManager>(this, v29);
    v12 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v30,
        v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_21;
    }
    v31 = lambda_c6f71df60640545799b1cdbef48bba18_::_lambda_c6f71df60640545799b1cdbef48bba18_(v43, this, &v40);
    Microsoft::WRL::Callback_Windows::Foundation::ITypedEventHandler_WindowsInternal::Shell::UnifiedTile::UnifiedTile___WindowsInternal::Shell::UnifiedTile::TileChangedEventArgs_____lambda_01ce00a31d27118b9358fad3f615112c___(
      &v42,
      v31);
    std::pair<DataStoreCache::NotificationCookie,Microsoft::WRL::ComPtr<IWeakReference>>::~pair<DataStoreCache::NotificationCookie,Microsoft::WRL::ComPtr<IWeakReference>>(v43);
    v32 = v42;
    v33 = (*(__int64 (__fastcall **)(__int64, struct INotificationPresenter *, char *))(*(_QWORD *)v46 + 152LL))(
            v46,
            v42,
            (char *)this + 192);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v33,
        v38);
      if ( v32 )
        (*(void (__fastcall **)(struct INotificationPresenter *))(*(_QWORD *)v32 + 16LL))(v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v12 = v34;
      goto LABEL_43;
    }
    if ( v32 )
      (*(void (__fastcall **)(struct INotificationPresenter *))(*(_QWORD *)v32 + 16LL))(v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  }
  v35 = a7;
  if ( *((struct INotificationPresenter **)this + 9) != a7 )
  {
    v42 = a7;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v42);
    v36 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v35;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v12 = 0;
LABEL_43:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  return v12;
}

```

## disassembly

```asm
0x18028b1f0  mov     [rsp-28h+arg_10], rbx
0x18028b1f5  push    rbp
0x18028b1f6  push    rsi
0x18028b1f7  push    rdi
0x18028b1f8  push    r14
0x18028b1fa  push    r15
0x18028b1fc  mov     rbp, rsp
0x18028b1ff  sub     rsp, 60h
0x18028b203  mov     rdi, r9
0x18028b206  mov     rbx, r8
0x18028b209  mov     r14, rcx
0x18028b20c  mov     [rcx+88h], rdx
0x18028b213  xor     r15d, r15d
0x18028b216  mov     [rbp+var_28], r15
0x18028b21a  lea     rax, [rbp+var_28]
0x18028b21e  mov     [rbp+var_30], rax
0x18028b222  lea     rcx, [rbp+var_30]
0x18028b226  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18028b22b  mov     rdx, rax
0x18028b22e  mov     rcx, rbx
0x18028b231  call    ??$AsWeak@UIRefreshTileNotifications@@@WRL@Microsoft@@YAJPEAUIRefreshTileNotifications@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IRefreshTileNotifications>(IRefreshTileNotifications *,Microsoft::WRL::WeakRef *)
0x18028b236  mov     ebx, eax
0x18028b238  test    eax, eax
0x18028b23a  jns     short loc_18028B242
0x18028b23c  lea     edx, [r15+29h]
0x18028b240  jmp     short loc_18028B26D
0x18028b242  lea     rax, [r14+0E0h]
0x18028b249  mov     [rbp+var_30], rax
0x18028b24d  lea     rcx, [rbp+var_30]
0x18028b251  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18028b256  mov     rdx, rax
0x18028b259  mov     rcx, [rbp+var_28]
0x18028b25d  call    ??$AsAgile@UIWeakReference@@@WRL@Microsoft@@YAJPEAUIWeakReference@@PEAVAgileRef@01@@Z; Microsoft::WRL::AsAgile<IWeakReference>(IWeakReference *,Microsoft::WRL::AgileRef *)
0x18028b262  mov     ebx, eax
0x18028b264  test    eax, eax
0x18028b266  jns     short loc_18028B285
0x18028b268  mov     edx, 2Ah ; '*'; void *
0x18028b26d  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b274  mov     r9d, eax; char *
0x18028b277  mov     rcx, [rbp+28h]; this
0x18028b27b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b280  jmp     loc_18028B66A
0x18028b285  lea     rax, [r14+0A0h]
0x18028b28c  mov     [rbp+var_30], rax
0x18028b290  lea     rcx, [rbp+var_30]
0x18028b294  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18028b299  mov     rbx, rax
0x18028b29c  test    rdi, rdi
0x18028b29f  jz      short loc_18028B2CB
0x18028b2a1  mov     rcx, rax
0x18028b2a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b2a9  mov     r9, rbx
0x18028b2ac  mov     r8, rdi
0x18028b2af  lea     rdx, _GUID_f9e87849_b323_eefa_3204_8a2d2d2b4432
0x18028b2b6  xor     ecx, ecx
0x18028b2b8  call    cs:__imp_RoGetAgileReference
0x18028b2be  mov     ebx, eax
0x18028b2c0  test    eax, eax
0x18028b2c2  jns     short loc_18028B2EB
0x18028b2c4  mov     edx, 2Ch ; ','
0x18028b2c9  jmp     short loc_18028B26D
0x18028b2cb  mov     [rbp+var_20], r15
0x18028b2cf  mov     rax, [rax]
0x18028b2d2  mov     [rbp+var_30], rax
0x18028b2d6  mov     [rbx], r15
0x18028b2d9  lea     rcx, [rbp+var_30]
0x18028b2dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b2e2  lea     rcx, [rbp+var_20]
0x18028b2e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b2eb  lea     rdi, [r14+90h]
0x18028b2f2  mov     rdx, [rbp+arg_20]
0x18028b2f6  mov     rcx, rdi
0x18028b2f9  call    ??4?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDataItem@DataStoreCache@@@Z; Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(DataStoreCache::IDataItem *)
0x18028b2fe  lea     rcx, [r14+98h]
0x18028b305  mov     rdx, [rbp+arg_28]
0x18028b309  call    ??4?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDataItem@DataStoreCache@@@Z; Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(DataStoreCache::IDataItem *)
0x18028b30e  lea     rbx, [r14+50h]
0x18028b312  mov     rcx, [rbx]; string
0x18028b315  call    cs:__imp_WindowsDeleteString
0x18028b31b  mov     [rbx], r15
0x18028b31e  mov     rdx, rbx; HSTRING *
0x18028b321  mov     rcx, [rdi]; struct IUnknown *
0x18028b324  call    ?GetWNSId@TileNotificationManager@@SAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; TileNotificationManager::GetWNSId(IUnknown *,HSTRING__ * *)
0x18028b329  mov     ebx, eax
0x18028b32b  test    eax, eax
0x18028b32d  jns     short loc_18028B339
0x18028b32f  mov     edx, 31h ; '1'
0x18028b334  jmp     loc_18028B26D
0x18028b339  mov     [rbp+arg_8], r15
0x18028b33d  lea     rdx, [rbp+arg_8]
0x18028b341  mov     rcx, rdi
0x18028b344  call    ??$As@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<WindowsInternal::Shell::UnifiedTile::IUnifiedTile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTile>>)
0x18028b349  mov     ebx, eax
0x18028b34b  test    eax, eax
0x18028b34d  jns     short loc_18028B376
0x18028b34f  mov     rcx, [rbp+28h]; this
0x18028b353  mov     r9d, eax; char *
0x18028b356  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b35d  mov     edx, 34h ; '4'; void *
0x18028b362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b367  nop
0x18028b368  lea     rcx, [rbp+arg_8]
0x18028b36c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b371  jmp     loc_18028B66A
0x18028b376  mov     [rbp+arg_0], r15
0x18028b37a  mov     rdi, [rbp+arg_8]
0x18028b37e  mov     rax, [rdi]
0x18028b381  mov     rbx, [rax+30h]
0x18028b385  lea     rcx, [rbp+arg_0]
0x18028b389  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b38e  lea     rdx, [rbp+arg_0]
0x18028b392  mov     rcx, rdi
0x18028b395  mov     rax, rbx
0x18028b398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b39d  mov     ebx, eax
0x18028b39f  test    eax, eax
0x18028b3a1  jns     short loc_18028B3C7
0x18028b3a3  mov     rcx, [rbp+28h]; this
0x18028b3a7  mov     r9d, eax; char *
0x18028b3aa  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b3b1  mov     edx, 36h ; '6'; void *
0x18028b3b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b3bb  nop
0x18028b3bc  lea     rcx, [rbp+arg_0]
0x18028b3c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b3c5  jmp     short loc_18028B368
0x18028b3c7  mov     [rbp+var_40], r15
0x18028b3cb  lea     rdx, [rbp+var_40]
0x18028b3cf  lea     rcx, [rbp+arg_0]
0x18028b3d3  call    ??$As@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>>)
0x18028b3d8  mov     ebx, eax
0x18028b3da  test    eax, eax
0x18028b3dc  jns     short loc_18028B402
0x18028b3de  mov     edx, 38h ; '8'; void *
0x18028b3e3  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b3ea  mov     r9d, eax; char *
0x18028b3ed  mov     rcx, [rbp+28h]; this
0x18028b3f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b3f6  nop
0x18028b3f7  lea     rcx, [rbp+var_40]
0x18028b3fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b400  jmp     short loc_18028B3BC
0x18028b402  mov     rsi, [rbp+var_40]
0x18028b406  mov     rax, [rsi]
0x18028b409  mov     rdi, [rax+30h]
0x18028b40d  lea     rbx, [r14+0A8h]
0x18028b414  mov     rcx, [rbx]; string
0x18028b417  call    cs:__imp_WindowsDeleteString
0x18028b41d  mov     [rbx], r15
0x18028b420  mov     rdx, rbx
0x18028b423  mov     rcx, rsi
0x18028b426  mov     rax, rdi
0x18028b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b42e  mov     ebx, eax
0x18028b430  test    eax, eax
0x18028b432  jns     short loc_18028B43B
0x18028b434  mov     edx, 3Ah ; ':'
0x18028b439  jmp     short loc_18028B3E3
0x18028b43b  mov     rsi, [rbp+var_40]
0x18028b43f  mov     rax, [rsi]
0x18028b442  mov     rdi, [rax+38h]
0x18028b446  lea     rbx, [r14+0B0h]
0x18028b44d  mov     rcx, [rbx]; string
0x18028b450  call    cs:__imp_WindowsDeleteString
0x18028b456  mov     [rbx], r15
0x18028b459  mov     rdx, rbx
0x18028b45c  mov     rcx, rsi
0x18028b45f  mov     rax, rdi
0x18028b462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b467  mov     ebx, eax
0x18028b469  test    eax, eax
0x18028b46b  jns     short loc_18028B477
0x18028b46d  mov     edx, 3Bh ; ';'
0x18028b472  jmp     loc_18028B3E3
0x18028b477  mov     rsi, [rbp+arg_0]
0x18028b47b  mov     rax, [rsi]
0x18028b47e  mov     rdi, [rax+38h]
0x18028b482  lea     rbx, [r14+0B8h]
0x18028b489  mov     rcx, [rbx]; string
0x18028b48c  call    cs:__imp_WindowsDeleteString
0x18028b492  mov     [rbx], r15
0x18028b495  mov     rdx, rbx
0x18028b498  mov     rcx, rsi
0x18028b49b  mov     rax, rdi
0x18028b49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b4a3  mov     ebx, eax
0x18028b4a5  test    eax, eax
0x18028b4a7  jns     short loc_18028B4B3
0x18028b4a9  mov     edx, 3Ch ; '<'
0x18028b4ae  jmp     loc_18028B3E3
0x18028b4b3  mov     [rbp+string], r15
0x18028b4b7  xor     ecx, ecx; string
0x18028b4b9  call    cs:__imp_WindowsDeleteString
0x18028b4bf  mov     [rbp+string], r15
0x18028b4c3  lea     rdx, [rbp+string]; HSTRING *
0x18028b4c7  mov     rcx, r14; this
0x18028b4ca  call    ?GetPackageFullName@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetPackageFullName(HSTRING__ * *)
0x18028b4cf  test    eax, eax
0x18028b4d1  js      short loc_18028B4DD
0x18028b4d3  cmp     [rbp+string], r15
0x18028b4d7  jnz     loc_18028B60B
0x18028b4dd  mov     [rbp+var_30], r15
0x18028b4e1  lea     rax, [rbp+var_30]
0x18028b4e5  mov     [rbp+var_20], rax
0x18028b4e9  lea     rcx, [rbp+var_20]
0x18028b4ed  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18028b4f2  mov     rdx, rax
0x18028b4f5  mov     rcx, r14
0x18028b4f8  call    ??$AsWeak@VTileNotificationManager@@@WRL@Microsoft@@YAJPEAVTileNotificationManager@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<TileNotificationManager>(TileNotificationManager *,Microsoft::WRL::WeakRef *)
0x18028b4fd  mov     ebx, eax
0x18028b4ff  test    eax, eax
0x18028b501  jns     short loc_18028B539
0x18028b503  mov     rcx, [rbp+28h]; this
0x18028b507  mov     r9d, eax; char *
0x18028b50a  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b511  mov     edx, 45h ; 'E'; void *
0x18028b516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b51b  nop
0x18028b51c  lea     rcx, [rbp+var_30]
0x18028b520  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b525  nop
0x18028b526  mov     rcx, [rbp+string]; string
0x18028b52a  call    cs:__imp_WindowsDeleteString
0x18028b530  mov     [rbp+string], r15
0x18028b534  jmp     loc_18028B3F7
0x18028b539  lea     r8, [rbp+var_30]
0x18028b53d  mov     rdx, r14
0x18028b540  lea     rcx, [rbp+var_18]
0x18028b544  call    _lambda_c6f71df60640545799b1cdbef48bba18____lambda_c6f71df60640545799b1cdbef48bba18_
0x18028b549  mov     rdx, rax
0x18028b54c  lea     rcx, [rbp+var_20]
0x18028b550  call    Microsoft__WRL__Callback_Windows__Foundation__ITypedEventHandler_WindowsInternal__Shell__UnifiedTile__UnifiedTile___WindowsInternal__Shell__UnifiedTile__TileChangedEventArgs_____lambda_01ce00a31d27118b9358fad3f615112c___
0x18028b555  nop
0x18028b556  lea     rcx, [rbp+var_18]
0x18028b55a  call    ??1?$pair@UNotificationCookie@DataStoreCache@@V?$ComPtr@UIWeakReference@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<DataStoreCache::NotificationCookie,Microsoft::WRL::ComPtr<IWeakReference>>::~pair<DataStoreCache::NotificationCookie,Microsoft::WRL::ComPtr<IWeakReference>>(void)
0x18028b55f  mov     rcx, [rbp+arg_8]
0x18028b563  mov     rax, [rcx]
0x18028b566  lea     r8, [r14+0C0h]
0x18028b56d  mov     rbx, [rbp+var_20]
0x18028b571  mov     rdx, rbx
0x18028b574  mov     rax, [rax+98h]
0x18028b57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b580  mov     edi, eax
0x18028b582  test    eax, eax
0x18028b584  jns     short loc_18028B5ED
0x18028b586  mov     rcx, [rbp+28h]; this
0x18028b58a  mov     r9d, eax; char *
0x18028b58d  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028b594  mov     edx, 61h ; 'a'; void *
0x18028b599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028b59e  nop
0x18028b59f  test    rbx, rbx
0x18028b5a2  jz      short loc_18028B5B4
0x18028b5a4  mov     rax, [rbx]
0x18028b5a7  mov     rcx, rbx
0x18028b5aa  mov     rax, [rax+10h]
0x18028b5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b5b3  nop
0x18028b5b4  lea     rcx, [rbp+var_30]
0x18028b5b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b5bd  nop
0x18028b5be  mov     rcx, [rbp+string]; string
0x18028b5c2  call    cs:__imp_WindowsDeleteString
0x18028b5c8  mov     [rbp+string], r15
0x18028b5cc  lea     rcx, [rbp+var_40]
0x18028b5d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b5d5  nop
0x18028b5d6  lea     rcx, [rbp+arg_0]
0x18028b5da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b5df  nop
0x18028b5e0  lea     rcx, [rbp+arg_8]
0x18028b5e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b5e9  mov     ebx, edi
0x18028b5eb  jmp     short loc_18028B66A
0x18028b5ed  test    rbx, rbx
0x18028b5f0  jz      short loc_18028B602
0x18028b5f2  mov     rax, [rbx]
0x18028b5f5  mov     rcx, rbx
0x18028b5f8  mov     rax, [rax+10h]
0x18028b5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b601  nop
0x18028b602  lea     rcx, [rbp+var_30]
0x18028b606  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028b60b  mov     rbx, [rbp+arg_30]
0x18028b60f  cmp     [r14+48h], rbx
0x18028b613  jz      short loc_18028B63C
0x18028b615  mov     [rbp+var_20], rbx
0x18028b619  lea     rcx, [rbp+var_20]
0x18028b61d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18028b622  mov     rcx, [r14+48h]
0x18028b626  mov     [r14+48h], rbx
0x18028b62a  test    rcx, rcx
0x18028b62d  jz      short loc_18028B63C
0x18028b62f  mov     rax, [rcx]
0x18028b632  mov     rax, [rax+10h]
0x18028b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028b63b  nop
0x18028b63c  mov     rcx, [rbp+string]; string
0x18028b640  call    cs:__imp_WindowsDeleteString
0x18028b646  mov     [rbp+string], r15
  ... truncated ...
```
