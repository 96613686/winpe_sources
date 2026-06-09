# BfeSessionCreate

- ea: `0x18004cce8`
- end: `0x18004d061`
- name: `BfeSessionCreate`
- size: `889`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE ClientBinding@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x18000dc10`

## callees

- `0x1800040d0`
- `0x18000e7e0`
- `0x180012d8c`
- `0x180012e20`
- `0x1800197d0`
- `0x180023280`
- `0x180024e40`
- `0x180025d94`
- `0x180029174`
- `0x18003592c`
- `0x180035d80`
- `0x18003798c`
- `0x1800385a0`
- `0x18003870c`
- `0x180038a20`
- `0x180038fc8`
- `0x180039b94`
- `0x18004cce8`
- `0x18004d068`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d00e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d00e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d04c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d04c`
- `RPCRT4!UuidCreate` at `0x18004cdfa`
- `RPCRT4!UuidCreate` at `0x18004cdfa`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004ce3d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004ce3d`

## string_xrefs

- `0x18004ce0a`: `UuidCreate`
- `0x18004ce26`: `BfeSessionCreate`
- `0x18004ce9f`: `BfeSessionCreate`

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
  __int64 v21; // rdx
  __int64 *v22; // rax
  __int64 v23; // [rsp+20h] [rbp-A1h] BYREF
  PSID *v24; // [rsp+28h] [rbp-99h] BYREF
  __int64 v25; // [rsp+30h] [rbp-91h] BYREF
  __int64 v26; // [rsp+38h] [rbp-89h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext[2]; // [rsp+40h] [rbp-81h] BYREF
  int RpcCallAttributes; // [rsp+50h] [rbp-71h] BYREF
  _DWORD v29[27]; // [rsp+54h] [rbp-6Dh] BYREF

  hAuthzClientContext[0] = 0;
  v23 = 0;
  RpcCallAttributes = 2;
  memset_0(v29, 0, sizeof(v29));
  *a4 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
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
  v11 = v23;
  *(_QWORD *)(v23 + 16) = *a2;
  v12 = qword_1800F2198;
  *a2 = 0;
  *(_QWORD *)(v11 + 80) = ++v12;
  *(_QWORD *)(v11 + 8) = v11;
  *(_QWORD *)v11 = v11;
  qword_1800F2198 = v12;
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
  v29[0] = 16;
  v14 = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  if ( v14 )
  {
    v16 = "RpcServerInqCallAttributesW";
    goto LABEL_12;
  }
  *(_DWORD *)(*(_QWORD *)(v11 + 16) + 40LL) = v29[15];
  *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v11 + 48) = hAuthzClientContext[0];
  hAuthzClientContext[0] = 0;
  AuthzContextFromClientBinding = BfeAuthzContextGetInfo(*(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v11 + 48));
  if ( AuthzContextFromClientBinding )
    goto LABEL_14;
  WfpMemFree(*(_QWORD *)(v11 + 16) + 48LL);
  v19 = v24;
  *(_QWORD *)(*(_QWORD *)(v11 + 16) + 48LL) = 0;
  AuthzContextFromClientBinding = BfeSidCopy(*v19, (_QWORD *)(*(_QWORD *)(v11 + 16) + 48LL));
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
  *(_DWORD *)(*(_QWORD *)(v11 + 16) + 64LL) = v29[12];
  v20 = *(_QWORD *)(v11 + 16);
  if ( !*(_DWORD *)(v20 + 36) )
    *(_DWORD *)(v20 + 36) = 6000000;
  AuthzContextFromClientBinding = BfeRpcGetAccessTokenFromClientBinding(ClientBinding, (void **)(v11 + 40));
  if ( AuthzContextFromClientBinding
    || (AuthzContextFromClientBinding = BfeNotifySinkCreate(*v19, v21, (_QWORD *)(v11 + 56))) != 0
    || (AuthzContextFromClientBinding = WfpStringCopy((void *)(*(_QWORD *)(v11 + 56) + 88LL))) != 0 )
  {
LABEL_14:
    BfeSessionDestroy(v9, &v23);
    goto LABEL_15;
  }
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x100) == 0 && (unsigned int)BfeSessionInProc(v11) )
    *(_DWORD *)(v11 + 88) = 1;
  EnterCriticalSection(&stru_1800EE408);
  v22 = (__int64 *)qword_1800EE440;
  if ( *(__int64 **)qword_1800EE440 != &qword_1800EE438 )
    __fastfail(3u);
  *(_QWORD *)v11 = &qword_1800EE438;
  *(_QWORD *)(v11 + 8) = v22;
  *v22 = v11;
  qword_1800EE440 = v11;
  LeaveCriticalSection(&stru_1800EE408);
  *a5 = v11;
LABEL_15:
  WfpMemFree(&v25);
  WfpMemFree(&v26);
  WfpMemFree(&v24);
  BfeRpcFreeAuthzContext(hAuthzClientContext);
  if ( AuthzContextFromClientBinding )
    WfpReportError(AuthzContextFromClientBinding, "BfeSessionCreate");
  return AuthzContextFromClientBinding;
}

```

