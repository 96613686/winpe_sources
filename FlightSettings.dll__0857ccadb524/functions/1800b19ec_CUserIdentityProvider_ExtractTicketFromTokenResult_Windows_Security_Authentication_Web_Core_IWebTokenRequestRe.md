# CUserIdentityProvider::ExtractTicketFromTokenResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,HSTRING__ * *)

- ea: `0x1800b19ec`
- end: `0x1800b1d4a`
- name: `?ExtractTicketFromTokenResult@CUserIdentityProvider@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(CUserIdentityProvider *__hidden this, struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, HSTRING *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b1e24`
- `0x1800b3600`
- `0x1800b3af0`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18006dc84`
- `0x180086644`
- `0x1800961e0`
- `0x1800b19ec`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1bea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b1be0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b1be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1bf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1bf4`

## string_xrefs

- `0x1800b1a2e`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b1acd`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b1c9d`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b1d1b`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CUserIdentityProvider::ExtractTicketFromTokenResult(
        CUserIdentityProvider *this,
        struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *a2,
        HSTRING *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 (__fastcall *v8)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  int (__fastcall *v13)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  __int64 v14; // r9
  __int64 (__fastcall *v15)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // [rsp+20h] [rbp-28h] BYREF
  __int64 v23; // [rsp+28h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+30h] [rbp-18h] BYREF
  __int64 v25; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int v27; // [rsp+70h] [rbp+28h] BYREF
  int v28; // [rsp+74h] [rbp+2Ch]
  int v29; // [rsp+78h] [rbp+30h] BYREF
  int v30; // [rsp+80h] [rbp+38h] BYREF
  __int64 v31; // [rsp+88h] [rbp+40h] BYREF

  v28 = HIDWORD(this);
  *a3 = 0;
  v27 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, int *))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v27);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 818;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)v5,
      v22);
    return v5;
  }
  if ( v27 )
  {
    if ( v27 == 1 )
    {
      v5 = -2147023673;
      goto LABEL_9;
    }
    if ( v27 == 3 )
    {
      Token = 0;
      UstCommon::CComTemporaryRevertToSelf::RevertToSelf(&Token);
      v31 = 0;
      v13 = *(int (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a2 + 64LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      if ( v13(a2, &v31) >= 0 )
      {
        if ( v31 )
        {
          v29 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 48LL))(v31, &v29) >= 0 )
          {
            v14 = (unsigned int)v29;
            if ( v29 > 0 )
              v14 = (unsigned __int16)v29 | 0x80070000;
            v25 = -2147483646;
            FSRegUtils::SetFlightingRegDWORD(&v25, 4, L"UserRequiredErrorCode", v14);
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      if ( Token )
      {
        if ( !SetThreadToken(0, Token) )
          GetLastError();
        CloseHandle(Token);
      }
      v5 = -2138701812;
      goto LABEL_9;
    }
    if ( v27 != 5 )
    {
      v5 = -2147024344;
      goto LABEL_9;
    }
    v31 = 0;
    v8 = *(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a2 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    v9 = v8(a2, &v31);
    v5 = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v11 = 860;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)v10,
        v22);
LABEL_18:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      return v5;
    }
    if ( !v31 )
    {
      v5 = -2147024344;
      v10 = 2147942952LL;
      v11 = 861;
      goto LABEL_15;
    }
    v29 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 48LL))(v31, &v29);
    if ( v12 < 0 )
    {
      v5 = v12;
      goto LABEL_18;
    }
    v5 = v29;
    if ( v29 > 0 )
      v5 = (unsigned __int16)v29 | 0x80070000;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  }
  if ( v5 == -895025145 )
    return 3399942151LL;
LABEL_9:
  if ( v5 == -2138701812 )
    return 2156265484LL;
  result = 2148073494LL;
  if ( v5 != -2146893802 )
  {
    result = 3400335361LL;
    if ( v5 != -894631935 )
    {
      result = 3399942148LL;
      if ( v5 != -895025148 )
      {
        if ( (v5 & 0x80000000) != 0 )
        {
          v6 = 895;
          goto LABEL_3;
        }
        v23 = 0;
        v15 = *(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        v16 = v15(a2, &v23);
        v5 = v16;
        if ( v16 < 0 )
        {
          v17 = 899;
LABEL_45:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
            (const char *)(unsigned int)v16,
            v22);
LABEL_54:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
          return v5;
        }
        v30 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 56LL))(v23, &v30);
        v5 = v16;
        if ( v16 < 0 )
        {
          v17 = 903;
          goto LABEL_45;
        }
        if ( v30 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v22 = 0;
        v18 = v23;
        v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
        v20 = v19(v18, 0, &v22);
        v5 = v20;
        if ( v20 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 48LL))(v22, a3);
          v5 = v20;
          if ( v20 >= 0 )
          {
LABEL_53:
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
            goto LABEL_54;
          }
          v21 = 912;
        }
        else
        {
          v21 = 909;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
          (const char *)(unsigned int)v20,
          v22);
        goto LABEL_53;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b19ec  mov     [rsp-20h+arg_0], rcx
0x1800b19f1  push    rbp
0x1800b19f2  push    rbx
0x1800b19f3  push    rsi
0x1800b19f4  push    rdi
0x1800b19f5  mov     rbp, rsp
0x1800b19f8  sub     rsp, 48h
0x1800b19fc  mov     rsi, r8
0x1800b19ff  mov     rdi, rdx
0x1800b1a02  mov     qword ptr [r8], 0
0x1800b1a09  mov     dword ptr [rbp+arg_0], 0
0x1800b1a10  mov     rax, [rdx]
0x1800b1a13  lea     rdx, [rbp+arg_0]
0x1800b1a17  mov     rcx, rdi
0x1800b1a1a  mov     rax, [rax+38h]
0x1800b1a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1a23  mov     ebx, eax
0x1800b1a25  test    eax, eax
0x1800b1a27  jns     short loc_1800B1A46
0x1800b1a29  mov     edx, 332h; void *
0x1800b1a2e  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b1a35  mov     r9d, ebx; char *
0x1800b1a38  mov     rcx, [rbp+20h]; this
0x1800b1a3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1a41  jmp     loc_1800B1D3F
0x1800b1a46  mov     ecx, dword ptr [rbp+arg_0]
0x1800b1a49  test    ecx, ecx
0x1800b1a4b  jz      loc_1800B1B23
0x1800b1a51  sub     ecx, 1
0x1800b1a54  jz      loc_1800B1C04
0x1800b1a5a  sub     ecx, 2
0x1800b1a5d  jz      loc_1800B1B39
0x1800b1a63  cmp     ecx, 2
0x1800b1a66  jz      short loc_1800B1A80
0x1800b1a68  mov     ebx, 80070228h
0x1800b1a6d  cmp     ebx, 8086000Ch
0x1800b1a73  jnz     loc_1800B1C0E
0x1800b1a79  mov     eax, ebx
0x1800b1a7b  jmp     loc_1800B1D41
0x1800b1a80  mov     [rbp+arg_18], 0
0x1800b1a88  mov     rax, [rdi]
0x1800b1a8b  mov     rbx, [rax+40h]
0x1800b1a8f  lea     rcx, [rbp+arg_18]
0x1800b1a93  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1a98  lea     rdx, [rbp+arg_18]
0x1800b1a9c  mov     rcx, rdi
0x1800b1a9f  mov     rax, rbx
0x1800b1aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1aa7  mov     ebx, eax
0x1800b1aa9  test    eax, eax
0x1800b1aab  jns     short loc_1800B1AB7
0x1800b1aad  mov     r9d, eax
0x1800b1ab0  mov     edx, 35Ch
0x1800b1ab5  jmp     short loc_1800B1ACD
0x1800b1ab7  mov     rcx, [rbp+arg_18]
0x1800b1abb  test    rcx, rcx
0x1800b1abe  jnz     short loc_1800B1ADF
0x1800b1ac0  mov     ebx, 80070228h
0x1800b1ac5  mov     r9d, ebx; char *
0x1800b1ac8  mov     edx, 35Dh; void *
0x1800b1acd  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b1ad4  mov     rcx, [rbp+20h]; this
0x1800b1ad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1add  jmp     short loc_1800B1AFC
0x1800b1adf  mov     [rbp+arg_8], 0
0x1800b1ae6  mov     rax, [rcx]
0x1800b1ae9  lea     rdx, [rbp+arg_8]
0x1800b1aed  mov     rax, [rax+30h]
0x1800b1af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1af6  test    eax, eax
0x1800b1af8  jns     short loc_1800B1B0A
0x1800b1afa  mov     ebx, eax
0x1800b1afc  lea     rcx, [rbp+arg_18]
0x1800b1b00  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1b05  jmp     loc_1800B1D3F
0x1800b1b0a  mov     ebx, [rbp+arg_8]
0x1800b1b0d  test    ebx, ebx
0x1800b1b0f  jle     short loc_1800B1B1A
0x1800b1b11  movzx   ebx, bx
0x1800b1b14  or      ebx, 80070000h
0x1800b1b1a  lea     rcx, [rbp+arg_18]
0x1800b1b1e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1b23  cmp     ebx, 0CAA70007h
0x1800b1b29  jnz     loc_1800B1A6D
0x1800b1b2f  mov     eax, 0CAA70007h
0x1800b1b34  jmp     loc_1800B1D41
0x1800b1b39  mov     [rbp+Token], 0
0x1800b1b41  lea     rcx, [rbp+Token]; TokenHandle
0x1800b1b45  call    ?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ; UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)
0x1800b1b4a  mov     [rbp+arg_18], 0
0x1800b1b52  mov     rax, [rdi]
0x1800b1b55  mov     rbx, [rax+40h]
0x1800b1b59  lea     rcx, [rbp+arg_18]
0x1800b1b5d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1b62  lea     rdx, [rbp+arg_18]
0x1800b1b66  mov     rcx, rdi
0x1800b1b69  mov     rax, rbx
0x1800b1b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b71  test    eax, eax
0x1800b1b73  js      short loc_1800B1BCB
0x1800b1b75  mov     rcx, [rbp+arg_18]
0x1800b1b79  test    rcx, rcx
0x1800b1b7c  jz      short loc_1800B1BCB
0x1800b1b7e  mov     [rbp+arg_8], 0
0x1800b1b85  mov     rax, [rcx]
0x1800b1b88  lea     rdx, [rbp+arg_8]
0x1800b1b8c  mov     rax, [rax+30h]
0x1800b1b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1b95  test    eax, eax
0x1800b1b97  js      short loc_1800B1BCB
0x1800b1b99  mov     r9d, [rbp+arg_8]
0x1800b1b9d  test    r9d, r9d
0x1800b1ba0  jle     short loc_1800B1BAD
0x1800b1ba2  movzx   r9d, r9w
0x1800b1ba6  or      r9d, 80070000h
0x1800b1bad  mov     [rbp+var_10], 0FFFFFFFF80000002h
0x1800b1bb5  lea     r8, aUserrequireder; "UserRequiredErrorCode"
0x1800b1bbc  mov     edx, 4
0x1800b1bc1  lea     rcx, [rbp+var_10]
0x1800b1bc5  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b1bca  nop
0x1800b1bcb  lea     rcx, [rbp+arg_18]
0x1800b1bcf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1bd4  nop
0x1800b1bd5  mov     rdx, [rbp+Token]; Token
0x1800b1bd9  test    rdx, rdx
0x1800b1bdc  jz      short loc_1800B1BFA
0x1800b1bde  xor     ecx, ecx; Thread
0x1800b1be0  call    cs:__imp_SetThreadToken
0x1800b1be6  test    eax, eax
0x1800b1be8  jnz     short loc_1800B1BF0
0x1800b1bea  call    cs:__imp_GetLastError
0x1800b1bf0  mov     rcx, [rbp+Token]; hObject
0x1800b1bf4  call    cs:__imp_CloseHandle
0x1800b1bfa  mov     ebx, 8086000Ch
0x1800b1bff  jmp     loc_1800B1A6D
0x1800b1c04  mov     ebx, 800704C7h
0x1800b1c09  jmp     loc_1800B1A6D
0x1800b1c0e  mov     eax, 80090016h
0x1800b1c13  cmp     ebx, eax
0x1800b1c15  jz      loc_1800B1D41
0x1800b1c1b  mov     eax, 0CAAD0001h
0x1800b1c20  cmp     ebx, eax
0x1800b1c22  jz      loc_1800B1D41
0x1800b1c28  mov     eax, 0CAA70004h
0x1800b1c2d  cmp     ebx, eax
0x1800b1c2f  jz      loc_1800B1D41
0x1800b1c35  test    ebx, ebx
0x1800b1c37  jns     short loc_1800B1C43
0x1800b1c39  mov     edx, 37Fh
0x1800b1c3e  jmp     loc_1800B1A2E
0x1800b1c43  mov     [rbp+var_20], 0
0x1800b1c4b  mov     rax, [rdi]
0x1800b1c4e  mov     rbx, [rax+30h]
0x1800b1c52  lea     rcx, [rbp+var_20]
0x1800b1c56  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1c5b  lea     rdx, [rbp+var_20]
0x1800b1c5f  mov     rcx, rdi
0x1800b1c62  mov     rax, rbx
0x1800b1c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1c6a  mov     ebx, eax
0x1800b1c6c  test    eax, eax
0x1800b1c6e  jns     short loc_1800B1C77
0x1800b1c70  mov     edx, 383h
0x1800b1c75  jmp     short loc_1800B1C9D
0x1800b1c77  mov     [rbp+arg_10], 0
0x1800b1c7e  mov     rcx, [rbp+var_20]
0x1800b1c82  mov     rax, [rcx]
0x1800b1c85  lea     rdx, [rbp+arg_10]
0x1800b1c89  mov     rax, [rax+38h]
0x1800b1c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1c92  mov     ebx, eax
0x1800b1c94  test    eax, eax
0x1800b1c96  jns     short loc_1800B1CB5
0x1800b1c98  mov     edx, 387h; void *
0x1800b1c9d  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b1ca4  mov     r9d, eax; char *
0x1800b1ca7  mov     rcx, [rbp+20h]; this
0x1800b1cab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1cb0  jmp     loc_1800B1D36
0x1800b1cb5  cmp     [rbp+arg_10], 1
0x1800b1cb9  jz      short loc_1800B1CC0
0x1800b1cbb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "responsesLength == 1")
0x1800b1cc0  mov     [rbp+var_28], 0
0x1800b1cc8  mov     rdi, [rbp+var_20]
0x1800b1ccc  mov     rax, [rdi]
0x1800b1ccf  mov     rbx, [rax+30h]
0x1800b1cd3  lea     rcx, [rbp+var_28]
0x1800b1cd7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1cdc  lea     r8, [rbp+var_28]
0x1800b1ce0  xor     edx, edx
0x1800b1ce2  mov     rcx, rdi
0x1800b1ce5  mov     rax, rbx
0x1800b1ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ced  mov     ebx, eax
0x1800b1cef  test    eax, eax
0x1800b1cf1  jns     short loc_1800B1CFA
0x1800b1cf3  mov     edx, 38Dh
0x1800b1cf8  jmp     short loc_1800B1D18
0x1800b1cfa  mov     rcx, [rbp+var_28]
0x1800b1cfe  mov     rax, [rcx]
0x1800b1d01  mov     rdx, rsi
0x1800b1d04  mov     rax, [rax+30h]
0x1800b1d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1d0d  mov     ebx, eax
0x1800b1d0f  test    eax, eax
0x1800b1d11  jns     short loc_1800B1D2C
0x1800b1d13  mov     edx, 390h; void *
0x1800b1d18  mov     r9d, eax; char *
0x1800b1d1b  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b1d22  mov     rcx, [rbp+20h]; this
0x1800b1d26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1d2b  nop
0x1800b1d2c  lea     rcx, [rbp+var_28]
0x1800b1d30  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1d35  nop
0x1800b1d36  lea     rcx, [rbp+var_20]
0x1800b1d3a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1d3f  mov     eax, ebx
0x1800b1d41  add     rsp, 48h
0x1800b1d45  pop     rdi
0x1800b1d46  pop     rsi
0x1800b1d47  pop     rbx
0x1800b1d48  pop     rbp
0x1800b1d49  retn
```
