# Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(ushort const *,ushort const *,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> *)

- ea: `0x180049628`
- end: `0x180049b08`
- name: `?_GetConfigurableEapMethods@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEBG0PEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@2Collections@Foundation@5@@Z`
- size: `1248`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e608`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x180035ca0`
- `0x180036f60`
- `0x180036f9c`
- `0x180049628`
- `0x18004ac70`
- `0x18008e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180049718`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800498f8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180049718`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800498f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049768`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800497ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004994e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800499af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049768`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800497ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004994e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800499af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004969a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800496e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800498c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004969a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800496e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800498c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049a8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049ad6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049a8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049ad6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049794`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004997a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180049794`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004997a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049820`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049820`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a03`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180049a2a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180049ac3`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180049a2a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180049ac3`

## string_xrefs

- `0x18004975c`: `WlanProfileTemplate`
- `0x1800497c2`: `WlanProfileTemplate`
- `0x180049942`: `WlanProfileTemplate`
- `0x1800499a3`: `WlanProfileTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(
        __int64 a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  LSTATUS v7; // eax
  signed int v8; // edi
  int v9; // r15d
  DWORD i; // edx
  Windows::Networking::UX::Internal::WlanInterface *v11; // rcx
  BYTE *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // esi
  DWORD j; // edx
  Windows::Networking::UX::Internal::WlanInterface *v20; // rcx
  BYTE *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD lpcbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v36; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE *v37; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v38; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v41; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v42; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  BYTE *v45; // [rsp+80h] [rbp-80h] BYREF
  int v46; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v47[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v48[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR Name[512]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR SubKey[512]; // [rsp+8B0h] [rbp+7B0h] BYREF

  memset_0(SubKey, 0, sizeof(SubKey));
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v9 = 1;
    for ( i = 0; !RegEnumKeyW(hKey, i, SubKey, 0x200u); i = v9++ )
    {
      v38 = 0;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &v38) )
      {
        memset_0(v47, 0, 0x208u);
        Type = 0;
        cbData = 0;
        v40 = _o__wtoi(SubKey);
        if ( !Windows::Networking::UX::Internal::WlanInterface::_LoadEapMethodFriendlyName(v11, v38, a3, v47, phkResult) )
        {
          Type = 0;
          cbData = 0;
          if ( !RegQueryValueExW(v38, L"WlanProfileTemplate", 0, &Type, 0, &cbData) && cbData && Type == 1 )
          {
            v12 = (BYTE *)LocalAlloc(0x40u, cbData);
            v39 = v12;
            if ( v12 )
            {
              if ( !RegQueryValueExW(v38, L"WlanProfileTemplate", 0, &Type, v12, &cbData) )
              {
                v37 = 0;
                if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,unsigned int &,unsigned short (&)[260],unsigned short * &>(
                            (__int64)&v37,
                            (__int64)&v40,
                            (__int64)v47,
                            (__int64)&v39) >= 0 )
                  (*(void (__fastcall **)(__int64, BYTE *))(*(_QWORD *)a4 + 104LL))(a4, v37);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v37,
                  v13,
                  v14);
                v12 = v39;
              }
              LocalFree(v12);
            }
          }
          else
          {
            memset_0(Name, 0, sizeof(Name));
            v42 = 0;
            if ( !RegOpenKeyExW(v38, L"WLANProfileCreationUXAuth", 0, 0x20019u, &v42) )
            {
              v37 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v37,
                v15,
                v16);
              if ( (int)Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWiFiEapMethod,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0>>(
                          v17,
                          &v37) >= 0 )
              {
                v18 = 1;
                for ( j = 0; !RegEnumKeyW(v42, j, Name, 0x200u); j = v18++ )
                {
                  v41 = 0;
                  if ( !RegOpenKeyExW(v42, Name, 0, 0x20019u, &v41) )
                  {
                    memset_0(v48, 0, 0x208u);
                    v36 = 0;
                    lpcbData = 520;
                    v46 = _o__wtoi(Name);
                    if ( !Windows::Networking::UX::Internal::WlanInterface::_LoadEapMethodFriendlyName(
                            v20,
                            v41,
                            L"FriendlyName",
                            v48,
                            phkResulta) )
                    {
                      v36 = 0;
                      lpcbData = 0;
                      if ( !RegQueryValueExW(v41, L"WlanProfileTemplate", 0, &v36, 0, &lpcbData) )
                      {
                        if ( lpcbData )
                        {
                          if ( v36 == 1 )
                          {
                            v21 = (BYTE *)LocalAlloc(0x40u, lpcbData);
                            v45 = v21;
                            if ( v21 )
                            {
                              if ( !RegQueryValueExW(v41, L"WlanProfileTemplate", 0, &v36, v21, &lpcbData) )
                              {
                                v39 = 0;
                                if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,unsigned int &,unsigned short (&)[260],unsigned short * &>(
                                            (__int64)&v39,
                                            (__int64)&v46,
                                            (__int64)v48,
                                            (__int64)&v45) >= 0 )
                                  (*(void (__fastcall **)(BYTE *, BYTE *))(*(_QWORD *)v37 + 104LL))(v37, v39);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                                  &v39,
                                  v22,
                                  v23);
                                v21 = v45;
                              }
                              LocalFree(v21);
                            }
                          }
                        }
                      }
                    }
                    RegCloseKey(v41);
                  }
                }
                v44 = 0;
                v45 = v37;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v44,
                  v24,
                  v25);
                if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,unsigned int &,unsigned short (&)[260],Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> *>(
                            &v44,
                            &v40,
                            v47,
                            &v45) >= 0 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 104LL))(a4, v44);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v44,
                  v26,
                  v27);
              }
              RegCloseKey(v42);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v37,
                v28,
                v29);
            }
          }
        }
        RegCloseKey(v38);
      }
    }
  }
  RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049628  mov     [rsp-8+arg_0], rbx
0x18004962d  push    rbp
0x18004962e  push    rsi
0x18004962f  push    rdi
0x180049630  push    r12
0x180049632  push    r13
0x180049634  push    r14
0x180049636  push    r15
0x180049638  lea     rbp, [rsp-0BC0h]
0x180049640  sub     rsp, 0CC0h
0x180049647  mov     rax, cs:__security_cookie
0x18004964e  xor     rax, rsp
0x180049651  mov     [rbp+0BF0h+var_40], rax
0x180049658  mov     r14, r9
0x18004965b  mov     r12, r8
0x18004965e  mov     rbx, rdx
0x180049661  xor     edx, edx; Val
0x180049663  mov     r8d, 400h; Size
0x180049669  lea     rcx, [rbp+0BF0h+SubKey]; void *
0x180049670  call    memset_0
0x180049675  xor     r13d, r13d
0x180049678  mov     [rsp+0CF0h+hKey], r13
0x18004967d  lea     rax, [rsp+0CF0h+hKey]
0x180049682  mov     [rsp+0CF0h+phkResult], rax; phkResult
0x180049687  mov     r9d, 20019h; samDesired
0x18004968d  xor     r8d, r8d; ulOptions
0x180049690  mov     rdx, rbx; lpSubKey
0x180049693  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004969a  call    cs:__imp_RegOpenKeyExW
0x1800496a0  mov     edi, eax
0x1800496a2  test    eax, eax
0x1800496a4  jle     short loc_1800496AF
0x1800496a6  movzx   edi, ax
0x1800496a9  or      edi, 80070000h
0x1800496af  test    edi, edi
0x1800496b1  js      loc_180049AD1
0x1800496b7  mov     r15d, 1
0x1800496bd  xor     edx, edx
0x1800496bf  jmp     loc_180049AB1
0x1800496c4  mov     [rsp+0CF0h+var_CA8], r13
0x1800496c9  lea     rax, [rsp+0CF0h+var_CA8]
0x1800496ce  mov     [rsp+0CF0h+phkResult], rax; unsigned int
0x1800496d3  mov     r9d, 20019h; samDesired
0x1800496d9  xor     r8d, r8d; ulOptions
0x1800496dc  lea     rdx, [rbp+0BF0h+SubKey]; lpSubKey
0x1800496e3  mov     rcx, [rsp+0CF0h+hKey]; hKey
0x1800496e8  call    cs:__imp_RegOpenKeyExW
0x1800496ee  test    eax, eax
0x1800496f0  jnz     loc_180049AAB
0x1800496f6  xor     edx, edx; Val
0x1800496f8  mov     r8d, 208h; Size
0x1800496fe  lea     rcx, [rbp+0BF0h+var_C60]; void *
0x180049702  call    memset_0
0x180049707  mov     [rsp+0CF0h+Type], r13d
0x18004970c  mov     [rsp+0CF0h+cbData], r13d
0x180049711  lea     rcx, [rbp+0BF0h+SubKey]
0x180049718  call    cs:__imp__o__wtoi
0x18004971e  mov     [rsp+0CF0h+var_C98], eax
0x180049722  lea     r9, [rbp+0BF0h+var_C60]; unsigned __int16 *
0x180049726  mov     r8, r12; unsigned __int16 *
0x180049729  mov     rdx, [rsp+0CF0h+var_CA8]; HKEY
0x18004972e  call    ?_LoadEapMethodFriendlyName@WlanInterface@Internal@UX@Networking@Windows@@IEAAKPEAUHKEY__@@PEBGPEAGK@Z; Windows::Networking::UX::Internal::WlanInterface::_LoadEapMethodFriendlyName(HKEY__ *,ushort const *,ushort *,ulong)
0x180049733  test    eax, eax
0x180049735  jnz     loc_180049AA0
0x18004973b  mov     [rsp+0CF0h+Type], r13d
0x180049740  mov     [rsp+0CF0h+cbData], r13d
0x180049745  lea     rax, [rsp+0CF0h+cbData]
0x18004974a  mov     [rsp+0CF0h+lpcbData], rax; lpcbData
0x18004974f  mov     [rsp+0CF0h+phkResult], r13; lpData
0x180049754  lea     r9, [rsp+0CF0h+Type]; lpType
0x180049759  xor     r8d, r8d; lpReserved
0x18004975c  lea     rdx, ValueName; "WlanProfileTemplate"
0x180049763  mov     rcx, [rsp+0CF0h+var_CA8]; hKey
0x180049768  call    cs:__imp_RegQueryValueExW
0x18004976e  test    eax, eax
0x180049770  jnz     loc_18004982B
0x180049776  mov     eax, [rsp+0CF0h+cbData]
0x18004977a  test    eax, eax
0x18004977c  jz      loc_18004982B
0x180049782  cmp     [rsp+0CF0h+Type], 1
0x180049787  jnz     loc_18004982B
0x18004978d  mov     edx, eax; uBytes
0x18004978f  mov     ecx, 40h ; '@'; uFlags
0x180049794  call    cs:__imp_LocalAlloc
0x18004979a  mov     rbx, rax
0x18004979d  mov     [rsp+0CF0h+var_CA0], rax
0x1800497a2  test    rax, rax
0x1800497a5  jz      loc_180049AA0
0x1800497ab  lea     rax, [rsp+0CF0h+cbData]
0x1800497b0  mov     [rsp+0CF0h+lpcbData], rax; lpcbData
0x1800497b5  mov     [rsp+0CF0h+phkResult], rbx; lpData
0x1800497ba  lea     r9, [rsp+0CF0h+Type]; lpType
0x1800497bf  xor     r8d, r8d; lpReserved
0x1800497c2  lea     rdx, ValueName; "WlanProfileTemplate"
0x1800497c9  mov     rcx, [rsp+0CF0h+var_CA8]; hKey
0x1800497ce  call    cs:__imp_RegQueryValueExW
0x1800497d4  test    eax, eax
0x1800497d6  jnz     short loc_18004981D
0x1800497d8  mov     [rsp+0CF0h+var_CB0], r13
0x1800497dd  lea     r9, [rsp+0CF0h+var_CA0]
0x1800497e2  lea     r8, [rbp+0BF0h+var_C60]
0x1800497e6  lea     rdx, [rsp+0CF0h+var_C98]
0x1800497eb  lea     rcx, [rsp+0CF0h+var_CB0]
0x1800497f0  call    ??$MakeAndInitialize@VCWiFiEapMethod@Internal@UX@Networking@Windows@@UIWiFiEapMethod@345@AEAIAEAY0BAE@GAEAPEAG@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIWiFiEapMethod@UX@Networking@Windows@@@WRL@Microsoft@@@012@AEAIAEAY0BAE@GAEAPEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,uint &,ushort (&)[260],ushort * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IWiFiEapMethod>>,uint &,ushort (&)[260],ushort * &)
0x1800497f5  test    eax, eax
0x1800497f7  js      short loc_18004980E
0x1800497f9  mov     rax, [r14]
0x1800497fc  mov     rdx, [rsp+0CF0h+var_CB0]
0x180049801  mov     rcx, r14
0x180049804  mov     rax, [rax+68h]
0x180049808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004980d  nop
0x18004980e  lea     rcx, [rsp+0CF0h+var_CB0]
0x180049813  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049818  mov     rbx, [rsp+0CF0h+var_CA0]
0x18004981d  mov     rcx, rbx; hMem
0x180049820  call    cs:__imp_LocalFree
0x180049826  jmp     loc_180049AA0
0x18004982b  xor     edx, edx; Val
0x18004982d  mov     r8d, 400h; Size
0x180049833  lea     rcx, [rbp+0BF0h+Name]; void *
0x18004983a  call    memset_0
0x18004983f  mov     [rsp+0CF0h+var_C88], r13
0x180049844  lea     rax, [rsp+0CF0h+var_C88]
0x180049849  mov     [rsp+0CF0h+phkResult], rax; phkResult
0x18004984e  mov     r9d, 20019h; samDesired
0x180049854  xor     r8d, r8d; ulOptions
0x180049857  lea     rdx, aWlanprofilecre; "WLANProfileCreationUXAuth"
0x18004985e  mov     rcx, [rsp+0CF0h+var_CA8]; hKey
0x180049863  call    cs:__imp_RegOpenKeyExW
0x180049869  test    eax, eax
0x18004986b  jnz     loc_180049AA0
0x180049871  mov     [rsp+0CF0h+var_CB0], r13
0x180049876  lea     rcx, [rsp+0CF0h+var_CB0]
0x18004987b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049880  lea     rdx, [rsp+0CF0h+var_CB0]
0x180049885  call    ??$CreateExternalObjectVector@UIWiFiEapMethod@UX@Networking@Windows@@V?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWiFiEapMethod,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> * *)
0x18004988a  test    eax, eax
0x18004988c  js      loc_180049A8A
0x180049892  mov     esi, 1
0x180049897  xor     edx, edx
0x180049899  jmp     loc_180049A18
0x18004989e  mov     [rsp+0CF0h+var_C90], r13
0x1800498a3  lea     rax, [rsp+0CF0h+var_C90]
0x1800498a8  mov     [rsp+0CF0h+phkResult], rax; unsigned int
0x1800498ad  mov     r9d, 20019h; samDesired
0x1800498b3  xor     r8d, r8d; ulOptions
0x1800498b6  lea     rdx, [rbp+0BF0h+Name]; lpSubKey
0x1800498bd  mov     rcx, [rsp+0CF0h+var_C88]; hKey
0x1800498c2  call    cs:__imp_RegOpenKeyExW
0x1800498c8  test    eax, eax
0x1800498ca  jnz     loc_180049A14
0x1800498d0  xor     edx, edx; Val
0x1800498d2  mov     r8d, 208h; Size
0x1800498d8  lea     rcx, [rbp+0BF0h+var_A50]; void *
0x1800498df  call    memset_0
0x1800498e4  mov     [rsp+0CF0h+var_CB4], r13d
0x1800498e9  mov     [rsp+0CF0h+var_CB8], 208h
0x1800498f1  lea     rcx, [rbp+0BF0h+Name]
0x1800498f8  call    cs:__imp__o__wtoi
0x1800498fe  mov     [rbp+0BF0h+var_C68], eax
0x180049901  lea     r9, [rbp+0BF0h+var_A50]; unsigned __int16 *
0x180049908  lea     r8, aFriendlyname; "FriendlyName"
0x18004990f  mov     rdx, [rsp+0CF0h+var_C90]; HKEY
0x180049914  call    ?_LoadEapMethodFriendlyName@WlanInterface@Internal@UX@Networking@Windows@@IEAAKPEAUHKEY__@@PEBGPEAGK@Z; Windows::Networking::UX::Internal::WlanInterface::_LoadEapMethodFriendlyName(HKEY__ *,ushort const *,ushort *,ulong)
0x180049919  test    eax, eax
0x18004991b  jnz     loc_180049A09
0x180049921  mov     [rsp+0CF0h+var_CB4], r13d
0x180049926  mov     [rsp+0CF0h+var_CB8], r13d
0x18004992b  lea     rax, [rsp+0CF0h+var_CB8]
0x180049930  mov     [rsp+0CF0h+lpcbData], rax; lpcbData
0x180049935  mov     [rsp+0CF0h+phkResult], r13; lpData
0x18004993a  lea     r9, [rsp+0CF0h+var_CB4]; lpType
0x18004993f  xor     r8d, r8d; lpReserved
0x180049942  lea     rdx, ValueName; "WlanProfileTemplate"
0x180049949  mov     rcx, [rsp+0CF0h+var_C90]; hKey
0x18004994e  call    cs:__imp_RegQueryValueExW
0x180049954  test    eax, eax
0x180049956  jnz     loc_180049A09
0x18004995c  mov     eax, [rsp+0CF0h+var_CB8]
0x180049960  test    eax, eax
0x180049962  jz      loc_180049A09
0x180049968  cmp     [rsp+0CF0h+var_CB4], 1
0x18004996d  jnz     loc_180049A09
0x180049973  mov     edx, eax; uBytes
0x180049975  mov     ecx, 40h ; '@'; uFlags
0x18004997a  call    cs:__imp_LocalAlloc
0x180049980  mov     rbx, rax
0x180049983  mov     [rbp+0BF0h+var_C70], rax
0x180049987  test    rax, rax
0x18004998a  jz      short loc_180049A09
0x18004998c  lea     rax, [rsp+0CF0h+var_CB8]
0x180049991  mov     [rsp+0CF0h+lpcbData], rax; lpcbData
0x180049996  mov     [rsp+0CF0h+phkResult], rbx; lpData
0x18004999b  lea     r9, [rsp+0CF0h+var_CB4]; lpType
0x1800499a0  xor     r8d, r8d; lpReserved
0x1800499a3  lea     rdx, ValueName; "WlanProfileTemplate"
0x1800499aa  mov     rcx, [rsp+0CF0h+var_C90]; hKey
0x1800499af  call    cs:__imp_RegQueryValueExW
0x1800499b5  test    eax, eax
0x1800499b7  jnz     short loc_180049A00
0x1800499b9  mov     [rsp+0CF0h+var_CA0], r13
0x1800499be  lea     r9, [rbp+0BF0h+var_C70]
0x1800499c2  lea     r8, [rbp+0BF0h+var_A50]
0x1800499c9  lea     rdx, [rbp+0BF0h+var_C68]
0x1800499cd  lea     rcx, [rsp+0CF0h+var_CA0]
0x1800499d2  call    ??$MakeAndInitialize@VCWiFiEapMethod@Internal@UX@Networking@Windows@@UIWiFiEapMethod@345@AEAIAEAY0BAE@GAEAPEAG@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIWiFiEapMethod@UX@Networking@Windows@@@WRL@Microsoft@@@012@AEAIAEAY0BAE@GAEAPEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,uint &,ushort (&)[260],ushort * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IWiFiEapMethod>>,uint &,ushort (&)[260],ushort * &)
0x1800499d7  test    eax, eax
0x1800499d9  js      short loc_1800499F2
0x1800499db  mov     rcx, [rsp+0CF0h+var_CB0]
0x1800499e0  mov     rax, [rcx]
0x1800499e3  mov     rdx, [rsp+0CF0h+var_CA0]
0x1800499e8  mov     rax, [rax+68h]
0x1800499ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499f1  nop
0x1800499f2  lea     rcx, [rsp+0CF0h+var_CA0]
0x1800499f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800499fc  mov     rbx, [rbp+0BF0h+var_C70]
0x180049a00  mov     rcx, rbx; hMem
0x180049a03  call    cs:__imp_LocalFree
0x180049a09  mov     rcx, [rsp+0CF0h+var_C90]; hKey
0x180049a0e  call    cs:__imp_RegCloseKey
0x180049a14  mov     edx, esi; dwIndex
0x180049a16  inc     esi
0x180049a18  mov     r9d, 200h; cchName
0x180049a1e  lea     r8, [rbp+0BF0h+Name]; lpName
0x180049a25  mov     rcx, [rsp+0CF0h+var_C88]; hKey
0x180049a2a  call    cs:__imp_RegEnumKeyW
0x180049a30  test    eax, eax
0x180049a32  jz      loc_18004989E
0x180049a38  mov     [rsp+0CF0h+var_C78], r13
0x180049a3d  mov     rax, [rsp+0CF0h+var_CB0]
0x180049a42  mov     [rbp+0BF0h+var_C70], rax
0x180049a46  lea     rcx, [rsp+0CF0h+var_C78]
0x180049a4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049a50  lea     r9, [rbp+0BF0h+var_C70]
0x180049a54  lea     r8, [rbp+0BF0h+var_C60]
0x180049a58  lea     rdx, [rsp+0CF0h+var_C98]
0x180049a5d  lea     rcx, [rsp+0CF0h+var_C78]
0x180049a62  call    ??$MakeAndInitialize@VCWiFiEapMethod@Internal@UX@Networking@Windows@@UIWiFiEapMethod@345@AEAIAEAY0BAE@GPEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@2Collections@Foundation@5@@Details@WRL@Microsoft@@YAJPEAPEAUIWiFiEapMethod@UX@Networking@Windows@@AEAIAEAY0BAE@G$$QEAPEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@Internal@Collections@Foundation@6@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiEapMethod,Windows::Networking::UX::IWiFiEapMethod,uint &,ushort (&)[260],Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> *>(Windows::Networking::UX::IWiFiEapMethod * *,uint &,ushort (&)[260],Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> * &&)
0x180049a67  test    eax, eax
0x180049a69  js      short loc_180049A80
0x180049a6b  mov     rax, [r14]
0x180049a6e  mov     rdx, [rsp+0CF0h+var_C78]
0x180049a73  mov     rcx, r14
0x180049a76  mov     rax, [rax+68h]
0x180049a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a7f  nop
0x180049a80  lea     rcx, [rsp+0CF0h+var_C78]
0x180049a85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049a8a  mov     rcx, [rsp+0CF0h+var_C88]; hKey
0x180049a8f  call    cs:__imp_RegCloseKey
0x180049a95  nop
0x180049a96  lea     rcx, [rsp+0CF0h+var_CB0]
0x180049a9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049aa0  mov     rcx, [rsp+0CF0h+var_CA8]; hKey
0x180049aa5  call    cs:__imp_RegCloseKey
0x180049aab  mov     edx, r15d; dwIndex
0x180049aae  inc     r15d
0x180049ab1  mov     r9d, 200h; cchName
0x180049ab7  lea     r8, [rbp+0BF0h+SubKey]; lpName
0x180049abe  mov     rcx, [rsp+0CF0h+hKey]; hKey
0x180049ac3  call    cs:__imp_RegEnumKeyW
0x180049ac9  test    eax, eax
0x180049acb  jz      loc_1800496C4
0x180049ad1  mov     rcx, [rsp+0CF0h+hKey]; hKey
0x180049ad6  call    cs:__imp_RegCloseKey
0x180049adc  mov     eax, edi
0x180049ade  mov     rcx, [rbp+0BF0h+var_40]
0x180049ae5  xor     rcx, rsp; StackCookie
0x180049ae8  call    __security_check_cookie
0x180049aed  mov     rbx, [rsp+0CF0h+arg_0]
0x180049af5  add     rsp, 0CC0h
0x180049afc  pop     r15
0x180049afe  pop     r14
0x180049b00  pop     r13
0x180049b02  pop     r12
0x180049b04  pop     rdi
0x180049b05  pop     rsi
0x180049b06  pop     rbp
0x180049b07  retn
```