## disassembly

```asm
0x18004cce8  push    rbp
0x18004ccea  push    rbx
0x18004cceb  push    rsi
0x18004ccec  push    rdi
0x18004cced  push    r12
0x18004ccef  push    r13
0x18004ccf1  push    r14
0x18004ccf3  push    r15
0x18004ccf5  lea     rbp, [rsp-17h]
0x18004ccfa  sub     rsp, 0D8h
0x18004cd01  mov     rax, cs:__security_cookie
0x18004cd08  xor     rax, rsp
0x18004cd0b  mov     [rbp+4Fh+var_50], rax
0x18004cd0f  mov     r13, [rbp+4Fh+arg_20]
0x18004cd13  xor     edi, edi
0x18004cd15  mov     r14, r8
0x18004cd18  mov     [rsp+110h+hAuthzClientContext], rdi
0x18004cd1d  mov     rsi, rdx
0x18004cd20  mov     [rsp+110h+var_F0], rdi
0x18004cd25  mov     r15, rcx
0x18004cd28  mov     [rbp+4Fh+RpcCallAttributes], 2
0x18004cd2f  lea     r8d, [rdi+6Ch]; Size
0x18004cd33  xor     edx, edx; Val
0x18004cd35  lea     rcx, [rbp+4Fh+var_BC]; void *
0x18004cd39  mov     r12, r9
0x18004cd3c  call    memset_0
0x18004cd41  mov     [r12], rdi
0x18004cd45  lea     rdx, [rsp+110h+hAuthzClientContext]
0x18004cd4a  mov     rcx, r15
0x18004cd4d  mov     [rsp+110h+var_E8], rdi
0x18004cd52  mov     [rsp+110h+var_D8], rdi
0x18004cd57  mov     [rsp+110h+var_E0], rdi
0x18004cd5c  mov     [r13+0], rdi
0x18004cd60  call    BfeRpcGetAuthzContextFromClientBinding
0x18004cd65  mov     rbx, rax
0x18004cd68  test    rax, rax
0x18004cd6b  jnz     loc_18004CE68
0x18004cd71  mov     rcx, [rsp+110h+hAuthzClientContext]; hAuthzClientContext
0x18004cd76  call    BfeEngineOpenAccessCheckFromContext
0x18004cd7b  mov     rbx, rax
0x18004cd7e  test    rax, rax
0x18004cd81  jnz     loc_18004CE68
0x18004cd87  lea     r8, [rsp+110h+var_F0]
0x18004cd8c  lea     edx, [rdi+8]; dwFlags
0x18004cd8f  lea     ecx, [rdi+60h]; dwBytes
0x18004cd92  call    WfpMemAlloc
0x18004cd97  mov     rbx, rax
0x18004cd9a  test    rax, rax
0x18004cd9d  jnz     loc_18004CE68
0x18004cda3  mov     rax, [rsi]
0x18004cda6  mov     rcx, r14
0x18004cda9  mov     rdi, [rsp+110h+var_F0]
0x18004cdae  mov     [rdi+10h], rax
0x18004cdb2  lea     rdx, [rdi+18h]
0x18004cdb6  mov     rax, cs:qword_1800F2198
0x18004cdbd  mov     [rsi], rbx
0x18004cdc0  inc     rax
0x18004cdc3  mov     [rdi+50h], rax
0x18004cdc7  mov     [rdi+8], rdi
0x18004cdcb  mov     [rdi], rdi
0x18004cdce  mov     cs:qword_1800F2198, rax
0x18004cdd5  lea     rax, [rdi+40h]
0x18004cdd9  mov     [rax+8], rax
0x18004cddd  mov     [rax], rax
0x18004cde0  call    BfeFwpmLangInfoCopy
0x18004cde5  mov     rbx, rax
0x18004cde8  test    rax, rax
0x18004cdeb  jnz     short loc_18004CE68
0x18004cded  mov     rcx, [rdi+10h]
0x18004cdf1  call    BfeGuidIsNull
0x18004cdf6  test    eax, eax
0x18004cdf8  jz      short loc_18004CE13
0x18004cdfa  call    cs:__imp_UuidCreate
0x18004ce01  nop     dword ptr [rax+rax+00h]
0x18004ce06  test    eax, eax
0x18004ce08  jz      short loc_18004CE13
0x18004ce0a  lea     rdx, aUuidcreate; "UuidCreate"
0x18004ce11  jmp     short loc_18004CE58
0x18004ce13  mov     rcx, [rdi+10h]
0x18004ce17  call    BfeSessionIsKeyInUse
0x18004ce1c  test    eax, eax
0x18004ce1e  jz      short loc_18004CE2F
0x18004ce20  mov     r8d, 80320009h
0x18004ce26  lea     rdx, aBfesessioncrea; "BfeSessionCreate"
0x18004ce2d  jmp     short loc_18004CE5B
0x18004ce2f  lea     rdx, [rbp+4Fh+RpcCallAttributes]; RpcCallAttributes
0x18004ce33  mov     [rbp+4Fh+var_BC], 10h
0x18004ce3a  mov     rcx, r15; ClientBinding
0x18004ce3d  call    cs:__imp_RpcServerInqCallAttributesW
0x18004ce44  nop     dword ptr [rax+rax+00h]
0x18004ce49  test    eax, eax
0x18004ce4b  jz      loc_18004CED2
0x18004ce51  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributesW"
0x18004ce58  mov     r8d, eax
0x18004ce5b  call    WfpReportSysErrorAsWinError
0x18004ce60  mov     rbx, rax
0x18004ce63  test    rax, rax
0x18004ce66  jz      short loc_18004CE72
0x18004ce68  lea     rdx, [rsp+110h+var_F0]
0x18004ce6d  call    BfeSessionDestroy
0x18004ce72  lea     rcx, [rsp+110h+var_E0]
0x18004ce77  call    WfpMemFree
0x18004ce7c  lea     rcx, [rsp+110h+var_D8]
0x18004ce81  call    WfpMemFree
0x18004ce86  lea     rcx, [rsp+110h+var_E8]
0x18004ce8b  call    WfpMemFree
0x18004ce90  lea     rcx, [rsp+110h+hAuthzClientContext]
0x18004ce95  call    BfeRpcFreeAuthzContext
0x18004ce9a  test    rbx, rbx
0x18004ce9d  jz      short loc_18004CEAE
0x18004ce9f  lea     rdx, aBfesessioncrea; "BfeSessionCreate"
0x18004cea6  mov     rcx, rbx
0x18004cea9  call    WfpReportError
0x18004ceae  mov     rax, rbx
0x18004ceb1  mov     rcx, [rbp+4Fh+var_50]
0x18004ceb5  xor     rcx, rsp; StackCookie
0x18004ceb8  call    __security_check_cookie
0x18004cebd  add     rsp, 0D8h
0x18004cec4  pop     r15
0x18004cec6  pop     r14
0x18004cec8  pop     r13
0x18004ceca  pop     r12
0x18004cecc  pop     rdi
0x18004cecd  pop     rsi
0x18004cece  pop     rbx
0x18004cecf  pop     rbp
0x18004ced0  retn
0x18004ced2  mov     rcx, [rdi+10h]
0x18004ced6  lea     r8, [rsp+110h+var_E8]
0x18004cedb  mov     eax, [rbp+4Fh+var_80]
0x18004cede  mov     [rcx+28h], eax
0x18004cee1  mov     rax, [rsp+110h+hAuthzClientContext]
0x18004cee6  mov     [rdi+30h], rax
0x18004ceea  mov     [rsp+110h+hAuthzClientContext], 0
0x18004cef3  mov     rcx, [rdi+30h]; hAuthzClientContext
0x18004cef7  call    BfeAuthzContextGetInfo
0x18004cefc  mov     rbx, rax
0x18004ceff  test    rax, rax
0x18004cf02  jnz     loc_18004CE68
0x18004cf08  mov     rcx, [rdi+10h]
0x18004cf0c  add     rcx, 30h ; '0'
0x18004cf10  call    WfpMemFree
0x18004cf15  mov     rax, [rdi+10h]
0x18004cf19  mov     r14, [rsp+110h+var_E8]
0x18004cf1e  mov     [rax+30h], rbx
0x18004cf22  mov     rdx, [rdi+10h]
0x18004cf26  mov     rcx, [r14]; pSourceSid
0x18004cf29  add     rdx, 30h ; '0'
0x18004cf2d  call    BfeSidCopy
0x18004cf32  mov     rbx, rax
0x18004cf35  test    rax, rax
0x18004cf38  jnz     loc_18004CE68
0x18004cf3e  mov     rcx, [rdi+10h]
0x18004cf42  add     rcx, 38h ; '8'
0x18004cf46  call    WfpMemFree
0x18004cf4b  mov     rax, [rdi+10h]
0x18004cf4f  mov     [rax+38h], rbx
0x18004cf53  mov     rdx, [rdi+10h]
0x18004cf57  test    dword ptr [rdx+20h], 10000000h
0x18004cf5e  jnz     short loc_18004CF78
0x18004cf60  mov     rcx, [r14]; pSid1
0x18004cf63  add     rdx, 38h ; '8'
0x18004cf67  call    BfeLookupAccountSidWithCache
0x18004cf6c  mov     rbx, rax
0x18004cf6f  test    rax, rax
0x18004cf72  jnz     loc_18004CE68
0x18004cf78  mov     eax, [rbp+4Fh+var_8C]
0x18004cf7b  mov     rdx, [rdi+10h]
0x18004cf7f  mov     [rdx+40h], eax
0x18004cf82  mov     rax, [rdi+10h]
0x18004cf86  cmp     dword ptr [rax+24h], 0
0x18004cf8a  jnz     short loc_18004CF93
0x18004cf8c  mov     dword ptr [rax+24h], 5B8D80h
0x18004cf93  lea     rdx, [rdi+28h]
0x18004cf97  mov     rcx, r15
0x18004cf9a  call    BfeRpcGetAccessTokenFromClientBinding
0x18004cf9f  mov     rbx, rax
0x18004cfa2  test    rax, rax
0x18004cfa5  jnz     loc_18004CE68
0x18004cfab  mov     rcx, [r14]; pSid
0x18004cfae  lea     r8, [rdi+38h]
0x18004cfb2  call    BfeNotifySinkCreate
0x18004cfb7  mov     rbx, rax
0x18004cfba  test    rax, rax
0x18004cfbd  jnz     loc_18004CE68
0x18004cfc3  mov     rcx, [rdi+38h]
0x18004cfc7  mov     r8, r12
0x18004cfca  add     rcx, 58h ; 'X'; Src
0x18004cfce  call    WfpStringCopy
0x18004cfd3  mov     rbx, rax
0x18004cfd6  test    rax, rax
0x18004cfd9  jnz     loc_18004CE68
0x18004cfdf  mov     rax, gs:60h
0x18004cfe8  test    dword ptr [rax+0BCh], 100h
0x18004cff2  jnz     short loc_18004D007
0x18004cff4  mov     rcx, rdi
0x18004cff7  call    BfeSessionInProc
0x18004cffc  test    eax, eax
0x18004cffe  jz      short loc_18004D007
0x18004d000  mov     dword ptr [rdi+58h], 1
0x18004d007  lea     rcx, stru_1800EE408; lpCriticalSection
0x18004d00e  call    cs:__imp_EnterCriticalSection
0x18004d015  nop     dword ptr [rax+rax+00h]
0x18004d01a  mov     rax, cs:qword_1800EE440
0x18004d021  lea     rcx, qword_1800EE438
0x18004d028  cmp     [rax], rcx
0x18004d02b  jz      short loc_18004D034
0x18004d02d  mov     ecx, 3
0x18004d032  int     29h; Win8: RtlFailFast(ecx)
0x18004d034  mov     [rdi], rcx
0x18004d037  lea     rcx, stru_1800EE408; lpCriticalSection
0x18004d03e  mov     [rdi+8], rax
0x18004d042  mov     [rax], rdi
0x18004d045  mov     cs:qword_1800EE440, rdi
0x18004d04c  call    cs:__imp_LeaveCriticalSection
0x18004d053  nop     dword ptr [rax+rax+00h]
0x18004d058  mov     [r13+0], rdi
0x18004d05c  jmp     loc_18004CE72
```
