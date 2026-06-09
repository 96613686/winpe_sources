# BfeAccessCheck

- ea: `0x180010360`
- end: `0x1800108d6`
- name: `BfeAccessCheck`
- size: `1398`
- prototype: `__int64 __fastcall(char *pSecurityDescriptor, DWORD, _DWORD *)`
- caller_count: `80`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004b50`
- `0x1800060f0`
- `0x18000651c`
- `0x18000aef4`
- `0x18000ba68`
- `0x18001c9fc`
- `0x18001e0dc`
- `0x18001e310`
- `0x18001e3bc`
- `0x18001e864`
- `0x18001eea0`
- `0x18001fb00`
- `0x18001fc3c`
- `0x1800280e0`
- `0x180035664`
- `0x1800370f4`
- `0x180038e90`
- `0x18004248c`
- `0x180043aac`
- `0x1800443a0`
- `0x180044dc8`
- `0x180045600`
- `0x1800463d4`
- `0x1800468a0`
- `0x180046d50`
- `0x180047774`
- `0x180049c70`
- `0x18004c910`
- `0x18004cacc`
- `0x18004cdbc`
- `0x180055324`
- `0x180056ef8`
- `0x180060380`
- `0x180060b30`
- `0x180060e80`
- `0x180060f30`
- `0x180062330`
- `0x180063850`
- `0x180064490`
- `0x180064630`
- `0x1800656b0`
- `0x1800657b0`
- `0x180065808`
- `0x180065a14`
- `0x1800669ac`
- `0x1800674b0`
- `0x18006793c`
- `0x1800679d4`
- `0x180067b80`
- `0x1800681b4`

## callees

- `0x18000f1a8`
- `0x180010360`
- `0x180010ad0`
- `0x18001236c`
- `0x180012950`
- `0x18002aef0`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001039c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001039c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010801`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010720`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001041a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800105a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001041a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800105a2`
- `AUTHZ!AuthzAccessCheck` at `0x18001051f`
- `AUTHZ!AuthzAccessCheck` at `0x18001051f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800104d4`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800104d4`

## string_xrefs

- `0x180010647`: `BfeAccessCheck`
- `0x18001076d`: `BfeAccessCheckFromContext`
- `0x180010736`: `AuthzAccessCheck`
- `0x1800108b4`: `AuthzAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeAccessCheck(char *pSecurityDescriptor, DWORD a2, _DWORD *a3)
{
  __int64 v6; // rdi
  __int64 *Value; // rax
  __int64 v8; // rax
  AUTHZ_CLIENT_CONTEXT_HANDLE v9; // r12
  __int64 *v10; // rax
  __int64 v11; // rax
  _DWORD *v12; // rax
  char *v13; // rsi
  __int64 *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 i; // rbx
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // r8d
  DWORD LastError; // eax
  int v31; // r8d
  _QWORD *v32; // rcx
  __int64 v33; // rax
  int v34; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-71h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-69h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-49h] BYREF
  int v38; // [rsp+88h] [rbp-41h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v40[16]; // [rsp+B8h] [rbp-11h] BYREF
  const char *v41; // [rsp+C8h] [rbp-1h]
  __int64 v42; // [rsp+D0h] [rbp+7h]
  int *v43; // [rsp+D8h] [rbp+Fh]
  __int64 v44; // [rsp+E0h] [rbp+17h]

  v6 = 0;
  EnterCriticalSection(&gBfeAuthz);
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( !Value
    || (v8 = *Value) == 0
    || (v9 = *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(v8 + 48)) == 0
    || (v10 = (__int64 *)TlsGetValue(gBfeContextComponent)) != 0
    && (v11 = *v10) != 0
    && *(_DWORD *)(*(_QWORD *)(v11 + 16) + 64LL)
    || (v12 = TlsGetValue(gBfeContextComponent)) != 0 && v12[6] )
  {
LABEL_41:
    if ( a3 )
      *a3 = 1;
    goto LABEL_43;
  }
  v13 = pSecurityDescriptor - 28;
  if ( !pSecurityDescriptor )
    v13 = 0;
  v14 = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( v14 && (v15 = *v14) != 0 )
    v16 = *(_QWORD *)(v15 + 80);
  else
    v16 = 0;
  for ( i = qword_1800F2AF8; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_1800F2AF8 )
    {
      i = 0;
      goto LABEL_25;
    }
    if ( *(_QWORD *)(i + 16) == v16 && *(char **)(i + 24) == v13 )
      break;
  }
  v18 = *(_QWORD *)i;
  if ( *(_QWORD *)(*(_QWORD *)i + 8LL) != i )
    goto LABEL_21;
  v19 = *(__int64 **)(i + 8);
  if ( *v19 != i )
    goto LABEL_21;
  *v19 = v18;
  *(_QWORD *)(v18 + 8) = v19;
  v20 = qword_1800F2AF8;
  if ( *(__int64 **)(qword_1800F2AF8 + 8) != &qword_1800F2AF8 )
    goto LABEL_21;
  *(_QWORD *)i = qword_1800F2AF8;
  *(_QWORD *)(i + 8) = &qword_1800F2AF8;
  *(_QWORD *)(v20 + 8) = i;
  qword_1800F2AF8 = i;
  if ( (a2 & *(_DWORD *)(i + 32)) == a2 )
    goto LABEL_41;
