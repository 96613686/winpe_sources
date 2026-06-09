# Details::GetLauncherOptions(bool,ushort const *,CloudExperienceHostAPI::Redirection::IRedirectionManager *)

- ea: `0x180025af0`
- end: `0x180025ce2`
- name: `?GetLauncherOptions@Details@@YA?AV?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@_NPEBGPEAUIRedirectionManager@Redirection@CloudExperienceHostAPI@@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180027080`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x180017a84`
- `0x180017c58`
- `0x180020ea8`
- `0x180025af0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025bba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HSTRING __fastcall Details::GetLauncherOptions(HSTRING a1, char a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64); // rdi
  wchar_t **v15; // rdx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-50h]
  __int64 v19; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v20[2]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v20[1] = a1;
  v20[0] = 0;
  if ( a4 )
  {
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a4 + 56LL);
    WindowsDeleteString(0);
    v20[0] = 0;
    v8 = v7(a4, v20);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v8,
        0);
  }
  *(_QWORD *)a1 = 0;
  v18 = 1;
  if ( WindowsCreateStringReference(L"Windows.System.LauncherOptions", 0x1Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(string, a1);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v9,
      1);
  v19 = 0;
  v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a1;
  v11 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v12 = v11(v10, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v19);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v12,
      1);
  v13 = v19;
  v14 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 56LL);
  if ( !v20[0] )
  {
    v15 = &off_180057A60;
    if ( !a2 )
      v15 = off_180057A58;
    v18 = 3;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, v15);
  }
  v16 = v14(v13);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v16,
      v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  WindowsDeleteString(v20[0]);
  return a1;
}

