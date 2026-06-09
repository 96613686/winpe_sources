# Common::Deployment::GetProtectionLevelFromManifest(IXMLDOMDocument2 *,Common::Deployment::DATA_PROTECTION_LEVEL &,bool &)

- ea: `0x1801e2c74`
- end: `0x1801e2fd8`
- name: `?GetProtectionLevelFromManifest@Deployment@Common@@YAJPEAUIXMLDOMDocument2@@AEAW4DATA_PROTECTION_LEVEL@12@AEA_N@Z`
- size: `868`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, struct IXMLDOMDocument2 *, enum Common::Deployment::DATA_PROTECTION_LEVEL *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012b700`

## callees

- `0x18000b3bc`
- `0x18008f690`
- `0x1800a8f80`
- `0x1800b8300`
- `0x1800bead4`
- `0x1801e2c74`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2ef9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f42`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2ef9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f42`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e2f69`
- `OLEAUT32!__imp_VariantInit` at `0x1801e2e82`
- `OLEAUT32!__imp_VariantInit` at `0x1801e2e82`
- `OLEAUT32!__imp_VariantClear` at `0x1801e2ecc`
- `OLEAUT32!__imp_VariantClear` at `0x1801e2f89`
- `OLEAUT32!__imp_VariantClear` at `0x1801e2ecc`
- `OLEAUT32!__imp_VariantClear` at `0x1801e2f89`

## string_xrefs

- `0x1801e2cc8`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2d28`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2d98`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2df2`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2e56`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2eb6`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1801e2cb4`: `make_bstr_nothrow xpath`
- `0x1801e2c96`: `/*[local-name()='Package']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.dataProtection']/*[local-name()='DataProtection']`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Common::Deployment::GetProtectionLevelFromManifest(
        Common::Deployment *this,
        struct IXMLDOMDocument2 *a2,
        enum Common::Deployment::DATA_PROTECTION_LEVEL *a3,
        bool *a4)
{
  __int64 v7; // rbx
  int v8; // ebx
  __int64 (__fastcall *v9)(Common::Deployment *, __int64, __int64 *); // rdi
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64 *); // rdi
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64, __int64 *); // rdi
  __int64 v17; // rcx
  const char *v19; // [rsp+28h] [rbp-38h]
  __int64 v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v25; // [rsp+98h] [rbp+38h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  LODWORD(a2->lpVtbl) = 0;
  wil::make_bstr_nothrow(
    &v22,
    L"/*[local-name()='Package']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.dataProtec"
     "tion']/*[local-name()='DataProtection']",
    a3,
    a4);
  v7 = v22;
  if ( v22 )
  {
    *(_BYTE *)a3 = 0;
    v25 = 0;
    v9 = *(__int64 (__fastcall **)(Common::Deployment *, __int64, __int64 *))(*(_QWORD *)this + 296LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v8 = v9(this, v7, &v25);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB42,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v8,
        (int)"selectSingleNode",
        v19);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      goto LABEL_35;
    }
    v10 = v25;
    if ( !v25 )
    {
LABEL_34:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      v8 = 0;
      goto LABEL_35;
    }
    v26 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 136LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v8 = v11(v10, &v26);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB46,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v8,
        (int)"get_attributes",
        v19);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      goto LABEL_5;
    }
    if ( !v26 )
    {
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      goto LABEL_34;
    }
    wil::make_bstr_nothrow(&v21, L"UserDataAvailability", v12, v13);
    v14 = v21;
    if ( !v21 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB4B,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)0x8007000ELL,
        (int)"make_bstr_nothrow AttributeName",
        v19);
