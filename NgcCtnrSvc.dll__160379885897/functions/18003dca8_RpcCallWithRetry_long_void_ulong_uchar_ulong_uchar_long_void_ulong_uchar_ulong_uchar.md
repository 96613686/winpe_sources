# RpcCallWithRetry<long (&)(void *,ulong *,uchar * *),ulong * &,uchar * * &>(long (&)(void *,ulong *,uchar * *),ulong * &,uchar * * &)

- ea: `0x18003dca8`
- end: `0x18003de24`
- name: `??$RpcCallWithRetry@A6AJPEAXPEAKPEAPEAE@ZAEAPEAKAEAPEAPEAE@@YAJA6AJPEAXPEAKPEAPEAE@ZAEAPEAKAEAPEAPEAE@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003dad0`

## callees

- `0x180023278`
- `0x1800232a0`
- `0x18003dca8`
- `0x18004148c`
- `0x180041664`
- `0x180042120`
- `0x180042214`
- `0x180042250`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ddcb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ddcb`
- `RPCRT4!RpcExceptionFilter` at `0x18007dc6b`
- `RPCRT4!RpcExceptionFilter` at `0x18007dc6b`

## string_xrefs

- `0x18003dcf2`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003dd5f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003ddb1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003de00`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RpcCallWithRetry<long (&)(void *,unsigned long *,unsigned char * *),unsigned long * &,unsigned char * * &>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  NgcIsoRpcClient *v5; // rax
  NgcIsoRpcClient *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rbx
  __int64 v11; // rdi
  NgcIsoRpcClient *v12; // rax
  void *v13; // rax
  int AuthorizationNonce; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = NgcIsoRpcClient::Instance();
  if ( NgcIsoRpcClient::IsBound(v5)
    || (v6 = NgcIsoRpcClient::Instance(), v7 = NgcIsoRpcClient::Bind(v6), v8 = v7, v7 >= 0) )
  {
    v10 = *a3;
    v11 = *a2;
    v12 = NgcIsoRpcClient::Instance();
    v13 = NgcIsoRpcClient::BindingHandle(v12);
    AuthorizationNonce = c_NgcIsoGetAuthorizationNonce(v13, v11, v10);
    v15 = AuthorizationNonce;
    if ( AuthorizationNonce < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
        (const char *)(unsigned int)AuthorizationNonce,
        20);
    return v15;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
      (const char *)(unsigned int)v7,
      v16);
    return v8;
  }
}

