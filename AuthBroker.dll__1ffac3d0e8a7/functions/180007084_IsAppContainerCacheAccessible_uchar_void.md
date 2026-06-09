# _IsAppContainerCacheAccessible(uchar *,void *)

- ea: `0x180007084`
- end: `0x180007373`
- name: `?_IsAppContainerCacheAccessible@@YAJPEAEPEAX@Z`
- size: `751`
- prototype: `__int64 __fastcall(unsigned __int8 *isAppContainerCacheAccessible, void *appContainerSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000fcfc`

## callees

- `0x180007084`
- `0x18000737c`
- `0x180010a00`
- `0x180011b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000726a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000730b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000726a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000730b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007345`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007345`
- `AUTHZ!AuthzFreeContext` at `0x180007354`
- `AUTHZ!AuthzFreeContext` at `0x180007354`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800070ed`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800070ed`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180007170`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180007170`
- `AUTHZ!AuthzAccessCheck` at `0x1800071e7`
- `AUTHZ!AuthzAccessCheck` at `0x1800071e7`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800072e9`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800072e9`

## pseudocode

```c
__int64 __fastcall _IsAppContainerCacheAccessible(
        unsigned __int8 *isAppContainerCacheAccessible,
        void *appContainerSid)
{
  signed int AppDataSecurityDescriptor; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  unsigned __int16 v6; // dx
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  AUTHZ_RESOURCE_MANAGER_HANDLE__ *resManager; // [rsp+50h] [rbp-39h] BYREF
  void *pSecurityDescriptor; // [rsp+58h] [rbp-31h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE__ *clientContext; // [rsp+60h] [rbp-29h] BYREF
  _LUID luid; // [rsp+68h] [rbp-21h]
  _AUTHZ_ACCESS_REPLY accessReply; // [rsp+70h] [rbp-19h] BYREF
  _AUTHZ_ACCESS_REQUEST accessRequest; // [rsp+90h] [rbp+7h] BYREF
  unsigned int grantedAccessMask; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int saclEvaluationResult; // [rsp+100h] [rbp+77h] BYREF
  unsigned int errors; // [rsp+108h] [rbp+7Fh] BYREF

  accessRequest.OptionalArguments = 0;
  *isAppContainerCacheAccessible = 0;
  luid = 0;
  resManager = 0;
  pSecurityDescriptor = 0;
  clientContext = 0;
  memset(&accessReply, 0, sizeof(accessReply));
  memset(&accessRequest, 0, 32);
  if ( AuthzInitializeResourceManager(1u, 0, 0, 0, 0, &resManager) && resManager )
  {
    AppDataSecurityDescriptor = GetAppDataSecurityDescriptor(&pSecurityDescriptor, appContainerSid);
    if ( AppDataSecurityDescriptor >= 0 )
    {
      if ( AuthzInitializeContextFromSid(2u, appContainerSid, resManager, 0, luid, 0, &clientContext) && clientContext )
      {
        accessReply.GrantedAccessMask = &grantedAccessMask;
        grantedAccessMask = 0;
        accessReply.SaclEvaluationResults = &saclEvaluationResult;
        saclEvaluationResult = 0;
        accessReply.Error = &errors;
        errors = 0;
        accessRequest.DesiredAccess = 0x2000000;
        accessReply.ResultListLength = 1;
        if ( AuthzAccessCheck(0, clientContext, &accessRequest, 0, pSecurityDescriptor, 0, 0, &accessReply, 0) )
        {
          if ( (*accessReply.GrantedAccessMask & 0x1F01FF) == 0x1F01FF && !*accessReply.Error )
            *isAppContainerCacheAccessible = 1;
        }
        else
        {
          LastError = GetLastError();
          AppDataSecurityDescriptor = LastError;
          if ( LastError > 0 )
            AppDataSecurityDescriptor = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 5u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Control.Logger,
              0x3Bu,
              WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
              AppDataSecurityDescriptor);
          }
        }
      }
      else
      {
        v8 = GetLastError();
        AppDataSecurityDescriptor = v8;
        if ( v8 > 0 )
          AppDataSecurityDescriptor = (unsigned __int16)v8 | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 5u )
        {
          v6 = 58;
          goto LABEL_32;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        v6 = 57;
LABEL_32:
        WPP_SF_(v5[1].Control.Logger, v6, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
      }
    }
  }
  else
  {
    v9 = GetLastError();
    AppDataSecurityDescriptor = v9;
    if ( v9 > 0 )
      AppDataSecurityDescriptor = (unsigned __int16)v9 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      v6 = 56;
      goto LABEL_32;
    }
  }
  if ( resManager
    && !AuthzFreeResourceManager(resManager)
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x3Cu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v10);
  }
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  if ( clientContext )
    AuthzFreeContext(clientContext);
  return (unsigned int)AppDataSecurityDescriptor;
}

