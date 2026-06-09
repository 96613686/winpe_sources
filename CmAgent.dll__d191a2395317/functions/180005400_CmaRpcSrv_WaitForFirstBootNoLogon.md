# CmaRpcSrv_WaitForFirstBootNoLogon

- ea: `0x180005400`
- end: `0x180005520`
- name: `CmaRpcSrv_WaitForFirstBootNoLogon`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x180005400`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18001c8a8`
- `0x180020194`
- `0x180020308`

## string_xrefs

- `0x1800054e2`: `onecore\base\gendrv\silos\clem\agent\service\api.cpp`
- `0x18000546a`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall CmaRpcSrv_WaitForFirstBootNoLogon(__int64 a1, int a2, int a3, int *a4)
{
  int started; // eax
  unsigned int *v6; // rdx
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // edi
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-188h] BYREF
  int v13; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v14[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v13 = a3;
  v12 = a2;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v14,
    (__int64)"WaitForFirstBootNoLogon");
  v14[0] = &CmAgentTraceProvider::WaitForFirstBootNoLogon::`vftable';
  CmAgentTraceProvider::WaitForFirstBootNoLogon::StartActivity((CmAgentTraceProvider::WaitForFirstBootNoLogon *)v14);
  started = Container::Manager::Agent::Core::_anonymous_namespace_::WaitForAutoStartServices((DWORD *)&v12);
  v7 = started;
  if ( started < 0 )
  {
    v8 = 1092;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)started);
    v9 = 0;
    goto LABEL_10;
  }
  started = Container::Manager::Agent::Core::WaitForSystemQuiesce((Container::Manager::Agent::Core *)&v13, v6);
  v7 = started;
  if ( started == -2147023436 )
  {
    v9 = 1;
  }
  else
  {
    if ( started < 0 )
    {
      v8 = 1104;
      goto LABEL_3;
    }
    v9 = 0;
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    (__int64)v14,
    0);
  v7 = 0;
LABEL_10:
  v14[0] = &CmAgentTraceProvider::WaitForFirstBootNoLogon::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v14);
  if ( v7 >= 0 )
  {
    *a4 = v9;
    result = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      (const char *)(unsigned int)v7);
    result = (unsigned int)v7;
  }
  try
  {
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCB,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      v10);
  }
  return result;
}

```

## disassembly

```asm
0x180005400  mov     [rsp+arg_0], rbx
0x180005405  push    rsi
0x180005406  push    rdi
0x180005407  push    r14
0x180005409  sub     rsp, 190h
0x180005410  mov     rax, cs:__security_cookie
0x180005417  xor     rax, rsp
0x18000541a  mov     [rsp+1A8h+var_28], rax
0x180005422  mov     rsi, r9
0x180005425  mov     [rsp+1A8h+var_180], r8d
0x18000542a  mov     [rsp+1A8h+var_188], edx; int
0x18000542e  lea     rdx, aWaitforfirstbo_0; "WaitForFirstBootNoLogon"
0x180005435  lea     rcx, [rsp+1A8h+var_178]
0x18000543a  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000543f  lea     r14, ??_7WaitForFirstBootNoLogon@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::WaitForFirstBootNoLogon::`vftable'
0x180005446  mov     [rsp+1A8h+var_178], r14
0x18000544b  lea     rcx, [rsp+1A8h+var_178]; this
0x180005450  call    ?StartActivity@WaitForFirstBootNoLogon@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::WaitForFirstBootNoLogon::StartActivity(void)
0x180005455  lea     rcx, [rsp+1A8h+var_188]
0x18000545a  call    Container__Manager__Agent__Core___anonymous_namespace___WaitForAutoStartServices
0x18000545f  mov     ebx, eax
0x180005461  test    eax, eax
0x180005463  jns     short loc_180005485
0x180005465  mov     edx, 444h; void *
0x18000546a  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180005471  mov     r9d, eax; char *
0x180005474  mov     rcx, [rsp+1A8h]; this
0x18000547c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005481  xor     edi, edi
0x180005483  jmp     short loc_1800054BA
0x180005485  lea     rcx, [rsp+1A8h+var_180]; this
0x18000548a  call    ?WaitForSystemQuiesce@Core@Agent@Manager@Container@@YAJAEAK@Z; Container::Manager::Agent::Core::WaitForSystemQuiesce(ulong &)
0x18000548f  mov     ebx, eax
0x180005491  cmp     eax, 800705B4h
0x180005496  jnz     short loc_18000549F
0x180005498  mov     edi, 1
0x18000549d  jmp     short loc_1800054AC
0x18000549f  test    eax, eax
0x1800054a1  jns     short loc_1800054AA
0x1800054a3  mov     edx, 450h
0x1800054a8  jmp     short loc_18000546A
0x1800054aa  xor     edi, edi
0x1800054ac  xor     edx, edx
0x1800054ae  lea     rcx, [rsp+1A8h+var_178]
0x1800054b3  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800054b8  xor     ebx, ebx
0x1800054ba  mov     [rsp+1A8h+var_178], r14
0x1800054bf  lea     rcx, [rsp+1A8h+var_178]
0x1800054c4  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800054c9  lea     rcx, [rsp+1A8h+var_178]
0x1800054ce  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800054d3  test    ebx, ebx
0x1800054d5  jns     short loc_1800054F7
0x1800054d7  mov     rcx, [rsp+1A8h]; this
0x1800054df  mov     r9d, ebx; char *
0x1800054e2  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800054e9  mov     edx, 0C4h; void *
0x1800054ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054f3  mov     eax, ebx
0x1800054f5  jmp     short loc_1800054FB
0x1800054f7  mov     [rsi], edi
0x1800054f9  xor     eax, eax
0x1800054fb  mov     rcx, [rsp+1A8h+var_28]
0x180005503  xor     rcx, rsp; StackCookie
0x180005506  call    __security_check_cookie
0x18000550b  mov     rbx, [rsp+1A8h+arg_0]
0x180005513  add     rsp, 190h
0x18000551a  pop     r14
0x18000551c  pop     rdi
0x18000551d  pop     rsi
0x18000551e  retn
```
