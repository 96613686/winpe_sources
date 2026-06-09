# BfeAccessCheck

- ea: `0x180010d60`
- end: `0x180011319`
- name: `BfeAccessCheck`
- size: `1465`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `79`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a70`
- `0x180005a8c`
- `0x1800065d0`
- `0x180006a04`
- `0x18000b5b4`
- `0x18000c188`
- `0x18001e17c`
- `0x18001e47c`
- `0x18001e4cc`
- `0x18001e568`
- `0x18001e614`
- `0x18001edcc`
- `0x180021168`
- `0x1800217dc`
- `0x1800222dc`
- `0x180033428`
- `0x1800376d0`
- `0x18003a8e4`
- `0x18004388c`
- `0x1800454dc`
- `0x180046280`
- `0x180046c24`
- `0x1800474b8`
- `0x18004821c`
- `0x1800488b0`
- `0x1800496a0`
- `0x18004bc48`
- `0x18004e3d8`
- `0x18004e5ac`
- `0x18004e89c`
- `0x1800571ec`
- `0x180058dc0`
- `0x1800626a0`
- `0x180062e50`
- `0x1800631a0`
- `0x180063250`
- `0x180064670`
- `0x180065bb0`
- `0x180066800`
- `0x1800669b0`
- `0x180067b74`
- `0x180067c78`
- `0x180067cd0`
- `0x180067f08`
- `0x1800699e8`
- `0x180069e90`
- `0x180069f28`
- `0x18006a0ec`
- `0x18006a748`
- `0x18006a888`

## callees

- `0x18000fb34`
- `0x180010d60`
- `0x180011510`
- `0x180012d8c`
- `0x1800133a0`
- `0x18002c690`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001123e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001123e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011157`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010dae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010de2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010e05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010e32`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010fcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010dae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010de2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010e05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010e32`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010fcc`
- `AUTHZ!AuthzAccessCheck` at `0x180010f43`
- `AUTHZ!AuthzAccessCheck` at `0x180010f43`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180010ef2`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180010ef2`

## string_xrefs

- `0x18001107d`: `BfeAccessCheck`
- `0x1800111aa`: `BfeAccessCheckFromContext`
- `0x180011173`: `AuthzAccessCheck`
- `0x1800112f7`: `AuthzAccessCheck`

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
  for ( i = qword_1800F5B18; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_1800F5B18 )
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
  v20 = qword_1800F5B18;
  if ( *(__int64 **)(qword_1800F5B18 + 8) != &qword_1800F5B18 )
    goto LABEL_21;
  *(_QWORD *)i = qword_1800F5B18;
  *(_QWORD *)(i + 8) = &qword_1800F5B18;
  *(_QWORD *)(v20 + 8) = i;
  qword_1800F5B18 = i;
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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
  if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
    v22 = qword_1800F5B20;
    if ( *(__int64 **)qword_1800F5B20 != &qword_1800F5B18 )
      goto LABEL_21;
    v23 = *(_QWORD **)(qword_1800F5B20 + 8);
    if ( *v23 != qword_1800F5B20 )
      goto LABEL_21;
    qword_1800F5B20 = *(_QWORD *)(qword_1800F5B20 + 8);
    *v23 = &qword_1800F5B18;
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
    v27 = qword_1800F5B18;
    if ( *(__int64 **)(qword_1800F5B18 + 8) != &qword_1800F5B18 )
LABEL_21:
      __fastfail(3u);
    *(_QWORD *)v22 = qword_1800F5B18;
    *(_QWORD *)(v22 + 8) = &qword_1800F5B18;
    *(_QWORD *)(v27 + 8) = v22;
    qword_1800F5B18 = v22;
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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
0x180010d60  mov     [rsp-8+arg_18], rbx
0x180010d65  push    rbp
0x180010d66  push    rsi
0x180010d67  push    rdi
0x180010d68  push    r12
0x180010d6a  push    r13
0x180010d6c  push    r14
0x180010d6e  push    r15
0x180010d70  lea     rbp, [rsp-27h]
0x180010d75  sub     rsp, 0F0h
0x180010d7c  mov     rax, cs:__security_cookie
0x180010d83  xor     rax, rsp
0x180010d86  mov     [rbp+57h+var_38], rax
0x180010d8a  mov     r15, rcx
0x180010d8d  mov     r14, r8
0x180010d90  lea     rcx, gBfeAuthz; lpCriticalSection
0x180010d97  mov     r13d, edx
0x180010d9a  xor     edi, edi
0x180010d9c  call    cs:__imp_EnterCriticalSection
0x180010da3  nop     dword ptr [rax+rax+00h]
0x180010da8  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180010dae  call    cs:__imp_TlsGetValue
0x180010db5  nop     dword ptr [rax+rax+00h]
0x180010dba  test    rax, rax
0x180010dbd  jz      loc_18001104B
0x180010dc3  mov     rax, [rax]
0x180010dc6  test    rax, rax
0x180010dc9  jz      loc_18001104B
0x180010dcf  mov     r12, [rax+30h]
0x180010dd3  test    r12, r12
0x180010dd6  jz      loc_18001104B
0x180010ddc  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180010de2  call    cs:__imp_TlsGetValue
0x180010de9  nop     dword ptr [rax+rax+00h]
0x180010dee  test    rax, rax
0x180010df1  jz      short loc_180010DFF
0x180010df3  mov     rax, [rax]
0x180010df6  test    rax, rax
0x180010df9  jnz     loc_180010EAC
0x180010dff  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180010e05  call    cs:__imp_TlsGetValue
0x180010e0c  nop     dword ptr [rax+rax+00h]
0x180010e11  test    rax, rax
0x180010e14  jz      short loc_180010E1F
0x180010e16  cmp     [rax+18h], edi
0x180010e19  jnz     loc_18001104B
0x180010e1f  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180010e25  lea     rsi, [r15-1Ch]
0x180010e29  xor     eax, eax
0x180010e2b  test    r15, r15
0x180010e2e  cmovz   rsi, rax
0x180010e32  call    cs:__imp_TlsGetValue
0x180010e39  nop     dword ptr [rax+rax+00h]
0x180010e3e  test    rax, rax
0x180010e41  jz      loc_180011150
0x180010e47  mov     rax, [rax]
0x180010e4a  test    rax, rax
0x180010e4d  jz      loc_180011150
0x180010e53  mov     rax, [rax+50h]
0x180010e57  mov     rbx, cs:qword_1800F5B18
0x180010e5e  lea     rdx, qword_1800F5B18
0x180010e65  cmp     rbx, rdx
0x180010e68  jz      short loc_180010EBE
0x180010e6a  cmp     [rbx+10h], rax
0x180010e6e  jnz     short loc_180010E76
0x180010e70  cmp     [rbx+18h], rsi
0x180010e74  jz      short loc_180010E7B
0x180010e76  mov     rbx, [rbx]
0x180010e79  jmp     short loc_180010E65
0x180010e7b  mov     rax, [rbx]
0x180010e7e  cmp     [rax+8], rbx
0x180010e82  jnz     short loc_180010EA5
0x180010e84  mov     rcx, [rbx+8]
0x180010e88  cmp     [rcx], rbx
0x180010e8b  jnz     short loc_180010EA5
0x180010e8d  mov     [rcx], rax
0x180010e90  mov     [rax+8], rcx
0x180010e94  mov     rax, cs:qword_1800F5B18
0x180010e9b  cmp     [rax+8], rdx
0x180010e9f  jz      loc_18001102A
0x180010ea5  mov     ecx, 3
0x180010eaa  int     29h; Win8: RtlFailFast(ecx)
0x180010eac  mov     rax, [rax+10h]
0x180010eb0  cmp     [rax+40h], edi
0x180010eb3  jz      loc_180010DFF
0x180010eb9  jmp     loc_18001104B
0x180010ebe  xor     ebx, ebx
0x180010ec0  xorps   xmm0, xmm0
0x180010ec3  mov     [rbp+57h+AccessMask], r13d
0x180010ec7  xor     eax, eax
0x180010ec9  mov     [rbp+57h+var_C8], 5
0x180010ed0  lea     rdx, GenericMapping; GenericMapping
0x180010ed7  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180010edb  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180010edf  mov     [rbp+57h+var_98], eax
0x180010ee2  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180010ee6  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180010eea  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x180010eee  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x180010ef2  call    cs:__imp_MapGenericMask
0x180010ef9  nop     dword ptr [rax+rax+00h]
0x180010efe  mov     eax, [rbp+57h+AccessMask]
0x180010f01  lea     r8, [rbp+57h+pRequest]; pRequest
0x180010f05  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x180010f08  xor     r9d, r9d; hAuditEvent
0x180010f0b  mov     [rsp+120h+phAccessCheckResults], rdi; phAccessCheckResults
0x180010f10  lea     rax, [rbp+57h+var_98]
0x180010f14  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x180010f18  mov     rdx, r12; hAuthzClientContext
0x180010f1b  lea     rax, [rbp+57h+var_C8]
0x180010f1f  mov     [rbp+57h+var_C0.ResultListLength], 1
0x180010f26  mov     [rbp+57h+var_C0.Error], rax
0x180010f2a  xor     ecx, ecx; Flags
0x180010f2c  lea     rax, [rbp+57h+var_C0]
0x180010f30  mov     [rsp+120h+pReply], rax; pReply
0x180010f35  mov     [rsp+120h+OptionalSecurityDescriptorCount], edi; OptionalSecurityDescriptorCount
0x180010f39  mov     [rsp+120h+OptionalSecurityDescriptorArray], rdi; OptionalSecurityDescriptorArray
0x180010f3e  mov     [rsp+120h+pSecurityDescriptor], r15; pSecurityDescriptor
0x180010f43  call    cs:__imp_AuthzAccessCheck
0x180010f4a  nop     dword ptr [rax+rax+00h]
0x180010f4f  test    eax, eax
0x180010f51  jz      loc_180011157
0x180010f57  test    r14, r14
0x180010f5a  jnz     loc_18001112F
0x180010f60  mov     r8d, [rbp+57h+var_C8]
0x180010f64  test    r8d, r8d
0x180010f67  jnz     loc_1800112F7
0x180010f6d  lea     r12, WPP_GLOBAL_Control
0x180010f74  test    rdi, rdi
0x180010f77  jnz     loc_18001105E
0x180010f7d  test    r14, r14
0x180010f80  jnz     loc_180011141
0x180010f86  test    rbx, rbx
0x180010f89  jnz     loc_1800112E0
0x180010f8f  mov     rbx, cs:qword_1800F5B20
0x180010f96  lea     r14, qword_1800F5B18
0x180010f9d  cmp     [rbx], r14
0x180010fa0  jnz     loc_180010EA5
0x180010fa6  mov     rax, [rbx+8]
0x180010faa  cmp     [rax], rbx
0x180010fad  jnz     loc_180010EA5
0x180010fb3  mov     cs:qword_1800F5B20, rax
0x180010fba  mov     [rax], r14
0x180010fbd  mov     rcx, [rbx+18h]; lpMem
0x180010fc1  call    BfeObjectSecurityRelease
0x180010fc6  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180010fcc  call    cs:__imp_TlsGetValue
0x180010fd3  nop     dword ptr [rax+rax+00h]
0x180010fd8  test    rax, rax
0x180010fdb  jz      loc_18001127F
0x180010fe1  mov     rax, [rax]
0x180010fe4  test    rax, rax
0x180010fe7  jz      loc_18001127F
0x180010fed  mov     rcx, [rax+50h]
0x180010ff1  mov     [rbx+10h], rcx
0x180010ff5  mov     [rbx+18h], rsi
0x180010ff9  mov     [rbx+20h], r13d
0x180010ffd  test    rsi, rsi
0x180011000  jz      short loc_180011005
0x180011002  inc     dword ptr [rsi+18h]
0x180011005  mov     rax, cs:qword_1800F5B18
0x18001100c  cmp     [rax+8], r14
0x180011010  jnz     loc_180010EA5
0x180011016  mov     [rbx], rax
0x180011019  mov     [rbx+8], r14
0x18001101d  mov     [rax+8], rbx
0x180011021  mov     cs:qword_1800F5B18, rbx
0x180011028  jmp     short loc_18001105E
0x18001102a  mov     [rbx], rax
0x18001102d  mov     [rbx+8], rdx
0x180011031  mov     [rax+8], rbx
0x180011035  mov     cs:qword_1800F5B18, rbx
0x18001103c  mov     eax, [rbx+20h]
0x18001103f  and     eax, r13d
0x180011042  cmp     eax, r13d
0x180011045  jnz     loc_180010EC0
0x18001104b  lea     r12, WPP_GLOBAL_Control
0x180011052  test    r14, r14
0x180011055  jz      short loc_18001105E
0x180011057  mov     dword ptr [r14], 1
0x18001105e  lea     rcx, gBfeAuthz; lpCriticalSection
0x180011065  call    cs:__imp_LeaveCriticalSection
0x18001106c  nop     dword ptr [rax+rax+00h]
0x180011071  test    rdi, rdi
0x180011074  jz      short loc_1800110B8
0x180011076  mov     rcx, cs:WPP_GLOBAL_Control
0x18001107d  lea     rbx, aBfeaccesscheck; "BfeAccessCheck"
0x180011084  cmp     rcx, r12
0x180011087  jz      short loc_1800110AF
0x180011089  cmp     byte ptr [rcx+19h], 2
0x18001108d  jb      short loc_1800110AF
0x18001108f  test    byte ptr [rcx+1Ch], 1
0x180011093  jz      short loc_1800110AF
0x180011095  mov     rcx, [rcx+10h]
0x180011099  mov     edx, 1Ah
0x18001109e  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x1800110a2  xor     r9d, r9d
0x1800110a5  mov     [rsp+120h+pSecurityDescriptor], rbx
0x1800110aa  call    WPP_SF_Ssd
0x1800110af  cmp     cs:gWfpLogUserModeErrors, 0
0x1800110b6  jnz     short loc_1800110E3
0x1800110b8  mov     rax, rdi
0x1800110bb  mov     rcx, [rbp+57h+var_38]
0x1800110bf  xor     rcx, rsp; StackCookie
0x1800110c2  call    __security_check_cookie
0x1800110c7  mov     rbx, [rsp+120h+arg_18]
0x1800110cf  add     rsp, 0F0h
0x1800110d6  pop     r15
0x1800110d8  pop     r14
0x1800110da  pop     r13
0x1800110dc  pop     r12
0x1800110de  pop     rdi
0x1800110df  pop     rsi
0x1800110e0  pop     rbp
0x1800110e1  retn
0x1800110e3  test    cs:byte_1800F6115, 1
0x1800110ea  jz      short loc_1800110B8
0x1800110ec  lea     rax, [rbp+57h+var_D0]
0x1800110f0  mov     [rbp+57h+var_D0], edi
0x1800110f3  mov     [rbp+57h+var_48], rax
0x1800110f7  lea     rdx, WFP_USERMODE_ERROR
0x1800110fe  lea     rax, [rbp+57h+var_68]
0x180011102  mov     [rbp+57h+var_58], rbx
0x180011106  mov     r9d, 3
0x18001110c  mov     [rsp+120h+pSecurityDescriptor], rax
0x180011111  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180011118  mov     [rbp+57h+var_50], 0Fh
0x180011120  mov     [rbp+57h+var_40], 4
0x180011128  call    McGenEventWrite_EtwEventWriteTransfer
0x18001112d  jmp     short loc_1800110B8
0x18001112f  xor     eax, eax
0x180011131  lea     r12, WPP_GLOBAL_Control
0x180011138  cmp     [rbp+57h+var_C8], eax
0x18001113b  setz    al
0x18001113e  mov     [r14], eax
0x180011141  cmp     dword ptr [r14], 0
0x180011145  jz      loc_18001105E
0x18001114b  jmp     loc_180010F86
0x180011150  xor     eax, eax
0x180011152  jmp     loc_180010E57
0x180011157  call    cs:__imp_GetLastError
0x18001115e  nop     dword ptr [rax+rax+00h]
0x180011163  mov     edi, eax
0x180011165  mov     rcx, cs:WPP_GLOBAL_Control
0x18001116c  lea     r12, WPP_GLOBAL_Control
0x180011173  lea     r15, aAuthzaccessche; "AuthzAccessCheck"
0x18001117a  cmp     rcx, r12
0x18001117d  jz      short loc_180011189
0x18001117f  cmp     byte ptr [rcx+19h], 2
0x180011183  jnb     loc_18001124F
0x180011189  cmp     cs:gWfpLogUserModeErrors, 0
0x180011190  jnz     loc_180011286
0x180011196  test    edi, edi
0x180011198  jg      loc_1800112E9
0x18001119e  movsxd  rdi, edi
0x1800111a1  test    rdi, rdi
0x1800111a4  jz      loc_180010F7D
0x1800111aa  lea     r15, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x1800111b1  cmp     rcx, r12
0x1800111b4  jz      short loc_1800111DC
0x1800111b6  cmp     byte ptr [rcx+19h], 2
0x1800111ba  jb      short loc_1800111DC
0x1800111bc  test    byte ptr [rcx+1Ch], 1
0x1800111c0  jz      short loc_1800111DC
0x1800111c2  mov     rcx, [rcx+10h]
0x1800111c6  mov     edx, 1Ah
0x1800111cb  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x1800111cf  xor     r9d, r9d
0x1800111d2  mov     [rsp+120h+pSecurityDescriptor], r15
0x1800111d7  call    WPP_SF_Ssd
0x1800111dc  cmp     cs:gWfpLogUserModeErrors, 0
0x1800111e3  jz      loc_180010F74
0x1800111e9  test    cs:byte_1800F6115, 1
0x1800111f0  jz      loc_180010F74
0x1800111f6  lea     rax, [rbp+57h+var_D0]
0x1800111fa  mov     [rbp+57h+var_D0], edi
0x1800111fd  mov     [rbp+57h+var_48], rax
0x180011201  lea     rdx, WFP_USERMODE_ERROR
0x180011208  lea     rax, [rbp+57h+var_68]
0x18001120c  mov     [rbp+57h+var_58], r15
0x180011210  mov     r9d, 3
0x180011216  mov     [rsp+120h+pSecurityDescriptor], rax
0x18001121b  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180011222  mov     [rbp+57h+var_50], 1Ah
0x18001122a  mov     [rbp+57h+var_40], 4
0x180011232  call    McGenEventWrite_EtwEventWriteTransfer
0x180011237  lea     rcx, gBfeAuthz; lpCriticalSection
0x18001123e  call    cs:__imp_LeaveCriticalSection
0x180011245  nop     dword ptr [rax+rax+00h]
0x18001124a  jmp     loc_180011076
0x18001124f  test    byte ptr [rcx+1Ch], 1
0x180011253  jz      loc_180011189
0x180011259  mov     rcx, [rcx+10h]
0x18001125d  mov     edx, 17h
0x180011262  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], edi
0x180011266  xor     r9d, r9d
0x180011269  mov     [rsp+120h+pSecurityDescriptor], r15
0x18001126e  call    WPP_SF_SsD
0x180011273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001127a  jmp     loc_180011189
  ... truncated ...
```
