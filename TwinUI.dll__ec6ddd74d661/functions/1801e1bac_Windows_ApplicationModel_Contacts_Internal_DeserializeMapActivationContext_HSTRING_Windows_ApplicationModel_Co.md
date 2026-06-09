# Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(HSTRING__ *,Windows::ApplicationModel::Contacts::IContactAddress * *)

- ea: `0x1801e1bac`
- end: `0x1801e1f7b`
- name: `?DeserializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAUIContactAddress@234@@Z`
- size: `975`
- prototype: `__int64 __fastcall(HSTRING this, HSTRING, struct Windows::ApplicationModel::Contacts::IContactAddress **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d6598`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x180053740`
- `0x180142e10`
- `0x1801e1a40`
- `0x1801e1ae8`
- `0x1801e1bac`
- `0x1801e20e0`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1de6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1e00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1de6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1e00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1f2f`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(
        HSTRING this,
        _QWORD *a2,
        struct Windows::ApplicationModel::Contacts::IContactAddress **a3)
{
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  __int128 v15; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]

  *a2 = 0;
  v15 = 0;
  v4 = Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::Initialize(
         (Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v15,
         this);
  if ( v4 >= 0 )
  {
    v14 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Contacts.ContactAddress",
      0x31u,
      0x30u);
    v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>(
           v17,
           &v14);
    if ( v4 >= 0 )
    {
      WindowsDeleteString(0);
      *(double *)&string = 0.0;
      v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98B0);
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
             v15,
             *(_QWORD *)(v5 + 24),
             &string);
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 56LL))(v14, string);
      WindowsDeleteString(string);
      if ( v4 >= 0 )
      {
        *(double *)&string = 0.0;
        WindowsDeleteString(0);
        *(double *)&string = 0.0;
        v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9898);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
               v15,
               *(_QWORD *)(v6 + 24),
               &string);
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 72LL))(v14, string);
        WindowsDeleteString(string);
        if ( v4 >= 0 )
        {
          *(double *)&string = 0.0;
          WindowsDeleteString(0);
          *(double *)&string = 0.0;
          v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98A0);
          v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                 v15,
                 *(_QWORD *)(v7 + 24),
                 &string);
          if ( v4 >= 0 )
            v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 88LL))(v14, string);
          WindowsDeleteString(string);
          if ( v4 >= 0 )
          {
            *(double *)&string = 0.0;
            WindowsDeleteString(0);
            *(double *)&string = 0.0;
            v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98C8);
            v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                   v15,
                   *(_QWORD *)(v8 + 24),
                   &string);
            if ( v4 >= 0 )
              v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 104LL))(v14, string);
            WindowsDeleteString(string);
            if ( v4 >= 0 )
            {
              *(double *)&string = 0.0;
              WindowsDeleteString(0);
              *(double *)&string = 0.0;
              v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98D0);
              v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                     v15,
                     *(_QWORD *)(v9 + 24),
                     &string);
              if ( v4 >= 0 )
                v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 120LL))(v14, string);
              WindowsDeleteString(string);
              if ( v4 >= 0 )
              {
                *(double *)&string = 0.0;
                v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98B8);
                v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 88LL))(
                       v15,
                       *(_QWORD *)(v10 + 24),
                       &string);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 136LL))(
                         v14,
                         (unsigned int)(int)*(double *)&string);
                  if ( v4 >= 0 )
                  {
                    *(double *)&string = 0.0;
                    WindowsDeleteString(0);
                    *(double *)&string = 0.0;
                    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98C0);
                    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                           v15,
                           *(_QWORD *)(v11 + 24),
                           &string);
                    if ( v4 >= 0 )
                      v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 152LL))(v14, string);
                    WindowsDeleteString(string);
                    if ( v4 >= 0 )
                    {
                      *a2 = v14;
                      v14 = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v14);
  }
  Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer((Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801e1bac  mov     [rsp-18h+arg_10], rbx
0x1801e1bb1  push    rbp
0x1801e1bb2  push    rsi
0x1801e1bb3  push    rdi
0x1801e1bb4  mov     rbp, rsp
0x1801e1bb7  sub     rsp, 70h
0x1801e1bbb  mov     rax, cs:__security_cookie
0x1801e1bc2  xor     rax, rsp
0x1801e1bc5  mov     [rbp+var_10], rax
0x1801e1bc9  mov     rdi, rdx
0x1801e1bcc  xorps   xmm0, xmm0
0x1801e1bcf  xor     esi, esi
0x1801e1bd1  mov     [rdx], rsi
0x1801e1bd4  mov     rdx, rcx; HSTRING
0x1801e1bd7  lea     rcx, [rbp+var_40]; this
0x1801e1bdb  movdqu  [rbp+var_40], xmm0
0x1801e1be0  call    ?Initialize@JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::Initialize(HSTRING__ *)
0x1801e1be5  mov     ebx, eax
0x1801e1be7  test    eax, eax
0x1801e1be9  js      loc_1801E1F53
0x1801e1bef  lea     r9d, [rsi+30h]; unsigned int
0x1801e1bf3  mov     [rbp+var_48], rsi
0x1801e1bf7  lea     r8d, [rsi+31h]; unsigned int
0x1801e1bfb  mov     [rbp+var_18], rsi
0x1801e1bff  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Contacts_ContactAddress@@3QBGB; "Windows.ApplicationModel.Contacts.Conta"...
0x1801e1c06  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e1c0a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e1c0f  mov     rcx, [rbp+var_18]
0x1801e1c13  lea     rdx, [rbp+var_48]
0x1801e1c17  call    ??$ActivateInstance@V?$ComPtr@UIContactAddress@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIContactAddress@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>)
0x1801e1c1c  mov     ebx, eax
0x1801e1c1e  test    eax, eax
0x1801e1c20  js      loc_1801E1F4A
0x1801e1c26  xor     ecx, ecx; string
0x1801e1c28  mov     [rbp+string], rsi
0x1801e1c2c  call    cs:__imp_WindowsDeleteString
0x1801e1c33  nop     dword ptr [rax+rax+00h]
0x1801e1c38  lea     rdx, off_1803F98B0; "StreetAddress"
0x1801e1c3f  mov     [rbp+string], rsi
0x1801e1c43  lea     rcx, [rbp+hstringHeader]
0x1801e1c47  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1c4c  mov     rcx, qword ptr [rbp+var_40]
0x1801e1c50  lea     r8, [rbp+string]
0x1801e1c54  mov     r9, rax
0x1801e1c57  mov     rdx, [rcx]
0x1801e1c5a  mov     rax, [rdx+50h]
0x1801e1c5e  mov     rdx, [r9+18h]
0x1801e1c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1c67  mov     ebx, eax
0x1801e1c69  test    eax, eax
0x1801e1c6b  js      short loc_1801E1C83
0x1801e1c6d  mov     rcx, [rbp+var_48]
0x1801e1c71  mov     rdx, [rbp+string]
0x1801e1c75  mov     rax, [rcx]
0x1801e1c78  mov     rax, [rax+38h]
0x1801e1c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1c81  mov     ebx, eax
0x1801e1c83  mov     rcx, [rbp+string]; string
0x1801e1c87  call    cs:__imp_WindowsDeleteString
0x1801e1c8e  nop     dword ptr [rax+rax+00h]
0x1801e1c93  test    ebx, ebx
0x1801e1c95  js      loc_1801E1F4A
0x1801e1c9b  xor     ecx, ecx; string
0x1801e1c9d  mov     [rbp+string], rsi
0x1801e1ca1  call    cs:__imp_WindowsDeleteString
0x1801e1ca8  nop     dword ptr [rax+rax+00h]
0x1801e1cad  lea     rdx, off_1803F9898; "Locality"
0x1801e1cb4  mov     [rbp+string], rsi
0x1801e1cb8  lea     rcx, [rbp+hstringHeader]
0x1801e1cbc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1cc1  mov     rcx, qword ptr [rbp+var_40]
0x1801e1cc5  lea     r8, [rbp+string]
0x1801e1cc9  mov     r9, rax
0x1801e1ccc  mov     rdx, [rcx]
0x1801e1ccf  mov     rax, [rdx+50h]
0x1801e1cd3  mov     rdx, [r9+18h]
0x1801e1cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1cdc  mov     ebx, eax
0x1801e1cde  test    eax, eax
0x1801e1ce0  js      short loc_1801E1CF8
0x1801e1ce2  mov     rcx, [rbp+var_48]
0x1801e1ce6  mov     rdx, [rbp+string]
0x1801e1cea  mov     rax, [rcx]
0x1801e1ced  mov     rax, [rax+48h]
0x1801e1cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1cf6  mov     ebx, eax
0x1801e1cf8  mov     rcx, [rbp+string]; string
0x1801e1cfc  call    cs:__imp_WindowsDeleteString
0x1801e1d03  nop     dword ptr [rax+rax+00h]
0x1801e1d08  test    ebx, ebx
0x1801e1d0a  js      loc_1801E1F4A
0x1801e1d10  xor     ecx, ecx; string
0x1801e1d12  mov     [rbp+string], rsi
0x1801e1d16  call    cs:__imp_WindowsDeleteString
0x1801e1d1d  nop     dword ptr [rax+rax+00h]
0x1801e1d22  lea     rdx, off_1803F98A0; "Region"
0x1801e1d29  mov     [rbp+string], rsi
0x1801e1d2d  lea     rcx, [rbp+hstringHeader]
0x1801e1d31  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1d36  mov     rcx, qword ptr [rbp+var_40]
0x1801e1d3a  lea     r8, [rbp+string]
0x1801e1d3e  mov     r9, rax
0x1801e1d41  mov     rdx, [rcx]
0x1801e1d44  mov     rax, [rdx+50h]
0x1801e1d48  mov     rdx, [r9+18h]
0x1801e1d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1d51  mov     ebx, eax
0x1801e1d53  test    eax, eax
0x1801e1d55  js      short loc_1801E1D6D
0x1801e1d57  mov     rcx, [rbp+var_48]
0x1801e1d5b  mov     rdx, [rbp+string]
0x1801e1d5f  mov     rax, [rcx]
0x1801e1d62  mov     rax, [rax+58h]
0x1801e1d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1d6b  mov     ebx, eax
0x1801e1d6d  mov     rcx, [rbp+string]; string
0x1801e1d71  call    cs:__imp_WindowsDeleteString
0x1801e1d78  nop     dword ptr [rax+rax+00h]
0x1801e1d7d  test    ebx, ebx
0x1801e1d7f  js      loc_1801E1F4A
0x1801e1d85  xor     ecx, ecx; string
0x1801e1d87  mov     [rbp+string], rsi
0x1801e1d8b  call    cs:__imp_WindowsDeleteString
0x1801e1d92  nop     dword ptr [rax+rax+00h]
0x1801e1d97  lea     rdx, off_1803F98C8; "Country"
0x1801e1d9e  mov     [rbp+string], rsi
0x1801e1da2  lea     rcx, [rbp+hstringHeader]
0x1801e1da6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1dab  mov     rcx, qword ptr [rbp+var_40]
0x1801e1daf  lea     r8, [rbp+string]
0x1801e1db3  mov     r9, rax
0x1801e1db6  mov     rdx, [rcx]
0x1801e1db9  mov     rax, [rdx+50h]
0x1801e1dbd  mov     rdx, [r9+18h]
0x1801e1dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1dc6  mov     ebx, eax
0x1801e1dc8  test    eax, eax
0x1801e1dca  js      short loc_1801E1DE2
0x1801e1dcc  mov     rcx, [rbp+var_48]
0x1801e1dd0  mov     rdx, [rbp+string]
0x1801e1dd4  mov     rax, [rcx]
0x1801e1dd7  mov     rax, [rax+68h]
0x1801e1ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1de0  mov     ebx, eax
0x1801e1de2  mov     rcx, [rbp+string]; string
0x1801e1de6  call    cs:__imp_WindowsDeleteString
0x1801e1ded  nop     dword ptr [rax+rax+00h]
0x1801e1df2  test    ebx, ebx
0x1801e1df4  js      loc_1801E1F4A
0x1801e1dfa  xor     ecx, ecx; string
0x1801e1dfc  mov     [rbp+string], rsi
0x1801e1e00  call    cs:__imp_WindowsDeleteString
0x1801e1e07  nop     dword ptr [rax+rax+00h]
0x1801e1e0c  lea     rdx, off_1803F98D0; "PostalCode"
0x1801e1e13  mov     [rbp+string], rsi
0x1801e1e17  lea     rcx, [rbp+hstringHeader]
0x1801e1e1b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1e20  mov     rcx, qword ptr [rbp+var_40]
0x1801e1e24  lea     r8, [rbp+string]
0x1801e1e28  mov     r9, rax
0x1801e1e2b  mov     rdx, [rcx]
0x1801e1e2e  mov     rax, [rdx+50h]
0x1801e1e32  mov     rdx, [r9+18h]
0x1801e1e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1e3b  mov     ebx, eax
0x1801e1e3d  test    eax, eax
0x1801e1e3f  js      short loc_1801E1E57
0x1801e1e41  mov     rcx, [rbp+var_48]
0x1801e1e45  mov     rdx, [rbp+string]
0x1801e1e49  mov     rax, [rcx]
0x1801e1e4c  mov     rax, [rax+78h]
0x1801e1e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1e55  mov     ebx, eax
0x1801e1e57  mov     rcx, [rbp+string]; string
0x1801e1e5b  call    cs:__imp_WindowsDeleteString
0x1801e1e62  nop     dword ptr [rax+rax+00h]
0x1801e1e67  test    ebx, ebx
0x1801e1e69  js      loc_1801E1F4A
0x1801e1e6f  xorps   xmm0, xmm0
0x1801e1e72  lea     rdx, off_1803F98B8; "Kind"
0x1801e1e79  lea     rcx, [rbp+hstringHeader]
0x1801e1e7d  movsd   [rbp+string], xmm0
0x1801e1e82  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1e87  mov     rcx, qword ptr [rbp+var_40]
0x1801e1e8b  lea     r8, [rbp+string]
0x1801e1e8f  mov     r9, rax
0x1801e1e92  mov     rdx, [rcx]
0x1801e1e95  mov     rax, [rdx+58h]
0x1801e1e99  mov     rdx, [r9+18h]
0x1801e1e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1ea2  mov     ebx, eax
0x1801e1ea4  test    eax, eax
0x1801e1ea6  js      loc_1801E1F4A
0x1801e1eac  mov     rcx, [rbp+var_48]
0x1801e1eb0  cvttsd2si rdx, [rbp+string]
0x1801e1eb6  mov     rax, [rcx]
0x1801e1eb9  mov     rax, [rax+88h]
0x1801e1ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1ec5  mov     ebx, eax
0x1801e1ec7  test    eax, eax
0x1801e1ec9  js      short loc_1801E1F4A
0x1801e1ecb  xor     ecx, ecx; string
0x1801e1ecd  mov     [rbp+string], rsi
0x1801e1ed1  call    cs:__imp_WindowsDeleteString
0x1801e1ed8  nop     dword ptr [rax+rax+00h]
0x1801e1edd  lea     rdx, off_1803F98C0; "Description"
0x1801e1ee4  mov     [rbp+string], rsi
0x1801e1ee8  lea     rcx, [rbp+hstringHeader]
0x1801e1eec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e1ef1  mov     rcx, qword ptr [rbp+var_40]
0x1801e1ef5  lea     r8, [rbp+string]
0x1801e1ef9  mov     r9, rax
0x1801e1efc  mov     rdx, [rcx]
0x1801e1eff  mov     rax, [rdx+50h]
0x1801e1f03  mov     rdx, [r9+18h]
0x1801e1f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1f0c  mov     ebx, eax
0x1801e1f0e  test    eax, eax
0x1801e1f10  js      short loc_1801E1F2B
0x1801e1f12  mov     rcx, [rbp+var_48]
0x1801e1f16  mov     rdx, [rbp+string]
0x1801e1f1a  mov     rax, [rcx]
0x1801e1f1d  mov     rax, [rax+98h]
0x1801e1f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1f29  mov     ebx, eax
0x1801e1f2b  mov     rcx, [rbp+string]; string
0x1801e1f2f  call    cs:__imp_WindowsDeleteString
0x1801e1f36  nop     dword ptr [rax+rax+00h]
0x1801e1f3b  test    ebx, ebx
0x1801e1f3d  js      short loc_1801E1F4A
0x1801e1f3f  mov     rax, [rbp+var_48]
0x1801e1f43  mov     [rdi], rax
0x1801e1f46  mov     [rbp+var_48], rsi
0x1801e1f4a  lea     rcx, [rbp+var_48]
0x1801e1f4e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e1f53  lea     rcx, [rbp+var_40]; this
0x1801e1f57  call    ??1JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer(void)
0x1801e1f5c  mov     eax, ebx
0x1801e1f5e  mov     rcx, [rbp+var_10]
0x1801e1f62  xor     rcx, rsp; StackCookie
0x1801e1f65  call    __security_check_cookie
0x1801e1f6a  mov     rbx, [rsp+70h+arg_10]
0x1801e1f72  add     rsp, 70h
0x1801e1f76  pop     rdi
0x1801e1f77  pop     rsi
0x1801e1f78  pop     rbp
0x1801e1f79  retn
```
