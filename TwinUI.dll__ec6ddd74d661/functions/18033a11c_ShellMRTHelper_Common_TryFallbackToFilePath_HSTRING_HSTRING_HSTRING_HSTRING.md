# ShellMRTHelper::Common::TryFallbackToFilePath(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x18033a11c`
- end: `0x18033a481`
- name: `?TryFallbackToFilePath@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@00PEAPEAU3@@Z`
- size: `869`
- prototype: `int(ShellMRTHelper::Common *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c44`
- `0x18013d040`

## callees

- `0x180009dd0`
- `0x18000b370`
- `0x18001c710`
- `0x1800378dc`
- `0x1800416a0`
- `0x1800ba13c`
- `0x18010c864`
- `0x180113cf0`
- `0x180142e10`
- `0x18033a11c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18033a1af`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18033a1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033a343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033a416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033a416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18033a3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18033a3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033a174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033a2bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033a174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033a2bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18033a186`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18033a186`

## string_xrefs

- `0x18033a20f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18033a25c`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18033a304`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18033a430`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18033a1e5`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::TryFallbackToFilePath(
        ShellMRTHelper::Common *this,
        HSTRING a2,
        ShellMRTHelper::Common *a3,
        HSTRING *a4)
{
  const WCHAR *StringRawBuffer; // rbx
  HSTRING v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, ShellMRTHelper::Common *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  PCWSTR v19; // rbx
  unsigned __int64 v20; // rcx
  unsigned __int64 i; // rax
  HRESULT v22; // eax
  __int64 v23; // rdx
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  __int64 v26; // [rsp+28h] [rbp-31h] BYREF
  PCNZWCH sourceString; // [rsp+30h] [rbp-29h] BYREF
  UINT32 v28[2]; // [rsp+38h] [rbp-21h]
  __int64 v29; // [rsp+40h] [rbp-19h]
  UINT32 length; // [rsp+48h] [rbp-11h] BYREF
  __int64 v31; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  if ( a3 )
  {
    sourceString = 0;
    *(_QWORD *)v28 = 0;
    v29 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    if ( PathIsRelativeW(StringRawBuffer) && *StringRawBuffer != 64 )
    {
      v32[0] = this;
      v32[1] = a2;
      if ( PathIsURLW(StringRawBuffer) )
      {
        if ( ShellMRTHelper::Common::HasMsAppXUriScheme(a3, v9) )
        {
          v31 = 0;
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Foundation.Uri",
            0x17u,
            0x16u);
          v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                  v34,
                  &v31);
          v11 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x132,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v10,
              (int)string);
LABEL_17:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
LABEL_32:
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
            return v11;
          }
          v26 = 0;
          v12 = v31;
          v13 = *(__int64 (__fastcall **)(__int64, ShellMRTHelper::Common *, __int64 *))(*(_QWORD *)v31 + 48LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v26);
          v14 = v13(v12, a3, &v26);
          v11 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v14,
              (int)string);
LABEL_16:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v26);
            goto LABEL_17;
          }
          string = 0;
          v15 = v26;
          v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 104LL);
          WindowsDeleteString(0);
          string = 0;
          v17 = v16(v15, &string);
          v11 = v17;
          if ( v17 < 0 )
          {
            v18 = 313;
LABEL_15:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v17,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_16;
          }
          length = 0;
          v19 = WindowsGetStringRawBuffer(string, &length);
          if ( length > 1 )
          {
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
            *(_QWORD *)v28 = -1;
            v29 = -1;
            v17 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v32, v19 + 1, &sourceString);
            v11 = v17;
            if ( v17 < 0 )
            {
              v18 = 320;
              goto LABEL_15;
            }
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v26);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
        }
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
        *(_QWORD *)v28 = -1;
        v29 = -1;
        v22 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v32, StringRawBuffer, &sourceString);
        v11 = v22;
        if ( v22 < 0 )
        {
          v23 = 327;
          goto LABEL_31;
        }
      }
    }
    if ( sourceString && *sourceString )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v20 = 0;
      for ( i = *(_QWORD *)v28; v20 < i; ++v20 )
      {
        if ( sourceString[v20] == 47 )
        {
          sourceString[v20] = 92;
          i = *(_QWORD *)v28;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v22 = WindowsCreateString(sourceString, v28[0], a4);
      v11 = v22;
      if ( v22 < 0 )
      {
        v23 = 338;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v22,
          (int)string);
        goto LABEL_32;
      }
    }
    else
    {
      v22 = WindowsDuplicateString((HSTRING)a3, a4);
      v11 = v22;
      if ( v22 < 0 )
      {
        v23 = 343;
        goto LABEL_31;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
  }
  return 0;
}

```