```

## disassembly

```asm
0x180025af0  mov     [rsp-18h+arg_8], rbx
0x180025af5  mov     [rsp-18h+arg_10], rsi
0x180025afa  push    rbp
0x180025afb  push    rdi
0x180025afc  push    r14
0x180025afe  mov     rbp, rsp
0x180025b01  sub     rsp, 70h
0x180025b05  mov     rax, cs:__security_cookie
0x180025b0c  xor     rax, rsp
0x180025b0f  mov     [rbp+var_10], rax
0x180025b13  mov     rdi, r9
0x180025b16  mov     r14b, dl
0x180025b19  mov     rsi, rcx
0x180025b1c  mov     [rbp+var_38], rcx
0x180025b20  mov     [rbp+var_50], 0
0x180025b27  mov     [rbp+var_40], 0
0x180025b2f  test    r9, r9
0x180025b32  jz      short loc_180025B7C
0x180025b34  mov     rax, [r9]
0x180025b37  mov     rbx, [rax+38h]
0x180025b3b  xor     ecx, ecx; string
0x180025b3d  call    cs:__imp_WindowsDeleteString
0x180025b44  nop     dword ptr [rax+rax+00h]
0x180025b49  mov     [rbp+var_40], 0
0x180025b51  lea     rdx, [rbp+var_40]
0x180025b55  mov     rcx, rdi
0x180025b58  mov     rax, rbx
0x180025b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b60  mov     rcx, [rbp+18h]; this
0x180025b64  test    eax, eax
0x180025b66  jns     short loc_180025B7C
0x180025b68  mov     r9d, eax; char *
0x180025b6b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025b72  mov     edx, 35h ; '5'; void *
0x180025b77  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025b7c  mov     qword ptr [rsi], 0
0x180025b83  mov     ebx, 1
0x180025b88  mov     [rbp+var_50], ebx
0x180025b8b  lea     r9, [rbp+string]; string
0x180025b8f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180025b93  lea     edx, [rbx+1Dh]; length
0x180025b96  lea     rcx, ?RuntimeClass_Windows_System_LauncherOptions@@3QBGB; "Windows.System.LauncherOptions"
0x180025b9d  call    cs:__imp_WindowsCreateStringReference
0x180025ba4  nop     dword ptr [rax+rax+00h]
0x180025ba9  test    eax, eax
0x180025bab  jns     short loc_180025BC6
0x180025bad  xor     r9d, r9d; lpArguments
0x180025bb0  xor     r8d, r8d; nNumberOfArguments
0x180025bb3  mov     edx, ebx; dwExceptionFlags
0x180025bb5  mov     ecx, 0C000000Dh; dwExceptionCode
0x180025bba  call    cs:__imp_RaiseException
0x180025bc1  nop     dword ptr [rax+rax+00h]
0x180025bc6  mov     rdx, rsi
0x180025bc9  mov     rcx, [rbp+string]
0x180025bcd  call    ??$ActivateInstance@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>)
0x180025bd2  mov     rcx, [rbp+18h]; this
0x180025bd6  test    eax, eax
0x180025bd8  jns     short loc_180025BEF
0x180025bda  mov     r9d, eax; char *
0x180025bdd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025be4  mov     edx, 3Ch ; '<'; void *
0x180025be9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025bef  mov     [rbp+var_48], 0
0x180025bf7  mov     rdi, [rsi]
0x180025bfa  mov     rax, [rdi]
0x180025bfd  mov     rbx, [rax]
0x180025c00  lea     rcx, [rbp+var_48]
0x180025c04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025c09  lea     r8, [rbp+var_48]
0x180025c0d  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x180025c14  mov     rcx, rdi
0x180025c17  mov     rax, rbx
0x180025c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c1f  nop
0x180025c20  mov     rcx, [rbp+18h]; this
0x180025c24  test    eax, eax
0x180025c26  jns     short loc_180025C3D
0x180025c28  mov     r9d, eax; char *
0x180025c2b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025c32  mov     edx, 3Eh ; '>'; void *
0x180025c37  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025c3d  mov     rbx, [rbp+var_48]
0x180025c41  mov     rax, [rbx]
0x180025c44  mov     rdi, [rax+38h]
0x180025c48  mov     rdx, [rbp+var_40]
0x180025c4c  test    rdx, rdx
0x180025c4f  jnz     short loc_180025C7B
0x180025c51  lea     rax, off_180057A58; "Microsoft.CloudExperienceHost_8wekyb3d8"...
0x180025c58  lea     rdx, off_180057A60; "Microsoft.Windows.CloudExperienceHost_c"...
0x180025c5f  test    r14b, r14b
0x180025c62  cmovz   rdx, rax
0x180025c66  lea     rcx, [rbp+string]
0x180025c6a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180025c6f  nop
0x180025c70  mov     [rbp+var_50], 3
0x180025c77  mov     rdx, [rax+18h]
0x180025c7b  mov     rcx, rbx
0x180025c7e  mov     rax, rdi
0x180025c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c86  mov     rcx, [rbp+18h]; this
0x180025c8a  test    eax, eax
0x180025c8c  jns     short loc_180025CA3
0x180025c8e  mov     r9d, eax; char *
0x180025c91  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025c98  mov     edx, 40h ; '@'; void *
0x180025c9d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025ca3  lea     rcx, [rbp+var_48]
0x180025ca7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025cac  nop
0x180025cad  mov     rcx, [rbp+var_40]; string
0x180025cb1  call    cs:__imp_WindowsDeleteString
0x180025cb8  nop     dword ptr [rax+rax+00h]
0x180025cbd  mov     rax, rsi
0x180025cc0  mov     rcx, [rbp+var_10]
0x180025cc4  xor     rcx, rsp; StackCookie
0x180025cc7  call    __security_check_cookie
0x180025ccc  lea     r11, [rsp+70h+var_s0]
0x180025cd1  mov     rbx, [r11+28h]
0x180025cd5  mov     rsi, [r11+30h]
0x180025cd9  mov     rsp, r11
0x180025cdc  pop     r14
0x180025cde  pop     rdi
0x180025cdf  pop     rbp
0x180025ce0  retn
```
