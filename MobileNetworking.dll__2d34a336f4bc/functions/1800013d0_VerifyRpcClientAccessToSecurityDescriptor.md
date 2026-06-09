# VerifyRpcClientAccessToSecurityDescriptor

- ea: `0x1800013d0`
- end: `0x1800018c7`
- name: `VerifyRpcClientAccessToSecurityDescriptor`
- size: `1271`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, ACCESS_MASK)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001130`

## callees

- `0x1800013d0`
- `0x1800018d0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000180a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000180a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000145d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000145d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000152d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000152d`
- `AUTHZ!AuthzAccessCheck` at `0x18000161a`
- `AUTHZ!AuthzAccessCheck` at `0x18000161a`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180001559`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180001559`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x1800014a8`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x1800014a8`

## pseudocode

```c
__int64 __fastcall VerifyRpcClientAccessToSecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor, ACCESS_MASK a2)
{
  int v2; // edi
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  int v7; // esi
  unsigned int AuthorizationContextForClient; // eax
  unsigned int v9; // eax
  AUTHZ_CLIENT_CONTEXT_HANDLE v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r9
  DWORD LastError; // eax
  int v17; // [rsp+58h] [rbp-39h] BYREF
  PVOID pAuthzClientContext; // [rsp+60h] [rbp-31h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+68h] [rbp-29h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+88h] [rbp-9h] BYREF
  WINBOOL IsMember; // [rsp+108h] [rbp+77h] BYREF
  int v22; // [rsp+110h] [rbp+7Fh] BYREF

  v2 = 0;
  IsMember = 0;
  pAuthzClientContext = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    {
      WPP_SF_(v5[2], 72, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *(_QWORD *)&g_pSecurity )
  {
    v6 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v7 = 1;
LABEL_9:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v6 = 5023;
  v7 = 0;
  if ( v5 == &WPP_GLOBAL_Control )
    goto LABEL_22;
  if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
  {
    WPP_SF_L(v5[2], 73, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 5023);
    goto LABEL_9;
  }
LABEL_10:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
  {
    WPP_SF_L(v5[2], 74, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v6);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v5 == &WPP_GLOBAL_Control )
      goto LABEL_22;
    if ( (*((_BYTE *)v5 + 28) & 4) == 0 )
      goto LABEL_19;
    v12 = 131;
    goto LABEL_48;
  }
  AuthorizationContextForClient = RpcGetAuthorizationContextForClient(0, 0, 0, 0, 0, 0, 0, &pAuthzClientContext);
  v6 = AuthorizationContextForClient;
  if ( AuthorizationContextForClient == 1725 )
  {
    v6 = 0;
    goto LABEL_18;
  }
  if ( AuthorizationContextForClient )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_22;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_19;
    v12 = 132;
    v13 = AuthorizationContextForClient;
    goto LABEL_49;
  }
  v2 = 1;
  v9 = IsRpcClientPrivilegedUser(&IsMember);
  v6 = v9;
  if ( v9 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_22;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_19;
    v12 = 133;
    v13 = v9;
    goto LABEL_49;
  }
  if ( IsMember )
  {
LABEL_18:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  if ( pSecurityDescriptor )
  {
    v11 = (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext;
    v22 = 5;
    v6 = 0;
    v17 = 0;
    memset(&pReply, 0, sizeof(pReply));
    memset(&pRequest, 0, sizeof(pRequest));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    pReply.GrantedAccessMask = (PACCESS_MASK)&v17;
    pRequest.DesiredAccess = a2;
    pReply.Error = (PDWORD)&v22;
    pReply.ResultListLength = 1;
    if ( AuthzAccessCheck(0, v11, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0)
      || (LastError = GetLastError(), (v6 = LastError) == 0) )
    {
      if ( !v22 && v17 == a2 )
        goto LABEL_40;
      v6 = 5;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_41;
      v14 = 12;
      v15 = 5;
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_41:
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
        {
          WPP_SF_L(v5[2], 13, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v6);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_44:
        if ( !v6 )
          goto LABEL_19;
        if ( v5 == &WPP_GLOBAL_Control )
          goto LABEL_22;
        if ( (*((_BYTE *)v5 + 28) & 4) == 0 )
          goto LABEL_19;
        v12 = 135;
        goto LABEL_48;
      }
      v14 = 11;
      v15 = LastError;
    }
    WPP_SF_L(v5[2], v14, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v15);
LABEL_40:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v6 = 87;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_22;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = 134;
LABEL_48:
    v13 = v6;
LABEL_49:
    WPP_SF_L(v5[2], v12, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v13);
    goto LABEL_18;
  }
LABEL_19:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
  {
    WPP_SF_(v5[2], 75, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( v7 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
  {
    WPP_SF_L(v5[2], 76, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    RpcFreeAuthorizationContext(&pAuthzClientContext);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_L(v5[2], 136, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800013d0  mov     rax, rsp
0x1800013d3  push    rbp
0x1800013d4  lea     rbp, [rax-5Fh]
0x1800013d8  sub     rsp, 0E0h
0x1800013df  mov     [rax-10h], rsi
0x1800013e3  mov     [rax-18h], rdi
0x1800013e7  mov     [rax-20h], r12
0x1800013eb  xor     r12d, r12d
0x1800013ee  mov     [rax-28h], r13
0x1800013f2  mov     edi, r12d
0x1800013f5  mov     [rax-30h], r14
0x1800013f9  mov     r14, rcx
0x1800013fc  mov     [rax-38h], r15
0x180001400  mov     r15d, edx
0x180001403  mov     [rbp+57h+IsMember], r12d
0x180001407  mov     [rbp+57h+var_88], r12
0x18000140b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001412  lea     r13, WPP_GLOBAL_Control
0x180001419  cmp     rcx, r13
0x18000141c  jz      short loc_180001437
0x18000141e  test    byte ptr [rcx+1Ch], 8
0x180001422  jnz     loc_1800016E2
0x180001428  cmp     rcx, r13
0x18000142b  jz      short loc_180001437
0x18000142d  test    byte ptr [rcx+1Ch], 8
0x180001431  jnz     loc_180001703
0x180001437  cmp     cs:g_pSecurity, rdi
0x18000143e  mov     [rsp+0E0h+arg_0], rbx
0x180001446  jz      loc_180001724
0x18000144c  mov     rcx, cs:g_pSecurity
0x180001453  mov     ebx, r12d
0x180001456  add     rcx, 170h; lpCriticalSection
0x18000145d  call    cs:__imp_EnterCriticalSection
0x180001463  mov     esi, 1
0x180001468  mov     rcx, cs:WPP_GLOBAL_Control
0x18000146f  cmp     rcx, r13
0x180001472  jz      short loc_18000147E
0x180001474  test    byte ptr [rcx+1Ch], 8
0x180001478  jnz     loc_1800016BE
0x18000147e  test    ebx, ebx
0x180001480  jnz     loc_18000175C
0x180001486  lea     rcx, [rbp+57h+var_88]
0x18000148a  xor     r9d, r9d; pExpirationTime
0x18000148d  mov     [rsp+0E0h+pAuthzClientContext], rcx; pAuthzClientContext
0x180001492  xor     r8d, r8d; Reserved1
0x180001495  mov     [rsp+0E0h+Reserved4], r12; Reserved4
0x18000149a  xor     edx, edx; ImpersonateOnReturn
0x18000149c  mov     [rsp+0E0h+Reserved3], r12d; Reserved3
0x1800014a1  xor     ecx, ecx; ClientBinding
0x1800014a3  mov     qword ptr [rsp+0E0h+Reserved2.LowPart], r12; Reserved2
0x1800014a8  call    cs:__imp_RpcGetAuthorizationContextForClient
0x1800014ae  mov     ebx, eax
0x1800014b0  cmp     eax, 6BDh
0x1800014b5  jz      loc_180001682
0x1800014bb  test    eax, eax
0x1800014bd  jnz     loc_180001779
0x1800014c3  lea     rcx, [rbp+57h+IsMember]; IsMember
0x1800014c7  mov     edi, 1
0x1800014cc  call    IsRpcClientPrivilegedUser
0x1800014d1  mov     ebx, eax
0x1800014d3  test    eax, eax
0x1800014d5  jnz     loc_1800017A0
0x1800014db  cmp     [rbp+57h+IsMember], r12d
0x1800014df  jz      loc_180001590
0x1800014e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014ec  cmp     rcx, r13
0x1800014ef  jz      short loc_1800014FB
0x1800014f1  test    byte ptr [rcx+1Ch], 8
0x1800014f5  jnz     loc_180001865
0x1800014fb  mov     r15, [rsp+0E0h+var_30]
0x180001503  test    esi, esi
0x180001505  mov     rsi, [rsp+0D8h]
0x18000150d  mov     r14, [rsp+0E0h+var_28]
0x180001515  mov     r12, [rsp+0E0h+var_18]
0x18000151d  jz      short loc_18000153A
0x18000151f  mov     rcx, cs:g_pSecurity
0x180001526  add     rcx, 170h; lpCriticalSection
0x18000152d  call    cs:__imp_LeaveCriticalSection
0x180001533  mov     rcx, cs:WPP_GLOBAL_Control
0x18000153a  cmp     rcx, r13
0x18000153d  jz      short loc_180001549
0x18000153f  test    byte ptr [rcx+1Ch], 8
0x180001543  jnz     loc_180001886
0x180001549  test    edi, edi
0x18000154b  mov     rdi, [rsp+0E0h+var_10]
0x180001553  jz      short loc_180001566
0x180001555  lea     rcx, [rbp+57h+var_88]; pAuthzClientContext
0x180001559  call    cs:__imp_RpcFreeAuthorizationContext
0x18000155f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001566  cmp     rcx, r13
0x180001569  mov     r13, [rsp+0E0h+var_20]
0x180001571  jz      short loc_18000157D
0x180001573  test    byte ptr [rcx+1Ch], 8
0x180001577  jnz     loc_1800018AA
0x18000157d  mov     eax, ebx
0x18000157f  mov     rbx, [rsp+0E0h+arg_0]
0x180001587  add     rsp, 0E0h
0x18000158e  pop     rbp
0x18000158f  retn
0x180001590  test    r14, r14
0x180001593  jz      loc_1800017C7
0x180001599  mov     r12, [rbp+57h+var_88]
0x18000159d  xorps   xmm0, xmm0
0x1800015a0  xorps   xmm1, xmm1
0x1800015a3  mov     [rbp+57h+arg_18], 5
0x1800015aa  xor     ebx, ebx
0x1800015ac  xor     eax, eax
0x1800015ae  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x1800015b2  mov     [rbp+57h+var_90], eax
0x1800015b5  movups  xmmword ptr [rbp+57h+pReply.ResultListLength], xmm0
0x1800015b9  movups  xmmword ptr [rbp+57h+pReply.SaclEvaluationResults], xmm0
0x1800015bd  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm1
0x1800015c1  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm1
0x1800015c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015cc  cmp     rcx, r13
0x1800015cf  jz      short loc_1800015DB
0x1800015d1  test    byte ptr [rcx+1Ch], 8
0x1800015d5  jnz     loc_1800017F0
0x1800015db  mov     [rsp+40h], rbx; phAccessCheckResults
0x1800015e0  lea     rax, [rbp+57h+var_90]
0x1800015e4  mov     [rbp+57h+pReply.GrantedAccessMask], rax
0x1800015e8  lea     r8, [rbp+57h+pRequest]; pRequest
0x1800015ec  lea     rax, [rbp+57h+arg_18]
0x1800015f0  mov     [rbp+57h+pRequest.DesiredAccess], r15d
0x1800015f4  mov     [rbp+57h+pReply.Error], rax
0x1800015f8  xor     r9d, r9d; hAuditEvent
0x1800015fb  lea     rax, [rbp+57h+pReply]
0x1800015ff  mov     [rbp+57h+pReply.ResultListLength], edi
0x180001602  mov     [rsp+0E0h+pAuthzClientContext], rax; pReply
0x180001607  mov     rdx, r12; hAuthzClientContext
0x18000160a  mov     dword ptr [rsp+0E0h+Reserved4], ebx; OptionalSecurityDescriptorCount
0x18000160e  xor     ecx, ecx; Flags
0x180001610  mov     qword ptr [rsp+0E0h+Reserved3], rbx; OptionalSecurityDescriptorArray
0x180001615  mov     qword ptr [rsp+0E0h+Reserved2.LowPart], r14; pSecurityDescriptor
0x18000161a  call    cs:__imp_AuthzAccessCheck
0x180001620  test    eax, eax
0x180001622  jz      loc_18000180A
0x180001628  cmp     [rbp+57h+arg_18], 0
0x18000162c  jnz     short loc_18000168A
0x18000162e  cmp     [rbp+57h+var_90], r15d
0x180001632  jnz     short loc_18000168A
0x180001634  mov     rcx, cs:WPP_GLOBAL_Control
0x18000163b  cmp     rcx, r13
0x18000163e  jz      short loc_18000164A
0x180001640  test    byte ptr [rcx+1Ch], 8
0x180001644  jnz     loc_180001841
0x18000164a  test    ebx, ebx
0x18000164c  jz      loc_1800014EC
0x180001652  cmp     rcx, r13
0x180001655  jz      loc_1800014FB
0x18000165b  test    byte ptr [rcx+1Ch], 4
0x18000165f  jz      loc_1800014EC
0x180001665  mov     edx, 87h
0x18000166a  mov     r9d, ebx
0x18000166d  mov     rcx, [rcx+10h]
0x180001671  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001678  call    WPP_SF_L
0x18000167d  jmp     loc_1800014E5
0x180001682  mov     ebx, r12d
0x180001685  jmp     loc_1800014E5
0x18000168a  mov     ebx, 5
0x18000168f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001696  cmp     rcx, r13
0x180001699  jz      short loc_18000164A
0x18000169b  test    byte ptr [rcx+1Ch], 4
0x18000169f  jz      short loc_18000163B
0x1800016a1  mov     edx, 0Ch
0x1800016a6  mov     r9d, ebx
0x1800016a9  mov     rcx, [rcx+10h]
0x1800016ad  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800016b4  call    WPP_SF_L
0x1800016b9  jmp     loc_180001634
0x1800016be  mov     rcx, [rcx+10h]
0x1800016c2  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800016c9  mov     edx, 4Ah ; 'J'
0x1800016ce  mov     r9d, ebx
0x1800016d1  call    WPP_SF_L
0x1800016d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016dd  jmp     loc_18000147E
0x1800016e2  mov     rcx, [rcx+10h]
0x1800016e6  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800016ed  mov     edx, 82h
0x1800016f2  call    WPP_SF_
0x1800016f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016fe  jmp     loc_180001428
0x180001703  mov     rcx, [rcx+10h]
0x180001707  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000170e  mov     edx, 48h ; 'H'
0x180001713  call    WPP_SF_
0x180001718  mov     rcx, cs:WPP_GLOBAL_Control
0x18000171f  jmp     loc_180001437
0x180001724  mov     ebx, 139Fh
0x180001729  mov     esi, r12d
0x18000172c  cmp     rcx, r13
0x18000172f  jz      loc_1800014FB
0x180001735  test    byte ptr [rcx+1Ch], 4
0x180001739  jz      loc_18000146F
0x18000173f  mov     rcx, [rcx+10h]
0x180001743  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000174a  mov     edx, 49h ; 'I'
0x18000174f  mov     r9d, ebx
0x180001752  call    WPP_SF_L
0x180001757  jmp     loc_180001468
0x18000175c  cmp     rcx, r13
0x18000175f  jz      loc_1800014FB
0x180001765  test    byte ptr [rcx+1Ch], 4
0x180001769  jz      loc_1800014EC
0x18000176f  mov     edx, 83h
0x180001774  jmp     loc_18000166A
0x180001779  mov     rcx, cs:WPP_GLOBAL_Control
0x180001780  cmp     rcx, r13
0x180001783  jz      loc_1800014FB
0x180001789  test    byte ptr [rcx+1Ch], 4
0x18000178d  jz      loc_1800014EC
0x180001793  mov     edx, 84h
0x180001798  mov     r9d, eax
0x18000179b  jmp     loc_18000166D
0x1800017a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017a7  cmp     rcx, r13
0x1800017aa  jz      loc_1800014FB
0x1800017b0  test    byte ptr [rcx+1Ch], 4
0x1800017b4  jz      loc_1800014EC
0x1800017ba  mov     edx, 85h
0x1800017bf  mov     r9d, eax
0x1800017c2  jmp     loc_18000166D
0x1800017c7  mov     ebx, 57h ; 'W'
0x1800017cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017d3  cmp     rcx, r13
0x1800017d6  jz      loc_1800014FB
0x1800017dc  test    byte ptr [rcx+1Ch], 4
0x1800017e0  jz      loc_1800014EC
0x1800017e6  mov     edx, 86h
0x1800017eb  jmp     loc_18000166A
0x1800017f0  mov     rcx, [rcx+10h]
0x1800017f4  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800017fb  mov     edx, 0Ah
0x180001800  call    WPP_SF_
0x180001805  jmp     loc_1800015DB
0x18000180a  call    cs:__imp_GetLastError
0x180001810  mov     ebx, eax
0x180001812  test    eax, eax
0x180001814  jz      loc_180001628
0x18000181a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001821  cmp     rcx, r13
0x180001824  jz      loc_18000164A
0x18000182a  test    byte ptr [rcx+1Ch], 4
0x18000182e  jz      loc_18000163B
0x180001834  mov     edx, 0Bh
0x180001839  mov     r9d, eax
0x18000183c  jmp     loc_1800016A9
0x180001841  mov     rcx, [rcx+10h]
0x180001845  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000184c  mov     edx, 0Dh
0x180001851  mov     r9d, ebx
0x180001854  call    WPP_SF_L
0x180001859  mov     rcx, cs:WPP_GLOBAL_Control
0x180001860  jmp     loc_18000164A
0x180001865  mov     rcx, [rcx+10h]
0x180001869  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001870  mov     edx, 4Bh ; 'K'
0x180001875  call    WPP_SF_
0x18000187a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001881  jmp     loc_1800014FB
0x180001886  mov     rcx, [rcx+10h]
0x18000188a  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001891  mov     edx, 4Ch ; 'L'
0x180001896  xor     r9d, r9d
0x180001899  call    WPP_SF_L
0x18000189e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018a5  jmp     loc_180001549
0x1800018aa  mov     rcx, [rcx+10h]
0x1800018ae  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800018b5  mov     edx, 88h
0x1800018ba  mov     r9d, ebx
0x1800018bd  call    WPP_SF_L
0x1800018c2  jmp     loc_18000157D
```
