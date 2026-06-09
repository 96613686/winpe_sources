# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)

- ea: `0x180003504`
- end: `0x1800037af`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800031fc`

## callees

- `0x180003504`
- `0x180004514`
- `0x1800061f4`
- `0x180006214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000360e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003650`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003677`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000369e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800036c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000360e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003650`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003677`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000369e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800036c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ba`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180003764`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180003764`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003587`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003587`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800035db`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000372c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800035db`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000372c`

## string_xrefs

- `0x18000362e`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000378a`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(
        __int64 a1)
{
  const char *v1; // r9
  __int64 v2; // rdx
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // r9
  DWORD v8; // ebx
  HANDLE v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  DWORD v12; // ebx
  HANDLE v13; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  void *pPrimaryGroup; // rax
  HRESULT v17; // eax
  int lpdwDaclSize; // [rsp+20h] [rbp-79h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+70h] [rbp-29h] BYREF
  PSID pOwner; // [rsp+78h] [rbp-21h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-19h] BYREF
  PACL pDacl; // [rsp+88h] [rbp-11h] BYREF
  void *v26; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v27[6]; // [rsp+98h] [rbp-1h] BYREF
  char v28; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  DWORD dwPrimaryGroupSize; // [rsp+100h] [rbp+67h] BYREF
  int v31; // [rsp+104h] [rbp+6Bh]
  DWORD dwOwnerSize; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+110h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+118h] [rbp+7Fh] BYREF

  v31 = HIDWORD(a1);
  v28 = 1;
  pDacl = 0;
  v27[0] = &pDacl;
  pSacl = 0;
  v27[1] = &pSacl;
  pOwner = 0;
  v27[2] = &pOwner;
  v26 = 0;
  v27[3] = &v26;
  SecurityDescriptor = 0;
  v27[4] = &pAbsoluteSecurityDescriptor;
  v27[5] = &SecurityDescriptor;
  pAbsoluteSecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:(ML;;NX;;;LW)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v2 = 304;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v2,
                  (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
                  v1);
    goto LABEL_24;
  }
  if ( MakeAbsoluteSD(
         SecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize)
    || GetLastError() != 122 )
  {
    v2 = 308;
    goto LABEL_23;
  }
  v3 = dwAbsoluteSecurityDescriptorSize;
  ProcessHeap = GetProcessHeap();
  pAbsoluteSecurityDescriptor = HeapAlloc(ProcessHeap, 8u, v3);
  if ( !pAbsoluteSecurityDescriptor )
  {
    v5 = 312;
LABEL_7:
    LastError = -2147024882;
    v7 = 2147942414LL;
    goto LABEL_8;
  }
  v8 = dwDaclSize;
  v9 = GetProcessHeap();
  pDacl = (PACL)HeapAlloc(v9, 8u, v8);
  if ( !pDacl )
  {
    v5 = 315;
    goto LABEL_7;
  }
  v10 = dwSaclSize;
  v11 = GetProcessHeap();
  pSacl = (PACL)HeapAlloc(v11, 8u, v10);
  if ( !pSacl )
  {
    v5 = 318;
    goto LABEL_7;
  }
  v12 = dwOwnerSize;
  v13 = GetProcessHeap();
  pOwner = HeapAlloc(v13, 8u, v12);
  if ( !pOwner )
  {
    v5 = 321;
    goto LABEL_7;
  }
  v14 = dwPrimaryGroupSize;
  v15 = GetProcessHeap();
  pPrimaryGroup = HeapAlloc(v15, 8u, v14);
  v26 = pPrimaryGroup;
  if ( !pPrimaryGroup )
  {
    v5 = 324;
    goto LABEL_7;
  }
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          pDacl,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v2 = 327;
    goto LABEL_23;
  }
  v17 = CoInitializeSecurity(pAbsoluteSecurityDescriptor, -1, 0, 0, 0, 2u, 0, 0, 0);
  LastError = v17;
  if ( v17 >= 0 )
  {
    LastError = 0;
    goto LABEL_24;
  }
  v7 = (unsigned int)v17;
  v5 = 330;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)v7,
    lpdwDaclSize);
LABEL_24:
  wil::details::lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>::~lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>(v27);
  return LastError;
}

```

