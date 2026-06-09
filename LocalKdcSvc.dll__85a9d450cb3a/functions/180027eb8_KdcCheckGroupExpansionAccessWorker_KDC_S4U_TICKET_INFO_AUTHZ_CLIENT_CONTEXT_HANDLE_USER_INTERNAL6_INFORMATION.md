# KdcCheckGroupExpansionAccessWorker(_KDC_S4U_TICKET_INFO *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_USER_INTERNAL6_INFORMATION *)

- ea: `0x180027eb8`
- end: `0x1800280a5`
- name: `?KdcCheckGroupExpansionAccessWorker@@YA?AV?$tuple@JUGroupExpansionErrors@@@std@@PEAU_KDC_S4U_TICKET_INFO@@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_USER_INTERNAL6_INFORMATION@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(__int64, __int64, AUTHZ_CLIENT_CONTEXT_HANDLE, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027e50`

## callees

- `0x180002ad0`
- `0x1800101ec`
- `0x18001022c`
- `0x180027eb8`
- `0x180072338`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fb2`
- `AUTHZ!AuthzAccessCheck` at `0x180027fa8`
- `AUTHZ!AuthzAccessCheck` at `0x180027fa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcCheckGroupExpansionAccessWorker(
        __int64 a1,
        __int64 a2,
        AUTHZ_CLIENT_CONTEXT_HANDLE a3,
        __int64 a4)
{
  bool v4; // zf
  GUID *v6; // rax
  void *pSecurityDescriptor; // rax
  DWORD LastError; // eax
  CSecurityData *v9; // rcx
  unsigned int v10; // ecx
  DWORD i; // eax
  __int64 v12; // rdi
  __int64 v13; // r9
  CSecurityData *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // eax
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+50h] [rbp-69h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+70h] [rbp-49h] BYREF
  __int64 v20; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp-19h]
  _QWORD v22[6]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+1Fh] BYREF
  int v24; // [rsp+E0h] [rbp+27h]

  *(_QWORD *)&pRequest.DesiredAccess = 16;
  v23 = 0;
  v4 = (*(_DWORD *)(a4 + 280) & 0x180) == 0;
  v24 = 0;
  v20 = 0;
  v21 = 0;
  v6 = &GUID_C_COMPUTER;
  if ( v4 )
    v6 = &GUID_C_USER;
  *(_QWORD *)&pRequest.ObjectTypeListLength = 3;
  v22[1] = v6;
  *(_QWORD *)&pReply.ResultListLength = 3;
  v22[3] = &GUID_PS_REMOTE_ACCESS_INFO;
  pReply.SaclEvaluationResults = 0;
  v22[5] = &GUID_A_TOKEN_GROUPS_GLOBAL_AND_UNIVERSAL;
  pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)v22;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v23;
  pReply.Error = (PDWORD)&v20;
  pSecurityDescriptor = *(void **)(a4 + 264);
  v22[0] = 0;
  v22[2] = 1;
  v22[4] = 2;
  pRequest.OptionalArguments = 0;
  pRequest.PrincipalSelfSid = 0;
  if ( AuthzAccessCheck(0, a3, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= pReply.ResultListLength )
      {
        v16 = v21;
        *(_QWORD *)a1 = v20;
        *(_QWORD *)(a1 + 8) = v16;
        return a1;
      }
      v12 = i;
      v13 = *((unsigned int *)&v20 + i);
      if ( (_DWORD)v13 )
        break;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v13, i);
    if ( *((_DWORD *)&v20 + v12) != 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v14);
    v15 = v21;
    *(_QWORD *)a1 = v20;
    *(_DWORD *)(a1 + 8) = v15;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v20) = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
      LastError = v20;
    }
    if ( LastError != 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9);
    v10 = v21;
    *(_QWORD *)a1 = v20;
    *(_DWORD *)(a1 + 8) = v10;
  }
  *(_DWORD *)(a1 + 12) = -1073741790;
  return a1;
}

