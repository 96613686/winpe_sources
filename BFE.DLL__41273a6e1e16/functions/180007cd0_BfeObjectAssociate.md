# BfeObjectAssociate

- ea: `0x180007cd0`
- end: `0x1800083f4`
- name: `BfeObjectAssociate`
- size: `1828`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800065d0`
- `0x180006ed0`
- `0x1800079f8`
- `0x18002e2f0`
- `0x18002f8c8`
- `0x18002fd34`
- `0x1800300c0`

## callees

- `0x180007cd0`
- `0x180008400`
- `0x1800084ec`
- `0x180008570`
- `0x180008868`
- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x1800133a0`
- `0x1800135ac`
- `0x1800197d0`
- `0x18002c5dc`
- `0x18003a7a0`
- `0x180047c1c`
- `0x18004fb50`
- `0x1800560f8`
- `0x1800592f4`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008317`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000806f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000806f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800083dc`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800083dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008247`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d59`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007daf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d59`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007d8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007daf`
- `AUTHZ!AuthzAccessCheck` at `0x180007f27`
- `AUTHZ!AuthzAccessCheck` at `0x180007f27`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007ed2`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007ed2`

## string_xrefs

- `0x180007e1a`: `BfeAccessCheck`
- `0x18000827c`: `BfeAccessCheckFromContext`
- `0x1800082ae`: `BfeAccessCheckFromContext`
- `0x18000809a`: `BfeObjectAssocCreate`
- `0x180008256`: `AuthzAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeObjectAssociate(int a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  char *v8; // r14
  __int64 *Value; // rax
  __int64 v10; // rax
  AUTHZ_CLIENT_CONTEXT_HANDLE v11; // r15
  __int64 *v12; // rax
  __int64 v13; // rax
  _DWORD *v14; // rax
  __int64 v15; // r13
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rcx
  int v19; // r8d
  __int64 v21; // rcx
  __int64 LastError; // r8
  _DWORD *v23; // rax
  __int64 v24; // rcx
  _DWORD *v25; // r15
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rdi
  __int64 v32; // rax
  int v33; // r8d
  __int64 v34; // rax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-71h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-69h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-49h] BYREF
  int v39; // [rsp+88h] [rbp-41h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v41[16]; // [rsp+B8h] [rbp-11h] BYREF
  const char *v42; // [rsp+C8h] [rbp-1h]
  __int64 v43; // [rsp+D0h] [rbp+7h]
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+D8h] [rbp+Fh]
  __int64 v45; // [rsp+E0h] [rbp+17h]

  if ( !a2 || !*a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 || !*a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v6 = a2;
  if ( (a1 & 2) == 0 )
  {
    v6 = a3;
    a3 = a2;
  }
  v7 = 0;
  v8 = (char *)v6[14];
  pSecurityDescriptor = v8;
  EnterCriticalSection(&gBfeAuthz);
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( Value )
  {
    v10 = *Value;
    if ( v10 )
    {
      v11 = *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v10 + 48);
      if ( v11 )
      {
        v12 = (__int64 *)TlsGetValue(gBfeContextComponent);
        if ( !v12 || (v13 = *v12) == 0 || !*(_DWORD *)(*(_QWORD *)(v13 + 16) + 64LL) )
        {
          v14 = TlsGetValue(gBfeContextComponent);
          if ( !v14 || !v14[6] )
          {
            v15 = v8 ? (__int64)(v8 - 28) : 0LL;
            v16 = BfeAccessCheckFindResult(v15);
            v17 = v16;
            if ( !v16 || (*(_BYTE *)(v16 + 32) & 2) == 0 )
            {
              AccessMask = 2;
              v39 = 0;
              v36 = 5;
              memset(&pRequest, 0, sizeof(pRequest));
              *(&pReply.ResultListLength + 1) = 0;
              pReply.SaclEvaluationResults = 0;
              MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
              pRequest.DesiredAccess = AccessMask;
              pReply.GrantedAccessMask = (PACCESS_MASK)&v39;
              pReply.ResultListLength = 1;
              pReply.Error = &v36;
              if ( AuthzAccessCheck(0, v11, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
              {
                LastError = v36;
                if ( !v36 )
                {
LABEL_31:
                  if ( !v7 )
                  {
                    if ( v17 )
                      *(_DWORD *)(v17 + 32) |= 2u;
                    else
                      BfeAccessCheckCacheResult(v15, 2);
                  }
                  goto LABEL_20;
                }
              }
              else
              {
                LastError = GetLastError();
              }
              v7 = WfpReportSysErrorAsWinError(v21, "AuthzAccessCheck", LastError);
              if ( v7 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v33, 0, (__int64)"BfeAccessCheckFromContext", v7);
                }
                if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
                {
                  v42 = "BfeAccessCheckFromContext";
                  LODWORD(pSecurityDescriptor) = v7;
                  p_pSecurityDescriptor = &pSecurityDescriptor;
                  v43 = 26;
                  v45 = 4;
                  McGenEventWrite_EtwEventWriteTransfer(
                    (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
                    (unsigned int)WFP_USERMODE_ERROR,
                    v33,
                    3,
                    (__int64)v41);
                  LeaveCriticalSection(&gBfeAuthz);
LABEL_21:
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v19, 0, (__int64)"BfeAccessCheck", v7);
                  }
                  if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
                  {
                    LODWORD(pSecurityDescriptor) = v7;
                    p_pSecurityDescriptor = &pSecurityDescriptor;
                    v42 = "BfeAccessCheck";
                    v43 = 15;
                    v45 = 4;
                    McGenEventWrite_EtwEventWriteTransfer(
                      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
                      (unsigned int)WFP_USERMODE_ERROR,
                      v19,
                      3,
                      (__int64)v41);
                  }
                  goto LABEL_26;
                }
              }
              goto LABEL_31;
            }
          }
        }
      }
    }
  }
LABEL_20:
  LeaveCriticalSection(&gBfeAuthz);
  if ( v7 )
    goto LABEL_21;
  if ( a3 == v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v19, 0, (__int64)"BfeObjectAssociate", 50);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      LODWORD(pSecurityDescriptor) = 50;
      p_pSecurityDescriptor = &pSecurityDescriptor;
      v42 = "BfeObjectAssociate";
      v43 = 19;
      v45 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v19,
        3,
        (__int64)v41);
    }
    v7 = -2147024846;
    goto LABEL_26;
  }
  if ( !a3 || !*a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LOBYTE(v18) = (a3[1] & 2) != 0;
  if ( ((unsigned __int8)v18 & ((a1 & 4) == 0)) != 0 )
  {
    if ( *a3 <= *v6 )
      goto LABEL_88;
    if ( !(unsigned int)BfeObjectIsDurable(v6) )
    {
      v29 = 2150760470LL;
      goto LABEL_89;
    }
  }
  else if ( !v6 )
  {
LABEL_45:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_46;
  }
  if ( !*v6 )
    goto LABEL_45;
LABEL_46:
  if ( v6[15] )
  {
    if ( !(unsigned int)BfeObjectIsValid(a3) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v30 = a3[15];
    if ( v30 )
      v31 = *(_QWORD *)(v30 + 16);
    else
      v31 = 0;
    if ( !(unsigned int)BfeObjectIsValid(v6) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v32 = v6[15];
    v18 = v32 ? *(_QWORD *)(v32 + 16) : 0LL;
    if ( v31 != v18 )
    {
      v29 = 2150760460LL;
      goto LABEL_89;
    }
  }
  if ( (a1 & 1) != 0 && (v6[1] & 1) != 0 )
  {
LABEL_88:
    v29 = 50;
LABEL_89:
    v7 = WfpReportSysErrorAsWinError(v18, "BfeObjectAssociate", v29);
    if ( !v7 )
      return v7;
    goto LABEL_26;
  }
  pSecurityDescriptor = 0;
  if ( !a3 || !*a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v6 || !*v6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v25 = pSecurityDescriptor;
    v7 = WfpMemAlloc25B(0x38u);
  }
  else
  {
    v23 = HeapAlloc(gWfpHeap, 0, 0x38u);
    v25 = v23;
    if ( v23 )
    {
      v7 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v23));
    }
    else
    {
      v34 = WfpReportSysErrorAsNtStatus(v24, "HeapAlloc", 3221225495LL);
      v7 = v34;
      if ( v34 )
        WfpReportError(v34, "WfpMemAlloc");
    }
  }
  if ( v7 )
  {
    WfpReportError(v7, "BfeObjectAssocCreate");
LABEL_26:
    WfpReportError(v7, "BfeObjectAssociate");
    return v7;
  }
  v25[12] = a1;
  BfeIterateAssociationEnterLock();
  *(_QWORD *)v25 = a3;
  v26 = a3 + 10;
  v27 = (_QWORD *)v26[1];
  if ( (_QWORD *)*v27 != v26
    || (*((_QWORD *)v25 + 2) = v27,
        *((_QWORD *)v25 + 1) = v26,
        *v27 = v25 + 2,
        v26[1] = v25 + 2,
        *((_QWORD *)v25 + 3) = v6,
        v28 = (_QWORD *)v6[13],
        (_QWORD *)*v28 != v6 + 12) )
  {
    __fastfail(3u);
  }
  *((_QWORD *)v25 + 4) = v6 + 12;
  *((_QWORD *)v25 + 5) = v28;
  *v28 = v25 + 8;
  v6[13] = v25 + 8;
  BfeIterateAssociationLeaveLock();
  if ( (a1 & 1) != 0 )
    BfeObjectMakeGarbageCollected(v6);
  return v7;
}

```

