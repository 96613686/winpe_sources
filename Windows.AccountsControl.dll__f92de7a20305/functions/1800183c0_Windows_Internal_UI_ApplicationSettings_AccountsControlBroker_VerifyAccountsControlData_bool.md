# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyAccountsControlData(bool *)

- ea: `0x1800183c0`
- end: `0x180018521`
- name: `?VerifyAccountsControlData@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEA_N@Z`
- size: `353`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800137b0`

## callees

- `0x180002fe4`
- `0x180006eac`
- `0x18000c0ec`
- `0x1800183c0`
- `0x180018528`
- `0x180019e0c`
- `0x1800440a8`

## import_xrefs

- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180018487`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180018487`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800183ec`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800184a8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800183ec`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800184a8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180018430`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180018430`

## string_xrefs

- `0x1800183ff`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001845b`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyAccountsControlData(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        bool *a2)
{
  int UserContext; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  bool v11; // [rsp+60h] [rbp+28h] BYREF
  int v12; // [rsp+68h] [rbp+30h] BYREF
  void *v13; // [rsp+70h] [rbp+38h] BYREF
  unsigned __int64 v14; // [rsp+78h] [rbp+40h] BYREF

  *a2 = 0;
  v11 = 0;
  v9[0] = 0;
  UserContext = UMgrQueryUserContext(*((_QWORD *)this + 130), v9);
  v5 = UserContext;
  if ( UserContext >= 0 )
  {
    v13 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v13,
      0);
    v6 = UMgrQueryUserToken(v9[0], &v13);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v6 = IsDefaultAccount(v13, &v11);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v12 = 0;
        if ( (unsigned __int8)IsIsEmbeddedModeAllowedPresent() && (v6 = IsEmbeddedModeAllowed(&v12), v5 = v6, v6 < 0) )
        {
          v7 = 302;
        }
        else
        {
          v14 = 0;
          v6 = UMgrQueryUserContext(0, &v14);
          v5 = v6;
          if ( v6 >= 0 )
          {
            if ( !v11 || v12 )
            {
              v6 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(this, v14, 0, a2);
              v5 = v6;
              if ( v6 < 0 )
              {
                v7 = 315;
                goto LABEL_7;
              }
            }
            else
            {
              v6 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(this, v14, 1, a2);
              v5 = v6;
              if ( v6 < 0 )
              {
                v7 = 311;
                goto LABEL_7;
              }
            }
            v5 = 0;
            goto LABEL_20;
          }
          v7 = 306;
        }
      }
      else
      {
        v7 = 296;
      }
    }
    else
    {
      v7 = 295;
    }
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
LABEL_20:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x124,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)UserContext,
    v9[0]);
  return v5;
}

