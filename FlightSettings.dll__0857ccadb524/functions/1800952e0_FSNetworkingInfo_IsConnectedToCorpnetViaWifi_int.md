# FSNetworkingInfo::IsConnectedToCorpnetViaWifi(int *)

- ea: `0x1800952e0`
- end: `0x18009574d`
- name: `?IsConnectedToCorpnetViaWifi@FSNetworkingInfo@@UEAAJPEAH@Z`
- size: `1133`
- prototype: `__int64 __fastcall(FSNetworkingInfo *__hidden this, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001146c`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec78`
- `0x180085a24`
- `0x1800888bc`
- `0x1800944a0`
- `0x1800952e0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800955f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800955f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009562b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009566d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800956d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095569`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009562b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009566d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800956d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009559c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009559c`

## string_xrefs

- `0x180095384`: `onecore\base\flighting\flightsettings\broker\lib\networkinginfo.cpp`
- `0x1800953dd`: `onecore\base\flighting\flightsettings\broker\lib\networkinginfo.cpp`
- `0x18009544c`: `onecore\base\flighting\flightsettings\broker\lib\networkinginfo.cpp`
- `0x180095693`: `onecore\base\flighting\flightsettings\broker\lib\networkinginfo.cpp`
- `0x1800956b6`: `onecore\base\flighting\flightsettings\broker\lib\networkinginfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FSNetworkingInfo::IsConnectedToCorpnetViaWifi(FSNetworkingInfo *this, int *a2)
{
  int FlightingRegString; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64 *); // rdi
  int v11; // eax
  __int64 v12; // rdx
  unsigned int i; // esi
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, _QWORD); // rbx
  int (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, __int64 *); // rbx
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v23; // eax
  int v24; // eax
  wchar_t *j; // rcx
  wchar_t *v26; // rax
  int v28; // [rsp+20h] [rbp-69h] BYREF
  HSTRING string; // [rsp+28h] [rbp-61h] BYREF
  int (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-59h] BYREF
  __int64 v31; // [rsp+38h] [rbp-51h] BYREF
  __int64 v32; // [rsp+40h] [rbp-49h] BYREF
  __int64 v33; // [rsp+48h] [rbp-41h] BYREF
  __int64 v34; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-31h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int16 *v37; // [rsp+68h] [rbp-21h] BYREF
  __int64 v38; // [rsp+70h] [rbp-19h]
  __int64 v39; // [rsp+78h] [rbp-11h]
  _QWORD v40[3]; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER String; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v37 = 0;
  v38 = 0;
  v39 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
  v38 = -1;
  v39 = -1;
  Context = (wchar_t *)-2147483646LL;
  FlightingRegString = FSRegUtils::GetFlightingRegString((HKEY *)&Context, 2u, L"CorpnetNamesList", &v37);
  v4 = FlightingRegString;
  if ( FlightingRegString == -2147024894 )
  {
    FlightingRegString = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                           &v37,
                           L"MSFTCORP;MSFTCORP (NEW)",
                           -1);
    v4 = FlightingRegString;
    if ( FlightingRegString < 0 )
    {
      v5 = 68;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\networkinginfo.cpp",
        (const char *)(unsigned int)FlightingRegString,
        v28);
      goto LABEL_44;
    }
  }
  else if ( FlightingRegString < 0 )
  {
    v5 = 73;
    goto LABEL_6;
  }
  v33 = 0;
  v30 = 0;
  v42 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &String,
    L"Windows.Networking.Connectivity.NetworkInformation",
    0x33u,
    0x32u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(
         v42,
         (__int64)&v33);
  v4 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 79;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\networkinginfo.cpp",
      (const char *)v7,
      v28);
LABEL_10:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    goto LABEL_44;
  }
  v9 = v33;
  if ( !v33 )
  {
    v4 = -2147024882;
    v7 = 2147942414LL;
    v8 = 80;
    goto LABEL_9;
  }
  v32 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  v11 = v10(v9, &v32);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 84;
    goto LABEL_15;
  }
  v35 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v35);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 88;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\networkinginfo.cpp",
      (const char *)(unsigned int)v11,
      v28);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    goto LABEL_10;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v35 )
    {
      *a2 = 0;
      goto LABEL_43;
    }
    v14 = v32;
    v15 = *(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
    if ( v15(v14, i, &v30) >= 0 )
      break;
LABEL_37:
    ;
  }
  v31 = 0;
  v16 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
  v17 = **v30;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  if ( v17(v16, &GUID_e2045145_4c9f_400c_9150_7ec7d6e2888a, &v31) < 0
    || (LOBYTE(v28) = 0, (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v28) < 0)
    || !(_BYTE)v28 )
  {
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    goto LABEL_37;
  }
  v34 = 0;
  v18 = v31;
  v19 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  if ( v19(v18, &v34) < 0 )
  {
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    goto LABEL_36;
  }
  string = 0;
  v20 = v34;
  v21 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v21(v20, &string) < 0 )
  {
LABEL_34:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_35;
  }
  memset(v40, 0, sizeof(v40));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          v40,
          StringRawBuffer,
          -1);
  v4 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\networkinginfo.cpp",
      (const char *)(unsigned int)v23,
      v28);
    goto LABEL_41;
  }
  memset(&String, 0, sizeof(String));
  v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(&String, &v37);
  v4 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\networkinginfo.cpp",
      (const char *)(unsigned int)v24,
      v28);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    goto LABEL_16;
  }
  Context = 0;
  for ( j = (wchar_t *)String.Reserved.Reserved1; ; j = 0 )
  {
    v26 = wcstok_s(j, L";", &Context);
    if ( !v26 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
      goto LABEL_34;
    }
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         v40,
                         v26,
                         -1) == 2 )
      break;
  }
  *a2 = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&String);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
LABEL_43:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v4 = 0;
LABEL_44:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
  return v4;
}

```

