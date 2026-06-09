# NotificationCreator::_CreateUpdatableNotificationWithProgress(NotificationMetadata *,bool,uint,Windows::UI::Notifications::IToastNotification * *)

- ea: `0x180136c80`
- end: `0x1801370b6`
- name: `?_CreateUpdatableNotificationWithProgress@NotificationCreator@@AEAAJPEAUNotificationMetadata@@_NIPEAPEAUIToastNotification@Notifications@UI@Windows@@@Z`
- size: `1078`
- prototype: `int(NotificationCreator *__hidden this, struct NotificationMetadata *, bool, unsigned int, struct Windows::UI::Notifications::IToastNotification **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801349ac`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x1800252e8`
- `0x1800553d4`
- `0x180133f50`
- `0x1801351a0`
- `0x180136464`
- `0x180136538`
- `0x180136c80`
- `0x1801370bc`
- `0x1801371f4`
- `0x180137304`
- `0x180137444`
- `0x180137548`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x180136e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x180136e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136da2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013703f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013706b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180137079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180137087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136da2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013703f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013706b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180137079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180137087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136d2e`

## string_xrefs

- `0x180136d66`: `onecoreuap\enduser\winstore\installservice\lib\notificationcreator.cpp`
- `0x180137009`: `onecoreuap\enduser\winstore\installservice\lib\notificationcreator.cpp`
- `0x180136d59`: `NotificationCreator::_CreateUpdatableNotificationWithProgress`
- `0x180136ffd`: `NotificationCreator::_CreateUpdatableNotificationWithProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall NotificationCreator::_CreateUpdatableNotificationWithProgress(
        NotificationCreator *this,
        struct NotificationMetadata *a2,
        bool a3,
        __int64 a4,
        struct Windows::UI::Notifications::IToastNotification **a5)
{
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v9; // rdi
  PCWSTR v10; // rbx
  HRESULT GroupForNotificationType; // esi
  struct Windows::Data::Xml::Dom::IXmlDocument *v12; // rdi
  HSTRING v13; // rbx
  struct Windows::UI::Notifications::IToastNotification *v14; // rbx
  HSTRING v15; // rdi
  __int64 (__fastcall *v16)(struct Windows::UI::Notifications::IToastNotification *, GUID *, __int64 *); // rdi
  unsigned int v17; // ebx
  __int64 v18; // rcx
  int v20; // [rsp+28h] [rbp-A9h]
  _BYTE v21[8]; // [rsp+50h] [rbp-81h] BYREF
  HSTRING newString; // [rsp+58h] [rbp-79h] BYREF
  HSTRING v23; // [rsp+60h] [rbp-71h] BYREF
  HSTRING string; // [rsp+68h] [rbp-69h] BYREF
  HSTRING v25; // [rsp+70h] [rbp-61h] BYREF
  HSTRING v26; // [rsp+78h] [rbp-59h] BYREF
  HSTRING v27; // [rsp+80h] [rbp-51h] BYREF
  __int64 v28; // [rsp+88h] [rbp-49h] BYREF
  __int64 v29; // [rsp+90h] [rbp-41h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v30; // [rsp+98h] [rbp-39h] BYREF
  struct Windows::UI::Notifications::IToastNotification *v31; // [rsp+A0h] [rbp-31h] BYREF
  HSTRING_HEADER v32; // [rsp+A8h] [rbp-29h] BYREF
  HSTRING stringReplaced; // [rsp+C0h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-9h] BYREF
  HSTRING v35; // [rsp+E0h] [rbp+Fh]

  *a5 = 0;
  string = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 6), 0);
  v9 = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 5), 0);
  v10 = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 3), 0);
  WindowsDeleteString(0);
  string = 0;
  GroupForNotificationType = NotificationCreator::_FormatString(
                               this,
                               &string,
                               L"ms-windows-store://pdp/?productId=%1&skuid=%2&catalogid=%3",
                               v10,
                               v9,
                               StringRawBuffer);
  WindowsGetStringRawBuffer(string, 0);
  LogMessage(
    4u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationcreator.cpp",
    0x1E3u,
    "NotificationCreator::_CreateUpdatableNotificationWithProgress",
    -1,
    L"Launch Url: %s",
    0,
    0);
  v27 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    WindowsDeleteString(0);
    v27 = 0;
    GroupForNotificationType = GetGroupForNotificationType(*((unsigned int *)a2 + 2), &v27);
  }
  v26 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    WindowsDeleteString(0);
    v26 = 0;
    GroupForNotificationType = NotificationCreator::_LoadFormattedString(this, 0x2EE1u, 0, &v26);
  }
  v12 = 0;
  v30 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"<toast><visual><binding><text>%Title%</text><progress value=\"{progressValue}\" status=\"{progressStatus}\" /></bi"
       "nding></visual></toast>",
      0x86u,
      0x85u);
    WindowsDeleteString(0);
    newString = 0;
    v13 = (HSTRING)*((_QWORD *)a2 + 8);
    stringReplaced = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v32, L"%Title%", 8u, 7u);
    GroupForNotificationType = WindowsReplaceString(v35, stringReplaced, v13, &newString);
    if ( GroupForNotificationType >= 0 )
    {
      GroupForNotificationType = _CreateXmlDocument(newString, &v30);
      v12 = v30;
      if ( GroupForNotificationType >= 0 )
        GroupForNotificationType = _SetNotificationAction(v30, string, 0);
    }
    WindowsDeleteString(newString);
  }
  v14 = 0;
  v31 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    GroupForNotificationType = _CreateNotificationFromXml(v12, v27, *((HSTRING *)a2 + 3), a3, &v31);
    v14 = v31;
  }
  v23 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
    v23 = 0;
    Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(&newString);
    v15 = newString;
    if ( newString )
    {
      GroupForNotificationType = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(newString + 36));
      if ( GroupForNotificationType >= 0 )
      {
        *((_BYTE *)v15 + 152) = 1;
        newString = 0;
        v23 = v15;
      }
    }
    else
    {
      GroupForNotificationType = -2147024882;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&newString);
  }
  v21[0] = 0;
  if ( GroupForNotificationType >= 0 )
    GroupForNotificationType = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, _BYTE *))(*(_QWORD *)v23 + 80LL))(
                                 v23,
                                 qword_1802CB208,
                                 v26,
                                 v21);
  v25 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    WindowsDeleteString(0);
    v25 = 0;
    GroupForNotificationType = _FormatProgressValueForNotification(*((_DWORD *)a2 + 22), &v25);
    if ( GroupForNotificationType >= 0 )
      GroupForNotificationType = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, _BYTE *))(*(_QWORD *)v23 + 80LL))(
                                   v23,
                                   qword_1802CB228,
                                   v25,
                                   v21);
  }
  v29 = 0;
  if ( GroupForNotificationType >= 0 )
    GroupForNotificationType = _CreateNotificationDataFromKVP((unsigned __int64)(v23 + 4) & -(__int64)(v23 != 0), &v29);
  v28 = 0;
  if ( GroupForNotificationType >= 0 )
  {
    v16 = **(__int64 (__fastcall ***)(struct Windows::UI::Notifications::IToastNotification *, GUID *, __int64 *))v14;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
    GroupForNotificationType = v16(v14, &GUID_15154935_28ea_4727_88e9_c58680e2d118, &v28);
    if ( GroupForNotificationType >= 0 )
    {
      GroupForNotificationType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 56LL))(v28, v29);
      if ( GroupForNotificationType >= 0 )
      {
        (*(void (__fastcall **)(struct Windows::UI::Notifications::IToastNotification *))(*(_QWORD *)v14 + 8LL))(v14);
        *a5 = v14;
        GroupForNotificationType = 0;
      }
    }
  }
  v17 = TraceHR(
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationcreator.cpp",
          0x22Au,
          "NotificationCreator::_CreateUpdatableNotificationWithProgress",
          "hr",
          GroupForNotificationType,
          v20);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
  v18 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  WindowsDeleteString(v25);
  v25 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
  WindowsDeleteString(v26);
  v26 = 0;
  WindowsDeleteString(v27);
  v27 = 0;
  WindowsDeleteString(string);
  return v17;
}

```

