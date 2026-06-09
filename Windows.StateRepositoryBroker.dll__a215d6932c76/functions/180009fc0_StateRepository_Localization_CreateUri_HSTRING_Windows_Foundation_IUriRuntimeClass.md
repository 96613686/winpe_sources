# StateRepository::Localization::CreateUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180009fc0`
- end: `0x18000a151`
- name: `?CreateUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(StateRepository::Localization *this, _QWORD *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009f2c`

## callees

- `0x180001d60`
- `0x180006224`
- `0x1800071a4`
- `0x180009fc0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a03b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a022`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a022`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a064`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a064`

## string_xrefs

- `0x18000a01b`: `Windows.Foundation.Uri`
- `0x180009ff2`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x18000a074`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x18000a0cd`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::CreateUri(
        StateRepository::Localization *this,
        _QWORD *a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  unsigned int v5; // ebx
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-38h] BYREF
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( a2 )
  {
    if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = string;
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v14);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_00000035_0000_0000_c000_000000000046, &v14);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v14;
      v13 = 0;
      v9 = **v14;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
      v10 = v9(v8, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v13);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v15 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, StateRepository::Localization *, __int64 *))(*(_QWORD *)v13 + 48LL))(
                v13,
                this,
                &v15);
        v5 = v10;
        if ( v10 >= 0 )
        {
          *a2 = v15;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
          v5 = 0;
          goto LABEL_13;
        }
        v11 = 79;
      }
      else
      {
        v11 = 76;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)(unsigned int)v10,
        v13);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v13);
    }
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v14);
    return v5;
  }
  v5 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
    (const char *)0x80004003LL,
    v13);
  return v5;
}

```

## disassembly

```asm
0x180009fc0  mov     [rsp-18h+arg_10], rbx
0x180009fc5  mov     [rsp-18h+arg_18], rsi
0x180009fca  push    rbp
0x180009fcb  push    rdi
0x180009fcc  push    r14
0x180009fce  mov     rbp, rsp
0x180009fd1  sub     rsp, 60h
0x180009fd5  mov     rax, cs:__security_cookie
0x180009fdc  xor     rax, rsp
0x180009fdf  mov     [rbp+var_8], rax
0x180009fe3  mov     rsi, rdx
0x180009fe6  mov     r14, rcx
0x180009fe9  test    rdx, rdx
0x180009fec  jnz     short loc_18000A00E
0x180009fee  mov     rcx, [rbp+18h]; this
0x180009ff2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009ff9  mov     ebx, 80004003h
0x180009ffe  lea     edx, [rsi+45h]; void *
0x18000a001  mov     r9d, ebx; char *
0x18000a004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a009  jmp     loc_18000A12E
0x18000a00e  lea     r9, [rbp+string]; string
0x18000a012  mov     edx, 16h; length
0x18000a017  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000a01b  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18000a022  call    cs:__imp_WindowsCreateStringReference
0x18000a028  test    eax, eax
0x18000a02a  jns     short loc_18000A041
0x18000a02c  xor     r9d, r9d; lpArguments
0x18000a02f  xor     r8d, r8d; nNumberOfArguments
0x18000a032  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000a037  lea     edx, [r9+1]; dwExceptionFlags
0x18000a03b  call    cs:__imp_RaiseException
0x18000a041  mov     rbx, [rbp+string]
0x18000a045  lea     rcx, [rbp+var_38]
0x18000a049  mov     [rbp+var_38], 0
0x18000a051  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000a056  lea     r8, [rbp+var_38]
0x18000a05a  mov     rcx, rbx
0x18000a05d  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000a064  call    cs:__imp_RoGetActivationFactory
0x18000a06a  mov     ebx, eax
0x18000a06c  test    eax, eax
0x18000a06e  jns     short loc_18000A08D
0x18000a070  mov     rcx, [rbp+18h]; this
0x18000a074  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a07b  mov     r9d, eax; char *
0x18000a07e  mov     edx, 49h ; 'I'; void *
0x18000a083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a088  jmp     loc_18000A125
0x18000a08d  mov     rbx, [rbp+var_38]
0x18000a091  lea     rcx, [rbp+var_40]
0x18000a095  mov     [rbp+var_40], 0
0x18000a09d  mov     rax, [rbx]
0x18000a0a0  mov     rdi, [rax]
0x18000a0a3  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000a0a8  lea     r8, [rbp+var_40]
0x18000a0ac  mov     rcx, rbx
0x18000a0af  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18000a0b6  mov     rax, rdi
0x18000a0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0be  mov     ebx, eax
0x18000a0c0  test    eax, eax
0x18000a0c2  jns     short loc_18000A0E7
0x18000a0c4  mov     edx, 4Ch ; 'L'; void *
0x18000a0c9  mov     rcx, [rbp+18h]; this
0x18000a0cd  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a0d4  mov     r9d, eax; char *
0x18000a0d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0dc  lea     rcx, [rbp+var_40]
0x18000a0e0  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000a0e5  jmp     short loc_18000A125
0x18000a0e7  mov     rcx, [rbp+var_40]
0x18000a0eb  lea     r8, [rbp+var_30]
0x18000a0ef  mov     [rbp+var_30], 0
0x18000a0f7  mov     rdx, r14
0x18000a0fa  mov     rax, [rcx]
0x18000a0fd  mov     rax, [rax+30h]
0x18000a101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a106  mov     ebx, eax
0x18000a108  test    eax, eax
0x18000a10a  jns     short loc_18000A113
0x18000a10c  mov     edx, 4Fh ; 'O'
0x18000a111  jmp     short loc_18000A0C9
0x18000a113  mov     rax, [rbp+var_30]
0x18000a117  lea     rcx, [rbp+var_40]
0x18000a11b  mov     [rsi], rax
0x18000a11e  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000a123  xor     ebx, ebx
0x18000a125  lea     rcx, [rbp+var_38]
0x18000a129  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000a12e  mov     eax, ebx
0x18000a130  mov     rcx, [rbp+var_8]
0x18000a134  xor     rcx, rsp; StackCookie
0x18000a137  call    __security_check_cookie
0x18000a13c  lea     r11, [rsp+60h+var_s0]
0x18000a141  mov     rbx, [r11+30h]
0x18000a145  mov     rsi, [r11+38h]
0x18000a149  mov     rsp, r11
0x18000a14c  pop     r14
0x18000a14e  pop     rdi
0x18000a14f  pop     rbp
0x18000a150  retn
```
