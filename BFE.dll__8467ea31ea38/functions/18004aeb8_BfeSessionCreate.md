# BfeSessionCreate

- ea: `0x18004aeb8`
- end: `0x18004b218`
- name: `BfeSessionCreate`
- size: `864`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, _QWORD *, __int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x18000d4d0`

## callees

- `0x1800040f0`
- `0x18000e000`
- `0x18001236c`
- `0x180012400`
- `0x180018b74`
- `0x180020c30`
- `0x180022730`
- `0x180023680`
- `0x180036bd4`
- `0x180037690`
- `0x180038c24`
- `0x1800399fc`
- `0x180039b70`
- `0x180039e30`
- `0x18003a434`
- `0x18003a8c8`
- `0x18003b4a0`
- `0x18004aeb8`
- `0x18004b220`
- `0x180058b30`
- `0x1800595ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b209`
- `RPCRT4!UuidCreate` at `0x18004afca`
- `RPCRT4!UuidCreate` at `0x18004afca`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004b007`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004b007`

## string_xrefs

- `0x18004afd4`: `UuidCreate`
- `0x18004aff0`: `BfeSessionCreate`
- `0x18004b063`: `BfeSessionCreate`

## pseudocode

```c
__int64 __fastcall BfeSessionCreate(RPC_BINDING_HANDLE ClientBinding, _QWORD *a2, __int64 a3, _QWORD *a4, __int64 *a5)
{
  __int64 v9; // rcx
  __int64 AuthzContextFromClientBinding; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  UUID *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  const char *v16; // rdx
  __int64 v17; // r8
  PSID *v19; // r14
  __int64 v20; // rax
  __int64 *v21; // rax
  __int64 v22; // [rsp+20h] [rbp-A1h] BYREF
  PSID *v23; // [rsp+28h] [rbp-99h] BYREF
  __int64 v24; // [rsp+30h] [rbp-91h] BYREF
  __int64 v25; // [rsp+38h] [rbp-89h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext[2]; // [rsp+40h] [rbp-81h] BYREF
  int RpcCallAttributes; // [rsp+50h] [rbp-71h] BYREF
  _DWORD v28[27]; // [rsp+54h] [rbp-6Dh] BYREF

  hAuthzClientContext[0] = 0;
  v22 = 0;
  RpcCallAttributes = 2;
  memset_0(v28, 0, sizeof(v28));
  *a4 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  *a5 = 0;
  AuthzContextFromClientBinding = BfeRpcGetAuthzContextFromClientBinding(ClientBinding, hAuthzClientContext);
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  AuthzContextFromClientBinding = BfeEngineOpenAccessCheckFromContext(hAuthzClientContext[0]);
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  AuthzContextFromClientBinding = WfpMemAlloc(0x60u, 8u);
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  v11 = v22;
  *(_QWORD *)(v22 + 16) = *a2;
  v12 = qword_1800EF088;
  *a2 = 0;
  *(_QWORD *)(v11 + 80) = ++v12;
  *(_QWORD *)(v11 + 8) = v11;
  *(_QWORD *)v11 = v11;
  qword_1800EF088 = v12;
  *(_QWORD *)(v11 + 72) = v11 + 64;
  *(_QWORD *)(v11 + 64) = v11 + 64;
  AuthzContextFromClientBinding = BfeFwpmLangInfoCopy(a3, v11 + 24);
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  if ( (unsigned int)BfeGuidIsNull(*(_QWORD *)(v11 + 16)) )
  {
    v14 = UuidCreate(v13);
    if ( v14 )
    {
      v16 = "UuidCreate";
LABEL_12:
      v17 = v14;
LABEL_13:
      AuthzContextFromClientBinding = WfpReportSysErrorAsWinError(v15, v16, v17);
      if ( !AuthzContextFromClientBinding )
        goto LABEL_15;
      goto LABEL_14;
    }
  }
  if ( (unsigned int)BfeSessionIsKeyInUse(*(_QWORD *)(v11 + 16)) )
  {
    v17 = 2150760457LL;
    v16 = "BfeSessionCreate";
    goto LABEL_13;
  }
  v28[0] = 16;
  v14 = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  if ( v14 )
  {
    v16 = "RpcServerInqCallAttributesW";
    goto LABEL_12;
  }
  *(_DWORD *)(*(_QWORD *)(v11 + 16) + 40LL) = v28[15];
  *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v11 + 48) = hAuthzClientContext[0];
  hAuthzClientContext[0] = 0;
  AuthzContextFromClientBinding = BfeAuthzContextGetInfo(*(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v11 + 48));
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  WfpMemFree(*(_QWORD *)(v11 + 16) + 48LL);
  v19 = v23;
  *(_QWORD *)(*(_QWORD *)(v11 + 16) + 48LL) = 0;
  AuthzContextFromClientBinding = BfeSidCopy(*v19);
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  WfpMemFree(*(_QWORD *)(v11 + 16) + 56LL);
  *(_QWORD *)(*(_QWORD *)(v11 + 16) + 56LL) = 0;
  if ( (*(_DWORD *)(*(_QWORD *)(v11 + 16) + 32LL) & 0x10000000) == 0 )
  {
    AuthzContextFromClientBinding = BfeLookupAccountSidWithCache(*v19);
    if ( AuthzContextFromClientBinding )
      goto LABEL_14;
  }
  *(_DWORD *)(*(_QWORD *)(v11 + 16) + 64LL) = v28[12];
  v20 = *(_QWORD *)(v11 + 16);
  if ( !*(_DWORD *)(v20 + 36) )
    *(_DWORD *)(v20 + 36) = 6000000;
  AuthzContextFromClientBinding = BfeRpcGetAccessTokenFromClientBinding(ClientBinding, v11 + 40);
  if ( AuthzContextFromClientBinding
    || (AuthzContextFromClientBinding = BfeNotifySinkCreate(*v19)) != 0
    || (AuthzContextFromClientBinding = WfpStringCopy((void *)(*(_QWORD *)(v11 + 56) + 88LL))) != 0 )
  {
LABEL_14:
    BfeSessionDestroy(v9, &v22);
    goto LABEL_15;
  }
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x100) == 0 && (unsigned int)BfeSessionInProc(v11) )
    *(_DWORD *)(v11 + 88) = 1;
  EnterCriticalSection(&stru_1800EB308);
  v21 = (__int64 *)qword_1800EB340;
  if ( *(__int64 **)qword_1800EB340 != &qword_1800EB338 )
    __fastfail(3u);
  *(_QWORD *)v11 = &qword_1800EB338;
  *(_QWORD *)(v11 + 8) = v21;
  *v21 = v11;
  qword_1800EB340 = v11;
  LeaveCriticalSection(&stru_1800EB308);
  *a5 = v11;
