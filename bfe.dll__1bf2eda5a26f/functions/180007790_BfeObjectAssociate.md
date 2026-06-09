# BfeObjectAssociate

- ea: `0x180007790`
- end: `0x180007e6d`
- name: `BfeObjectAssociate`
- size: `1757`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800060f0`
- `0x1800069d0`
- `0x1800074cc`
- `0x18002c908`
- `0x18002de40`
- `0x18002e280`
- `0x18002e60c`

## callees

- `0x180007790`
- `0x180007e80`
- `0x180007f6c`
- `0x180007fe0`
- `0x1800082a4`
- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180012950`
- `0x180012b54`
- `0x180018b74`
- `0x18002ae3c`
- `0x18003bfe8`
- `0x180045dc0`
- `0x18004e230`
- `0x1800542bc`
- `0x1800575c4`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007807`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007807`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b00`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007e5b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007813`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000783c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007813`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000783c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007859`
- `AUTHZ!AuthzAccessCheck` at `0x1800079be`
- `AUTHZ!AuthzAccessCheck` at `0x1800079be`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000796f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000796f`

## string_xrefs

- `0x1800078b8`: `BfeAccessCheck`
- `0x180007d01`: `BfeAccessCheckFromContext`
- `0x180007d33`: `BfeAccessCheckFromContext`
- `0x180007b25`: `BfeObjectAssocCreate`
- `0x180007cdb`: `AuthzAccessCheck`

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
  EnterCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[131]);
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
                if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
                  LeaveCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[131]);
LABEL_21:
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v19, 0, (__int64)"BfeAccessCheck", v7);
                  }
                  if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
  LeaveCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[131]);
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
    if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
0x180007790  push    rbp
0x180007792  push    rbx
0x180007793  push    rsi
0x180007794  push    rdi
0x180007795  push    r12
0x180007797  push    r14
0x180007799  push    r15
0x18000779b  lea     rbp, [rsp-27h]
0x1800077a0  sub     rsp, 0F0h
0x1800077a7  mov     rax, cs:__security_cookie
0x1800077ae  xor     rax, rsp
0x1800077b1  mov     [rbp+57h+var_38], rax
0x1800077b5  mov     rbx, r8
0x1800077b8  mov     rdi, rdx
0x1800077bb  mov     r12d, ecx
0x1800077be  test    rdx, rdx
0x1800077c1  jz      short loc_1800077C9
0x1800077c3  cmp     qword ptr [rdx], 0
0x1800077c7  jnz     short loc_1800077CE
0x1800077c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800077ce  test    rbx, rbx
0x1800077d1  jz      short loc_1800077D9
0x1800077d3  cmp     qword ptr [rbx], 0
0x1800077d7  jnz     short loc_1800077DE
0x1800077d9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800077de  bt      r12d, 1
0x1800077e3  mov     [rsp+120h+arg_0], r13
0x1800077eb  mov     rsi, rdi
0x1800077ee  lea     rcx, qword_1800F2668+418h; lpCriticalSection
0x1800077f5  cmovnb  rsi, rbx
0x1800077f9  cmovnb  rbx, rdi
0x1800077fd  xor     edi, edi
0x1800077ff  mov     r14, [rsi+70h]
0x180007803  mov     [rbp+57h+var_D0], r14
0x180007807  call    cs:__imp_EnterCriticalSection
0x18000780d  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180007813  call    cs:__imp_TlsGetValue
0x180007819  lea     r15, WPP_GLOBAL_Control
0x180007820  test    rax, rax
0x180007823  jz      short loc_18000789B
0x180007825  mov     rax, [rax]
0x180007828  test    rax, rax
0x18000782b  jz      short loc_18000789B
0x18000782d  mov     r15, [rax+30h]
0x180007831  test    r15, r15
0x180007834  jz      short loc_180007894
0x180007836  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000783c  call    cs:__imp_TlsGetValue
0x180007842  test    rax, rax
0x180007845  jz      short loc_180007853
0x180007847  mov     rax, [rax]
0x18000784a  test    rax, rax
0x18000784d  jnz     loc_180007A04
0x180007853  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180007859  call    cs:__imp_TlsGetValue
0x18000785f  test    rax, rax
0x180007862  jz      short loc_180007869
0x180007864  cmp     [rax+18h], edi
0x180007867  jnz     short loc_180007894
0x180007869  test    r14, r14
0x18000786c  jz      loc_180007932
0x180007872  lea     r13, [r14-1Ch]
0x180007876  mov     rcx, r13
0x180007879  call    BfeAccessCheckFindResult
0x18000787e  mov     r14, rax
0x180007881  test    rax, rax
0x180007884  jz      loc_18000793A
0x18000788a  test    byte ptr [rax+20h], 2
0x18000788e  jz      loc_18000793A
0x180007894  lea     r15, WPP_GLOBAL_Control
0x18000789b  lea     rcx, qword_1800F2668+418h; lpCriticalSection
0x1800078a2  call    cs:__imp_LeaveCriticalSection
0x1800078a8  test    rdi, rdi
0x1800078ab  jz      loc_180007A69
0x1800078b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078b8  lea     rbx, aBfeaccesscheck; "BfeAccessCheck"
0x1800078bf  cmp     rcx, r15
0x1800078c2  jz      short loc_1800078EA
0x1800078c4  cmp     byte ptr [rcx+19h], 2
0x1800078c8  jb      short loc_1800078EA
0x1800078ca  test    byte ptr [rcx+1Ch], 1
0x1800078ce  jz      short loc_1800078EA
0x1800078d0  mov     rcx, [rcx+10h]
0x1800078d4  mov     edx, 1Ah
0x1800078d9  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x1800078dd  xor     r9d, r9d
0x1800078e0  mov     [rsp+120h+pSecurityDescriptor], rbx
0x1800078e5  call    WPP_SF_Ssd
0x1800078ea  cmp     dword ptr cs:1800EF078h, 0
0x1800078f1  jnz     loc_180007A16
0x1800078f7  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x1800078fe  mov     rdx, rbx
0x180007901  mov     rcx, rdi
0x180007904  call    WfpReportError
0x180007909  mov     r13, [rsp+120h+arg_0]
0x180007911  mov     rax, rdi
0x180007914  mov     rcx, [rbp+57h+var_38]
0x180007918  xor     rcx, rsp; StackCookie
0x18000791b  call    __security_check_cookie
0x180007920  add     rsp, 0F0h
0x180007927  pop     r15
0x180007929  pop     r14
0x18000792b  pop     r12
0x18000792d  pop     rdi
0x18000792e  pop     rsi
0x18000792f  pop     rbx
0x180007930  pop     rbp
0x180007931  retn
0x180007932  xor     r13d, r13d
0x180007935  jmp     loc_180007876
0x18000793a  xorps   xmm0, xmm0
0x18000793d  mov     [rbp+57h+AccessMask], 2
0x180007944  xor     eax, eax
0x180007946  mov     [rbp+57h+var_98], edi
0x180007949  lea     rdx, GenericMapping; GenericMapping
0x180007950  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180007954  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180007958  mov     [rbp+57h+var_C8], 5
0x18000795f  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180007963  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180007967  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x18000796b  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x18000796f  call    cs:__imp_MapGenericMask
0x180007975  mov     eax, [rbp+57h+AccessMask]
0x180007978  lea     r8, [rbp+57h+pRequest]; pRequest
0x18000797c  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x18000797f  xor     r9d, r9d; hAuditEvent
0x180007982  mov     [rsp+120h+phAccessCheckResults], rdi; phAccessCheckResults
0x180007987  lea     rax, [rbp+57h+var_98]
0x18000798b  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x18000798f  mov     rdx, r15; hAuthzClientContext
0x180007992  lea     rax, [rbp+57h+var_C8]
0x180007996  mov     [rbp+57h+var_C0.ResultListLength], 1
0x18000799d  mov     [rbp+57h+var_C0.Error], rax
0x1800079a1  xor     ecx, ecx; Flags
0x1800079a3  lea     rax, [rbp+57h+var_C0]
0x1800079a7  mov     [rsp+120h+pReply], rax; pReply
0x1800079ac  mov     rax, [rbp+57h+var_D0]
0x1800079b0  mov     [rsp+120h+OptionalSecurityDescriptorCount], edi; OptionalSecurityDescriptorCount
0x1800079b4  mov     [rsp+120h+OptionalSecurityDescriptorArray], rdi; OptionalSecurityDescriptorArray
0x1800079b9  mov     [rsp+120h+pSecurityDescriptor], rax; pSecurityDescriptor
0x1800079be  call    cs:__imp_AuthzAccessCheck
0x1800079c4  test    eax, eax
0x1800079c6  jz      loc_180007CD2
0x1800079cc  mov     r8d, [rbp+57h+var_C8]
0x1800079d0  test    r8d, r8d
0x1800079d3  jnz     loc_180007CDB
0x1800079d9  lea     r15, WPP_GLOBAL_Control
0x1800079e0  test    rdi, rdi
0x1800079e3  jnz     loc_18000789B
0x1800079e9  test    r14, r14
0x1800079ec  jnz     loc_180007DA7
0x1800079f2  mov     edx, 2
0x1800079f7  mov     rcx, r13
0x1800079fa  call    BfeAccessCheckCacheResult
0x1800079ff  jmp     loc_18000789B
0x180007a04  mov     rax, [rax+10h]
0x180007a08  cmp     [rax+40h], edi
0x180007a0b  jz      loc_180007853
0x180007a11  jmp     loc_180007894
0x180007a16  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180007a1d  jz      loc_1800078F7
0x180007a23  lea     rax, [rbp+57h+var_D0]
0x180007a27  mov     dword ptr [rbp+57h+var_D0], edi
0x180007a2a  mov     [rbp+57h+var_48], rax
0x180007a2e  lea     rdx, WFP_USERMODE_ERROR
0x180007a35  lea     rax, [rbp+57h+var_68]
0x180007a39  mov     [rbp+57h+var_58], rbx
0x180007a3d  mov     r9d, 3
0x180007a43  mov     [rsp+120h+pSecurityDescriptor], rax
0x180007a48  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180007a4f  mov     [rbp+57h+var_50], 0Fh
0x180007a57  mov     [rbp+57h+var_40], 4
0x180007a5f  call    McGenEventWrite_EtwEventWriteTransfer
0x180007a64  jmp     loc_1800078F7
0x180007a69  cmp     rbx, rsi
0x180007a6c  jz      loc_180007BC0
0x180007a72  test    rbx, rbx
0x180007a75  jz      short loc_180007A7D
0x180007a77  cmp     qword ptr [rbx], 0
0x180007a7b  jnz     short loc_180007A82
0x180007a7d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007a82  test    byte ptr [rbx+8], 2
0x180007a86  setnz   cl
0x180007a89  test    r12b, 4
0x180007a8d  setz    al
0x180007a90  test    al, cl
0x180007a92  jnz     loc_180007BFB
0x180007a98  test    rsi, rsi
0x180007a9b  jz      short loc_180007AA3
0x180007a9d  cmp     qword ptr [rsi], 0
0x180007aa1  jnz     short loc_180007AA8
0x180007aa3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007aa8  cmp     qword ptr [rsi+78h], 0
0x180007aad  jnz     loc_180007C4F
0x180007ab3  mov     r14d, r12d
0x180007ab6  and     r14d, 1
0x180007aba  jnz     loc_180007CA2
0x180007ac0  mov     [rbp+57h+var_D0], 0
0x180007ac8  test    rbx, rbx
0x180007acb  jz      short loc_180007AD3
0x180007acd  cmp     qword ptr [rbx], 0
0x180007ad1  jnz     short loc_180007AD8
0x180007ad3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007ad8  test    rsi, rsi
0x180007adb  jz      short loc_180007AE3
0x180007add  cmp     qword ptr [rsi], 0
0x180007ae1  jnz     short loc_180007AE8
0x180007ae3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007ae8  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180007aed  xor     edx, edx; dwFlags
0x180007aef  test    eax, eax
0x180007af1  jnz     short loc_180007B39
0x180007af3  mov     rcx, cs:gWfpHeap; hHeap
0x180007afa  mov     r8d, 38h ; '8'; dwBytes
0x180007b00  call    cs:__imp_HeapAlloc
0x180007b06  mov     r15, rax
0x180007b09  test    rax, rax
0x180007b0c  jz      loc_180007DB1
0x180007b12  xor     edi, edi
0x180007b14  cmp     cs:gWfpTrackHeapBytes, edi
0x180007b1a  jnz     loc_180007E4F
0x180007b20  test    rdi, rdi
0x180007b23  jz      short loc_180007B50
0x180007b25  lea     rdx, aBfeobjectassoc; "BfeObjectAssocCreate"
0x180007b2c  mov     rcx, rdi
0x180007b2f  call    WfpReportError
0x180007b34  jmp     loc_1800078F7
0x180007b39  lea     r8, [rbp+57h+var_D0]
0x180007b3d  mov     ecx, 38h ; '8'; dwBytes
0x180007b42  call    WfpMemAlloc25B
0x180007b47  mov     r15, [rbp+57h+var_D0]
0x180007b4b  mov     rdi, rax
0x180007b4e  jmp     short loc_180007B20
0x180007b50  mov     [r15+30h], r12d
0x180007b54  call    BfeIterateAssociationEnterLock
0x180007b59  mov     [r15], rbx
0x180007b5c  add     rbx, 50h ; 'P'
0x180007b60  mov     rcx, [rbx+8]
0x180007b64  cmp     [rcx], rbx
0x180007b67  jz      short loc_180007B70
0x180007b69  mov     ecx, 3
0x180007b6e  int     29h; Win8: RtlFailFast(ecx)
0x180007b70  mov     [r15+10h], rcx
0x180007b74  lea     rax, [r15+8]
0x180007b78  mov     [rax], rbx
0x180007b7b  mov     [rcx], rax
0x180007b7e  lea     rcx, [rsi+60h]
0x180007b82  mov     [rbx+8], rax
0x180007b86  mov     [r15+18h], rsi
0x180007b8a  mov     rdx, [rcx+8]
0x180007b8e  cmp     [rdx], rcx
0x180007b91  jnz     short loc_180007B69
0x180007b93  lea     rax, [r15+20h]
0x180007b97  mov     [rax], rcx
0x180007b9a  mov     [rax+8], rdx
0x180007b9e  mov     [rdx], rax
0x180007ba1  mov     [rcx+8], rax
0x180007ba5  call    BfeIterateAssociationLeaveLock
0x180007baa  test    r14d, r14d
0x180007bad  jz      loc_180007909
0x180007bb3  mov     rcx, rsi
0x180007bb6  call    BfeObjectMakeGarbageCollected
0x180007bbb  jmp     loc_180007909
0x180007bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bc7  cmp     rcx, r15
0x180007bca  jz      short loc_180007BD2
0x180007bcc  cmp     byte ptr [rcx+19h], 2
0x180007bd0  jnb     short loc_180007C22
0x180007bd2  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x180007bd9  cmp     dword ptr cs:1800EF078h, 0
0x180007be0  jz      short loc_180007BEF
0x180007be2  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180007be9  jnz     loc_180007DF1
0x180007bef  mov     rdi, 0FFFFFFFF80070032h
0x180007bf6  jmp     loc_1800078FE
0x180007bfb  mov     rax, [rsi]
0x180007bfe  cmp     [rbx], rax
0x180007c01  jbe     loc_180007CAC
0x180007c07  mov     rcx, rsi
0x180007c0a  call    BfeObjectIsDurable
0x180007c0f  test    eax, eax
0x180007c11  jnz     loc_180007A9D
0x180007c17  mov     r8d, 80320016h
0x180007c1d  jmp     loc_180007CB2
0x180007c22  test    byte ptr [rcx+1Ch], 1
0x180007c26  lea     rbx, aBfeobjectassoc_0; "BfeObjectAssociate"
0x180007c2d  jz      short loc_180007BD9
0x180007c2f  mov     rcx, [rcx+10h]
0x180007c33  mov     edx, 17h
0x180007c38  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], 32h ; '2'
0x180007c40  xor     r9d, r9d
0x180007c43  mov     [rsp+120h+pSecurityDescriptor], rbx
0x180007c48  call    WPP_SF_SsD
0x180007c4d  jmp     short loc_180007BD9
0x180007c4f  mov     rcx, rbx
0x180007c52  call    BfeObjectIsValid
0x180007c57  test    eax, eax
0x180007c59  jz      loc_180007E3B
0x180007c5f  mov     rax, [rbx+78h]
  ... truncated ...
```
