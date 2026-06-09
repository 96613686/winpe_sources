# SystemSettings::StorageSenseHandlers::CAppTileData::GetHasExtensionCategory(HSTRING__ *,uchar *)

- ea: `0x1800a6adc`
- end: `0x1800a6ee3`
- name: `?GetHasExtensionCategory@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAE@Z`
- size: `1031`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, HSTRING, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043f9c`
- `0x1800a7c4c`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180035f2c`
- `0x1800a03d8`
- `0x1800a6adc`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6c64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6c4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6c4b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a6bf3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a6c79`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a6bf3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a6c79`

## string_xrefs

- `0x1800a6c44`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetHasExtensionCategory(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        HSTRING a2,
        unsigned __int8 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  _QWORD *v8; // rax
  int ActivationFactory; // eax
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, HSTRING, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v25; // rcx
  int v26; // [rsp+20h] [rbp-49h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  int v28; // [rsp+38h] [rbp-31h] BYREF
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h] BYREF
  __int64 v32; // [rsp+58h] [rbp-11h] BYREF
  __int64 v33; // [rsp+60h] [rbp-9h] BYREF
  __int64 v34; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a3 = 0;
  if ( *((_DWORD *)this + 12) )
    return 2147942487LL;
  v33 = 0;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  v29 = 0;
  v27 = 0;
  v34 = 0;
  v28 = 0;
  v5 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(
         (char *)this + 40,
         &v33);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v5,
      v26);
LABEL_29:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
    return v6;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 80LL))(v33, &v34);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v7,
      v26);
    goto LABEL_29;
  }
  v8 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                   &string,
                   L"Windows.Internal.StateRepository.Application");
  ActivationFactory = RoGetActivationFactory(*v8, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v31);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
    goto LABEL_29;
  }
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationExtension",
         0x35u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v10 = RoGetActivationFactory(string, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v27);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v10,
      v26);
    v11 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_29;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v31 + 264LL))(v31, v34, &v32);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v12,
      v26);
    v13 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_29;
  }
  v14 = v32;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
  v16 = v15(v14, 0, &v30);
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v16,
      v26);
    v17 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_29;
  }
  v18 = v27;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v27 + 136LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
  v20 = v19(v18, v30, a2, &v29);
  v6 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v20,
      v26);
    v21 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_29;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 56LL))(v29, &v28);
  v6 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v22,
      v26);
    v23 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_29;
  }
  if ( v28 )
    *a3 = 1;
  v25 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x1800a6adc  mov     [rsp-8+arg_18], rbx
