# KdcPerformA2AAccessCheck(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_KDC_AUTHZ_INFO *,uchar *,long *)

- ea: `0x18002daac`
- end: `0x18002dc2c`
- name: `?KdcPerformA2AAccessCheck@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_KDC_AUTHZ_INFO@@PEAEPEAJ@Z`
- size: `384`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, struct _KDC_AUTHZ_INFO *, unsigned __int8 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024ffc`

## callees

- `0x1800101ec`
- `0x18002daac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbd6`
- `ntdll!RtlEqualSid` at `0x18002db24`
- `ntdll!RtlEqualSid` at `0x18002db24`
- `AUTHZ!AuthzAccessCheck` at `0x18002dbb3`
- `AUTHZ!AuthzAccessCheck` at `0x18002dbb3`

## pseudocode

```c
__int64 __fastcall KdcPerformA2AAccessCheck(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        struct _KDC_AUTHZ_INFO *a2,
        unsigned __int8 *a3,
        int *a4)
{
  unsigned int i; // ebx
  DWORD LastError; // eax
  __int64 result; // rax
  __int128 v11; // [rsp+50h] [rbp-29h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-19h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+80h] [rbp+7h] BYREF
  int v14; // [rsp+E0h] [rbp+67h] BYREF
  int v15; // [rsp+F8h] [rbp+7Fh] BYREF

  v15 = 5;
  pRequest.OptionalArguments = 0;
  v14 = 0;
  *a4 = 0;
  memset(&pReply, 0, sizeof(pReply));
  memset(&pRequest, 0, 32);
  v11 = 0;
  if ( hAuthzClientContext )
  {
    for ( i = 0; i < *((_DWORD *)a2 + 2); ++i )
    {
      if ( RtlEqualSid(*(PSID *)(*(_QWORD *)a2 + 16LL * i), GlobalOtherOrganizationSid) )
      {
        LODWORD(v11) = 0;
        pRequest.DesiredAccess = 256;
        *((_QWORD *)&v11 + 1) = &GUID_A_SECURED_FOR_CROSS_ORGANIZATION;
        pRequest.ObjectTypeListLength = 1;
        pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)&v11;
        pRequest.OptionalArguments = 0;
        pReply.GrantedAccessMask = (PACCESS_MASK)&v14;
        pRequest.PrincipalSelfSid = 0;
        pReply.Error = (PDWORD)&v15;
        pReply.ResultListLength = 1;
        if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, a3, 0, 0, &pReply, 0) )
        {
          if ( !*pReply.Error )
            return 0;
        }
        else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
        }
        result = 12;
        *a4 = -1073740781;
        return result;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002daac  mov     [rsp-8+arg_8], rbx
