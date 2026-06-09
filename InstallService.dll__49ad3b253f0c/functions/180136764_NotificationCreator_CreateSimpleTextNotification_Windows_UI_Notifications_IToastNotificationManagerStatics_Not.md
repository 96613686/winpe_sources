# NotificationCreator::_CreateSimpleTextNotification(Windows::UI::Notifications::IToastNotificationManagerStatics *,NotificationMetadata *,bool,bool,HSTRING__ *,bool,Windows::UI::Notifications::IToastNotification * *)

- ea: `0x180136764`
- end: `0x180136c78`
- name: `?_CreateSimpleTextNotification@NotificationCreator@@AEAAJPEAUIToastNotificationManagerStatics@Notifications@UI@Windows@@PEAUNotificationMetadata@@_N2PEAUHSTRING__@@2PEAPEAUIToastNotification@345@@Z`
- size: `1300`
- prototype: `__int64 __fastcall(NotificationCreator *__hidden this, struct Windows::UI::Notifications::IToastNotificationManagerStatics *, struct NotificationMetadata *, bool, bool, HSTRING, bool, struct Windows::UI::Notifications::IToastNotification **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801349ac`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x1800252e8`
- `0x18002c310`
- `0x180033188`
- `0x180136538`
- `0x180136764`
- `0x180137304`
- `0x1801373dc`
- `0x180137444`
- `0x180137548`
- `0x180137890`
- `0x180137af8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013691c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801369d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801369ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136843`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013691c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801369d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801369ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180136879`

## string_xrefs