```

## disassembly

```asm
0x18003dca8  mov     [rsp+arg_10], r8
0x18003dcad  mov     [rsp+arg_8], rdx
0x18003dcb2  mov     qword ptr [rsp+arg_0], rcx
0x18003dcb7  push    rbx
0x18003dcb8  push    rsi
0x18003dcb9  push    rdi
0x18003dcba  push    r14
0x18003dcbc  sub     rsp, 38h
0x18003dcc0  mov     rdi, r8
0x18003dcc3  mov     r14, rdx
0x18003dcc6  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dccb  mov     rcx, rax; this
0x18003dcce  call    ?IsBound@NgcIsoRpcClient@@QEBA_NXZ; NgcIsoRpcClient::IsBound(void)
0x18003dcd3  test    al, al
0x18003dcd5  jnz     short loc_18003DD0A
0x18003dcd7  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dcdc  mov     rcx, rax; this
0x18003dcdf  call    ?Bind@NgcIsoRpcClient@@QEAAJXZ; NgcIsoRpcClient::Bind(void)
0x18003dce4  mov     ebx, eax
0x18003dce6  test    eax, eax
0x18003dce8  jns     short loc_18003DD0A
0x18003dcea  mov     rcx, [rsp+58h]; this
0x18003dcef  mov     r9d, eax; char *
0x18003dcf2  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003dcf9  mov     edx, 0E5h; void *
0x18003dcfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd03  mov     eax, ebx
0x18003dd05  jmp     loc_18003DE19
0x18003dd0a  lea     rsi, c_NgcIsoGetAuthorizationNonce
0x18003dd11  mov     [rsp+58h+var_30], rsi
0x18003dd16  mov     ecx, 14h
0x18003dd1b  mov     [rsp+58h+var_38], ecx; int
0x18003dd1f  xor     eax, eax
0x18003dd21  mov     [rsp+58h+arg_18], eax
0x18003dd25  cmp     eax, ecx
0x18003dd27  jnb     loc_18003DE17
0x18003dd2d  mov     rbx, [rdi]
0x18003dd30  mov     rdi, [r14]
0x18003dd33  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dd38  mov     rcx, rax; this
0x18003dd3b  call    ?BindingHandle@NgcIsoRpcClient@@QEBAPEAXXZ; NgcIsoRpcClient::BindingHandle(void)
0x18003dd40  mov     r8, rbx
0x18003dd43  mov     rdx, rdi
0x18003dd46  mov     rcx, rax
0x18003dd49  mov     rax, rsi
0x18003dd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd51  mov     ebx, eax
0x18003dd53  test    eax, eax
0x18003dd55  jns     short loc_18003DD70
0x18003dd57  mov     rcx, [rsp+58h]; this
0x18003dd5c  mov     r9d, eax; char *
0x18003dd5f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003dd66  mov     edx, 0F0h; void *
0x18003dd6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd70  mov     eax, ebx
0x18003dd72  jmp     loc_18003DE19
0x18003dd77  mov     r9d, eax
0x18003dd7a  mov     [rsp+58h+arg_0], 0
0x18003dd7f  lea     rdx, [rsp+58h+arg_0]; bool *
0x18003dd84  mov     ecx, eax; int
0x18003dd86  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003dd8b  test    al, al
0x18003dd8d  jz      short loc_18003DDF6
0x18003dd8f  cmp     [rsp+58h+arg_0], 0
0x18003dd94  jz      short loc_18003DDC6
0x18003dd96  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dd9b  mov     rcx, rax; this
0x18003dd9e  call    ?Bind@NgcIsoRpcClient@@QEAAJXZ; NgcIsoRpcClient::Bind(void)
0x18003dda3  mov     ebx, eax
0x18003dda5  test    eax, eax
0x18003dda7  jns     short loc_18003DDC6
0x18003dda9  mov     rcx, [rsp+58h]; this
0x18003ddae  mov     r9d, eax; char *
0x18003ddb1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003ddb8  mov     edx, 0FAh; void *
0x18003ddbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ddc2  mov     eax, ebx
0x18003ddc4  jmp     short loc_18003DE19
0x18003ddc6  mov     ecx, 1F4h; dwMilliseconds
0x18003ddcb  call    cs:__imp_Sleep
0x18003ddd2  nop     dword ptr [rax+rax+00h]
0x18003ddd7  nop
0x18003ddd8  mov     eax, [rsp+58h+arg_18]
0x18003dddc  inc     eax
0x18003ddde  mov     rdi, [rsp+58h+arg_10]
0x18003dde3  mov     r14, [rsp+58h+arg_8]
0x18003dde8  mov     rsi, [rsp+58h+var_30]
0x18003dded  mov     ecx, [rsp+58h+var_38]
0x18003ddf1  jmp     loc_18003DD21
0x18003ddf6  test    r9d, r9d
0x18003ddf9  jz      short loc_18003DE13
0x18003ddfb  mov     rcx, [rsp+58h]; this
0x18003de00  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003de07  mov     edx, 101h; void *
0x18003de0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003de11  jmp     short loc_18003DE19
0x18003de13  xor     eax, eax
0x18003de15  jmp     short loc_18003DE19
0x18003de17  xor     eax, eax
0x18003de19  add     rsp, 38h
0x18003de1d  pop     r14
0x18003de1f  pop     rdi
0x18003de20  pop     rsi
0x18003de21  pop     rbx
0x18003de22  retn
0x18007dc5d  push    rbp
0x18007dc5f  sub     rsp, 20h
0x18007dc63  mov     rbp, rdx
0x18007dc66  mov     rcx, [rcx]
0x18007dc69  mov     ecx, [rcx]; ExceptionCode
0x18007dc6b  call    cs:__imp_RpcExceptionFilter
0x18007dc72  nop     dword ptr [rax+rax+00h]
0x18007dc77  nop
0x18007dc78  add     rsp, 20h
0x18007dc7c  pop     rbp
0x18007dc7d  retn
```
