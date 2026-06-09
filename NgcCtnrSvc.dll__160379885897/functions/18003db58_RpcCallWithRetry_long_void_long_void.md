# RpcCallWithRetry<long (&)(void *),>(long (&)(void *))

- ea: `0x18003db58`
- end: `0x18003dc9f`
- name: `??$RpcCallWithRetry@A6AJPEAX@Z$$V@@YAJA6AJPEAX@Z@Z`
- size: `327`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(void *))`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003cbf0`
- `0x18003da58`

## callees

- `0x180023278`
- `0x1800232a0`
- `0x18003db58`
- `0x18004148c`
- `0x180041664`
- `0x180042120`
- `0x180042214`
- `0x180042250`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003dc53`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003dc53`

## string_xrefs

- `0x18003db92`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003dbe7`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003dc39`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18003dc7e`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RpcCallWithRetry<long (&)(void *),>(__int64 (__fastcall *a1)(void *))
{
  NgcIsoRpcClient *v2; // rax
  NgcIsoRpcClient *v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  NgcIsoRpcClient *v7; // rax
  void *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = NgcIsoRpcClient::Instance();
  if ( NgcIsoRpcClient::IsBound(v2)
    || (v3 = NgcIsoRpcClient::Instance(), v4 = NgcIsoRpcClient::Bind(v3), v5 = v4, v4 >= 0) )
  {
    v7 = NgcIsoRpcClient::Instance();
    v8 = NgcIsoRpcClient::BindingHandle(v7);
    v9 = a1(v8);
    v10 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
        (const char *)(unsigned int)v9,
        v11);
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
      (const char *)(unsigned int)v4,
      v11);
    return v5;
  }
}

```

## disassembly

```asm
0x18003db58  mov     [rsp+arg_0], rcx
0x18003db5d  push    rbx
0x18003db5e  push    rdi
0x18003db5f  sub     rsp, 28h
0x18003db63  mov     rdi, rcx
0x18003db66  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003db6b  mov     rcx, rax; this
0x18003db6e  call    ?IsBound@NgcIsoRpcClient@@QEBA_NXZ; NgcIsoRpcClient::IsBound(void)
0x18003db73  test    al, al
0x18003db75  jnz     short loc_18003DBAA
0x18003db77  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003db7c  mov     rcx, rax; this
0x18003db7f  call    ?Bind@NgcIsoRpcClient@@QEAAJXZ; NgcIsoRpcClient::Bind(void)
0x18003db84  mov     ebx, eax
0x18003db86  test    eax, eax
0x18003db88  jns     short loc_18003DBAA
0x18003db8a  mov     rcx, [rsp+38h]; this
0x18003db8f  mov     r9d, eax; char *
0x18003db92  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003db99  mov     edx, 0E5h; void *
0x18003db9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dba3  mov     eax, ebx
0x18003dba5  jmp     loc_18003DC97
0x18003dbaa  mov     ecx, 14h
0x18003dbaf  mov     [rsp+38h+arg_18], ecx
0x18003dbb3  xor     eax, eax
0x18003dbb5  mov     [rsp+38h+arg_10], eax
0x18003dbb9  cmp     eax, ecx
0x18003dbbb  jnb     loc_18003DC95
0x18003dbc1  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dbc6  mov     rcx, rax; this
0x18003dbc9  call    ?BindingHandle@NgcIsoRpcClient@@QEBAPEAXXZ; NgcIsoRpcClient::BindingHandle(void)
0x18003dbce  mov     rcx, rax
0x18003dbd1  mov     rax, rdi
0x18003dbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbd9  mov     ebx, eax
0x18003dbdb  test    eax, eax
0x18003dbdd  jns     short loc_18003DBF8
0x18003dbdf  mov     rcx, [rsp+38h]; this
0x18003dbe4  mov     r9d, eax; char *
0x18003dbe7  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003dbee  mov     edx, 0F0h; void *
0x18003dbf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dbf8  mov     eax, ebx
0x18003dbfa  jmp     loc_18003DC97
0x18003dbff  mov     r9d, eax
0x18003dc02  mov     [rsp+38h+arg_8], 0
0x18003dc07  lea     rdx, [rsp+38h+arg_8]; bool *
0x18003dc0c  mov     ecx, eax; int
0x18003dc0e  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003dc13  test    al, al
0x18003dc15  jz      short loc_18003DC74
0x18003dc17  cmp     [rsp+38h+arg_8], 0
0x18003dc1c  jz      short loc_18003DC4E
0x18003dc1e  call    ?Instance@NgcIsoRpcClient@@SAAEAV1@XZ; NgcIsoRpcClient::Instance(void)
0x18003dc23  mov     rcx, rax; this
0x18003dc26  call    ?Bind@NgcIsoRpcClient@@QEAAJXZ; NgcIsoRpcClient::Bind(void)
0x18003dc2b  mov     ebx, eax
0x18003dc2d  test    eax, eax
0x18003dc2f  jns     short loc_18003DC4E
0x18003dc31  mov     rcx, [rsp+38h]; this
0x18003dc36  mov     r9d, eax; char *
0x18003dc39  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003dc40  mov     edx, 0FAh; void *
0x18003dc45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dc4a  mov     eax, ebx
0x18003dc4c  jmp     short loc_18003DC97
0x18003dc4e  mov     ecx, 1F4h; dwMilliseconds
0x18003dc53  call    cs:__imp_Sleep
0x18003dc5a  nop     dword ptr [rax+rax+00h]
0x18003dc5f  nop
0x18003dc60  mov     eax, [rsp+38h+arg_10]
0x18003dc64  inc     eax
0x18003dc66  mov     rdi, [rsp+38h+arg_0]
0x18003dc6b  mov     ecx, [rsp+38h+arg_18]
0x18003dc6f  jmp     loc_18003DBB5
0x18003dc74  test    r9d, r9d
0x18003dc77  jz      short loc_18003DC91
0x18003dc79  mov     rcx, [rsp+38h]; this
0x18003dc7e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003dc85  mov     edx, 101h; void *
0x18003dc8a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003dc8f  jmp     short loc_18003DC97
0x18003dc91  xor     eax, eax
0x18003dc93  jmp     short loc_18003DC97
0x18003dc95  xor     eax, eax
0x18003dc97  add     rsp, 28h
0x18003dc9b  pop     rdi
0x18003dc9c  pop     rbx
0x18003dc9d  retn
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
