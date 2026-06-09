# GetLanguageAndRegion(HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800ffe38`
- end: `0x18010000b`
- name: `?GetLanguageAndRegion@@YAJPEAPEAUHSTRING__@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(HSTRING *, HSTRING *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007cf24`
- `0x180082c10`
- `0x180082ed0`
- `0x180083240`
- `0x1800d9c20`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800252e8`
- `0x1800ffe38`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fffd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fffe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fff8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fffd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fffe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800fff59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800fff59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ffeb2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ffeb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetLanguageAndRegion(HSTRING *a1, HSTRING *a2)
{
  HSTRING v4; // rbx
  HRESULT ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  HSTRING v12; // rax
  HSTRING v13; // rax
  HSTRING v15; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string1; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string2; // [rsp+60h] [rbp-10h]

  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  string = 0;
  v15 = 0;
  v17 = 0;
  string2 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.UserProfile.GlobalizationPreferences",
    0x34u,
    0x33u);
  v4 = string2;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158, &v17);
  if ( ActivationFactory >= 0 )
  {
    v19 = 0;
    v6 = v17;
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 72LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
    ActivationFactory = v7(v6, &v19);
    if ( ActivationFactory >= 0 )
    {
      string1 = 0;
      v8 = v19;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v19 + 48LL);
      WindowsDeleteString(0);
      string1 = 0;
      ActivationFactory = v9(v8, 0, &string1);
      if ( ActivationFactory >= 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        string2 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L",en,neutral", 0xCu, 0xBu);
        ActivationFactory = WindowsConcatString(string1, string2, &string);
      }
      WindowsDeleteString(string1);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
    if ( ActivationFactory >= 0 )
    {
      if ( !a2
        || (v10 = v17,
            v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 80LL),
            WindowsDeleteString(v15),
            v15 = 0,
            ActivationFactory = v11(v10, &v15),
            ActivationFactory >= 0) )
      {
        v12 = string;
        string = 0;
        *a1 = v12;
        if ( a2 )
        {
          v13 = v15;
          v15 = 0;
          *a2 = v13;
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
  WindowsDeleteString(v15);
  v15 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800ffe38  mov     [rsp-28h+arg_10], rbx
0x1800ffe3d  push    rbp
0x1800ffe3e  push    rsi
0x1800ffe3f  push    rdi
0x1800ffe40  push    r14
0x1800ffe42  push    r15
0x1800ffe44  mov     rbp, rsp
0x1800ffe47  sub     rsp, 70h
0x1800ffe4b  mov     rax, cs:__security_cookie
0x1800ffe52  xor     rax, rsp
0x1800ffe55  mov     [rbp+var_8], rax
0x1800ffe59  mov     rsi, rdx
0x1800ffe5c  mov     r14, rcx
0x1800ffe5f  xor     r15d, r15d
0x1800ffe62  mov     [rcx], r15
0x1800ffe65  test    rdx, rdx
0x1800ffe68  jz      short loc_1800FFE6D
0x1800ffe6a  mov     [rdx], r15
0x1800ffe6d  mov     [rbp+string], r15
0x1800ffe71  mov     [rbp+var_50], r15
0x1800ffe75  mov     [rbp+var_40], r15
0x1800ffe79  mov     [rbp+string2], r15
0x1800ffe7d  mov     r9d, 33h ; '3'; unsigned int
0x1800ffe83  lea     r8d, [r9+1]; unsigned int
0x1800ffe87  lea     rdx, ?RuntimeClass_Windows_System_UserProfile_GlobalizationPreferences@@3QBGB; "Windows.System.UserProfile.Globalizatio"...
0x1800ffe8e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ffe92  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ffe97  mov     rbx, [rbp+string2]
0x1800ffe9b  lea     rcx, [rbp+var_40]
0x1800ffe9f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ffea4  lea     r8, [rbp+var_40]
0x1800ffea8  lea     rdx, _GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158
0x1800ffeaf  mov     rcx, rbx
0x1800ffeb2  call    cs:__imp_RoGetActivationFactory
0x1800ffeb8  mov     ebx, eax
0x1800ffeba  test    eax, eax
0x1800ffebc  js      loc_1800FFFC7
0x1800ffec2  mov     [rbp+var_30], r15
0x1800ffec6  mov     rdi, [rbp+var_40]
0x1800ffeca  mov     rax, [rdi]
0x1800ffecd  mov     rbx, [rax+48h]
0x1800ffed1  lea     rcx, [rbp+var_30]
0x1800ffed5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800ffeda  lea     rdx, [rbp+var_30]
0x1800ffede  mov     rcx, rdi
0x1800ffee1  mov     rax, rbx
0x1800ffee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffee9  mov     ebx, eax
0x1800ffeeb  test    eax, eax
0x1800ffeed  js      short loc_1800FFF6C
0x1800ffeef  mov     [rbp+string1], r15
0x1800ffef3  mov     rdi, [rbp+var_30]
0x1800ffef7  mov     rax, [rdi]
0x1800ffefa  mov     rbx, [rax+30h]
0x1800ffefe  xor     ecx, ecx; string
0x1800fff00  call    cs:__imp_WindowsDeleteString
0x1800fff06  mov     [rbp+string1], r15
0x1800fff0a  lea     r8, [rbp+string1]
0x1800fff0e  xor     edx, edx
0x1800fff10  mov     rcx, rdi
0x1800fff13  mov     rax, rbx
0x1800fff16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff1b  mov     ebx, eax
0x1800fff1d  test    eax, eax
0x1800fff1f  js      short loc_1800FFF61
0x1800fff21  mov     rcx, [rbp+string]; string
0x1800fff25  call    cs:__imp_WindowsDeleteString
0x1800fff2b  mov     [rbp+string], r15
0x1800fff2f  mov     [rbp+string2], r15
0x1800fff33  mov     r9d, 0Bh; unsigned int
0x1800fff39  lea     r8d, [r9+1]; unsigned int
0x1800fff3d  lea     rdx, aEnNeutral; ",en,neutral"
0x1800fff44  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800fff48  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800fff4d  lea     r8, [rbp+string]; newString
0x1800fff51  mov     rdx, [rbp+string2]; string2
0x1800fff55  mov     rcx, [rbp+string1]; string1
0x1800fff59  call    cs:__imp_WindowsConcatString
0x1800fff5f  mov     ebx, eax
0x1800fff61  mov     rcx, [rbp+string1]; string
0x1800fff65  call    cs:__imp_WindowsDeleteString
0x1800fff6b  nop
0x1800fff6c  lea     rcx, [rbp+var_30]
0x1800fff70  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fff75  test    ebx, ebx
0x1800fff77  js      short loc_1800FFFC7
0x1800fff79  test    rsi, rsi
0x1800fff7c  jz      short loc_1800FFFAC
0x1800fff7e  mov     rdi, [rbp+var_40]
0x1800fff82  mov     rax, [rdi]
0x1800fff85  mov     rbx, [rax+50h]
0x1800fff89  mov     rcx, [rbp+var_50]; string
0x1800fff8d  call    cs:__imp_WindowsDeleteString
0x1800fff93  mov     [rbp+var_50], r15
0x1800fff97  lea     rdx, [rbp+var_50]
0x1800fff9b  mov     rcx, rdi
0x1800fff9e  mov     rax, rbx
0x1800fffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffa6  mov     ebx, eax
0x1800fffa8  test    eax, eax
0x1800fffaa  js      short loc_1800FFFC7
0x1800fffac  mov     rax, [rbp+string]
0x1800fffb0  mov     [rbp+string], r15
0x1800fffb4  mov     [r14], rax
0x1800fffb7  test    rsi, rsi
0x1800fffba  jz      short loc_1800FFFC7
0x1800fffbc  mov     rax, [rbp+var_50]
0x1800fffc0  mov     [rbp+var_50], r15
0x1800fffc4  mov     [rsi], rax
0x1800fffc7  lea     rcx, [rbp+var_40]
0x1800fffcb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fffd0  nop
0x1800fffd1  mov     rcx, [rbp+var_50]; string
0x1800fffd5  call    cs:__imp_WindowsDeleteString
0x1800fffdb  mov     [rbp+var_50], r15
0x1800fffdf  mov     rcx, [rbp+string]; string
0x1800fffe3  call    cs:__imp_WindowsDeleteString
0x1800fffe9  mov     eax, ebx
0x1800fffeb  mov     rcx, [rbp+var_8]
0x1800fffef  xor     rcx, rsp; StackCookie
0x1800ffff2  call    __security_check_cookie
0x1800ffff7  mov     rbx, [rsp+70h+arg_10]
0x1800fffff  add     rsp, 70h
0x180100003  pop     r15
0x180100005  pop     r14
0x180100007  pop     rdi
0x180100008  pop     rsi
0x180100009  pop     rbp
0x18010000a  retn
```
