# UCOneSettingsHandler::GetPayloadFromWOSC(ushort const *)

- ea: `0x140007ef4`
- end: `0x14000818a`
- name: `?GetPayloadFromWOSC@UCOneSettingsHandler@@SAJPEBG@Z`
- size: `662`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140007c60`

## callees

- `0x1400014c0`
- `0x140007cb0`
- `0x140007eac`
- `0x140007ef4`
- `0x140008190`
- `0x1400081bc`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140008168`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140008168`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140007f75`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140007f75`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140007f25`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140007f25`

## string_xrefs

- `0x140008044`: `CONFIG`

## pseudocode

```c
__int64 __fastcall UCOneSettingsHandler::GetPayloadFromWOSC(const unsigned __int16 *a1)
{
  __int64 result; // rax
  __int64 v2; // rbx
  int ActivationFactory; // ebx
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, const wchar_t **); // rbx
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-49h] BYREF
  const wchar_t *v16; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+48h] [rbp-31h] BYREF
  const wchar_t *v19; // [rsp+50h] [rbp-29h] BYREF
  __int64 v20; // [rsp+58h] [rbp-21h] BYREF
  char v21; // [rsp+61h] [rbp-18h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-11h] BYREF
  __int64 v23; // [rsp+80h] [rbp+7h]
  char v24[32]; // [rsp+88h] [rbp+Fh] BYREF

  v19 = L"UECPL";
  result = RoInitialize(1);
  if ( (int)result >= 0 )
  {
    v21 = 1;
    v20 = 0;
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
      0x3Au,
      0x39u);
    v2 = v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v20);
    ActivationFactory = RoGetActivationFactory(v2, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v20);
    if ( ActivationFactory >= 0 )
    {
      v15 = 0;
      v4 = v20;
      v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v20 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v15);
      v23 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &sourceString, 1u, 0);
      v6 = v23;
      v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, &v19);
      ActivationFactory = v5(v4, *(_QWORD *)(v7 + 24), v6, &v15);
      if ( ActivationFactory >= 0 )
      {
        v18 = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 96LL))(v15, &v18);
        if ( ActivationFactory >= 0 )
        {
          v17 = 0;
          v8 = v18;
          v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v18 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
          v23 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"CONFIG", 7u, 6u);
          ActivationFactory = v9(v8, v23, &v17);
          if ( ActivationFactory >= 0 )
          {
            v16 = 0;
            v10 = v17;
            v11 = *(__int64 (__fastcall **)(__int64, __int64, const wchar_t **))(*(_QWORD *)v17 + 72LL);
            v23 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DATA", 5u, 4u);
            ActivationFactory = v11(v10, v23, &v16);
            if ( ActivationFactory >= 0 )
            {
              v19 = v16;
              if ( v16 )
                (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v16 + 8LL))(v16);
              ActivationFactory = UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer(&v19);
              if ( ActivationFactory >= 0 )
              {
                v14 = v16;
                if ( v16 )
                {
                  v16 = 0;
                  (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v14 + 16LL))(v14);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v18);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v15);
                ActivationFactory = 0;
                goto LABEL_22;
              }
              v13 = v16;
              if ( v16 )
              {
                v16 = 0;
                (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v13 + 16LL))(v13);
              }
            }
            else
            {
              v12 = v16;
              if ( v16 )
              {
                v16 = 0;
                (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v12 + 16LL))(v12);
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v18);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v15);
    }
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v20);
    RoUninitialize();
    return (unsigned int)ActivationFactory;
  }
  return result;
}

