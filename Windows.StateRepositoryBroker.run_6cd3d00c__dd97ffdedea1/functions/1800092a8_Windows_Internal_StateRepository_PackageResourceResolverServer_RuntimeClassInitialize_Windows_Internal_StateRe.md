# Windows::Internal::StateRepository::PackageResourceResolverServer::RuntimeClassInitialize(Windows::Internal::StateRepository::IPackage *)

- ea: `0x1800092a8`
- end: `0x18000946b`
- name: `?RuntimeClassInitialize@PackageResourceResolverServer@StateRepository@Internal@Windows@@QEAAJPEAUIPackage@234@@Z`
- size: `451`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PackageResourceResolverServer *__hidden this, struct Windows::Internal::StateRepository::IPackage *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007370`

## callees

- `0x180001d60`
- `0x180006224`
- `0x1800071a4`
- `0x1800092a8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009306`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800092ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800092ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009327`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009327`

## string_xrefs

- `0x180009337`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`
- `0x18000938d`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::RuntimeClassInitialize(
        Windows::Internal::StateRepository::PackageResourceResolverServer *this,
        struct Windows::Internal::StateRepository::IPackage *a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, struct Windows::Internal::StateRepository::IPackage *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v13 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.MrtPackage", 0x2Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_ede4711a_0c90_4d5b_acf3_58af696d9425, &v13);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = v13;
    v12 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)v13 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
    v9 = v8(v7, a2, &v12);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 80LL))(v12, (char *)this + 64);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 88LL))(v12, (char *)this + 72);
        v6 = v9;
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 104LL))(v12, (char *)this + 80);
          v6 = v9;
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 112LL))(v12, (char *)this + 88);
            v6 = v9;
            if ( v9 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
              v6 = 0;
              goto LABEL_17;
            }
            v10 = 33;
          }
          else
          {
            v10 = 32;
          }
        }
        else
        {
          v10 = 31;
        }
      }
      else
      {
        v10 = 30;
      }
    }
    else
    {
      v10 = 28;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
      (const char *)(unsigned int)v9,
      v12);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v12);
  }
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
  return v6;
}

```

## disassembly

```asm
0x1800092a8  mov     [rsp-18h+arg_10], rbx
0x1800092ad  mov     [rsp-18h+arg_18], rsi
0x1800092b2  push    rbp
0x1800092b3  push    rdi
0x1800092b4  push    r14
0x1800092b6  mov     rbp, rsp
0x1800092b9  sub     rsp, 60h
0x1800092bd  mov     rax, cs:__security_cookie
0x1800092c4  xor     rax, rsp
0x1800092c7  mov     [rbp+var_10], rax
0x1800092cb  mov     r14, rdx
0x1800092ce  mov     [rbp+var_38], 0
0x1800092d6  mov     rsi, rcx
0x1800092d9  lea     r9, [rbp+string]; string
0x1800092dd  mov     edx, 2Bh ; '+'; length
0x1800092e2  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtPackage@@3QBGB; "Windows.Internal.StateRepository.MrtPac"...
0x1800092e9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800092ed  call    cs:__imp_WindowsCreateStringReference
0x1800092f3  test    eax, eax
0x1800092f5  jns     short loc_18000930C
0x1800092f7  xor     r9d, r9d; lpArguments
0x1800092fa  xor     r8d, r8d; nNumberOfArguments
0x1800092fd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009302  lea     edx, [r9+1]; dwExceptionFlags
0x180009306  call    cs:__imp_RaiseException
0x18000930c  mov     rbx, [rbp+string]
0x180009310  lea     rcx, [rbp+var_38]
0x180009314  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009319  lea     r8, [rbp+var_38]
0x18000931d  mov     rcx, rbx
0x180009320  lea     rdx, _GUID_ede4711a_0c90_4d5b_acf3_58af696d9425
0x180009327  call    cs:__imp_RoGetActivationFactory
0x18000932d  mov     ebx, eax
0x18000932f  test    eax, eax
0x180009331  jns     short loc_180009350
0x180009333  mov     rcx, [rbp+18h]; this
0x180009337  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000933e  mov     r9d, eax; char *
0x180009341  mov     edx, 19h; void *
0x180009346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000934b  jmp     loc_18000943F
0x180009350  mov     rdi, [rbp+var_38]
0x180009354  lea     rcx, [rbp+var_40]
0x180009358  mov     [rbp+var_40], 0
0x180009360  mov     rax, [rdi]
0x180009363  mov     rbx, [rax+50h]
0x180009367  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000936c  lea     r8, [rbp+var_40]
0x180009370  mov     rdx, r14
0x180009373  mov     rcx, rdi
0x180009376  mov     rax, rbx
0x180009379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000937e  mov     ebx, eax
0x180009380  test    eax, eax
0x180009382  jns     short loc_1800093AA
0x180009384  mov     edx, 1Ch; void *
0x180009389  mov     rcx, [rbp+18h]; this
0x18000938d  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180009394  mov     r9d, eax; char *
0x180009397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000939c  lea     rcx, [rbp+var_40]
0x1800093a0  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x1800093a5  jmp     loc_18000943F
0x1800093aa  mov     rcx, [rbp+var_40]
0x1800093ae  lea     rdx, [rsi+40h]
0x1800093b2  mov     rax, [rcx]
0x1800093b5  mov     rax, [rax+50h]
0x1800093b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093be  mov     ebx, eax
0x1800093c0  test    eax, eax
0x1800093c2  jns     short loc_1800093CB
0x1800093c4  mov     edx, 1Eh
0x1800093c9  jmp     short loc_180009389
0x1800093cb  mov     rcx, [rbp+var_40]
0x1800093cf  lea     rdx, [rsi+48h]
0x1800093d3  mov     rax, [rcx]
0x1800093d6  mov     rax, [rax+58h]
0x1800093da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093df  mov     ebx, eax
0x1800093e1  test    eax, eax
0x1800093e3  jns     short loc_1800093EC
0x1800093e5  mov     edx, 1Fh
0x1800093ea  jmp     short loc_180009389
0x1800093ec  mov     rcx, [rbp+var_40]
0x1800093f0  lea     rdx, [rsi+50h]
0x1800093f4  mov     rax, [rcx]
0x1800093f7  mov     rax, [rax+68h]
0x1800093fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009400  mov     ebx, eax
0x180009402  test    eax, eax
0x180009404  jns     short loc_180009410
0x180009406  mov     edx, 20h ; ' '
0x18000940b  jmp     loc_180009389
0x180009410  mov     rcx, [rbp+var_40]
0x180009414  lea     rdx, [rsi+58h]
0x180009418  mov     rax, [rcx]
0x18000941b  mov     rax, [rax+70h]
0x18000941f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009424  mov     ebx, eax
0x180009426  test    eax, eax
0x180009428  jns     short loc_180009434
0x18000942a  mov     edx, 21h ; '!'
0x18000942f  jmp     loc_180009389
0x180009434  lea     rcx, [rbp+var_40]
0x180009438  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000943d  xor     ebx, ebx
0x18000943f  lea     rcx, [rbp+var_38]
0x180009443  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009448  mov     eax, ebx
0x18000944a  mov     rcx, [rbp+var_10]
0x18000944e  xor     rcx, rsp; StackCookie
0x180009451  call    __security_check_cookie
0x180009456  lea     r11, [rsp+60h+var_s0]
0x18000945b  mov     rbx, [r11+30h]
0x18000945f  mov     rsi, [r11+38h]
0x180009463  mov     rsp, r11
0x180009466  pop     r14
0x180009468  pop     rdi
0x180009469  pop     rbp
0x18000946a  retn
```
