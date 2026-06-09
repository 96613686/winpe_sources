# BfeFilterChangeNotify

- ea: `0x180011290`
- end: `0x180011a35`
- name: `BfeFilterChangeNotify`
- size: `1957`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000dab0`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180011290`
- `0x180011a40`
- `0x180012950`
- `0x180035500`
- `0x180035548`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011670`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011a22`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011670`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011a22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001149f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001149f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117f2`
- `AUTHZ!AuthzAccessCheck` at `0x180011462`
- `AUTHZ!AuthzAccessCheck` at `0x18001160b`
- `AUTHZ!AuthzAccessCheck` at `0x180011462`
- `AUTHZ!AuthzAccessCheck` at `0x18001160b`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011411`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800115ba`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011411`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800115ba`

## string_xrefs

- `0x18001176e`: `BfeAccessCheckFromContext`
- `0x180011835`: `BfeAccessCheckFromContext`
- `0x180011741`: `AuthzAccessCheck`
- `0x180011808`: `AuthzAccessCheck`

## pseudocode

```c
void __fastcall BfeFilterChangeNotify(
        _QWORD *a1,
        int a2,
        __int64 **a3,
        __int64 *a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  __int64 *v8; // rax
  DWORD v10; // r8d
  __int64 *v11; // rdx
  __int64 matched; // rax
  int v13; // r8d
  DWORD v14; // r14d
  _QWORD *v15; // rcx
  AUTHZ_CLIENT_CONTEXT_HANDLE v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rax
  int v22; // ecx
  _QWORD *v23; // rax
  __int64 v24; // rax
  AUTHZ_CLIENT_CONTEXT_HANDLE v25; // rbx
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  DWORD LastError; // eax
  int v28; // r8d
  signed int v29; // esi
  _QWORD *v30; // rcx
  bool v31; // zf
  signed int *v32; // rax
  DWORD v33; // eax
  signed int v34; // esi
  _QWORD *v35; // rcx
  bool v36; // zf
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 FirstAssociation; // rax
  DWORD AccessMask; // [rsp+50h] [rbp-B0h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-A8h] BYREF
  __m256i v42; // [rsp+78h] [rbp-88h] BYREF
  DWORD v43; // [rsp+98h] [rbp-68h] BYREF
  signed int v44; // [rsp+A0h] [rbp-60h] BYREF
  signed int v45; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v47[16]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  signed int *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+100h] [rbp+0h] BYREF
  __int64 v53; // [rsp+128h] [rbp+28h]

  v43 = 0;
  memset(&v42, 0, 28);
  v8 = *a3;
  memset(v46, 0, sizeof(v46));
  v10 = 0;
  if ( (a2 & (_DWORD)v8[1]) == 0 )
    return;
  v11 = a3[1];
  if ( v11 )
  {
    if ( *(_WORD *)(*(_QWORD *)a4[1] + 64LL) == *(_WORD *)v11 )
    {
      matched = FilterMatchEnumAll(a4[2], v11, &v43);
      v14 = matched;
      if ( matched )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v13, 0, (__int64)"BfeFeFilterEnumIsMatch", matched);
          v15 = WPP_GLOBAL_Control;
        }
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          v43 = v14;
          pRequest.OptionalArguments = &v43;
          pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)"BfeFeFilterEnumIsMatch";
          *(_QWORD *)&pRequest.ObjectTypeListLength = 23;
          v53 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v13,
            3,
            (__int64)&pRequest);
          v15 = WPP_GLOBAL_Control;
        }
        if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 25) >= 2u && (*((_BYTE *)v15 + 28) & 1) != 0 )
          WPP_SF_Ssd(v15[2], 26, v13, 0, (__int64)"BfeFilterIsMatchS", v14);
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          v43 = v14;
          pRequest.OptionalArguments = &v43;
          pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)"BfeFilterIsMatchS";
          *(_QWORD *)&pRequest.ObjectTypeListLength = 18;
          v53 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v13,
            3,
            (__int64)&pRequest);
        }
        if ( !pSecurityDescriptor )
        {
LABEL_18:
          v17 = a1[5];
          EnterCriticalSection((LPCRITICAL_SECTION)v17);
          *(_DWORD *)(v17 + 80) = 1;
          if ( *(_DWORD *)(v17 + 84) || !SetEvent(*(HANDLE *)(v17 + 216)) )
            goto LABEL_19;
          goto LABEL_95;
        }
        v16 = (AUTHZ_CLIENT_CONTEXT_HANDLE)a1[7];
        AccessMask = 128;
        v44 = 0;
        memset(&pRequest, 0, sizeof(pRequest));
        v43 = 5;
        memset(&pReply, 0, sizeof(pReply));
        MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
        pRequest.DesiredAccess = AccessMask;
        pReply.GrantedAccessMask = (PACCESS_MASK)&v44;
        pReply.ResultListLength = 1;
        pReply.Error = &v43;
        if ( AuthzAccessCheck(0, v16, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
        {
          if ( !v43 )
            goto LABEL_18;
          return;
        }
        LastError = GetLastError();
        v29 = LastError;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v28, 0, (__int64)"AuthzAccessCheck", LastError);
          v30 = WPP_GLOBAL_Control;
        }
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          v45 = v29;
          v50 = &v45;
          v48 = "AuthzAccessCheck";
          v49 = 17;
          v51 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v28,
            3,
            (__int64)v47);
          v30 = WPP_GLOBAL_Control;
        }
        v31 = v29 == 0;
        if ( v29 > 0 )
        {
          v29 = (unsigned __int16)v29 | 0x80070000;
          v31 = v29 == 0;
        }
        if ( v31 )
          return;
        if ( v30 != &WPP_GLOBAL_Control && *((_BYTE *)v30 + 25) >= 2u && (*((_BYTE *)v30 + 28) & 1) != 0 )
          WPP_SF_Ssd(v30[2], 26, v28, 0, (__int64)"BfeAccessCheckFromContext", v29);
        if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
          return;
        v45 = v29;
        v32 = &v45;
LABEL_94:
        v50 = v32;
        v49 = 26;
        v48 = "BfeAccessCheckFromContext";
        v51 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v28,
          3,
          (__int64)v47);
        return;
      }
      v10 = v43;
    }
  }
  else
  {
    v10 = 1;
  }
  if ( !v10 )
    return;
  v18 = **a3;
  if ( !v18 )
    goto LABEL_36;
  v19 = *(_QWORD **)v18;
  if ( !*(_QWORD *)v18 )
    goto LABEL_85;
  v20 = *(_QWORD **)(*a4 + 40);
  if ( v20 )
  {
    v21 = *v19 - *v20;
    if ( *v19 == *v20 )
      v21 = v19[1] - v20[1];
    if ( !v21 )
    {
LABEL_85:
      v22 = *(_DWORD *)(v18 + 28);
      if ( (v22 & 4) != 0 )
      {
        if ( (*(_BYTE *)(*a4 + 32) & 2) == 0 )
          return;
      }
      else if ( (v22 & 8) == 0 && (*(_BYTE *)(*a4 + 32) & 2) != 0
             || (v22 & 0x10) == 0 && (*(_BYTE *)(*a4 + 32) & 0x20) != 0 )
      {
        return;
      }
      if ( !*(_QWORD *)(v18 + 32)
        || (*(_BYTE *)(*a4 + 32) & 4) != 0
        && (FirstAssociation = BfeObjectFindFirstAssociation(a4, 1, 1, 0),
            (unsigned int)BfeProviderContextIsMatch(FirstAssociation, *(_QWORD *)(v18 + 32))) )
      {
        v23 = *(_QWORD **)(v18 + 64);
        if ( !v23 )
          goto LABEL_36;
        v37 = *a4;
        if ( (*(_DWORD *)(*a4 + 128) & 0x4000) != 0 )
        {
          v38 = *v23 - *(_QWORD *)(v37 + 132);
          if ( *v23 == *(_QWORD *)(v37 + 132) )
            v38 = v23[1] - *(_QWORD *)(v37 + 140);
          if ( !v38 )
          {
LABEL_36:
            v24 = *a4;
            LODWORD(v46[0]) = a2;
            *(_OWORD *)((char *)v46 + 4) = *(_OWORD *)v24;
            *((_QWORD *)&v46[1] + 1) = *(_QWORD *)(v24 + 176);
            v42.m256i_i64[3] = (__int64)v46;
            v42.m256i_i32[4] = 8;
            if ( pSecurityDescriptor )
            {
              v25 = (AUTHZ_CLIENT_CONTEXT_HANDLE)a1[7];
              v43 = 128;
              v45 = 0;
              memset(&pRequest, 0, sizeof(pRequest));
              AccessMask = 5;
              *(&pReply.ResultListLength + 1) = 0;
              pReply.SaclEvaluationResults = 0;
              MapGenericMask(&v43, (PGENERIC_MAPPING)&GenericMapping);
              pRequest.DesiredAccess = v43;
              pReply.GrantedAccessMask = (PACCESS_MASK)&v45;
              pReply.ResultListLength = 1;
              pReply.Error = &AccessMask;
              if ( !AuthzAccessCheck(0, v25, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
              {
                v33 = GetLastError();
                v34 = v33;
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v28, 0, (__int64)"AuthzAccessCheck", v33);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
                {
                  v44 = v34;
                  v50 = &v44;
                  v48 = "AuthzAccessCheck";
                  v49 = 17;
                  v51 = 4;
                  McGenEventWrite_EtwEventWriteTransfer(
                    (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
                    (unsigned int)WFP_USERMODE_ERROR,
                    v28,
                    3,
                    (__int64)v47);
                  v35 = WPP_GLOBAL_Control;
                }
                v36 = v34 == 0;
                if ( v34 > 0 )
                {
                  v34 = (unsigned __int16)v34 | 0x80070000;
                  v36 = v34 == 0;
                }
                if ( v36 )
                  return;
                if ( v35 != &WPP_GLOBAL_Control && *((_BYTE *)v35 + 25) >= 2u && (*((_BYTE *)v35 + 28) & 1) != 0 )
                  WPP_SF_Ssd(v35[2], 26, v28, 0, (__int64)"BfeAccessCheckFromContext", v34);
                if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
                  return;
                v44 = v34;
                v32 = &v44;
                goto LABEL_94;
              }
              if ( AccessMask )
                return;
            }
            v26 = (struct _RTL_CRITICAL_SECTION *)a1[5];
            v42.m256i_i64[1] = a1[6];
            if ( BfeNotifyOneWay(v26) )
            {
              v17 = a1[5];
              EnterCriticalSection((LPCRITICAL_SECTION)v17);
              *(_DWORD *)(v17 + 80) = 1;
              if ( *(_DWORD *)(v17 + 84) || !SetEvent(*(HANDLE *)(v17 + 216)) )
                goto LABEL_19;
LABEL_95:
              *(_DWORD *)(v17 + 84) = 1;
LABEL_19:
              LeaveCriticalSection((LPCRITICAL_SECTION)v17);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180011290  push    rbp
0x180011292  push    rbx
0x180011293  push    rsi
0x180011294  push    rdi
0x180011295  push    r12
0x180011297  push    r13
0x180011299  push    r15
0x18001129b  lea     rbp, [rsp-50h]
0x1800112a0  sub     rsp, 150h
0x1800112a7  mov     rax, cs:__security_cookie
0x1800112ae  xor     rax, rsp
0x1800112b1  mov     [rbp+80h+var_50], rax
0x1800112b5  mov     r12, [rbp+80h+arg_20]
0x1800112bc  xorps   xmm0, xmm0
0x1800112bf  xor     r13d, r13d
0x1800112c2  mov     rbx, r8
0x1800112c5  xor     eax, eax
0x1800112c7  mov     [rbp+80h+var_E8], r13d
0x1800112cb  movups  [rsp+180h+var_108], xmm0
0x1800112d0  mov     rdi, r9
0x1800112d3  mov     esi, edx
0x1800112d5  mov     rax, [rbx]
0x1800112d8  mov     r15, rcx
0x1800112db  movups  [rbp+80h+var_D0], xmm0
0x1800112df  mov     r8d, r13d
0x1800112e2  movups  [rbp+80h+var_C0], xmm0
0x1800112e6  movups  [rbp+80h+var_108+0Ch], xmm0
0x1800112ea  test    [rax+8], edx
0x1800112ed  jz      loc_1800114B8
0x1800112f3  mov     rdx, [rbx+8]
0x1800112f7  mov     [rsp+180h+var_38], r14
0x1800112ff  test    rdx, rdx
0x180011302  jz      loc_18001196D
0x180011308  mov     rax, [r9+8]
0x18001130c  mov     rcx, [rax]
0x18001130f  movzx   eax, word ptr [rdx]
0x180011312  cmp     [rcx+40h], ax
0x180011316  jnz     loc_1800114AB
0x18001131c  mov     rcx, [r9+10h]
0x180011320  lea     r8, [rbp+80h+var_E8]
0x180011324  call    FilterMatchEnumAll
0x180011329  mov     r14, rax
0x18001132c  test    rax, rax
0x18001132f  jz      loc_1800114A7
0x180011335  mov     rcx, cs:WPP_GLOBAL_Control
0x18001133c  lea     rdi, WPP_GLOBAL_Control
0x180011343  lea     rbx, aBfefefilterenu; "BfeFeFilterEnumIsMatch"
0x18001134a  cmp     rcx, rdi
0x18001134d  jz      short loc_18001137D
0x18001134f  cmp     byte ptr [rcx+19h], 2
0x180011353  jb      short loc_18001137D
0x180011355  test    byte ptr [rcx+1Ch], 1
0x180011359  jz      short loc_18001137D
0x18001135b  mov     rcx, [rcx+10h]
0x18001135f  mov     edx, 1Ah
0x180011364  mov     dword ptr [rsp+180h+OptionalSecurityDescriptorArray], r14d
0x180011369  xor     r9d, r9d
0x18001136c  mov     [rsp+180h+pSecurityDescriptor], rbx
0x180011371  call    WPP_SF_Ssd
0x180011376  mov     rcx, cs:WPP_GLOBAL_Control
0x18001137d  cmp     cs:gWfpLogUserModeErrors, r13d
0x180011384  jnz     loc_180011683
0x18001138a  lea     rbx, aBfefilterismat; "BfeFilterIsMatchS"
0x180011391  cmp     rcx, rdi
0x180011394  jz      short loc_1800113BD
0x180011396  cmp     byte ptr [rcx+19h], 2
0x18001139a  jb      short loc_1800113BD
0x18001139c  test    byte ptr [rcx+1Ch], 1
0x1800113a0  jz      short loc_1800113BD
0x1800113a2  mov     rcx, [rcx+10h]
0x1800113a6  mov     edx, 1Ah
0x1800113ab  mov     dword ptr [rsp+180h+OptionalSecurityDescriptorArray], r14d
0x1800113b0  xor     r9d, r9d
0x1800113b3  mov     [rsp+180h+pSecurityDescriptor], rbx
0x1800113b8  call    WPP_SF_Ssd
0x1800113bd  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800113c4  jnz     loc_1800116DE
0x1800113ca  test    r12, r12
0x1800113cd  jz      loc_18001147E
0x1800113d3  mov     rbx, [r15+38h]
0x1800113d7  lea     rdx, GenericMapping; GenericMapping
0x1800113de  xorps   xmm0, xmm0
0x1800113e1  mov     [rsp+180h+AccessMask], 80h
0x1800113e9  xor     eax, eax
0x1800113eb  mov     [rbp+80h+var_E0], r13d
0x1800113ef  lea     rcx, [rsp+180h+AccessMask]; AccessMask
0x1800113f4  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x1800113f8  movups  xmmword ptr [rbp+80h+pRequest.DesiredAccess], xmm0
0x1800113fc  mov     [rbp+80h+var_E8], 5
0x180011403  movups  xmmword ptr [rbp+80h+pRequest.ObjectTypeList], xmm0
0x180011407  movups  xmmword ptr [rsp+180h+var_128.ResultListLength], xmm0
0x18001140c  movups  xmmword ptr [rsp+180h+var_128.SaclEvaluationResults], xmm0
0x180011411  call    cs:__imp_MapGenericMask
0x180011417  mov     eax, [rsp+180h+AccessMask]
0x18001141b  lea     r8, [rbp+80h+pRequest]; pRequest
0x18001141f  mov     [rbp+80h+pRequest.DesiredAccess], eax
0x180011422  xor     r9d, r9d; hAuditEvent
0x180011425  mov     [rsp+180h+phAccessCheckResults], r13; phAccessCheckResults
0x18001142a  lea     rax, [rbp+80h+var_E0]
0x18001142e  mov     [rsp+180h+var_128.GrantedAccessMask], rax
0x180011433  mov     rdx, rbx; hAuthzClientContext
0x180011436  lea     rax, [rbp+80h+var_E8]
0x18001143a  mov     [rsp+180h+var_128.ResultListLength], 1
0x180011442  mov     [rsp+180h+var_128.Error], rax
0x180011447  xor     ecx, ecx; Flags
0x180011449  lea     rax, [rsp+180h+var_128]
0x18001144e  mov     [rsp+180h+pReply], rax; pReply
0x180011453  mov     [rsp+180h+OptionalSecurityDescriptorCount], r13d; OptionalSecurityDescriptorCount
0x180011458  mov     [rsp+180h+OptionalSecurityDescriptorArray], r13; OptionalSecurityDescriptorArray
0x18001145d  mov     [rsp+180h+pSecurityDescriptor], r12; pSecurityDescriptor
0x180011462  call    cs:__imp_AuthzAccessCheck
0x180011468  test    eax, eax
0x18001146a  jz      loc_180011732
0x180011470  cmp     [rbp+80h+var_E8], r13d
0x180011474  mov     eax, r13d
0x180011477  setz    al
0x18001147a  test    eax, eax
0x18001147c  jz      short loc_1800114B0
0x18001147e  mov     rbx, [r15+28h]
0x180011482  mov     rcx, rbx; lpCriticalSection
0x180011485  call    cs:__imp_EnterCriticalSection
0x18001148b  mov     dword ptr [rbx+50h], 1
0x180011492  cmp     [rbx+54h], r13d
0x180011496  jz      loc_180011A1B
0x18001149c  mov     rcx, rbx; lpCriticalSection
0x18001149f  call    cs:__imp_LeaveCriticalSection
0x1800114a5  jmp     short loc_1800114B0
0x1800114a7  mov     r8d, [rbp+80h+var_E8]
0x1800114ab  test    r8d, r8d
0x1800114ae  jnz     short loc_1800114D6
0x1800114b0  mov     r14, [rsp+180h+var_38]
0x1800114b8  mov     rcx, [rbp+80h+var_50]
0x1800114bc  xor     rcx, rsp; StackCookie
0x1800114bf  call    __security_check_cookie
0x1800114c4  add     rsp, 150h
0x1800114cb  pop     r15
0x1800114cd  pop     r13
0x1800114cf  pop     r12
0x1800114d1  pop     rdi
0x1800114d2  pop     rsi
0x1800114d3  pop     rbx
0x1800114d4  pop     rbp
0x1800114d5  retn
0x1800114d6  mov     rax, [rbx]
0x1800114d9  mov     rbx, [rax]
0x1800114dc  test    rbx, rbx
0x1800114df  jz      short loc_18001154D
0x1800114e1  mov     rcx, [rbx]
0x1800114e4  test    rcx, rcx
0x1800114e7  jz      short loc_18001150A
0x1800114e9  mov     rax, [rdi]
0x1800114ec  mov     rdx, [rax+28h]
0x1800114f0  test    rdx, rdx
0x1800114f3  jz      short loc_1800114B0
0x1800114f5  mov     rax, [rcx]
0x1800114f8  sub     rax, [rdx]
0x1800114fb  jnz     short loc_180011505
0x1800114fd  mov     rax, [rcx+8]
0x180011501  sub     rax, [rdx+8]
0x180011505  test    rax, rax
0x180011508  jnz     short loc_1800114B0
0x18001150a  mov     ecx, [rbx+1Ch]
0x18001150d  test    cl, 4
0x180011510  jnz     loc_180011A09
0x180011516  test    cl, 8
0x180011519  jnz     short loc_180011524
0x18001151b  mov     rax, [rdi]
0x18001151e  test    byte ptr [rax+20h], 2
0x180011522  jnz     short loc_1800114B0
0x180011524  test    cl, 10h
0x180011527  jnz     short loc_180011536
0x180011529  mov     rax, [rdi]
0x18001152c  test    byte ptr [rax+20h], 20h
0x180011530  jnz     loc_1800114B0
0x180011536  cmp     [rbx+20h], r13
0x18001153a  jnz     loc_1800119D0
0x180011540  mov     rax, [rbx+40h]
0x180011544  test    rax, rax
0x180011547  jnz     loc_180011998
0x18001154d  mov     rax, [rdi]
0x180011550  mov     dword ptr [rbp+80h+var_D0], esi
0x180011553  movups  xmm0, xmmword ptr [rax]
0x180011556  movups  [rbp+80h+var_D0+4], xmm0
0x18001155a  mov     rax, [rax+0B0h]
0x180011561  mov     qword ptr [rbp+80h+var_C0+8], rax
0x180011565  lea     rax, [rbp+80h+var_D0]
0x180011569  mov     [rbp+80h+var_F0], rax
0x18001156d  mov     [rbp+80h+var_F8], 8
0x180011574  test    r12, r12
0x180011577  jz      loc_18001162C
0x18001157d  mov     rbx, [r15+38h]
0x180011581  lea     rdx, GenericMapping; GenericMapping
0x180011588  xorps   xmm0, xmm0
0x18001158b  mov     [rbp+80h+var_E8], 80h
0x180011592  xor     eax, eax
0x180011594  mov     [rbp+80h+var_D8], r13d
0x180011598  lea     rcx, [rbp+80h+var_E8]; AccessMask
0x18001159c  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x1800115a0  movups  xmmword ptr [rbp+80h+pRequest.DesiredAccess], xmm0
0x1800115a4  mov     [rsp+180h+AccessMask], 5
0x1800115ac  movups  xmmword ptr [rbp+80h+pRequest.ObjectTypeList], xmm0
0x1800115b0  movups  xmmword ptr [rsp+180h+var_128.ResultListLength], xmm0
0x1800115b5  movups  xmmword ptr [rsp+180h+var_128.SaclEvaluationResults], xmm0
0x1800115ba  call    cs:__imp_MapGenericMask
0x1800115c0  mov     eax, [rbp+80h+var_E8]
0x1800115c3  lea     r8, [rbp+80h+pRequest]; pRequest
0x1800115c7  mov     [rbp+80h+pRequest.DesiredAccess], eax
0x1800115ca  xor     r9d, r9d; hAuditEvent
0x1800115cd  mov     [rsp+180h+phAccessCheckResults], r13; phAccessCheckResults
0x1800115d2  lea     rax, [rbp+80h+var_D8]
0x1800115d6  mov     [rsp+180h+var_128.GrantedAccessMask], rax
0x1800115db  mov     rdx, rbx; hAuthzClientContext
0x1800115de  lea     rax, [rsp+180h+AccessMask]
0x1800115e3  mov     [rsp+180h+var_128.ResultListLength], 1
0x1800115eb  mov     [rsp+180h+var_128.Error], rax
0x1800115f0  xor     ecx, ecx; Flags
0x1800115f2  lea     rax, [rsp+180h+var_128]
0x1800115f7  mov     [rsp+180h+pReply], rax; pReply
0x1800115fc  mov     [rsp+180h+OptionalSecurityDescriptorCount], r13d; OptionalSecurityDescriptorCount
0x180011601  mov     [rsp+180h+OptionalSecurityDescriptorArray], r13; OptionalSecurityDescriptorArray
0x180011606  mov     [rsp+180h+pSecurityDescriptor], r12; pSecurityDescriptor
0x18001160b  call    cs:__imp_AuthzAccessCheck
0x180011611  test    eax, eax
0x180011613  jz      loc_1800117F2
0x180011619  cmp     [rsp+180h+AccessMask], r13d
0x18001161e  mov     eax, r13d
0x180011621  setz    al
0x180011624  test    eax, eax
0x180011626  jz      loc_1800114B0
0x18001162c  mov     rax, [r15+30h]
0x180011630  lea     rdx, [rsp+180h+var_108]
0x180011635  mov     rcx, [r15+28h]; lpCriticalSection
0x180011639  mov     qword ptr [rbp+80h+var_108+8], rax
0x18001163d  call    BfeNotifyOneWay
0x180011642  test    rax, rax
0x180011645  jz      loc_1800114B0
0x18001164b  mov     rbx, [r15+28h]
0x18001164f  mov     rcx, rbx; lpCriticalSection
0x180011652  call    cs:__imp_EnterCriticalSection
0x180011658  mov     dword ptr [rbx+50h], 1
0x18001165f  cmp     [rbx+54h], r13d
0x180011663  jnz     loc_18001149C
0x180011669  mov     rcx, [rbx+0D8h]; hEvent
0x180011670  call    cs:__imp_SetEvent
0x180011676  test    eax, eax
0x180011678  jz      loc_18001149C
0x18001167e  jmp     loc_180088A4C
0x180011683  test    cs:byte_1800F30F5, 1
0x18001168a  jz      loc_18001138A
0x180011690  lea     rax, [rbp+80h+var_E8]
0x180011694  mov     [rbp+80h+var_E8], r14d
0x180011698  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x18001169c  lea     rdx, WFP_USERMODE_ERROR
0x1800116a3  lea     rax, [rbp+80h+pRequest]
0x1800116a7  mov     [rbp+80h+pRequest.ObjectTypeList], rbx
0x1800116ab  mov     r9d, 3
0x1800116b1  mov     [rsp+180h+pSecurityDescriptor], rax
0x1800116b6  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800116bd  mov     qword ptr [rbp+80h+pRequest.ObjectTypeListLength], 17h
0x1800116c5  mov     [rbp+80h+var_58], 4
0x1800116cd  call    McGenEventWrite_EtwEventWriteTransfer
0x1800116d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116d9  jmp     loc_18001138A
0x1800116de  test    cs:byte_1800F30F5, 1
0x1800116e5  jz      loc_1800113CA
0x1800116eb  lea     rax, [rbp+80h+var_E8]
0x1800116ef  mov     [rbp+80h+var_E8], r14d
0x1800116f3  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x1800116f7  lea     rdx, WFP_USERMODE_ERROR
0x1800116fe  lea     rax, [rbp+80h+pRequest]
0x180011702  mov     [rbp+80h+pRequest.ObjectTypeList], rbx
0x180011706  mov     r9d, 3
0x18001170c  mov     [rsp+180h+pSecurityDescriptor], rax
0x180011711  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180011718  mov     qword ptr [rbp+80h+pRequest.ObjectTypeListLength], 12h
0x180011720  mov     [rbp+80h+var_58], 4
0x180011728  call    McGenEventWrite_EtwEventWriteTransfer
0x18001172d  jmp     loc_1800113CA
0x180011732  call    cs:__imp_GetLastError
0x180011738  mov     esi, eax
0x18001173a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011741  lea     rbx, aAuthzaccessche; "AuthzAccessCheck"
0x180011748  cmp     rcx, rdi
0x18001174b  jz      short loc_180011753
0x18001174d  cmp     byte ptr [rcx+19h], 2
0x180011751  jnb     short loc_1800117C6
0x180011753  cmp     cs:gWfpLogUserModeErrors, r13d
0x18001175a  jnz     loc_1800118B9
0x180011760  test    esi, esi
0x180011762  jg      loc_180011978
0x180011768  jz      loc_1800114B0
0x18001176e  lea     rbx, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x180011775  cmp     rcx, rdi
0x180011778  jz      short loc_1800117A0
0x18001177a  cmp     byte ptr [rcx+19h], 2
0x18001177e  jb      short loc_1800117A0
0x180011780  test    byte ptr [rcx+1Ch], 1
0x180011784  jz      short loc_1800117A0
0x180011786  mov     rcx, [rcx+10h]
0x18001178a  mov     edx, 1Ah
  ... truncated ...
```
