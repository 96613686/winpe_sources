# GetPackageFamilyAndFullNameForExtension(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtension> const &,HSTRING__ * *,HSTRING__ * *)

- ea: `0x14000cc94`
- end: `0x14000cecc`
- name: `?GetPackageFamilyAndFullNameForExtension@@YAXAEBV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAPEAUHSTRING__@@1@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *, HSTRING *, HSTRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b114`
- `0x14000c3ec`

## callees

- `0x14000cc94`
- `0x14000d49c`
- `0x14000fbb0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000cd94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000ce55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000cd94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000ce55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ce98`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyAndFullNameForExtension(__int64 *a1, HSTRING *a2, HSTRING *a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  HRESULT v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  HRESULT v21; // eax
  __int64 v23; // [rsp+20h] [rbp-20h] BYREF
  __int64 v24; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HSTRING v27; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v25[0] = 0;
  v5 = *a1;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v25);
  v7 = v6(v5, v25);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x62,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v7,
      v23);
  v23 = 0;
  v8 = v25[0];
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25[0] + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v23);
  v10 = v9(v8, &v23);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x64,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v10,
      v23);
  string = 0;
  v11 = v23;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 112LL);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(v11, &string);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x67,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v13,
      v23);
  v14 = WindowsDuplicateString(string, a3);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x68,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v14,
      v23);
  v24 = 0;
  v15 = v23;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v24);
  v17 = v16(v15, &v24);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6B,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v17,
      v23);
  v27 = 0;
  v18 = v24;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 88LL);
  WindowsDeleteString(0);
  v27 = 0;
  v20 = v19(v18, &v27);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6E,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v20,
      v23);
  v21 = WindowsDuplicateString(v27, a2);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v21,
      v23);
  WindowsDeleteString(v27);
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v24);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v23);
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v25);
}

