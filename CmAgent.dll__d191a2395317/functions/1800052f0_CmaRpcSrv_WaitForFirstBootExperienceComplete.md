# CmaRpcSrv_WaitForFirstBootExperienceComplete

- ea: `0x1800052f0`
- end: `0x1800053f9`
- name: `CmaRpcSrv_WaitForFirstBootExperienceComplete`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x1800052f0`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18001c774`
- `0x180023090`

## string_xrefs

- `0x1800053b6`: `onecore\base\gendrv\silos\clem\agent\service\api.cpp`
- `0x18000536d`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall CmaRpcSrv_WaitForFirstBootExperienceComplete(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  int BootExperienceComplete; // eax
  int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  unsigned __int8 v11[16]; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v12[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v11[0] = 0;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v12,
    (__int64)"WaitForFirstBootExperience");
  v12[0] = &CmAgentTraceProvider::WaitForFirstBootExperience::`vftable';
  CmAgentTraceProvider::WaitForFirstBootExperience::StartActivity((CmAgentTraceProvider::WaitForFirstBootExperience *)v12);
  BootExperienceComplete = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForFirstBootExperienceComplete(
                             qword_18004B978,
                             a2,
                             a3,
                             (bool *)v11);
  v8 = BootExperienceComplete;
  if ( BootExperienceComplete >= 0 )
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      (__int64)v12,
      0);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41C,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)BootExperienceComplete);
  }
  v12[0] = &CmAgentTraceProvider::WaitForFirstBootExperience::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v12);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v12);
  if ( v8 >= 0 )
  {
    *a4 = v11[0];
    result = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      (const char *)(unsigned int)v8);
    result = (unsigned int)v8;
  }
  try
  {
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xAF,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800052f0  mov     [rsp+arg_0], rbx
0x1800052f5  push    rsi
0x1800052f6  push    rdi
0x1800052f7  push    r14
0x1800052f9  sub     rsp, 190h
0x180005300  mov     rax, cs:__security_cookie
0x180005307  xor     rax, rsp
0x18000530a  mov     [rsp+1A8h+var_28], rax
0x180005312  mov     rdi, r9
0x180005315  mov     esi, r8d
0x180005318  mov     ebx, edx
0x18000531a  mov     [rsp+1A8h+var_188], 0; int
0x18000531f  lea     rdx, aWaitforfirstbo; "WaitForFirstBootExperience"
0x180005326  lea     rcx, [rsp+1A8h+var_178]
0x18000532b  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180005330  lea     r14, ??_7WaitForFirstBootExperience@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::WaitForFirstBootExperience::`vftable'
0x180005337  mov     [rsp+1A8h+var_178], r14
0x18000533c  lea     rcx, [rsp+1A8h+var_178]; this
0x180005341  call    ?StartActivity@WaitForFirstBootExperience@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::WaitForFirstBootExperience::StartActivity(void)
0x180005346  lea     r9, [rsp+1A8h+var_188]; bool *
0x18000534b  mov     r8d, esi; unsigned int
0x18000534e  mov     edx, ebx; unsigned int
0x180005350  mov     rcx, cs:qword_18004B978; this
0x180005357  call    ?WaitForFirstBootExperienceComplete@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAAJKKAEA_N@Z; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForFirstBootExperienceComplete(ulong,ulong,bool &)
0x18000535c  mov     ebx, eax
0x18000535e  test    eax, eax
0x180005360  jns     short loc_180005380
0x180005362  mov     rcx, [rsp+1A8h]; this
0x18000536a  mov     r9d, eax; char *
0x18000536d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180005374  mov     edx, 41Ch; void *
0x180005379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000537e  jmp     short loc_18000538E
0x180005380  xor     edx, edx
0x180005382  lea     rcx, [rsp+1A8h+var_178]
0x180005387  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000538c  xor     ebx, ebx
0x18000538e  mov     [rsp+1A8h+var_178], r14
0x180005393  lea     rcx, [rsp+1A8h+var_178]
0x180005398  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000539d  lea     rcx, [rsp+1A8h+var_178]
0x1800053a2  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800053a7  test    ebx, ebx
0x1800053a9  jns     short loc_1800053CB
0x1800053ab  mov     rcx, [rsp+1A8h]; this
0x1800053b3  mov     r9d, ebx; char *
0x1800053b6  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800053bd  mov     edx, 0A8h; void *
0x1800053c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053c7  mov     eax, ebx
0x1800053c9  jmp     short loc_1800053D4
0x1800053cb  movzx   eax, [rsp+1A8h+var_188]
0x1800053d0  mov     [rdi], eax
0x1800053d2  xor     eax, eax
0x1800053d4  mov     rcx, [rsp+1A8h+var_28]
0x1800053dc  xor     rcx, rsp; StackCookie
0x1800053df  call    __security_check_cookie
0x1800053e4  mov     rbx, [rsp+1A8h+arg_0]
0x1800053ec  add     rsp, 190h
0x1800053f3  pop     r14
0x1800053f5  pop     rdi
0x1800053f6  pop     rsi
0x1800053f7  retn
```
