# _anonymous_namespace_::s_GetSiteForAppAssociatedWithUri

- ea: `0x18015cecc`
- end: `0x18015d13a`
- name: `_anonymous_namespace_::s_GetSiteForAppAssociatedWithUri`
- size: `622`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18015cda4`

## callees

- `0x180009dd0`
- `0x18000b370`
- `0x18001c710`
- `0x180041f54`
- `0x180053740`
- `0x180142e10`
- `0x180157d30`
- `0x18015cecc`
- `0x180376f3c`
- `0x1803bb010`

## import_xrefs

- `SHELL32!SHCreateAssociationRegistration` at `0x18015cf19`
- `SHELL32!SHCreateAssociationRegistration` at `0x18015cf19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015cfbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d0f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015cfbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015d0f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015d019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015d0ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015d019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015d0ac`

## string_xrefs

- `0x18015cf41`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::s_GetSiteForAppAssociatedWithUri(
        unsigned __int16 *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, IUnknown **),
        struct IUnknown **a3)
{
  HRESULT AppIdFromProgId; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  void *v12; // rdi
  __int64 (__fastcall *v13)(void *, PCWSTR, __int64, __int64, HSTRING_HEADER *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall **v15)(_QWORD, GUID *, IUnknown **); // rax
  __int64 (__fastcall *v16)(_QWORD, GUID *, IUnknown **); // rbx
  ImmersiveAssociationHelpers *v17; // rax
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v21; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  void *ppv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+78h] [rbp+Fh]

  string = (HSTRING)a1;
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  AppIdFromProgId = SHCreateAssociationRegistration(&GUID_a357134e_8c1e_4edd_8474_40a80546f54f, &ppv);
  if ( AppIdFromProgId >= 0 )
  {
    v24 = 0;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    AppIdFromProgId = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                        v26,
                        &v24);
    if ( AppIdFromProgId >= 0 )
    {
      v7 = v24;
      v22 = 0;
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
      v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
      AppIdFromProgId = v8(v7, *(_QWORD *)(v9 + 24), &v22);
      if ( AppIdFromProgId >= 0 )
      {
        v10 = v22;
        string = 0;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 136LL);
        WindowsDeleteString(0);
        string = 0;
        AppIdFromProgId = v11(v10, &string);
        if ( AppIdFromProgId >= 0 )
        {
          v12 = ppv;
          memset(&hstringHeader, 0, sizeof(hstringHeader));
          v13 = *(__int64 (__fastcall **)(void *, PCWSTR, __int64, __int64, HSTRING_HEADER *))(*(_QWORD *)ppv + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          AppIdFromProgId = v13(v12, StringRawBuffer, 1, 1, &hstringHeader);
          if ( AppIdFromProgId >= 0 )
          {
            v21 = 0;
            WindowsDeleteString(0);
            v21 = 0;
            AppIdFromProgId = GetAppIdFromProgId((unsigned __int16 *)hstringHeader.Reserved.Reserved1, (HSTRING)&v21);
            if ( AppIdFromProgId >= 0 )
            {
              v15 = *a2;
              punk = 0;
              v16 = *v15;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&punk);
              AppIdFromProgId = v16(a2, &GUID_adf3165c_ba9e_42a7_922f_2005d7bd711a, &punk);
              if ( AppIdFromProgId >= 0 )
              {
                v17 = (ImmersiveAssociationHelpers *)WindowsGetStringRawBuffer(v21, 0);
                AppIdFromProgId = GetMainWindowViewPreferenceSite(punk, a1, v17, a3);
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&punk);
            }
            WindowsDeleteString(v21);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        }
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v24);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  return (unsigned int)AppIdFromProgId;
}

```

## disassembly