```

## disassembly

```asm
0x180027eb8  push    rbp
0x180027eba  push    rbx
0x180027ebb  push    rsi
0x180027ebc  push    rdi
0x180027ebd  push    r14
0x180027ebf  lea     rbp, [rsp-37h]
0x180027ec4  sub     rsp, 0F0h
0x180027ecb  mov     rax, cs:__security_cookie
0x180027ed2  xor     rax, rsp
0x180027ed5  mov     [rbp+57h+var_28], rax
0x180027ed9  xor     eax, eax
0x180027edb  mov     qword ptr [rbp+57h+pRequest.DesiredAccess], 10h
0x180027ee3  mov     [rbp+57h+var_38], rax
0x180027ee7  xor     esi, esi
0x180027ee9  test    dword ptr [r9+118h], 180h
0x180027ef4  mov     rbx, rcx
0x180027ef7  mov     [rbp+57h+var_30], eax
0x180027efa  lea     rcx, ?GUID_C_USER@@3U_GUID@@A; _GUID GUID_C_USER
0x180027f01  mov     [rbp+57h+var_78], rax
0x180027f05  mov     rdx, r8; hAuthzClientContext
0x180027f08  mov     [rbp+57h+var_70], eax
0x180027f0b  lea     r8, [rbp+57h+pRequest]; pRequest
0x180027f0f  mov     [rsp+110h+phAccessCheckResults], rsi; phAccessCheckResults
0x180027f14  lea     rax, ?GUID_C_COMPUTER@@3U_GUID@@A; _GUID GUID_C_COMPUTER
0x180027f1b  cmovz   rax, rcx
0x180027f1f  mov     qword ptr [rbp+57h+pRequest.ObjectTypeListLength], 3
0x180027f27  mov     [rbp+57h+var_60], rax
0x180027f2b  lea     r14d, [rsi+1]
0x180027f2f  lea     rax, ?GUID_PS_REMOTE_ACCESS_INFO@@3U_GUID@@A; _GUID GUID_PS_REMOTE_ACCESS_INFO
0x180027f36  mov     qword ptr [rbp+57h+var_C0.ResultListLength], 3
0x180027f3e  mov     [rbp+57h+var_50], rax
0x180027f42  xor     ecx, ecx; Flags
0x180027f44  lea     rax, ?GUID_A_TOKEN_GROUPS_GLOBAL_AND_UNIVERSAL@@3U_GUID@@A; _GUID GUID_A_TOKEN_GROUPS_GLOBAL_AND_UNIVERSAL
0x180027f4b  mov     [rbp+57h+var_C0.SaclEvaluationResults], rsi
0x180027f4f  mov     [rbp+57h+var_40], rax
0x180027f53  lea     rax, [rbp+57h+var_68]
0x180027f57  mov     [rbp+57h+pRequest.ObjectTypeList], rax
0x180027f5b  lea     rax, [rbp+57h+var_38]
0x180027f5f  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x180027f63  lea     rax, [rbp+57h+var_78]
0x180027f67  mov     [rbp+57h+var_C0.Error], rax
0x180027f6b  lea     rax, [rbp+57h+var_C0]
0x180027f6f  mov     [rsp+110h+pReply], rax; pReply
0x180027f74  mov     rax, [r9+108h]
0x180027f7b  xor     r9d, r9d; hAuditEvent
0x180027f7e  mov     [rsp+110h+OptionalSecurityDescriptorCount], esi; OptionalSecurityDescriptorCount
0x180027f82  mov     [rsp+110h+OptionalSecurityDescriptorArray], rsi; OptionalSecurityDescriptorArray
0x180027f87  mov     [rsp+110h+pSecurityDescriptor], rax; pSecurityDescriptor
0x180027f8c  mov     [rbp+57h+var_68], rsi
0x180027f90  mov     [rbp+57h+var_58], 1
0x180027f98  mov     [rbp+57h+var_48], 2
0x180027fa0  mov     [rbp+57h+pRequest.OptionalArguments], rsi
0x180027fa4  mov     [rbp+57h+pRequest.PrincipalSelfSid], rsi
0x180027fa8  call    cs:__imp_AuthzAccessCheck
0x180027fae  test    eax, eax
0x180027fb0  jnz     short loc_18002800F
0x180027fb2  call    cs:__imp_GetLastError
0x180027fb8  mov     dword ptr [rbp+57h+var_78], eax
0x180027fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fc2  lea     rdx, WPP_GLOBAL_Control
0x180027fc9  cmp     rcx, rdx
0x180027fcc  jz      short loc_180027FED
0x180027fce  test    [rcx+1Ch], r14b
0x180027fd2  jz      short loc_180027FED
0x180027fd4  mov     rcx, [rcx+10h]
0x180027fd8  lea     edx, [rsi+0Ah]
0x180027fdb  mov     r9d, eax
0x180027fde  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180027fe5  call    WPP_SF_d
0x180027fea  mov     eax, dword ptr [rbp+57h+var_78]
0x180027fed  cmp     eax, 5
0x180027ff0  jz      short loc_180027FF7
0x180027ff2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180027ff7  movsd   xmm0, [rbp+57h+var_78]
0x180027ffc  mov     ecx, [rbp+57h+var_70]
0x180027fff  movsd   qword ptr [rbx], xmm0
0x180028003  mov     [rbx+8], ecx
0x180028006  mov     dword ptr [rbx+0Ch], 0C0000022h
0x18002800d  jmp     short loc_180028088
0x18002800f  mov     eax, esi
0x180028011  cmp     eax, [rbp+57h+var_C0.ResultListLength]
0x180028014  jnb     short loc_180028076
0x180028016  mov     edi, eax
0x180028018  mov     r9d, dword ptr [rbp+rdi*4+57h+var_78]
0x18002801d  test    r9d, r9d
0x180028020  jnz     short loc_180028027
0x180028022  add     eax, r14d
0x180028025  jmp     short loc_180028011
0x180028027  mov     rcx, cs:WPP_GLOBAL_Control
0x18002802e  lea     rdx, WPP_GLOBAL_Control
0x180028035  cmp     rcx, rdx
0x180028038  jz      short loc_180028059
0x18002803a  test    [rcx+1Ch], r14b
0x18002803e  jz      short loc_180028059
0x180028040  mov     rcx, [rcx+10h]
0x180028044  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002804b  mov     edx, 0Bh
0x180028050  mov     dword ptr [rsp+110h+pSecurityDescriptor], eax
0x180028054  call    WPP_SF_Dd
0x180028059  cmp     dword ptr [rbp+rdi*4+57h+var_78], 5
0x18002805e  jz      short loc_180028065
0x180028060  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028065  movsd   xmm0, [rbp+57h+var_78]
0x18002806a  mov     eax, [rbp+57h+var_70]
0x18002806d  movsd   qword ptr [rbx], xmm0
0x180028071  mov     [rbx+8], eax
0x180028074  jmp     short loc_180028006
0x180028076  movsd   xmm0, [rbp+57h+var_78]
0x18002807b  mov     eax, [rbp+57h+var_70]
0x18002807e  movsd   qword ptr [rbx], xmm0
0x180028082  mov     [rbx+8], eax
0x180028085  mov     [rbx+0Ch], esi
0x180028088  mov     rax, rbx
0x18002808b  mov     rcx, [rbp+57h+var_28]
0x18002808f  xor     rcx, rsp; StackCookie
0x180028092  call    __security_check_cookie
0x180028097  add     rsp, 0F0h
0x18002809e  pop     r14
0x1800280a0  pop     rdi
0x1800280a1  pop     rsi
0x1800280a2  pop     rbx
0x1800280a3  pop     rbp
0x1800280a4  retn
```