LABEL_13:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      goto LABEL_9;
    }
    v20 = 0;
    v15 = v26;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v26 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v8 = v16(v15, v14, &v20);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB4F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v8,
        (int)"getNamedItem",
        v19);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      goto LABEL_13;
    }
    if ( !v20 )
    {
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      goto LABEL_33;
    }
    VariantInit(&pvarg);
    v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v20 + 64LL))(v20, &pvarg);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB53,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v8,
        (int)"get_nodeValue",
        v19);
      VariantClear(&pvarg);
      goto LABEL_16;
    }
    if ( pvarg.llVal )
    {
      if ( CompareStringOrdinal(L"always", -1, pvarg.bstrVal, -1, 1) == 2 )
      {
        LODWORD(a2->lpVtbl) = 1;
      }
      else if ( CompareStringOrdinal(L"afterFirstUnlock", -1, pvarg.bstrVal, -1, 1) == 2 )
      {
        LODWORD(a2->lpVtbl) = 2;
      }
      else if ( CompareStringOrdinal(L"whileUnlocked", -1, pvarg.bstrVal, -1, 1) == 2 )
      {
        LODWORD(a2->lpVtbl) = 3;
      }
      else
      {
        if ( CompareStringOrdinal(L"applicationManaged", -1, pvarg.bstrVal, -1, 1) != 2 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v17);
          goto LABEL_31;
        }
        LODWORD(a2->lpVtbl) = 0;
      }
      *(_BYTE *)a3 = 1;
    }
