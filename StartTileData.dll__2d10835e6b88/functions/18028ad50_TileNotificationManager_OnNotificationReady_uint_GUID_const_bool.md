# TileNotificationManager::OnNotificationReady(uint,_GUID const &,bool)

- ea: `0x18028ad50`
- end: `0x18028afb1`
- name: `?OnNotificationReady@TileNotificationManager@@UEAAJIAEBU_GUID@@_N@Z`
- size: `609`
- prototype: `__int64 __fastcall(TileNotificationManager *__hidden this, unsigned int, const struct _GUID *, bool)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ce94`
- `0x180015960`
- `0x18001aca4`
- `0x18007ce8c`
- `0x1801cd234`
- `0x180201e50`
- `0x180283060`
- `0x180283590`
- `0x180289a98`
- `0x180289e10`
- `0x18028ad50`
- `0x18028b730`
- `0x18028b980`
- `0x18028bf18`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18028ae48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18028ae48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028ad9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028adbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028af74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028af88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028ad9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028adbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028af74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18028af88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028addf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028adef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028addf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028adef`

## string_xrefs

- `0x18028af1c`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TileNotificationManager::OnNotificationReady(
        RTL_SRWLOCK *this,
        unsigned int a2,
        const struct _GUID *a3,
        bool a4)
{
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v9; // rbx
  unsigned int v10; // ebx
  __int64 v11; // rbx
  int Manager; // eax
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-E0h]
  struct IRefreshTileNotifications *v16; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v21; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v22; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  WindowsDeleteString(0);
  v19 = 0;
  TileNotificationManager::GetApplicationUserModelId((TileNotificationManager *)this, &v19);
  WindowsDeleteString(0);
  string = 0;
  TileNotificationManager::GetTileID((TileNotificationManager *)this, &string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v9 = WindowsGetStringRawBuffer(v19, 0);
  wil::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
  v23[0] = &NotificationTelemetry::NotificationReady::`vftable';
  NotificationTelemetry::NotificationReady::StartActivity(
    (NotificationTelemetry::NotificationReady *)v23,
    v9,
    StringRawBuffer,
    a2,
    a3,
    a4);
  if ( !a4 )
    goto LABEL_13;
  v20 = 0;
  AcquireSRWLockShared(this + 29);
  v21 = this + 29;
  LODWORD(v18) = a2;
  std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(
    &this[26],
    &v22,
    &v18);
  if ( v22 != this[26].Ptr )
  {
    v11 = v22[5];
    if ( v11 )
    {
      v18 = v22[5];
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v18);
      v18 = 0;
      v20 = v11;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v21);
    v16 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    Manager = TileNotificationManager::GetManager((TileNotificationManager *)this, &v16);
    v10 = Manager;
    if ( Manager < 0 )
    {
      v13 = 176;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)Manager,
        v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
      goto LABEL_11;
    }
    Manager = (*(__int64 (__fastcall **)(struct IRefreshTileNotifications *, PVOID))(*(_QWORD *)v16 + 32LL))(
                v16,
                this[18].Ptr);
    v10 = Manager;
    if ( Manager < 0 )
    {
      v13 = 177;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
LABEL_13:
    wil::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23);
    v10 = 0;
    goto LABEL_14;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v21);
  v10 = -2147023728;
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
LABEL_14:
  NotificationTelemetry::NotificationReady::~NotificationReady((NotificationTelemetry::NotificationReady *)v23);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v19);
  return v10;
}

