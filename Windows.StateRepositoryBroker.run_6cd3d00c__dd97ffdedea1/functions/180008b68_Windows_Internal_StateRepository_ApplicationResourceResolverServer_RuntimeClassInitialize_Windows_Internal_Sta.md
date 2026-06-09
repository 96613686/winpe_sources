# Windows::Internal::StateRepository::ApplicationResourceResolverServer::RuntimeClassInitialize(Windows::Internal::StateRepository::IApplication *)

- ea: `0x180008b68`
- end: `0x180008dee`
- name: `?RuntimeClassInitialize@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@QEAAJPEAUIApplication@234@@Z`
- size: `646`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, struct Windows::Internal::StateRepository::IApplication *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006d10`

## callees

- `0x180001d60`
- `0x180006224`
- `0x1800071a4`
- `0x180008b68`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bc6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008bad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008be7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008be7`

## string_xrefs

- `0x180008bf7`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x180008c4d`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::RuntimeClassInitialize(
        Windows::Internal::StateRepository::ApplicationResourceResolverServer *this,
        struct Windows::Internal::StateRepository::IApplication *a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, struct Windows::Internal::StateRepository::IApplication *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v13 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.MrtApplication", 0x2Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_f7e80409_27e5_4514_805f_a431c4ce3b96, &v13);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = v13;
    v12 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplication *, __int64 *))(*(_QWORD *)v13 + 80LL);
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
          v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 96LL))(v12, (char *)this + 80);
          v6 = v9;
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 104LL))(v12, (char *)this + 88);
            v6 = v9;
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 120LL))(v12, (char *)this + 96);
              v6 = v9;
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 136LL))(v12, (char *)this + 104);
                v6 = v9;
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 152LL))(v12, (char *)this + 112);
                  v6 = v9;
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 184LL))(v12, (char *)this + 120);
                    v6 = v9;
                    if ( v9 >= 0 )
                    {
                      v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 200LL))(
                             v12,
                             (char *)this + 128);
                      v6 = v9;
                      if ( v9 >= 0 )
                      {
                        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
                        v6 = 0;
                        goto LABEL_27;
                      }
                      v10 = 38;
                    }
                    else
                    {
                      v10 = 37;
                    }
                  }
                  else
                  {
                    v10 = 36;
                  }
                }
                else
                {
                  v10 = 35;
                }
              }
              else
              {
                v10 = 34;
              }
            }
            else
            {
              v10 = 33;
            }
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)v9,
      v12);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v12);
  }
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v13);
  return v6;
}

```

## disassembly

