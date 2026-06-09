# ChatServiceAlgorithms::GetMd5Hash(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800b2f8c`
- end: `0x1800b33e6`
- name: `?GetMd5Hash@ChatServiceAlgorithms@@SAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1114`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008fd90`
- `0x180092a60`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800b2f8c`
- `0x1800b3484`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b3029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b311a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b31d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b3029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b311a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b31d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b32fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b32fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b319c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b336f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b319c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b32ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b336f`

## string_xrefs

- `0x1800b3002`: `Windows.Security.Cryptography.CryptographicBuffer`
- `0x1800b31b2`: `Windows.Security.Cryptography.Core.HashAlgorithmProvider`
- `0x1800b30f3`: `Windows.Security.Cryptography.Core.HashAlgorithmNames`

## pseudocode

```c
__int64 __fastcall ChatServiceAlgorithms::GetMd5Hash(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  int ActivationFactory; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, _QWORD, __int64 *); // rbx
  char v9; // r8
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, HSTRING *); // rbx
  int v25; // eax
  int v26; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  __int64 v34; // [rsp+48h] [rbp-31h]
  const WCHAR *v35; // [rsp+50h] [rbp-29h] BYREF
  __int64 v36; // [rsp+58h] [rbp-21h] BYREF
  __int64 v37; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+68h] [rbp-11h] BYREF
  __int64 v39; // [rsp+70h] [rbp-9h] BYREF
  __int64 v40; // [rsp+78h] [rbp-1h] BYREF
  __int64 v41; // [rsp+80h] [rbp+7h] BYREF
  HSTRING v42; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v43; // [rsp+90h] [rbp+17h] BYREF
  _OWORD v44[2]; // [rsp+98h] [rbp+1Fh] BYREF

  memset(v44, 0, sizeof(v44));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v44);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v44,
                           v3) )
  {
    v4 = -2147024882;
    Log_HREvent_94(-2147024882);
    goto LABEL_43;
  }
  v36 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.CryptographicBuffer",
    0x32u,
    0x31u);
  ActivationFactory = RoGetActivationFactory(v34, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v36);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_94(ActivationFactory);
    v6 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    goto LABEL_43;
  }
  v7 = v36;
  v41 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD, __int64 *))(*(_QWORD *)v36 + 120LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  v35 = *(const WCHAR **)&v44[0];
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v35, v9);
  v11 = v8(v7, v10[1].Reserved.Reserved1, 0, &v41);
  v4 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent_94(v11);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v12 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_43;
  }
  v37 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.Core.HashAlgorithmNames",
    0x36u,
    0x35u);
  v13 = RoGetActivationFactory(v34, &GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76, &v37);
  v4 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_94(v13);
    goto LABEL_13;
  }
  v15 = v37;
  string = 0;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = v16(v15, &string);
  v4 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_94(v17);
LABEL_17:
    WindowsDeleteString(string);
    string = 0;
LABEL_13:
    v14 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_9;
  }
  v39 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.Core.HashAlgorithmProvider",
    0x39u,
    0x38u);
  v18 = RoGetActivationFactory(v34, &GUID_9fac9741_5cc4_4336_ae38_6212b75a915a, &v39);
  v4 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_94(v18);
LABEL_20:
    v19 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_17;
  }
  v40 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, string, &v40);
  v4 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent_94(v20);
    goto LABEL_24;
  }
  v43 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v40 + 64LL))(v40, v41, &v43);
  v4 = v22;
  if ( v22 < 0 )
  {
    Log_HREvent_94(v22);
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
LABEL_24:
    v21 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_20;
  }
  v23 = v36;
  v42 = 0;
  v24 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v36 + 96LL);
  WindowsDeleteString(0);
  v42 = 0;
  v25 = v24(v23, v43, &v42);
  v4 = v25;
  if ( v25 < 0 )
  {
    v26 = v25;
LABEL_31:
    Log_HREvent_94(v26);
    WindowsDeleteString(v42);
    v42 = 0;
    goto LABEL_28;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v42, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a2,
                           StringRawBuffer) )
  {
    v4 = -2147024882;
    v26 = -2147024882;
    goto LABEL_31;
  }
  WindowsDeleteString(v42);
  v42 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  v28 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  WindowsDeleteString(string);
  v30 = v37;
  string = 0;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  v31 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v4 = 0;
