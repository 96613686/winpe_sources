# _IsWindowsStoreAutoDownloadDisabled(void)

- ea: `0x180062a80`
- end: `0x180062b7b`
- name: `?_IsWindowsStoreAutoDownloadDisabled@@YA_NXZ`
- size: `251`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180061e88`
- `0x180062098`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180034d9c`
- `0x18003771c`
- `0x180062a80`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180062ac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180062ac3`

## string_xrefs

- `0x180062abc`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x180062b53`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x180062b68`: `onecore\base\languageoverlay\common\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool _IsWindowsStoreAutoDownloadDisabled(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int v3; // eax
  wil::details::in1diag3 *v4; // rcx
  int v5; // eax
  const char *v6; // r9
  bool v7; // bl
  _QWORD *v8; // rcx
  bool result; // al
  int v10; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v11; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v11 = 0;
  v10 = 1;
  v13 = 0;
  v0 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
         0x47u,
         &v12,
         (HSTRING *)&v13);
  try
  {
    if ( v0 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    }
    else
    {
      v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
             v13,
             (__int64 *)&v11);
      v4 = retaddr;
      if ( v3 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v11 + 112LL))(v11, &v10);
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x14D,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v5,
            v10);
        v7 = (v10 & 0xFFFFFFFD) == 0;
        v8 = v11;
        if ( v11 )
        {
          v11 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v8 + 16LL))(v8, *v8);
        }
        return v7;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v4,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
      (const char *)(unsigned int)v3,
      v10);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180062a80  mov     r11, rsp
0x180062a83  push    rbx
0x180062a84  sub     rsp, 60h
0x180062a88  mov     rax, cs:__security_cookie
0x180062a8f  xor     rax, rsp
0x180062a92  mov     [rsp+68h+var_18], rax
0x180062a97  mov     qword ptr [r11-40h], 0
0x180062a9f  mov     [rsp+68h+var_48], 1; int
0x180062aa7  mov     qword ptr [r11-20h], 0
0x180062aaf  lea     r9, [r11-20h]; string
0x180062ab3  lea     r8, [r11-38h]; hstringHeader
0x180062ab7  mov     edx, 47h ; 'G'; length
0x180062abc  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180062ac3  call    cs:__imp_WindowsCreateStringReference
0x180062ac9  test    eax, eax
0x180062acb  js      short loc_180062B48
0x180062acd  lea     rdx, [rsp+68h+var_40]
0x180062ad2  mov     rcx, [rsp+68h+var_20]
0x180062ad7  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x180062adc  mov     rcx, [rsp+68h]
0x180062ae1  test    eax, eax
0x180062ae3  js      short loc_180062B50
0x180062ae5  mov     rcx, [rsp+68h+var_40]
0x180062aea  mov     rax, [rcx]
0x180062aed  lea     rdx, [rsp+68h+var_48]
0x180062af2  mov     rax, [rax+70h]
0x180062af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062afb  mov     rcx, [rsp+68h]; this
0x180062b00  test    eax, eax
0x180062b02  js      short loc_180062B65
0x180062b04  test    [rsp+68h+var_48], 0FFFFFFFDh
0x180062b0c  setz    bl
0x180062b0f  mov     rcx, [rsp+68h+var_40]
0x180062b14  test    rcx, rcx
0x180062b17  jz      short loc_180062B2F
0x180062b19  mov     [rsp+68h+var_40], 0
0x180062b22  mov     rdx, [rcx]
0x180062b25  mov     rax, [rdx+10h]
0x180062b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b2e  nop
0x180062b2f  mov     al, bl
0x180062b31  jmp     short loc_180062B35
0x180062b33  xor     al, al
0x180062b35  mov     rcx, [rsp+68h+var_18]
0x180062b3a  xor     rcx, rsp; StackCookie
0x180062b3d  call    __security_check_cookie
0x180062b42  add     rsp, 60h
0x180062b46  pop     rbx
0x180062b47  retn
0x180062b48  mov     ecx, eax; this
0x180062b4a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180062b4f  nop
0x180062b50  mov     r9d, eax; char *
0x180062b53  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062b5a  mov     edx, 14Bh; void *
0x180062b5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180062b65  mov     r9d, eax; char *
0x180062b68  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062b6f  mov     edx, 14Dh; void *
0x180062b74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