- `0x1801368b7`: `onecoreuap\enduser\winstore\installservice\lib\notificationcreator.cpp`
- `0x180136b63`: `onecoreuap\enduser\winstore\installservice\lib\notificationcreator.cpp`
- `0x180136bf5`: `onecoreuap\enduser\winstore\installservice\lib\notificationcreator.cpp`
- `0x1801367cd`: `ms-windows-store://DownloadsAndUpdates`
- `0x180136b50`: `toastNotificationManager->GetTemplateContent(ToastTemplateType::ToastTemplateType_ToastImageAndText02, &spToastTemplate)`
- `0x1801368aa`: `NotificationCreator::_CreateSimpleTextNotification`
- `0x180136b57`: `NotificationCreator::_CreateSimpleTextNotification`
- `0x180136be9`: `NotificationCreator::_CreateSimpleTextNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NotificationCreator::_CreateSimpleTextNotification(
        NotificationCreator *this,
        struct Windows::UI::Notifications::IToastNotificationManagerStatics *a2,
        struct NotificationMetadata *a3,
        bool a4,
        bool a5,
        HSTRING a6,
        bool a7,
        struct Windows::UI::Notifications::IToastNotification **a8)
{
  HSTRING v11; // rdi
  bool v12; // si
  int TitleAndMessageForNotification; // ebx
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v15; // rdi
  PCWSTR v16; // rbx
  HSTRING v17; // rax
  unsigned int v18; // r9d
  unsigned int v19; // r8d
  const WCHAR *v20; // rdx
  struct Windows::UI::Notifications::IToastNotificationManagerStatics *v21; // r15
  __int64 (__fastcall *v22)(struct Windows::UI::Notifications::IToastNotificationManagerStatics *, __int64, struct Windows::Data::Xml::Dom::IXmlDocument **); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  int v26; // [rsp+28h] [rbp-B1h]
  HSTRING v27; // [rsp+58h] [rbp-81h] BYREF
  HSTRING v28; // [rsp+60h] [rbp-79h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-71h] BYREF
  HSTRING string; // [rsp+70h] [rbp-69h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v31; // [rsp+78h] [rbp-61h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-59h] BYREF
  struct Windows::UI::Notifications::IToastNotificationManagerStatics *v33; // [rsp+88h] [rbp-51h]
  struct Windows::UI::Notifications::IToastNotification **v34; // [rsp+90h] [rbp-49h]
  HSTRING_HEADER v35; // [rsp+98h] [rbp-41h] BYREF
  HSTRING v36; // [rsp+B0h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-21h] BYREF
  HSTRING v38; // [rsp+D0h] [rbp-9h]

  v33 = a2;
  v11 = a6;
  v29 = a6;
  v34 = a8;
  LODWORD(v27) = 0;
  *a8 = 0;
  string = 0;
  v12 = 0;
  if ( a4 )
  {
    TitleAndMessageForNotification = 0;
    Microsoft::WRL::Wrappers::HString::Set(
      (Microsoft::WRL::Wrappers::HString *)&string,
      L"ms-windows-store://DownloadsAndUpdates",
      0x26u);
  }
  else if ( *((_QWORD *)a3 + 10) && (unsigned int)(*((_DWORD *)a3 + 2) - 4) <= 1 )
  {
    v12 = 1;
    v29 = (HSTRING)*((_QWORD *)a3 + 10);
    TitleAndMessageForNotification = Microsoft::WRL::Wrappers::HString::Set(&string, &v29);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a3 + 6), 0);
    v15 = WindowsGetStringRawBuffer(*((HSTRING *)a3 + 5), 0);
    v16 = WindowsGetStringRawBuffer(*((HSTRING *)a3 + 3), 0);
    WindowsDeleteString(string);
    string = 0;
    TitleAndMessageForNotification = NotificationCreator::_FormatString(
                                       this,
                                       &string,
                                       L"ms-windows-store://pdp/?productId=%1&skuid=%2&catalogid=%3",
                                       v16,
                                       v15,
                                       StringRawBuffer);
    WindowsGetStringRawBuffer(string, 0);
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationcreator.cpp",
      0x17Fu,
      "NotificationCreator::_CreateSimpleTextNotification",
      -1,
      L"Launch Url: %s",
      0,
      0);
    v11 = v29;
    v12 = 0;
  }
  v27 = 0;
  v28 = 0;
  newString = 0;
  if ( TitleAndMessageForNotification < 0 )
    goto LABEL_26;
  switch ( *((_DWORD *)a3 + 2) )
  {
    case 4:
      WindowsDeleteString(0);
      v27 = 0;
      TitleAndMessageForNotification = NotificationCreator::_LoadFormattedString(
                                         this,
                                         0x2AFDu,
                                         *((HSTRING *)a3 + 8),
                                         &v27);
      if ( TitleAndMessageForNotification < 0 )
        break;
      WindowsDeleteString(v28);
      v28 = 0;
      TitleAndMessageForNotification = NotificationCreator::_LoadFormattedString(this, 0x2AFFu, v11, &v28);
      if ( TitleAndMessageForNotification < 0 )
        break;
      v18 = 3;
      v19 = 4;
      v20 = L"I_S";
LABEL_23:
      v36 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v35, v20, v19, v18);
      goto LABEL_24;
    case 5:
      WindowsDeleteString(0);
      v28 = 0;
      WindowsDeleteString(v27);
      v27 = 0;
      TitleAndMessageForNotification = NotificationCreator::_GetTitleAndMessageForNotification(
                                         this,
                                         a4,
                                         v11,
                                         (struct NotificationMetadata *)((char *)a3 + 64),
                                         0x2AFEu,
                                         0x2711u,
                                         0x2AFCu,
                                         &v27,
                                         &v28);
      if ( TitleAndMessageForNotification < 0 )
        break;
      if ( !a4 )
      {
        v38 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"U_S", 4u, 3u);
        goto LABEL_14;
      }
      v18 = 5;
      v19 = 6;
      v20 = L"U_S_C";
      goto LABEL_23;
    case 6:
      WindowsDeleteString(0);
      v28 = 0;
      WindowsDeleteString(v27);
      v27 = 0;
      TitleAndMessageForNotification = NotificationCreator::_GetTitleAndMessageForNotification(
                                         this,
                                         a4,
                                         v11,
                                         (struct NotificationMetadata *)((char *)a3 + 64),
                                         0x2AF9u,
                                         0x2710u,
                                         0x2AFAu,
                                         &v27,
                                         &v28);
      if ( TitleAndMessageForNotification >= 0 )
      {
        if ( a4 )
        {
          v38 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"I_E_C", 6u, 5u);
LABEL_14:
          v17 = v38;
LABEL_25:
          v29 = v17;
          TitleAndMessageForNotification = Microsoft::WRL::Wrappers::HString::Set(&newString, &v29);
          break;
        }
        v36 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v35, L"I_E", 4u, 3u);
LABEL_24:
        v17 = v36;
        goto LABEL_25;
      }
      break;
  }
LABEL_26:
  v31 = 0;
  if ( TitleAndMessageForNotification >= 0 )
  {
    v21 = v33;
    v22 = *(__int64 (__fastcall **)(struct Windows::UI::Notifications::IToastNotificationManagerStatics *, __int64, struct Windows::Data::Xml::Dom::IXmlDocument **))(*(_QWORD *)v33 + 64LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
    v23 = v22(v21, 1, &v31);
    TitleAndMessageForNotification = TraceHR(
                                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationcreator.cpp",
                                       0x1B6u,
                                       "NotificationCreator::_CreateSimpleTextNotification",
                                       "toastNotificationManager->GetTemplateContent(ToastTemplateType::ToastTemplateType"
                                       "_ToastImageAndText02, &spToastTemplate)",
                                       v23,
                                       v26);
    if ( TitleAndMessageForNotification >= 0 )
    {
      TitleAndMessageForNotification = _SetNotificationIcon(v31, *((HSTRING *)a3 + 9));
      if ( TitleAndMessageForNotification >= 0 )
      {
        TitleAndMessageForNotification = _SetNotificationTexts(v31, v27, v28);
        if ( TitleAndMessageForNotification >= 0 )
        {
          TitleAndMessageForNotification = _SetNotificationAction(v31, string, v12);
          if ( TitleAndMessageForNotification >= 0 )
          {
            if ( !a4 )
              v11 = (HSTRING)*((_QWORD *)a3 + 3);
            TitleAndMessageForNotification = _CreateNotificationFromXml(v31, newString, v11, a5, v34);
          }
        }
      }
    }
  }
  v24 = TraceHR(
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationcreator.cpp",
          0x1CCu,
          "NotificationCreator::_CreateSimpleTextNotification",
          "hr",
          TitleAndMessageForNotification,
          v26);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v28);
  v28 = 0;
  WindowsDeleteString(v27);
  v27 = 0;
  WindowsDeleteString(string);
  return v24;
}

```

