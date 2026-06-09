# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::OnCreateSession(void)

- ea: `0x180022d50`
- end: `0x180022f03`
- name: `?OnCreateSession@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022f10`

## callees

- `0x180002140`
- `0x180003ce4`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18002239c`
- `0x180022614`
- `0x180022894`
- `0x180022d50`
- `0x180022f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180022d94`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180022d94`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180022dcf`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180022dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022da4`

## string_xrefs

- `0x180022ef1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180022de6`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::OnCreateSession(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)
{
  const char *v2; // r9
  int v3; // eax
  int v4; // ebx
  bool v6; // zf
  int CompareAddress[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v8[42]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v9[42]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v10[42]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+358h]

  while ( !*((_DWORD *)this + 8) )
  {
    CompareAddress[0] = 0;
    if ( !WaitOnAddress((char *)this + 32, CompareAddress, 4u, 0xFFFFFFFF) )
    {
      if ( GetLastError() != 1460 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xDBF,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v2);
      break;
    }
  }
  v3 = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::ConfigureWdagUtilityAccountForAutologon(this);
  *((_DWORD *)this + 4) = v3;
  *((_DWORD *)this + 5) = 1;
  v4 = v3;
  WakeByAddressAll((char *)this + 20);
  if ( v4 >= 0 )
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      (__int64)v8,
      (__int64)"FirstUserLogon");
    v8[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    CmAgentTraceProvider::FirstUserLogon::StartActivity((CmAgentTraceProvider::FirstUserLogon *)v8);
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      (__int64)v9,
      (__int64)v8,
      0);
    v6 = *((_DWORD *)this + 88) == 0;
    v9[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      (__int64)v10,
      (__int64)this + 40,
      !v6);
    v10[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
      (__int64)this + 40,
      (__int64)v9);
    v10[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v10);
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v10);
    v9[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v9);
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v9);
    v8[0] = &CmAgentTraceProvider::FirstUserLogon::`vftable';
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v8);
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v4,
      CompareAddress[0]);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180022d50  push    rbp
0x180022d52  push    rbx
0x180022d53  push    rsi
0x180022d54  push    rdi
0x180022d55  lea     rbp, [rsp-338h]
0x180022d5d  sub     rsp, 438h
0x180022d64  mov     rax, cs:__security_cookie
0x180022d6b  xor     rax, rsp
0x180022d6e  mov     [rbp+350h+var_30], rax
0x180022d75  mov     rdi, rcx
0x180022d78  mov     eax, [rdi+20h]
0x180022d7b  test    eax, eax
0x180022d7d  jnz     short loc_180022DBB
0x180022d7f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180022d83  mov     [rsp+450h+CompareAddress], eax; int
0x180022d87  lea     r8d, [rax+4]; AddressSize
0x180022d8b  lea     rdx, [rsp+450h+CompareAddress]; CompareAddress
0x180022d90  lea     rcx, [rdi+20h]; Address
0x180022d94  call    cs:__imp_WaitOnAddress
0x180022d9b  nop     dword ptr [rax+rax+00h]
0x180022da0  test    eax, eax
0x180022da2  jnz     short loc_180022D78
0x180022da4  call    cs:__imp_GetLastError
0x180022dab  nop     dword ptr [rax+rax+00h]
0x180022db0  cmp     eax, 5B4h
0x180022db5  jnz     loc_180022EEA
0x180022dbb  call    ?ConfigureWdagUtilityAccountForAutologon@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJXZ; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::ConfigureWdagUtilityAccountForAutologon(void)
0x180022dc0  lea     rcx, [rdi+14h]; Address
0x180022dc4  mov     [rdi+10h], eax
0x180022dc7  mov     dword ptr [rcx], 1
0x180022dcd  mov     ebx, eax
0x180022dcf  call    cs:__imp_WakeByAddressAll
0x180022dd6  nop     dword ptr [rax+rax+00h]
0x180022ddb  test    ebx, ebx
0x180022ddd  jns     short loc_180022E01
0x180022ddf  mov     rcx, [rbp+358h]; this
0x180022de6  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022ded  mov     r9d, ebx; char *
0x180022df0  mov     edx, 268h; void *
0x180022df5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022dfa  mov     eax, ebx
0x180022dfc  jmp     loc_180022ECE
0x180022e01  lea     rdx, aFirstuserlogon; "FirstUserLogon"
0x180022e08  lea     rcx, [rsp+450h+var_420]
0x180022e0d  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180022e12  lea     rsi, ??_7FirstUserLogon@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::FirstUserLogon::`vftable'
0x180022e19  lea     rcx, [rsp+450h+var_420]; this
0x180022e1e  mov     [rsp+450h+var_420], rsi
0x180022e23  call    ?StartActivity@FirstUserLogon@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::FirstUserLogon::StartActivity(void)
0x180022e28  xor     r8d, r8d
0x180022e2b  lea     rdx, [rsp+450h+var_420]
0x180022e30  lea     rcx, [rbp+350h+var_2D0]
0x180022e37  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x180022e3c  cmp     dword ptr [rdi+160h], 0
0x180022e43  lea     rdx, [rdi+28h]
0x180022e47  lea     rcx, [rbp+350h+var_180]
0x180022e4e  mov     [rbp+350h+var_2D0], rsi
0x180022e55  setnz   r8b
0x180022e59  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x180022e5e  lea     rdx, [rbp+350h+var_2D0]
0x180022e65  mov     [rbp+350h+var_180], rsi
0x180022e6c  lea     rcx, [rdi+28h]
0x180022e70  call    ??4?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x180022e75  lea     rcx, [rbp+350h+var_180]
0x180022e7c  mov     [rbp+350h+var_180], rsi
0x180022e83  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180022e88  lea     rcx, [rbp+350h+var_180]
0x180022e8f  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180022e94  lea     rcx, [rbp+350h+var_2D0]
0x180022e9b  mov     [rbp+350h+var_2D0], rsi
0x180022ea2  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180022ea7  lea     rcx, [rbp+350h+var_2D0]
0x180022eae  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180022eb3  lea     rcx, [rsp+450h+var_420]
0x180022eb8  mov     [rsp+450h+var_420], rsi
0x180022ebd  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180022ec2  lea     rcx, [rsp+450h+var_420]
0x180022ec7  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180022ecc  xor     eax, eax
0x180022ece  mov     rcx, [rbp+350h+var_30]
0x180022ed5  xor     rcx, rsp; StackCookie
0x180022ed8  call    __security_check_cookie
0x180022edd  add     rsp, 438h
0x180022ee4  pop     rdi
0x180022ee5  pop     rsi
0x180022ee6  pop     rbx
0x180022ee7  pop     rbp
0x180022ee8  retn
0x180022eea  mov     rcx, [rbp+358h]; this
0x180022ef1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022ef8  mov     edx, 0DBFh; void *
0x180022efd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
