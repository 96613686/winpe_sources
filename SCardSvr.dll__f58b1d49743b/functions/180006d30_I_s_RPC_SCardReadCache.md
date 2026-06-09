# I_s_RPC_SCardReadCache

- ea: `0x180006d30`
- end: `0x180007058`
- name: `I_s_RPC_SCardReadCache`
- size: `808`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned int, unsigned __int16 *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800072f0`

## callees

- `0x1800028b0`
- `0x180005eac`
- `0x180006d30`
- `0x180023168`
- `0x180023276`
- `0x18003261b`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ec4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ec4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006fb8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006fb8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006fa3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006fa3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006df9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006df9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006fca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006fca`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180006e25`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180006e25`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x180006ddc`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x180006ddc`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180006f14`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180006f5f`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180006f14`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180006f5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_s_RPC_SCardReadCache(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        _QWORD *a5,
        _DWORD *a6)
{
  PSID *v8; // rbx
  int v9; // r14d
  ulong AuthorizationContextForClient; // edi
  HANDLE ProcessHeap; // rax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  HANDLE v14; // rax
  void *v15; // rax
  const WCHAR *v16; // rdx
  void *v17; // rbx
  PSID *v19; // rax
  DWORD pSizeRequired; // [rsp+60h] [rbp-A8h] BYREF
  PVOID pAuthzClientContext; // [rsp+68h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-98h] BYREF
  ulong pExceptionObject; // [rsp+78h] [rbp-90h] BYREF
  ulong v24; // [rsp+7Ch] [rbp-8Ch] BYREF
  ulong v25; // [rsp+80h] [rbp-88h] BYREF
  PSID pSid; // [rsp+88h] [rbp-80h] BYREF
  void **v27; // [rsp+90h] [rbp-78h] BYREF
  void *Src; // [rsp+98h] [rbp-70h]
  SIZE_T dwBytes; // [rsp+A0h] [rbp-68h]
  ulong v30; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v31; // [rsp+B0h] [rbp-58h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-50h] BYREF

  v31 = a4;
  v27 = &CBuffer::`vftable';
  Src = 0;
  dwBytes = 0;
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  pSid = 0;
  v8 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSizeRequired = 0;
  pAuthzClientContext = 0;
  v9 = 0;
  hMem = 0;
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
    v19 = (PSID *)AllocH(pSizeRequired);
    v8 = v19;
    if ( v19 )
    {
      if ( AuthzGetInformationFromContext(
             (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
             AuthzContextInfoUserSid,
             pSizeRequired,
             &pSizeRequired,
             v19)
        && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        if ( EqualSid(pSid, *v8) )
        {
          v9 = 1;
          goto LABEL_2;
        }
        if ( ConvertSidToStringSidW(*v8, (LPWSTR *)&hMem) )
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
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  if ( pAuthzClientContext )
    RpcFreeAuthorizationContext(&pAuthzClientContext);
  try
  {
    if ( AuthorizationContextForClient )
    {
      pExceptionObject = AuthorizationContextForClient;
      throw &pExceptionObject;
    }
    v12 = ServerCacheRead(a2, a3, v31, v9, (const unsigned __int16 *)hMem, (struct CBuffer *)&v27);
    if ( v12 )
    {
      v24 = v12;
      throw &v24;
    }
    v13 = dwBytes;
    *a6 = dwBytes;
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 8u, v13);
    *a5 = v15;
    if ( !v15 )
    {
      v25 = -2146435066;
      throw &v25;
    }
    v16 = &Data;
    v17 = Src;
    if ( HIDWORD(dwBytes) )
      v16 = (const WCHAR *)Src;
    memcpy_0(v15, v16, (unsigned int)*a6);
  }
  catch ( ulong v30 )
  {
    pSizeRequired = v30;
    v17 = Src;
    AuthorizationContextForClient = v30;
  }
  catch ( ... )
  {
    pSizeRequired = -2146435055;
    v17 = Src;
    AuthorizationContextForClient = -2146435055;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v17 )
    operator delete[](v17);
  return AuthorizationContextForClient;
}

```

## disassembly

```asm
0x180006d30  mov     r11, rsp
0x180006d33  push    rbx
0x180006d34  push    rsi
0x180006d35  push    rdi
0x180006d36  push    r12
0x180006d38  push    r13
0x180006d3a  push    r14
0x180006d3c  push    r15
0x180006d3e  sub     rsp, 0D0h
0x180006d45  mov     rax, cs:__security_cookie
0x180006d4c  xor     rax, rsp
0x180006d4f  mov     [rsp+108h+var_48], rax
0x180006d57  mov     [rsp+108h+var_58], r9
0x180006d5f  mov     r13d, r8d
0x180006d62  mov     r12, rdx
0x180006d65  mov     r15, [rsp+108h+arg_20]
0x180006d6d  mov     rsi, [rsp+108h+arg_28]
0x180006d75  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180006d7c  mov     [r11-78h], rax
0x180006d80  xor     edx, edx; ImpersonateOnReturn
0x180006d82  mov     [r11-70h], rdx
0x180006d86  mov     [r11-68h], rdx
0x180006d8a  mov     [rsp+108h+hMem], rdx
0x180006d8f  mov     eax, 1
0x180006d94  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x180006d9a  mov     [r11-80h], rdx
0x180006d9e  mov     ebx, edx
0x180006da0  mov     [r11-50h], ebx
0x180006da4  mov     word ptr [r11-4Ch], 500h
0x180006dab  mov     [rsp+108h+pSizeRequired], edx
0x180006daf  mov     [rsp+108h+var_A0], rdx
0x180006db4  mov     r14d, edx
0x180006db7  mov     [rsp+108h+hMem], rdx
0x180006dbc  lea     rcx, [rsp+108h+var_A0]
0x180006dc1  mov     [rsp+108h+pAuthzClientContext], rcx; pAuthzClientContext
0x180006dc6  mov     [rsp+108h+Reserved4], rdx; Reserved4
0x180006dcb  mov     [rsp+108h+Reserved3], edx; Reserved3
0x180006dcf  mov     qword ptr [rsp+108h+Reserved2.LowPart], rdx; Reserved2
0x180006dd4  xor     r9d, r9d; pExpirationTime
0x180006dd7  xor     r8d, r8d; Reserved1
0x180006dda  xor     ecx, ecx; ClientBinding
0x180006ddc  call    cs:__imp_RpcGetAuthorizationContextForClient
0x180006de2  mov     edi, eax
0x180006de4  test    eax, eax
0x180006de6  jz      loc_180006EFD
0x180006dec  mov     rcx, [rsp+108h+pSid]; pSid
0x180006df4  test    rcx, rcx
0x180006df7  jz      short loc_180006DFF
0x180006df9  call    cs:__imp_FreeSid
0x180006dff  test    rbx, rbx
0x180006e02  jz      short loc_180006E18
0x180006e04  call    cs:__imp_GetProcessHeap
0x180006e0a  mov     rcx, rax; hHeap
0x180006e0d  mov     r8, rbx; lpMem
0x180006e10  xor     edx, edx; dwFlags
0x180006e12  call    cs:__imp_HeapFree
0x180006e18  cmp     [rsp+108h+var_A0], 0
0x180006e1e  jz      short loc_180006E2B
0x180006e20  lea     rcx, [rsp+108h+var_A0]; pAuthzClientContext
0x180006e25  call    cs:__imp_RpcFreeAuthorizationContext
0x180006e2b  test    edi, edi
0x180006e2d  jnz     loc_180006FFA
0x180006e33  lea     rax, [rsp+108h+var_78]
0x180006e3b  mov     qword ptr [rsp+108h+Reserved3], rax; struct CBuffer *
0x180006e40  mov     rax, [rsp+108h+hMem]
0x180006e45  mov     qword ptr [rsp+108h+Reserved2.LowPart], rax; unsigned __int16 *
0x180006e4a  mov     r9d, r14d; int
0x180006e4d  mov     r8, [rsp+108h+var_58]; unsigned __int16 *
0x180006e55  mov     edx, r13d; unsigned int
0x180006e58  mov     rcx, r12; struct _GUID *
0x180006e5b  call    ?ServerCacheRead@@YAKPEAU_GUID@@KPEBGH1AEAVCBuffer@@@Z; ServerCacheRead(_GUID *,ulong,ushort const *,int,ushort const *,CBuffer &)
0x180006e60  test    eax, eax
0x180006e62  jnz     loc_18000700F
0x180006e68  mov     ebx, dword ptr [rsp+108h+dwBytes]
0x180006e6f  mov     [rsi], ebx
0x180006e71  call    cs:__imp_GetProcessHeap
0x180006e77  mov     rcx, rax; hHeap
0x180006e7a  mov     r8d, ebx; dwBytes
0x180006e7d  mov     edx, 8; dwFlags
0x180006e82  call    cs:__imp_HeapAlloc
0x180006e88  mov     [r15], rax
0x180006e8b  test    rax, rax
0x180006e8e  jz      loc_180007024
0x180006e94  lea     rdx, Data
0x180006e9b  mov     rbx, [rsp+108h+Src]
0x180006ea3  cmp     dword ptr [rsp+108h+dwBytes+4], edi
0x180006eaa  cmova   rdx, rbx; Src
0x180006eae  mov     r8d, [rsi]; Size
0x180006eb1  mov     rcx, rax; void *
0x180006eb4  call    memcpy_0
0x180006eb9  nop
0x180006eba  mov     rcx, [rsp+108h+hMem]; hMem
0x180006ebf  test    rcx, rcx
0x180006ec2  jz      short loc_180006ECB
0x180006ec4  call    cs:__imp_LocalFree
0x180006eca  nop
0x180006ecb  test    rbx, rbx
0x180006ece  jz      short loc_180006ED8
0x180006ed0  mov     rcx, rbx; Block
0x180006ed3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006ed8  mov     eax, edi
0x180006eda  mov     rcx, [rsp+108h+var_48]
0x180006ee2  xor     rcx, rsp; StackCookie
0x180006ee5  call    __security_check_cookie
0x180006eea  add     rsp, 0D0h
0x180006ef1  pop     r15
0x180006ef3  pop     r14
0x180006ef5  pop     r13
0x180006ef7  pop     r12
0x180006ef9  pop     rdi
0x180006efa  pop     rsi
0x180006efb  pop     rbx
0x180006efc  retn
0x180006efd  mov     qword ptr [rsp+108h+Reserved2.LowPart], rbx; Buffer
0x180006f02  lea     r9, [rsp+108h+pSizeRequired]; pSizeRequired
0x180006f07  xor     r8d, r8d; BufferSize
0x180006f0a  mov     edx, 1; InfoClass
0x180006f0f  mov     rcx, [rsp+108h+var_A0]; hAuthzClientContext
0x180006f14  call    cs:__imp_AuthzGetInformationFromContext
0x180006f1a  test    eax, eax
0x180006f1c  jnz     short loc_180006F31
0x180006f1e  call    cs:__imp_GetLastError
0x180006f24  mov     edi, eax
0x180006f26  cmp     eax, 7Ah ; 'z'
0x180006f29  jnz     loc_180006DEC
0x180006f2f  xor     edi, edi
0x180006f31  mov     ecx, [rsp+108h+pSizeRequired]; unsigned __int64
0x180006f35  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x180006f3a  mov     rbx, rax
0x180006f3d  test    rax, rax
0x180006f40  jz      loc_180006FF0
0x180006f46  mov     qword ptr [rsp+108h+Reserved2.LowPart], rax; Buffer
0x180006f4b  lea     r9, [rsp+108h+pSizeRequired]; pSizeRequired
0x180006f50  mov     r8d, [rsp+108h+pSizeRequired]; BufferSize
0x180006f55  mov     edx, 1; InfoClass
0x180006f5a  mov     rcx, [rsp+108h+var_A0]; hAuthzClientContext
0x180006f5f  call    cs:__imp_AuthzGetInformationFromContext
0x180006f65  test    eax, eax
0x180006f67  jz      short loc_180006FD8
0x180006f69  lea     rax, [rsp+108h+pSid]
0x180006f71  mov     [rsp+108h+var_B8], rax; pSid
0x180006f76  xor     eax, eax
0x180006f78  mov     [rsp+108h+nSubAuthority7], eax; nSubAuthority7
0x180006f7c  mov     [rsp+108h+nSubAuthority6], eax; nSubAuthority6
0x180006f80  mov     dword ptr [rsp+108h+pAuthzClientContext], eax; nSubAuthority5
0x180006f84  mov     dword ptr [rsp+108h+Reserved4], eax; nSubAuthority4
0x180006f88  mov     [rsp+108h+Reserved3], eax; nSubAuthority3
0x180006f8c  mov     [rsp+108h+Reserved2.LowPart], eax; nSubAuthority2
0x180006f90  xor     r9d, r9d; nSubAuthority1
0x180006f93  mov     r8d, 12h; nSubAuthority0
0x180006f99  mov     dl, 1; nSubAuthorityCount
0x180006f9b  lea     rcx, [rsp+108h+pIdentifierAuthority]; pIdentifierAuthority
0x180006fa3  call    cs:__imp_AllocateAndInitializeSid
0x180006fa9  test    eax, eax
0x180006fab  jz      short loc_180006FD8
0x180006fad  mov     rdx, [rbx]; pSid2
0x180006fb0  mov     rcx, [rsp+108h+pSid]; pSid1
0x180006fb8  call    cs:__imp_EqualSid
0x180006fbe  test    eax, eax
0x180006fc0  jnz     short loc_180006FE5
0x180006fc2  lea     rdx, [rsp+108h+hMem]; StringSid
0x180006fc7  mov     rcx, [rbx]; Sid
0x180006fca  call    cs:__imp_ConvertSidToStringSidW
0x180006fd0  test    eax, eax
0x180006fd2  jnz     loc_180006DEC
0x180006fd8  call    cs:__imp_GetLastError
0x180006fde  mov     edi, eax
0x180006fe0  jmp     loc_180006DEC
0x180006fe5  mov     r14d, 1
0x180006feb  jmp     loc_180006DEC
0x180006ff0  mov     edi, 80100006h
0x180006ff5  jmp     loc_180006DEC
0x180006ffa  mov     [rsp+108h+pExceptionObject], edi
0x180006ffe  lea     rdx, _TI1K; pThrowInfo
0x180007005  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18000700a  call    _CxxThrowException_0
0x18000700f  mov     [rsp+108h+var_8C], eax
0x180007013  lea     rdx, _TI1K; pThrowInfo
0x18000701a  lea     rcx, [rsp+108h+var_8C]; pExceptionObject
0x18000701f  call    _CxxThrowException_0
0x180007024  mov     [rsp+108h+var_88], 80100006h
0x18000702f  lea     rdx, _TI1K; pThrowInfo
0x180007036  lea     rcx, [rsp+108h+var_88]; pExceptionObject
0x18000703e  call    _CxxThrowException_0
0x180007044  jmp     short $+2
0x180007046  mov     rbx, [rsp+108h+Src]
0x18000704e  mov     edi, [rsp+108h+pSizeRequired]
0x180007052  jmp     loc_180006EBA
```
