# ShellMRTHelper::Common::TryFallbackToFilePath(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x1800dadbc`
- end: `0x1800db123`
- name: `?TryFallbackToFilePath@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@00PEAPEAU3@@Z`
- size: `871`
- prototype: `int(ShellMRTHelper::Common *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d258`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800c1818`
- `0x1800dadbc`
- `0x1800db12c`
- `0x1800db180`
- `0x1800eb5b8`
- `0x1801180c8`
- `0x180201e50`
- `0x18036bf1c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dae94`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dae94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dae7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dae7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800db0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800db0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daf55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dafde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800daf55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dafde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800db04f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800db04f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dae14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dae14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daeea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db0f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daeea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db0f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800dae20`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800dae20`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800dae43`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800dae43`

## string_xrefs

- `0x1800daeb5`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800daf2e`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800dafca`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800db067`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800db0d4`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800dae76`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellMRTHelper::Common::TryFallbackToFilePath(
        ShellMRTHelper::Common *this,
        HSTRING a2,
        ShellMRTHelper::Common *a3,
        HSTRING *a4)
{
  const WCHAR *StringRawBuffer; // rbx
  HSTRING v9; // rdx
  HRESULT v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, ShellMRTHelper::Common *, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  PCWSTR v22; // rbx
  HRESULT v23; // eax
  __int64 v24; // rdx
  HRESULT v25; // eax
  HSTRING v26; // [rsp+20h] [rbp-39h] BYREF
  __int64 v27; // [rsp+28h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-29h] BYREF
  UINT32 v29[2]; // [rsp+38h] [rbp-21h]
  __int64 v30; // [rsp+40h] [rbp-19h]
  UINT32 length; // [rsp+48h] [rbp-11h] BYREF
  __int64 v32; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v33[2]; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  if ( a3 )
  {
    hMem = 0;
    *(_QWORD *)v29 = 0;
    v30 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    if ( PathIsRelativeW(StringRawBuffer) && *StringRawBuffer != 64 )
    {
      v33[0] = this;
      v33[1] = a2;
      if ( PathIsURLW(StringRawBuffer) )
      {
        if ( ShellMRTHelper::Common::HasMsAppXUriScheme(a3, v9) )
        {
          v27 = 0;
          string = 0;
          v10 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
          if ( v10 < 0 )
          {
            RaiseException(v10, 1u, 0, 0);
            __debugbreak();
          }
          v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                  string,
                  &v27);
          v12 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x132,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v11,
              (int)v26);
            v13 = v27;
            if ( v27 )
            {
              v27 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
            goto LABEL_11;
          }
          v32 = 0;
          v15 = v27;
          v16 = *(__int64 (__fastcall **)(__int64, ShellMRTHelper::Common *, __int64 *))(*(_QWORD *)v27 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v17 = v16(v15, a3, &v32);
          v12 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v17,
              (int)v26);
LABEL_22:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
LABEL_29:
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&hMem);
            return v12;
          }
          v26 = 0;
          v18 = v32;
          v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 104LL);
          WindowsDeleteString(0);
          v26 = 0;
          v20 = v19(v18, &v26);
          v12 = v20;
          if ( v20 < 0 )
          {
            v21 = 313;
LABEL_21:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v20,
              (int)v26);
            WindowsDeleteString(v26);
            v26 = 0;
            goto LABEL_22;
          }
          length = 0;
          v22 = WindowsGetStringRawBuffer(v26, &length);
          if ( length > 1 )
          {
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&hMem);
            *(_QWORD *)v29 = -1;
            v30 = -1;
            v20 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v33, v22 + 1, &hMem);
            v12 = v20;
            if ( v20 < 0 )
            {
              v21 = 320;
              goto LABEL_21;
            }
          }
          WindowsDeleteString(v26);
          v26 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        }
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&hMem);
        *(_QWORD *)v29 = -1;
        v30 = -1;
        v23 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v33, StringRawBuffer, &hMem);
        v12 = v23;
        if ( v23 < 0 )
        {
          v24 = 327;
          goto LABEL_28;
        }
      }
    }
    if ( hMem && *(_WORD *)hMem )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::ReplaceChars(&hMem);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&hMem);
      v23 = WindowsCreateString((PCNZWCH)hMem, v29[0], a4);
      v12 = v23;
      if ( v23 < 0 )
      {
        v24 = 338;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v23,
          (int)v26);
        goto LABEL_29;
      }
    }
    else
    {
      v25 = WindowsDuplicateString((HSTRING)a3, a4);
      v12 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x157,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v25,
          (int)v26);
