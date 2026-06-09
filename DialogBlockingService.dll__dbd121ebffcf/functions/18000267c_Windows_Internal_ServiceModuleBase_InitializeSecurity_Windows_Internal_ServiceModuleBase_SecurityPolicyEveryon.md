# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)

- ea: `0x18000267c`
- end: `0x180002927`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800023c8`

## callees

- `0x18000267c`
- `0x180003eb4`
- `0x1800067e4`
- `0x180006804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800028dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800028dc`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002753`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800028a4`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180002753`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800028a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002786`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002816`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002840`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002786`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002816`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002773`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002832`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002773`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002761`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800026ff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800026ff`

## string_xrefs

- `0x1800027a6`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002902`: `onecore\internal\com\inc\comservicehelper.h`

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
0x18000267c  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x180002681  push    rbp
0x180002682  push    rbx
0x180002683  push    rsi
0x180002684  push    rdi
0x180002685  lea     rbp, [rsp-3Fh]
0x18000268a  sub     rsp, 0D8h
0x180002691  xor     edi, edi
0x180002693  mov     [rbp+57h+var_28], 1
0x180002697  lea     rax, [rbp+57h+pDacl]
0x18000269b  mov     [rbp+57h+pDacl], rdi
0x18000269f  mov     [rbp+57h+var_58], rax
0x1800026a3  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800026a7  lea     rax, [rbp+57h+var_70]
0x1800026ab  mov     [rbp+57h+var_70], rdi
0x1800026af  mov     [rbp+57h+var_50], rax
0x1800026b3  lea     edx, [rdi+1]; StringSDRevision
0x1800026b6  lea     rax, [rbp+57h+var_78]
0x1800026ba  mov     [rbp+57h+var_78], rdi
0x1800026be  mov     [rbp+57h+var_48], rax
0x1800026c2  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:("...
0x1800026c9  lea     rax, [rbp+57h+var_60]
0x1800026cd  mov     [rbp+57h+var_60], rdi
0x1800026d1  mov     [rbp+57h+var_40], rax
0x1800026d5  xor     r9d, r9d; SecurityDescriptorSize
0x1800026d8  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x1800026dc  mov     [rbp+57h+SecurityDescriptor], rdi
0x1800026e0  mov     [rbp+57h+var_38], rax
0x1800026e4  lea     rax, [rbp+57h+SecurityDescriptor]
0x1800026e8  mov     [rbp+57h+var_30], rax
0x1800026ec  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x1800026f0  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x1800026f3  mov     [rbp+57h+dwDaclSize], edi
0x1800026f6  mov     [rbp+57h+dwSaclSize], edi
0x1800026f9  mov     [rbp+57h+dwOwnerSize], edi
0x1800026fc  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x1800026ff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002705  test    eax, eax
0x180002707  jnz     short loc_180002713
0x180002709  mov     edx, 130h
0x18000270e  jmp     loc_1800028FE
0x180002713  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180002717  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000271b  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180002720  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180002724  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x180002729  lea     rax, [rbp+57h+dwOwnerSize]
0x18000272d  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180002732  xor     r9d, r9d; pDacl
0x180002735  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x18000273a  lea     rax, [rbp+57h+dwSaclSize]
0x18000273e  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180002743  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180002745  lea     rax, [rbp+57h+dwDaclSize]
0x180002749  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x18000274e  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x180002753  call    cs:__imp_MakeAbsoluteSD
0x180002759  test    eax, eax
0x18000275b  jnz     loc_1800028F9
0x180002761  call    cs:__imp_GetLastError
0x180002767  cmp     eax, 7Ah ; 'z'
0x18000276a  jnz     loc_1800028F9
0x180002770  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180002773  call    cs:__imp_GetProcessHeap
0x180002779  mov     esi, 8
0x18000277e  mov     r8d, ebx; dwBytes
0x180002781  mov     edx, esi; dwFlags
0x180002783  mov     rcx, rax; hHeap
0x180002786  call    cs:__imp_HeapAlloc
0x18000278c  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x180002790  test    rax, rax
0x180002793  jnz     short loc_1800027B7
0x180002795  mov     edx, 138h; void *
0x18000279a  mov     ebx, 8007000Eh
0x18000279f  mov     r9d, ebx; char *
0x1800027a2  mov     rcx, [rbp+5Fh]; this
0x1800027a6  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800027ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800027b2  jmp     loc_180002910
0x1800027b7  mov     ebx, [rbp+57h+dwDaclSize]
0x1800027ba  call    cs:__imp_GetProcessHeap
0x1800027c0  mov     r8d, ebx; dwBytes
0x1800027c3  mov     edx, esi; dwFlags
0x1800027c5  mov     rcx, rax; hHeap
0x1800027c8  call    cs:__imp_HeapAlloc
0x1800027ce  mov     [rbp+57h+pDacl], rax
0x1800027d2  test    rax, rax
0x1800027d5  jnz     short loc_1800027DE
0x1800027d7  mov     edx, 13Bh
0x1800027dc  jmp     short loc_18000279A
0x1800027de  mov     ebx, [rbp+57h+dwSaclSize]
0x1800027e1  call    cs:__imp_GetProcessHeap
0x1800027e7  mov     r8d, ebx; dwBytes
0x1800027ea  mov     edx, esi; dwFlags
0x1800027ec  mov     rcx, rax; hHeap
0x1800027ef  call    cs:__imp_HeapAlloc
0x1800027f5  mov     [rbp+57h+var_70], rax
0x1800027f9  test    rax, rax
0x1800027fc  jnz     short loc_180002805
0x1800027fe  mov     edx, 13Eh
0x180002803  jmp     short loc_18000279A
0x180002805  mov     ebx, [rbp+57h+dwOwnerSize]
0x180002808  call    cs:__imp_GetProcessHeap
0x18000280e  mov     r8d, ebx; dwBytes
0x180002811  mov     edx, esi; dwFlags
0x180002813  mov     rcx, rax; hHeap
0x180002816  call    cs:__imp_HeapAlloc
0x18000281c  mov     [rbp+57h+var_78], rax
0x180002820  test    rax, rax
0x180002823  jnz     short loc_18000282F
0x180002825  mov     edx, 141h
0x18000282a  jmp     loc_18000279A
0x18000282f  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x180002832  call    cs:__imp_GetProcessHeap
0x180002838  mov     r8d, ebx; dwBytes
0x18000283b  mov     edx, esi; dwFlags
0x18000283d  mov     rcx, rax; hHeap
0x180002840  call    cs:__imp_HeapAlloc
0x180002846  mov     [rbp+57h+var_60], rax
0x18000284a  test    rax, rax
0x18000284d  jnz     short loc_180002859
0x18000284f  mov     edx, 144h
0x180002854  jmp     loc_18000279A
0x180002859  mov     r9, [rbp+57h+pDacl]; pDacl
0x18000285d  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x180002861  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180002865  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180002869  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18000286e  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180002872  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x180002877  lea     rax, [rbp+57h+dwOwnerSize]
0x18000287b  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180002880  mov     rax, [rbp+57h+var_78]
0x180002884  mov     [rsp+0F0h+pOwner], rax; pOwner
0x180002889  lea     rax, [rbp+57h+dwSaclSize]
0x18000288d  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180002892  mov     rax, [rbp+57h+var_70]
0x180002896  mov     [rsp+0F0h+pSacl], rax; pSacl
0x18000289b  lea     rax, [rbp+57h+dwDaclSize]
0x18000289f  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800028a4  call    cs:__imp_MakeAbsoluteSD
0x1800028aa  test    eax, eax
0x1800028ac  jnz     short loc_1800028B5
0x1800028ae  mov     edx, 147h
0x1800028b3  jmp     short loc_1800028FE
0x1800028b5  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x1800028b9  xor     r9d, r9d; pReserved1
0x1800028bc  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x1800028c1  xor     r8d, r8d; asAuthSvc
0x1800028c4  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x1800028c8  or      edx, 0FFFFFFFFh; cAuthSvc
0x1800028cb  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x1800028d0  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x1800028d8  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x1800028dc  call    cs:__imp_CoInitializeSecurity
0x1800028e2  mov     ebx, eax
0x1800028e4  test    eax, eax
0x1800028e6  jns     short loc_1800028F5
0x1800028e8  mov     r9d, eax
0x1800028eb  mov     edx, 14Ah
0x1800028f0  jmp     loc_1800027A2
0x1800028f5  mov     ebx, edi
0x1800028f7  jmp     short loc_180002910
0x1800028f9  mov     edx, 134h; void *
0x1800028fe  mov     rcx, [rbp+5Fh]; this
0x180002902  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002909  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000290e  mov     ebx, eax
0x180002910  lea     rcx, [rbp+57h+var_58]
0x180002914  call    ??1?$lambda_call@V_lambda_f43ef05b8ea00435162459fb60b25850_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>::~lambda_call<_lambda_f43ef05b8ea00435162459fb60b25850_>(void)
0x180002919  mov     eax, ebx
0x18000291b  add     rsp, 0D8h
0x180002922  pop     rdi
0x180002923  pop     rsi
0x180002924  pop     rbx
0x180002925  pop     rbp
0x180002926  retn
```
