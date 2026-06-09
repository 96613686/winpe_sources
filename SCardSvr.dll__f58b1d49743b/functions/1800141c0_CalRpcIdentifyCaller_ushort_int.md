# CalRpcIdentifyCaller(ushort * *,int *)

- ea: `0x1800141c0`
- end: `0x1800143a1`
- name: `?CalRpcIdentifyCaller@@YAKPEAPEAGPEAH@Z`
- size: `481`
- prototype: `__int64 __fastcall(LPWSTR *StringSid, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019640`

## callees

- `0x1800141c0`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001425c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001425c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001424e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001424e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001437e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001437e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014360`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014360`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001434e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001434e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014243`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014243`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014370`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014370`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18001426e`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18001426e`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x18001422d`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x18001422d`
- `AUTHZ!AuthzGetInformationFromContext` at `0x1800142b5`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180014312`
- `AUTHZ!AuthzGetInformationFromContext` at `0x1800142b5`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180014312`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CalRpcIdentifyCaller(LPWSTR *StringSid, int *a2)
{
  PSID *v4; // rbx
  DWORD AuthorizationContextForClient; // edi
  HANDLE v6; // rax
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v10; // rax
  DWORD pSizeRequired; // [rsp+60h] [rbp-48h] BYREF
  PVOID pAuthzClientContext; // [rsp+68h] [rbp-40h] BYREF
  PSID pSid; // [rsp+70h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-30h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a2 = 0;
  *StringSid = 0;
  pSid = 0;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSizeRequired = 0;
  pAuthzClientContext = 0;
  AuthorizationContextForClient = RpcGetAuthorizationContextForClient(0, 0, 0, 0, 0, 0, 0, &pAuthzClientContext);
  if ( !AuthorizationContextForClient )
  {
    if ( !AuthzGetInformationFromContext(
            (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
            AuthzContextInfoUserSid,
            0,
            &pSizeRequired,
            0) )
    {
      AuthorizationContextForClient = GetLastError();
      if ( AuthorizationContextForClient != 122 )
        goto LABEL_2;
      AuthorizationContextForClient = 0;
    }
    v8 = pSizeRequired;
    ProcessHeap = GetProcessHeap();
    v10 = (PSID *)HeapAlloc(ProcessHeap, 8u, v8);
    v4 = v10;
    if ( v10 )
    {
      if ( AuthzGetInformationFromContext(
             (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
             AuthzContextInfoUserSid,
             pSizeRequired,
             &pSizeRequired,
             v10)
        && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        if ( EqualSid(pSid, *v4) )
        {
          *a2 = 1;
          goto LABEL_2;
        }
        if ( ConvertSidToStringSidW(*v4, StringSid) )
          goto LABEL_2;
      }
      AuthorizationContextForClient = GetLastError();
      goto LABEL_2;
    }
    AuthorizationContextForClient = -2146435066;
  }
LABEL_2:
  if ( pSid )
    FreeSid(pSid);
  if ( v4 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v4);
  }
  if ( pAuthzClientContext )
    RpcFreeAuthorizationContext(&pAuthzClientContext);
  return AuthorizationContextForClient;
}

```

## disassembly

```asm
0x1800141c0  mov     r11, rsp
0x1800141c3  mov     [r11+18h], rbx
0x1800141c7  mov     [r11+20h], rbp
0x1800141cb  push    rsi
0x1800141cc  push    rdi
0x1800141cd  push    r14
0x1800141cf  sub     rsp, 90h
0x1800141d6  mov     rax, cs:__security_cookie
0x1800141dd  xor     rax, rsp
0x1800141e0  mov     [rsp+0A8h+var_28], rax
0x1800141e8  xor     ebp, ebp
0x1800141ea  mov     word ptr [rsp+0A8h+pIdentifierAuthority.Value+4], 500h
0x1800141f1  mov     [rdx], ebp
0x1800141f3  mov     rsi, rcx
0x1800141f6  mov     [rcx], rbp
0x1800141f9  mov     r14, rdx
0x1800141fc  lea     rcx, [r11-40h]
0x180014200  mov     [r11-38h], rbp
0x180014204  mov     [r11-70h], rcx
0x180014208  mov     ebx, ebp
0x18001420a  mov     [r11-78h], rbp
0x18001420e  xor     r9d, r9d; pExpirationTime
0x180014211  mov     [rsp+0A8h+Reserved3], ebp; Reserved3
0x180014215  xor     r8d, r8d; Reserved1
0x180014218  xor     edx, edx; ImpersonateOnReturn
0x18001421a  mov     qword ptr [rsp+0A8h+Reserved2.LowPart], rbp; Reserved2
0x18001421f  xor     ecx, ecx; ClientBinding
0x180014221  mov     dword ptr [rsp+0A8h+pIdentifierAuthority.Value], ebx
0x180014225  mov     [rsp+0A8h+pSizeRequired], ebp
0x180014229  mov     [r11-40h], rbp
0x18001422d  call    cs:__imp_RpcGetAuthorizationContextForClient
0x180014233  mov     edi, eax
0x180014235  test    eax, eax
0x180014237  jz      short loc_18001429E
0x180014239  mov     rcx, [rsp+0A8h+pSid]; pSid
0x18001423e  test    rcx, rcx
0x180014241  jz      short loc_180014249
0x180014243  call    cs:__imp_FreeSid
0x180014249  test    rbx, rbx
0x18001424c  jz      short loc_180014262
0x18001424e  call    cs:__imp_GetProcessHeap
0x180014254  mov     r8, rbx; lpMem
0x180014257  xor     edx, edx; dwFlags
0x180014259  mov     rcx, rax; hHeap
0x18001425c  call    cs:__imp_HeapFree
0x180014262  cmp     [rsp+0A8h+pAuthzClientContext], rbp
0x180014267  jz      short loc_180014274
0x180014269  lea     rcx, [rsp+0A8h+pAuthzClientContext]; pAuthzClientContext
0x18001426e  call    cs:__imp_RpcFreeAuthorizationContext
0x180014274  mov     eax, edi
0x180014276  mov     rcx, [rsp+0A8h+var_28]
0x18001427e  xor     rcx, rsp; StackCookie
0x180014281  call    __security_check_cookie
0x180014286  lea     r11, [rsp+0A8h+var_18]
0x18001428e  mov     rbx, [r11+30h]
0x180014292  mov     rbp, [r11+38h]
0x180014296  mov     rsp, r11
0x180014299  pop     r14
0x18001429b  pop     rdi
0x18001429c  pop     rsi
0x18001429d  retn
0x18001429e  mov     rcx, [rsp+0A8h+pAuthzClientContext]; hAuthzClientContext
0x1800142a3  lea     r9, [rsp+0A8h+pSizeRequired]; pSizeRequired
0x1800142a8  xor     r8d, r8d; BufferSize
0x1800142ab  mov     qword ptr [rsp+0A8h+Reserved2.LowPart], rbp; Buffer
0x1800142b0  mov     edx, 1; InfoClass
0x1800142b5  call    cs:__imp_AuthzGetInformationFromContext
0x1800142bb  test    eax, eax
0x1800142bd  jnz     short loc_1800142D2
0x1800142bf  call    cs:__imp_GetLastError
0x1800142c5  mov     edi, eax
0x1800142c7  cmp     eax, 7Ah ; 'z'
0x1800142ca  jnz     loc_180014239
0x1800142d0  mov     edi, ebp
0x1800142d2  mov     ebx, [rsp+0A8h+pSizeRequired]
0x1800142d6  call    cs:__imp_GetProcessHeap
0x1800142dc  mov     r8d, ebx; dwBytes
0x1800142df  mov     edx, 8; dwFlags
0x1800142e4  mov     rcx, rax; hHeap
0x1800142e7  call    cs:__imp_HeapAlloc
0x1800142ed  mov     rbx, rax
0x1800142f0  test    rax, rax
0x1800142f3  jz      loc_180014397
0x1800142f9  mov     r8d, [rsp+0A8h+pSizeRequired]; BufferSize
0x1800142fe  lea     r9, [rsp+0A8h+pSizeRequired]; pSizeRequired
0x180014303  mov     rcx, [rsp+0A8h+pAuthzClientContext]; hAuthzClientContext
0x180014308  mov     edx, 1; InfoClass
0x18001430d  mov     qword ptr [rsp+0A8h+Reserved2.LowPart], rax; Buffer
0x180014312  call    cs:__imp_AuthzGetInformationFromContext
0x180014318  test    eax, eax
0x18001431a  jz      short loc_18001437E
0x18001431c  lea     rax, [rsp+0A8h+pSid]
0x180014321  xor     r9d, r9d; nSubAuthority1
0x180014324  mov     [rsp+0A8h+var_58], rax; pSid
0x180014329  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18001432e  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x180014332  mov     r8d, 12h; nSubAuthority0
0x180014338  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x18001433c  mov     dl, 1; nSubAuthorityCount
0x18001433e  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x180014342  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x180014346  mov     [rsp+0A8h+Reserved3], ebp; nSubAuthority3
0x18001434a  mov     [rsp+0A8h+Reserved2.LowPart], ebp; nSubAuthority2
0x18001434e  call    cs:__imp_AllocateAndInitializeSid
0x180014354  test    eax, eax
0x180014356  jz      short loc_18001437E
0x180014358  mov     rdx, [rbx]; pSid2
0x18001435b  mov     rcx, [rsp+0A8h+pSid]; pSid1
0x180014360  call    cs:__imp_EqualSid
0x180014366  test    eax, eax
0x180014368  jnz     short loc_18001438B
0x18001436a  mov     rcx, [rbx]; Sid
0x18001436d  mov     rdx, rsi; StringSid
0x180014370  call    cs:__imp_ConvertSidToStringSidW
0x180014376  test    eax, eax
0x180014378  jnz     loc_180014239
0x18001437e  call    cs:__imp_GetLastError
0x180014384  mov     edi, eax
0x180014386  jmp     loc_180014239
0x18001438b  mov     dword ptr [r14], 1
0x180014392  jmp     loc_180014239
0x180014397  mov     edi, 80100006h
0x18001439c  jmp     loc_180014239
```
