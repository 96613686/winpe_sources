# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::CreateWithProcessIdForUser(Windows::System::IUser *,HSTRING__ *,uint,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability * *)

- ea: `0x1800159f0`
- end: `0x180015af4`
- name: `?CreateWithProcessIdForUser@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAUIUser@System@5@PEAUHSTRING__@@IPEAPEAUIAppCapability@2345@@Z`
- size: `260`
- prototype: `__int64 __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory *__hidden this, struct Windows::System::IUser *, HSTRING, unsigned int, struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapability **TokenInformation)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e1fc`
- `0x18000e21c`
- `0x180012ac4`
- `0x1800159f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015a82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015a82`

## string_xrefs

- `0x180015a1e`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x180015a90`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::CreateWithProcessIdForUser(
        Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory *this,
        struct Windows::System::IUser *a2,
        HSTRING a3,
        unsigned int a4,
        struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapability **TokenInformation)
{
  struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapability **v5; // rdi
  int LastError; // ebx
  __int64 v7; // rdx
  const char *v9; // r9
  int ReturnLength; // [rsp+20h] [rbp-20h]
  DWORD v11[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct Windows::System::IUser *v13; // [rsp+68h] [rbp+28h] BYREF
  HSTRING v14; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF

  v15 = a4;
  v14 = a3;
  v13 = a2;
  v5 = TokenInformation;
  if ( !TokenInformation )
  {
    LastError = -2147467261;
    v7 = 32;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    return (unsigned int)LastError;
  }
  *TokenInformation = 0;
  if ( !a3 )
  {
    LastError = -2147024809;
    v7 = 35;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    LastError = -2147024809;
    v7 = 36;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    LODWORD(TokenInformation) = 0;
    v11[0] = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, v11) )
    {
      if ( (_DWORD)TokenInformation )
      {
        LastError = -2147024809;
        v7 = 43;
        goto LABEL_3;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x298,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                    v9);
      if ( LastError < 0 )
      {
        v7 = 42;
        goto LABEL_3;
      }
    }
  }
  LastError = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,HSTRING__ * &,Windows::System::IUser * &,unsigned int &>(
                v5,
                &v14,
                &v13,
                &v15);
  if ( LastError < 0 )
  {
    v7 = 50;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800159f0  mov     [rsp-18h+arg_18], r9d
0x1800159f5  mov     [rsp-18h+arg_10], r8
0x1800159fa  mov     [rsp-18h+arg_8], rdx
0x1800159ff  push    rbp
0x180015a00  push    rbx
0x180015a01  push    rdi
0x180015a02  mov     rbp, rsp
0x180015a05  sub     rsp, 40h
0x180015a09  mov     rdi, [rbp+TokenInformation]
0x180015a0d  test    rdi, rdi
0x180015a10  jnz     short loc_180015A34
0x180015a12  mov     ebx, 80004003h
0x180015a17  lea     edx, [rdi+20h]; void *
0x180015a1a  mov     rcx, [rbp+18h]; this
0x180015a1e  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180015a25  mov     r9d, ebx; char *
0x180015a28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a2d  mov     eax, ebx
0x180015a2f  jmp     loc_180015AEC
0x180015a34  mov     qword ptr [rdi], 0
0x180015a3b  test    r8, r8
0x180015a3e  jnz     short loc_180015A4B
0x180015a40  mov     ebx, 80070057h
0x180015a45  lea     edx, [r8+23h]
0x180015a49  jmp     short loc_180015A1A
0x180015a4b  test    r9d, r9d
0x180015a4e  jnz     short loc_180015A5B
0x180015a50  mov     ebx, 80070057h
0x180015a55  lea     edx, [r9+24h]
0x180015a59  jmp     short loc_180015A1A
0x180015a5b  test    rdx, rdx
0x180015a5e  jnz     short loc_180015AC6
0x180015a60  lea     r9d, [rdx+4]; TokenInformationLength
0x180015a64  mov     dword ptr [rbp+TokenInformation], edx
0x180015a67  mov     [rbp+var_10], edx
0x180015a6a  lea     rax, [rbp+var_10]
0x180015a6e  lea     edx, [r9+19h]; TokenInformationClass
0x180015a72  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x180015a77  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180015a7b  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180015a82  call    cs:__imp_GetTokenInformation
0x180015a88  test    eax, eax
0x180015a8a  jnz     short loc_180015AB1
0x180015a8c  mov     rcx, [rbp+18h]; this
0x180015a90  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015a97  mov     edx, 298h; void *
0x180015a9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015aa1  mov     ebx, eax
0x180015aa3  test    eax, eax
0x180015aa5  jns     short loc_180015AC6
0x180015aa7  mov     edx, 2Ah ; '*'
0x180015aac  jmp     loc_180015A1A
0x180015ab1  cmp     dword ptr [rbp+TokenInformation], 0
0x180015ab5  jz      short loc_180015AC6
0x180015ab7  mov     ebx, 80070057h
0x180015abc  mov     edx, 2Bh ; '+'
0x180015ac1  jmp     loc_180015A1A
0x180015ac6  lea     r9, [rbp+arg_18]
0x180015aca  mov     rcx, rdi
0x180015acd  lea     r8, [rbp+arg_8]
0x180015ad1  lea     rdx, [rbp+arg_10]
0x180015ad5  call    ??$MakeAndInitialize@VAppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UIAppCapability@2345@AEAPEAUHSTRING__@@AEAPEAUIUser@System@5@AEAI@Details@WRL@Microsoft@@YAJPEAPEAUIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@AEAPEAUHSTRING__@@AEAPEAUIUser@System@7@AEAI@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,HSTRING__ * &,Windows::System::IUser * &,uint &>(Windows::Security::Authorization::AppCapabilityAccess::IAppCapability * *,HSTRING__ * &,Windows::System::IUser * &,uint &)
0x180015ada  mov     ebx, eax
0x180015adc  test    eax, eax
0x180015ade  jns     short loc_180015AEA
0x180015ae0  mov     edx, 32h ; '2'
0x180015ae5  jmp     loc_180015A1A
0x180015aea  xor     eax, eax
0x180015aec  add     rsp, 40h
0x180015af0  pop     rdi
0x180015af1  pop     rbx
0x180015af2  pop     rbp
0x180015af3  retn
```
