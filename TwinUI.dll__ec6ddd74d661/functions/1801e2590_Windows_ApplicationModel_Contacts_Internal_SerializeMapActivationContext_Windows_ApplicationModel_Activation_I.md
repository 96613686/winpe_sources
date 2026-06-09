# Windows::ApplicationModel::Contacts::Internal::SerializeMapActivationContext(Windows::ApplicationModel::Activation::IContactActivatedEventArgs *,HSTRING__ * *)

- ea: `0x1801e2590`
- end: `0x1801e29aa`
- name: `?SerializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUIContactActivatedEventArgs@Activation@34@PEAPEAUHSTRING__@@@Z`
- size: `1050`
- prototype: `int(Windows::ApplicationModel::Contacts::Internal *__hidden this, struct Windows::ApplicationModel::Activation::IContactActivatedEventArgs *, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180053740`
- `0x180142e10`
- `0x1801e1ae8`
- `0x1801e21c4`
- `0x1801e2590`
- `0x1801e2df0`
- `0x1801e2e78`
- `0x1801e2f08`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e26a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e26cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e271a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e273f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e278e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e27b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e28f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e26a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e26cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e271a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e273f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e278e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e27b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e28f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2945`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::SerializeMapActivationContext(
        __int64 (__fastcall ***this)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *),
        HSTRING *a2,
        HSTRING *a3)
{
  int v5; // ebx
  __int64 (__fastcall **v6)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v7)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  HSTRING v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  HSTRING v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  HSTRING v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  HSTRING v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  HSTRING v28; // rbx
  __int64 v29; // rax
  double v30; // xmm6_8
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  HSTRING v34; // rbx
  __int64 v35; // rax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v38; // [rsp+28h] [rbp-58h] BYREF
  __int128 v39; // [rsp+30h] [rbp-50h] BYREF
  __int64 v40; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v41[32]; // [rsp+48h] [rbp-38h] BYREF

  *a2 = 0;
  v39 = 0;
  v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Initialize((Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39);
  if ( v5 >= 0 )
  {
    v6 = *this;
    v40 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
    v5 = v7((Windows::ApplicationModel::Contacts::Internal *)this, &GUID_b32bf870_eee7_4ad2_aaf1_a87effcf00a4, &v40);
    if ( v5 >= 0 )
    {
      v8 = v40;
      v38 = 0;
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v38);
      v5 = v9(v8, &v38);
      if ( v5 >= 0 )
      {
        v10 = v38;
        string = 0;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v5 = v11(v10, &string);
        if ( v5 >= 0 )
        {
          v12 = string;
          v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98B0);
          v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                 (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                 *(HSTRING *)(v13 + 24),
                 v12);
        }
        WindowsDeleteString(string);
        if ( v5 >= 0 )
        {
          v14 = v38;
          string = 0;
          v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 64LL);
          WindowsDeleteString(0);
          string = 0;
          v5 = v15(v14, &string);
          if ( v5 >= 0 )
          {
            v16 = string;
            v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F9898);
            v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                   (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                   *(HSTRING *)(v17 + 24),
                   v16);
          }
          WindowsDeleteString(string);
          if ( v5 >= 0 )
          {
            v18 = v38;
            string = 0;
            v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 80LL);
            WindowsDeleteString(0);
            string = 0;
            v5 = v19(v18, &string);
            if ( v5 >= 0 )
            {
              v20 = string;
              v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98A0);
              v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                     (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                     *(HSTRING *)(v21 + 24),
                     v20);
            }
            WindowsDeleteString(string);
            if ( v5 >= 0 )
            {
              v22 = v38;
              string = 0;
              v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 96LL);
              WindowsDeleteString(0);
              string = 0;
              v5 = v23(v22, &string);
              if ( v5 >= 0 )
              {
                v24 = string;
                v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98C8);
                v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                       (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                       *(HSTRING *)(v25 + 24),
                       v24);
              }
              WindowsDeleteString(string);
              if ( v5 >= 0 )
              {
                v26 = v38;
                string = 0;
                v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 112LL);
                WindowsDeleteString(0);
                string = 0;
                v5 = v27(v26, &string);
                if ( v5 >= 0 )
                {
                  v28 = string;
                  v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98D0);
                  v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                         (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                         *(HSTRING *)(v29 + 24),
                         v28);
                }
                WindowsDeleteString(string);
                if ( v5 >= 0 )
                {
                  LODWORD(string) = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 128LL))(v38, &string);
                  if ( v5 >= 0 )
                  {
                    v30 = (double)(int)string;
                    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98B8);
                    v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetNumberValue(
                           (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                           *(HSTRING *)(v31 + 24),
                           v30);
                    if ( v5 >= 0 )
                    {
                      v32 = v38;
                      string = 0;
                      v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 144LL);
                      WindowsDeleteString(0);
                      string = 0;
                      v5 = v33(v32, &string);
                      if ( v5 >= 0 )
                      {
                        v34 = string;
                        v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803F98C0);
                        v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                               (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                               *(HSTRING *)(v35 + 24),
                               v34);
                      }
                      WindowsDeleteString(string);
                      if ( v5 >= 0 )
                        v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Stringify(
                               (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                               a2);
                    }
                  }
                }
              }
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v38);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
  }
  Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer((Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v39);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801e2590  mov     [rsp-18h+arg_10], rbx
0x1801e2595  mov     [rsp-18h+arg_18], rsi
0x1801e259a  push    rbp
0x1801e259b  push    rdi
0x1801e259c  push    r14
0x1801e259e  mov     rbp, rsp
0x1801e25a1  sub     rsp, 80h
0x1801e25a8  movaps  [rsp+80h+var_10], xmm6
0x1801e25ad  mov     rax, cs:__security_cookie
0x1801e25b4  xor     rax, rsp
0x1801e25b7  mov     [rbp+var_18], rax
0x1801e25bb  mov     rdi, rcx
0x1801e25be  xorps   xmm0, xmm0
0x1801e25c1  xor     r14d, r14d
0x1801e25c4  lea     rcx, [rbp+var_50]; this
0x1801e25c8  mov     [rdx], r14
0x1801e25cb  mov     rsi, rdx
0x1801e25ce  movdqu  [rbp+var_50], xmm0
0x1801e25d3  call    ?Initialize@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJXZ; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Initialize(void)
0x1801e25d8  mov     ebx, eax
0x1801e25da  test    eax, eax
0x1801e25dc  js      loc_1801E2975
0x1801e25e2  mov     rax, [rdi]
0x1801e25e5  lea     rcx, [rbp+var_40]
0x1801e25e9  mov     [rbp+var_40], r14
0x1801e25ed  mov     rbx, [rax]
0x1801e25f0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e25f5  lea     r8, [rbp+var_40]
0x1801e25f9  mov     rcx, rdi
0x1801e25fc  lea     rdx, _GUID_b32bf870_eee7_4ad2_aaf1_a87effcf00a4
0x1801e2603  mov     rax, rbx
0x1801e2606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e260b  mov     ebx, eax
0x1801e260d  test    eax, eax
0x1801e260f  js      loc_1801E296C
0x1801e2615  mov     rdi, [rbp+var_40]
0x1801e2619  lea     rcx, [rbp+var_58]
0x1801e261d  mov     [rbp+var_58], r14
0x1801e2621  mov     rax, [rdi]
0x1801e2624  mov     rbx, [rax+30h]
0x1801e2628  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e262d  lea     rdx, [rbp+var_58]
0x1801e2631  mov     rcx, rdi
0x1801e2634  mov     rax, rbx
0x1801e2637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e263c  mov     ebx, eax
0x1801e263e  test    eax, eax
0x1801e2640  js      loc_1801E2963
0x1801e2646  mov     rdi, [rbp+var_58]
0x1801e264a  xor     ecx, ecx; string
0x1801e264c  mov     [rbp+string], r14
0x1801e2650  mov     rax, [rdi]
0x1801e2653  mov     rbx, [rax+30h]
0x1801e2657  call    cs:__imp_WindowsDeleteString
0x1801e265e  nop     dword ptr [rax+rax+00h]
0x1801e2663  lea     rdx, [rbp+string]
0x1801e2667  mov     [rbp+string], r14
0x1801e266b  mov     rcx, rdi
0x1801e266e  mov     rax, rbx
0x1801e2671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2676  mov     ebx, eax
0x1801e2678  test    eax, eax
0x1801e267a  js      short loc_1801E26A2
0x1801e267c  mov     rbx, [rbp+string]
0x1801e2680  lea     rdx, off_1803F98B0; "StreetAddress"
0x1801e2687  lea     rcx, [rbp+var_38]
0x1801e268b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e2690  mov     r8, rbx; HSTRING
0x1801e2693  lea     rcx, [rbp+var_50]; this
0x1801e2697  mov     rdx, [rax+18h]; HSTRING
0x1801e269b  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e26a0  mov     ebx, eax
0x1801e26a2  mov     rcx, [rbp+string]; string
0x1801e26a6  call    cs:__imp_WindowsDeleteString
0x1801e26ad  nop     dword ptr [rax+rax+00h]
0x1801e26b2  test    ebx, ebx
0x1801e26b4  js      loc_1801E2963
0x1801e26ba  mov     rdi, [rbp+var_58]
0x1801e26be  xor     ecx, ecx; string
0x1801e26c0  mov     [rbp+string], r14
0x1801e26c4  mov     rax, [rdi]
0x1801e26c7  mov     rbx, [rax+40h]
0x1801e26cb  call    cs:__imp_WindowsDeleteString
0x1801e26d2  nop     dword ptr [rax+rax+00h]
0x1801e26d7  lea     rdx, [rbp+string]
0x1801e26db  mov     [rbp+string], r14
0x1801e26df  mov     rcx, rdi
0x1801e26e2  mov     rax, rbx
0x1801e26e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e26ea  mov     ebx, eax
0x1801e26ec  test    eax, eax
0x1801e26ee  js      short loc_1801E2716
0x1801e26f0  mov     rbx, [rbp+string]
0x1801e26f4  lea     rdx, off_1803F9898; "Locality"
0x1801e26fb  lea     rcx, [rbp+var_38]
0x1801e26ff  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e2704  mov     r8, rbx; HSTRING
0x1801e2707  lea     rcx, [rbp+var_50]; this
0x1801e270b  mov     rdx, [rax+18h]; HSTRING
0x1801e270f  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e2714  mov     ebx, eax
0x1801e2716  mov     rcx, [rbp+string]; string
0x1801e271a  call    cs:__imp_WindowsDeleteString
0x1801e2721  nop     dword ptr [rax+rax+00h]
0x1801e2726  test    ebx, ebx
0x1801e2728  js      loc_1801E2963
0x1801e272e  mov     rdi, [rbp+var_58]
0x1801e2732  xor     ecx, ecx; string
0x1801e2734  mov     [rbp+string], r14
0x1801e2738  mov     rax, [rdi]
0x1801e273b  mov     rbx, [rax+50h]
0x1801e273f  call    cs:__imp_WindowsDeleteString
0x1801e2746  nop     dword ptr [rax+rax+00h]
0x1801e274b  lea     rdx, [rbp+string]
0x1801e274f  mov     [rbp+string], r14
0x1801e2753  mov     rcx, rdi
0x1801e2756  mov     rax, rbx
0x1801e2759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e275e  mov     ebx, eax
0x1801e2760  test    eax, eax
0x1801e2762  js      short loc_1801E278A
0x1801e2764  mov     rbx, [rbp+string]
0x1801e2768  lea     rdx, off_1803F98A0; "Region"
0x1801e276f  lea     rcx, [rbp+var_38]
0x1801e2773  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e2778  mov     r8, rbx; HSTRING
0x1801e277b  lea     rcx, [rbp+var_50]; this
0x1801e277f  mov     rdx, [rax+18h]; HSTRING
0x1801e2783  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e2788  mov     ebx, eax
0x1801e278a  mov     rcx, [rbp+string]; string
0x1801e278e  call    cs:__imp_WindowsDeleteString
0x1801e2795  nop     dword ptr [rax+rax+00h]
0x1801e279a  test    ebx, ebx
0x1801e279c  js      loc_1801E2963
0x1801e27a2  mov     rdi, [rbp+var_58]
0x1801e27a6  xor     ecx, ecx; string
0x1801e27a8  mov     [rbp+string], r14
0x1801e27ac  mov     rax, [rdi]
0x1801e27af  mov     rbx, [rax+60h]
0x1801e27b3  call    cs:__imp_WindowsDeleteString
0x1801e27ba  nop     dword ptr [rax+rax+00h]
0x1801e27bf  lea     rdx, [rbp+string]
0x1801e27c3  mov     [rbp+string], r14
0x1801e27c7  mov     rcx, rdi
0x1801e27ca  mov     rax, rbx
0x1801e27cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e27d2  mov     ebx, eax
0x1801e27d4  test    eax, eax
0x1801e27d6  js      short loc_1801E27FE
0x1801e27d8  mov     rbx, [rbp+string]
0x1801e27dc  lea     rdx, off_1803F98C8; "Country"
0x1801e27e3  lea     rcx, [rbp+var_38]
0x1801e27e7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e27ec  mov     r8, rbx; HSTRING
0x1801e27ef  lea     rcx, [rbp+var_50]; this
0x1801e27f3  mov     rdx, [rax+18h]; HSTRING
0x1801e27f7  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e27fc  mov     ebx, eax
0x1801e27fe  mov     rcx, [rbp+string]; string
0x1801e2802  call    cs:__imp_WindowsDeleteString
0x1801e2809  nop     dword ptr [rax+rax+00h]
0x1801e280e  test    ebx, ebx
0x1801e2810  js      loc_1801E2963
0x1801e2816  mov     rdi, [rbp+var_58]
0x1801e281a  xor     ecx, ecx; string
0x1801e281c  mov     [rbp+string], r14
0x1801e2820  mov     rax, [rdi]
0x1801e2823  mov     rbx, [rax+70h]
0x1801e2827  call    cs:__imp_WindowsDeleteString
0x1801e282e  nop     dword ptr [rax+rax+00h]
0x1801e2833  lea     rdx, [rbp+string]
0x1801e2837  mov     [rbp+string], r14
0x1801e283b  mov     rcx, rdi
0x1801e283e  mov     rax, rbx
0x1801e2841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2846  mov     ebx, eax
0x1801e2848  test    eax, eax
0x1801e284a  js      short loc_1801E2872
0x1801e284c  mov     rbx, [rbp+string]
0x1801e2850  lea     rdx, off_1803F98D0; "PostalCode"
0x1801e2857  lea     rcx, [rbp+var_38]
0x1801e285b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e2860  mov     r8, rbx; HSTRING
0x1801e2863  lea     rcx, [rbp+var_50]; this
0x1801e2867  mov     rdx, [rax+18h]; HSTRING
0x1801e286b  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e2870  mov     ebx, eax
0x1801e2872  mov     rcx, [rbp+string]; string
0x1801e2876  call    cs:__imp_WindowsDeleteString
0x1801e287d  nop     dword ptr [rax+rax+00h]
0x1801e2882  test    ebx, ebx
0x1801e2884  js      loc_1801E2963
0x1801e288a  mov     rcx, [rbp+var_58]
0x1801e288e  lea     rdx, [rbp+string]
0x1801e2892  mov     dword ptr [rbp+string], r14d
0x1801e2896  mov     rax, [rcx]
0x1801e2899  mov     rax, [rax+80h]
0x1801e28a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e28a5  mov     ebx, eax
0x1801e28a7  test    eax, eax
0x1801e28a9  js      loc_1801E2963
0x1801e28af  movd    xmm6, dword ptr [rbp+string]
0x1801e28b4  lea     rdx, off_1803F98B8; "Kind"
0x1801e28bb  lea     rcx, [rbp+var_38]
0x1801e28bf  cvtdq2pd xmm6, xmm6
0x1801e28c3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e28c8  lea     rcx, [rbp+var_50]; this
0x1801e28cc  mov     rdx, [rax+18h]; HSTRING
0x1801e28d0  movaps  xmm2, xmm6; double
0x1801e28d3  call    ?SetNumberValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@N@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetNumberValue(HSTRING__ *,double)
0x1801e28d8  mov     ebx, eax
0x1801e28da  test    eax, eax
0x1801e28dc  js      loc_1801E2963
0x1801e28e2  mov     rdi, [rbp+var_58]
0x1801e28e6  xor     ecx, ecx; string
0x1801e28e8  mov     [rbp+string], r14
0x1801e28ec  mov     rax, [rdi]
0x1801e28ef  mov     rbx, [rax+90h]
0x1801e28f6  call    cs:__imp_WindowsDeleteString
0x1801e28fd  nop     dword ptr [rax+rax+00h]
0x1801e2902  lea     rdx, [rbp+string]
0x1801e2906  mov     [rbp+string], r14
0x1801e290a  mov     rcx, rdi
0x1801e290d  mov     rax, rbx
0x1801e2910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2915  mov     ebx, eax
0x1801e2917  test    eax, eax
0x1801e2919  js      short loc_1801E2941
0x1801e291b  mov     rbx, [rbp+string]
0x1801e291f  lea     rdx, off_1803F98C0; "Description"
0x1801e2926  lea     rcx, [rbp+var_38]
0x1801e292a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e292f  mov     r8, rbx; HSTRING
0x1801e2932  lea     rcx, [rbp+var_50]; this
0x1801e2936  mov     rdx, [rax+18h]; HSTRING
0x1801e293a  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801e293f  mov     ebx, eax
0x1801e2941  mov     rcx, [rbp+string]; string
0x1801e2945  call    cs:__imp_WindowsDeleteString
0x1801e294c  nop     dword ptr [rax+rax+00h]
0x1801e2951  test    ebx, ebx
0x1801e2953  js      short loc_1801E2963
0x1801e2955  mov     rdx, rsi; HSTRING *
0x1801e2958  lea     rcx, [rbp+var_50]; this
0x1801e295c  call    ?Stringify@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Stringify(HSTRING__ * *)
0x1801e2961  mov     ebx, eax
0x1801e2963  lea     rcx, [rbp+var_58]
0x1801e2967  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e296c  lea     rcx, [rbp+var_40]
0x1801e2970  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e2975  lea     rcx, [rbp+var_50]; this
0x1801e2979  call    ??1JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer(void)
0x1801e297e  mov     eax, ebx
0x1801e2980  mov     rcx, [rbp+var_18]
0x1801e2984  xor     rcx, rsp; StackCookie
0x1801e2987  call    __security_check_cookie
0x1801e298c  lea     r11, [rsp+80h+var_s0]
0x1801e2994  mov     rbx, [r11+30h]
0x1801e2998  mov     rsi, [r11+38h]
0x1801e299c  movaps  xmm6, [rsp+80h+var_10]
0x1801e29a1  mov     rsp, r11
0x1801e29a4  pop     r14
0x1801e29a6  pop     rdi
0x1801e29a7  pop     rbp
0x1801e29a8  retn
```