## disassembly

```asm
0x180007cd0  push    rbp
0x180007cd2  push    rbx
0x180007cd3  push    rsi
0x180007cd4  push    rdi
0x180007cd5  push    r12
0x180007cd7  push    r14
0x180007cd9  push    r15
0x180007cdb  lea     rbp, [rsp-27h]
0x180007ce0  sub     rsp, 0F0h
0x180007ce7  mov     rax, cs:__security_cookie
0x180007cee  xor     rax, rsp
0x180007cf1  mov     [rbp+57h+var_38], rax
0x180007cf5  mov     rbx, r8
0x180007cf8  mov     rdi, rdx
0x180007cfb  mov     r12d, ecx
0x180007cfe  test    rdx, rdx
0x180007d01  jz      short loc_180007D09
0x180007d03  cmp     qword ptr [rdx], 0
0x180007d07  jnz     short loc_180007D0E
0x180007d09  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(from)")
0x180007d0e  test    rbx, rbx
0x180007d11  jz      short loc_180007D19
0x180007d13  cmp     qword ptr [rbx], 0
0x180007d17  jnz     short loc_180007D1E
0x180007d19  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(to)")
0x180007d1e  bt      r12d, 1
0x180007d23  mov     [rsp+120h+arg_0], r13
0x180007d2b  mov     rsi, rdi
0x180007d2e  lea     rcx, gBfeAuthz; lpCriticalSection
0x180007d35  cmovnb  rsi, rbx
0x180007d39  cmovnb  rbx, rdi
0x180007d3d  xor     edi, edi
0x180007d3f  mov     r14, [rsi+70h]
0x180007d43  mov     [rbp+57h+var_D0], r14
0x180007d47  call    cs:__imp_EnterCriticalSection
0x180007d4e  nop     dword ptr [rax+rax+00h]
0x180007d53  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180007d59  call    cs:__imp_TlsGetValue
0x180007d60  nop     dword ptr [rax+rax+00h]
0x180007d65  lea     r15, WPP_GLOBAL_Control
0x180007d6c  test    rax, rax
0x180007d6f  jz      loc_180007DF7
0x180007d75  mov     rax, [rax]
0x180007d78  test    rax, rax
0x180007d7b  jz      short loc_180007DF7
0x180007d7d  mov     r15, [rax+30h]
0x180007d81  test    r15, r15
0x180007d84  jz      short loc_180007DF0
0x180007d86  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180007d8c  call    cs:__imp_TlsGetValue
0x180007d93  nop     dword ptr [rax+rax+00h]
0x180007d98  test    rax, rax
0x180007d9b  jz      short loc_180007DA9
0x180007d9d  mov     rax, [rax]
0x180007da0  test    rax, rax
0x180007da3  jnz     loc_180007F73
0x180007da9  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180007daf  call    cs:__imp_TlsGetValue
0x180007db6  nop     dword ptr [rax+rax+00h]
0x180007dbb  test    rax, rax
0x180007dbe  jz      short loc_180007DC5
0x180007dc0  cmp     [rax+18h], edi
0x180007dc3  jnz     short loc_180007DF0
0x180007dc5  test    r14, r14
0x180007dc8  jz      loc_180007E95
0x180007dce  lea     r13, [r14-1Ch]
0x180007dd2  mov     rcx, r13
0x180007dd5  call    BfeAccessCheckFindResult
0x180007dda  mov     r14, rax
0x180007ddd  test    rax, rax
0x180007de0  jz      loc_180007E9D
0x180007de6  test    byte ptr [rax+20h], 2
0x180007dea  jz      loc_180007E9D
0x180007df0  lea     r15, WPP_GLOBAL_Control
0x180007df7  lea     rcx, gBfeAuthz; lpCriticalSection
0x180007dfe  call    cs:__imp_LeaveCriticalSection
0x180007e05  nop     dword ptr [rax+rax+00h]
0x180007e0a  test    rdi, rdi
0x180007e0d  jz      loc_180007FD8
0x180007e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e1a  lea     rbx, aBfeaccesscheck; "BfeAccessCheck"
0x180007e21  cmp     rcx, r15
0x180007e24  jz      short loc_180007E4C
0x180007e26  cmp     byte ptr [rcx+19h], 2
0x180007e2a  jb      short loc_180007E4C
0x180007e2c  test    byte ptr [rcx+1Ch], 1
0x180007e30  jz      short loc_180007E4C
0x180007e32  mov     rcx, [rcx+10h]
0x180007e36  mov     edx, 1Ah
0x180007e3b  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x180007e3f  xor     r9d, r9d
0x180007e42  mov     [rsp+120h+pSecurityDescriptor], rbx
0x180007e47  call    WPP_SF_Ssd
0x180007e4c  cmp     cs:gWfpLogUserModeErrors, 0
0x180007e53  jnz     loc_180007F85
0x180007e59  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x180007e60  mov     rdx, rbx
0x180007e63  mov     rcx, rdi
0x180007e66  call    WfpReportError
0x180007e6b  mov     r13, [rsp+120h+arg_0]
0x180007e73  mov     rax, rdi
0x180007e76  mov     rcx, [rbp+57h+var_38]
0x180007e7a  xor     rcx, rsp; StackCookie
0x180007e7d  call    __security_check_cookie
0x180007e82  add     rsp, 0F0h
0x180007e89  pop     r15
0x180007e8b  pop     r14
0x180007e8d  pop     r12
0x180007e8f  pop     rdi
0x180007e90  pop     rsi
0x180007e91  pop     rbx
0x180007e92  pop     rbp
0x180007e93  retn
0x180007e95  xor     r13d, r13d
0x180007e98  jmp     loc_180007DD2
0x180007e9d  xorps   xmm0, xmm0
0x180007ea0  mov     [rbp+57h+AccessMask], 2
0x180007ea7  xor     eax, eax
0x180007ea9  mov     [rbp+57h+var_98], edi
0x180007eac  lea     rdx, GenericMapping; GenericMapping
0x180007eb3  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180007eb7  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180007ebb  mov     [rbp+57h+var_C8], 5
0x180007ec2  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180007ec6  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180007eca  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x180007ece  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x180007ed2  call    cs:__imp_MapGenericMask
0x180007ed9  nop     dword ptr [rax+rax+00h]
0x180007ede  mov     eax, [rbp+57h+AccessMask]
0x180007ee1  lea     r8, [rbp+57h+pRequest]; pRequest
0x180007ee5  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x180007ee8  xor     r9d, r9d; hAuditEvent
0x180007eeb  mov     [rsp+120h+phAccessCheckResults], rdi; phAccessCheckResults
0x180007ef0  lea     rax, [rbp+57h+var_98]
0x180007ef4  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x180007ef8  mov     rdx, r15; hAuthzClientContext
0x180007efb  lea     rax, [rbp+57h+var_C8]
0x180007eff  mov     [rbp+57h+var_C0.ResultListLength], 1
0x180007f06  mov     [rbp+57h+var_C0.Error], rax
0x180007f0a  xor     ecx, ecx; Flags
0x180007f0c  lea     rax, [rbp+57h+var_C0]
0x180007f10  mov     [rsp+120h+pReply], rax; pReply
0x180007f15  mov     rax, [rbp+57h+var_D0]
0x180007f19  mov     [rsp+120h+OptionalSecurityDescriptorCount], edi; OptionalSecurityDescriptorCount
0x180007f1d  mov     [rsp+120h+OptionalSecurityDescriptorArray], rdi; OptionalSecurityDescriptorArray
0x180007f22  mov     [rsp+120h+pSecurityDescriptor], rax; pSecurityDescriptor
0x180007f27  call    cs:__imp_AuthzAccessCheck
0x180007f2e  nop     dword ptr [rax+rax+00h]
0x180007f33  test    eax, eax
0x180007f35  jz      loc_180008247
0x180007f3b  mov     r8d, [rbp+57h+var_C8]
0x180007f3f  test    r8d, r8d
0x180007f42  jnz     loc_180008256
0x180007f48  lea     r15, WPP_GLOBAL_Control
0x180007f4f  test    rdi, rdi
0x180007f52  jnz     loc_180007DF7
0x180007f58  test    r14, r14
0x180007f5b  jnz     loc_180008328
0x180007f61  mov     edx, 2
0x180007f66  mov     rcx, r13
0x180007f69  call    BfeAccessCheckCacheResult
0x180007f6e  jmp     loc_180007DF7
0x180007f73  mov     rax, [rax+10h]
0x180007f77  cmp     [rax+40h], edi
0x180007f7a  jz      loc_180007DA9
0x180007f80  jmp     loc_180007DF0
0x180007f85  test    cs:byte_1800F6115, 1
0x180007f8c  jz      loc_180007E59
0x180007f92  lea     rax, [rbp+57h+var_D0]
0x180007f96  mov     dword ptr [rbp+57h+var_D0], edi
0x180007f99  mov     [rbp+57h+var_48], rax
0x180007f9d  lea     rdx, WFP_USERMODE_ERROR
0x180007fa4  lea     rax, [rbp+57h+var_68]
0x180007fa8  mov     [rbp+57h+var_58], rbx
0x180007fac  mov     r9d, 3
0x180007fb2  mov     [rsp+120h+pSecurityDescriptor], rax
0x180007fb7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180007fbe  mov     [rbp+57h+var_50], 0Fh
0x180007fc6  mov     [rbp+57h+var_40], 4
0x180007fce  call    McGenEventWrite_EtwEventWriteTransfer
0x180007fd3  jmp     loc_180007E59
0x180007fd8  cmp     rbx, rsi
0x180007fdb  jz      loc_180008135
0x180007fe1  test    rbx, rbx
0x180007fe4  jz      short loc_180007FEC
0x180007fe6  cmp     qword ptr [rbx], 0
0x180007fea  jnz     short loc_180007FF1
0x180007fec  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180007ff1  test    byte ptr [rbx+8], 2
0x180007ff5  setnz   cl
0x180007ff8  test    r12b, 4
0x180007ffc  setz    al
0x180007fff  test    al, cl
0x180008001  jnz     loc_180008170
0x180008007  test    rsi, rsi
0x18000800a  jz      short loc_180008012
0x18000800c  cmp     qword ptr [rsi], 0
0x180008010  jnz     short loc_180008017
0x180008012  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180008017  cmp     qword ptr [rsi+78h], 0
0x18000801c  jnz     loc_1800081C4
0x180008022  mov     r14d, r12d
0x180008025  and     r14d, 1
0x180008029  jnz     loc_180008217
0x18000802f  mov     [rbp+57h+var_D0], 0
0x180008037  test    rbx, rbx
0x18000803a  jz      short loc_180008042
0x18000803c  cmp     qword ptr [rbx], 0
0x180008040  jnz     short loc_180008047
0x180008042  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(from)")
0x180008047  test    rsi, rsi
0x18000804a  jz      short loc_180008052
0x18000804c  cmp     qword ptr [rsi], 0
0x180008050  jnz     short loc_180008057
0x180008052  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(to)")
0x180008057  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000805c  xor     edx, edx; dwFlags
0x18000805e  test    eax, eax
0x180008060  jnz     short loc_1800080AE
0x180008062  mov     rcx, cs:gWfpHeap; hHeap
0x180008069  mov     r8d, 38h ; '8'; dwBytes
0x18000806f  call    cs:__imp_HeapAlloc
0x180008076  nop     dword ptr [rax+rax+00h]
0x18000807b  mov     r15, rax
0x18000807e  test    rax, rax
0x180008081  jz      loc_180008332
0x180008087  xor     edi, edi
0x180008089  cmp     cs:gWfpTrackHeapBytes, edi
0x18000808f  jnz     loc_1800083D0
0x180008095  test    rdi, rdi
0x180008098  jz      short loc_1800080C5
0x18000809a  lea     rdx, aBfeobjectassoc; "BfeObjectAssocCreate"
0x1800080a1  mov     rcx, rdi
0x1800080a4  call    WfpReportError
0x1800080a9  jmp     loc_180007E59
0x1800080ae  lea     r8, [rbp+57h+var_D0]
0x1800080b2  mov     ecx, 38h ; '8'; dwBytes
0x1800080b7  call    WfpMemAlloc25B
0x1800080bc  mov     r15, [rbp+57h+var_D0]
0x1800080c0  mov     rdi, rax
0x1800080c3  jmp     short loc_180008095
0x1800080c5  mov     [r15+30h], r12d
0x1800080c9  call    BfeIterateAssociationEnterLock
0x1800080ce  mov     [r15], rbx
0x1800080d1  add     rbx, 50h ; 'P'
0x1800080d5  mov     rcx, [rbx+8]
0x1800080d9  cmp     [rcx], rbx
0x1800080dc  jz      short loc_1800080E5
0x1800080de  mov     ecx, 3
0x1800080e3  int     29h; Win8: RtlFailFast(ecx)
0x1800080e5  mov     [r15+10h], rcx
0x1800080e9  lea     rax, [r15+8]
0x1800080ed  mov     [rax], rbx
0x1800080f0  mov     [rcx], rax
0x1800080f3  lea     rcx, [rsi+60h]
0x1800080f7  mov     [rbx+8], rax
0x1800080fb  mov     [r15+18h], rsi
0x1800080ff  mov     rdx, [rcx+8]
0x180008103  cmp     [rdx], rcx
0x180008106  jnz     short loc_1800080DE
0x180008108  lea     rax, [r15+20h]
0x18000810c  mov     [rax], rcx
0x18000810f  mov     [rax+8], rdx
0x180008113  mov     [rdx], rax
0x180008116  mov     [rcx+8], rax
0x18000811a  call    BfeIterateAssociationLeaveLock
0x18000811f  test    r14d, r14d
0x180008122  jz      loc_180007E6B
0x180008128  mov     rcx, rsi
0x18000812b  call    BfeObjectMakeGarbageCollected
0x180008130  jmp     loc_180007E6B
0x180008135  mov     rcx, cs:WPP_GLOBAL_Control
0x18000813c  cmp     rcx, r15
0x18000813f  jz      short loc_180008147
0x180008141  cmp     byte ptr [rcx+19h], 2
0x180008145  jnb     short loc_180008197
0x180008147  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x18000814e  cmp     cs:gWfpLogUserModeErrors, 0
0x180008155  jz      short loc_180008164
0x180008157  test    cs:byte_1800F6115, 1
0x18000815e  jnz     loc_180008372
0x180008164  mov     rdi, 0FFFFFFFF80070032h
0x18000816b  jmp     loc_180007E60
0x180008170  mov     rax, [rsi]
0x180008173  cmp     [rbx], rax
0x180008176  jbe     loc_180008221
0x18000817c  mov     rcx, rsi
0x18000817f  call    BfeObjectIsDurable
0x180008184  test    eax, eax
0x180008186  jnz     loc_18000800C
0x18000818c  mov     r8d, 80320016h
0x180008192  jmp     loc_180008227
0x180008197  test    byte ptr [rcx+1Ch], 1
0x18000819b  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x1800081a2  jz      short loc_18000814E
0x1800081a4  mov     rcx, [rcx+10h]
0x1800081a8  mov     edx, 17h
0x1800081ad  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], 32h ; '2'
0x1800081b5  xor     r9d, r9d
  ... truncated ...
```
