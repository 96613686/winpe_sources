# BfeFilterChangeNotify

- ea: `0x180011c50`
- end: `0x180012438`
- name: `BfeFilterChangeNotify`
- size: `2024`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e250`
- `0x18000fb34`
- `0x180011510`
- `0x180011c50`
- `0x180012440`
- `0x1800133a0`
- `0x1800332c0`
- `0x18003330c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001205b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001241f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001205b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001241f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012037`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121e9`
- `AUTHZ!AuthzAccessCheck` at `0x180011e28`
- `AUTHZ!AuthzAccessCheck` at `0x180011fea`
- `AUTHZ!AuthzAccessCheck` at `0x180011e28`
- `AUTHZ!AuthzAccessCheck` at `0x180011fea`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011dd1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011f93`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011dd1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011f93`

## string_xrefs

- `0x180012165`: `BfeAccessCheckFromContext`
- `0x180012232`: `BfeAccessCheckFromContext`
- `0x180012138`: `AuthzAccessCheck`
- `0x180012205`: `AuthzAccessCheck`

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
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
        if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
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
                if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
                if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
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
0x180011c50  push    rbp
0x180011c52  push    rbx
0x180011c53  push    rsi
0x180011c54  push    rdi
0x180011c55  push    r12
0x180011c57  push    r13
0x180011c59  push    r15
0x180011c5b  lea     rbp, [rsp-50h]
0x180011c60  sub     rsp, 150h
0x180011c67  mov     rax, cs:__security_cookie
0x180011c6e  xor     rax, rsp
0x180011c71  mov     [rbp+80h+var_50], rax
0x180011c75  mov     r12, [rbp+80h+arg_20]
0x180011c7c  xorps   xmm0, xmm0
0x180011c7f  xor     r13d, r13d
0x180011c82  mov     rbx, r8
0x180011c85  xor     eax, eax
0x180011c87  mov     [rbp+80h+var_E8], r13d
0x180011c8b  movups  [rsp+180h+var_108], xmm0
0x180011c90  mov     rdi, r9
0x180011c93  mov     esi, edx
0x180011c95  mov     rax, [rbx]
0x180011c98  mov     r15, rcx
0x180011c9b  movups  [rbp+80h+var_D0], xmm0
0x180011c9f  mov     r8d, r13d
0x180011ca2  movups  [rbp+80h+var_C0], xmm0
0x180011ca6  movups  [rbp+80h+var_108+0Ch], xmm0
0x180011caa  test    [rax+8], edx
0x180011cad  jz      loc_180011E90
0x180011cb3  mov     rdx, [rbx+8]
0x180011cb7  mov     [rsp+180h+var_38], r14
0x180011cbf  test    rdx, rdx
0x180011cc2  jz      loc_18001236A
0x180011cc8  mov     rax, [r9+8]
0x180011ccc  mov     rcx, [rax]
0x180011ccf  movzx   eax, word ptr [rdx]
0x180011cd2  cmp     [rcx+40h], ax
0x180011cd6  jnz     loc_180011E83
0x180011cdc  mov     rcx, [r9+10h]
0x180011ce0  lea     r8, [rbp+80h+var_E8]
0x180011ce4  call    FilterMatchEnumAll
0x180011ce9  mov     r14, rax
0x180011cec  test    rax, rax
0x180011cef  jz      loc_180011E7F
0x180011cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cfc  lea     rdi, WPP_GLOBAL_Control
0x180011d03  lea     rbx, aBfefefilterenu; "BfeFeFilterEnumIsMatch"
0x180011d0a  cmp     rcx, rdi
0x180011d0d  jz      short loc_180011D3D
0x180011d0f  cmp     byte ptr [rcx+19h], 2
0x180011d13  jb      short loc_180011D3D
0x180011d15  test    byte ptr [rcx+1Ch], 1
0x180011d19  jz      short loc_180011D3D
0x180011d1b  mov     rcx, [rcx+10h]
0x180011d1f  mov     edx, 1Ah
0x180011d24  mov     dword ptr [rsp+180h+OptionalSecurityDescriptorArray], r14d
0x180011d29  xor     r9d, r9d
0x180011d2c  mov     [rsp+180h+pSecurityDescriptor], rbx
0x180011d31  call    WPP_SF_Ssd
0x180011d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d3d  cmp     cs:gWfpLogUserModeErrors, r13d
0x180011d44  jnz     loc_180012074
0x180011d4a  lea     rbx, aBfefilterismat; "BfeFilterIsMatchS"
0x180011d51  cmp     rcx, rdi
0x180011d54  jz      short loc_180011D7D
0x180011d56  cmp     byte ptr [rcx+19h], 2
0x180011d5a  jb      short loc_180011D7D
0x180011d5c  test    byte ptr [rcx+1Ch], 1
0x180011d60  jz      short loc_180011D7D
0x180011d62  mov     rcx, [rcx+10h]
0x180011d66  mov     edx, 1Ah
0x180011d6b  mov     dword ptr [rsp+180h+OptionalSecurityDescriptorArray], r14d
0x180011d70  xor     r9d, r9d
0x180011d73  mov     [rsp+180h+pSecurityDescriptor], rbx
0x180011d78  call    WPP_SF_Ssd
0x180011d7d  cmp     cs:gWfpLogUserModeErrors, r13d
0x180011d84  jnz     loc_1800120CF
0x180011d8a  test    r12, r12
0x180011d8d  jz      loc_180011E4A
0x180011d93  mov     rbx, [r15+38h]
0x180011d97  lea     rdx, GenericMapping; GenericMapping
0x180011d9e  xorps   xmm0, xmm0
0x180011da1  mov     [rsp+180h+AccessMask], 80h
0x180011da9  xor     eax, eax
0x180011dab  mov     [rbp+80h+var_E0], r13d
0x180011daf  lea     rcx, [rsp+180h+AccessMask]; AccessMask
0x180011db4  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x180011db8  movups  xmmword ptr [rbp+80h+pRequest.DesiredAccess], xmm0
0x180011dbc  mov     [rbp+80h+var_E8], 5
0x180011dc3  movups  xmmword ptr [rbp+80h+pRequest.ObjectTypeList], xmm0
0x180011dc7  movups  xmmword ptr [rsp+180h+var_128.ResultListLength], xmm0
0x180011dcc  movups  xmmword ptr [rsp+180h+var_128.SaclEvaluationResults], xmm0
0x180011dd1  call    cs:__imp_MapGenericMask
0x180011dd8  nop     dword ptr [rax+rax+00h]
0x180011ddd  mov     eax, [rsp+180h+AccessMask]
0x180011de1  lea     r8, [rbp+80h+pRequest]; pRequest
0x180011de5  mov     [rbp+80h+pRequest.DesiredAccess], eax
0x180011de8  xor     r9d, r9d; hAuditEvent
0x180011deb  mov     [rsp+180h+phAccessCheckResults], r13; phAccessCheckResults
0x180011df0  lea     rax, [rbp+80h+var_E0]
0x180011df4  mov     [rsp+180h+var_128.GrantedAccessMask], rax
0x180011df9  mov     rdx, rbx; hAuthzClientContext
0x180011dfc  lea     rax, [rbp+80h+var_E8]
0x180011e00  mov     [rsp+180h+var_128.ResultListLength], 1
0x180011e08  mov     [rsp+180h+var_128.Error], rax
0x180011e0d  xor     ecx, ecx; Flags
0x180011e0f  lea     rax, [rsp+180h+var_128]
0x180011e14  mov     [rsp+180h+pReply], rax; pReply
0x180011e19  mov     [rsp+180h+OptionalSecurityDescriptorCount], r13d; OptionalSecurityDescriptorCount
0x180011e1e  mov     [rsp+180h+OptionalSecurityDescriptorArray], r13; OptionalSecurityDescriptorArray
0x180011e23  mov     [rsp+180h+pSecurityDescriptor], r12; pSecurityDescriptor
0x180011e28  call    cs:__imp_AuthzAccessCheck
0x180011e2f  nop     dword ptr [rax+rax+00h]
0x180011e34  test    eax, eax
0x180011e36  jz      loc_180012123
0x180011e3c  cmp     [rbp+80h+var_E8], r13d
0x180011e40  mov     eax, r13d
0x180011e43  setz    al
0x180011e46  test    eax, eax
0x180011e48  jz      short loc_180011E88
0x180011e4a  mov     rbx, [r15+28h]
0x180011e4e  mov     rcx, rbx; lpCriticalSection
0x180011e51  call    cs:__imp_EnterCriticalSection
0x180011e58  nop     dword ptr [rax+rax+00h]
0x180011e5d  mov     dword ptr [rbx+50h], 1
0x180011e64  cmp     [rbx+54h], r13d
0x180011e68  jz      loc_180012418
0x180011e6e  mov     rcx, rbx; lpCriticalSection
0x180011e71  call    cs:__imp_LeaveCriticalSection
0x180011e78  nop     dword ptr [rax+rax+00h]
0x180011e7d  jmp     short loc_180011E88
0x180011e7f  mov     r8d, [rbp+80h+var_E8]
0x180011e83  test    r8d, r8d
0x180011e86  jnz     short loc_180011EAF
0x180011e88  mov     r14, [rsp+180h+var_38]
0x180011e90  mov     rcx, [rbp+80h+var_50]
0x180011e94  xor     rcx, rsp; StackCookie
0x180011e97  call    __security_check_cookie
0x180011e9c  add     rsp, 150h
0x180011ea3  pop     r15
0x180011ea5  pop     r13
0x180011ea7  pop     r12
0x180011ea9  pop     rdi
0x180011eaa  pop     rsi
0x180011eab  pop     rbx
0x180011eac  pop     rbp
0x180011ead  retn
0x180011eaf  mov     rax, [rbx]
0x180011eb2  mov     rbx, [rax]
0x180011eb5  test    rbx, rbx
0x180011eb8  jz      short loc_180011F26
0x180011eba  mov     rcx, [rbx]
0x180011ebd  test    rcx, rcx
0x180011ec0  jz      short loc_180011EE3
0x180011ec2  mov     rax, [rdi]
0x180011ec5  mov     rdx, [rax+28h]
0x180011ec9  test    rdx, rdx
0x180011ecc  jz      short loc_180011E88
0x180011ece  mov     rax, [rcx]
0x180011ed1  sub     rax, [rdx]
0x180011ed4  jnz     short loc_180011EDE
0x180011ed6  mov     rax, [rcx+8]
0x180011eda  sub     rax, [rdx+8]
0x180011ede  test    rax, rax
0x180011ee1  jnz     short loc_180011E88
0x180011ee3  mov     ecx, [rbx+1Ch]
0x180011ee6  test    cl, 4
0x180011ee9  jnz     loc_180012406
0x180011eef  test    cl, 8
0x180011ef2  jnz     short loc_180011EFD
0x180011ef4  mov     rax, [rdi]
0x180011ef7  test    byte ptr [rax+20h], 2
0x180011efb  jnz     short loc_180011E88
0x180011efd  test    cl, 10h
0x180011f00  jnz     short loc_180011F0F
0x180011f02  mov     rax, [rdi]
0x180011f05  test    byte ptr [rax+20h], 20h
0x180011f09  jnz     loc_180011E88
0x180011f0f  cmp     [rbx+20h], r13
0x180011f13  jnz     loc_1800123CD
0x180011f19  mov     rax, [rbx+40h]
0x180011f1d  test    rax, rax
0x180011f20  jnz     loc_180012395
0x180011f26  mov     rax, [rdi]
0x180011f29  mov     dword ptr [rbp+80h+var_D0], esi
0x180011f2c  movups  xmm0, xmmword ptr [rax]
0x180011f2f  movups  [rbp+80h+var_D0+4], xmm0
0x180011f33  mov     rax, [rax+0B0h]
0x180011f3a  mov     qword ptr [rbp+80h+var_C0+8], rax
0x180011f3e  lea     rax, [rbp+80h+var_D0]
0x180011f42  mov     [rbp+80h+var_F0], rax
0x180011f46  mov     [rbp+80h+var_F8], 8
0x180011f4d  test    r12, r12
0x180011f50  jz      loc_180012011
0x180011f56  mov     rbx, [r15+38h]
0x180011f5a  lea     rdx, GenericMapping; GenericMapping
0x180011f61  xorps   xmm0, xmm0
0x180011f64  mov     [rbp+80h+var_E8], 80h
0x180011f6b  xor     eax, eax
0x180011f6d  mov     [rbp+80h+var_D8], r13d
0x180011f71  lea     rcx, [rbp+80h+var_E8]; AccessMask
0x180011f75  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x180011f79  movups  xmmword ptr [rbp+80h+pRequest.DesiredAccess], xmm0
0x180011f7d  mov     [rsp+180h+AccessMask], 5
0x180011f85  movups  xmmword ptr [rbp+80h+pRequest.ObjectTypeList], xmm0
0x180011f89  movups  xmmword ptr [rsp+180h+var_128.ResultListLength], xmm0
0x180011f8e  movups  xmmword ptr [rsp+180h+var_128.SaclEvaluationResults], xmm0
0x180011f93  call    cs:__imp_MapGenericMask
0x180011f9a  nop     dword ptr [rax+rax+00h]
0x180011f9f  mov     eax, [rbp+80h+var_E8]
0x180011fa2  lea     r8, [rbp+80h+pRequest]; pRequest
0x180011fa6  mov     [rbp+80h+pRequest.DesiredAccess], eax
0x180011fa9  xor     r9d, r9d; hAuditEvent
0x180011fac  mov     [rsp+180h+phAccessCheckResults], r13; phAccessCheckResults
0x180011fb1  lea     rax, [rbp+80h+var_D8]
0x180011fb5  mov     [rsp+180h+var_128.GrantedAccessMask], rax
0x180011fba  mov     rdx, rbx; hAuthzClientContext
0x180011fbd  lea     rax, [rsp+180h+AccessMask]
0x180011fc2  mov     [rsp+180h+var_128.ResultListLength], 1
0x180011fca  mov     [rsp+180h+var_128.Error], rax
0x180011fcf  xor     ecx, ecx; Flags
0x180011fd1  lea     rax, [rsp+180h+var_128]
0x180011fd6  mov     [rsp+180h+pReply], rax; pReply
0x180011fdb  mov     [rsp+180h+OptionalSecurityDescriptorCount], r13d; OptionalSecurityDescriptorCount
0x180011fe0  mov     [rsp+180h+OptionalSecurityDescriptorArray], r13; OptionalSecurityDescriptorArray
0x180011fe5  mov     [rsp+180h+pSecurityDescriptor], r12; pSecurityDescriptor
0x180011fea  call    cs:__imp_AuthzAccessCheck
0x180011ff1  nop     dword ptr [rax+rax+00h]
0x180011ff6  test    eax, eax
0x180011ff8  jz      loc_1800121E9
0x180011ffe  cmp     [rsp+180h+AccessMask], r13d
0x180012003  mov     eax, r13d
0x180012006  setz    al
0x180012009  test    eax, eax
0x18001200b  jz      loc_180011E88
0x180012011  mov     rax, [r15+30h]
0x180012015  lea     rdx, [rsp+180h+var_108]
0x18001201a  mov     rcx, [r15+28h]; lpCriticalSection
0x18001201e  mov     qword ptr [rbp+80h+var_108+8], rax
0x180012022  call    BfeNotifyOneWay
0x180012027  test    rax, rax
0x18001202a  jz      loc_180011E88
0x180012030  mov     rbx, [r15+28h]
0x180012034  mov     rcx, rbx; lpCriticalSection
0x180012037  call    cs:__imp_EnterCriticalSection
0x18001203e  nop     dword ptr [rax+rax+00h]
0x180012043  mov     dword ptr [rbx+50h], 1
0x18001204a  cmp     [rbx+54h], r13d
0x18001204e  jnz     loc_180011E6E
0x180012054  mov     rcx, [rbx+0D8h]; hEvent
0x18001205b  call    cs:__imp_SetEvent
0x180012062  nop     dword ptr [rax+rax+00h]
0x180012067  test    eax, eax
0x180012069  jz      loc_180011E6E
0x18001206f  jmp     loc_18008B92E
0x180012074  test    cs:byte_1800F6115, 1
0x18001207b  jz      loc_180011D4A
0x180012081  lea     rax, [rbp+80h+var_E8]
0x180012085  mov     [rbp+80h+var_E8], r14d
0x180012089  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x18001208d  lea     rdx, WFP_USERMODE_ERROR
0x180012094  lea     rax, [rbp+80h+pRequest]
0x180012098  mov     [rbp+80h+pRequest.ObjectTypeList], rbx
0x18001209c  mov     r9d, 3
0x1800120a2  mov     [rsp+180h+pSecurityDescriptor], rax
0x1800120a7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800120ae  mov     qword ptr [rbp+80h+pRequest.ObjectTypeListLength], 17h
0x1800120b6  mov     [rbp+80h+var_58], 4
0x1800120be  call    McGenEventWrite_EtwEventWriteTransfer
0x1800120c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120ca  jmp     loc_180011D4A
0x1800120cf  test    cs:byte_1800F6115, 1
0x1800120d6  jz      loc_180011D8A
0x1800120dc  lea     rax, [rbp+80h+var_E8]
0x1800120e0  mov     [rbp+80h+var_E8], r14d
0x1800120e4  mov     [rbp+80h+pRequest.OptionalArguments], rax
0x1800120e8  lea     rdx, WFP_USERMODE_ERROR
0x1800120ef  lea     rax, [rbp+80h+pRequest]
0x1800120f3  mov     [rbp+80h+pRequest.ObjectTypeList], rbx
0x1800120f7  mov     r9d, 3
0x1800120fd  mov     [rsp+180h+pSecurityDescriptor], rax
0x180012102  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012109  mov     qword ptr [rbp+80h+pRequest.ObjectTypeListLength], 12h
0x180012111  mov     [rbp+80h+var_58], 4
0x180012119  call    McGenEventWrite_EtwEventWriteTransfer
0x18001211e  jmp     loc_180011D8A
0x180012123  call    cs:__imp_GetLastError
0x18001212a  nop     dword ptr [rax+rax+00h]
0x18001212f  mov     esi, eax
0x180012131  mov     rcx, cs:WPP_GLOBAL_Control
0x180012138  lea     rbx, aAuthzaccessche; "AuthzAccessCheck"
0x18001213f  cmp     rcx, rdi
0x180012142  jz      short loc_18001214A
0x180012144  cmp     byte ptr [rcx+19h], 2
0x180012148  jnb     short loc_1800121BD
0x18001214a  cmp     cs:gWfpLogUserModeErrors, r13d
0x180012151  jnz     loc_1800122B6
0x180012157  test    esi, esi
0x180012159  jg      loc_180012375
0x18001215f  jz      loc_180011E88
  ... truncated ...
```