LABEL_43:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v44);
  return v4;
}

```

## disassembly

```asm
0x1800b2f8c  mov     [rsp-8+arg_10], rbx
0x1800b2f91  mov     [rsp-8+arg_18], rsi
0x1800b2f96  push    rbp
0x1800b2f97  push    rdi
0x1800b2f98  push    r14
0x1800b2f9a  lea     rbp, [rsp-47h]
0x1800b2f9f  sub     rsp, 0C0h
0x1800b2fa6  mov     rax, cs:__security_cookie
0x1800b2fad  xor     rax, rsp
0x1800b2fb0  mov     [rbp+57h+var_18], rax
0x1800b2fb4  xorps   xmm0, xmm0
0x1800b2fb7  mov     r8, rcx
0x1800b2fba  lea     rcx, [rbp+57h+var_38]
0x1800b2fbe  mov     rsi, rdx
0x1800b2fc1  movups  [rbp+57h+var_38], xmm0
0x1800b2fc5  movups  [rbp+57h+var_28], xmm0
0x1800b2fc9  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800b2fce  mov     rdx, r8
0x1800b2fd1  lea     rcx, [rbp+57h+var_38]
0x1800b2fd5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800b2fda  xor     r14d, r14d
0x1800b2fdd  test    al, al
0x1800b2fdf  jnz     short loc_1800B2FF8
0x1800b2fe1  mov     ebx, 8007000Eh
0x1800b2fe6  lea     r9d, [r14+73h]
0x1800b2fea  mov     ecx, ebx; int
0x1800b2fec  xor     edx, edx
0x1800b2fee  call    Log_HREvent_94
0x1800b2ff3  jmp     loc_1800B33B7
0x1800b2ff8  mov     r9d, 31h ; '1'; unsigned int
0x1800b2ffe  mov     [rbp+57h+var_78], r14
0x1800b3002  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x1800b3009  mov     [rbp+57h+var_88], r14
0x1800b300d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b3011  lea     r8d, [r9+1]; unsigned int
0x1800b3015  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b301a  mov     rcx, [rbp+57h+var_88]
0x1800b301e  lea     r8, [rbp+57h+var_78]
0x1800b3022  lea     rdx, _GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb
0x1800b3029  call    cs:__imp_RoGetActivationFactory
0x1800b302f  mov     ebx, eax
0x1800b3031  test    eax, eax
0x1800b3033  jns     short loc_1800B306A
0x1800b3035  mov     edx, 1
0x1800b303a  mov     ecx, eax; int
0x1800b303c  lea     r9d, [rdx+77h]
0x1800b3040  call    Log_HREvent_94
0x1800b3045  mov     rdx, [rbp+57h+var_78]
0x1800b3049  test    rdx, rdx
0x1800b304c  jz      loc_1800B33B7
0x1800b3052  mov     [rbp+57h+var_78], r14
0x1800b3056  mov     rcx, [rdx]
0x1800b3059  mov     rax, [rcx+10h]
0x1800b305d  mov     rcx, rdx
0x1800b3060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3065  jmp     loc_1800B33B7
0x1800b306a  mov     rdi, [rbp+57h+var_78]
0x1800b306e  lea     rcx, [rbp+57h+var_50]
0x1800b3072  mov     [rbp+57h+var_50], r14
0x1800b3076  mov     rax, [rdi]
0x1800b3079  mov     rbx, [rax+78h]
0x1800b307d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3082  mov     rcx, qword ptr [rbp+57h+var_38]
0x1800b3086  lea     rdx, [rbp+57h+var_80]
0x1800b308a  mov     [rbp+57h+var_80], rcx
0x1800b308e  lea     rcx, [rbp+57h+hstringHeader]
0x1800b3092  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b3097  lea     r9, [rbp+57h+var_50]
0x1800b309b  xor     r8d, r8d
0x1800b309e  mov     rcx, rdi
0x1800b30a1  mov     rdx, [rax+18h]
0x1800b30a5  mov     rax, rbx
0x1800b30a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b30ad  mov     ebx, eax
0x1800b30af  test    eax, eax
0x1800b30b1  jns     short loc_1800B30E9
0x1800b30b3  mov     edx, 1
0x1800b30b8  mov     ecx, eax; int
0x1800b30ba  lea     r9d, [rdx+7Bh]
0x1800b30be  call    Log_HREvent_94
0x1800b30c3  lea     rcx, [rbp+57h+var_50]
0x1800b30c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b30cc  mov     rcx, [rbp+57h+var_78]
0x1800b30d0  test    rcx, rcx
0x1800b30d3  jz      loc_1800B33B7
0x1800b30d9  mov     [rbp+57h+var_78], r14
0x1800b30dd  mov     rax, [rcx]
0x1800b30e0  mov     rax, [rax+10h]
0x1800b30e4  jmp     loc_1800B3060
0x1800b30e9  mov     r9d, 35h ; '5'; unsigned int
0x1800b30ef  mov     [rbp+57h+var_70], r14
0x1800b30f3  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmNames@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800b30fa  mov     [rbp+57h+var_88], r14
0x1800b30fe  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b3102  lea     r8d, [r9+1]; unsigned int
0x1800b3106  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b310b  mov     rcx, [rbp+57h+var_88]
0x1800b310f  lea     r8, [rbp+57h+var_70]
0x1800b3113  lea     rdx, _GUID_6b5e0516_de96_4f0a_8d57_dcc9dae36c76
0x1800b311a  call    cs:__imp_RoGetActivationFactory
0x1800b3120  mov     ebx, eax
0x1800b3122  test    eax, eax
0x1800b3124  jns     short loc_1800B3156
0x1800b3126  mov     edx, 1
0x1800b312b  mov     r9d, 82h
0x1800b3131  mov     ecx, eax; int
0x1800b3133  call    Log_HREvent_94
0x1800b3138  mov     rcx, [rbp+57h+var_70]
0x1800b313c  test    rcx, rcx
0x1800b313f  jz      short loc_1800B30C3
0x1800b3141  mov     [rbp+57h+var_70], r14
0x1800b3145  mov     rax, [rcx]
0x1800b3148  mov     rax, [rax+10h]
0x1800b314c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3151  jmp     loc_1800B30C3
0x1800b3156  mov     rdi, [rbp+57h+var_70]
0x1800b315a  xor     ecx, ecx; string
0x1800b315c  mov     [rbp+57h+string], r14
0x1800b3160  mov     rax, [rdi]
0x1800b3163  mov     rbx, [rax+30h]
0x1800b3167  call    cs:__imp_WindowsDeleteString
0x1800b316d  lea     rdx, [rbp+57h+string]
0x1800b3171  mov     [rbp+57h+string], r14
0x1800b3175  mov     rcx, rdi
0x1800b3178  mov     rax, rbx
0x1800b317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3180  mov     ebx, eax
0x1800b3182  test    eax, eax
0x1800b3184  jns     short loc_1800B31A8
0x1800b3186  mov     edx, 1
0x1800b318b  mov     r9d, 85h
0x1800b3191  mov     ecx, eax; int
0x1800b3193  call    Log_HREvent_94
0x1800b3198  mov     rcx, [rbp+57h+string]; string
0x1800b319c  call    cs:__imp_WindowsDeleteString
0x1800b31a2  mov     [rbp+57h+string], r14
0x1800b31a6  jmp     short loc_1800B3138
0x1800b31a8  mov     r9d, 38h ; '8'; unsigned int
0x1800b31ae  mov     [rbp+57h+var_60], r14
0x1800b31b2  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_Core_HashAlgorithmProvider@@3QBGB; "Windows.Security.Cryptography.Core.Hash"...
0x1800b31b9  mov     [rbp+57h+var_88], r14
0x1800b31bd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b31c1  lea     r8d, [r9+1]; unsigned int
0x1800b31c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b31ca  mov     rcx, [rbp+57h+var_88]
0x1800b31ce  lea     r8, [rbp+57h+var_60]
0x1800b31d2  lea     rdx, _GUID_9fac9741_5cc4_4336_ae38_6212b75a915a
0x1800b31d9  call    cs:__imp_RoGetActivationFactory
0x1800b31df  mov     ebx, eax
0x1800b31e1  test    eax, eax
0x1800b31e3  jns     short loc_1800B3212
0x1800b31e5  mov     edx, 1
0x1800b31ea  mov     r9d, 8Bh
0x1800b31f0  mov     ecx, eax; int
0x1800b31f2  call    Log_HREvent_94
0x1800b31f7  mov     rcx, [rbp+57h+var_60]
0x1800b31fb  test    rcx, rcx
0x1800b31fe  jz      short loc_1800B3198
0x1800b3200  mov     [rbp+57h+var_60], r14
0x1800b3204  mov     rax, [rcx]
0x1800b3207  mov     rax, [rax+10h]
0x1800b320b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3210  jmp     short loc_1800B3198
0x1800b3212  mov     rcx, [rbp+57h+var_60]
0x1800b3216  lea     r8, [rbp+57h+var_58]
0x1800b321a  mov     rdx, [rbp+57h+string]
0x1800b321e  mov     [rbp+57h+var_58], r14
0x1800b3222  mov     rax, [rcx]
0x1800b3225  mov     rax, [rax+30h]
0x1800b3229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b322e  mov     ebx, eax
0x1800b3230  test    eax, eax
0x1800b3232  jns     short loc_1800B3261
0x1800b3234  mov     edx, 1
0x1800b3239  mov     r9d, 8Eh
0x1800b323f  mov     ecx, eax; int
0x1800b3241  call    Log_HREvent_94
0x1800b3246  mov     rcx, [rbp+57h+var_58]
0x1800b324a  test    rcx, rcx
0x1800b324d  jz      short loc_1800B31F7
0x1800b324f  mov     [rbp+57h+var_58], r14
0x1800b3253  mov     rax, [rcx]
0x1800b3256  mov     rax, [rax+10h]
0x1800b325a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b325f  jmp     short loc_1800B31F7
0x1800b3261  mov     rcx, [rbp+57h+var_58]
0x1800b3265  lea     r8, [rbp+57h+var_40]
0x1800b3269  mov     rdx, [rbp+57h+var_50]
0x1800b326d  mov     [rbp+57h+var_40], r14
0x1800b3271  mov     rax, [rcx]
0x1800b3274  mov     rax, [rax+40h]
0x1800b3278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b327d  mov     ebx, eax
0x1800b327f  test    eax, eax
0x1800b3281  jns     short loc_1800B32A0
0x1800b3283  mov     edx, 1
0x1800b3288  mov     r9d, 91h
0x1800b328e  mov     ecx, eax; int
0x1800b3290  call    Log_HREvent_94
0x1800b3295  lea     rcx, [rbp+57h+var_40]
0x1800b3299  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b329e  jmp     short loc_1800B3246
0x1800b32a0  mov     rdi, [rbp+57h+var_78]
0x1800b32a4  xor     ecx, ecx; string
0x1800b32a6  mov     [rbp+57h+var_48], r14
0x1800b32aa  mov     rax, [rdi]
0x1800b32ad  mov     rbx, [rax+60h]
0x1800b32b1  call    cs:__imp_WindowsDeleteString
0x1800b32b7  mov     rdx, [rbp+57h+var_40]
0x1800b32bb  lea     r8, [rbp+57h+var_48]
0x1800b32bf  mov     rcx, rdi
0x1800b32c2  mov     [rbp+57h+var_48], r14
0x1800b32c6  mov     rax, rbx
0x1800b32c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b32ce  mov     ebx, eax
0x1800b32d0  test    eax, eax
0x1800b32d2  jns     short loc_1800B32F6
0x1800b32d4  mov     edx, 1
0x1800b32d9  mov     r9d, 95h
0x1800b32df  mov     ecx, eax; int
0x1800b32e1  call    Log_HREvent_94
0x1800b32e6  mov     rcx, [rbp+57h+var_48]; string
0x1800b32ea  call    cs:__imp_WindowsDeleteString
0x1800b32f0  mov     [rbp+57h+var_48], r14
0x1800b32f4  jmp     short loc_1800B3295
0x1800b32f6  mov     rcx, [rbp+57h+var_48]; string
0x1800b32fa  xor     edx, edx; length
0x1800b32fc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b3302  mov     rdx, rax
0x1800b3305  mov     rcx, rsi
0x1800b3308  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800b330d  test    al, al
0x1800b330f  jnz     short loc_1800B3322
0x1800b3311  mov     ebx, 8007000Eh
0x1800b3316  xor     edx, edx
0x1800b3318  mov     ecx, ebx
0x1800b331a  mov     r9d, 97h
0x1800b3320  jmp     short loc_1800B32E1
0x1800b3322  mov     rcx, [rbp+57h+var_48]; string
0x1800b3326  call    cs:__imp_WindowsDeleteString
0x1800b332c  lea     rcx, [rbp+57h+var_40]
0x1800b3330  mov     [rbp+57h+var_48], r14
0x1800b3334  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3339  mov     rcx, [rbp+57h+var_58]
0x1800b333d  test    rcx, rcx
0x1800b3340  jz      short loc_1800B3352
0x1800b3342  mov     [rbp+57h+var_58], r14
0x1800b3346  mov     rax, [rcx]
0x1800b3349  mov     rax, [rax+10h]
0x1800b334d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3352  mov     rcx, [rbp+57h+var_60]
0x1800b3356  test    rcx, rcx
0x1800b3359  jz      short loc_1800B336B
0x1800b335b  mov     [rbp+57h+var_60], r14
0x1800b335f  mov     rax, [rcx]
0x1800b3362  mov     rax, [rax+10h]
0x1800b3366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b336b  mov     rcx, [rbp+57h+string]; string
0x1800b336f  call    cs:__imp_WindowsDeleteString
0x1800b3375  mov     rcx, [rbp+57h+var_70]
0x1800b3379  mov     [rbp+57h+string], r14
0x1800b337d  test    rcx, rcx
0x1800b3380  jz      short loc_1800B3392
0x1800b3382  mov     [rbp+57h+var_70], r14
0x1800b3386  mov     rax, [rcx]
0x1800b3389  mov     rax, [rax+10h]
0x1800b338d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3392  lea     rcx, [rbp+57h+var_50]
0x1800b3396  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b339b  mov     rcx, [rbp+57h+var_78]
0x1800b339f  test    rcx, rcx
0x1800b33a2  jz      short loc_1800B33B4
0x1800b33a4  mov     [rbp+57h+var_78], r14
0x1800b33a8  mov     rax, [rcx]
0x1800b33ab  mov     rax, [rax+10h]
0x1800b33af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b33b4  mov     ebx, r14d
0x1800b33b7  lea     rcx, [rbp+57h+var_38]
0x1800b33bb  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800b33c0  mov     eax, ebx
0x1800b33c2  mov     rcx, [rbp+57h+var_18]
0x1800b33c6  xor     rcx, rsp; StackCookie
0x1800b33c9  call    __security_check_cookie
0x1800b33ce  lea     r11, [rsp+0D0h+var_10]
0x1800b33d6  mov     rbx, [r11+30h]
0x1800b33da  mov     rsi, [r11+38h]
0x1800b33de  mov     rsp, r11
0x1800b33e1  pop     r14
0x1800b33e3  pop     rdi
0x1800b33e4  pop     rbp
0x1800b33e5  retn
```
