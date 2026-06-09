# SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(Windows::Security::Credentials::IWebAccount *,bool *)

- ea: `0x18001d104`
- end: `0x18001d26c`
- name: `?IsAccountPerUser@WorkAccountList@WorkAccess@SystemSettings@@AEBAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z`
- size: `360`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bb3c`
- `0x18001fc24`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18001197c`
- `0x18001d104`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d176`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d176`

## string_xrefs

- `0x18001d18f`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d1e1`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d14b`: `Windows.Security.Authentication.Web.Provider.WebAccountManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        bool *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  int v14; // [rsp+28h] [rbp-38h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a3 = 0;
  v15 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Provider.WebAccountManager",
    0x3Fu,
    0x3Eu);
  v5 = v17;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_b2e8e1a6_d49a_4032_84bf_1a2847747bf1, &v15);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
    v9 = **v15;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    v10 = v9(v8, &GUID_5c6ce37c_12b2_423a_bf3d_85b8d7e53656, &v13);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v14 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *, int *))(*(_QWORD *)v13 + 64LL))(
              v13,
              a2,
              &v14);
      v7 = v10;
      if ( v10 >= 0 )
      {
        *a3 = v14 == 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
        v7 = 0;
        goto LABEL_9;
      }
      v11 = 523;
    }
    else
    {
      v11 = 520;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v10,
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x205,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v13);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return v7;
}

```

## disassembly

```asm
0x18001d104  mov     [rsp-18h+arg_0], rbx
0x18001d109  mov     [rsp-18h+arg_18], rsi
0x18001d10e  push    rbp
0x18001d10f  push    rdi
0x18001d110  push    r14
0x18001d112  mov     rbp, rsp
0x18001d115  sub     rsp, 60h
0x18001d119  mov     rax, cs:__security_cookie
0x18001d120  xor     rax, rsp
0x18001d123  mov     [rbp+var_8], rax
0x18001d127  mov     rsi, r8
0x18001d12a  mov     r14, rdx
0x18001d12d  mov     byte ptr [r8], 0
0x18001d131  mov     [rbp+var_30], 0
0x18001d139  mov     [rbp+var_10], 0
0x18001d141  mov     r9d, 3Eh ; '>'; unsigned int
0x18001d147  lea     r8d, [r9+1]; unsigned int
0x18001d14b  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Provider_WebAccountManager@@3QBGB; "Windows.Security.Authentication.Web.Pro"...
0x18001d152  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001d156  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d15b  mov     rbx, [rbp+var_10]
0x18001d15f  lea     rcx, [rbp+var_30]
0x18001d163  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d168  lea     r8, [rbp+var_30]
0x18001d16c  lea     rdx, _GUID_b2e8e1a6_d49a_4032_84bf_1a2847747bf1
0x18001d173  mov     rcx, rbx
0x18001d176  call    cs:__imp_RoGetActivationFactory
0x18001d17d  nop     dword ptr [rax+rax+00h]
0x18001d182  mov     ebx, eax
0x18001d184  test    eax, eax
0x18001d186  jns     short loc_18001D1A5
0x18001d188  mov     rcx, [rbp+18h]; this
0x18001d18c  mov     r9d, eax; char *
0x18001d18f  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d196  mov     edx, 205h; void *
0x18001d19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1a0  jmp     loc_18001D23F
0x18001d1a5  mov     [rbp+var_40], 0
0x18001d1ad  mov     rbx, [rbp+var_30]
0x18001d1b1  mov     rax, [rbx]
0x18001d1b4  mov     rdi, [rax]
0x18001d1b7  lea     rcx, [rbp+var_40]
0x18001d1bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1c0  lea     r8, [rbp+var_40]
0x18001d1c4  lea     rdx, _GUID_5c6ce37c_12b2_423a_bf3d_85b8d7e53656
0x18001d1cb  mov     rcx, rbx
0x18001d1ce  mov     rax, rdi
0x18001d1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d6  mov     ebx, eax
0x18001d1d8  test    eax, eax
0x18001d1da  jns     short loc_18001D200
0x18001d1dc  mov     edx, 208h; void *
0x18001d1e1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d1e8  mov     r9d, eax; char *
0x18001d1eb  mov     rcx, [rbp+18h]; this
0x18001d1ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1f4  nop
0x18001d1f5  lea     rcx, [rbp+var_40]
0x18001d1f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1fe  jmp     short loc_18001D23F
0x18001d200  mov     [rbp+var_38], 0
0x18001d207  mov     rcx, [rbp+var_40]
0x18001d20b  mov     rax, [rcx]
0x18001d20e  lea     r8, [rbp+var_38]
0x18001d212  mov     rdx, r14
0x18001d215  mov     rax, [rax+40h]
0x18001d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d21e  mov     ebx, eax
0x18001d220  test    eax, eax
0x18001d222  jns     short loc_18001D22B
0x18001d224  mov     edx, 20Bh
0x18001d229  jmp     short loc_18001D1E1
0x18001d22b  cmp     [rbp+var_38], 0
0x18001d22f  setz    al
0x18001d232  mov     [rsi], al
0x18001d234  lea     rcx, [rbp+var_40]
0x18001d238  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d23d  xor     ebx, ebx
0x18001d23f  lea     rcx, [rbp+var_30]
0x18001d243  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d248  mov     eax, ebx
0x18001d24a  mov     rcx, [rbp+var_8]
0x18001d24e  xor     rcx, rsp; StackCookie
0x18001d251  call    __security_check_cookie
0x18001d256  lea     r11, [rsp+60h+var_s0]
0x18001d25b  mov     rbx, [r11+20h]
0x18001d25f  mov     rsi, [r11+38h]
0x18001d263  mov     rsp, r11
0x18001d266  pop     r14
0x18001d268  pop     rdi
0x18001d269  pop     rbp
0x18001d26a  retn
```