0x18002dab1  push    rbp
0x18002dab2  push    rsi
0x18002dab3  push    rdi
0x18002dab4  push    r14
0x18002dab6  push    r15
0x18002dab8  lea     rbp, [rsp-37h]
0x18002dabd  sub     rsp, 0B0h
0x18002dac4  xor     eax, eax
0x18002dac6  mov     [rbp+57h+arg_18], 5
0x18002dacd  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x18002dad1  xorps   xmm0, xmm0
0x18002dad4  mov     [rbp+57h+arg_0], eax
0x18002dad7  xorps   xmm1, xmm1
0x18002dada  mov     [r9], eax
0x18002dadd  mov     rdi, r9
0x18002dae0  mov     r15, r8
0x18002dae3  mov     rsi, rdx
0x18002dae6  mov     r14, rcx
0x18002dae9  movups  xmmword ptr [rbp+57h+var_70.ResultListLength], xmm0
0x18002daed  movups  xmmword ptr [rbp+57h+var_70.SaclEvaluationResults], xmm0
0x18002daf1  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm1
0x18002daf5  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm1
0x18002daf9  movups  [rbp+57h+var_80], xmm0
0x18002dafd  test    rcx, rcx
0x18002db00  jz      loc_18002DC13
0x18002db06  xor     ebx, ebx
0x18002db08  cmp     ebx, [rsi+8]
0x18002db0b  jnb     loc_18002DC13
0x18002db11  mov     rcx, [rsi]
0x18002db14  mov     rdx, cs:?GlobalOtherOrganizationSid@@3PEAXEA; Sid2
0x18002db1b  mov     eax, ebx
0x18002db1d  add     rax, rax
0x18002db20  mov     rcx, [rcx+rax*8]; Sid1
0x18002db24  call    cs:__imp_RtlEqualSid
0x18002db2a  test    al, al
0x18002db2c  jnz     short loc_18002DB32
0x18002db2e  inc     ebx
0x18002db30  jmp     short loc_18002DB08
0x18002db32  xor     eax, eax
0x18002db34  mov     [rsp+0D0h+phAccessCheckResults], 0; phAccessCheckResults
0x18002db3d  mov     dword ptr [rbp+57h+var_80], eax
0x18002db40  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002db44  lea     rax, ?GUID_A_SECURED_FOR_CROSS_ORGANIZATION@@3U_GUID@@A; _GUID GUID_A_SECURED_FOR_CROSS_ORGANIZATION
0x18002db4b  mov     [rbp+57h+pRequest.DesiredAccess], 100h
0x18002db52  mov     qword ptr [rbp+57h+var_80+8], rax
0x18002db56  xor     r9d, r9d; hAuditEvent
0x18002db59  lea     rax, [rbp+57h+var_80]
0x18002db5d  mov     [rbp+57h+pRequest.ObjectTypeListLength], 1
0x18002db64  mov     [rbp+57h+pRequest.ObjectTypeList], rax
0x18002db68  mov     rdx, r14; hAuthzClientContext
0x18002db6b  lea     rax, [rbp+57h+arg_0]
0x18002db6f  mov     [rbp+57h+pRequest.OptionalArguments], 0
0x18002db77  mov     [rbp+57h+var_70.GrantedAccessMask], rax
0x18002db7b  xor     ecx, ecx; Flags
0x18002db7d  lea     rax, [rbp+57h+arg_18]
0x18002db81  mov     [rbp+57h+pRequest.PrincipalSelfSid], 0
0x18002db89  mov     [rbp+57h+var_70.Error], rax
0x18002db8d  lea     rax, [rbp+57h+var_70]
0x18002db91  mov     [rsp+0D0h+pReply], rax; pReply
0x18002db96  mov     [rsp+0D0h+OptionalSecurityDescriptorCount], 0; OptionalSecurityDescriptorCount
0x18002db9e  mov     [rsp+0D0h+OptionalSecurityDescriptorArray], 0; OptionalSecurityDescriptorArray
0x18002dba7  mov     [rsp+0D0h+pSecurityDescriptor], r15; pSecurityDescriptor
0x18002dbac  mov     [rbp+57h+var_70.ResultListLength], 1
0x18002dbb3  call    cs:__imp_AuthzAccessCheck
0x18002dbb9  test    eax, eax
0x18002dbbb  jnz     short loc_18002DBFD
0x18002dbbd  mov     rax, cs:WPP_GLOBAL_Control
0x18002dbc4  lea     rcx, WPP_GLOBAL_Control
0x18002dbcb  cmp     rax, rcx
0x18002dbce  jz      short loc_18002DC06
0x18002dbd0  test    byte ptr [rax+1Ch], 1
0x18002dbd4  jz      short loc_18002DC06
0x18002dbd6  call    cs:__imp_GetLastError
0x18002dbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbe3  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002dbea  mov     edx, 6Ah ; 'j'
0x18002dbef  mov     r9d, eax
0x18002dbf2  mov     rcx, [rcx+10h]
0x18002dbf6  call    WPP_SF_d
0x18002dbfb  jmp     short loc_18002DC06
0x18002dbfd  mov     rax, [rbp+57h+var_70.Error]
0x18002dc01  cmp     dword ptr [rax], 0
0x18002dc04  jz      short loc_18002DC13
0x18002dc06  mov     eax, 0Ch
0x18002dc0b  mov     dword ptr [rdi], 0C0000413h
0x18002dc11  jmp     short loc_18002DC15
0x18002dc13  xor     eax, eax
0x18002dc15  mov     rbx, [rsp+0D0h+arg_8]
0x18002dc1d  add     rsp, 0B0h
0x18002dc24  pop     r15
0x18002dc26  pop     r14
0x18002dc28  pop     rdi
0x18002dc29  pop     rsi
0x18002dc2a  pop     rbp
0x18002dc2b  retn
```