```asm
0x18015cecc  push    rbp
0x18015cece  push    rbx
0x18015cecf  push    rsi
0x18015ced0  push    rdi
0x18015ced1  push    r12
0x18015ced3  push    r14
0x18015ced5  push    r15
0x18015ced7  lea     rbp, [rsp-27h]
0x18015cedc  sub     rsp, 90h
0x18015cee3  mov     rax, cs:__security_cookie
0x18015ceea  xor     rax, rsp
0x18015ceed  mov     [rbp+57h+var_40], rax
0x18015cef1  mov     rsi, rcx
0x18015cef4  mov     [rbp+57h+string], rcx
0x18015cef8  xor     r12d, r12d
0x18015cefb  lea     rcx, [rbp+57h+ppv]
0x18015ceff  mov     [rbp+57h+ppv], r12
0x18015cf03  mov     r15, r8
0x18015cf06  mov     r14, rdx
0x18015cf09  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015cf0e  lea     rdx, [rbp+57h+ppv]; ppv
0x18015cf12  lea     rcx, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x18015cf19  call    cs:__imp_SHCreateAssociationRegistration
0x18015cf20  nop     dword ptr [rax+rax+00h]
0x18015cf25  mov     ebx, eax
0x18015cf27  test    eax, eax
0x18015cf29  js      loc_18015D110
0x18015cf2f  lea     r9d, [r12+16h]; unsigned int
0x18015cf34  mov     [rbp+57h+var_68], r12
0x18015cf38  lea     r8d, [r12+17h]; unsigned int
0x18015cf3d  mov     [rbp+57h+var_48], r12
0x18015cf41  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18015cf48  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18015cf4c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18015cf51  mov     rcx, [rbp+57h+var_48]
0x18015cf55  lea     rdx, [rbp+57h+var_68]
0x18015cf59  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18015cf5e  mov     ebx, eax
0x18015cf60  test    eax, eax
0x18015cf62  js      loc_18015D107
0x18015cf68  mov     rdi, [rbp+57h+var_68]
0x18015cf6c  lea     rcx, [rbp+57h+var_78]
0x18015cf70  mov     [rbp+57h+var_78], r12
0x18015cf74  mov     rax, [rdi]
0x18015cf77  mov     rbx, [rax+30h]
0x18015cf7b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015cf80  lea     rdx, [rbp+57h+string]
0x18015cf84  lea     rcx, [rbp+57h+hstringHeader]
0x18015cf88  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18015cf8d  lea     r8, [rbp+57h+var_78]
0x18015cf91  mov     rcx, rdi
0x18015cf94  mov     rdx, [rax+18h]
0x18015cf98  mov     rax, rbx
0x18015cf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cfa0  mov     ebx, eax
0x18015cfa2  test    eax, eax
0x18015cfa4  js      loc_18015D0FE
0x18015cfaa  mov     rdi, [rbp+57h+var_78]
0x18015cfae  xor     ecx, ecx; string
0x18015cfb0  mov     [rbp+57h+string], r12
0x18015cfb4  mov     rax, [rdi]
0x18015cfb7  mov     rbx, [rax+88h]
0x18015cfbe  call    cs:__imp_WindowsDeleteString
0x18015cfc5  nop     dword ptr [rax+rax+00h]
0x18015cfca  lea     rdx, [rbp+57h+string]
0x18015cfce  mov     [rbp+57h+string], r12
0x18015cfd2  mov     rcx, rdi
0x18015cfd5  mov     rax, rbx
0x18015cfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cfdd  mov     ebx, eax
0x18015cfdf  test    eax, eax
0x18015cfe1  js      loc_18015D0EE
0x18015cfe7  mov     rdi, [rbp+57h+ppv]
0x18015cfeb  lea     rcx, [rbp+57h+hstringHeader]
0x18015cfef  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x18015cff3  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x18015cff7  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x18015cffb  mov     rax, [rdi]
0x18015cffe  mov     rbx, [rax+40h]
0x18015d002  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015d007  mov     rcx, [rbp+57h+string]; string
0x18015d00b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18015d00f  xor     edx, edx; length
0x18015d011  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x18015d015  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18015d019  call    cs:__imp_WindowsGetStringRawBuffer
0x18015d020  nop     dword ptr [rax+rax+00h]
0x18015d025  lea     rcx, [rbp+57h+hstringHeader]
0x18015d029  mov     rdx, rax
0x18015d02c  lea     r8d, [r12+1]
0x18015d031  mov     [rsp+0C0h+var_A0], rcx
0x18015d036  mov     rcx, rdi
0x18015d039  mov     r9d, r8d
0x18015d03c  mov     rax, rbx
0x18015d03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d044  mov     ebx, eax
0x18015d046  test    eax, eax
0x18015d048  js      loc_18015D0E5
0x18015d04e  xor     ecx, ecx; string
0x18015d050  mov     [rbp+57h+var_80], r12
0x18015d054  call    cs:__imp_WindowsDeleteString
0x18015d05b  nop     dword ptr [rax+rax+00h]
0x18015d060  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned __int16 *
0x18015d064  lea     rdx, [rbp+57h+var_80]; HSTRING
0x18015d068  mov     [rbp+57h+var_80], r12
0x18015d06c  call    GetAppIdFromProgId
0x18015d071  mov     ebx, eax
0x18015d073  test    eax, eax
0x18015d075  js      short loc_18015D0D5
0x18015d077  mov     rax, [r14]
0x18015d07a  lea     rcx, [rbp+57h+punk]
0x18015d07e  mov     [rbp+57h+punk], r12
0x18015d082  mov     rbx, [rax]
0x18015d085  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015d08a  lea     r8, [rbp+57h+punk]
0x18015d08e  mov     rcx, r14
0x18015d091  lea     rdx, _GUID_adf3165c_ba9e_42a7_922f_2005d7bd711a
0x18015d098  mov     rax, rbx
0x18015d09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d0a0  mov     ebx, eax
0x18015d0a2  test    eax, eax
0x18015d0a4  js      short loc_18015D0CC
0x18015d0a6  mov     rcx, [rbp+57h+var_80]; string
0x18015d0aa  xor     edx, edx; length
0x18015d0ac  call    cs:__imp_WindowsGetStringRawBuffer
0x18015d0b3  nop     dword ptr [rax+rax+00h]
0x18015d0b8  mov     rcx, [rbp+57h+punk]; punk
0x18015d0bc  mov     r9, r15; struct IUnknown **
0x18015d0bf  mov     r8, rax; this
0x18015d0c2  mov     rdx, rsi; unsigned __int16 *
0x18015d0c5  call    ?GetMainWindowViewPreferenceSite@@YAJPEAUIMainWindowActivationInfo@Actions@ApplicationModel@Windows@@PEBG1PEAPEAUIUnknown@@@Z; GetMainWindowViewPreferenceSite(Windows::ApplicationModel::Actions::IMainWindowActivationInfo *,ushort const *,ushort const *,IUnknown * *)
0x18015d0ca  mov     ebx, eax
0x18015d0cc  lea     rcx, [rbp+57h+punk]
0x18015d0d0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015d0d5  mov     rcx, [rbp+57h+var_80]; string
0x18015d0d9  call    cs:__imp_WindowsDeleteString
0x18015d0e0  nop     dword ptr [rax+rax+00h]
0x18015d0e5  lea     rcx, [rbp+57h+hstringHeader]
0x18015d0e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015d0ee  mov     rcx, [rbp+57h+string]; string
0x18015d0f2  call    cs:__imp_WindowsDeleteString
0x18015d0f9  nop     dword ptr [rax+rax+00h]
0x18015d0fe  lea     rcx, [rbp+57h+var_78]
0x18015d102  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015d107  lea     rcx, [rbp+57h+var_68]
0x18015d10b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015d110  lea     rcx, [rbp+57h+ppv]
0x18015d114  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015d119  mov     eax, ebx
0x18015d11b  mov     rcx, [rbp+57h+var_40]
0x18015d11f  xor     rcx, rsp; StackCookie
0x18015d122  call    __security_check_cookie
0x18015d127  add     rsp, 90h
0x18015d12e  pop     r15
0x18015d130  pop     r14
0x18015d132  pop     r12
0x18015d134  pop     rdi
0x18015d135  pop     rsi
0x18015d136  pop     rbx
0x18015d137  pop     rbp
0x18015d138  retn
```