## disassembly

```asm
0x180136c80  mov     [rsp-8+arg_18], rbx
0x180136c85  push    rbp
0x180136c86  push    rsi
0x180136c87  push    rdi
0x180136c88  push    r12
0x180136c8a  push    r13
0x180136c8c  push    r14
0x180136c8e  push    r15
0x180136c90  lea     rbp, [rsp-1Fh]
0x180136c95  sub     rsp, 0F0h
0x180136c9c  mov     rax, cs:__security_cookie
0x180136ca3  xor     rax, rsp
0x180136ca6  mov     [rbp+4Fh+var_38], rax
0x180136caa  mov     r12b, r8b
0x180136cad  mov     r14, rdx
0x180136cb0  mov     r15, rcx
0x180136cb3  mov     r13, [rbp+4Fh+arg_20]
0x180136cb7  mov     qword ptr [r13+0], 0
0x180136cbf  mov     [rbp+4Fh+string], 0
0x180136cc7  xor     edx, edx; length
0x180136cc9  mov     rcx, [r14+30h]; string
0x180136ccd  call    cs:__imp_WindowsGetStringRawBuffer
0x180136cd3  mov     rsi, rax
0x180136cd6  xor     edx, edx; length
0x180136cd8  mov     rcx, [r14+28h]; string
0x180136cdc  call    cs:__imp_WindowsGetStringRawBuffer
0x180136ce2  mov     rdi, rax
0x180136ce5  xor     edx, edx; length
0x180136ce7  mov     rcx, [r14+18h]; string
0x180136ceb  call    cs:__imp_WindowsGetStringRawBuffer
0x180136cf1  mov     rbx, rax
0x180136cf4  mov     rcx, [rbp+4Fh+string]; string
0x180136cf8  call    cs:__imp_WindowsDeleteString
0x180136cfe  mov     [rbp+4Fh+string], 0
0x180136d06  mov     [rsp+120h+var_F8], rsi
0x180136d0b  mov     [rsp+120h+var_100], rdi
0x180136d10  mov     r9, rbx
0x180136d13  lea     r8, aMsWindowsStore_0; "ms-windows-store://pdp/?productId=%1&sk"...
0x180136d1a  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x180136d1e  mov     rcx, r15; this
0x180136d21  call    ?_FormatString@NotificationCreator@@AEAAJPEAPEAUHSTRING__@@PEBGZZ; NotificationCreator::_FormatString(HSTRING__ * *,ushort const *,...)
0x180136d26  mov     esi, eax
0x180136d28  xor     edx, edx; length
0x180136d2a  mov     rcx, [rbp+4Fh+string]; string
0x180136d2e  call    cs:__imp_WindowsGetStringRawBuffer
0x180136d34  mov     [rsp+120h+var_E0], rax
0x180136d39  xor     ebx, ebx
0x180136d3b  mov     [rsp+120h+var_E8], rbx; unsigned __int16 *
0x180136d40  mov     [rsp+120h+var_F0], rbx; char *
0x180136d45  lea     rax, aLaunchUrlS; "Launch Url: %s"
0x180136d4c  mov     [rsp+120h+var_F8], rax; int
0x180136d51  mov     dword ptr [rsp+120h+var_100], 0FFFFFFFFh; int
0x180136d59  lea     r9, aNotificationcr_3; "NotificationCreator::_CreateUpdatableNo"...
0x180136d60  mov     r8d, 1E3h; unsigned int
0x180136d66  lea     rdx, aOnecoreuapEndu_48; "onecoreuap\\enduser\\winstore\\installs"...
0x180136d6d  lea     ecx, [rbx+4]; unsigned int
0x180136d70  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180136d75  mov     [rbp+4Fh+var_A0], rbx
0x180136d79  test    esi, esi
0x180136d7b  js      short loc_180136D98
0x180136d7d  xor     ecx, ecx; string
0x180136d7f  call    cs:__imp_WindowsDeleteString
0x180136d85  mov     [rbp+4Fh+var_A0], rbx
0x180136d89  lea     rdx, [rbp+4Fh+var_A0]
0x180136d8d  mov     ecx, [r14+8]
0x180136d91  call    ?GetGroupForNotificationType@@YAJW4NotificationType@@PEAPEAUHSTRING__@@@Z; GetGroupForNotificationType(NotificationType,HSTRING__ * *)
0x180136d96  mov     esi, eax
0x180136d98  mov     [rbp+4Fh+var_A8], rbx
0x180136d9c  test    esi, esi
0x180136d9e  js      short loc_180136DC2
0x180136da0  xor     ecx, ecx; string
0x180136da2  call    cs:__imp_WindowsDeleteString
0x180136da8  mov     [rbp+4Fh+var_A8], rbx
0x180136dac  lea     r9, [rbp+4Fh+var_A8]; HSTRING *
0x180136db0  xor     r8d, r8d; string
0x180136db3  mov     edx, 2EE1h; uID
0x180136db8  mov     rcx, r15; this
0x180136dbb  call    ?_LoadFormattedString@NotificationCreator@@AEAAJIPEAUHSTRING__@@PEAPEAU2@@Z; NotificationCreator::_LoadFormattedString(uint,HSTRING__ *,HSTRING__ * *)
0x180136dc0  mov     esi, eax
0x180136dc2  xor     r15d, r15d
0x180136dc5  mov     edi, r15d
0x180136dc8  mov     [rbp+4Fh+var_88], r15
0x180136dcc  test    esi, esi
0x180136dce  js      loc_180136E71
0x180136dd4  mov     [rbp+4Fh+var_40], r15
0x180136dd8  mov     r9d, 85h; unsigned int
0x180136dde  lea     r8d, [r9+1]; unsigned int
0x180136de2  lea     rdx, aToastVisualBin; "<toast><visual><binding><text>%Title%</"...
0x180136de9  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180136ded  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180136df2  nop
0x180136df3  mov     [rbp+4Fh+newString], r15
0x180136df7  xor     ecx, ecx; string
0x180136df9  call    cs:__imp_WindowsDeleteString
0x180136dff  mov     [rbp+4Fh+newString], r15
0x180136e03  mov     rbx, [r14+40h]
0x180136e07  mov     [rbp+4Fh+stringReplaced], r15
0x180136e0b  lea     r9d, [r15+7]; unsigned int
0x180136e0f  lea     r8d, [r15+8]; unsigned int
0x180136e13  lea     rdx, aTitle; "%Title%"
0x180136e1a  lea     rcx, [rbp+4Fh+var_78]; hstringHeader
0x180136e1e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180136e23  lea     r9, [rbp+4Fh+newString]; newString
0x180136e27  mov     r8, rbx; stringReplaceWith
0x180136e2a  mov     rdx, [rbp+4Fh+stringReplaced]; stringReplaced
0x180136e2e  mov     rcx, [rbp+4Fh+var_40]; string
0x180136e32  call    cs:__imp_WindowsReplaceString
0x180136e38  mov     esi, eax
0x180136e3a  test    eax, eax
0x180136e3c  js      short loc_180136E66
0x180136e3e  lea     rdx, [rbp+4Fh+var_88]; struct Windows::Data::Xml::Dom::IXmlDocument **
0x180136e42  mov     rcx, [rbp+4Fh+newString]; HSTRING
0x180136e46  call    ?_CreateXmlDocument@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; _CreateXmlDocument(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x180136e4b  mov     esi, eax
0x180136e4d  mov     rdi, [rbp+4Fh+var_88]
0x180136e51  test    eax, eax
0x180136e53  js      short loc_180136E66
0x180136e55  xor     r8d, r8d; bool
0x180136e58  mov     rdx, [rbp+4Fh+string]; HSTRING
0x180136e5c  mov     rcx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136e5f  call    ?_SetNotificationAction@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@_N@Z; _SetNotificationAction(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *,bool)
0x180136e64  mov     esi, eax
0x180136e66  mov     rcx, [rbp+4Fh+newString]; string
0x180136e6a  call    cs:__imp_WindowsDeleteString
0x180136e70  nop
0x180136e71  mov     rbx, r15
0x180136e74  mov     [rbp+4Fh+var_80], rbx
0x180136e78  test    esi, esi
0x180136e7a  js      short loc_180136E9E
0x180136e7c  lea     rax, [rbp+4Fh+var_80]
0x180136e80  mov     [rsp+120h+var_100], rax; struct Windows::UI::Notifications::IToastNotification **
0x180136e85  mov     r9b, r12b; bool
0x180136e88  mov     r8, [r14+18h]; HSTRING
0x180136e8c  mov     rdx, [rbp+4Fh+var_A0]; HSTRING
0x180136e90  mov     rcx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136e93  call    ?_CreateNotificationFromXml@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@1_NPEAPEAUIToastNotification@Notifications@UI@5@@Z; _CreateNotificationFromXml(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *,HSTRING__ *,bool,Windows::UI::Notifications::IToastNotification * *)
0x180136e98  mov     esi, eax
0x180136e9a  mov     rbx, [rbp+4Fh+var_80]
0x180136e9e  mov     [rbp+4Fh+var_C0], r15
0x180136ea2  test    esi, esi
0x180136ea4  js      short loc_180136EF6
0x180136ea6  lea     rcx, [rbp+4Fh+var_C0]
0x180136eaa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180136eaf  mov     [rbp+4Fh+var_C0], r15
0x180136eb3  lea     rcx, [rbp+4Fh+newString]
0x180136eb7  call    ??$Make@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@12@AEBU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@5678@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@5678@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x180136ebc  mov     rdi, [rbp+4Fh+newString]
0x180136ec0  test    rdi, rdi
0x180136ec3  jnz     short loc_180136ECC
0x180136ec5  mov     esi, 8007000Eh
0x180136eca  jmp     short loc_180136EED
0x180136ecc  lea     rcx, [rdi+90h]; this
0x180136ed3  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x180136ed8  mov     esi, eax
0x180136eda  test    eax, eax
0x180136edc  js      short loc_180136EED
0x180136ede  mov     byte ptr [rdi+98h], 1
0x180136ee5  mov     [rbp+4Fh+newString], r15
0x180136ee9  mov     [rbp+4Fh+var_C0], rdi
0x180136eed  lea     rcx, [rbp+4Fh+newString]
0x180136ef1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180136ef6  mov     [rsp+120h+var_D0], r15b
0x180136efb  test    esi, esi
0x180136efd  js      short loc_180136F21
0x180136eff  mov     rcx, [rbp+4Fh+var_C0]
0x180136f03  mov     rax, [rcx]
0x180136f06  lea     r9, [rsp+120h+var_D0]
0x180136f0b  mov     r8, [rbp+4Fh+var_A8]
0x180136f0f  mov     rdx, cs:qword_1802CB208
0x180136f16  mov     rax, [rax+50h]
0x180136f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136f1f  mov     esi, eax
0x180136f21  mov     [rbp+4Fh+var_B0], r15
0x180136f25  test    esi, esi
0x180136f27  js      short loc_180136F6A
0x180136f29  xor     ecx, ecx; string
0x180136f2b  call    cs:__imp_WindowsDeleteString
0x180136f31  mov     [rbp+4Fh+var_B0], r15
0x180136f35  lea     rdx, [rbp+4Fh+var_B0]; HSTRING *
0x180136f39  mov     ecx, [r14+58h]; unsigned int
0x180136f3d  call    ?_FormatProgressValueForNotification@@YAJIPEAPEAUHSTRING__@@@Z; _FormatProgressValueForNotification(uint,HSTRING__ * *)
0x180136f42  mov     esi, eax
0x180136f44  test    eax, eax
0x180136f46  js      short loc_180136F6A
0x180136f48  mov     rcx, [rbp+4Fh+var_C0]
0x180136f4c  mov     rax, [rcx]
0x180136f4f  lea     r9, [rsp+120h+var_D0]
0x180136f54  mov     r8, [rbp+4Fh+var_B0]
0x180136f58  mov     rdx, cs:qword_1802CB228
0x180136f5f  mov     rax, [rax+50h]
0x180136f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136f68  mov     esi, eax
0x180136f6a  mov     [rbp+4Fh+var_90], r15
0x180136f6e  test    esi, esi
0x180136f70  js      short loc_180136F8E
0x180136f72  mov     rax, [rbp+4Fh+var_C0]
0x180136f76  lea     rdx, [rax+10h]
0x180136f7a  neg     rax
0x180136f7d  sbb     rcx, rcx
0x180136f80  and     rcx, rdx
0x180136f83  lea     rdx, [rbp+4Fh+var_90]
0x180136f87  call    ?_CreateNotificationDataFromKVP@@YAJPEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@PEAPEAUINotificationData@Notifications@UI@4@@Z; _CreateNotificationDataFromKVP(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *> *,Windows::UI::Notifications::INotificationData * *)
0x180136f8c  mov     esi, eax
0x180136f8e  mov     [rbp+4Fh+var_98], r15
0x180136f92  test    esi, esi
0x180136f94  js      short loc_180136FF2
0x180136f96  mov     rax, [rbx]
0x180136f99  mov     rdi, [rax]
0x180136f9c  lea     rcx, [rbp+4Fh+var_98]
0x180136fa0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180136fa5  lea     r8, [rbp+4Fh+var_98]
0x180136fa9  lea     rdx, _GUID_15154935_28ea_4727_88e9_c58680e2d118
0x180136fb0  mov     rcx, rbx
0x180136fb3  mov     rax, rdi
0x180136fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136fbb  mov     esi, eax
0x180136fbd  test    eax, eax
0x180136fbf  js      short loc_180136FF2
0x180136fc1  mov     rcx, [rbp+4Fh+var_98]
0x180136fc5  mov     rax, [rcx]
0x180136fc8  mov     rdx, [rbp+4Fh+var_90]
0x180136fcc  mov     rax, [rax+38h]
0x180136fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136fd5  mov     esi, eax
0x180136fd7  test    eax, eax
0x180136fd9  js      short loc_180136FF2
0x180136fdb  mov     rax, [rbx]
0x180136fde  mov     rcx, rbx
0x180136fe1  mov     rax, [rax+8]
0x180136fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136fea  nop
0x180136feb  mov     [r13+0], rbx
0x180136fef  mov     esi, r15d
0x180136ff2  mov     dword ptr [rsp+120h+var_100], esi; int
0x180136ff6  lea     r9, aHr; "hr"
0x180136ffd  lea     r8, aNotificationcr_3; "NotificationCreator::_CreateUpdatableNo"...
0x180137004  mov     edx, 22Ah; unsigned int
0x180137009  lea     rcx, aOnecoreuapEndu_48; "onecoreuap\\enduser\\winstore\\installs"...
0x180137010  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180137015  mov     ebx, eax
0x180137017  lea     rcx, [rbp+4Fh+var_98]
0x18013701b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180137020  nop
0x180137021  mov     rcx, [rbp+4Fh+var_90]
0x180137025  test    rcx, rcx
0x180137028  jz      short loc_18013703B
0x18013702a  mov     [rbp+4Fh+var_90], r15
0x18013702e  mov     rdx, [rcx]
0x180137031  mov     rax, [rdx+10h]
0x180137035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013703a  nop
0x18013703b  mov     rcx, [rbp+4Fh+var_B0]; string
0x18013703f  call    cs:__imp_WindowsDeleteString
0x180137045  mov     [rbp+4Fh+var_B0], r15
0x180137049  lea     rcx, [rbp+4Fh+var_C0]
0x18013704d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180137052  nop
0x180137053  lea     rcx, [rbp+4Fh+var_80]
0x180137057  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18013705c  nop
0x18013705d  lea     rcx, [rbp+4Fh+var_88]
0x180137061  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180137066  nop
0x180137067  mov     rcx, [rbp+4Fh+var_A8]; string
0x18013706b  call    cs:__imp_WindowsDeleteString
0x180137071  mov     [rbp+4Fh+var_A8], r15
0x180137075  mov     rcx, [rbp+4Fh+var_A0]; string
0x180137079  call    cs:__imp_WindowsDeleteString
0x18013707f  mov     [rbp+4Fh+var_A0], r15
0x180137083  mov     rcx, [rbp+4Fh+string]; string
0x180137087  call    cs:__imp_WindowsDeleteString
0x18013708d  mov     eax, ebx
0x18013708f  mov     rcx, [rbp+4Fh+var_38]
0x180137093  xor     rcx, rsp; StackCookie
0x180137096  call    __security_check_cookie
0x18013709b  mov     rbx, [rsp+120h+arg_18]
0x1801370a3  add     rsp, 0F0h
0x1801370aa  pop     r15
0x1801370ac  pop     r14
0x1801370ae  pop     r13
0x1801370b0  pop     r12
0x1801370b2  pop     rdi
0x1801370b3  pop     rsi
0x1801370b4  pop     rbp
0x1801370b5  retn
```