```

## disassembly

```asm
0x14000cc94  mov     [rsp-18h+arg_8], rbx
0x14000cc99  mov     [rsp-18h+arg_10], rsi
0x14000cc9e  push    rbp
0x14000cc9f  push    rdi
0x14000cca0  push    r14
0x14000cca2  mov     rbp, rsp
0x14000cca5  sub     rsp, 40h
0x14000cca9  mov     rsi, r8
0x14000ccac  mov     r14, rdx
0x14000ccaf  mov     [rbp+var_10], 0
0x14000ccb7  mov     rdi, [rcx]
0x14000ccba  mov     rax, [rdi]
0x14000ccbd  mov     rbx, [rax+48h]
0x14000ccc1  lea     rcx, [rbp+var_10]
0x14000ccc5  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ccca  lea     rdx, [rbp+var_10]
0x14000ccce  mov     rcx, rdi
0x14000ccd1  mov     rax, rbx
0x14000ccd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccd9  mov     rcx, [rbp+18h]; this
0x14000ccdd  test    eax, eax
0x14000ccdf  jns     short loc_14000CCF6
0x14000cce1  mov     r9d, eax; char *
0x14000cce4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cceb  mov     edx, 62h ; 'b'; void *
0x14000ccf0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ccf6  mov     [rbp+var_20], 0
0x14000ccfe  mov     rdi, [rbp+var_10]
0x14000cd02  mov     rax, [rdi]
0x14000cd05  mov     rbx, [rax+48h]
0x14000cd09  lea     rcx, [rbp+var_20]
0x14000cd0d  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cd12  lea     rdx, [rbp+var_20]
0x14000cd16  mov     rcx, rdi
0x14000cd19  mov     rax, rbx
0x14000cd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd21  mov     rcx, [rbp+18h]; this
0x14000cd25  test    eax, eax
0x14000cd27  jns     short loc_14000CD3E
0x14000cd29  mov     r9d, eax; char *
0x14000cd2c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cd33  mov     edx, 64h ; 'd'; void *
0x14000cd38  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cd3e  mov     [rbp+string], 0
0x14000cd46  mov     rdi, [rbp+var_20]
0x14000cd4a  mov     rax, [rdi]
0x14000cd4d  mov     rbx, [rax+70h]
0x14000cd51  xor     ecx, ecx; string
0x14000cd53  call    cs:__imp_WindowsDeleteString
0x14000cd59  mov     [rbp+string], 0
0x14000cd61  lea     rdx, [rbp+string]
0x14000cd65  mov     rcx, rdi
0x14000cd68  mov     rax, rbx
0x14000cd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd70  mov     rcx, [rbp+18h]; this
0x14000cd74  test    eax, eax
0x14000cd76  jns     short loc_14000CD8D
0x14000cd78  mov     r9d, eax; char *
0x14000cd7b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cd82  mov     edx, 67h ; 'g'; void *
0x14000cd87  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cd8d  mov     rdx, rsi; newString
0x14000cd90  mov     rcx, [rbp+string]; string
0x14000cd94  call    cs:__imp_WindowsDuplicateString
0x14000cd9a  mov     rcx, [rbp+18h]; this
0x14000cd9e  test    eax, eax
0x14000cda0  jns     short loc_14000CDB7
0x14000cda2  mov     r9d, eax; char *
0x14000cda5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cdac  mov     edx, 68h ; 'h'; void *
0x14000cdb1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cdb7  mov     [rbp+var_18], 0
0x14000cdbf  mov     rdi, [rbp+var_20]
0x14000cdc3  mov     rax, [rdi]
0x14000cdc6  mov     rbx, [rax+48h]
0x14000cdca  lea     rcx, [rbp+var_18]
0x14000cdce  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cdd3  lea     rdx, [rbp+var_18]
0x14000cdd7  mov     rcx, rdi
0x14000cdda  mov     rax, rbx
0x14000cddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cde2  mov     rcx, [rbp+18h]; this
0x14000cde6  test    eax, eax
0x14000cde8  jns     short loc_14000CDFF
0x14000cdea  mov     r9d, eax; char *
0x14000cded  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cdf4  mov     edx, 6Bh ; 'k'; void *
0x14000cdf9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cdff  mov     [rbp+arg_0], 0
0x14000ce07  mov     rdi, [rbp+var_18]
0x14000ce0b  mov     rax, [rdi]
0x14000ce0e  mov     rbx, [rax+58h]
0x14000ce12  xor     ecx, ecx; string
0x14000ce14  call    cs:__imp_WindowsDeleteString
0x14000ce1a  mov     [rbp+arg_0], 0
0x14000ce22  lea     rdx, [rbp+arg_0]
0x14000ce26  mov     rcx, rdi
0x14000ce29  mov     rax, rbx
0x14000ce2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce31  mov     rcx, [rbp+18h]; this
0x14000ce35  test    eax, eax
0x14000ce37  jns     short loc_14000CE4E
0x14000ce39  mov     r9d, eax; char *
0x14000ce3c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ce43  mov     edx, 6Eh ; 'n'; void *
0x14000ce48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ce4e  mov     rdx, r14; newString
0x14000ce51  mov     rcx, [rbp+arg_0]; string
0x14000ce55  call    cs:__imp_WindowsDuplicateString
0x14000ce5b  mov     rcx, [rbp+18h]; this
0x14000ce5f  test    eax, eax
0x14000ce61  jns     short loc_14000CE78
0x14000ce63  mov     r9d, eax; char *
0x14000ce66  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ce6d  mov     edx, 6Fh ; 'o'; void *
0x14000ce72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ce78  mov     rcx, [rbp+arg_0]; string
0x14000ce7c  call    cs:__imp_WindowsDeleteString
0x14000ce82  mov     [rbp+arg_0], 0
0x14000ce8a  lea     rcx, [rbp+var_18]
0x14000ce8e  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ce93  nop
0x14000ce94  mov     rcx, [rbp+string]; string
0x14000ce98  call    cs:__imp_WindowsDeleteString
0x14000ce9e  mov     [rbp+string], 0
0x14000cea6  lea     rcx, [rbp+var_20]
0x14000ceaa  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ceaf  nop
0x14000ceb0  lea     rcx, [rbp+var_10]
0x14000ceb4  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ceb9  mov     rbx, [rsp+40h+arg_8]
0x14000cebe  mov     rsi, [rsp+40h+arg_10]
0x14000cec3  add     rsp, 40h
0x14000cec7  pop     r14
0x14000cec9  pop     rdi
0x14000ceca  pop     rbp
0x14000cecb  retn
```