## disassembly

```asm
0x180136764  mov     [rsp-8+arg_18], rbx
0x180136769  push    rbp
0x18013676a  push    rsi
0x18013676b  push    rdi
0x18013676c  push    r12
0x18013676e  push    r13
0x180136770  push    r14
0x180136772  push    r15
0x180136774  lea     rbp, [rsp-7]
0x180136779  sub     rsp, 0E0h
0x180136780  mov     rax, cs:__security_cookie
0x180136787  xor     rax, rsp
0x18013678a  mov     [rbp+37h+var_38], rax
0x18013678e  mov     r12b, r9b
0x180136791  mov     r14, r8
0x180136794  mov     [rbp+37h+var_88], rdx
0x180136798  mov     r13, rcx
0x18013679b  mov     rdi, [rbp+37h+arg_28]
0x18013679f  mov     [rbp+37h+var_A8], rdi
0x1801367a3  mov     rax, [rbp+37h+arg_38]
0x1801367a7  mov     [rbp+37h+var_80], rax
0x1801367ab  xor     r15d, r15d
0x1801367ae  mov     dword ptr [rsp+110h+var_B8], r15d
0x1801367b3  mov     [rax], r15
0x1801367b6  mov     [rbp+37h+string], r15
0x1801367ba  xor     sil, sil
0x1801367bd  mov     [rsp+110h+var_C0], sil
0x1801367c2  test    r9b, r9b
0x1801367c5  jz      short loc_1801367E2
0x1801367c7  xor     ebx, ebx
0x1801367c9  lea     r8d, [r15+26h]; unsigned int
0x1801367cd  lea     rdx, aMsWindowsStore; "ms-windows-store://DownloadsAndUpdates"
0x1801367d4  lea     rcx, [rbp+37h+string]; this
0x1801367d8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801367dd  jmp     loc_1801368D1
0x1801367e2  mov     rcx, [r8+50h]
0x1801367e6  test    rcx, rcx
0x1801367e9  jz      short loc_180136812
0x1801367eb  mov     eax, [r8+8]
0x1801367ef  sub     eax, 4
0x1801367f2  cmp     eax, 1
0x1801367f5  ja      short loc_180136812
0x1801367f7  mov     sil, 1
0x1801367fa  mov     [rbp+37h+var_A8], rcx
0x1801367fe  lea     rdx, [rbp+37h+var_A8]; HSTRING *
0x180136802  lea     rcx, [rbp+37h+string]; newString
0x180136806  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18013680b  mov     ebx, eax
0x18013680d  jmp     loc_1801368D1
0x180136812  xor     edx, edx; length
0x180136814  mov     rcx, [r8+30h]; string
0x180136818  call    cs:__imp_WindowsGetStringRawBuffer
0x18013681e  mov     rsi, rax
0x180136821  xor     edx, edx; length
0x180136823  mov     rcx, [r14+28h]; string
0x180136827  call    cs:__imp_WindowsGetStringRawBuffer
0x18013682d  mov     rdi, rax
0x180136830  xor     edx, edx; length
0x180136832  mov     rcx, [r14+18h]; string
0x180136836  call    cs:__imp_WindowsGetStringRawBuffer
0x18013683c  mov     rbx, rax
0x18013683f  mov     rcx, [rbp+37h+string]; string
0x180136843  call    cs:__imp_WindowsDeleteString
0x180136849  mov     [rbp+37h+string], 0
0x180136851  mov     [rsp+110h+var_E8], rsi
0x180136856  mov     [rsp+110h+var_F0], rdi
0x18013685b  mov     r9, rbx
0x18013685e  lea     r8, aMsWindowsStore_0; "ms-windows-store://pdp/?productId=%1&sk"...
0x180136865  lea     rdx, [rbp+37h+string]; HSTRING *
0x180136869  mov     rcx, r13; this
0x18013686c  call    ?_FormatString@NotificationCreator@@AEAAJPEAPEAUHSTRING__@@PEBGZZ; NotificationCreator::_FormatString(HSTRING__ * *,ushort const *,...)
0x180136871  mov     ebx, eax
0x180136873  xor     edx, edx; length
0x180136875  mov     rcx, [rbp+37h+string]; string
0x180136879  call    cs:__imp_WindowsGetStringRawBuffer
0x18013687f  mov     [rsp+110h+var_D0], rax
0x180136884  mov     [rsp+110h+var_D8], 0; unsigned __int16 *
0x18013688d  mov     [rsp+110h+var_E0], 0; char *
0x180136896  lea     rax, aLaunchUrlS; "Launch Url: %s"
0x18013689d  mov     [rsp+110h+var_E8], rax; int
0x1801368a2  mov     dword ptr [rsp+110h+var_F0], 0FFFFFFFFh; int
0x1801368aa  lea     r9, aNotificationcr_0; "NotificationCreator::_CreateSimpleTextN"...
0x1801368b1  mov     r8d, 17Fh; unsigned int
0x1801368b7  lea     rdx, aOnecoreuapEndu_48; "onecoreuap\\enduser\\winstore\\installs"...
0x1801368be  mov     ecx, 4; unsigned int
0x1801368c3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1801368c8  mov     rdi, [rbp+37h+var_A8]
0x1801368cc  mov     sil, [rsp+110h+var_C0]
0x1801368d1  xor     eax, eax
0x1801368d3  mov     [rsp+110h+var_B8], rax
0x1801368d8  mov     [rbp+37h+var_B0], rax
0x1801368dc  mov     [rbp+37h+newString], rax
0x1801368e0  test    ebx, ebx
0x1801368e2  js      loc_180136B14
0x1801368e8  mov     ecx, [r14+8]
0x1801368ec  sub     ecx, 4
0x1801368ef  jz      loc_180136A82
0x1801368f5  sub     ecx, 1
0x1801368f8  jz      loc_1801369D5
0x1801368fe  cmp     ecx, 1
0x180136901  jnz     loc_180136B14
0x180136907  xor     ecx, ecx; string
0x180136909  call    cs:__imp_WindowsDeleteString
0x18013690f  mov     [rbp+37h+var_B0], 0
0x180136917  mov     rcx, [rsp+110h+var_B8]; string
0x18013691c  call    cs:__imp_WindowsDeleteString
0x180136922  mov     [rsp+110h+var_B8], 0
0x18013692b  lea     r9, [r14+40h]; struct Microsoft::WRL::Wrappers::HString *
0x18013692f  lea     rax, [rbp+37h+var_B0]
0x180136933  mov     [rsp+110h+var_D0], rax; HSTRING *
0x180136938  lea     rax, [rsp+110h+var_B8]
0x18013693d  mov     [rsp+110h+var_D8], rax; HSTRING *
0x180136942  mov     dword ptr [rsp+110h+var_E0], 2AFAh; unsigned int
0x18013694a  mov     dword ptr [rsp+110h+var_E8], 2710h; unsigned int
0x180136952  mov     dword ptr [rsp+110h+var_F0], 2AF9h; unsigned int
0x18013695a  mov     r8, rdi; HSTRING
0x18013695d  mov     dl, r12b; bool
0x180136960  mov     rcx, r13; this
0x180136963  call    ?_GetTitleAndMessageForNotification@NotificationCreator@@AEAAJ_NPEAUHSTRING__@@AEAVHString@Wrappers@WRL@Microsoft@@IIIPEAPEAU2@3@Z; NotificationCreator::_GetTitleAndMessageForNotification(bool,HSTRING__ *,Microsoft::WRL::Wrappers::HString &,uint,uint,uint,HSTRING__ * *,HSTRING__ * *)
0x180136968  mov     ebx, eax
0x18013696a  test    eax, eax
0x18013696c  js      loc_180136B14
0x180136972  test    r12b, r12b
0x180136975  jz      short loc_1801369A8
0x180136977  mov     [rbp+37h+var_40], 0
0x18013697f  mov     r9d, 5; unsigned int
0x180136985  lea     r8d, [r9+1]; unsigned int
0x180136989  lea     rdx, aIEC; "I_E_C"
0x180136990  lea     rcx, [rbp+37h+hstringHeader]; hstringHeader
0x180136994  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180136999  mov     r15d, 8
0x18013699f  mov     rax, [rbp+37h+var_40]
0x1801369a3  jmp     loc_180136B01
0x1801369a8  mov     [rbp+37h+var_60], 0
0x1801369b0  mov     r9d, 3; unsigned int
0x1801369b6  lea     r8d, [r9+1]; unsigned int
0x1801369ba  lea     rdx, aIE; "I_E"
0x1801369c1  lea     rcx, [rbp+37h+var_78]; hstringHeader
0x1801369c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801369ca  mov     r15d, 10h
0x1801369d0  jmp     loc_180136AFD
0x1801369d5  xor     ecx, ecx; string
0x1801369d7  call    cs:__imp_WindowsDeleteString
0x1801369dd  mov     [rbp+37h+var_B0], 0
0x1801369e5  mov     rcx, [rsp+110h+var_B8]; string
0x1801369ea  call    cs:__imp_WindowsDeleteString
0x1801369f0  mov     [rsp+110h+var_B8], 0
0x1801369f9  lea     r9, [r14+40h]; struct Microsoft::WRL::Wrappers::HString *
0x1801369fd  lea     rax, [rbp+37h+var_B0]
0x180136a01  mov     [rsp+110h+var_D0], rax; HSTRING *
0x180136a06  lea     rax, [rsp+110h+var_B8]
0x180136a0b  mov     [rsp+110h+var_D8], rax; HSTRING *
0x180136a10  mov     dword ptr [rsp+110h+var_E0], 2AFCh; unsigned int
0x180136a18  mov     dword ptr [rsp+110h+var_E8], 2711h; unsigned int
0x180136a20  mov     dword ptr [rsp+110h+var_F0], 2AFEh; unsigned int
0x180136a28  mov     r8, rdi; HSTRING
0x180136a2b  mov     dl, r12b; bool
0x180136a2e  mov     rcx, r13; this
0x180136a31  call    ?_GetTitleAndMessageForNotification@NotificationCreator@@AEAAJ_NPEAUHSTRING__@@AEAVHString@Wrappers@WRL@Microsoft@@IIIPEAPEAU2@3@Z; NotificationCreator::_GetTitleAndMessageForNotification(bool,HSTRING__ *,Microsoft::WRL::Wrappers::HString &,uint,uint,uint,HSTRING__ * *,HSTRING__ * *)
0x180136a36  mov     ebx, eax
0x180136a38  test    eax, eax
0x180136a3a  js      loc_180136B14
0x180136a40  test    r12b, r12b
0x180136a43  jz      short loc_180136A5B
0x180136a45  mov     r9d, 5
0x180136a4b  lea     r8d, [r9+1]
0x180136a4f  lea     rdx, aUSC; "U_S_C"
0x180136a56  jmp     loc_180136AEC
0x180136a5b  mov     [rbp+37h+var_40], 0
0x180136a63  mov     r9d, 3; unsigned int
0x180136a69  lea     r8d, [r9+1]; unsigned int
0x180136a6d  lea     rdx, aUS; "U_S"
0x180136a74  lea     rcx, [rbp+37h+hstringHeader]; hstringHeader
0x180136a78  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180136a7d  jmp     loc_18013699F
0x180136a82  xor     ecx, ecx; string
0x180136a84  call    cs:__imp_WindowsDeleteString
0x180136a8a  mov     [rsp+110h+var_B8], 0
0x180136a93  lea     r9, [rsp+110h+var_B8]; HSTRING *
0x180136a98  mov     r8, [r14+40h]; string
0x180136a9c  mov     edx, 2AFDh; uID
0x180136aa1  mov     rcx, r13; this
0x180136aa4  call    ?_LoadFormattedString@NotificationCreator@@AEAAJIPEAUHSTRING__@@PEAPEAU2@@Z; NotificationCreator::_LoadFormattedString(uint,HSTRING__ *,HSTRING__ * *)
0x180136aa9  mov     ebx, eax
0x180136aab  test    eax, eax
0x180136aad  js      short loc_180136B14
0x180136aaf  mov     rcx, [rbp+37h+var_B0]; string
0x180136ab3  call    cs:__imp_WindowsDeleteString
0x180136ab9  mov     [rbp+37h+var_B0], 0
0x180136ac1  lea     r9, [rbp+37h+var_B0]; HSTRING *
0x180136ac5  mov     r8, rdi; string
0x180136ac8  mov     edx, 2AFFh; uID
0x180136acd  mov     rcx, r13; this
0x180136ad0  call    ?_LoadFormattedString@NotificationCreator@@AEAAJIPEAUHSTRING__@@PEAPEAU2@@Z; NotificationCreator::_LoadFormattedString(uint,HSTRING__ *,HSTRING__ * *)
0x180136ad5  mov     ebx, eax
0x180136ad7  test    eax, eax
0x180136ad9  js      short loc_180136B14
0x180136adb  mov     r9d, 3; unsigned int
0x180136ae1  lea     r8d, [r9+1]; unsigned int
0x180136ae5  lea     rdx, aIS; "I_S"
0x180136aec  mov     [rbp+37h+var_60], 0
0x180136af4  lea     rcx, [rbp+37h+var_78]; hstringHeader
0x180136af8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180136afd  mov     rax, [rbp+37h+var_60]
0x180136b01  mov     [rbp+37h+var_A8], rax
0x180136b05  lea     rdx, [rbp+37h+var_A8]; HSTRING *
0x180136b09  lea     rcx, [rbp+37h+newString]; newString
0x180136b0d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180136b12  mov     ebx, eax
0x180136b14  mov     [rbp+37h+var_98], 0
0x180136b1c  test    ebx, ebx
0x180136b1e  js      loc_180136BDE
0x180136b24  mov     r15, [rbp+37h+var_88]
0x180136b28  mov     rax, [r15]
0x180136b2b  mov     rbx, [rax+40h]
0x180136b2f  lea     rcx, [rbp+37h+var_98]
0x180136b33  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180136b38  lea     r8, [rbp+37h+var_98]
0x180136b3c  mov     edx, 1
0x180136b41  mov     rcx, r15
0x180136b44  mov     rax, rbx
0x180136b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136b4c  mov     dword ptr [rsp+110h+var_F0], eax; int
0x180136b50  lea     r9, aToastnotificat_0; "toastNotificationManager->GetTemplateCo"...
0x180136b57  lea     r8, aNotificationcr_0; "NotificationCreator::_CreateSimpleTextN"...
0x180136b5e  mov     edx, 1B6h; unsigned int
0x180136b63  lea     rcx, aOnecoreuapEndu_48; "onecoreuap\\enduser\\winstore\\installs"...
0x180136b6a  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180136b6f  mov     ebx, eax
0x180136b71  test    eax, eax
0x180136b73  js      short loc_180136BDE
0x180136b75  mov     rdx, [r14+48h]; HSTRING
0x180136b79  mov     rcx, [rbp+37h+var_98]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136b7d  call    ?_SetNotificationIcon@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@@Z; _SetNotificationIcon(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *)
0x180136b82  mov     ebx, eax
0x180136b84  test    eax, eax
0x180136b86  js      short loc_180136BDE
0x180136b88  mov     r8, [rbp+37h+var_B0]; HSTRING
0x180136b8c  mov     rdx, [rsp+110h+var_B8]; HSTRING
0x180136b91  mov     rcx, [rbp+37h+var_98]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136b95  call    ?_SetNotificationTexts@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@1@Z; _SetNotificationTexts(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *,HSTRING__ *)
0x180136b9a  mov     ebx, eax
0x180136b9c  test    eax, eax
0x180136b9e  js      short loc_180136BDE
0x180136ba0  mov     r8b, sil; bool
0x180136ba3  mov     rdx, [rbp+37h+string]; HSTRING
0x180136ba7  mov     rcx, [rbp+37h+var_98]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136bab  call    ?_SetNotificationAction@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@_N@Z; _SetNotificationAction(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *,bool)
0x180136bb0  mov     ebx, eax
0x180136bb2  test    eax, eax
0x180136bb4  js      short loc_180136BDE
0x180136bb6  test    r12b, r12b
0x180136bb9  jnz     short loc_180136BBF
0x180136bbb  mov     rdi, [r14+18h]
0x180136bbf  mov     rax, [rbp+37h+var_80]
0x180136bc3  mov     [rsp+110h+var_F0], rax; struct Windows::UI::Notifications::IToastNotification **
0x180136bc8  mov     r9b, [rbp+37h+arg_20]; bool
0x180136bcc  mov     r8, rdi; HSTRING
0x180136bcf  mov     rdx, [rbp+37h+newString]; HSTRING
0x180136bd3  mov     rcx, [rbp+37h+var_98]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180136bd7  call    ?_CreateNotificationFromXml@@YAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAUHSTRING__@@1_NPEAPEAUIToastNotification@Notifications@UI@5@@Z; _CreateNotificationFromXml(Windows::Data::Xml::Dom::IXmlDocument *,HSTRING__ *,HSTRING__ *,bool,Windows::UI::Notifications::IToastNotification * *)
0x180136bdc  mov     ebx, eax
0x180136bde  mov     dword ptr [rsp+110h+var_F0], ebx; int
0x180136be2  lea     r9, aHr; "hr"
0x180136be9  lea     r8, aNotificationcr_0; "NotificationCreator::_CreateSimpleTextN"...
0x180136bf0  mov     edx, 1CCh; unsigned int
0x180136bf5  lea     rcx, aOnecoreuapEndu_48; "onecoreuap\\enduser\\winstore\\installs"...
0x180136bfc  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180136c01  mov     ebx, eax
0x180136c03  lea     rcx, [rbp+37h+var_98]
0x180136c07  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180136c0c  nop
0x180136c0d  mov     rcx, [rbp+37h+newString]; string
0x180136c11  call    cs:__imp_WindowsDeleteString
0x180136c17  mov     [rbp+37h+newString], 0
0x180136c1f  mov     rcx, [rbp+37h+var_B0]; string
0x180136c23  call    cs:__imp_WindowsDeleteString
0x180136c29  mov     [rbp+37h+var_B0], 0
0x180136c31  mov     rcx, [rsp+110h+var_B8]; string
0x180136c36  call    cs:__imp_WindowsDeleteString
0x180136c3c  mov     [rsp+110h+var_B8], 0
0x180136c45  mov     rcx, [rbp+37h+string]; string
0x180136c49  call    cs:__imp_WindowsDeleteString
0x180136c4f  mov     eax, ebx
0x180136c51  mov     rcx, [rbp+37h+var_38]
0x180136c55  xor     rcx, rsp; StackCookie
0x180136c58  call    __security_check_cookie
0x180136c5d  mov     rbx, [rsp+110h+arg_18]
0x180136c65  add     rsp, 0E0h
0x180136c6c  pop     r15
0x180136c6e  pop     r14
0x180136c70  pop     r13
0x180136c72  pop     r12
0x180136c74  pop     rdi
0x180136c75  pop     rsi
0x180136c76  pop     rbp
0x180136c77  retn
```