0x1800a6ae1  push    rbp
0x1800a6ae2  push    rsi
0x1800a6ae3  push    rdi
0x1800a6ae4  push    r14
0x1800a6ae6  push    r15
0x1800a6ae8  lea     rbp, [rsp-37h]
0x1800a6aed  sub     rsp, 0A0h
0x1800a6af4  mov     rax, cs:__security_cookie
0x1800a6afb  xor     rax, rsp
0x1800a6afe  mov     [rbp+57h+var_30], rax
0x1800a6b02  mov     rsi, r8
0x1800a6b05  mov     r14, rdx
0x1800a6b08  xor     r15d, r15d
0x1800a6b0b  mov     [r8], r15b
0x1800a6b0e  cmp     [rcx+30h], r15d
0x1800a6b12  jnz     loc_1800A6EBB
0x1800a6b18  mov     [rbp+57h+var_60], r15
0x1800a6b1c  mov     [rbp+57h+var_78], r15
0x1800a6b20  mov     [rbp+57h+var_68], r15
0x1800a6b24  mov     [rbp+57h+var_70], r15
0x1800a6b28  mov     [rbp+57h+var_80], r15
0x1800a6b2c  mov     [rbp+57h+var_90], r15
0x1800a6b30  mov     [rbp+57h+var_58], r15
0x1800a6b34  mov     [rbp+57h+var_88], r15d
0x1800a6b38  add     rcx, 28h ; '('
0x1800a6b3c  lea     rdx, [rbp+57h+var_60]
0x1800a6b40  call    ??$As@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IPackageInfo>>)
0x1800a6b45  mov     ebx, eax
0x1800a6b47  test    eax, eax
0x1800a6b49  jns     short loc_1800A6B83
0x1800a6b4b  mov     rcx, [rbp+5Fh]; this
0x1800a6b4f  mov     r9d, eax; char *
0x1800a6b52  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6b59  mov     edx, 25Fh; void *
0x1800a6b5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6b63  nop
0x1800a6b64  mov     rcx, [rbp+57h+var_90]
0x1800a6b68  test    rcx, rcx
0x1800a6b6b  jz      short loc_1800A6B7E
0x1800a6b6d  mov     [rbp+57h+var_90], r15
0x1800a6b71  mov     rax, [rcx]
0x1800a6b74  mov     rax, [rax+10h]
0x1800a6b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6b7d  nop
0x1800a6b7e  jmp     loc_1800A6E2E
0x1800a6b83  mov     rcx, [rbp+57h+var_60]
0x1800a6b87  mov     rax, [rcx]
0x1800a6b8a  lea     rdx, [rbp+57h+var_58]
0x1800a6b8e  mov     rax, [rax+50h]
0x1800a6b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6b97  mov     ebx, eax
0x1800a6b99  test    eax, eax
0x1800a6b9b  jns     short loc_1800A6BD5
0x1800a6b9d  mov     rcx, [rbp+5Fh]; this
0x1800a6ba1  mov     r9d, eax; char *
0x1800a6ba4  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6bab  mov     edx, 260h; void *
0x1800a6bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6bb5  nop
0x1800a6bb6  mov     rcx, [rbp+57h+var_90]
0x1800a6bba  test    rcx, rcx
0x1800a6bbd  jz      short loc_1800A6BD0
0x1800a6bbf  mov     [rbp+57h+var_90], r15
0x1800a6bc3  mov     rax, [rcx]
0x1800a6bc6  mov     rax, [rax+10h]
0x1800a6bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6bcf  nop
0x1800a6bd0  jmp     loc_1800A6E2E
0x1800a6bd5  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800a6bdc  lea     rcx, [rbp+57h+string]; string
0x1800a6be0  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800a6be5  lea     r8, [rbp+57h+var_70]
0x1800a6be9  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800a6bf0  mov     rcx, [rax]
0x1800a6bf3  call    cs:__imp_RoGetActivationFactory
0x1800a6bf9  mov     ebx, eax
0x1800a6bfb  test    eax, eax
0x1800a6bfd  jns     short loc_1800A6C37
0x1800a6bff  mov     rcx, [rbp+5Fh]; this
0x1800a6c03  mov     r9d, eax; char *
0x1800a6c06  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6c0d  mov     edx, 261h; void *
0x1800a6c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c17  nop
0x1800a6c18  mov     rcx, [rbp+57h+var_90]
0x1800a6c1c  test    rcx, rcx
0x1800a6c1f  jz      short loc_1800A6C32
0x1800a6c21  mov     [rbp+57h+var_90], r15
0x1800a6c25  mov     rax, [rcx]
0x1800a6c28  mov     rax, [rax+10h]
0x1800a6c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c31  nop
0x1800a6c32  jmp     loc_1800A6E2E
0x1800a6c37  lea     r9, [rbp+57h+string]; string
0x1800a6c3b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a6c3f  mov     edx, 35h ; '5'; length
0x1800a6c44  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800a6c4b  call    cs:__imp_WindowsCreateStringReference
0x1800a6c51  test    eax, eax
0x1800a6c53  jns     short loc_1800A6C6A
0x1800a6c55  xor     r9d, r9d; lpArguments
0x1800a6c58  xor     r8d, r8d; nNumberOfArguments
0x1800a6c5b  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6c5f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a6c64  call    cs:__imp_RaiseException
0x1800a6c6a  lea     r8, [rbp+57h+var_90]
0x1800a6c6e  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x1800a6c75  mov     rcx, [rbp+57h+string]
0x1800a6c79  call    cs:__imp_RoGetActivationFactory
0x1800a6c7f  mov     ebx, eax
0x1800a6c81  test    eax, eax
0x1800a6c83  jns     short loc_1800A6CBD
0x1800a6c85  mov     rcx, [rbp+5Fh]; this
0x1800a6c89  mov     r9d, eax; char *
0x1800a6c8c  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6c93  mov     edx, 262h; void *
0x1800a6c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c9d  nop
0x1800a6c9e  mov     rcx, [rbp+57h+var_90]
0x1800a6ca2  test    rcx, rcx
0x1800a6ca5  jz      short loc_1800A6CB8
0x1800a6ca7  mov     [rbp+57h+var_90], r15
0x1800a6cab  mov     rax, [rcx]
0x1800a6cae  mov     rax, [rax+10h]
0x1800a6cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6cb7  nop
0x1800a6cb8  jmp     loc_1800A6E2E
0x1800a6cbd  mov     rcx, [rbp+57h+var_70]
0x1800a6cc1  mov     rax, [rcx]
0x1800a6cc4  lea     r8, [rbp+57h+var_68]
0x1800a6cc8  mov     rdx, [rbp+57h+var_58]
0x1800a6ccc  mov     rax, [rax+108h]
0x1800a6cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6cd8  mov     ebx, eax
0x1800a6cda  test    eax, eax
0x1800a6cdc  jns     short loc_1800A6D16
0x1800a6cde  mov     rcx, [rbp+5Fh]; this
0x1800a6ce2  mov     r9d, eax; char *
0x1800a6ce5  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6cec  mov     edx, 263h; void *
0x1800a6cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6cf6  nop
0x1800a6cf7  mov     rcx, [rbp+57h+var_90]
0x1800a6cfb  test    rcx, rcx
0x1800a6cfe  jz      short loc_1800A6D11
0x1800a6d00  mov     [rbp+57h+var_90], r15
0x1800a6d04  mov     rax, [rcx]
0x1800a6d07  mov     rax, [rax+10h]
0x1800a6d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d10  nop
0x1800a6d11  jmp     loc_1800A6E2E
0x1800a6d16  mov     rdi, [rbp+57h+var_68]
0x1800a6d1a  mov     rax, [rdi]
0x1800a6d1d  mov     rbx, [rax+30h]
0x1800a6d21  lea     rcx, [rbp+57h+var_78]
0x1800a6d25  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6d2a  lea     r8, [rbp+57h+var_78]
0x1800a6d2e  xor     edx, edx
0x1800a6d30  mov     rcx, rdi
0x1800a6d33  mov     rax, rbx
0x1800a6d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d3b  mov     ebx, eax
0x1800a6d3d  test    eax, eax
0x1800a6d3f  jns     short loc_1800A6D79
0x1800a6d41  mov     rcx, [rbp+5Fh]; this
0x1800a6d45  mov     r9d, eax; char *
0x1800a6d48  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6d4f  mov     edx, 264h; void *
0x1800a6d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6d59  nop
0x1800a6d5a  mov     rcx, [rbp+57h+var_90]
0x1800a6d5e  test    rcx, rcx
0x1800a6d61  jz      short loc_1800A6D74
0x1800a6d63  mov     [rbp+57h+var_90], r15
0x1800a6d67  mov     rax, [rcx]
0x1800a6d6a  mov     rax, [rax+10h]
0x1800a6d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d73  nop
0x1800a6d74  jmp     loc_1800A6E2E
0x1800a6d79  mov     rdi, [rbp+57h+var_90]
0x1800a6d7d  mov     rax, [rdi]
0x1800a6d80  mov     rbx, [rax+88h]
0x1800a6d87  lea     rcx, [rbp+57h+var_80]
0x1800a6d8b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6d90  lea     r9, [rbp+57h+var_80]
0x1800a6d94  mov     r8, r14
0x1800a6d97  mov     rdx, [rbp+57h+var_78]
0x1800a6d9b  mov     rcx, rdi
0x1800a6d9e  mov     rax, rbx
0x1800a6da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6da6  mov     ebx, eax
0x1800a6da8  test    eax, eax
0x1800a6daa  jns     short loc_1800A6DE1
0x1800a6dac  mov     rcx, [rbp+5Fh]; this
0x1800a6db0  mov     r9d, eax; char *
0x1800a6db3  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6dba  mov     edx, 265h; void *
0x1800a6dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6dc4  nop
0x1800a6dc5  mov     rcx, [rbp+57h+var_90]
0x1800a6dc9  test    rcx, rcx
0x1800a6dcc  jz      short loc_1800A6DDF
0x1800a6dce  mov     [rbp+57h+var_90], r15
0x1800a6dd2  mov     rax, [rcx]
0x1800a6dd5  mov     rax, [rax+10h]
0x1800a6dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dde  nop
0x1800a6ddf  jmp     short loc_1800A6E2E
0x1800a6de1  mov     rcx, [rbp+57h+var_80]
0x1800a6de5  mov     rax, [rcx]
0x1800a6de8  lea     rdx, [rbp+57h+var_88]
0x1800a6dec  mov     rax, [rax+38h]
0x1800a6df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6df5  mov     ebx, eax
0x1800a6df7  test    eax, eax
0x1800a6df9  jns     short loc_1800A6E63
0x1800a6dfb  mov     rcx, [rbp+5Fh]; this
0x1800a6dff  mov     r9d, eax; char *
0x1800a6e02  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a6e09  mov     edx, 266h; void *
0x1800a6e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6e13  nop
0x1800a6e14  mov     rcx, [rbp+57h+var_90]
0x1800a6e18  test    rcx, rcx
0x1800a6e1b  jz      short loc_1800A6E2E
0x1800a6e1d  mov     [rbp+57h+var_90], r15
0x1800a6e21  mov     rax, [rcx]
0x1800a6e24  mov     rax, [rax+10h]
0x1800a6e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e2d  nop
0x1800a6e2e  lea     rcx, [rbp+57h+var_80]
0x1800a6e32  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e37  nop
0x1800a6e38  lea     rcx, [rbp+57h+var_70]
0x1800a6e3c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e41  nop
0x1800a6e42  lea     rcx, [rbp+57h+var_68]
0x1800a6e46  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e4b  nop
0x1800a6e4c  lea     rcx, [rbp+57h+var_78]
0x1800a6e50  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e55  nop
0x1800a6e56  lea     rcx, [rbp+57h+var_60]
0x1800a6e5a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e5f  mov     eax, ebx
0x1800a6e61  jmp     short loc_1800A6EC0
0x1800a6e63  cmp     [rbp+57h+var_88], r15d
0x1800a6e67  jbe     short loc_1800A6E6C
0x1800a6e69  mov     byte ptr [rsi], 1
0x1800a6e6c  mov     rcx, [rbp+57h+var_90]
0x1800a6e70  test    rcx, rcx
0x1800a6e73  jz      short loc_1800A6E86
0x1800a6e75  mov     [rbp+57h+var_90], r15
0x1800a6e79  mov     rax, [rcx]
0x1800a6e7c  mov     rax, [rax+10h]
0x1800a6e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e85  nop
0x1800a6e86  lea     rcx, [rbp+57h+var_80]
0x1800a6e8a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e8f  nop
0x1800a6e90  lea     rcx, [rbp+57h+var_70]
0x1800a6e94  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6e99  nop
0x1800a6e9a  lea     rcx, [rbp+57h+var_68]
0x1800a6e9e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6ea3  nop
0x1800a6ea4  lea     rcx, [rbp+57h+var_78]
0x1800a6ea8  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6ead  nop
0x1800a6eae  lea     rcx, [rbp+57h+var_60]
0x1800a6eb2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a6eb7  xor     eax, eax
0x1800a6eb9  jmp     short loc_1800A6EC0
0x1800a6ebb  mov     eax, 80070057h
0x1800a6ec0  mov     rcx, [rbp+57h+var_30]
0x1800a6ec4  xor     rcx, rsp; StackCookie
0x1800a6ec7  call    __security_check_cookie
0x1800a6ecc  mov     rbx, [rsp+0C0h+arg_18]
0x1800a6ed4  add     rsp, 0A0h
0x1800a6edb  pop     r15
0x1800a6edd  pop     r14
0x1800a6edf  pop     rdi
0x1800a6ee0  pop     rsi
0x1800a6ee1  pop     rbp
0x1800a6ee2  retn
```