LABEL_11:
        if ( hMem )
          LocalFree(hMem);
        return v12;
      }
    }
    if ( hMem )
      LocalFree(hMem);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dadbc  mov     [rsp-8+arg_0], rbx
0x1800dadc1  mov     [rsp-8+arg_8], rsi
0x1800dadc6  push    rbp
0x1800dadc7  push    rdi
0x1800dadc8  push    r12
0x1800dadca  push    r14
0x1800dadcc  push    r15
0x1800dadce  lea     rbp, [rsp-37h]
0x1800dadd3  sub     rsp, 90h
0x1800dadda  mov     rax, cs:__security_cookie
0x1800dade1  xor     rax, rsp
0x1800dade4  mov     [rbp+57h+var_28], rax
0x1800dade8  mov     r14, r9
0x1800dadeb  mov     rsi, r8
0x1800dadee  mov     rdi, rdx
0x1800dadf1  mov     r15, rcx
0x1800dadf4  xor     r12d, r12d
0x1800dadf7  mov     [r9], r12
0x1800dadfa  test    r8, r8
0x1800dadfd  jz      loc_1800DB0F9
0x1800dae03  mov     [rbp+57h+hMem], r12
0x1800dae07  mov     qword ptr [rbp+57h+var_78], r12
0x1800dae0b  mov     [rbp+57h+var_70], r12
0x1800dae0f  xor     edx, edx; length
0x1800dae11  mov     rcx, r8; string
0x1800dae14  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dae1a  mov     rbx, rax
0x1800dae1d  mov     rcx, rax; pszPath
0x1800dae20  call    cs:__imp_PathIsRelativeW
0x1800dae26  test    eax, eax
0x1800dae28  jz      loc_1800DB01C
0x1800dae2e  cmp     word ptr [rbx], 40h ; '@'
0x1800dae32  jz      loc_1800DB01C
0x1800dae38  mov     [rbp+57h+var_58], r15
0x1800dae3c  mov     [rbp+57h+var_50], rdi
0x1800dae40  mov     rcx, rbx; pszPath
0x1800dae43  call    cs:__imp_PathIsURLW
0x1800dae49  test    eax, eax
0x1800dae4b  jz      loc_1800DB085
0x1800dae51  mov     rcx, rsi; this
0x1800dae54  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x1800dae59  test    al, al
0x1800dae5b  jz      loc_1800DB01C
0x1800dae61  mov     [rbp+57h+var_88], r12
0x1800dae65  mov     [rbp+57h+string], r12
0x1800dae69  lea     r9, [rbp+57h+string]; string
0x1800dae6d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800dae71  lea     edx, [r12+16h]; length
0x1800dae76  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800dae7d  call    cs:__imp_WindowsCreateStringReference
0x1800dae83  test    eax, eax
0x1800dae85  jns     short loc_1800DAE9B
0x1800dae87  xor     r9d, r9d; lpArguments
0x1800dae8a  xor     r8d, r8d; nNumberOfArguments
0x1800dae8d  lea     edx, [r12+1]; dwExceptionFlags
0x1800dae92  mov     ecx, eax; dwExceptionCode
0x1800dae94  call    cs:__imp_RaiseException
0x1800dae9a  int     3; Trap to Debugger
0x1800dae9b  lea     rdx, [rbp+57h+var_88]
0x1800dae9f  mov     rcx, [rbp+57h+string]
0x1800daea3  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800daea8  mov     ebx, eax
0x1800daeaa  test    eax, eax
0x1800daeac  jns     short loc_1800DAEF7
0x1800daeae  mov     rcx, [rbp+5Fh]; this
0x1800daeb2  mov     r9d, eax; char *
0x1800daeb5  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800daebc  mov     edx, 132h; void *
0x1800daec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daec6  nop
0x1800daec7  mov     rcx, [rbp+57h+var_88]
0x1800daecb  test    rcx, rcx
0x1800daece  jz      short loc_1800DAEE1
0x1800daed0  mov     [rbp+57h+var_88], r12
0x1800daed4  mov     rax, [rcx]
0x1800daed7  mov     rax, [rax+10h]
0x1800daedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daee0  nop
0x1800daee1  mov     rcx, [rbp+57h+hMem]; hMem
0x1800daee5  test    rcx, rcx
0x1800daee8  jz      short loc_1800DAEF0
0x1800daeea  call    cs:__imp_LocalFree
0x1800daef0  mov     eax, ebx
0x1800daef2  jmp     loc_1800DB0FB
0x1800daef7  mov     [rbp+57h+var_60], r12
0x1800daefb  mov     rdi, [rbp+57h+var_88]
0x1800daeff  mov     rax, [rdi]
0x1800daf02  mov     rbx, [rax+30h]
0x1800daf06  lea     rcx, [rbp+57h+var_60]
0x1800daf0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800daf0f  lea     r8, [rbp+57h+var_60]
0x1800daf13  mov     rdx, rsi
0x1800daf16  mov     rcx, rdi
0x1800daf19  mov     rax, rbx
0x1800daf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf21  mov     ebx, eax
0x1800daf23  test    eax, eax
0x1800daf25  jns     short loc_1800DAF44
0x1800daf27  mov     rcx, [rbp+5Fh]; this
0x1800daf2b  mov     r9d, eax; char *
0x1800daf2e  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800daf35  mov     edx, 135h; void *
0x1800daf3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daf3f  jmp     loc_1800DAFE8
0x1800daf44  mov     [rbp+57h+var_90], r12
0x1800daf48  mov     rdi, [rbp+57h+var_60]
0x1800daf4c  mov     rax, [rdi]
0x1800daf4f  mov     rbx, [rax+68h]
0x1800daf53  xor     ecx, ecx; string
0x1800daf55  call    cs:__imp_WindowsDeleteString
0x1800daf5b  mov     [rbp+57h+var_90], r12
0x1800daf5f  lea     rdx, [rbp+57h+var_90]
0x1800daf63  mov     rcx, rdi
0x1800daf66  mov     rax, rbx
0x1800daf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf6e  mov     ebx, eax
0x1800daf70  test    eax, eax
0x1800daf72  jns     short loc_1800DAF7B
0x1800daf74  mov     edx, 139h
0x1800daf79  jmp     short loc_1800DAFC7
0x1800daf7b  mov     [rbp+57h+length], r12d
0x1800daf7f  lea     rdx, [rbp+57h+length]; length
0x1800daf83  mov     rcx, [rbp+57h+var_90]; string
0x1800daf87  call    cs:__imp_WindowsGetStringRawBuffer
0x1800daf8d  mov     rbx, rax
0x1800daf90  cmp     [rbp+57h+length], 1
0x1800daf94  jbe     short loc_1800DAFFC
0x1800daf96  lea     rcx, [rbp+57h+hMem]
0x1800daf9a  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800daf9f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800dafa3  mov     qword ptr [rbp+57h+var_78], rcx
0x1800dafa7  mov     [rbp+57h+var_70], rcx
0x1800dafab  lea     rdx, [rbx+2]
0x1800dafaf  lea     r8, [rbp+57h+hMem]
0x1800dafb3  lea     rcx, [rbp+57h+var_58]
0x1800dafb7  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x1800dafbc  mov     ebx, eax
0x1800dafbe  test    eax, eax
0x1800dafc0  jns     short loc_1800DAFFC
0x1800dafc2  mov     edx, 140h; void *
0x1800dafc7  mov     r9d, eax; char *
0x1800dafca  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800dafd1  mov     rcx, [rbp+5Fh]; this
0x1800dafd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dafda  mov     rcx, [rbp+57h+var_90]; string
0x1800dafde  call    cs:__imp_WindowsDeleteString
0x1800dafe4  mov     [rbp+57h+var_90], r12
0x1800dafe8  lea     rcx, [rbp+57h+var_60]
0x1800dafec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800daff1  lea     rcx, [rbp+57h+var_88]
0x1800daff5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800daffa  jmp     short loc_1800DB077
0x1800daffc  mov     rcx, [rbp+57h+var_90]; string
0x1800db000  call    cs:__imp_WindowsDeleteString
0x1800db006  mov     [rbp+57h+var_90], r12
0x1800db00a  lea     rcx, [rbp+57h+var_60]
0x1800db00e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db013  lea     rcx, [rbp+57h+var_88]
0x1800db017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db01c  mov     rax, [rbp+57h+hMem]
0x1800db020  test    rax, rax
0x1800db023  jz      loc_1800DB0BB
0x1800db029  cmp     [rax], r12w
0x1800db02d  jz      loc_1800DB0BB
0x1800db033  lea     rcx, [rbp+57h+hMem]
0x1800db037  call    ?ReplaceChars@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAXGG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::ReplaceChars(ushort,ushort)
0x1800db03c  lea     rcx, [rbp+57h+hMem]
0x1800db040  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1800db045  mov     r8, r14; string
0x1800db048  mov     edx, [rbp+57h+var_78]; length
0x1800db04b  mov     rcx, [rbp+57h+hMem]; sourceString
0x1800db04f  call    cs:__imp_WindowsCreateString
0x1800db055  mov     ebx, eax
0x1800db057  test    eax, eax
0x1800db059  jns     loc_1800DB0EA
0x1800db05f  mov     edx, 152h; void *
0x1800db064  mov     r9d, eax; char *
0x1800db067  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800db06e  mov     rcx, [rbp+5Fh]; this
0x1800db072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db077  lea     rcx, [rbp+57h+hMem]
0x1800db07b  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800db080  jmp     loc_1800DAEF0
0x1800db085  lea     rcx, [rbp+57h+hMem]
0x1800db089  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800db08e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800db092  mov     qword ptr [rbp+57h+var_78], rcx
0x1800db096  mov     [rbp+57h+var_70], rcx
0x1800db09a  lea     r8, [rbp+57h+hMem]
0x1800db09e  mov     rdx, rbx
0x1800db0a1  lea     rcx, [rbp+57h+var_58]
0x1800db0a5  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x1800db0aa  mov     ebx, eax
0x1800db0ac  test    eax, eax
0x1800db0ae  jns     loc_1800DB01C
0x1800db0b4  mov     edx, 147h
0x1800db0b9  jmp     short loc_1800DB064
0x1800db0bb  mov     rdx, r14; newString
0x1800db0be  mov     rcx, rsi; string
0x1800db0c1  call    cs:__imp_WindowsDuplicateString
0x1800db0c7  mov     ebx, eax
0x1800db0c9  test    eax, eax
0x1800db0cb  jns     short loc_1800DB0EA
0x1800db0cd  mov     rcx, [rbp+5Fh]; this
0x1800db0d1  mov     r9d, eax; char *
0x1800db0d4  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800db0db  mov     edx, 157h; void *
0x1800db0e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db0e5  jmp     loc_1800DAEE1
0x1800db0ea  mov     rcx, [rbp+57h+hMem]; hMem
0x1800db0ee  test    rcx, rcx
0x1800db0f1  jz      short loc_1800DB0F9
0x1800db0f3  call    cs:__imp_LocalFree
0x1800db0f9  xor     eax, eax
0x1800db0fb  mov     rcx, [rbp+57h+var_28]
0x1800db0ff  xor     rcx, rsp; StackCookie
0x1800db102  call    __security_check_cookie
0x1800db107  lea     r11, [rsp+0B0h+var_20]
0x1800db10f  mov     rbx, [r11+30h]
0x1800db113  mov     rsi, [r11+38h]
0x1800db117  mov     rsp, r11
0x1800db11a  pop     r15
0x1800db11c  pop     r14
0x1800db11e  pop     r12
0x1800db120  pop     rdi
0x1800db121  pop     rbp
0x1800db122  retn
```