LABEL_31:
    VariantClear(&pvarg);
    goto LABEL_32;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xB3E,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)0x8007000ELL,
    (int)"make_bstr_nothrow xpath",
    v19);
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801e2c74  mov     [rsp-28h+arg_0], rbx
0x1801e2c79  push    rbp
0x1801e2c7a  push    rsi
0x1801e2c7b  push    rdi
0x1801e2c7c  push    r14
0x1801e2c7e  push    r15
0x1801e2c80  mov     rbp, rsp
0x1801e2c83  sub     rsp, 60h
0x1801e2c87  mov     r15, r8
0x1801e2c8a  mov     r14, rdx
0x1801e2c8d  mov     rsi, rcx
0x1801e2c90  mov     dword ptr [rdx], 0
0x1801e2c96  lea     rdx, aLocalNamePacka_7; "/*[local-name()='Package']/*[local-name"...
0x1801e2c9d  lea     rcx, [rbp+var_20]
0x1801e2ca1  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1801e2ca6  nop
0x1801e2ca7  mov     rbx, [rbp+var_20]
0x1801e2cab  test    rbx, rbx
0x1801e2cae  jnz     short loc_1801E2CDE
0x1801e2cb0  mov     rcx, [rbp+28h]; this
0x1801e2cb4  lea     rax, aMakeBstrNothro; "make_bstr_nothrow xpath"
0x1801e2cbb  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2cc0  mov     ebx, 8007000Eh
0x1801e2cc5  mov     r9d, ebx; char *
0x1801e2cc8  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2ccf  mov     edx, 0B3Eh; void *
0x1801e2cd4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2cd9  jmp     loc_1801E2FB9
0x1801e2cde  mov     byte ptr [r15], 0
0x1801e2ce2  mov     [rbp+arg_8], 0
0x1801e2cea  mov     rax, [rsi]
0x1801e2ced  mov     rdi, [rax+128h]
0x1801e2cf4  lea     rcx, [rbp+arg_8]
0x1801e2cf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2cfd  lea     r8, [rbp+arg_8]
0x1801e2d01  mov     rdx, rbx
0x1801e2d04  mov     rcx, rsi
0x1801e2d07  mov     rax, rdi
0x1801e2d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2d0f  mov     ebx, eax
0x1801e2d11  test    eax, eax
0x1801e2d13  jns     short loc_1801E2D48
0x1801e2d15  mov     rcx, [rbp+28h]; this
0x1801e2d19  lea     rax, aSelectsingleno; "selectSingleNode"
0x1801e2d20  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2d25  mov     r9d, ebx; char *
0x1801e2d28  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2d2f  mov     edx, 0B42h; void *
0x1801e2d34  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2d39  nop
0x1801e2d3a  lea     rcx, [rbp+arg_8]
0x1801e2d3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2d43  jmp     loc_1801E2FB9
0x1801e2d48  mov     rbx, [rbp+arg_8]
0x1801e2d4c  test    rbx, rbx
0x1801e2d4f  jz      loc_1801E2FAE
0x1801e2d55  mov     [rbp+arg_18], 0
0x1801e2d5d  mov     rax, [rbx]
0x1801e2d60  mov     rdi, [rax+88h]
0x1801e2d67  lea     rcx, [rbp+arg_18]
0x1801e2d6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2d70  lea     rdx, [rbp+arg_18]
0x1801e2d74  mov     rcx, rbx
0x1801e2d77  mov     rax, rdi
0x1801e2d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2d7f  mov     ebx, eax
0x1801e2d81  test    eax, eax
0x1801e2d83  jns     short loc_1801E2DB5
0x1801e2d85  mov     rcx, [rbp+28h]; this
0x1801e2d89  lea     rax, aGetAttributes; "get_attributes"
0x1801e2d90  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2d95  mov     r9d, ebx; char *
0x1801e2d98  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2d9f  mov     edx, 0B46h; void *
0x1801e2da4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2da9  nop
0x1801e2daa  lea     rcx, [rbp+arg_18]
0x1801e2dae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2db3  jmp     short loc_1801E2D3A
0x1801e2db5  cmp     [rbp+arg_18], 0
0x1801e2dba  jz      loc_1801E2FA4
0x1801e2dc0  lea     rdx, aUserdataavaila; "UserDataAvailability"
0x1801e2dc7  lea     rcx, [rbp+var_28]
0x1801e2dcb  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1801e2dd0  nop
0x1801e2dd1  mov     rbx, [rbp+var_28]
0x1801e2dd5  test    rbx, rbx
0x1801e2dd8  jnz     short loc_1801E2E0F
0x1801e2dda  mov     rcx, [rbp+28h]; this
0x1801e2dde  lea     rax, aMakeBstrNothro_0; "make_bstr_nothrow AttributeName"
0x1801e2de5  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2dea  mov     ebx, 8007000Eh
0x1801e2def  mov     r9d, ebx; char *
0x1801e2df2  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2df9  mov     edx, 0B4Bh; void *
0x1801e2dfe  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2e03  nop
0x1801e2e04  lea     rcx, [rbp+var_28]
0x1801e2e08  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801e2e0d  jmp     short loc_1801E2DAA
0x1801e2e0f  mov     [rbp+var_30], 0
0x1801e2e17  mov     rsi, [rbp+arg_18]
0x1801e2e1b  mov     rax, [rsi]
0x1801e2e1e  mov     rdi, [rax+38h]
0x1801e2e22  lea     rcx, [rbp+var_30]
0x1801e2e26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2e2b  lea     r8, [rbp+var_30]
0x1801e2e2f  mov     rdx, rbx
0x1801e2e32  mov     rcx, rsi
0x1801e2e35  mov     rax, rdi
0x1801e2e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2e3d  mov     ebx, eax
0x1801e2e3f  test    eax, eax
0x1801e2e41  jns     short loc_1801E2E73
0x1801e2e43  mov     rcx, [rbp+28h]; this
0x1801e2e47  lea     rax, aGetnameditem; "getNamedItem"
0x1801e2e4e  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2e53  mov     r9d, ebx; char *
0x1801e2e56  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2e5d  mov     edx, 0B4Fh; void *
0x1801e2e62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2e67  nop
0x1801e2e68  lea     rcx, [rbp+var_30]
0x1801e2e6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2e71  jmp     short loc_1801E2E04
0x1801e2e73  cmp     [rbp+var_30], 0
0x1801e2e78  jz      loc_1801E2F90
0x1801e2e7e  lea     rcx, [rbp+pvarg]; pvarg
0x1801e2e82  call    cs:__imp_VariantInit
0x1801e2e88  nop
0x1801e2e89  mov     rcx, [rbp+var_30]
0x1801e2e8d  mov     rax, [rcx]
0x1801e2e90  lea     rdx, [rbp+pvarg]
0x1801e2e94  mov     rax, [rax+40h]
0x1801e2e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2e9d  mov     ebx, eax
0x1801e2e9f  test    eax, eax
0x1801e2ea1  jns     short loc_1801E2ED4
0x1801e2ea3  mov     rcx, [rbp+28h]; this
0x1801e2ea7  lea     rax, aGetNodevalue; "get_nodeValue"
0x1801e2eae  mov     qword ptr [rsp+60h+bIgnoreCase], rax; int
0x1801e2eb3  mov     r9d, ebx; char *
0x1801e2eb6  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1801e2ebd  mov     edx, 0B53h; void *
0x1801e2ec2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801e2ec7  nop
0x1801e2ec8  lea     rcx, [rbp+pvarg]; pvarg
0x1801e2ecc  call    cs:__imp_VariantClear
0x1801e2ed2  jmp     short loc_1801E2E68
0x1801e2ed4  mov     r8, qword ptr [rbp+pvarg+8]; lpString2
0x1801e2ed8  test    r8, r8
0x1801e2edb  jz      loc_1801E2F85
0x1801e2ee1  mov     ebx, 1
0x1801e2ee6  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x1801e2eea  or      edi, 0FFFFFFFFh
0x1801e2eed  mov     r9d, edi; cchCount2
0x1801e2ef0  mov     edx, edi; cchCount1
0x1801e2ef2  lea     rcx, aAlways; "always"
0x1801e2ef9  call    cs:__imp_CompareStringOrdinal
0x1801e2eff  lea     esi, [rbx+1]
0x1801e2f02  cmp     eax, esi
0x1801e2f04  jnz     short loc_1801E2F0B
0x1801e2f06  mov     [r14], ebx
0x1801e2f09  jmp     short loc_1801E2F7A
0x1801e2f0b  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x1801e2f0f  mov     r9d, edi; cchCount2
0x1801e2f12  mov     r8, qword ptr [rbp+pvarg+8]; lpString2
0x1801e2f16  mov     edx, edi; cchCount1
0x1801e2f18  lea     rcx, aAfterfirstunlo; "afterFirstUnlock"
0x1801e2f1f  call    cs:__imp_CompareStringOrdinal
0x1801e2f25  cmp     eax, esi
0x1801e2f27  jnz     short loc_1801E2F2E
0x1801e2f29  mov     [r14], esi
0x1801e2f2c  jmp     short loc_1801E2F7A
0x1801e2f2e  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x1801e2f32  mov     r9d, edi; cchCount2
0x1801e2f35  mov     r8, qword ptr [rbp+pvarg+8]; lpString2
0x1801e2f39  mov     edx, edi; cchCount1
0x1801e2f3b  lea     rcx, aWhileunlocked; "whileUnlocked"
0x1801e2f42  call    cs:__imp_CompareStringOrdinal
0x1801e2f48  cmp     eax, esi
0x1801e2f4a  jnz     short loc_1801E2F55
0x1801e2f4c  mov     dword ptr [r14], 3
0x1801e2f53  jmp     short loc_1801E2F7A
0x1801e2f55  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x1801e2f59  mov     r9d, edi; cchCount2
0x1801e2f5c  mov     r8, qword ptr [rbp+pvarg+8]; lpString2
0x1801e2f60  mov     edx, edi; cchCount1
0x1801e2f62  lea     rcx, aApplicationman; "applicationManaged"
0x1801e2f69  call    cs:__imp_CompareStringOrdinal
0x1801e2f6f  cmp     eax, esi
0x1801e2f71  jnz     short loc_1801E2F7F
0x1801e2f73  mov     dword ptr [r14], 0
0x1801e2f7a  mov     [r15], bl
0x1801e2f7d  jmp     short loc_1801E2F85
0x1801e2f7f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801e2f84  nop
0x1801e2f85  lea     rcx, [rbp+pvarg]; pvarg
0x1801e2f89  call    cs:__imp_VariantClear
0x1801e2f8f  nop
0x1801e2f90  lea     rcx, [rbp+var_30]
0x1801e2f94  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2f99  nop
0x1801e2f9a  lea     rcx, [rbp+var_28]
0x1801e2f9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801e2fa3  nop
0x1801e2fa4  lea     rcx, [rbp+arg_18]
0x1801e2fa8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2fad  nop
0x1801e2fae  lea     rcx, [rbp+arg_8]
0x1801e2fb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e2fb7  xor     ebx, ebx
0x1801e2fb9  lea     rcx, [rbp+var_20]
0x1801e2fbd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801e2fc2  mov     eax, ebx
0x1801e2fc4  mov     rbx, [rsp+60h+arg_0]
0x1801e2fcc  add     rsp, 60h
0x1801e2fd0  pop     r15
0x1801e2fd2  pop     r14
0x1801e2fd4  pop     rdi
0x1801e2fd5  pop     rsi
0x1801e2fd6  pop     rbp
0x1801e2fd7  retn
```