```

## disassembly

```asm
0x140007ef4  push    rbp
0x140007ef6  push    rbx
0x140007ef7  push    rsi
0x140007ef8  push    rdi
0x140007ef9  push    r14
0x140007efb  lea     rbp, [rsp-37h]
0x140007f00  sub     rsp, 0B0h
0x140007f07  mov     rax, cs:__security_cookie
0x140007f0e  xor     rax, rsp
0x140007f11  mov     [rbp+57h+var_28], rax
0x140007f15  lea     rax, aUecpl; "UECPL"
0x140007f1c  mov     [rbp+57h+var_80], rax
0x140007f20  mov     ecx, 1
0x140007f25  call    cs:__imp_RoInitialize
0x140007f2b  xor     r14d, r14d
0x140007f2e  test    eax, eax
0x140007f30  js      loc_140008170
0x140007f36  mov     [rbp+57h+var_6F], 1
0x140007f3a  mov     [rbp+57h+var_78], r14
0x140007f3e  mov     [rbp+57h+var_50], r14
0x140007f42  lea     r9d, [r14+39h]; unsigned int
0x140007f46  lea     r8d, [r14+3Ah]; unsigned int
0x140007f4a  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x140007f51  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140007f55  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140007f5a  mov     rbx, [rbp+57h+var_50]
0x140007f5e  lea     rcx, [rbp+57h+var_78]
0x140007f62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140007f67  lea     r8, [rbp+57h+var_78]
0x140007f6b  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x140007f72  mov     rcx, rbx
0x140007f75  call    cs:__imp_RoGetActivationFactory
0x140007f7b  mov     ebx, eax
0x140007f7d  test    eax, eax
0x140007f7f  js      loc_14000815E
0x140007f85  mov     [rbp+57h+var_A0], r14
0x140007f89  mov     rsi, [rbp+57h+var_78]
0x140007f8d  mov     rax, [rsi]
0x140007f90  mov     rdi, [rax+38h]
0x140007f94  lea     rcx, [rbp+57h+var_A0]
0x140007f98  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140007f9d  mov     [rbp+57h+var_50], r14
0x140007fa1  xor     r9d, r9d; unsigned int
0x140007fa4  lea     r8d, [r14+1]; unsigned int
0x140007fa8  lea     rdx, sourceString; sourceString
0x140007faf  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140007fb3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140007fb8  nop
0x140007fb9  mov     rbx, [rbp+57h+var_50]
0x140007fbd  lea     rdx, [rbp+57h+var_80]
0x140007fc1  lea     rcx, [rbp+57h+var_48]
0x140007fc5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140007fca  nop
0x140007fcb  lea     r9, [rbp+57h+var_A0]
0x140007fcf  mov     r8, rbx
0x140007fd2  mov     rdx, [rax+18h]
0x140007fd6  mov     rcx, rsi
0x140007fd9  mov     rax, rdi
0x140007fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fe1  mov     ebx, eax
0x140007fe3  test    eax, eax
0x140007fe5  jns     short loc_140007FF5
0x140007fe7  lea     rcx, [rbp+57h+var_A0]
0x140007feb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140007ff0  jmp     loc_14000815E
0x140007ff5  mov     [rbp+57h+var_88], r14
0x140007ff9  mov     rcx, [rbp+57h+var_A0]
0x140007ffd  mov     rax, [rcx]
0x140008000  lea     rdx, [rbp+57h+var_88]
0x140008004  mov     rax, [rax+60h]
0x140008008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000800d  mov     ebx, eax
0x14000800f  test    eax, eax
0x140008011  jns     short loc_14000801E
0x140008013  lea     rcx, [rbp+57h+var_88]
0x140008017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x14000801c  jmp     short loc_140007FE7
0x14000801e  mov     [rbp+57h+var_90], r14
0x140008022  mov     rdi, [rbp+57h+var_88]
0x140008026  mov     rax, [rdi]
0x140008029  mov     rbx, [rax+40h]
0x14000802d  lea     rcx, [rbp+57h+var_90]
0x140008031  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008036  mov     [rbp+57h+var_50], r14
0x14000803a  mov     r9d, 6; unsigned int
0x140008040  lea     r8d, [r9+1]; unsigned int
0x140008044  lea     rdx, aConfig; "CONFIG"
0x14000804b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14000804f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140008054  nop
0x140008055  lea     r8, [rbp+57h+var_90]
0x140008059  mov     rdx, [rbp+57h+var_50]
0x14000805d  mov     rcx, rdi
0x140008060  mov     rax, rbx
0x140008063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008068  mov     ebx, eax
0x14000806a  test    eax, eax
0x14000806c  jns     short loc_140008079
0x14000806e  lea     rcx, [rbp+57h+var_90]
0x140008072  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008077  jmp     short loc_140008013
0x140008079  mov     [rbp+57h+var_98], r14
0x14000807d  mov     rdi, [rbp+57h+var_90]
0x140008081  mov     rax, [rdi]
0x140008084  mov     rbx, [rax+48h]
0x140008088  mov     [rbp+57h+var_50], r14
0x14000808c  mov     r9d, 4; unsigned int
0x140008092  lea     r8d, [r9+1]; unsigned int
0x140008096  lea     rdx, aData; "DATA"
0x14000809d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1400080a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400080a6  nop
0x1400080a7  lea     r8, [rbp+57h+var_98]
0x1400080ab  mov     rdx, [rbp+57h+var_50]
0x1400080af  mov     rcx, rdi
0x1400080b2  mov     rax, rbx
0x1400080b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080ba  mov     ebx, eax
0x1400080bc  test    eax, eax
0x1400080be  jns     short loc_1400080DC
0x1400080c0  mov     rcx, [rbp+57h+var_98]
0x1400080c4  test    rcx, rcx
0x1400080c7  jz      short loc_1400080DA
0x1400080c9  mov     [rbp+57h+var_98], r14
0x1400080cd  mov     rdx, [rcx]
0x1400080d0  mov     rax, [rdx+10h]
0x1400080d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080d9  nop
0x1400080da  jmp     short loc_14000806E
0x1400080dc  mov     rcx, [rbp+57h+var_98]
0x1400080e0  mov     [rbp+57h+var_80], rcx
0x1400080e4  test    rcx, rcx
0x1400080e7  jz      short loc_1400080F6
0x1400080e9  mov     rax, [rcx]
0x1400080ec  mov     rax, [rax+8]
0x1400080f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080f5  nop
0x1400080f6  lea     rcx, [rbp+57h+var_80]
0x1400080fa  call    ?ParsePayloadAndUpdateWNFBuffer@UCOneSettingsHandler@@CAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Z; UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>)
0x1400080ff  mov     ebx, eax
0x140008101  test    eax, eax
0x140008103  jns     short loc_140008124
0x140008105  mov     rcx, [rbp+57h+var_98]
0x140008109  test    rcx, rcx
0x14000810c  jz      short loc_14000811F
0x14000810e  mov     [rbp+57h+var_98], r14
0x140008112  mov     rdx, [rcx]
0x140008115  mov     rax, [rdx+10h]
0x140008119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000811e  nop
0x14000811f  jmp     loc_14000806E
0x140008124  mov     rcx, [rbp+57h+var_98]
0x140008128  test    rcx, rcx
0x14000812b  jz      short loc_14000813E
0x14000812d  mov     [rbp+57h+var_98], r14
0x140008131  mov     rax, [rcx]
0x140008134  mov     rax, [rax+10h]
0x140008138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000813d  nop
0x14000813e  lea     rcx, [rbp+57h+var_90]
0x140008142  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008147  nop
0x140008148  lea     rcx, [rbp+57h+var_88]
0x14000814c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008151  nop
0x140008152  lea     rcx, [rbp+57h+var_A0]
0x140008156  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x14000815b  mov     ebx, r14d
0x14000815e  lea     rcx, [rbp+57h+var_78]
0x140008162  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008167  nop
0x140008168  call    cs:__imp_RoUninitialize
0x14000816e  mov     eax, ebx
0x140008170  mov     rcx, [rbp+57h+var_28]
0x140008174  xor     rcx, rsp; StackCookie
0x140008177  call    __security_check_cookie
0x14000817c  add     rsp, 0B0h
0x140008183  pop     r14
0x140008185  pop     rdi
0x140008186  pop     rsi
0x140008187  pop     rbx
0x140008188  pop     rbp
0x140008189  retn
```
