# ShellMRTHelper::MRTHelperBase::Resolve(ShellMRTHelper::MRTHelperBase::MRTResolutionType,ushort const *,ushort * *)

- ea: `0x18013d040`
- end: `0x18013d75c`
- name: `?Resolve@MRTHelperBase@ShellMRTHelper@@AEAAJW4MRTResolutionType@12@PEBGPEAPEAG@Z`
- size: `1820`
- prototype: `int __high(enum ShellMRTHelper::MRTHelperBase::MRTResolutionType, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180336124`

## callees

- `0x180009dfc`
- `0x18000a850`
- `0x18000e2b0`
- `0x18000e498`
- `0x1800378dc`
- `0x180037b9c`
- `0x1800416a0`
- `0x180041f54`
- `0x180053740`
- `0x180055268`
- `0x1800ba13c`
- `0x180106af8`
- `0x18010c7c0`
- `0x18010c864`
- `0x18013d040`
- `0x180142e10`
- `0x180334280`
- `0x180334340`
- `0x18033a11c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013d225`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013d225`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18013d12f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18013d12f`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18013d39d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18013d39d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d608`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d6fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d608`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013d6fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d6cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d6cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013d4fb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013d4fb`

## string_xrefs

- `0x18013d14b`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d184`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d1f0`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d257`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d367`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d3b7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d42d`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d5dc`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18013d68f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ShellMRTHelper::MRTHelperBase::Resolve(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  HSTRING v7; // rdx
  HSTRING v8; // rdx
  bool HasFileUriScheme; // di
  const WCHAR *v10; // r13
  int v11; // eax
  unsigned int v12; // ebx
  HRESULT v13; // eax
  int v14; // eax
  __int64 v15; // rax
  wchar_t *v16; // rax
  signed int v17; // ebx
  wchar_t *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, GUID *, UINT32 *); // rbx
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, HSTRING *); // rbx
  HSTRING v27; // rdi
  __int64 (__fastcall *v28)(HSTRING, int *); // rbx
  HRESULT v29; // eax
  signed int v30; // eax
  unsigned __int16 **v31; // r8
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, HSTRING, int *); // rbx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64, int *); // rbx
  HRESULT Instance; // eax
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  HSTRING v40; // rdi
  __int64 (__fastcall *v41)(HSTRING, __int64, int *); // rbx
  HSTRING v42; // rdi
  __int64 (__fastcall *v43)(HSTRING, __int64, const WCHAR *, _QWORD); // rbx
  const WCHAR *v44; // r8
  ShellMRTHelper::Common *v45; // rdi
  __int64 v46; // rcx
  const WCHAR *v47; // rdx
  HSTRING v48; // rbx
  __int64 v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v54; // rax
  int *ppv; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  int v58[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h]
  __int64 v60; // [rsp+48h] [rbp-B8h]
  UINT32 length[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszPathOut; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h]
  __int64 v65; // [rsp+70h] [rbp-90h]
  _BYTE v66[24]; // [rsp+80h] [rbp-80h] BYREF
  ShellMRTHelper::Common *v67; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER v69; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v62 = a3;
  *a4 = 0;
  *(_QWORD *)v58 = 0;
  v59 = 0;
  v60 = 0;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v66, &v62);
  HasFileUriScheme = ShellMRTHelper::Common::HasFileUriScheme(v67, v7);
  v10 = &pszDefault;
  if ( HasFileUriScheme || ShellMRTHelper::Common::HasMsAppDataUriScheme(v67, v8) )
  {
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    Instance = CoCreateInstance(
                 &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
                 0,
                 1u,
                 &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
                 (LPVOID *)&string);
    v17 = Instance;
    v38 = retaddr;
    if ( Instance >= 0 )
    {
      if ( HasFileUriScheme )
      {
        v40 = string;
        v41 = *(__int64 (__fastcall **)(HSTRING, __int64, int *))(*(_QWORD *)string + 56LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
        v59 = -1;
        v60 = -1;
        Instance = v41(v40, a3, v58);
        v17 = Instance;
        v38 = retaddr;
        if ( Instance >= 0 )
        {
LABEL_57:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          goto LABEL_58;
        }
        v39 = 285;
      }
      else
      {
        if ( !*(_BYTE *)(a1 + 45) )
        {
          v17 = -2147024809;
          goto LABEL_57;
        }
        v42 = string;
        v43 = *(__int64 (__fastcall **)(HSTRING, __int64, const WCHAR *, _QWORD))(*(_QWORD *)string + 48LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
        v59 = -1;
        v60 = -1;
        v44 = &pszDefault;
        if ( *(_QWORD *)(a1 + 48) )
          v44 = *(const WCHAR **)(a1 + 48);
        ppv = v58;
        Instance = v43(v42, a3, v44, 0);
        v17 = Instance;
        v38 = retaddr;
        if ( Instance >= 0 )
          goto LABEL_57;
        v39 = 291;
      }
    }
    else
    {
      v39 = 281;
    }
    wil::details::in1diag3::_Log_Hr(
      v38,
      (void *)v39,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)Instance,
      (int)ppv);
    goto LABEL_57;
  }
  v11 = ShellMRTHelper::MRTHelperBase::InitializeMRTObjects((ShellMRTHelper::MRTHelperBase *)a1);
  v12 = v11;
  if ( *(_BYTE *)(a1 + 46) && ((unsigned int)(v11 + 2147024894) <= 1 || v11 == -2147023728) )
  {
    ppszPathOut = 0;
    v64 = 0;
    v65 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&ppszPathOut);
    v64 = -1;
    v65 = -1;
    v13 = PathAllocCombine(*(PCWSTR *)(a1 + 72), (PCWSTR)a3, 0, &ppszPathOut);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v58,
              ppszPathOut,
              -1);
      v12 = v14;
      if ( v14 >= 0 )
      {
        v15 = *(_QWORD *)v58;
        *(_QWORD *)v58 = 0;
        v60 = 0;
        v59 = 0;
        *a4 = v15;
        v12 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v14,
          (int)ppv);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
        (const char *)(unsigned int)v13,
        (int)ppv);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&ppszPathOut);
    goto LABEL_70;
  }
  if ( v11 >= 0 )
  {
    if ( *(_WORD *)a3 == 64 )
    {
      if ( *(_WORD *)(a3 + 2) == 123 )
      {
        v16 = wcschr((const wchar_t *)a3, 0x3Fu);
        v17 = v16 == 0 ? 0x8000FFFF : 0;
        if ( v16 )
        {
          v18 = v16 + 1;
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v58,
                  v18,
                  v19 - 1);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v17,
            (int)ppv);
        }
        *(_QWORD *)length = 0;
        string = 0;
        if ( v17 < 0 )
          goto LABEL_32;
        v20 = *(_QWORD *)(a1 + 8);
        v21 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, UINT32 *))(*(_QWORD *)v20 + 88LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
        v22 = v21(v20, *(_QWORD *)v58, &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2, length);
        v17 = v22;
        v23 = retaddr;
        if ( v22 >= 0 )
        {
          v25 = *(_QWORD *)length;
          v26 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(**(_QWORD **)length + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          v22 = v26(v25, *(_QWORD *)(a1 + 16), &string);
          v17 = v22;
          v23 = retaddr;
          if ( v22 >= 0 )
          {
            v27 = string;
            v28 = *(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)string + 32LL);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
            v59 = -1;
            v60 = -1;
            v22 = v28(v27, v58);
            v17 = v22;
            v23 = retaddr;
            if ( v22 >= 0 )
            {
LABEL_32:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
              goto LABEL_58;
            }
            v24 = 357;
          }
          else
          {
            v24 = 346;
          }
        }
        else
        {
          v24 = 341;
        }
        wil::details::in1diag3::_Log_Hr(
          v23,
          (void *)v24,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v22,
          (int)ppv);
        goto LABEL_32;
      }
      v29 = SHLoadIndirectString((PCWSTR)a3, pszOutBuf, 0x104u, 0);
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v29,
          (int)ppv);
LABEL_59:
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v45 = *(ShellMRTHelper::Common **)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                             &ppszPathOut,
                                             &v62)
                                         + 24);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(a1 + 48);
        v47 = &pszDefault;
        if ( *(_QWORD *)v46 )
          v47 = *(const WCHAR **)v46;
        v48 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                             &hstringHeader,
                             v47,
                             *(_DWORD *)(v46 + 8))
                         + 24);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(a1 + 72);
        if ( *(_QWORD *)v49 )
          v10 = *(const WCHAR **)v49;
        v50 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v69, v10, *(_DWORD *)(v49 + 8));
        v51 = ShellMRTHelper::Common::TryFallbackToFilePath(*(ShellMRTHelper::Common **)(v50 + 24), v48, v45, &string);
        v12 = v51;
        if ( v51 < 0 )
        {
          v52 = 457;
LABEL_65:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v51,
            (int)ppv);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_70;
        }
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, length);
        v51 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v58,
                StringRawBuffer,
                length[0]);
        v12 = v51;
        if ( v51 < 0 )
        {
          v52 = 461;
          goto LABEL_65;
        }
        WindowsDeleteString(string);
LABEL_69:
        v54 = *(_QWORD *)v58;
        *(_QWORD *)v58 = 0;
        v60 = 0;
        v59 = 0;
        *a4 = v54;
        v12 = 0;
        goto LABEL_70;
      }
      v30 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v58,
              pszOutBuf,
              -1);
    }
    else
    {
      if ( *(_BYTE *)(a1 + 45) && ShellMRTHelper::Common::HasMsAppXUriScheme(v67, (HSTRING)0x80070490LL) )
      {
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &string,
          0);
        v32 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(v67, (HSTRING)&string, v31);
        v17 = v32;
        if ( v32 >= 0 )
        {
          v33 = *(_QWORD *)(a1 + 8);
          v34 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, int *))(*(_QWORD *)v33 + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
          v59 = -1;
          v60 = -1;
          v17 = v34(v33, *(_QWORD *)(a1 + 16), string, v58);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19B,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v32,
            (int)ppv);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&string);
LABEL_58:
        if ( v17 >= 0 )
          goto LABEL_69;
        goto LABEL_59;
      }
      v35 = *(_QWORD *)(a1 + 8);
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)v35 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
      v59 = -1;
      v60 = -1;
      v30 = v36(v35, *(_QWORD *)(a1 + 16), a3, v58);
    }
    v17 = v30;
    goto LABEL_58;
  }
  if ( v11 != -2147024891 && (unsigned int)(v11 + 2147024894) > 1 && v11 != -2147023728 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)v11,
      (int)ppv);
LABEL_70:
  v67 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v58);
  return v12;
}

```