## disassembly

```asm
0x1800952e0  mov     [rsp-8+arg_0], rbx
0x1800952e5  mov     [rsp-8+arg_10], rsi
0x1800952ea  push    rbp
0x1800952eb  push    rdi
0x1800952ec  push    r12
0x1800952ee  push    r14
0x1800952f0  push    r15
0x1800952f2  lea     rbp, [rsp-37h]
0x1800952f7  sub     rsp, 0C0h
0x1800952fe  mov     rax, cs:__security_cookie
0x180095305  xor     rax, rsp
0x180095308  mov     [rbp+57h+var_28], rax
0x18009530c  mov     r14, rdx
0x18009530f  xor     r15d, r15d
0x180095312  mov     [rbp+57h+var_78], r15
0x180095316  mov     [rbp+57h+var_70], r15
0x18009531a  mov     [rbp+57h+var_68], r15
0x18009531e  lea     rcx, [rbp+57h+var_78]
0x180095322  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180095327  or      r12, 0FFFFFFFFFFFFFFFFh
0x18009532b  mov     [rbp+57h+var_70], r12
0x18009532f  mov     [rbp+57h+var_68], r12
0x180095333  mov     [rbp+57h+Context], 0FFFFFFFF80000002h
0x18009533b  lea     r9, [rbp+57h+var_78]
0x18009533f  lea     r8, aCorpnetnamesli; "CorpnetNamesList"
0x180095346  lea     edx, [r15+2]
0x18009534a  lea     rcx, [rbp+57h+Context]
0x18009534e  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x180095353  mov     ebx, eax
0x180095355  cmp     eax, 80070002h
0x18009535a  jnz     short loc_18009537B
0x18009535c  mov     r8, r12
0x18009535f  lea     rdx, aMsftcorpMsftco; "MSFTCORP;MSFTCORP (NEW)"
0x180095366  lea     rcx, [rbp+57h+var_78]
0x18009536a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009536f  mov     ebx, eax
0x180095371  test    eax, eax
0x180095373  jns     short loc_18009539C
0x180095375  lea     edx, [r15+44h]
0x180095379  jmp     short loc_180095384
0x18009537b  test    eax, eax
0x18009537d  jns     short loc_18009539C
0x18009537f  mov     edx, 49h ; 'I'; void *
0x180095384  lea     r8, aOnecoreBaseFli_70; "onecore\\base\\flighting\\flightsetting"...
0x18009538b  mov     r9d, eax; char *
0x18009538e  mov     rcx, [rbp+5Fh]; this
0x180095392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095397  jmp     loc_18009571A
0x18009539c  mov     [rbp+57h+var_98], r15
0x1800953a0  mov     [rbp+57h+var_B0], r15
0x1800953a4  mov     [rbp+57h+var_30], r15
0x1800953a8  mov     r9d, 32h ; '2'; unsigned int
0x1800953ae  lea     r8d, [r9+1]; unsigned int
0x1800953b2  lea     rdx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x1800953b9  lea     rcx, [rbp+57h+String]; hstringHeader
0x1800953bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800953c2  lea     rdx, [rbp+57h+var_98]
0x1800953c6  mov     rcx, [rbp+57h+var_30]
0x1800953ca  call    ??$GetActivationFactory@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>)
0x1800953cf  mov     ebx, eax
0x1800953d1  test    eax, eax
0x1800953d3  jns     short loc_180095406
0x1800953d5  mov     r9d, eax; char *
0x1800953d8  mov     edx, 4Fh ; 'O'; void *
0x1800953dd  lea     r8, aOnecoreBaseFli_70; "onecore\\base\\flighting\\flightsetting"...
0x1800953e4  mov     rcx, [rbp+5Fh]; this
0x1800953e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800953ed  nop
0x1800953ee  lea     rcx, [rbp+57h+var_B0]
0x1800953f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800953f7  nop
0x1800953f8  lea     rcx, [rbp+57h+var_98]
0x1800953fc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095401  jmp     loc_18009571A
0x180095406  mov     rbx, [rbp+57h+var_98]
0x18009540a  test    rbx, rbx
0x18009540d  jnz     short loc_18009541E
0x18009540f  mov     ebx, 8007000Eh
0x180095414  mov     r9d, ebx
0x180095417  mov     edx, 50h ; 'P'
0x18009541c  jmp     short loc_1800953DD
0x18009541e  mov     [rbp+57h+var_A0], r15
0x180095422  mov     rax, [rbx]
0x180095425  mov     rdi, [rax+30h]
0x180095429  lea     rcx, [rbp+57h+var_A0]
0x18009542d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095432  lea     rdx, [rbp+57h+var_A0]
0x180095436  mov     rcx, rbx
0x180095439  mov     rax, rdi
0x18009543c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095441  mov     ebx, eax
0x180095443  test    eax, eax
0x180095445  jns     short loc_18009546B
0x180095447  mov     edx, 54h ; 'T'; void *
0x18009544c  lea     r8, aOnecoreBaseFli_70; "onecore\\base\\flighting\\flightsetting"...
0x180095453  mov     r9d, eax; char *
0x180095456  mov     rcx, [rbp+5Fh]; this
0x18009545a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009545f  nop
0x180095460  lea     rcx, [rbp+57h+var_A0]
0x180095464  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095469  jmp     short loc_1800953EE
0x18009546b  mov     [rbp+57h+var_88], r15d
0x18009546f  mov     rcx, [rbp+57h+var_A0]
0x180095473  mov     rax, [rcx]
0x180095476  lea     rdx, [rbp+57h+var_88]
0x18009547a  mov     rax, [rax+38h]
0x18009547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095483  mov     ebx, eax
0x180095485  test    eax, eax
0x180095487  jns     short loc_180095490
0x180095489  mov     edx, 58h ; 'X'
0x18009548e  jmp     short loc_18009544C
0x180095490  mov     esi, r15d
0x180095493  cmp     esi, [rbp+57h+var_88]
0x180095496  jnb     loc_1800956F7
0x18009549c  mov     rdi, [rbp+57h+var_A0]
0x1800954a0  mov     rax, [rdi]
0x1800954a3  mov     rbx, [rax+30h]
0x1800954a7  lea     rcx, [rbp+57h+var_B0]
0x1800954ab  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800954b0  lea     r8, [rbp+57h+var_B0]
0x1800954b4  mov     edx, esi
0x1800954b6  mov     rcx, rdi
0x1800954b9  mov     rax, rbx
0x1800954bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800954c1  test    eax, eax
0x1800954c3  js      loc_180095648
0x1800954c9  mov     [rbp+57h+var_A8], r15
0x1800954cd  mov     rbx, [rbp+57h+var_B0]
0x1800954d1  mov     rax, [rbx]
0x1800954d4  mov     rdi, [rax]
0x1800954d7  lea     rcx, [rbp+57h+var_A8]
0x1800954db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800954e0  lea     r8, [rbp+57h+var_A8]
0x1800954e4  lea     rdx, _GUID_e2045145_4c9f_400c_9150_7ec7d6e2888a
0x1800954eb  mov     rcx, rbx
0x1800954ee  mov     rax, rdi
0x1800954f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800954f6  nop
0x1800954f7  test    eax, eax
0x1800954f9  js      loc_18009563F
0x1800954ff  mov     byte ptr [rbp+57h+var_C0], r15b
0x180095503  mov     rcx, [rbp+57h+var_A8]
0x180095507  mov     rax, [rcx]
0x18009550a  lea     rdx, [rbp+57h+var_C0]
0x18009550e  mov     rax, [rax+38h]
0x180095512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095517  test    eax, eax
0x180095519  js      loc_18009563F
0x18009551f  cmp     byte ptr [rbp+57h+var_C0], r15b
0x180095523  jz      loc_18009563F
0x180095529  mov     [rbp+57h+var_90], r15
0x18009552d  mov     rdi, [rbp+57h+var_A8]
0x180095531  mov     rax, [rdi]
0x180095534  mov     rbx, [rax+48h]
0x180095538  lea     rcx, [rbp+57h+var_90]
0x18009553c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095541  lea     rdx, [rbp+57h+var_90]
0x180095545  mov     rcx, rdi
0x180095548  mov     rax, rbx
0x18009554b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095550  test    eax, eax
0x180095552  js      loc_180095635
0x180095558  mov     [rbp+57h+string], r15
0x18009555c  mov     rdi, [rbp+57h+var_90]
0x180095560  mov     rax, [rdi]
0x180095563  mov     rbx, [rax+30h]
0x180095567  xor     ecx, ecx; string
0x180095569  call    cs:__imp_WindowsDeleteString
0x18009556f  mov     [rbp+57h+string], r15
0x180095573  lea     rdx, [rbp+57h+string]
0x180095577  mov     rcx, rdi
0x18009557a  mov     rax, rbx
0x18009557d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095582  test    eax, eax
0x180095584  js      loc_180095627
0x18009558a  mov     [rbp+57h+var_60], r15
0x18009558e  mov     [rbp+57h+var_58], r15
0x180095592  mov     [rbp+57h+var_50], r15
0x180095596  xor     edx, edx; length
0x180095598  mov     rcx, [rbp+57h+string]; string
0x18009559c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800955a2  mov     r8, r12
0x1800955a5  mov     rdx, rax
0x1800955a8  lea     rcx, [rbp+57h+var_60]
0x1800955ac  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800955b1  mov     ebx, eax
0x1800955b3  test    eax, eax
0x1800955b5  js      loc_1800956AF
0x1800955bb  mov     [rbp+57h+String], r15
0x1800955bf  mov     [rbp+57h+var_40], r15
0x1800955c3  mov     [rbp+57h+var_38], r15
0x1800955c7  lea     rdx, [rbp+57h+var_78]
0x1800955cb  lea     rcx, [rbp+57h+String]
0x1800955cf  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x1800955d4  mov     ebx, eax
0x1800955d6  test    eax, eax
0x1800955d8  js      loc_18009568C
0x1800955de  mov     [rbp+57h+Context], r15
0x1800955e2  mov     rcx, [rbp+57h+String]; String
0x1800955e6  lea     r8, [rbp+57h+Context]; Context
0x1800955ea  lea     rdx, Delimiter; ";"
0x1800955f1  call    cs:__imp_wcstok_s
0x1800955f7  test    rax, rax
0x1800955fa  jz      short loc_180095614
0x1800955fc  mov     r8, r12
0x1800955ff  mov     rdx, rax
0x180095602  lea     rcx, [rbp+57h+var_60]
0x180095606  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18009560b  cmp     eax, 2
0x18009560e  jz      short loc_18009564F
0x180095610  xor     ecx, ecx
0x180095612  jmp     short loc_1800955E6
0x180095614  lea     rcx, [rbp+57h+String]
0x180095618  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009561d  lea     rcx, [rbp+57h+var_60]
0x180095621  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180095626  nop
0x180095627  mov     rcx, [rbp+57h+string]; string
0x18009562b  call    cs:__imp_WindowsDeleteString
0x180095631  mov     [rbp+57h+string], r15
0x180095635  lea     rcx, [rbp+57h+var_90]
0x180095639  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009563e  nop
0x18009563f  lea     rcx, [rbp+57h+var_A8]
0x180095643  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095648  inc     esi
0x18009564a  jmp     loc_180095493
0x18009564f  mov     dword ptr [r14], 1
0x180095656  lea     rcx, [rbp+57h+String]
0x18009565a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009565f  lea     rcx, [rbp+57h+var_60]
0x180095663  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180095668  nop
0x180095669  mov     rcx, [rbp+57h+string]; string
0x18009566d  call    cs:__imp_WindowsDeleteString
0x180095673  mov     [rbp+57h+string], r15
0x180095677  lea     rcx, [rbp+57h+var_90]
0x18009567b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095680  nop
0x180095681  lea     rcx, [rbp+57h+var_A8]
0x180095685  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009568a  jmp     short loc_1800956FA
0x18009568c  mov     rcx, [rbp+5Fh]; this
0x180095690  mov     r9d, eax; char *
0x180095693  lea     r8, aOnecoreBaseFli_70; "onecore\\base\\flighting\\flightsetting"...
0x18009569a  mov     edx, 76h ; 'v'; void *
0x18009569f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800956a4  lea     rcx, [rbp+57h+String]
0x1800956a8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800956ad  jmp     short loc_1800956C7
0x1800956af  mov     rcx, [rbp+5Fh]; this
0x1800956b3  mov     r9d, eax; char *
0x1800956b6  lea     r8, aOnecoreBaseFli_70; "onecore\\base\\flighting\\flightsetting"...
0x1800956bd  mov     edx, 72h ; 'r'; void *
0x1800956c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800956c7  lea     rcx, [rbp+57h+var_60]
0x1800956cb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800956d0  nop
0x1800956d1  mov     rcx, [rbp+57h+string]; string
0x1800956d5  call    cs:__imp_WindowsDeleteString
0x1800956db  mov     [rbp+57h+string], r15
0x1800956df  lea     rcx, [rbp+57h+var_90]
0x1800956e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800956e8  nop
0x1800956e9  lea     rcx, [rbp+57h+var_A8]
0x1800956ed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800956f2  jmp     loc_180095460
0x1800956f7  mov     [r14], r15d
0x1800956fa  lea     rcx, [rbp+57h+var_A0]
0x1800956fe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095703  nop
0x180095704  lea     rcx, [rbp+57h+var_B0]
0x180095708  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009570d  nop
0x18009570e  lea     rcx, [rbp+57h+var_98]
0x180095712  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180095717  mov     ebx, r15d
0x18009571a  lea     rcx, [rbp+57h+var_78]
0x18009571e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180095723  mov     eax, ebx
0x180095725  mov     rcx, [rbp+57h+var_28]
0x180095729  xor     rcx, rsp; StackCookie
0x18009572c  call    __security_check_cookie
0x180095731  lea     r11, [rsp+0E0h+var_20]
0x180095739  mov     rbx, [r11+30h]
0x18009573d  mov     rsi, [r11+40h]
0x180095741  mov     rsp, r11
0x180095744  pop     r15
0x180095746  pop     r14
0x180095748  pop     r12
0x18009574a  pop     rdi
0x18009574b  pop     rbp
0x18009574c  retn
```