```

## disassembly

```asm
0x1800183c0  push    rbp
0x1800183c2  push    rbx
0x1800183c3  push    rsi
0x1800183c4  push    rdi
0x1800183c5  mov     rbp, rsp
0x1800183c8  sub     rsp, 38h
0x1800183cc  mov     rdi, rdx
0x1800183cf  mov     rsi, rcx
0x1800183d2  mov     byte ptr [rdx], 0
0x1800183d5  mov     [rbp+arg_0], 0
0x1800183d9  mov     [rbp+var_18], 0
0x1800183e1  lea     rdx, [rbp+var_18]
0x1800183e5  mov     rcx, [rcx+410h]
0x1800183ec  call    cs:__imp_UMgrQueryUserContext
0x1800183f2  mov     ebx, eax
0x1800183f4  test    eax, eax
0x1800183f6  jns     short loc_180018415
0x1800183f8  mov     rcx, [rbp+20h]; this
0x1800183fc  mov     r9d, eax; char *
0x1800183ff  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180018406  mov     edx, 124h; void *
0x18001840b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018410  jmp     loc_180018516
0x180018415  mov     [rbp+arg_10], 0
0x18001841d  xor     edx, edx
0x18001841f  lea     rcx, [rbp+arg_10]
0x180018423  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180018428  lea     rdx, [rbp+arg_10]
0x18001842c  mov     rcx, [rbp+var_18]
0x180018430  call    cs:__imp_UMgrQueryUserToken
0x180018436  mov     ebx, eax
0x180018438  test    eax, eax
0x18001843a  jns     short loc_180018443
0x18001843c  mov     edx, 127h
0x180018441  jmp     short loc_18001845B
0x180018443  lea     rdx, [rbp+arg_0]; bool *
0x180018447  mov     rcx, [rbp+arg_10]; void *
0x18001844b  call    ?IsDefaultAccount@@YAJPEAXAEA_N@Z; IsDefaultAccount(void *,bool &)
0x180018450  mov     ebx, eax
0x180018452  test    eax, eax
0x180018454  jns     short loc_180018473
0x180018456  mov     edx, 128h; void *
0x18001845b  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180018462  mov     r9d, eax; char *
0x180018465  mov     rcx, [rbp+20h]; this
0x180018469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001846e  jmp     loc_18001850D
0x180018473  mov     [rbp+arg_8], 0
0x18001847a  call    IsIsEmbeddedModeAllowedPresent
0x18001847f  test    al, al
0x180018481  jz      short loc_18001849A
0x180018483  lea     rcx, [rbp+arg_8]
0x180018487  call    cs:__imp_IsEmbeddedModeAllowed
0x18001848d  mov     ebx, eax
0x18001848f  test    eax, eax
0x180018491  jns     short loc_18001849A
0x180018493  mov     edx, 12Eh
0x180018498  jmp     short loc_18001845B
0x18001849a  mov     [rbp+arg_18], 0
0x1800184a2  lea     rdx, [rbp+arg_18]
0x1800184a6  xor     ecx, ecx
0x1800184a8  call    cs:__imp_UMgrQueryUserContext
0x1800184ae  mov     ebx, eax
0x1800184b0  test    eax, eax
0x1800184b2  jns     short loc_1800184BB
0x1800184b4  mov     edx, 132h
0x1800184b9  jmp     short loc_18001845B
0x1800184bb  cmp     [rbp+arg_0], 0
0x1800184bf  jz      short loc_1800184E9
0x1800184c1  cmp     [rbp+arg_8], 0
0x1800184c5  jnz     short loc_1800184E9
0x1800184c7  mov     r9, rdi; bool *
0x1800184ca  mov     r8b, 1; bool
0x1800184cd  mov     rdx, [rbp+arg_18]; unsigned __int64
0x1800184d1  mov     rcx, rsi; this
0x1800184d4  call    ?VerifyProviders@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_K_NPEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(unsigned __int64,bool,bool *)
0x1800184d9  mov     ebx, eax
0x1800184db  test    eax, eax
0x1800184dd  jns     short loc_18001850B
0x1800184df  mov     edx, 137h
0x1800184e4  jmp     loc_18001845B
0x1800184e9  mov     r9, rdi; bool *
0x1800184ec  xor     r8d, r8d; bool
0x1800184ef  mov     rdx, [rbp+arg_18]; unsigned __int64
0x1800184f3  mov     rcx, rsi; this
0x1800184f6  call    ?VerifyProviders@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_K_NPEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(unsigned __int64,bool,bool *)
0x1800184fb  mov     ebx, eax
0x1800184fd  test    eax, eax
0x1800184ff  jns     short loc_18001850B
0x180018501  mov     edx, 13Bh
0x180018506  jmp     loc_18001845B
0x18001850b  xor     ebx, ebx
0x18001850d  lea     rcx, [rbp+arg_10]
0x180018511  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018516  mov     eax, ebx
0x180018518  add     rsp, 38h
0x18001851c  pop     rdi
0x18001851d  pop     rsi
0x18001851e  pop     rbx
0x18001851f  pop     rbp
0x180018520  retn
```
