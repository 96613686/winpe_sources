# ImpersonateUser(Microsoft::WRL::ComPtr<Windows::System::IUser>)

- ea: `0x1800130b0`
- end: `0x1800132cf`
- name: `?ImpersonateUser@@YAJV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012340`

## callees

- `0x1800050f0`
- `0x180010440`
- `0x180011438`
- `0x1800130b0`
- `0x180013ae4`
- `0x1800152b4`
- `0x1800152d4`
- `0x18002c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180013280`
- `RPCRT4!RpcImpersonateClient` at `0x180013280`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001323b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001323b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013173`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013173`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001326d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001326d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800131e5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800131e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ImpersonateUser(_QWORD *a1)
{
  int v2; // eax
  unsigned int LastError; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rdx
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // rdx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-19h]
  __int64 v14; // [rsp+30h] [rbp-9h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-1h] BYREF
  int v16; // [rsp+40h] [rbp+7h] BYREF
  HANDLE Token; // [rsp+48h] [rbp+Fh] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+27h] BYREF
  __int64 v20; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v18[1] = a1;
  v16 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v16);
  LastError = v2;
  if ( v2 >= 0 )
  {
    if ( !v16 )
    {
      LastError = -2147023652;
      v4 = 2147943644LL;
      v5 = 1318;
      goto LABEL_5;
    }
    v14 = 0;
    v20 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v6 = v20;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v14);
    LastError = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v18[0] = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v14 + 136LL))(v14, *a1, v18);
      LastError = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        hExistingToken = 0;
        v9 = UMgrQueryUserToken(v18[0], &hExistingToken);
        LastError = v9;
        if ( v9 >= 0 )
        {
          Token = 0;
          if ( DuplicateTokenEx(hExistingToken, 4u, 0, SecurityImpersonation, TokenImpersonation, &Token) )
          {
            if ( SetThreadToken(0, Token) )
            {
              RpcImpersonateClient(0);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
              LastError = 0;
              goto LABEL_21;
            }
            v11 = 1335;
          }
          else
          {
            v11 = 1334;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v11,
                        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
                        v10);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x532,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
            (const char *)(unsigned int)v9,
            TokenType);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
        goto LABEL_9;
      }
      v8 = 1327;
    }
    else
    {
      v8 = 1324;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)ActivationFactory,
      TokenType);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
    goto LABEL_21;
  }
  v4 = (unsigned int)v2;
  v5 = 1317;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
    (const char *)v4,
    TokenType);
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
  return LastError;
}