```asm
0x180008b68  mov     [rsp-18h+arg_10], rbx
0x180008b6d  mov     [rsp-18h+arg_18], rsi
0x180008b72  push    rbp
0x180008b73  push    rdi
0x180008b74  push    r14
0x180008b76  mov     rbp, rsp
0x180008b79  sub     rsp, 60h
0x180008b7d  mov     rax, cs:__security_cookie
0x180008b84  xor     rax, rsp
0x180008b87  mov     [rbp+var_10], rax
0x180008b8b  mov     r14, rdx
0x180008b8e  mov     [rbp+var_38], 0
0x180008b96  mov     rsi, rcx
0x180008b99  lea     r9, [rbp+string]; string
0x180008b9d  mov     edx, 2Fh ; '/'; length
0x180008ba2  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtApplication@@3QBGB; "Windows.Internal.StateRepository.MrtApp"...
0x180008ba9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180008bad  call    cs:__imp_WindowsCreateStringReference
0x180008bb3  test    eax, eax
0x180008bb5  jns     short loc_180008BCC
0x180008bb7  xor     r9d, r9d; lpArguments
0x180008bba  xor     r8d, r8d; nNumberOfArguments
0x180008bbd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008bc2  lea     edx, [r9+1]; dwExceptionFlags
0x180008bc6  call    cs:__imp_RaiseException
0x180008bcc  mov     rbx, [rbp+string]
0x180008bd0  lea     rcx, [rbp+var_38]
0x180008bd4  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180008bd9  lea     r8, [rbp+var_38]
0x180008bdd  mov     rcx, rbx
0x180008be0  lea     rdx, _GUID_f7e80409_27e5_4514_805f_a431c4ce3b96
0x180008be7  call    cs:__imp_RoGetActivationFactory
0x180008bed  mov     ebx, eax
0x180008bef  test    eax, eax
0x180008bf1  jns     short loc_180008C10
0x180008bf3  mov     rcx, [rbp+18h]; this
0x180008bf7  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008bfe  mov     r9d, eax; char *
0x180008c01  mov     edx, 19h; void *
0x180008c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c0b  jmp     loc_180008DC2
0x180008c10  mov     rdi, [rbp+var_38]
0x180008c14  lea     rcx, [rbp+var_40]
0x180008c18  mov     [rbp+var_40], 0
0x180008c20  mov     rax, [rdi]
0x180008c23  mov     rbx, [rax+50h]
0x180008c27  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180008c2c  lea     r8, [rbp+var_40]
0x180008c30  mov     rdx, r14
0x180008c33  mov     rcx, rdi
0x180008c36  mov     rax, rbx
0x180008c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3e  mov     ebx, eax
0x180008c40  test    eax, eax
0x180008c42  jns     short loc_180008C6A
0x180008c44  mov     edx, 1Ch; void *
0x180008c49  mov     rcx, [rbp+18h]; this
0x180008c4d  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008c54  mov     r9d, eax; char *
0x180008c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c5c  lea     rcx, [rbp+var_40]
0x180008c60  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180008c65  jmp     loc_180008DC2
0x180008c6a  mov     rcx, [rbp+var_40]
0x180008c6e  lea     rdx, [rsi+40h]
0x180008c72  mov     rax, [rcx]
0x180008c75  mov     rax, [rax+50h]
0x180008c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7e  mov     ebx, eax
0x180008c80  test    eax, eax
0x180008c82  jns     short loc_180008C8B
0x180008c84  mov     edx, 1Eh
0x180008c89  jmp     short loc_180008C49
0x180008c8b  mov     rcx, [rbp+var_40]
0x180008c8f  lea     rdx, [rsi+48h]
0x180008c93  mov     rax, [rcx]
0x180008c96  mov     rax, [rax+58h]
0x180008c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9f  mov     ebx, eax
0x180008ca1  test    eax, eax
0x180008ca3  jns     short loc_180008CAC
0x180008ca5  mov     edx, 1Fh
0x180008caa  jmp     short loc_180008C49
0x180008cac  mov     rcx, [rbp+var_40]
0x180008cb0  lea     rdx, [rsi+50h]
0x180008cb4  mov     rax, [rcx]
0x180008cb7  mov     rax, [rax+60h]
0x180008cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc0  mov     ebx, eax
0x180008cc2  test    eax, eax
0x180008cc4  jns     short loc_180008CD0
0x180008cc6  mov     edx, 20h ; ' '
0x180008ccb  jmp     loc_180008C49
0x180008cd0  mov     rcx, [rbp+var_40]
0x180008cd4  lea     rdx, [rsi+58h]
0x180008cd8  mov     rax, [rcx]
0x180008cdb  mov     rax, [rax+68h]
0x180008cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce4  mov     ebx, eax
0x180008ce6  test    eax, eax
0x180008ce8  jns     short loc_180008CF4
0x180008cea  mov     edx, 21h ; '!'
0x180008cef  jmp     loc_180008C49
0x180008cf4  mov     rcx, [rbp+var_40]
0x180008cf8  lea     rdx, [rsi+60h]
0x180008cfc  mov     rax, [rcx]
0x180008cff  mov     rax, [rax+78h]
0x180008d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d08  mov     ebx, eax
0x180008d0a  test    eax, eax
0x180008d0c  jns     short loc_180008D18
0x180008d0e  mov     edx, 22h ; '"'
0x180008d13  jmp     loc_180008C49
0x180008d18  mov     rcx, [rbp+var_40]
0x180008d1c  lea     rdx, [rsi+68h]
0x180008d20  mov     rax, [rcx]
0x180008d23  mov     rax, [rax+88h]
0x180008d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2f  mov     ebx, eax
0x180008d31  test    eax, eax
0x180008d33  jns     short loc_180008D3F
0x180008d35  mov     edx, 23h ; '#'
0x180008d3a  jmp     loc_180008C49
0x180008d3f  mov     rcx, [rbp+var_40]
0x180008d43  lea     rdx, [rsi+70h]
0x180008d47  mov     rax, [rcx]
0x180008d4a  mov     rax, [rax+98h]
0x180008d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d56  mov     ebx, eax
0x180008d58  test    eax, eax
0x180008d5a  jns     short loc_180008D66
0x180008d5c  mov     edx, 24h ; '$'
0x180008d61  jmp     loc_180008C49
0x180008d66  mov     rcx, [rbp+var_40]
0x180008d6a  lea     rdx, [rsi+78h]
0x180008d6e  mov     rax, [rcx]
0x180008d71  mov     rax, [rax+0B8h]
0x180008d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d7d  mov     ebx, eax
0x180008d7f  test    eax, eax
0x180008d81  jns     short loc_180008D8D
0x180008d83  mov     edx, 25h ; '%'
0x180008d88  jmp     loc_180008C49
0x180008d8d  mov     rcx, [rbp+var_40]
0x180008d91  lea     rdx, [rsi+80h]
0x180008d98  mov     rax, [rcx]
0x180008d9b  mov     rax, [rax+0C8h]
0x180008da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da7  mov     ebx, eax
0x180008da9  test    eax, eax
0x180008dab  jns     short loc_180008DB7
0x180008dad  mov     edx, 26h ; '&'
0x180008db2  jmp     loc_180008C49
0x180008db7  lea     rcx, [rbp+var_40]
0x180008dbb  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180008dc0  xor     ebx, ebx
0x180008dc2  lea     rcx, [rbp+var_38]
0x180008dc6  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180008dcb  mov     eax, ebx
0x180008dcd  mov     rcx, [rbp+var_10]
0x180008dd1  xor     rcx, rsp; StackCookie
0x180008dd4  call    __security_check_cookie
0x180008dd9  lea     r11, [rsp+60h+var_s0]
0x180008dde  mov     rbx, [r11+30h]
0x180008de2  mov     rsi, [r11+38h]
0x180008de6  mov     rsp, r11
0x180008de9  pop     r14
0x180008deb  pop     rdi
0x180008dec  pop     rbp
0x180008ded  retn
```
