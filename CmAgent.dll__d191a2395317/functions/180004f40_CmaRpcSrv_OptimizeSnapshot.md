# CmaRpcSrv_OptimizeSnapshot

- ea: `0x180004f40`
- end: `0x180005044`
- name: `CmaRpcSrv_OptimizeSnapshot`
- size: `260`
- prototype: `__int64 __fastcall(__int64, int, int *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x180004f40`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18001c0e8`
- `0x180020308`

## string_xrefs

- `0x180005006`: `onecore\base\gendrv\silos\clem\agent\service\api.cpp`
- `0x180004fb9`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall CmaRpcSrv_OptimizeSnapshot(__int64 a1, int a2, int *a3, __int64 a4)
{
  unsigned int *v5; // rdx
  int v6; // eax
  int v7; // ebx
  int v8; // edi
  const char *v9; // r9
  __int64 result; // rax
  int v11[4]; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v12[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v11[0] = a2;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "OptimizeSnapshot",
    a3,
    a4);
  v12[0] = &CmAgentTraceProvider::OptimizeSnapshot::`vftable';
  CmAgentTraceProvider::OptimizeSnapshot::StartActivity((CmAgentTraceProvider::OptimizeSnapshot *)v12);
  v6 = Container::Manager::Agent::Core::WaitForSystemQuiesce((Container::Manager::Agent::Core *)v11, v5);
  v7 = v6;
  if ( v6 == -2147023436 )
  {
    v8 = 1;
  }
  else
  {
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B5,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v6,
        v11[0]);
      v8 = 0;
      goto LABEL_7;
    }
    v8 = 0;
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v12,
    0);
  v7 = 0;
LABEL_7:
  v12[0] = &CmAgentTraceProvider::OptimizeSnapshot::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v12);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v12);
  if ( v7 >= 0 )
  {
    *a3 = v8;
    result = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      (const char *)(unsigned int)v7,
      v11[0]);
    result = (unsigned int)v7;
  }
  try
  {
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
      v9);
  }
  return result;
}

```

## disassembly

```asm
0x180004f40  mov     [rsp+arg_0], rbx
0x180004f45  push    rsi
0x180004f46  push    rdi
0x180004f47  push    r14
0x180004f49  sub     rsp, 190h
0x180004f50  mov     rax, cs:__security_cookie
0x180004f57  xor     rax, rsp
0x180004f5a  mov     [rsp+1A8h+var_28], rax
0x180004f62  mov     rsi, r8
0x180004f65  mov     [rsp+1A8h+var_188], edx; int
0x180004f69  lea     rdx, aOptimizesnapsh; "OptimizeSnapshot"
0x180004f70  lea     rcx, [rsp+1A8h+var_178]
0x180004f75  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180004f7a  lea     r14, ??_7OptimizeSnapshot@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::OptimizeSnapshot::`vftable'
0x180004f81  mov     [rsp+1A8h+var_178], r14
0x180004f86  lea     rcx, [rsp+1A8h+var_178]; this
0x180004f8b  call    ?StartActivity@OptimizeSnapshot@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::OptimizeSnapshot::StartActivity(void)
0x180004f90  lea     rcx, [rsp+1A8h+var_188]; this
0x180004f95  call    ?WaitForSystemQuiesce@Core@Agent@Manager@Container@@YAJAEAK@Z; Container::Manager::Agent::Core::WaitForSystemQuiesce(ulong &)
0x180004f9a  mov     ebx, eax
0x180004f9c  cmp     eax, 800705B4h
0x180004fa1  jnz     short loc_180004FAA
0x180004fa3  mov     edi, 1
0x180004fa8  jmp     short loc_180004FD0
0x180004faa  test    eax, eax
0x180004fac  jns     short loc_180004FCE
0x180004fae  mov     rcx, [rsp+1A8h]; this
0x180004fb6  mov     r9d, eax; char *
0x180004fb9  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004fc0  mov     edx, 4B5h; void *
0x180004fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fca  xor     edi, edi
0x180004fcc  jmp     short loc_180004FDE
0x180004fce  xor     edi, edi
0x180004fd0  xor     edx, edx
0x180004fd2  lea     rcx, [rsp+1A8h+var_178]
0x180004fd7  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180004fdc  xor     ebx, ebx
0x180004fde  mov     [rsp+1A8h+var_178], r14
0x180004fe3  lea     rcx, [rsp+1A8h+var_178]
0x180004fe8  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180004fed  lea     rcx, [rsp+1A8h+var_178]
0x180004ff2  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180004ff7  test    ebx, ebx
0x180004ff9  jns     short loc_18000501B
0x180004ffb  mov     rcx, [rsp+1A8h]; this
0x180005003  mov     r9d, ebx; char *
0x180005006  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18000500d  mov     edx, 0FBh; void *
0x180005012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005017  mov     eax, ebx
0x180005019  jmp     short loc_18000501F
0x18000501b  mov     [rsi], edi
0x18000501d  xor     eax, eax
0x18000501f  mov     rcx, [rsp+1A8h+var_28]
0x180005027  xor     rcx, rsp; StackCookie
0x18000502a  call    __security_check_cookie
0x18000502f  mov     rbx, [rsp+1A8h+arg_0]
0x180005037  add     rsp, 190h
0x18000503e  pop     r14
0x180005040  pop     rdi
0x180005041  pop     rsi
0x180005042  retn
```