LABEL_25:
  AccessMask = a2;
  v35 = 5;
  v38 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  *(&pReply.ResultListLength + 1) = 0;
  pReply.SaclEvaluationResults = 0;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  pRequest.DesiredAccess = AccessMask;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v38;
  pReply.ResultListLength = 1;
  pReply.Error = &v35;
  if ( AuthzAccessCheck(0, v9, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
  {
    if ( a3 )
    {
      *a3 = v35 == 0;
LABEL_53:
      if ( !*a3 )
        goto LABEL_43;
      goto LABEL_30;
    }
    if ( !v35 )
      goto LABEL_28;
    v33 = WfpReportSysErrorAsWinError(v21, "AuthzAccessCheck", v35);
    v32 = WPP_GLOBAL_Control;
    v6 = v33;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v6) = LastError;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v31, 0, (__int64)"AuthzAccessCheck", LastError);
      v32 = WPP_GLOBAL_Control;
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v34 = v6;
      v43 = &v34;
      v41 = "AuthzAccessCheck";
      v42 = 17;
      v44 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v31,
        3,
        (__int64)v40);
      v32 = WPP_GLOBAL_Control;
    }
    if ( (int)v6 > 0 )
      LODWORD(v6) = (unsigned __int16)v6 | 0x80070000;
    v6 = (int)v6;
  }
  if ( !v6 )
    goto LABEL_29;
  if ( v32 != &WPP_GLOBAL_Control && *((_BYTE *)v32 + 25) >= 2u && (*((_BYTE *)v32 + 28) & 1) != 0 )
    WPP_SF_Ssd(v32[2], 26, v31, 0, (__int64)"BfeAccessCheckFromContext", v6);
  if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
  {
    v34 = v6;
    v43 = &v34;
    v41 = "BfeAccessCheckFromContext";
    v42 = 26;
    v44 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
      (unsigned int)WFP_USERMODE_ERROR,
      v31,
      3,
      (__int64)v40);
    LeaveCriticalSection(&gBfeAuthz);
    goto LABEL_44;
  }
LABEL_28:
  if ( v6 )
    goto LABEL_43;
LABEL_29:
  if ( a3 )
    goto LABEL_53;
LABEL_30:
  if ( i )
  {
    *(_DWORD *)(i + 32) |= a2;
  }
  else
  {
    v22 = qword_1800F2B00;
    if ( *(__int64 **)qword_1800F2B00 != &qword_1800F2AF8 )
      goto LABEL_21;
    v23 = *(_QWORD **)(qword_1800F2B00 + 8);
    if ( *v23 != qword_1800F2B00 )
      goto LABEL_21;
    qword_1800F2B00 = *(_QWORD *)(qword_1800F2B00 + 8);
    *v23 = &qword_1800F2AF8;
    BfeObjectSecurityRelease(*(LPCVOID *)(v22 + 24));
    v24 = (__int64 *)TlsGetValue(gBfeContextComponent);
    if ( v24 && (v25 = *v24) != 0 )
      v26 = *(_QWORD *)(v25 + 80);
    else
      v26 = 0;
    *(_QWORD *)(v22 + 16) = v26;
    *(_QWORD *)(v22 + 24) = v13;
    *(_DWORD *)(v22 + 32) = a2;
    if ( v13 )
      ++*((_DWORD *)v13 + 6);
    v27 = qword_1800F2AF8;
    if ( *(__int64 **)(qword_1800F2AF8 + 8) != &qword_1800F2AF8 )
LABEL_21:
      __fastfail(3u);
    *(_QWORD *)v22 = qword_1800F2AF8;
    *(_QWORD *)(v22 + 8) = &qword_1800F2AF8;
    *(_QWORD *)(v27 + 8) = v22;
    qword_1800F2AF8 = v22;
  }