```

## disassembly

```asm
0x18028ad50  push    rbp
0x18028ad52  push    rbx
0x18028ad53  push    rsi
0x18028ad54  push    rdi
0x18028ad55  push    r12
0x18028ad57  push    r14
0x18028ad59  push    r15
0x18028ad5b  lea     rbp, [rsp-0D0h]
0x18028ad63  sub     rsp, 1D0h
0x18028ad6a  mov     rax, cs:__security_cookie
0x18028ad71  xor     rax, rsp
0x18028ad74  mov     [rbp+100h+var_40], rax
0x18028ad7b  mov     r14b, r9b
0x18028ad7e  mov     rsi, r8
0x18028ad81  mov     r12d, edx
0x18028ad84  mov     r15, rcx
0x18028ad87  mov     [rsp+200h+var_1B8], 0
0x18028ad90  mov     [rsp+200h+string], 0
0x18028ad99  xor     ecx, ecx; string
0x18028ad9b  call    cs:__imp_WindowsDeleteString
0x18028ada1  mov     [rsp+200h+var_1B8], 0
0x18028adaa  lea     rdx, [rsp+200h+var_1B8]; HSTRING *
0x18028adaf  mov     rcx, r15; this
0x18028adb2  call    ?GetApplicationUserModelId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetApplicationUserModelId(HSTRING__ * *)
0x18028adb7  mov     rcx, [rsp+200h+string]; string
0x18028adbc  call    cs:__imp_WindowsDeleteString
0x18028adc2  mov     [rsp+200h+string], 0
0x18028adcb  lea     rdx, [rsp+200h+string]; HSTRING *
0x18028add0  mov     rcx, r15; this
0x18028add3  call    ?GetTileID@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetTileID(HSTRING__ * *)
0x18028add8  xor     edx, edx; length
0x18028adda  mov     rcx, [rsp+200h+string]; string
0x18028addf  call    cs:__imp_WindowsGetStringRawBuffer
0x18028ade5  mov     rdi, rax
0x18028ade8  xor     edx, edx; length
0x18028adea  mov     rcx, [rsp+200h+var_1B8]; string
0x18028adef  call    cs:__imp_WindowsGetStringRawBuffer
0x18028adf5  mov     rbx, rax
0x18028adf8  lea     rcx, [rsp+200h+var_190]; struct wil::details::IFailureCallback *
0x18028adfd  call    ??0?$ActivityBase@VNotificationLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18028ae02  lea     rax, ??_7NotificationReady@NotificationTelemetry@@6B@; const NotificationTelemetry::NotificationReady::`vftable'
0x18028ae09  mov     [rsp+200h+var_190], rax
0x18028ae0e  mov     [rsp+200h+var_1D8], r14b; bool
0x18028ae13  mov     [rsp+200h+var_1E0], rsi; int
0x18028ae18  mov     r9d, r12d; unsigned int
0x18028ae1b  mov     r8, rdi; unsigned __int16 *
0x18028ae1e  mov     rdx, rbx; unsigned __int16 *
0x18028ae21  lea     rcx, [rsp+200h+var_190]; this
0x18028ae26  call    ?StartActivity@NotificationReady@NotificationTelemetry@@QEAAXPEBG0IAEBU_GUID@@_N@Z; NotificationTelemetry::NotificationReady::StartActivity(ushort const *,ushort const *,uint,_GUID const &,bool)
0x18028ae2b  nop
0x18028ae2c  test    r14b, r14b
0x18028ae2f  jz      loc_18028AF59
0x18028ae35  mov     [rsp+200h+var_1B0], 0
0x18028ae3e  lea     rbx, [r15+0E8h]
0x18028ae45  mov     rcx, rbx; SRWLock
0x18028ae48  call    cs:__imp_AcquireSRWLockShared
0x18028ae4e  mov     [rsp+200h+var_1A8], rbx
0x18028ae53  mov     dword ptr [rsp+200h+var_1C0], r12d
0x18028ae58  lea     rbx, [r15+0D0h]
0x18028ae5f  lea     r8, [rsp+200h+var_1C0]
0x18028ae64  lea     rdx, [rsp+200h+var_1A0]
0x18028ae69  mov     rcx, rbx
0x18028ae6c  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(ulong const &)
0x18028ae71  mov     r8, [rsp+200h+var_1A0]
0x18028ae76  cmp     r8, [rbx]
0x18028ae79  jnz     short loc_18028AE8F
0x18028ae7b  lea     rcx, [rsp+200h+var_1A8]
0x18028ae80  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18028ae85  mov     ebx, 80070490h
0x18028ae8a  jmp     loc_18028AF39
0x18028ae8f  mov     rbx, [r8+28h]
0x18028ae93  test    rbx, rbx
0x18028ae96  jz      short loc_18028AEBF
0x18028ae98  mov     [rsp+200h+var_1C0], rbx
0x18028ae9d  lea     rcx, [rsp+200h+var_1C0]
0x18028aea2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18028aea7  mov     [rsp+200h+var_1C0], 0
0x18028aeb0  mov     [rsp+200h+var_1B0], rbx
0x18028aeb5  lea     rcx, [rsp+200h+var_1C0]
0x18028aeba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028aebf  lea     rcx, [rsp+200h+var_1A8]
0x18028aec4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18028aec9  mov     [rsp+200h+var_1D0], 0
0x18028aed2  lea     rcx, [rsp+200h+var_1D0]
0x18028aed7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028aedc  lea     rdx, [rsp+200h+var_1D0]; struct IRefreshTileNotifications **
0x18028aee1  mov     rcx, r15; this
0x18028aee4  call    ?GetManager@TileNotificationManager@@AEAAJPEAPEAUIRefreshTileNotifications@@@Z; TileNotificationManager::GetManager(IRefreshTileNotifications * *)
0x18028aee9  mov     ebx, eax
0x18028aeeb  test    eax, eax
0x18028aeed  jns     short loc_18028AEF6
0x18028aeef  mov     edx, 0B0h
0x18028aef4  jmp     short loc_18028AF19
0x18028aef6  mov     rcx, [rsp+200h+var_1D0]
0x18028aefb  mov     rax, [rcx]
0x18028aefe  mov     rdx, [r15+90h]
0x18028af05  mov     rax, [rax+20h]
0x18028af09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028af0e  mov     ebx, eax
0x18028af10  test    eax, eax
0x18028af12  jns     short loc_18028AF45
0x18028af14  mov     edx, 0B1h; void *
0x18028af19  mov     r9d, eax; char *
0x18028af1c  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028af23  mov     rcx, [rbp+108h]; this
0x18028af2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18028af2f  lea     rcx, [rsp+200h+var_1D0]
0x18028af34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af39  lea     rcx, [rsp+200h+var_1B0]
0x18028af3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af43  jmp     short loc_18028AF65
0x18028af45  lea     rcx, [rsp+200h+var_1D0]
0x18028af4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af4f  lea     rcx, [rsp+200h+var_1B0]
0x18028af54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18028af59  lea     rcx, [rsp+200h+var_190]
0x18028af5e  call    ?Stop@?$ActivityBase@VNotificationLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NotificationLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18028af63  xor     ebx, ebx
0x18028af65  lea     rcx, [rsp+200h+var_190]; this
0x18028af6a  call    ??1NotificationReady@NotificationTelemetry@@QEAA@XZ; NotificationTelemetry::NotificationReady::~NotificationReady(void)
0x18028af6f  mov     rcx, [rsp+200h+string]; string
0x18028af74  call    cs:__imp_WindowsDeleteString
0x18028af7a  mov     [rsp+200h+string], 0
0x18028af83  mov     rcx, [rsp+200h+var_1B8]; string
0x18028af88  call    cs:__imp_WindowsDeleteString
0x18028af8e  mov     eax, ebx
0x18028af90  mov     rcx, [rbp+100h+var_40]
0x18028af97  xor     rcx, rsp; StackCookie
0x18028af9a  call    __security_check_cookie
0x18028af9f  add     rsp, 1D0h
0x18028afa6  pop     r15
0x18028afa8  pop     r14
0x18028afaa  pop     r12
0x18028afac  pop     rdi
0x18028afad  pop     rsi
0x18028afae  pop     rbx
0x18028afaf  pop     rbp
0x18028afb0  retn
```