```

## disassembly

```asm
0x180007084  mov     [rsp-8+arg_8], rbx
0x180007089  push    rbp
0x18000708a  push    rsi
0x18000708b  push    rdi
0x18000708c  push    r13
0x18000708e  push    r14
0x180007090  lea     rbp, [rsp-37h]
0x180007095  sub     rsp, 0C0h
0x18000709c  xor     r14d, r14d
0x18000709f  xor     eax, eax
0x1800070a1  xorps   xmm0, xmm0
0x1800070a4  mov     [rbp+57h+accessRequest.OptionalArguments], rax
0x1800070a8  xorps   xmm1, xmm1
0x1800070ab  mov     [isAppContainerCacheAccessible], r14b
0x1800070ae  mov     rdi, appContainerSid
0x1800070b1  mov     qword ptr [rbp+57h+luid.LowPart], r14
0x1800070b5  xor     edx, edx; pfnDynamicAccessCheck
0x1800070b7  mov     [rbp+57h+resManager], r14
0x1800070bb  lea     rax, [rbp+57h+resManager]
0x1800070bf  mov     [rbp+57h+pSecurityDescriptor], r14
0x1800070c3  mov     rsi, isAppContainerCacheAccessible
0x1800070c6  mov     [rsp+0E0h+phAuthzResourceManager], rax; phAuthzResourceManager
0x1800070cb  xor     r9d, r9d; pfnFreeDynamicGroups
0x1800070ce  mov     [rbp+57h+clientContext], r14
0x1800070d2  lea     ecx, [appContainerSid+1]; Flags
0x1800070d5  mov     [rsp+0E0h+szResourceManagerName], r14; szResourceManagerName
0x1800070da  xor     r8d, r8d; pfnComputeDynamicGroups
0x1800070dd  movups  xmmword ptr [rbp+57h+accessReply.ResultListLength], xmm0
0x1800070e1  movups  xmmword ptr [rbp+57h+accessReply.SaclEvaluationResults], xmm0
0x1800070e5  movups  xmmword ptr [rbp+57h+accessRequest.DesiredAccess], xmm1
0x1800070e9  movups  xmmword ptr [rbp+57h+accessRequest.ObjectTypeList], xmm1
0x1800070ed  call    cs:__imp_AuthzInitializeResourceManager
0x1800070f3  lea     r13, WPP_GLOBAL_Control
0x1800070fa  test    eax, eax
0x1800070fc  jz      loc_18000729E
0x180007102  cmp     [rbp+57h+resManager], r14
0x180007106  jz      loc_18000729E
0x18000710c  mov     appContainerSid, rdi; appContainerSid
0x18000710f  lea     isAppContainerCacheAccessible, [rbp+57h+pSecurityDescriptor]; pSD
0x180007113  call    _GetAppDataSecurityDescriptor
0x180007118  mov     ebx, eax
0x18000711a  test    eax, eax
0x18000711c  jns     short loc_18000714B
0x18000711e  mov     isAppContainerCacheAccessible, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180007125  cmp     isAppContainerCacheAccessible, r13
0x180007128  jz      $Exit_5
0x18000712e  test    byte ptr [isAppContainerCacheAccessible+44h], 10h
0x180007132  jz      $Exit_5
0x180007138  cmp     byte ptr [isAppContainerCacheAccessible+41h], 5
0x18000713c  jb      $Exit_5
0x180007142  lea     edx, [r14+39h]
0x180007146  jmp     loc_1800072D0
0x18000714b  mov     r8, [rbp+57h+resManager]; hAuthzResourceManager
0x18000714f  lea     rax, [rbp+57h+clientContext]
0x180007153  mov     [rsp+0E0h+phAuthzClientContext], rax; phAuthzClientContext
0x180007158  xor     r9d, r9d; pExpirationTime
0x18000715b  mov     rax, qword ptr [rbp+57h+luid.LowPart]
0x18000715f  mov     appContainerSid, rdi; UserSid
0x180007162  mov     [rsp+0E0h+phAuthzResourceManager], r14; DynamicGroupArgs
0x180007167  mov     [rsp+0E0h+szResourceManagerName], rax; Identifier
0x18000716c  lea     ecx, [r9+2]; Flags
0x180007170  call    cs:__imp_AuthzInitializeContextFromSid
0x180007176  test    eax, eax
0x180007178  jz      loc_18000726A
0x18000717e  mov     appContainerSid, [rbp+57h+clientContext]; hAuthzClientContext
0x180007182  test    appContainerSid, appContainerSid
0x180007185  jz      loc_18000726A
0x18000718b  mov     [rsp+0E0h+phAccessCheckResults], r14; phAccessCheckResults
0x180007190  lea     rax, [rbp+57h+grantedAccessMask]
0x180007194  mov     [rbp+57h+accessReply.GrantedAccessMask], rax
0x180007198  lea     r8, [rbp+57h+accessRequest]; pRequest
0x18000719c  lea     rax, [rbp+57h+saclEvaluationResult]
0x1800071a0  mov     [rbp+57h+grantedAccessMask], r14d
0x1800071a4  mov     [rbp+57h+accessReply.SaclEvaluationResults], rax
0x1800071a8  xor     r9d, r9d; hAuditEvent
0x1800071ab  lea     rax, [rbp+57h+errors]
0x1800071af  mov     [rbp+57h+saclEvaluationResult], r14d
0x1800071b3  mov     [rbp+57h+accessReply.Error], rax
0x1800071b7  xor     ecx, ecx; Flags
0x1800071b9  lea     rax, [rbp+57h+accessReply]
0x1800071bd  mov     [rbp+57h+errors], r14d
0x1800071c1  mov     [rsp+0E0h+pReply], rax; pReply
0x1800071c6  mov     rax, [rbp+57h+pSecurityDescriptor]
0x1800071ca  mov     dword ptr [rsp+0E0h+phAuthzClientContext], r14d; OptionalSecurityDescriptorCount
0x1800071cf  mov     [rsp+0E0h+phAuthzResourceManager], r14; OptionalSecurityDescriptorArray
0x1800071d4  mov     [rsp+0E0h+szResourceManagerName], rax; pSecurityDescriptor
0x1800071d9  mov     [rbp+57h+accessRequest.DesiredAccess], 2000000h
0x1800071e0  mov     [rbp+57h+accessReply.ResultListLength], 1
0x1800071e7  call    cs:__imp_AuthzAccessCheck
0x1800071ed  test    eax, eax
0x1800071ef  jnz     short loc_180007247
0x1800071f1  call    cs:__imp_GetLastError
0x1800071f7  mov     ebx, eax
0x1800071f9  test    eax, eax
0x1800071fb  jle     short loc_180007206
0x1800071fd  movzx   ebx, ax
0x180007200  or      ebx, 80070000h
0x180007206  mov     isAppContainerCacheAccessible, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000720d  cmp     isAppContainerCacheAccessible, r13
0x180007210  jz      $Exit_5
0x180007216  test    byte ptr [isAppContainerCacheAccessible+44h], 10h
0x18000721a  jz      $Exit_5
0x180007220  cmp     byte ptr [isAppContainerCacheAccessible+41h], 5
0x180007224  jb      $Exit_5
0x18000722a  mov     isAppContainerCacheAccessible, [isAppContainerCacheAccessible+38h]; Logger
0x18000722e  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180007235  mov     edx, 3Bh ; ';'; id
0x18000723a  mov     r9d, ebx; _a1
0x18000723d  call    WPP_SF_d
0x180007242  jmp     $Exit_5
0x180007247  mov     rax, [rbp+57h+accessReply.GrantedAccessMask]
0x18000724b  mov     ecx, [rax]
0x18000724d  mov     eax, 1F01FFh
0x180007252  and     ecx, eax
0x180007254  cmp     ecx, eax
0x180007256  jnz     $Exit_5
0x18000725c  mov     rax, [rbp+57h+accessReply.Error]
0x180007260  cmp     [rax], r14d
0x180007263  jnz     short $Exit_5
0x180007265  mov     byte ptr [rsi], 1
0x180007268  jmp     short $Exit_5
0x18000726a  call    cs:__imp_GetLastError
0x180007270  mov     ebx, eax
0x180007272  test    eax, eax
0x180007274  jle     short loc_18000727F
0x180007276  movzx   ebx, ax
0x180007279  or      ebx, 80070000h
0x18000727f  mov     isAppContainerCacheAccessible, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180007286  cmp     isAppContainerCacheAccessible, r13
0x180007289  jz      short $Exit_5
0x18000728b  test    byte ptr [isAppContainerCacheAccessible+44h], 10h
0x18000728f  jz      short $Exit_5
0x180007291  cmp     byte ptr [isAppContainerCacheAccessible+41h], 5
0x180007295  jb      short $Exit_5
0x180007297  mov     edx, 3Ah ; ':'
0x18000729c  jmp     short loc_1800072D0
0x18000729e  call    cs:__imp_GetLastError
0x1800072a4  mov     ebx, eax
0x1800072a6  test    eax, eax
0x1800072a8  jle     short loc_1800072B3
0x1800072aa  movzx   ebx, ax
0x1800072ad  or      ebx, 80070000h
0x1800072b3  mov     isAppContainerCacheAccessible, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800072ba  cmp     isAppContainerCacheAccessible, r13
0x1800072bd  jz      short $Exit_5
0x1800072bf  test    byte ptr [isAppContainerCacheAccessible+44h], 10h
0x1800072c3  jz      short $Exit_5
0x1800072c5  cmp     byte ptr [isAppContainerCacheAccessible+41h], 5
0x1800072c9  jb      short $Exit_5
0x1800072cb  mov     edx, 38h ; '8'; id
0x1800072d0  mov     isAppContainerCacheAccessible, [isAppContainerCacheAccessible+38h]; Logger
0x1800072d4  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800072db  call    WPP_SF_
0x1800072e0  mov     isAppContainerCacheAccessible, [rbp+57h+resManager]; hAuthzResourceManager
0x1800072e4  test    isAppContainerCacheAccessible, isAppContainerCacheAccessible
0x1800072e7  jz      short loc_18000733C
0x1800072e9  call    cs:__imp_AuthzFreeResourceManager
0x1800072ef  test    eax, eax
0x1800072f1  jnz     short loc_18000733C
0x1800072f3  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800072fa  cmp     rax, r13
0x1800072fd  jz      short loc_18000733C
0x1800072ff  test    byte ptr [rax+44h], 10h
0x180007303  jz      short loc_18000733C
0x180007305  cmp     byte ptr [rax+41h], 5
0x180007309  jb      short loc_18000733C
0x18000730b  call    cs:__imp_GetLastError
0x180007311  test    eax, eax
0x180007313  jle     short loc_18000731D
0x180007315  movzx   eax, ax
0x180007318  or      eax, 80070000h
0x18000731d  mov     isAppContainerCacheAccessible, cs:WPP_GLOBAL_Control
0x180007324  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000732b  mov     edx, 3Ch ; '<'; id
0x180007330  mov     r9d, eax; _a1
0x180007333  mov     isAppContainerCacheAccessible, [isAppContainerCacheAccessible+38h]; Logger
0x180007337  call    WPP_SF_d
0x18000733c  mov     isAppContainerCacheAccessible, [rbp+57h+pSecurityDescriptor]; hMem
0x180007340  test    isAppContainerCacheAccessible, isAppContainerCacheAccessible
0x180007343  jz      short loc_18000734B
0x180007345  call    cs:__imp_LocalFree
0x18000734b  mov     isAppContainerCacheAccessible, [rbp+57h+clientContext]; hAuthzClientContext
0x18000734f  test    isAppContainerCacheAccessible, isAppContainerCacheAccessible
0x180007352  jz      short loc_18000735A
0x180007354  call    cs:__imp_AuthzFreeContext
0x18000735a  mov     eax, ebx
0x18000735c  mov     rbx, [rsp+0E0h+arg_8]
0x180007364  add     rsp, 0C0h
0x18000736b  pop     r14
0x18000736d  pop     r13
0x18000736f  pop     rdi
0x180007370  pop     rsi
0x180007371  pop     rbp
0x180007372  retn
```