LABEL_43:
  LeaveCriticalSection(&gBfeAuthz);
  if ( v6 )
  {
LABEL_44:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v28, 0, (__int64)"BfeAccessCheck", v6);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v34 = v6;
      v43 = &v34;
      v41 = "BfeAccessCheck";
      v42 = 15;
      v44 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v28,
        3,
        (__int64)v40);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180010360  mov     [rsp-8+arg_18], rbx
0x180010365  push    rbp
0x180010366  push    rsi
0x180010367  push    rdi
0x180010368  push    r12
0x18001036a  push    r13
0x18001036c  push    r14
0x18001036e  push    r15
0x180010370  lea     rbp, [rsp-27h]
0x180010375  sub     rsp, 0F0h
0x18001037c  mov     rax, cs:__security_cookie
0x180010383  xor     rax, rsp
0x180010386  mov     [rbp+57h+var_38], rax
0x18001038a  mov     r15, rcx
0x18001038d  mov     r14, r8
0x180010390  lea     rcx, gBfeAuthz; lpCriticalSection
0x180010397  mov     r13d, edx
0x18001039a  xor     edi, edi
0x18001039c  call    cs:__imp_EnterCriticalSection
0x1800103a2  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800103a8  call    cs:__imp_TlsGetValue
0x1800103ae  test    rax, rax
0x1800103b1  jz      loc_18001061B
0x1800103b7  mov     rax, [rax]
0x1800103ba  test    rax, rax
0x1800103bd  jz      loc_18001061B
0x1800103c3  mov     r12, [rax+30h]
0x1800103c7  test    r12, r12
0x1800103ca  jz      loc_18001061B
0x1800103d0  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800103d6  call    cs:__imp_TlsGetValue
0x1800103dc  test    rax, rax
0x1800103df  jz      short loc_1800103ED
0x1800103e1  mov     rax, [rax]
0x1800103e4  test    rax, rax
0x1800103e7  jnz     loc_18001048E
0x1800103ed  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800103f3  call    cs:__imp_TlsGetValue
0x1800103f9  test    rax, rax
0x1800103fc  jz      short loc_180010407
0x1800103fe  cmp     [rax+18h], edi
0x180010401  jnz     loc_18001061B
0x180010407  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18001040d  lea     rsi, [r15-1Ch]
0x180010411  xor     eax, eax
0x180010413  test    r15, r15
0x180010416  cmovz   rsi, rax
0x18001041a  call    cs:__imp_TlsGetValue
0x180010420  test    rax, rax
0x180010423  jz      loc_180010719
0x180010429  mov     rax, [rax]
0x18001042c  test    rax, rax
0x18001042f  jz      loc_180010719
0x180010435  mov     rax, [rax+50h]
0x180010439  mov     rbx, cs:qword_1800F2AF8
0x180010440  lea     rdx, qword_1800F2AF8
0x180010447  cmp     rbx, rdx
0x18001044a  jz      short loc_1800104A0
0x18001044c  cmp     [rbx+10h], rax
0x180010450  jnz     short loc_180010458
0x180010452  cmp     [rbx+18h], rsi
0x180010456  jz      short loc_18001045D
0x180010458  mov     rbx, [rbx]
0x18001045b  jmp     short loc_180010447
0x18001045d  mov     rax, [rbx]
0x180010460  cmp     [rax+8], rbx
0x180010464  jnz     short loc_180010487
0x180010466  mov     rcx, [rbx+8]
0x18001046a  cmp     [rcx], rbx
0x18001046d  jnz     short loc_180010487
0x18001046f  mov     [rcx], rax
0x180010472  mov     [rax+8], rcx
0x180010476  mov     rax, cs:qword_1800F2AF8
0x18001047d  cmp     [rax+8], rdx
0x180010481  jz      loc_1800105FA
0x180010487  mov     ecx, 3
0x18001048c  int     29h; Win8: RtlFailFast(ecx)
0x18001048e  mov     rax, [rax+10h]
0x180010492  cmp     [rax+40h], edi
0x180010495  jz      loc_1800103ED
0x18001049b  jmp     loc_18001061B
0x1800104a0  xor     ebx, ebx
0x1800104a2  xorps   xmm0, xmm0
0x1800104a5  mov     [rbp+57h+AccessMask], r13d
0x1800104a9  xor     eax, eax
0x1800104ab  mov     [rbp+57h+var_C8], 5
0x1800104b2  lea     rdx, GenericMapping; GenericMapping
0x1800104b9  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x1800104bd  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800104c1  mov     [rbp+57h+var_98], eax
0x1800104c4  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x1800104c8  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x1800104cc  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x1800104d0  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x1800104d4  call    cs:__imp_MapGenericMask
0x1800104da  mov     eax, [rbp+57h+AccessMask]
0x1800104dd  lea     r8, [rbp+57h+pRequest]; pRequest
0x1800104e1  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x1800104e4  xor     r9d, r9d; hAuditEvent
0x1800104e7  mov     [rsp+120h+phAccessCheckResults], rdi; phAccessCheckResults
0x1800104ec  lea     rax, [rbp+57h+var_98]
0x1800104f0  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x1800104f4  mov     rdx, r12; hAuthzClientContext
0x1800104f7  lea     rax, [rbp+57h+var_C8]
0x1800104fb  mov     [rbp+57h+var_C0.ResultListLength], 1
0x180010502  mov     [rbp+57h+var_C0.Error], rax
0x180010506  xor     ecx, ecx; Flags
0x180010508  lea     rax, [rbp+57h+var_C0]
0x18001050c  mov     [rsp+120h+pReply], rax; pReply
0x180010511  mov     [rsp+120h+OptionalSecurityDescriptorCount], edi; OptionalSecurityDescriptorCount
0x180010515  mov     [rsp+120h+OptionalSecurityDescriptorArray], rdi; OptionalSecurityDescriptorArray
0x18001051a  mov     [rsp+120h+pSecurityDescriptor], r15; pSecurityDescriptor
0x18001051f  call    cs:__imp_AuthzAccessCheck
0x180010525  test    eax, eax
0x180010527  jz      loc_180010720
0x18001052d  test    r14, r14
0x180010530  jnz     loc_1800106F8
0x180010536  mov     r8d, [rbp+57h+var_C8]
0x18001053a  test    r8d, r8d
0x18001053d  jnz     loc_1800108B4
0x180010543  lea     r12, WPP_GLOBAL_Control
0x18001054a  test    rdi, rdi
0x18001054d  jnz     loc_18001062E
0x180010553  test    r14, r14
0x180010556  jnz     loc_18001070A
0x18001055c  test    rbx, rbx
0x18001055f  jnz     loc_18001089D
0x180010565  mov     rbx, cs:qword_1800F2B00
0x18001056c  lea     r14, qword_1800F2AF8
0x180010573  cmp     [rbx], r14
0x180010576  jnz     loc_180010487
0x18001057c  mov     rax, [rbx+8]
0x180010580  cmp     [rax], rbx
0x180010583  jnz     loc_180010487
0x180010589  mov     cs:qword_1800F2B00, rax
0x180010590  mov     [rax], r14
0x180010593  mov     rcx, [rbx+18h]; lpMem
0x180010597  call    BfeObjectSecurityRelease
0x18001059c  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800105a2  call    cs:__imp_TlsGetValue
0x1800105a8  test    rax, rax
0x1800105ab  jz      loc_18001083C
0x1800105b1  mov     rax, [rax]
0x1800105b4  test    rax, rax
0x1800105b7  jz      loc_18001083C
0x1800105bd  mov     rcx, [rax+50h]
0x1800105c1  mov     [rbx+10h], rcx
0x1800105c5  mov     [rbx+18h], rsi
0x1800105c9  mov     [rbx+20h], r13d
0x1800105cd  test    rsi, rsi
0x1800105d0  jz      short loc_1800105D5
0x1800105d2  inc     dword ptr [rsi+18h]
0x1800105d5  mov     rax, cs:qword_1800F2AF8
0x1800105dc  cmp     [rax+8], r14
0x1800105e0  jnz     loc_180010487
0x1800105e6  mov     [rbx], rax
0x1800105e9  mov     [rbx+8], r14
0x1800105ed  mov     [rax+8], rbx
0x1800105f1  mov     cs:qword_1800F2AF8, rbx
0x1800105f8  jmp     short loc_18001062E
0x1800105fa  mov     [rbx], rax
0x1800105fd  mov     [rbx+8], rdx
0x180010601  mov     [rax+8], rbx
0x180010605  mov     cs:qword_1800F2AF8, rbx
0x18001060c  mov     eax, [rbx+20h]
0x18001060f  and     eax, r13d
0x180010612  cmp     eax, r13d
0x180010615  jnz     loc_1800104A2
0x18001061b  lea     r12, WPP_GLOBAL_Control
0x180010622  test    r14, r14
0x180010625  jz      short loc_18001062E
0x180010627  mov     dword ptr [r14], 1
0x18001062e  lea     rcx, gBfeAuthz; lpCriticalSection
0x180010635  call    cs:__imp_LeaveCriticalSection
0x18001063b  test    rdi, rdi
0x18001063e  jz      short loc_180010682
0x180010640  mov     rcx, cs:WPP_GLOBAL_Control
0x180010647  lea     rbx, aBfeaccesscheck; "BfeAccessCheck"
0x18001064e  cmp     rcx, r12
0x180010651  jz      short loc_180010679
0x180010653  cmp     byte ptr [rcx+19h], 2
0x180010657  jb      short loc_180010679
0x180010659  test    byte ptr [rcx+1Ch], 1
0x18001065d  jz      short loc_180010679
0x18001065f  mov     rcx, [rcx+10h]
0x180010663  mov     edx, 1Ah
0x180010668  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x18001066c  xor     r9d, r9d
0x18001066f  mov     [rsp+120h+pSecurityDescriptor], rbx
0x180010674  call    WPP_SF_Ssd
0x180010679  cmp     cs:gWfpLogUserModeErrors, 0
0x180010680  jnz     short loc_1800106AC
0x180010682  mov     rax, rdi
0x180010685  mov     rcx, [rbp+57h+var_38]
0x180010689  xor     rcx, rsp; StackCookie
0x18001068c  call    __security_check_cookie
0x180010691  mov     rbx, [rsp+120h+arg_18]
0x180010699  add     rsp, 0F0h
0x1800106a0  pop     r15
0x1800106a2  pop     r14
0x1800106a4  pop     r13
0x1800106a6  pop     r12
0x1800106a8  pop     rdi
0x1800106a9  pop     rsi
0x1800106aa  pop     rbp
0x1800106ab  retn
0x1800106ac  test    cs:byte_1800F30F5, 1
0x1800106b3  jz      short loc_180010682
0x1800106b5  lea     rax, [rbp+57h+var_D0]
0x1800106b9  mov     [rbp+57h+var_D0], edi
0x1800106bc  mov     [rbp+57h+var_48], rax
0x1800106c0  lea     rdx, WFP_USERMODE_ERROR
0x1800106c7  lea     rax, [rbp+57h+var_68]
0x1800106cb  mov     [rbp+57h+var_58], rbx
0x1800106cf  mov     r9d, 3
0x1800106d5  mov     [rsp+120h+pSecurityDescriptor], rax
0x1800106da  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800106e1  mov     [rbp+57h+var_50], 0Fh
0x1800106e9  mov     [rbp+57h+var_40], 4
0x1800106f1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800106f6  jmp     short loc_180010682
0x1800106f8  xor     eax, eax
0x1800106fa  lea     r12, WPP_GLOBAL_Control
0x180010701  cmp     [rbp+57h+var_C8], eax
0x180010704  setz    al
0x180010707  mov     [r14], eax
0x18001070a  cmp     dword ptr [r14], 0
0x18001070e  jz      loc_18001062E
0x180010714  jmp     loc_18001055C
0x180010719  xor     eax, eax
0x18001071b  jmp     loc_180010439
0x180010720  call    cs:__imp_GetLastError
0x180010726  mov     edi, eax
0x180010728  mov     rcx, cs:WPP_GLOBAL_Control
0x18001072f  lea     r12, WPP_GLOBAL_Control
0x180010736  lea     r15, aAuthzaccessche; "AuthzAccessCheck"
0x18001073d  cmp     rcx, r12
0x180010740  jz      short loc_18001074C
0x180010742  cmp     byte ptr [rcx+19h], 2
0x180010746  jnb     loc_18001080C
0x18001074c  cmp     cs:gWfpLogUserModeErrors, 0
0x180010753  jnz     loc_180010843
0x180010759  test    edi, edi
0x18001075b  jg      loc_1800108A6
0x180010761  movsxd  rdi, edi
0x180010764  test    rdi, rdi
0x180010767  jz      loc_180010553
0x18001076d  lea     r15, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x180010774  cmp     rcx, r12
0x180010777  jz      short loc_18001079F
0x180010779  cmp     byte ptr [rcx+19h], 2
0x18001077d  jb      short loc_18001079F
0x18001077f  test    byte ptr [rcx+1Ch], 1
0x180010783  jz      short loc_18001079F
0x180010785  mov     rcx, [rcx+10h]
0x180010789  mov     edx, 1Ah
0x18001078e  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x180010792  xor     r9d, r9d
0x180010795  mov     [rsp+120h+pSecurityDescriptor], r15
0x18001079a  call    WPP_SF_Ssd
0x18001079f  cmp     cs:gWfpLogUserModeErrors, 0
0x1800107a6  jz      loc_18001054A
0x1800107ac  test    cs:byte_1800F30F5, 1
0x1800107b3  jz      loc_18001054A
0x1800107b9  lea     rax, [rbp+57h+var_D0]
0x1800107bd  mov     [rbp+57h+var_D0], edi
0x1800107c0  mov     [rbp+57h+var_48], rax
0x1800107c4  lea     rdx, WFP_USERMODE_ERROR
0x1800107cb  lea     rax, [rbp+57h+var_68]
0x1800107cf  mov     [rbp+57h+var_58], r15
0x1800107d3  mov     r9d, 3
0x1800107d9  mov     [rsp+120h+pSecurityDescriptor], rax
0x1800107de  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800107e5  mov     [rbp+57h+var_50], 1Ah
0x1800107ed  mov     [rbp+57h+var_40], 4
0x1800107f5  call    McGenEventWrite_EtwEventWriteTransfer
0x1800107fa  lea     rcx, gBfeAuthz; lpCriticalSection
0x180010801  call    cs:__imp_LeaveCriticalSection
0x180010807  jmp     loc_180010640
0x18001080c  test    byte ptr [rcx+1Ch], 1
0x180010810  jz      loc_18001074C
0x180010816  mov     rcx, [rcx+10h]
0x18001081a  mov     edx, 17h
0x18001081f  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x180010823  xor     r9d, r9d
0x180010826  mov     [rsp+120h+pSecurityDescriptor], r15
0x18001082b  call    WPP_SF_SsD
0x180010830  mov     rcx, cs:WPP_GLOBAL_Control
0x180010837  jmp     loc_18001074C
0x18001083c  xor     ecx, ecx
0x18001083e  jmp     loc_1800105C1
0x180010843  test    cs:byte_1800F30F5, 1
0x18001084a  jz      loc_180010759
0x180010850  lea     rax, [rbp+57h+var_D0]
0x180010854  mov     [rbp+57h+var_D0], edi
0x180010857  mov     [rbp+57h+var_48], rax
0x18001085b  lea     rdx, WFP_USERMODE_ERROR
0x180010862  lea     rax, [rbp+57h+var_68]
0x180010866  mov     [rbp+57h+var_58], r15
0x18001086a  mov     r9d, 3
  ... truncated ...
```