## disassembly

```asm
0x18033a11c  mov     [rsp-8+arg_0], rbx
0x18033a121  mov     [rsp-8+arg_8], rsi
0x18033a126  push    rbp
0x18033a127  push    rdi
0x18033a128  push    r12
0x18033a12a  push    r14
0x18033a12c  push    r15
0x18033a12e  lea     rbp, [rsp-37h]
0x18033a133  sub     rsp, 90h
0x18033a13a  mov     rax, cs:__security_cookie
0x18033a141  xor     rax, rsp
0x18033a144  mov     [rbp+57h+var_28], rax
0x18033a148  mov     r14, r9
0x18033a14b  mov     rsi, r8
0x18033a14e  mov     rdi, rdx
0x18033a151  mov     r15, rcx
0x18033a154  xor     r12d, r12d
0x18033a157  mov     [r9], r12
0x18033a15a  test    r8, r8
0x18033a15d  jz      loc_18033A456
0x18033a163  mov     [rbp+57h+sourceString], r12
0x18033a167  mov     qword ptr [rbp+57h+var_78], r12
0x18033a16b  mov     [rbp+57h+var_70], r12
0x18033a16f  xor     edx, edx; length
0x18033a171  mov     rcx, r8; string
0x18033a174  call    cs:__imp_WindowsGetStringRawBuffer
0x18033a17b  nop     dword ptr [rax+rax+00h]
0x18033a180  mov     rbx, rax
0x18033a183  mov     rcx, rax; pszPath
0x18033a186  call    cs:__imp_PathIsRelativeW
0x18033a18d  nop     dword ptr [rax+rax+00h]
0x18033a192  test    eax, eax
0x18033a194  jz      loc_18033A365
0x18033a19a  cmp     word ptr [rbx], 40h ; '@'
0x18033a19e  jz      loc_18033A365
0x18033a1a4  mov     [rbp+57h+var_58], r15
0x18033a1a8  mov     [rbp+57h+var_50], rdi
0x18033a1ac  mov     rcx, rbx; pszPath
0x18033a1af  call    cs:__imp_PathIsURLW
0x18033a1b6  nop     dword ptr [rax+rax+00h]
0x18033a1bb  test    eax, eax
0x18033a1bd  jz      loc_18033A3DA
0x18033a1c3  mov     rcx, rsi; this
0x18033a1c6  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x18033a1cb  test    al, al
0x18033a1cd  jz      loc_18033A365
0x18033a1d3  mov     [rbp+57h+var_60], r12
0x18033a1d7  mov     [rbp+57h+var_30], r12
0x18033a1db  lea     r9d, [r12+16h]; unsigned int
0x18033a1e0  lea     r8d, [r12+17h]; unsigned int
0x18033a1e5  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18033a1ec  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18033a1f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033a1f5  lea     rdx, [rbp+57h+var_60]
0x18033a1f9  mov     rcx, [rbp+57h+var_30]
0x18033a1fd  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18033a202  mov     ebx, eax
0x18033a204  test    eax, eax
0x18033a206  jns     short loc_18033A225
0x18033a208  mov     rcx, [rbp+5Fh]; this
0x18033a20c  mov     r9d, eax; char *
0x18033a20f  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18033a216  mov     edx, 132h; void *
0x18033a21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a220  jmp     loc_18033A331
0x18033a225  mov     [rbp+57h+var_88], r12
0x18033a229  mov     rdi, [rbp+57h+var_60]
0x18033a22d  mov     rax, [rdi]
0x18033a230  mov     rbx, [rax+30h]
0x18033a234  lea     rcx, [rbp+57h+var_88]
0x18033a238  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033a23d  lea     r8, [rbp+57h+var_88]
0x18033a241  mov     rdx, rsi
0x18033a244  mov     rcx, rdi
0x18033a247  mov     rax, rbx
0x18033a24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033a24f  mov     ebx, eax
0x18033a251  test    eax, eax
0x18033a253  jns     short loc_18033A272
0x18033a255  mov     rcx, [rbp+5Fh]; this
0x18033a259  mov     r9d, eax; char *
0x18033a25c  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18033a263  mov     edx, 135h; void *
0x18033a268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a26d  jmp     loc_18033A328
0x18033a272  mov     [rbp+57h+string], r12
0x18033a276  mov     rdi, [rbp+57h+var_88]
0x18033a27a  mov     rax, [rdi]
0x18033a27d  mov     rbx, [rax+68h]
0x18033a281  xor     ecx, ecx; string
0x18033a283  call    cs:__imp_WindowsDeleteString
0x18033a28a  nop     dword ptr [rax+rax+00h]
0x18033a28f  mov     [rbp+57h+string], r12
0x18033a293  lea     rdx, [rbp+57h+string]
0x18033a297  mov     rcx, rdi
0x18033a29a  mov     rax, rbx
0x18033a29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033a2a2  mov     ebx, eax
0x18033a2a4  test    eax, eax
0x18033a2a6  jns     short loc_18033A2AF
0x18033a2a8  mov     edx, 139h
0x18033a2ad  jmp     short loc_18033A301
0x18033a2af  mov     [rbp+57h+length], r12d
0x18033a2b3  lea     rdx, [rbp+57h+length]; length
0x18033a2b7  mov     rcx, [rbp+57h+string]; string
0x18033a2bb  call    cs:__imp_WindowsGetStringRawBuffer
0x18033a2c2  nop     dword ptr [rax+rax+00h]
0x18033a2c7  mov     rbx, rax
0x18033a2ca  cmp     [rbp+57h+length], 1
0x18033a2ce  jbe     short loc_18033A33F
0x18033a2d0  lea     rcx, [rbp+57h+sourceString]
0x18033a2d4  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18033a2d9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18033a2dd  mov     qword ptr [rbp+57h+var_78], rcx
0x18033a2e1  mov     [rbp+57h+var_70], rcx
0x18033a2e5  lea     rdx, [rbx+2]
0x18033a2e9  lea     r8, [rbp+57h+sourceString]
0x18033a2ed  lea     rcx, [rbp+57h+var_58]
0x18033a2f1  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x18033a2f6  mov     ebx, eax
0x18033a2f8  test    eax, eax
0x18033a2fa  jns     short loc_18033A33F
0x18033a2fc  mov     edx, 140h; void *
0x18033a301  mov     r9d, eax; char *
0x18033a304  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18033a30b  mov     rcx, [rbp+5Fh]; this
0x18033a30f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a314  mov     rcx, [rbp+57h+string]; string
0x18033a318  call    cs:__imp_WindowsDeleteString
0x18033a31f  nop     dword ptr [rax+rax+00h]
0x18033a324  mov     [rbp+57h+string], r12
0x18033a328  lea     rcx, [rbp+57h+var_88]
0x18033a32c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033a331  lea     rcx, [rbp+57h+var_60]
0x18033a335  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033a33a  jmp     loc_18033A440
0x18033a33f  mov     rcx, [rbp+57h+string]; string
0x18033a343  call    cs:__imp_WindowsDeleteString
0x18033a34a  nop     dword ptr [rax+rax+00h]
0x18033a34f  mov     [rbp+57h+string], r12
0x18033a353  lea     rcx, [rbp+57h+var_88]
0x18033a357  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033a35c  lea     rcx, [rbp+57h+var_60]
0x18033a360  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033a365  mov     rax, [rbp+57h+sourceString]
0x18033a369  test    rax, rax
0x18033a36c  jz      loc_18033A410
0x18033a372  cmp     [rax], r12w
0x18033a376  jz      loc_18033A410
0x18033a37c  lea     rcx, [rbp+57h+sourceString]
0x18033a380  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18033a385  mov     rcx, r12
0x18033a388  mov     rax, qword ptr [rbp+57h+var_78]
0x18033a38c  test    rax, rax
0x18033a38f  jz      short loc_18033A3AE
0x18033a391  mov     rdx, [rbp+57h+sourceString]
0x18033a395  cmp     word ptr [rdx+rcx*2], 2Fh ; '/'
0x18033a39a  jnz     short loc_18033A3A6
0x18033a39c  mov     word ptr [rdx+rcx*2], 5Ch ; '\'
0x18033a3a2  mov     rax, qword ptr [rbp+57h+var_78]
0x18033a3a6  inc     rcx
0x18033a3a9  cmp     rcx, rax
0x18033a3ac  jb      short loc_18033A391
0x18033a3ae  lea     rcx, [rbp+57h+sourceString]
0x18033a3b2  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18033a3b7  mov     r8, r14; string
0x18033a3ba  mov     edx, [rbp+57h+var_78]; length
0x18033a3bd  mov     rcx, [rbp+57h+sourceString]; sourceString
0x18033a3c1  call    cs:__imp_WindowsCreateString
0x18033a3c8  nop     dword ptr [rax+rax+00h]
0x18033a3cd  mov     ebx, eax
0x18033a3cf  test    eax, eax
0x18033a3d1  jns     short loc_18033A44D
0x18033a3d3  mov     edx, 152h
0x18033a3d8  jmp     short loc_18033A42D
0x18033a3da  lea     rcx, [rbp+57h+sourceString]
0x18033a3de  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18033a3e3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18033a3e7  mov     qword ptr [rbp+57h+var_78], rcx
0x18033a3eb  mov     [rbp+57h+var_70], rcx
0x18033a3ef  lea     r8, [rbp+57h+sourceString]
0x18033a3f3  mov     rdx, rbx
0x18033a3f6  lea     rcx, [rbp+57h+var_58]
0x18033a3fa  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x18033a3ff  mov     ebx, eax
0x18033a401  test    eax, eax
0x18033a403  jns     loc_18033A365
0x18033a409  mov     edx, 147h
0x18033a40e  jmp     short loc_18033A42D
0x18033a410  mov     rdx, r14; newString
0x18033a413  mov     rcx, rsi; string
0x18033a416  call    cs:__imp_WindowsDuplicateString
0x18033a41d  nop     dword ptr [rax+rax+00h]
0x18033a422  mov     ebx, eax
0x18033a424  test    eax, eax
0x18033a426  jns     short loc_18033A44D
0x18033a428  mov     edx, 157h; void *
0x18033a42d  mov     r9d, eax; char *
0x18033a430  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18033a437  mov     rcx, [rbp+5Fh]; this
0x18033a43b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a440  lea     rcx, [rbp+57h+sourceString]
0x18033a444  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18033a449  mov     eax, ebx
0x18033a44b  jmp     short loc_18033A458
0x18033a44d  lea     rcx, [rbp+57h+sourceString]
0x18033a451  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18033a456  xor     eax, eax
0x18033a458  mov     rcx, [rbp+57h+var_28]
0x18033a45c  xor     rcx, rsp; StackCookie
0x18033a45f  call    __security_check_cookie
0x18033a464  lea     r11, [rsp+0B0h+var_20]
0x18033a46c  mov     rbx, [r11+30h]
0x18033a470  mov     rsi, [r11+38h]
0x18033a474  mov     rsp, r11
0x18033a477  pop     r15
0x18033a479  pop     r14
0x18033a47b  pop     r12
0x18033a47d  pop     rdi
0x18033a47e  pop     rbp
0x18033a47f  retn
```
