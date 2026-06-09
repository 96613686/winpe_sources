# wpcplugs::AppRepository::StateRepo::IsDlcFromStateRepo(Windows::Internal::StateRepository::IPackage *)

- ea: `0x18006e9ec`
- end: `0x18006eba8`
- name: `?IsDlcFromStateRepo@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@@Z`
- size: `444`
- prototype: `bool __fastcall(wpcplugs::AppRepository::StateRepo *__hidden this, struct Windows::Internal::StateRepository::IPackage *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180071070`

## callees

- `0x1800060a0`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x18006e9ec`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006ea2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006eaa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006ea2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006eaa8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ea6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ea6b`

## string_xrefs

- `0x18006eb5c`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eb79`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eb96`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ea26`: `Windows.Internal.StateRepository.PackageExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall wpcplugs::AppRepository::StateRepo::IsDlcFromStateRepo(
        wpcplugs::AppRepository::StateRepo *this,
        struct Windows::Internal::StateRepository::IPackage *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  int v15; // eax
  bool v16; // bl
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  int v20; // [rsp+20h] [rbp-58h]
  _QWORD *v21; // [rsp+30h] [rbp-48h] BYREF
  int v22; // [rsp+38h] [rbp-40h] BYREF
  __int64 v23; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v21 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.PackageExtension",
         0x31u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
LABEL_13:
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0xFD,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v20);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_d266abd9_46c7_426d_a49a_442c979a7020, &v21);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_13;
  v23 = 0;
  v8 = v21;
  v9 = *v21;
  string = 0;
  v10 = WindowsCreateStringReference(L"xbox.contentpackage", 0x13u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
LABEL_15:
    wil::details::in1diag3::Throw_Hr(
      v14,
      (void *)0x100,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v13,
      v20);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *, wpcplugs::AppRepository::StateRepo *, HSTRING, __int64 *))(v9 + 144))(
          v8,
          this,
          string,
          &v23);
  v14 = retaddr;
  if ( v13 < 0 )
    goto LABEL_15;
  v22 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 56LL))(v23, &v22);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v15,
      v20);
  v16 = v22 != 0;
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
  }
  return v16;
}

```

## disassembly

```asm
0x18006e9ec  push    rbp
0x18006e9ee  push    rbx
0x18006e9ef  push    rsi
0x18006e9f0  push    rdi
0x18006e9f1  mov     rbp, rsp
0x18006e9f4  sub     rsp, 78h
0x18006e9f8  mov     rax, cs:__security_cookie
0x18006e9ff  xor     rax, rsp
0x18006ea02  mov     [rbp+var_10], rax
0x18006ea06  mov     rsi, rcx
0x18006ea09  mov     [rbp+var_48], 0
0x18006ea11  mov     [rbp+string], 0
0x18006ea19  lea     r9, [rbp+string]; string
0x18006ea1d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006ea21  mov     edx, 31h ; '1'; length
0x18006ea26  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageExtension@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006ea2d  call    cs:__imp_WindowsCreateStringReference
0x18006ea33  test    eax, eax
0x18006ea35  js      loc_18006EB6E
0x18006ea3b  mov     rbx, [rbp+string]
0x18006ea3f  mov     rcx, [rbp+var_48]
0x18006ea43  test    rcx, rcx
0x18006ea46  jz      short loc_18006EA5D
0x18006ea48  mov     [rbp+var_48], 0
0x18006ea50  mov     rax, [rcx]
0x18006ea53  mov     rax, [rax+10h]
0x18006ea57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea5c  nop
0x18006ea5d  lea     r8, [rbp+var_48]
0x18006ea61  lea     rdx, _GUID_d266abd9_46c7_426d_a49a_442c979a7020
0x18006ea68  mov     rcx, rbx
0x18006ea6b  call    cs:__imp_RoGetActivationFactory
0x18006ea71  mov     rcx, [rbp+20h]
0x18006ea75  test    eax, eax
0x18006ea77  js      loc_18006EB76
0x18006ea7d  mov     [rbp+var_38], 0
0x18006ea85  mov     rbx, [rbp+var_48]
0x18006ea89  mov     rdi, [rbx]
0x18006ea8c  mov     [rbp+string], 0
0x18006ea94  lea     r9, [rbp+string]; string
0x18006ea98  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006ea9c  mov     edx, 13h; length
0x18006eaa1  lea     rcx, aXboxContentpac; "xbox.contentpackage"
0x18006eaa8  call    cs:__imp_WindowsCreateStringReference
0x18006eaae  test    eax, eax
0x18006eab0  js      loc_18006EB8B
0x18006eab6  lea     r9, [rbp+var_38]
0x18006eaba  mov     r8, [rbp+string]
0x18006eabe  mov     rdx, rsi
0x18006eac1  mov     rcx, rbx
0x18006eac4  mov     rax, [rdi+90h]
0x18006eacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ead0  mov     rcx, [rbp+20h]
0x18006ead4  test    eax, eax
0x18006ead6  js      loc_18006EB93
0x18006eadc  mov     [rbp+var_40], 0
0x18006eae3  mov     rcx, [rbp+var_38]
0x18006eae7  mov     rax, [rcx]
0x18006eaea  lea     rdx, [rbp+var_40]
0x18006eaee  mov     rax, [rax+38h]
0x18006eaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eaf7  mov     rcx, [rbp+20h]; this
0x18006eafb  test    eax, eax
0x18006eafd  js      short loc_18006EB59
0x18006eaff  cmp     [rbp+var_40], 0
0x18006eb03  setnz   bl
0x18006eb06  mov     rcx, [rbp+var_38]
0x18006eb0a  test    rcx, rcx
0x18006eb0d  jz      short loc_18006EB24
0x18006eb0f  mov     [rbp+var_38], 0
0x18006eb17  mov     rax, [rcx]
0x18006eb1a  mov     rax, [rax+10h]
0x18006eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb23  nop
0x18006eb24  mov     rcx, [rbp+var_48]
0x18006eb28  test    rcx, rcx
0x18006eb2b  jz      short loc_18006EB42
0x18006eb2d  mov     [rbp+var_48], 0
0x18006eb35  mov     rdx, [rcx]
0x18006eb38  mov     rax, [rdx+10h]
0x18006eb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb41  nop
0x18006eb42  mov     al, bl
0x18006eb44  mov     rcx, [rbp+var_10]
0x18006eb48  xor     rcx, rsp; StackCookie
0x18006eb4b  call    __security_check_cookie
0x18006eb50  add     rsp, 78h
0x18006eb54  pop     rdi
0x18006eb55  pop     rsi
0x18006eb56  pop     rbx
0x18006eb57  pop     rbp
0x18006eb58  retn
0x18006eb59  mov     r9d, eax; char *
0x18006eb5c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eb63  mov     edx, 103h; void *
0x18006eb68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eb6e  mov     ecx, eax; this
0x18006eb70  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006eb75  nop
0x18006eb76  mov     r9d, eax; char *
0x18006eb79  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eb80  mov     edx, 0FDh; void *
0x18006eb85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eb8b  mov     ecx, eax; this
0x18006eb8d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006eb92  nop
0x18006eb93  mov     r9d, eax; char *
0x18006eb96  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eb9d  mov     edx, 100h; void *
0x18006eba2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
