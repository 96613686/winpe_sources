# BingMapsJson::ReverseGeocodeJsonParser::LoadJsonString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180143dec`
- end: `0x180143f6f`
- name: `?LoadJsonString@ReverseGeocodeJsonParser@BingMapsJson@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011de80`

## callees

- `0x180012310`
- `0x1800142c4`
- `0x180020c64`
- `0x1800a98c0`
- `0x180143dec`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180143e52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180143e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180143e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180143e39`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180143e7b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180143e7b`

## string_xrefs

- `0x180143e32`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BingMapsJson::ReverseGeocodeJsonParser::LoadJsonString(__int64 a1, __int64 a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v11; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v12[32]; // [rsp+28h] [rbp-21h] BYREF
  __int64 v13; // [rsp+48h] [rbp-1h] BYREF
  int v14; // [rsp+50h] [rbp+7h] BYREF
  __int64 v15; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING hstringHeader[4]; // [rsp+60h] [rbp+17h] BYREF

  memset(hstringHeader, 0, sizeof(hstringHeader));
  if ( WindowsCreateStringReference(
         L"Windows.Data.Json.JsonValue",
         0x1Bu,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v15 = 0;
  v4 = hstringHeader[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v15);
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    v6 = v15;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v8);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v12, &v11);
    ActivationFactory = v7(v6, *(_QWORD *)(v9 + 24), &v13);
    if ( ActivationFactory >= 0 )
    {
      v14 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 48LL))(v13, &v14);
      if ( ActivationFactory >= 0 )
      {
        if ( v14 != 5 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
          ActivationFactory = -2147024883;
          goto LABEL_11;
        }
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 96LL))(v13, a1);
        if ( ActivationFactory >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
          ActivationFactory = 0;
          goto LABEL_11;
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  }
LABEL_11:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180143dec  mov     [rsp-8+arg_10], rbx
0x180143df1  mov     [rsp-8+arg_18], rsi
0x180143df6  push    rbp
0x180143df7  push    rdi
0x180143df8  push    r14
0x180143dfa  lea     rbp, [rsp-47h]
0x180143dff  sub     rsp, 90h
0x180143e06  mov     rax, cs:__security_cookie
0x180143e0d  xor     rax, rsp
0x180143e10  mov     [rbp+57h+var_20], rax
0x180143e14  mov     r14, rdx
0x180143e17  mov     rsi, rcx
0x180143e1a  xorps   xmm0, xmm0
0x180143e1d  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180143e21  movups  xmmword ptr [rbp+57h+hstringHeader+10h], xmm0
0x180143e25  lea     r9, [rbp+57h+hstringHeader]; string
0x180143e29  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180143e2d  mov     edx, 1Bh; length
0x180143e32  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180143e39  call    cs:__imp_WindowsCreateStringReference
0x180143e3f  test    eax, eax
0x180143e41  jns     short loc_180143E58
0x180143e43  xor     r9d, r9d; lpArguments
0x180143e46  xor     r8d, r8d; nNumberOfArguments
0x180143e49  lea     edx, [r9+1]; dwExceptionFlags
0x180143e4d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180143e52  call    cs:__imp_RaiseException
0x180143e58  mov     [rbp+57h+var_48], 0
0x180143e60  mov     rbx, qword ptr [rbp+57h+hstringHeader]
0x180143e64  lea     rcx, [rbp+57h+var_48]
0x180143e68  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143e6d  lea     r8, [rbp+57h+var_48]
0x180143e71  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180143e78  mov     rcx, rbx
0x180143e7b  call    cs:__imp_RoGetActivationFactory
0x180143e81  mov     ebx, eax
0x180143e83  test    eax, eax
0x180143e85  js      loc_180143F40
0x180143e8b  mov     [rbp+57h+var_58], 0
0x180143e93  mov     rdi, [rbp+57h+var_48]
0x180143e97  mov     rax, [rdi]
0x180143e9a  mov     rbx, [rax+30h]
0x180143e9e  lea     rcx, [rbp+57h+var_58]
0x180143ea2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143ea7  mov     rcx, r14
0x180143eaa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180143eaf  mov     [rbp+57h+var_80], rax
0x180143eb3  lea     rdx, [rbp+57h+var_80]
0x180143eb7  lea     rcx, [rbp+57h+var_78]
0x180143ebb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180143ec0  nop
0x180143ec1  lea     r8, [rbp+57h+var_58]
0x180143ec5  mov     rdx, [rax+18h]
0x180143ec9  mov     rcx, rdi
0x180143ecc  mov     rax, rbx
0x180143ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ed4  mov     ebx, eax
0x180143ed6  test    eax, eax
0x180143ed8  jns     short loc_180143EE5
0x180143eda  lea     rcx, [rbp+57h+var_58]
0x180143ede  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143ee3  jmp     short loc_180143F40
0x180143ee5  mov     [rbp+57h+var_50], 0
0x180143eec  mov     rcx, [rbp+57h+var_58]
0x180143ef0  mov     rax, [rcx]
0x180143ef3  lea     rdx, [rbp+57h+var_50]
0x180143ef7  mov     rax, [rax+30h]
0x180143efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143f00  mov     ebx, eax
0x180143f02  test    eax, eax
0x180143f04  js      short loc_180143EDA
0x180143f06  cmp     [rbp+57h+var_50], 5
0x180143f0a  jz      short loc_180143F1C
0x180143f0c  lea     rcx, [rbp+57h+var_58]
0x180143f10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143f15  mov     ebx, 8007000Dh
0x180143f1a  jmp     short loc_180143F40
0x180143f1c  mov     rcx, [rbp+57h+var_58]
0x180143f20  mov     rax, [rcx]
0x180143f23  mov     rdx, rsi
0x180143f26  mov     rax, [rax+60h]
0x180143f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143f2f  mov     ebx, eax
0x180143f31  lea     rcx, [rbp+57h+var_58]
0x180143f35  test    eax, eax
0x180143f37  js      short loc_180143EDE
0x180143f39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143f3e  xor     ebx, ebx
0x180143f40  lea     rcx, [rbp+57h+var_48]
0x180143f44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180143f49  mov     eax, ebx
0x180143f4b  mov     rcx, [rbp+57h+var_20]
0x180143f4f  xor     rcx, rsp; StackCookie
0x180143f52  call    __security_check_cookie
0x180143f57  lea     r11, [rsp+0A0h+var_10]
0x180143f5f  mov     rbx, [r11+30h]
0x180143f63  mov     rsi, [r11+38h]
0x180143f67  mov     rsp, r11
0x180143f6a  pop     r14
0x180143f6c  pop     rdi
0x180143f6d  pop     rbp
0x180143f6e  retn
```