## disassembly

```asm
0x18013d040  mov     [rsp-8+arg_8], rbx
0x18013d045  push    rbp
0x18013d046  push    rsi
0x18013d047  push    rdi
0x18013d048  push    r12
0x18013d04a  push    r13
0x18013d04c  push    r14
0x18013d04e  push    r15
0x18013d050  lea     rbp, [rsp-200h]
0x18013d058  sub     rsp, 300h
0x18013d05f  mov     rax, cs:__security_cookie
0x18013d066  xor     rax, rsp
0x18013d069  mov     [rbp+230h+var_40], rax
0x18013d070  mov     r12, r9
0x18013d073  mov     r15, r8
0x18013d076  mov     r14, rcx
0x18013d079  mov     [rsp+330h+var_2D8], r8
0x18013d07e  xor     esi, esi
0x18013d080  mov     [r9], rsi
0x18013d083  mov     qword ptr [rsp+330h+var_2F8], rsi
0x18013d088  mov     [rsp+330h+var_2F0], rsi
0x18013d08d  mov     [rsp+330h+var_2E8], rsi
0x18013d092  lea     rdx, [rsp+330h+var_2D8]
0x18013d097  lea     rcx, [rbp+230h+var_2B0]
0x18013d09b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18013d0a0  nop
0x18013d0a1  mov     rcx, [rbp+230h+var_298]; this
0x18013d0a5  call    ?HasFileUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasFileUriScheme(HSTRING__ *)
0x18013d0aa  mov     dil, al
0x18013d0ad  lea     r13, pszDefault
0x18013d0b4  test    al, al
0x18013d0b6  jnz     loc_18013D4CE
0x18013d0bc  mov     rcx, [rbp+230h+var_298]; this
0x18013d0c0  call    ?HasMsAppDataUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppDataUriScheme(HSTRING__ *)
0x18013d0c5  test    al, al
0x18013d0c7  jnz     loc_18013D4CE
0x18013d0cd  mov     rcx, r14; this
0x18013d0d0  call    ?InitializeMRTObjects@MRTHelperBase@ShellMRTHelper@@AEAAJXZ; ShellMRTHelper::MRTHelperBase::InitializeMRTObjects(void)
0x18013d0d5  mov     ebx, eax
0x18013d0d7  mov     edx, 80070490h; HSTRING
0x18013d0dc  cmp     [r14+2Eh], sil
0x18013d0e0  jz      loc_18013D1C0
0x18013d0e6  lea     ecx, [rax+7FF8FFFEh]
0x18013d0ec  cmp     ecx, 1
0x18013d0ef  jbe     short loc_18013D0F9
0x18013d0f1  cmp     eax, edx
0x18013d0f3  jnz     loc_18013D1C0
0x18013d0f9  mov     [rsp+330h+ppszPathOut], rsi
0x18013d0fe  mov     [rsp+330h+var_2C8], rsi
0x18013d103  mov     [rsp+330h+var_2C0], rsi
0x18013d108  lea     rcx, [rsp+330h+ppszPathOut]
0x18013d10d  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18013d112  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18013d116  mov     [rsp+330h+var_2C8], rsi
0x18013d11b  mov     [rsp+330h+var_2C0], rsi
0x18013d120  lea     r9, [rsp+330h+ppszPathOut]; ppszPathOut
0x18013d125  xor     r8d, r8d; dwFlags
0x18013d128  mov     rdx, r15; pszMore
0x18013d12b  mov     rcx, [r14+48h]; pszPathIn
0x18013d12f  call    cs:__imp_PathAllocCombine
0x18013d136  nop     dword ptr [rax+rax+00h]
0x18013d13b  mov     ebx, eax
0x18013d13d  test    eax, eax
0x18013d13f  jns     short loc_18013D160
0x18013d141  mov     rcx, [rbp+238h]; this
0x18013d148  mov     r9d, eax; char *
0x18013d14b  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d152  mov     edx, 139h; void *
0x18013d157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d15c  xor     esi, esi
0x18013d15e  jmp     short loc_18013D1B1
0x18013d160  mov     r8, rsi
0x18013d163  mov     rdx, [rsp+330h+ppszPathOut]
0x18013d168  lea     rcx, [rsp+330h+var_2F8]
0x18013d16d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18013d172  mov     ebx, eax
0x18013d174  xor     esi, esi
0x18013d176  test    eax, eax
0x18013d178  jns     short loc_18013D197
0x18013d17a  mov     rcx, [rbp+238h]; this
0x18013d181  mov     r9d, eax; char *
0x18013d184  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d18b  mov     edx, 13Ah; void *
0x18013d190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d195  jmp     short loc_18013D1B1
0x18013d197  mov     rax, qword ptr [rsp+330h+var_2F8]
0x18013d19c  mov     qword ptr [rsp+330h+var_2F8], rsi
0x18013d1a1  mov     [rsp+330h+var_2E8], rsi
0x18013d1a6  mov     [rsp+330h+var_2F0], rsi
0x18013d1ab  mov     [r12], rax
0x18013d1af  mov     ebx, esi
0x18013d1b1  lea     rcx, [rsp+330h+ppszPathOut]
0x18013d1b6  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18013d1bb  jmp     loc_18013D721
0x18013d1c0  test    ebx, ebx
0x18013d1c2  jns     short loc_18013D206
0x18013d1c4  cmp     ebx, 80070005h
0x18013d1ca  jz      loc_18013D721
0x18013d1d0  add     eax, 7FF8FFFEh
0x18013d1d5  cmp     eax, 1
0x18013d1d8  jbe     loc_18013D721
0x18013d1de  cmp     ebx, edx
0x18013d1e0  jz      loc_18013D721
0x18013d1e6  mov     rcx, [rbp+238h]; this
0x18013d1ed  mov     r9d, ebx; char *
0x18013d1f0  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d1f7  mov     edx, 140h; void *
0x18013d1fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d201  jmp     loc_18013D721
0x18013d206  cmp     word ptr [r15], 40h ; '@'
0x18013d20b  jnz     loc_18013D3E3
0x18013d211  mov     rcx, r15; pszSource
0x18013d214  cmp     word ptr [r15+2], 7Bh ; '{'
0x18013d21a  jnz     loc_18013D390
0x18013d220  mov     edx, 3Fh ; '?'; Ch
0x18013d225  call    cs:__imp_wcschr
0x18013d22c  nop     dword ptr [rax+rax+00h]
0x18013d231  mov     rcx, rax
0x18013d234  neg     rcx
0x18013d237  sbb     ebx, ebx
0x18013d239  not     ebx
0x18013d23b  and     ebx, 8000FFFFh
0x18013d241  mov     rcx, [rbp+238h]; this
0x18013d248  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18013d24c  xor     r15d, r15d
0x18013d24f  test    rax, rax
0x18013d252  jnz     short loc_18013D26A
0x18013d254  mov     r9d, ebx; char *
0x18013d257  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d25e  mov     edx, 14Ah; void *
0x18013d263  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013d268  jmp     short loc_18013D28A
0x18013d26a  lea     rdx, [rax+2]
0x18013d26e  mov     r8, rsi
0x18013d271  inc     r8
0x18013d274  cmp     [rdx+r8*2], r15w
0x18013d279  jnz     short loc_18013D271
0x18013d27b  dec     r8
0x18013d27e  lea     rcx, [rsp+330h+var_2F8]
0x18013d283  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18013d288  mov     ebx, eax
0x18013d28a  mov     qword ptr [rsp+330h+length], r15
0x18013d28f  mov     [rsp+330h+string], r15
0x18013d294  test    ebx, ebx
0x18013d296  js      loc_18013D374
0x18013d29c  mov     rdi, [r14+8]
0x18013d2a0  mov     rax, [rdi]
0x18013d2a3  mov     rbx, [rax+58h]
0x18013d2a7  lea     rcx, [rsp+330h+length]
0x18013d2ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d2b1  lea     r9, [rsp+330h+length]
0x18013d2b6  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x18013d2bd  mov     rdx, qword ptr [rsp+330h+var_2F8]
0x18013d2c2  mov     rcx, rdi
0x18013d2c5  mov     rax, rbx
0x18013d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d2cd  mov     ebx, eax
0x18013d2cf  mov     rcx, [rbp+238h]
0x18013d2d6  test    eax, eax
0x18013d2d8  jns     short loc_18013D2E4
0x18013d2da  mov     edx, 155h
0x18013d2df  jmp     loc_18013D364
0x18013d2e4  mov     rdi, qword ptr [rsp+330h+length]
0x18013d2e9  mov     rax, [rdi]
0x18013d2ec  mov     rbx, [rax+38h]
0x18013d2f0  lea     rcx, [rsp+330h+string]
0x18013d2f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d2fa  lea     r8, [rsp+330h+string]
0x18013d2ff  mov     rdx, [r14+10h]
0x18013d303  mov     rcx, rdi
0x18013d306  mov     rax, rbx
0x18013d309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d30e  mov     ebx, eax
0x18013d310  mov     rcx, [rbp+238h]
0x18013d317  test    eax, eax
0x18013d319  jns     short loc_18013D322
0x18013d31b  mov     edx, 15Ah
0x18013d320  jmp     short loc_18013D364
0x18013d322  mov     rdi, [rsp+330h+string]
0x18013d327  mov     rax, [rdi]
0x18013d32a  mov     rbx, [rax+20h]
0x18013d32e  lea     rcx, [rsp+330h+var_2F8]
0x18013d333  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18013d338  mov     [rsp+330h+var_2F0], rsi
0x18013d33d  mov     [rsp+330h+var_2E8], rsi
0x18013d342  lea     rdx, [rsp+330h+var_2F8]
0x18013d347  mov     rcx, rdi
0x18013d34a  mov     rax, rbx
0x18013d34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d352  mov     ebx, eax
0x18013d354  mov     rcx, [rbp+238h]; this
0x18013d35b  test    eax, eax
0x18013d35d  jns     short loc_18013D374
0x18013d35f  mov     edx, 165h; void *
0x18013d364  mov     r9d, eax; char *
0x18013d367  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d36e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013d373  nop
0x18013d374  lea     rcx, [rsp+330h+string]
0x18013d379  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d37e  nop
0x18013d37f  lea     rcx, [rsp+330h+length]
0x18013d384  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d389  xor     esi, esi
0x18013d38b  jmp     loc_18013D5F9
0x18013d390  xor     r9d, r9d; ppvReserved
0x18013d393  mov     r8d, 104h; cchOutBuf
0x18013d399  lea     rdx, [rbp+230h+pszOutBuf]; pszOutBuf
0x18013d39d  call    cs:__imp_SHLoadIndirectString
0x18013d3a4  nop     dword ptr [rax+rax+00h]
0x18013d3a9  mov     rcx, [rbp+238h]; this
0x18013d3b0  test    eax, eax
0x18013d3b2  jns     short loc_18013D3CD
0x18013d3b4  mov     r9d, eax; char *
0x18013d3b7  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d3be  mov     edx, 172h; void *
0x18013d3c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013d3c8  jmp     loc_18013D601
0x18013d3cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18013d3d1  lea     rdx, [rbp+230h+pszOutBuf]
0x18013d3d5  lea     rcx, [rsp+330h+var_2F8]
0x18013d3da  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18013d3df  mov     ebx, eax
0x18013d3e1  jmp     short loc_18013D389
0x18013d3e3  cmp     [r14+2Dh], sil
0x18013d3e7  jz      loc_18013D48F
0x18013d3ed  mov     rcx, [rbp+230h+var_298]; this
0x18013d3f1  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x18013d3f6  test    al, al
0x18013d3f8  jz      loc_18013D48F
0x18013d3fe  mov     [rsp+330h+string], rsi
0x18013d403  xor     edx, edx
0x18013d405  lea     rcx, [rsp+330h+string]
0x18013d40a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18013d40f  lea     rdx, [rsp+330h+string]; HSTRING
0x18013d414  mov     rcx, [rbp+230h+var_298]; this
0x18013d418  call    ?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@PEAPEAG@Z; ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(HSTRING__ *,ushort * *)
0x18013d41d  mov     ebx, eax
0x18013d41f  mov     rcx, [rbp+238h]; this
0x18013d426  test    eax, eax
0x18013d428  jns     short loc_18013D440
0x18013d42a  mov     r9d, eax; char *
0x18013d42d  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013d434  mov     edx, 19Bh; void *
0x18013d439  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013d43e  jmp     short loc_18013D480
0x18013d440  mov     rdi, [r14+8]
0x18013d444  mov     rax, [rdi]
0x18013d447  mov     rbx, [rax+40h]
0x18013d44b  lea     rcx, [rsp+330h+var_2F8]
0x18013d450  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18013d455  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18013d459  mov     [rsp+330h+var_2F0], rsi
0x18013d45e  mov     [rsp+330h+var_2E8], rsi
0x18013d463  lea     r9, [rsp+330h+var_2F8]
0x18013d468  mov     r8, [rsp+330h+string]
0x18013d46d  mov     rdx, [r14+10h]
0x18013d471  mov     rcx, rdi
0x18013d474  mov     rax, rbx
0x18013d477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d47c  mov     ebx, eax
0x18013d47e  xor     esi, esi
0x18013d480  lea     rcx, [rsp+330h+string]
0x18013d485  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013d48a  jmp     loc_18013D5F9
0x18013d48f  mov     rdi, [r14+8]
0x18013d493  mov     rax, [rdi]
0x18013d496  mov     rbx, [rax+40h]
0x18013d49a  lea     rcx, [rsp+330h+var_2F8]
0x18013d49f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18013d4a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18013d4a8  mov     [rsp+330h+var_2F0], rsi
0x18013d4ad  mov     [rsp+330h+var_2E8], rsi
0x18013d4b2  lea     r9, [rsp+330h+var_2F8]
0x18013d4b7  mov     r8, r15
0x18013d4ba  mov     rdx, [r14+10h]
0x18013d4be  mov     rcx, rdi
0x18013d4c1  mov     rax, rbx
0x18013d4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d4c9  jmp     loc_18013D3DF
0x18013d4ce  mov     [rsp+330h+string], rsi
0x18013d4d3  lea     rcx, [rsp+330h+string]
0x18013d4d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d4dd  lea     rax, [rsp+330h+string]
0x18013d4e2  mov     [rsp+330h+ppv], rax; int
0x18013d4e7  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x18013d4ee  xor     edx, edx; pUnkOuter
0x18013d4f0  lea     r8d, [rdx+1]; dwClsContext
0x18013d4f4  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x18013d4fb  call    cs:__imp_CoCreateInstance
0x18013d502  nop     dword ptr [rax+rax+00h]
0x18013d507  mov     ebx, eax
0x18013d509  mov     rcx, [rbp+238h]
0x18013d510  test    eax, eax
0x18013d512  jns     short loc_18013D51E
0x18013d514  mov     edx, 119h
0x18013d519  jmp     loc_18013D5D9
0x18013d51e  test    dil, dil
0x18013d521  jz      short loc_18013D574
0x18013d523  mov     rdi, [rsp+330h+string]
  ... truncated ...
```
