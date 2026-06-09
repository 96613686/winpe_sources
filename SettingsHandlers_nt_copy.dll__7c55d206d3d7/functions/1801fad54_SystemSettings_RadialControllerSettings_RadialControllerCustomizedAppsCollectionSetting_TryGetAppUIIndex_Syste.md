# SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppsCollectionSetting::_TryGetAppUIIndex(SystemSettings::RadialControllerSettings::RadialControllerNotificationItem &,bool *)

- ea: `0x1801fad54`
- end: `0x1801fb02f`
- name: `?_TryGetAppUIIndex@RadialControllerCustomizedAppsCollectionSetting@RadialControllerSettings@SystemSettings@@AEAAJAEAURadialControllerNotificationItem@23@PEA_N@Z`
- size: `731`
- prototype: `__int64 __fastcall(SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppsCollectionSetting *__hidden this, struct SystemSettings::RadialControllerSettings::RadialControllerNotificationItem *, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801f88a0`
- `0x1801fa494`
- `0x1801fabfc`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001a64c`
- `0x1800336b0`
- `0x180046850`
- `0x1801f8950`
- `0x1801fad54`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801faf23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801faf23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fae84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faf39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faf8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fae84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faf39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faf8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faeff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faeff`

## string_xrefs

- `0x1801faed5`: `Comparing: notificationId=%ws customizedId=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppsCollectionSetting::_TryGetAppUIIndex(
        SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppsCollectionSetting *this,
        struct SystemSettings::RadialControllerSettings::RadialControllerNotificationItem *a2,
        bool *a3)
{
  int Size; // ebx
  __int64 v7; // rdx
  unsigned int i; // esi
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v16; // rax
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  InputDial::InputDialTraceProvider::Info(
    "shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
    "na",
    0xD3u,
    "_TryGetAppUIIndex");
  *a3 = 0;
  if ( !*((_QWORD *)this + 30) )
    return 0;
  *(_QWORD *)bIgnoreCase = *((_QWORD *)a2 + 1);
  Size = StringCchPrintfW(String1, 0x104u, L"%ws_%ws", L"RadialControllerCustomizedAppsCollection");
  if ( Size >= 0 )
  {
    v20[0] = 0;
    Size = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
             *((_QWORD *)this + 30),
             v20);
    if ( Size >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v20[0] )
          return 0;
        v19 = 0;
        v10 = *((_QWORD *)this + 30);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
        v11 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                v10,
                i,
                &v19);
        Size = v11;
        if ( v11 < 0 )
          break;
        string = 0;
        v12 = v19;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v14 = v13(v12, &string);
        Size = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE5,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
            (const char *)(unsigned int)v14,
            bIgnoreCase[0]);
          WindowsDeleteString(string);
          string = 0;
LABEL_18:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          return (unsigned int)Size;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        InputDial::InputDialTraceProvider::Info(
          "shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          "na",
          0xE7u,
          "Comparing: notificationId=%ws customizedId=%ws",
          String1,
          StringRawBuffer);
        v16 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(String1, -1, v16, -1, 1) == 2 )
        {
          InputDial::InputDialTraceProvider::Info(
            "shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
            "na",
            0xEAu,
            "_TryGetAppUIIndex: found index=%u",
            i);
          *((_DWORD *)a2 + 13) = i;
          *a3 = 1;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          return 0;
        }
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase[0]);
      goto LABEL_18;
    }
    v7 = 222;
  }
  else
  {
    v7 = 218;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
    (const char *)(unsigned int)Size,
    bIgnoreCase[0]);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x1801fad54  push    rbp
0x1801fad56  push    rbx
0x1801fad57  push    rsi
0x1801fad58  push    rdi
0x1801fad59  push    r12
0x1801fad5b  push    r14
0x1801fad5d  push    r15
0x1801fad5f  lea     rbp, [rsp-170h]
0x1801fad67  sub     rsp, 270h
0x1801fad6e  mov     rax, cs:__security_cookie
0x1801fad75  xor     rax, rsp
0x1801fad78  mov     [rbp+1A0h+var_40], rax
0x1801fad7f  mov     r12, r8
0x1801fad82  mov     r15, rdx
0x1801fad85  mov     r14, rcx
0x1801fad88  lea     r9, aTrygetappuiind; "_TryGetAppUIIndex"
0x1801fad8f  mov     r8d, 0D3h; unsigned int
0x1801fad95  lea     rdx, aNa; "na"
0x1801fad9c  lea     rdi, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801fada3  mov     rcx, rdi; char *
0x1801fada6  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x1801fadab  mov     byte ptr [r12], 0
0x1801fadb0  cmp     qword ptr [r14+0F0h], 0
0x1801fadb8  jz      loc_1801FAFAC
0x1801fadbe  mov     rax, [r15+8]
0x1801fadc2  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax; int
0x1801fadc7  lea     r9, aRadialcontroll_17; "RadialControllerCustomizedAppsCollectio"...
0x1801fadce  lea     r8, aWsWs; "%ws_%ws"
0x1801fadd5  mov     edx, 104h; unsigned __int64
0x1801fadda  lea     rcx, [rsp+2A0h+String1]; unsigned __int16 *
0x1801faddf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801fade4  mov     ebx, eax
0x1801fade6  test    eax, eax
0x1801fade8  jns     short loc_1801FAE08
0x1801fadea  mov     edx, 0DAh; void *
0x1801fadef  mov     r8, rdi; unsigned int
0x1801fadf2  mov     r9d, ebx; char *
0x1801fadf5  mov     rcx, [rbp+1A8h]; this
0x1801fadfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fae01  mov     eax, ebx
0x1801fae03  jmp     loc_1801FAFAE
0x1801fae08  mov     [rsp+2A0h+var_260], 0
0x1801fae10  lea     rdx, [rsp+2A0h+var_260]
0x1801fae15  mov     rcx, [r14+0F0h]
0x1801fae1c  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x1801fae21  mov     ebx, eax
0x1801fae23  test    eax, eax
0x1801fae25  jns     short loc_1801FAE2E
0x1801fae27  mov     edx, 0DEh
0x1801fae2c  jmp     short loc_1801FADEF
0x1801fae2e  xor     esi, esi
0x1801fae30  cmp     esi, [rsp+2A0h+var_260]
0x1801fae34  jnb     loc_1801FAFAC
0x1801fae3a  mov     [rsp+2A0h+var_268], 0
0x1801fae43  mov     rbx, [r14+0F0h]
0x1801fae4a  lea     rcx, [rsp+2A0h+var_268]
0x1801fae4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fae54  lea     r8, [rsp+2A0h+var_268]
0x1801fae59  mov     edx, esi
0x1801fae5b  mov     rcx, rbx
0x1801fae5e  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x1801fae63  mov     ebx, eax
0x1801fae65  test    eax, eax
0x1801fae67  js      loc_1801FB008
0x1801fae6d  mov     [rsp+2A0h+string], 0
0x1801fae76  mov     rdi, [rsp+2A0h+var_268]
0x1801fae7b  mov     rax, [rdi]
0x1801fae7e  mov     rbx, [rax+30h]
0x1801fae82  xor     ecx, ecx; string
0x1801fae84  call    cs:__imp_WindowsDeleteString
0x1801fae8b  nop     dword ptr [rax+rax+00h]
0x1801fae90  mov     [rsp+2A0h+string], 0
0x1801fae99  lea     rdx, [rsp+2A0h+string]
0x1801fae9e  mov     rcx, rdi
0x1801faea1  mov     rax, rbx
0x1801faea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faea9  mov     ebx, eax
0x1801faeab  test    eax, eax
0x1801faead  js      loc_1801FAFD0
0x1801faeb3  xor     edx, edx; length
0x1801faeb5  mov     rcx, [rsp+2A0h+string]; string
0x1801faeba  call    cs:__imp_WindowsGetStringRawBuffer
0x1801faec1  nop     dword ptr [rax+rax+00h]
0x1801faec6  mov     [rsp+2A0h+var_278], rax
0x1801faecb  lea     rax, [rsp+2A0h+String1]
0x1801faed0  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax
0x1801faed5  lea     r9, aComparingNotif; "Comparing: notificationId=%ws customize"...
0x1801faedc  mov     r8d, 0E7h; unsigned int
0x1801faee2  lea     rdx, aNa; "na"
0x1801faee9  lea     rdi, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801faef0  mov     rcx, rdi; char *
0x1801faef3  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x1801faef8  xor     edx, edx; length
0x1801faefa  mov     rcx, [rsp+2A0h+string]; string
0x1801faeff  call    cs:__imp_WindowsGetStringRawBuffer
0x1801faf06  nop     dword ptr [rax+rax+00h]
0x1801faf0b  mov     [rsp+2A0h+bIgnoreCase], 1; bIgnoreCase
0x1801faf13  or      ebx, 0FFFFFFFFh
0x1801faf16  mov     r9d, ebx; cchCount2
0x1801faf19  mov     r8, rax; lpString2
0x1801faf1c  mov     edx, ebx; cchCount1
0x1801faf1e  lea     rcx, [rsp+2A0h+String1]; lpString1
0x1801faf23  call    cs:__imp_CompareStringOrdinal
0x1801faf2a  nop     dword ptr [rax+rax+00h]
0x1801faf2f  cmp     eax, 2
0x1801faf32  jz      short loc_1801FAF5F
0x1801faf34  mov     rcx, [rsp+2A0h+string]; string
0x1801faf39  call    cs:__imp_WindowsDeleteString
0x1801faf40  nop     dword ptr [rax+rax+00h]
0x1801faf45  mov     [rsp+2A0h+string], 0
0x1801faf4e  lea     rcx, [rsp+2A0h+var_268]
0x1801faf53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801faf58  inc     esi
0x1801faf5a  jmp     loc_1801FAE30
0x1801faf5f  mov     [rsp+2A0h+bIgnoreCase], esi
0x1801faf63  lea     r9, aTrygetappuiind_0; "_TryGetAppUIIndex: found index=%u"
0x1801faf6a  mov     r8d, 0EAh; unsigned int
0x1801faf70  lea     rdx, aNa; "na"
0x1801faf77  mov     rcx, rdi; char *
0x1801faf7a  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x1801faf7f  mov     [r15+34h], esi
0x1801faf83  mov     byte ptr [r12], 1
0x1801faf88  mov     rcx, [rsp+2A0h+string]; string
0x1801faf8d  call    cs:__imp_WindowsDeleteString
0x1801faf94  nop     dword ptr [rax+rax+00h]
0x1801faf99  mov     [rsp+2A0h+string], 0
0x1801fafa2  lea     rcx, [rsp+2A0h+var_268]
0x1801fafa7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fafac  xor     eax, eax
0x1801fafae  mov     rcx, [rbp+1A0h+var_40]
0x1801fafb5  xor     rcx, rsp; StackCookie
0x1801fafb8  call    __security_check_cookie
0x1801fafbd  add     rsp, 270h
0x1801fafc4  pop     r15
0x1801fafc6  pop     r14
0x1801fafc8  pop     r12
0x1801fafca  pop     rdi
0x1801fafcb  pop     rsi
0x1801fafcc  pop     rbx
0x1801fafcd  pop     rbp
0x1801fafce  retn
0x1801fafd0  mov     rcx, [rbp+1A8h]; this
0x1801fafd7  mov     r9d, eax; char *
0x1801fafda  lea     r8, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801fafe1  mov     edx, 0E5h; void *
0x1801fafe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fafeb  nop
0x1801fafec  mov     rcx, [rsp+2A0h+string]; string
0x1801faff1  call    cs:__imp_WindowsDeleteString
0x1801faff8  nop     dword ptr [rax+rax+00h]
0x1801faffd  mov     [rsp+2A0h+string], 0
0x1801fb006  jmp     short loc_1801FB020
0x1801fb008  mov     rcx, [rbp+1A8h]; this
0x1801fb00f  mov     r9d, eax; char *
0x1801fb012  mov     r8, rdi; unsigned int
0x1801fb015  mov     edx, 0E2h; void *
0x1801fb01a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fb01f  nop
0x1801fb020  lea     rcx, [rsp+2A0h+var_268]
0x1801fb025  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fb02a  jmp     loc_1801FAE01
```
