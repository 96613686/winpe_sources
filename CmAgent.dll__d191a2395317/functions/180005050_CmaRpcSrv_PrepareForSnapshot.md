# CmaRpcSrv_PrepareForSnapshot

- ea: `0x180005050`
- end: `0x18000520b`
- name: `CmaRpcSrv_PrepareForSnapshot`
- size: `443`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x180005050`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18000b820`
- `0x18001666c`
- `0x18001c21c`
- `0x1800200e4`
- `0x180020194`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005138`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005198`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005138`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005198`

## string_xrefs

- `0x1800051ce`: `onecore\base\gendrv\silos\clem\agent\service\api.cpp`
- `0x1800050dc`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180005122`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall CmaRpcSrv_PrepareForSnapshot(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  int started; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // edi
  int updated; // eax
  __int64 v10; // rdx
  const char *v11; // r9
  __int64 result; // rax
  HKEY hKey; // [rsp+20h] [rbp-178h] BYREF
  HKEY v14; // [rsp+28h] [rbp-170h]
  _QWORD v15[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v4 = 0;
  v14 = 0;
  if ( a2 )
  {
    LODWORD(hKey) = *a2;
    BYTE4(hKey) = 1;
    v4 = (unsigned int)hKey;
    v14 = hKey;
  }
  LODWORD(hKey) = a3;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "PrepareForSnapshot",
    a3,
    a4);
  v15[0] = &CmAgentTraceProvider::PrepareForSnapshot::`vftable';
  CmAgentTraceProvider::PrepareForSnapshot::StartActivity((CmAgentTraceProvider::PrepareForSnapshot *)v15);
  started = Container::Manager::Agent::Core::_anonymous_namespace_::WaitForAutoStartServices(&hKey);
  v8 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)started,
      (int)hKey);
    goto LABEL_17;
  }
  hKey = 0;
  updated = Csl::CreateOrOpenRegistryKey(v6, L"SYSTEM\\Setup", v7, &hKey);
  v8 = updated;
  if ( updated < 0 )
  {
    v10 = 1151;
    goto LABEL_7;
  }
  updated = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&hKey, L"Respecialize", 0);
  v8 = updated;
  if ( updated < 0 )
  {
    v10 = 1153;
    goto LABEL_7;
  }
  if ( BYTE4(v14) )
  {
    updated = Container::Manager::Agent::Core::_anonymous_namespace_::UpdateUbrRegistryValue(v4);
    v8 = updated;
    if ( updated < 0 )
    {
      v10 = 1160;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)updated,
        (int)hKey);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_17;
    }
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v15,
    0);
  if ( hKey )
    RegCloseKey(hKey);
  v8 = 0;
LABEL_17:
  v15[0] = &CmAgentTraceProvider::PrepareForSnapshot::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
  if ( v8 >= 0 )
  {
    result = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      (const char *)(unsigned int)v8,
      (int)hKey);
    result = (unsigned int)v8;
  }
  try
  {
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      v11);
  }
  return result;
}