LABEL_15:
  WfpMemFree(&v24);
  WfpMemFree(&v25);
  WfpMemFree(&v23);
  BfeRpcFreeAuthzContext(hAuthzClientContext);
  if ( AuthzContextFromClientBinding )
    WfpReportError(AuthzContextFromClientBinding, "BfeSessionCreate");
  return AuthzContextFromClientBinding;
}

```

## disassembly

```asm
0x18004aeb8  push    rbp
0x18004aeba  push    rbx
0x18004aebb  push    rsi
0x18004aebc  push    rdi
0x18004aebd  push    r12
0x18004aebf  push    r13
0x18004aec1  push    r14
0x18004aec3  push    r15
0x18004aec5  lea     rbp, [rsp-17h]
0x18004aeca  sub     rsp, 0D8h
0x18004aed1  mov     rax, cs:__security_cookie
0x18004aed8  xor     rax, rsp
0x18004aedb  mov     [rbp+4Fh+var_50], rax
0x18004aedf  mov     r13, [rbp+4Fh+arg_20]
0x18004aee3  xor     edi, edi
0x18004aee5  mov     r14, r8
0x18004aee8  mov     [rsp+110h+hAuthzClientContext], rdi
0x18004aeed  mov     rsi, rdx
0x18004aef0  mov     [rsp+110h+var_F0], rdi
0x18004aef5  mov     r15, rcx
0x18004aef8  mov     [rbp+4Fh+RpcCallAttributes], 2
0x18004aeff  lea     r8d, [rdi+6Ch]; Size
0x18004af03  xor     edx, edx; Val
0x18004af05  lea     rcx, [rbp+4Fh+var_BC]; void *
0x18004af09  mov     r12, r9
0x18004af0c  call    memset_0
0x18004af11  mov     [r12], rdi
0x18004af15  lea     rdx, [rsp+110h+hAuthzClientContext]
0x18004af1a  mov     rcx, r15
0x18004af1d  mov     [rsp+110h+var_E8], rdi
0x18004af22  mov     [rsp+110h+var_D8], rdi
0x18004af27  mov     [rsp+110h+var_E0], rdi
0x18004af2c  mov     [r13+0], rdi
0x18004af30  call    BfeRpcGetAuthzContextFromClientBinding
0x18004af35  mov     rbx, rax
0x18004af38  test    rax, rax
0x18004af3b  jnz     loc_18004B02C
0x18004af41  mov     rcx, [rsp+110h+hAuthzClientContext]; hAuthzClientContext
0x18004af46  call    BfeEngineOpenAccessCheckFromContext
0x18004af4b  mov     rbx, rax
0x18004af4e  test    rax, rax
0x18004af51  jnz     loc_18004B02C
0x18004af57  lea     r8, [rsp+110h+var_F0]
0x18004af5c  lea     edx, [rdi+8]; dwFlags
0x18004af5f  lea     ecx, [rdi+60h]; dwBytes
0x18004af62  call    WfpMemAlloc
0x18004af67  mov     rbx, rax
0x18004af6a  test    rax, rax
0x18004af6d  jnz     loc_18004B02C
0x18004af73  mov     rax, [rsi]
0x18004af76  mov     rcx, r14
0x18004af79  mov     rdi, [rsp+110h+var_F0]
0x18004af7e  mov     [rdi+10h], rax
0x18004af82  lea     rdx, [rdi+18h]
0x18004af86  mov     rax, cs:qword_1800EF088
0x18004af8d  mov     [rsi], rbx
0x18004af90  inc     rax
0x18004af93  mov     [rdi+50h], rax
0x18004af97  mov     [rdi+8], rdi
0x18004af9b  mov     [rdi], rdi
0x18004af9e  mov     cs:qword_1800EF088, rax
0x18004afa5  lea     rax, [rdi+40h]
0x18004afa9  mov     [rax+8], rax
0x18004afad  mov     [rax], rax
0x18004afb0  call    BfeFwpmLangInfoCopy
0x18004afb5  mov     rbx, rax
0x18004afb8  test    rax, rax
0x18004afbb  jnz     short loc_18004B02C
0x18004afbd  mov     rcx, [rdi+10h]
0x18004afc1  call    BfeGuidIsNull
0x18004afc6  test    eax, eax
0x18004afc8  jz      short loc_18004AFDD
0x18004afca  call    cs:__imp_UuidCreate
0x18004afd0  test    eax, eax
0x18004afd2  jz      short loc_18004AFDD
0x18004afd4  lea     rdx, aUuidcreate; "UuidCreate"
0x18004afdb  jmp     short loc_18004B01C
0x18004afdd  mov     rcx, [rdi+10h]
0x18004afe1  call    BfeSessionIsKeyInUse
0x18004afe6  test    eax, eax
0x18004afe8  jz      short loc_18004AFF9
0x18004afea  mov     r8d, 80320009h
0x18004aff0  lea     rdx, aBfesessioncrea; "BfeSessionCreate"
0x18004aff7  jmp     short loc_18004B01F
0x18004aff9  lea     rdx, [rbp+4Fh+RpcCallAttributes]; RpcCallAttributes
0x18004affd  mov     [rbp+4Fh+var_BC], 10h
0x18004b004  mov     rcx, r15; ClientBinding
0x18004b007  call    cs:__imp_RpcServerInqCallAttributesW
0x18004b00d  test    eax, eax
0x18004b00f  jz      loc_18004B095
0x18004b015  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributesW"
0x18004b01c  mov     r8d, eax
0x18004b01f  call    WfpReportSysErrorAsWinError
0x18004b024  mov     rbx, rax
0x18004b027  test    rax, rax
0x18004b02a  jz      short loc_18004B036
0x18004b02c  lea     rdx, [rsp+110h+var_F0]
0x18004b031  call    BfeSessionDestroy
0x18004b036  lea     rcx, [rsp+110h+var_E0]
0x18004b03b  call    WfpMemFree
0x18004b040  lea     rcx, [rsp+110h+var_D8]
0x18004b045  call    WfpMemFree
0x18004b04a  lea     rcx, [rsp+110h+var_E8]
0x18004b04f  call    WfpMemFree
0x18004b054  lea     rcx, [rsp+110h+hAuthzClientContext]
0x18004b059  call    BfeRpcFreeAuthzContext
0x18004b05e  test    rbx, rbx
0x18004b061  jz      short loc_18004B072
0x18004b063  lea     rdx, aBfesessioncrea; "BfeSessionCreate"
0x18004b06a  mov     rcx, rbx
0x18004b06d  call    WfpReportError
0x18004b072  mov     rax, rbx
0x18004b075  mov     rcx, [rbp+4Fh+var_50]
0x18004b079  xor     rcx, rsp; StackCookie
0x18004b07c  call    __security_check_cookie
0x18004b081  add     rsp, 0D8h
0x18004b088  pop     r15
0x18004b08a  pop     r14
0x18004b08c  pop     r13
0x18004b08e  pop     r12
0x18004b090  pop     rdi
0x18004b091  pop     rsi
0x18004b092  pop     rbx
0x18004b093  pop     rbp
0x18004b094  retn
0x18004b095  mov     rcx, [rdi+10h]
0x18004b099  lea     r8, [rsp+110h+var_E8]
0x18004b09e  mov     eax, [rbp+4Fh+var_80]
0x18004b0a1  mov     [rcx+28h], eax
0x18004b0a4  mov     rax, [rsp+110h+hAuthzClientContext]
0x18004b0a9  mov     [rdi+30h], rax
0x18004b0ad  mov     [rsp+110h+hAuthzClientContext], 0
0x18004b0b6  mov     rcx, [rdi+30h]; hAuthzClientContext
0x18004b0ba  call    BfeAuthzContextGetInfo
0x18004b0bf  mov     rbx, rax
0x18004b0c2  test    rax, rax
0x18004b0c5  jnz     loc_18004B02C
0x18004b0cb  mov     rcx, [rdi+10h]
0x18004b0cf  add     rcx, 30h ; '0'
0x18004b0d3  call    WfpMemFree
0x18004b0d8  mov     rax, [rdi+10h]
0x18004b0dc  mov     r14, [rsp+110h+var_E8]
0x18004b0e1  mov     [rax+30h], rbx
0x18004b0e5  mov     rdx, [rdi+10h]
0x18004b0e9  mov     rcx, [r14]; pSourceSid
0x18004b0ec  add     rdx, 30h ; '0'
0x18004b0f0  call    BfeSidCopy
0x18004b0f5  mov     rbx, rax
0x18004b0f8  test    rax, rax
0x18004b0fb  jnz     loc_18004B02C
0x18004b101  mov     rcx, [rdi+10h]
0x18004b105  add     rcx, 38h ; '8'
0x18004b109  call    WfpMemFree
0x18004b10e  mov     rax, [rdi+10h]
0x18004b112  mov     [rax+38h], rbx
0x18004b116  mov     rdx, [rdi+10h]
0x18004b11a  test    dword ptr [rdx+20h], 10000000h
0x18004b121  jnz     short loc_18004B13B
0x18004b123  mov     rcx, [r14]; pSid1
0x18004b126  add     rdx, 38h ; '8'
0x18004b12a  call    BfeLookupAccountSidWithCache
0x18004b12f  mov     rbx, rax
0x18004b132  test    rax, rax
0x18004b135  jnz     loc_18004B02C
0x18004b13b  mov     eax, [rbp+4Fh+var_8C]
0x18004b13e  mov     rdx, [rdi+10h]
0x18004b142  mov     [rdx+40h], eax
0x18004b145  mov     rax, [rdi+10h]
0x18004b149  cmp     dword ptr [rax+24h], 0
0x18004b14d  jnz     short loc_18004B156
0x18004b14f  mov     dword ptr [rax+24h], 5B8D80h
0x18004b156  lea     rdx, [rdi+28h]
0x18004b15a  mov     rcx, r15
0x18004b15d  call    BfeRpcGetAccessTokenFromClientBinding
0x18004b162  mov     rbx, rax
0x18004b165  test    rax, rax
0x18004b168  jnz     loc_18004B02C
0x18004b16e  mov     rcx, [r14]; pSid
0x18004b171  lea     r8, [rdi+38h]
0x18004b175  call    BfeNotifySinkCreate
0x18004b17a  mov     rbx, rax
0x18004b17d  test    rax, rax
0x18004b180  jnz     loc_18004B02C
0x18004b186  mov     rcx, [rdi+38h]
0x18004b18a  mov     r8, r12
0x18004b18d  add     rcx, 58h ; 'X'; Src
0x18004b191  call    WfpStringCopy
0x18004b196  mov     rbx, rax
0x18004b199  test    rax, rax
0x18004b19c  jnz     loc_18004B02C
0x18004b1a2  mov     rax, gs:60h
0x18004b1ab  test    dword ptr [rax+0BCh], 100h
0x18004b1b5  jnz     short loc_18004B1CA
0x18004b1b7  mov     rcx, rdi
0x18004b1ba  call    BfeSessionInProc
0x18004b1bf  test    eax, eax
0x18004b1c1  jz      short loc_18004B1CA
0x18004b1c3  mov     dword ptr [rdi+58h], 1
0x18004b1ca  lea     rcx, stru_1800EB308; lpCriticalSection
0x18004b1d1  call    cs:__imp_EnterCriticalSection
0x18004b1d7  mov     rax, cs:qword_1800EB340
0x18004b1de  lea     rcx, qword_1800EB338
0x18004b1e5  cmp     [rax], rcx
0x18004b1e8  jz      short loc_18004B1F1
0x18004b1ea  mov     ecx, 3
0x18004b1ef  int     29h; Win8: RtlFailFast(ecx)
0x18004b1f1  mov     [rdi], rcx
0x18004b1f4  lea     rcx, stru_1800EB308; lpCriticalSection
0x18004b1fb  mov     [rdi+8], rax
0x18004b1ff  mov     [rax], rdi
0x18004b202  mov     cs:qword_1800EB340, rdi
0x18004b209  call    cs:__imp_LeaveCriticalSection
0x18004b20f  mov     [r13+0], rdi
0x18004b213  jmp     loc_18004B036
```
