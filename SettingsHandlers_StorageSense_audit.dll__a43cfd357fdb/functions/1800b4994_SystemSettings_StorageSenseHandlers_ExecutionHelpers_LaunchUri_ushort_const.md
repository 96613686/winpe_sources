# SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchUri(ushort const *)

- ea: `0x1800b4994`
- end: `0x1800b4b2d`
- name: `?LaunchUri@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEBG@Z`
- size: `409`
- prototype: `__int64 __fastcall(PCWSTR sourceString, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800575d0`
- `0x1800579e0`
- `0x180057cfc`
- `0x180058010`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180022a1c`
- `0x180035ee0`
- `0x180036c74`
- `0x1800b4994`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b49f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4a58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b49f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b49e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b49e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a6c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4aae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4aae`

## string_xrefs

- `0x1800b49d9`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::ExecutionHelpers::LaunchUri(
        PCWSTR sourceString,
        const unsigned __int16 *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, HSTRING, __int64 *); // rsi
  unsigned __int64 v6; // rcx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  __int64 v13; // [rsp+28h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF

  v14 = 0;
  v16 = 0;
  v13 = 0;
  v15 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                        string,
                        &v16);
  if ( ActivationFactory >= 0 )
  {
    v4 = v16;
    v5 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v13);
    length = 0;
    v6 = -1;
    do
      ++v6;
    while ( sourceString[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
    ActivationFactory = v5(v4, string, &v13);
    if ( ActivationFactory >= 0 )
    {
      v8 = *(_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[24])v7);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v14);
      ActivationFactory = RoGetActivationFactory(v8, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v14);
      if ( ActivationFactory >= 0 )
      {
        v9 = v14;
        v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v14 + 64LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
        ActivationFactory = v10(v9, v13, &v15);
      }
    }
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v14);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800b4994  mov     [rsp-18h+arg_8], rbx
0x1800b4999  mov     [rsp-18h+arg_10], rsi
0x1800b499e  push    rbp
0x1800b499f  push    rdi
0x1800b49a0  push    r14
0x1800b49a2  mov     rbp, rsp
0x1800b49a5  sub     rsp, 70h
0x1800b49a9  mov     rax, cs:__security_cookie
0x1800b49b0  xor     rax, rsp
0x1800b49b3  mov     [rbp+var_8], rax
0x1800b49b7  mov     rdi, rcx
0x1800b49ba  xor     r14d, r14d
0x1800b49bd  mov     [rbp+var_40], r14
0x1800b49c1  mov     [rbp+var_30], r14
0x1800b49c5  mov     [rbp+var_48], r14
0x1800b49c9  mov     [rbp+var_38], r14
0x1800b49cd  lea     r9, [rbp+string]; string
0x1800b49d1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800b49d5  lea     edx, [r14+16h]; length
0x1800b49d9  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800b49e0  call    cs:__imp_WindowsCreateStringReference
0x1800b49e6  test    eax, eax
0x1800b49e8  jns     short loc_1800B49FF
0x1800b49ea  xor     r9d, r9d; lpArguments
0x1800b49ed  xor     r8d, r8d; nNumberOfArguments
0x1800b49f0  lea     edx, [r14+1]; dwExceptionFlags
0x1800b49f4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b49f9  call    cs:__imp_RaiseException
0x1800b49ff  lea     rdx, [rbp+var_30]
0x1800b4a03  mov     rcx, [rbp+string]
0x1800b4a07  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800b4a0c  mov     ebx, eax
0x1800b4a0e  test    eax, eax
0x1800b4a10  js      loc_1800B4AE3
0x1800b4a16  mov     rbx, [rbp+var_30]
0x1800b4a1a  mov     rax, [rbx]
0x1800b4a1d  mov     rsi, [rax+30h]
0x1800b4a21  lea     rcx, [rbp+var_48]
0x1800b4a25  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4a2a  mov     [rbp+length], r14d
0x1800b4a2e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b4a32  inc     rcx; unsigned __int64
0x1800b4a35  cmp     [rdi+rcx*2], r14w
0x1800b4a3a  jnz     short loc_1800B4A32
0x1800b4a3c  lea     rdx, [rbp+length]; unsigned int *
0x1800b4a40  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b4a45  test    eax, eax
0x1800b4a47  jns     short loc_1800B4A5E
0x1800b4a49  xor     r9d, r9d; lpArguments
0x1800b4a4c  xor     r8d, r8d; nNumberOfArguments
0x1800b4a4f  lea     edx, [r9+1]; dwExceptionFlags
0x1800b4a53  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b4a58  call    cs:__imp_RaiseException
0x1800b4a5e  lea     r9, [rbp+string]; string
0x1800b4a62  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800b4a66  mov     edx, [rbp+length]; length
0x1800b4a69  mov     rcx, rdi; sourceString
0x1800b4a6c  call    cs:__imp_WindowsCreateStringReference
0x1800b4a72  lea     r8, [rbp+var_48]
0x1800b4a76  mov     rdx, [rbp+string]
0x1800b4a7a  mov     rcx, rbx
0x1800b4a7d  mov     rax, rsi
0x1800b4a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a85  mov     ebx, eax
0x1800b4a87  test    eax, eax
0x1800b4a89  js      short loc_1800B4AE3
0x1800b4a8b  lea     rcx, [rbp+string]; string
0x1800b4a8f  call    ??$?0$0BI@@StringReference@Internal@Windows@@QEAA@AEAY0BI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[24])
0x1800b4a94  mov     rbx, [rax]
0x1800b4a97  lea     rcx, [rbp+var_40]
0x1800b4a9b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4aa0  lea     r8, [rbp+var_40]
0x1800b4aa4  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x1800b4aab  mov     rcx, rbx
0x1800b4aae  call    cs:__imp_RoGetActivationFactory
0x1800b4ab4  mov     ebx, eax
0x1800b4ab6  test    eax, eax
0x1800b4ab8  js      short loc_1800B4AE3
0x1800b4aba  mov     rdi, [rbp+var_40]
0x1800b4abe  mov     rax, [rdi]
0x1800b4ac1  mov     rbx, [rax+40h]
0x1800b4ac5  lea     rcx, [rbp+var_38]
0x1800b4ac9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4ace  lea     r8, [rbp+var_38]
0x1800b4ad2  mov     rdx, [rbp+var_48]
0x1800b4ad6  mov     rcx, rdi
0x1800b4ad9  mov     rax, rbx
0x1800b4adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ae1  mov     ebx, eax
0x1800b4ae3  lea     rcx, [rbp+var_38]
0x1800b4ae7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4aec  nop
0x1800b4aed  lea     rcx, [rbp+var_48]
0x1800b4af1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4af6  nop
0x1800b4af7  lea     rcx, [rbp+var_30]
0x1800b4afb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4b00  nop
0x1800b4b01  lea     rcx, [rbp+var_40]
0x1800b4b05  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800b4b0a  mov     eax, ebx
0x1800b4b0c  mov     rcx, [rbp+var_8]
0x1800b4b10  xor     rcx, rsp; StackCookie
0x1800b4b13  call    __security_check_cookie
0x1800b4b18  lea     r11, [rsp+70h+var_s0]
0x1800b4b1d  mov     rbx, [r11+28h]
0x1800b4b21  mov     rsi, [r11+30h]
0x1800b4b25  mov     rsp, r11
0x1800b4b28  pop     r14
0x1800b4b2a  pop     rdi
0x1800b4b2b  pop     rbp
0x1800b4b2c  retn
```