```

## disassembly

```asm
0x180005050  mov     [rsp+arg_0], rbx
0x180005055  mov     [rsp+arg_8], rsi
0x18000505a  push    rdi
0x18000505b  sub     rsp, 190h
0x180005062  mov     rax, cs:__security_cookie
0x180005069  xor     rax, rsp
0x18000506c  mov     [rsp+198h+var_18], rax
0x180005074  xor     ebx, ebx
0x180005076  mov     [rsp+198h+var_170], rbx
0x18000507b  test    rdx, rdx
0x18000507e  jz      short loc_180005095
0x180005080  mov     eax, [rdx]
0x180005082  mov     dword ptr [rsp+198h+hKey], eax
0x180005086  mov     byte ptr [rsp+198h+hKey+4], 1
0x18000508b  mov     rbx, [rsp+198h+hKey]
0x180005090  mov     [rsp+198h+var_170], rbx
0x180005095  mov     dword ptr [rsp+198h+hKey], r8d; int
0x18000509a  lea     rdx, aPrepareforsnap; "PrepareForSnapshot"
0x1800050a1  lea     rcx, [rsp+198h+var_168]
0x1800050a6  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800050ab  lea     rsi, ??_7PrepareForSnapshot@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::PrepareForSnapshot::`vftable'
0x1800050b2  mov     [rsp+198h+var_168], rsi
0x1800050b7  lea     rcx, [rsp+198h+var_168]; this
0x1800050bc  call    ?StartActivity@PrepareForSnapshot@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::PrepareForSnapshot::StartActivity(void)
0x1800050c1  lea     rcx, [rsp+198h+hKey]
0x1800050c6  call    Container__Manager__Agent__Core___anonymous_namespace___WaitForAutoStartServices
0x1800050cb  mov     edi, eax
0x1800050cd  test    eax, eax
0x1800050cf  jns     short loc_1800050F2
0x1800050d1  mov     rcx, [rsp+198h]; this
0x1800050d9  mov     r9d, eax; char *
0x1800050dc  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800050e3  mov     edx, 475h; void *
0x1800050e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050ed  jmp     loc_1800051A6
0x1800050f2  mov     [rsp+198h+hKey], 0; int
0x1800050fb  lea     r9, [rsp+198h+hKey]
0x180005100  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180005107  call    ?CreateOrOpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::CreateOrOpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x18000510c  mov     edi, eax
0x18000510e  test    eax, eax
0x180005110  jns     short loc_180005146
0x180005112  mov     edx, 47Fh; void *
0x180005117  mov     rcx, [rsp+198h]; this
0x18000511f  mov     r9d, eax; char *
0x180005122  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180005129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000512e  mov     rcx, [rsp+198h+hKey]; hKey
0x180005133  test    rcx, rcx
0x180005136  jz      short loc_1800051A6
0x180005138  call    cs:__imp_RegCloseKey
0x18000513f  nop     dword ptr [rax+rax+00h]
0x180005144  jmp     short loc_1800051A6
0x180005146  xor     r8d, r8d; unsigned int
0x180005149  lea     rdx, aRespecialize; "Respecialize"
0x180005150  lea     rcx, [rsp+198h+hKey]; this
0x180005155  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x18000515a  mov     edi, eax
0x18000515c  test    eax, eax
0x18000515e  jns     short loc_180005167
0x180005160  mov     edx, 481h
0x180005165  jmp     short loc_180005117
0x180005167  cmp     byte ptr [rsp+198h+var_170+4], 0
0x18000516c  jz      short loc_180005182
0x18000516e  mov     ecx, ebx; unsigned int
0x180005170  call    Container__Manager__Agent__Core___anonymous_namespace___UpdateUbrRegistryValue
0x180005175  mov     edi, eax
0x180005177  test    eax, eax
0x180005179  jns     short loc_180005182
0x18000517b  mov     edx, 488h
0x180005180  jmp     short loc_180005117
0x180005182  xor     edx, edx
0x180005184  lea     rcx, [rsp+198h+var_168]
0x180005189  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000518e  mov     rcx, [rsp+198h+hKey]; hKey
0x180005193  test    rcx, rcx
0x180005196  jz      short loc_1800051A4
0x180005198  call    cs:__imp_RegCloseKey
0x18000519f  nop     dword ptr [rax+rax+00h]
0x1800051a4  xor     edi, edi
0x1800051a6  mov     [rsp+198h+var_168], rsi
0x1800051ab  lea     rcx, [rsp+198h+var_168]
0x1800051b0  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800051b5  lea     rcx, [rsp+198h+var_168]
0x1800051ba  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800051bf  test    edi, edi
0x1800051c1  jns     short loc_1800051E3
0x1800051c3  mov     rcx, [rsp+198h]; this
0x1800051cb  mov     r9d, edi; char *
0x1800051ce  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800051d5  mov     edx, 0E3h; void *
0x1800051da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051df  mov     eax, edi
0x1800051e1  jmp     short loc_1800051E5
0x1800051e3  xor     eax, eax
0x1800051e5  mov     rcx, [rsp+198h+var_18]
0x1800051ed  xor     rcx, rsp; StackCookie
0x1800051f0  call    __security_check_cookie
0x1800051f5  lea     r11, [rsp+198h+var_8]
0x1800051fd  mov     rbx, [r11+10h]
0x180005201  mov     rsi, [r11+18h]
0x180005205  mov     rsp, r11
0x180005208  pop     rdi
0x180005209  retn
```