## disassembly

```asm
0x180003504  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x180003509  push    rbp
0x18000350a  push    rbx
0x18000350b  push    rsi
0x18000350c  push    rdi
0x18000350d  lea     rbp, [rsp-3Fh]
0x180003512  sub     rsp, 0D8h
0x180003519  xor     edi, edi
0x18000351b  mov     [rbp+57h+var_28], 1
0x18000351f  lea     rax, [rbp+57h+pDacl]
0x180003523  mov     [rbp+57h+pDacl], rdi
0x180003527  mov     [rbp+57h+var_58], rax
0x18000352b  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000352f  lea     rax, [rbp+57h+var_70]
0x180003533  mov     [rbp+57h+var_70], rdi
0x180003537  mov     [rbp+57h+var_50], rax
0x18000353b  lea     edx, [rdi+1]; StringSDRevision
0x18000353e  lea     rax, [rbp+57h+var_78]
0x180003542  mov     [rbp+57h+var_78], rdi
0x180003546  mov     [rbp+57h+var_48], rax
0x18000354a  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:("...
0x180003551  lea     rax, [rbp+57h+var_60]
0x180003555  mov     [rbp+57h+var_60], rdi
0x180003559  mov     [rbp+57h+var_40], rax
0x18000355d  xor     r9d, r9d; SecurityDescriptorSize
0x180003560  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180003564  mov     [rbp+57h+SecurityDescriptor], rdi
0x180003568  mov     [rbp+57h+var_38], rax
0x18000356c  lea     rax, [rbp+57h+SecurityDescriptor]
0x180003570  mov     [rbp+57h+var_30], rax
0x180003574  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x180003578  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18000357b  mov     [rbp+57h+dwDaclSize], edi
0x18000357e  mov     [rbp+57h+dwSaclSize], edi
0x180003581  mov     [rbp+57h+dwOwnerSize], edi
0x180003584  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x180003587  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000358d  test    eax, eax
0x18000358f  jnz     short loc_18000359B
0x180003591  mov     edx, 130h
0x180003596  jmp     loc_180003786
0x18000359b  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000359f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800035a3  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800035a8  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800035ac  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x1800035b1  lea     rax, [rbp+57h+dwOwnerSize]
0x1800035b5  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800035ba  xor     r9d, r9d; pDacl
0x1800035bd  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x1800035c2  lea     rax, [rbp+57h+dwSaclSize]
0x1800035c6  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800035cb  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800035cd  lea     rax, [rbp+57h+dwDaclSize]
0x1800035d1  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x1800035d6  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x1800035db  call    cs:__imp_MakeAbsoluteSD
0x1800035e1  test    eax, eax
0x1800035e3  jnz     loc_180003781
0x1800035e9  call    cs:__imp_GetLastError
0x1800035ef  cmp     eax, 7Ah ; 'z'
0x1800035f2  jnz     loc_180003781
0x1800035f8  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x1800035fb  call    cs:__imp_GetProcessHeap
0x180003601  mov     esi, 8
0x180003606  mov     r8d, ebx; dwBytes
0x180003609  mov     edx, esi; dwFlags
0x18000360b  mov     rcx, rax; hHeap
0x18000360e  call    cs:__imp_HeapAlloc
0x180003614  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x180003618  test    rax, rax
0x18000361b  jnz     short loc_18000363F
0x18000361d  mov     edx, 138h; void *
0x180003622  mov     ebx, 8007000Eh
0x180003627  mov     r9d, ebx; char *
0x18000362a  mov     rcx, [rbp+5Fh]; this
0x18000362e  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000363a  jmp     loc_180003798
0x18000363f  mov     ebx, [rbp+57h+dwDaclSize]
0x180003642  call    cs:__imp_GetProcessHeap
0x180003648  mov     r8d, ebx; dwBytes
0x18000364b  mov     edx, esi; dwFlags
0x18000364d  mov     rcx, rax; hHeap
0x180003650  call    cs:__imp_HeapAlloc
0x180003656  mov     [rbp+57h+pDacl], rax
0x18000365a  test    rax, rax
0x18000365d  jnz     short loc_180003666
0x18000365f  mov     edx, 13Bh
0x180003664  jmp     short loc_180003622
0x180003666  mov     ebx, [rbp+57h+dwSaclSize]
0x180003669  call    cs:__imp_GetProcessHeap
0x18000366f  mov     r8d, ebx; dwBytes
0x180003672  mov     edx, esi; dwFlags
0x180003674  mov     rcx, rax; hHeap
0x180003677  call    cs:__imp_HeapAlloc
0x18000367d  mov     [rbp+57h+var_70], rax
0x180003681  test    rax, rax
0x180003684  jnz     short loc_18000368D
0x180003686  mov     edx, 13Eh
0x18000368b  jmp     short loc_180003622
0x18000368d  mov     ebx, [rbp+57h+dwOwnerSize]
0x180003690  call    cs:__imp_GetProcessHeap
0x180003696  mov     r8d, ebx; dwBytes
0x180003699  mov     edx, esi; dwFlags
0x18000369b  mov     rcx, rax; hHeap
0x18000369e  call    cs:__imp_HeapAlloc
0x1800036a4  mov     [rbp+57h+var_78], rax
0x1800036a8  test    rax, rax
0x1800036ab  jnz     short loc_1800036B7
0x1800036ad  mov     edx, 141h
0x1800036b2  jmp     loc_180003622
0x1800036b7  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x1800036ba  call    cs:__imp_GetProcessHeap
0x1800036c0  mov     r8d, ebx; dwBytes
0x1800036c3  mov     edx, esi; dwFlags
0x1800036c5  mov     rcx, rax; hHeap
0x1800036c8  call    cs:__imp_HeapAlloc
0x1800036ce  mov     [rbp+57h+var_60], rax
0x1800036d2  test    rax, rax
0x1800036d5  jnz     short loc_1800036E1
0x1800036d7  mov     edx, 144h
0x1800036dc  jmp     loc_180003622
0x1800036e1  mov     r9, [rbp+57h+pDacl]; pDacl
0x1800036e5  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x1800036e9  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800036ed  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800036f1  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x1800036f6  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800036fa  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x1800036ff  lea     rax, [rbp+57h+dwOwnerSize]
0x180003703  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180003708  mov     rax, [rbp+57h+var_78]
0x18000370c  mov     [rsp+0F0h+pOwner], rax; pOwner
0x180003711  lea     rax, [rbp+57h+dwSaclSize]
0x180003715  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000371a  mov     rax, [rbp+57h+var_70]
0x18000371e  mov     [rsp+0F0h+pSacl], rax; pSacl
0x180003723  lea     rax, [rbp+57h+dwDaclSize]
0x180003727  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000372c  call    cs:__imp_MakeAbsoluteSD
0x180003732  test    eax, eax
0x180003734  jnz     short loc_18000373D
0x180003736  mov     edx, 147h
0x18000373b  jmp     short loc_180003786
0x18000373d  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x180003741  xor     r9d, r9d; pReserved1
0x180003744  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x180003749  xor     r8d, r8d; asAuthSvc
0x18000374c  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x180003750  or      edx, 0FFFFFFFFh; cAuthSvc
0x180003753  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x180003758  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x180003760  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x180003764  call    cs:__imp_CoInitializeSecurity
0x18000376a  mov     ebx, eax
0x18000376c  test    eax, eax
0x18000376e  jns     short loc_18000377D
0x180003770  mov     r9d, eax
0x180003773  mov     edx, 14Ah
0x180003778  jmp     loc_18000362A
0x18000377d  mov     ebx, edi
0x18000377f  jmp     short loc_180003798
0x180003781  mov     edx, 134h; void *
0x180003786  mov     rcx, [rbp+5Fh]; this
0x18000378a  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180003791  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003796  mov     ebx, eax
0x180003798  lea     rcx, [rbp+57h+var_58]
0x18000379c  call    ??1?$lambda_call@V_lambda_f43ef05b8ea00435162459fb60b25850_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>::~lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>(void)
0x1800037a1  mov     eax, ebx
0x1800037a3  add     rsp, 0D8h
0x1800037aa  pop     rdi
0x1800037ab  pop     rsi
0x1800037ac  pop     rbx
0x1800037ad  pop     rbp
0x1800037ae  retn
```