```

## disassembly

```asm
0x1800130b0  mov     [rsp-8+arg_8], rbx
0x1800130b5  mov     [rsp-8+arg_10], rdi
0x1800130ba  push    rbp
0x1800130bb  lea     rbp, [rsp-57h]
0x1800130c0  sub     rsp, 90h
0x1800130c7  mov     rax, cs:__security_cookie
0x1800130ce  xor     rax, rsp
0x1800130d1  mov     [rbp+57h+var_10], rax
0x1800130d5  mov     rdi, rcx
0x1800130d8  mov     [rbp+57h+var_38], rcx
0x1800130dc  mov     [rbp+57h+var_50], 0
0x1800130e3  mov     rcx, [rcx]
0x1800130e6  mov     rax, [rcx]
0x1800130e9  lea     rdx, [rbp+57h+var_50]
0x1800130ed  mov     rax, [rax+38h]
0x1800130f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130f6  mov     ebx, eax
0x1800130f8  test    eax, eax
0x1800130fa  jns     short loc_180013106
0x1800130fc  mov     r9d, eax
0x1800130ff  mov     edx, 525h
0x180013104  jmp     short loc_180013119
0x180013106  cmp     [rbp+57h+var_50], 0
0x18001310a  jnz     short loc_18001312E
0x18001310c  mov     ebx, 800704DCh
0x180013111  mov     r9d, ebx; char *
0x180013114  mov     edx, 526h; void *
0x180013119  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180013120  mov     rcx, [rbp+5Fh]; this
0x180013124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013129  jmp     loc_1800132A4
0x18001312e  mov     [rbp+57h+var_60], 0
0x180013136  mov     [rbp+57h+var_18], 0
0x18001313e  mov     r9d, 23h ; '#'; unsigned int
0x180013144  lea     r8d, [r9+1]; unsigned int
0x180013148  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18001314f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180013153  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013158  mov     rbx, [rbp+57h+var_18]
0x18001315c  lea     rcx, [rbp+57h+var_60]
0x180013160  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180013165  lea     r8, [rbp+57h+var_60]
0x180013169  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180013170  mov     rcx, rbx
0x180013173  call    cs:__imp_RoGetActivationFactory
0x180013179  mov     ebx, eax
0x18001317b  test    eax, eax
0x18001317d  jns     short loc_1800131A6
0x18001317f  mov     edx, 52Ch; void *
0x180013184  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001318b  mov     r9d, eax; char *
0x18001318e  mov     rcx, [rbp+5Fh]; this
0x180013192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013197  nop
0x180013198  lea     rcx, [rbp+57h+var_60]
0x18001319c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800131a1  jmp     loc_1800132A4
0x1800131a6  mov     [rbp+57h+var_40], 0
0x1800131ae  mov     rcx, [rbp+57h+var_60]
0x1800131b2  mov     rax, [rcx]
0x1800131b5  lea     r8, [rbp+57h+var_40]
0x1800131b9  mov     rdx, [rdi]
0x1800131bc  mov     rax, [rax+88h]
0x1800131c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131c8  mov     ebx, eax
0x1800131ca  test    eax, eax
0x1800131cc  jns     short loc_1800131D5
0x1800131ce  mov     edx, 52Fh
0x1800131d3  jmp     short loc_180013184
0x1800131d5  mov     [rbp+57h+hExistingToken], 0
0x1800131dd  lea     rdx, [rbp+57h+hExistingToken]
0x1800131e1  mov     rcx, [rbp+57h+var_40]
0x1800131e5  call    cs:__imp_UMgrQueryUserToken
0x1800131eb  mov     ebx, eax
0x1800131ed  test    eax, eax
0x1800131ef  jns     short loc_180013214
0x1800131f1  mov     rcx, [rbp+5Fh]; this
0x1800131f5  mov     r9d, eax; char *
0x1800131f8  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800131ff  mov     edx, 532h; void *
0x180013204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013209  lea     rcx, [rbp+57h+hExistingToken]
0x18001320d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013212  jmp     short loc_180013198
0x180013214  mov     [rbp+57h+Token], 0
0x18001321c  lea     rax, [rbp+57h+Token]
0x180013220  mov     [rsp+90h+phNewToken], rax; phNewToken
0x180013225  mov     r9d, 2; ImpersonationLevel
0x18001322b  mov     [rsp+90h+TokenType], r9d; TokenType
0x180013230  xor     r8d, r8d; lpTokenAttributes
0x180013233  lea     edx, [r9+2]; dwDesiredAccess
0x180013237  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x18001323b  call    cs:__imp_DuplicateTokenEx
0x180013241  test    eax, eax
0x180013243  jnz     short loc_180013267
0x180013245  mov     edx, 536h; void *
0x18001324a  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180013251  mov     rcx, [rbp+5Fh]; this
0x180013255  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001325a  mov     ebx, eax
0x18001325c  lea     rcx, [rbp+57h+Token]
0x180013260  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013265  jmp     short loc_180013209
0x180013267  mov     rdx, [rbp+57h+Token]; Token
0x18001326b  xor     ecx, ecx; Thread
0x18001326d  call    cs:__imp_SetThreadToken
0x180013273  test    eax, eax
0x180013275  jnz     short loc_18001327E
0x180013277  mov     edx, 537h
0x18001327c  jmp     short loc_18001324A
0x18001327e  xor     ecx, ecx; BindingHandle
0x180013280  call    cs:__imp_RpcImpersonateClient
0x180013286  lea     rcx, [rbp+57h+Token]
0x18001328a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001328f  lea     rcx, [rbp+57h+hExistingToken]
0x180013293  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013298  nop
0x180013299  lea     rcx, [rbp+57h+var_60]
0x18001329d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800132a2  xor     ebx, ebx
0x1800132a4  mov     rcx, rdi
0x1800132a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800132ac  mov     eax, ebx
0x1800132ae  mov     rcx, [rbp+57h+var_10]
0x1800132b2  xor     rcx, rsp; StackCookie
0x1800132b5  call    __security_check_cookie
0x1800132ba  lea     r11, [rsp+90h+var_s0]
0x1800132c2  mov     rbx, [r11+18h]
0x1800132c6  mov     rdi, [r11+20h]
0x1800132ca  mov     rsp, r11
0x1800132cd  pop     rbp
0x1800132ce  retn
```
