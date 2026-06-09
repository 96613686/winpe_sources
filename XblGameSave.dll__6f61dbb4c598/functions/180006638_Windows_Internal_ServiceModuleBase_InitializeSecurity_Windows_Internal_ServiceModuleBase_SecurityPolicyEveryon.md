# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(void)

- ea: `0x180006638`
- end: `0x1800068e3`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000637c`

## callees

- `0x180006638`
- `0x180008668`
- `0x18000aba4`
- `0x18000abc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000673e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006780`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000673e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006780`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000672b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000672b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006719`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180006894`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180006894`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800066b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800066b7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000670b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000685c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000670b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000685c`

## string_xrefs

- `0x18000675e`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800068ba`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(
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
  v27[0] = &pDacl;
  pDacl = 0;
  v27[1] = &pSacl;
  pSacl = 0;
  v27[2] = &pOwner;
  pOwner = 0;
  v27[3] = &v26;
  v26 = 0;
  v27[4] = &pAbsoluteSecurityDescriptor;
  v27[5] = &SecurityDescriptor;
  SecurityDescriptor = 0;
  pAbsoluteSecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:PSG:BUD:(A;;0x1F;;;AC)(A;;0x1F;;;WD)S:(ML;;NX;;;LW)",
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
  v28 = 0;
  _lambda_bed1b5be4148163977e87fd2fb1bced4_::operator()(v27);
  return LastError;
}

```

## disassembly

```asm
0x180006638  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x18000663d  push    rbp
0x18000663e  push    rbx
0x18000663f  push    rsi
0x180006640  push    rdi
0x180006641  lea     rbp, [rsp-3Fh]
0x180006646  sub     rsp, 0D8h
0x18000664d  xor     edi, edi
0x18000664f  lea     rax, [rbp+57h+pDacl]
0x180006653  mov     [rbp+57h+var_58], rax
0x180006657  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000665b  lea     rax, [rbp+57h+var_70]
0x18000665f  mov     [rbp+57h+pDacl], rdi
0x180006663  mov     [rbp+57h+var_50], rax
0x180006667  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0x1F;;;AC)(A;;0x1F;;;WD)S"...
0x18000666e  lea     rax, [rbp+57h+var_78]
0x180006672  mov     [rbp+57h+var_70], rdi
0x180006676  mov     [rbp+57h+var_48], rax
0x18000667a  lea     edx, [rdi+1]; StringSDRevision
0x18000667d  lea     rax, [rbp+57h+var_60]
0x180006681  mov     [rbp+57h+var_78], rdi
0x180006685  mov     [rbp+57h+var_40], rax
0x180006689  xor     r9d, r9d; SecurityDescriptorSize
0x18000668c  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180006690  mov     [rbp+57h+var_60], rdi
0x180006694  mov     [rbp+57h+var_38], rax
0x180006698  lea     rax, [rbp+57h+SecurityDescriptor]
0x18000669c  mov     [rbp+57h+var_30], rax
0x1800066a0  mov     [rbp+57h+SecurityDescriptor], rdi
0x1800066a4  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x1800066a8  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x1800066ab  mov     [rbp+57h+dwDaclSize], edi
0x1800066ae  mov     [rbp+57h+dwSaclSize], edi
0x1800066b1  mov     [rbp+57h+dwOwnerSize], edi
0x1800066b4  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x1800066b7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800066bd  test    eax, eax
0x1800066bf  jnz     short loc_1800066CB
0x1800066c1  mov     edx, 130h
0x1800066c6  jmp     loc_1800068B6
0x1800066cb  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800066cf  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800066d3  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800066d8  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800066dc  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x1800066e1  lea     rax, [rbp+57h+dwOwnerSize]
0x1800066e5  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800066ea  xor     r9d, r9d; pDacl
0x1800066ed  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x1800066f2  lea     rax, [rbp+57h+dwSaclSize]
0x1800066f6  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800066fb  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800066fd  lea     rax, [rbp+57h+dwDaclSize]
0x180006701  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x180006706  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x18000670b  call    cs:__imp_MakeAbsoluteSD
0x180006711  test    eax, eax
0x180006713  jnz     loc_1800068B1
0x180006719  call    cs:__imp_GetLastError
0x18000671f  cmp     eax, 7Ah ; 'z'
0x180006722  jnz     loc_1800068B1
0x180006728  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18000672b  call    cs:__imp_GetProcessHeap
0x180006731  mov     esi, 8
0x180006736  mov     r8d, ebx; dwBytes
0x180006739  mov     edx, esi; dwFlags
0x18000673b  mov     rcx, rax; hHeap
0x18000673e  call    cs:__imp_HeapAlloc
0x180006744  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x180006748  test    rax, rax
0x18000674b  jnz     short loc_18000676F
0x18000674d  mov     edx, 138h; void *
0x180006752  mov     ebx, 8007000Eh
0x180006757  mov     r9d, ebx; char *
0x18000675a  mov     rcx, [rbp+5Fh]; this
0x18000675e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180006765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000676a  jmp     loc_1800068C8
0x18000676f  mov     ebx, [rbp+57h+dwDaclSize]
0x180006772  call    cs:__imp_GetProcessHeap
0x180006778  mov     r8d, ebx; dwBytes
0x18000677b  mov     edx, esi; dwFlags
0x18000677d  mov     rcx, rax; hHeap
0x180006780  call    cs:__imp_HeapAlloc
0x180006786  mov     [rbp+57h+pDacl], rax
0x18000678a  test    rax, rax
0x18000678d  jnz     short loc_180006796
0x18000678f  mov     edx, 13Bh
0x180006794  jmp     short loc_180006752
0x180006796  mov     ebx, [rbp+57h+dwSaclSize]
0x180006799  call    cs:__imp_GetProcessHeap
0x18000679f  mov     r8d, ebx; dwBytes
0x1800067a2  mov     edx, esi; dwFlags
0x1800067a4  mov     rcx, rax; hHeap
0x1800067a7  call    cs:__imp_HeapAlloc
0x1800067ad  mov     [rbp+57h+var_70], rax
0x1800067b1  test    rax, rax
0x1800067b4  jnz     short loc_1800067BD
0x1800067b6  mov     edx, 13Eh
0x1800067bb  jmp     short loc_180006752
0x1800067bd  mov     ebx, [rbp+57h+dwOwnerSize]
0x1800067c0  call    cs:__imp_GetProcessHeap
0x1800067c6  mov     r8d, ebx; dwBytes
0x1800067c9  mov     edx, esi; dwFlags
0x1800067cb  mov     rcx, rax; hHeap
0x1800067ce  call    cs:__imp_HeapAlloc
0x1800067d4  mov     [rbp+57h+var_78], rax
0x1800067d8  test    rax, rax
0x1800067db  jnz     short loc_1800067E7
0x1800067dd  mov     edx, 141h
0x1800067e2  jmp     loc_180006752
0x1800067e7  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x1800067ea  call    cs:__imp_GetProcessHeap
0x1800067f0  mov     r8d, ebx; dwBytes
0x1800067f3  mov     edx, esi; dwFlags
0x1800067f5  mov     rcx, rax; hHeap
0x1800067f8  call    cs:__imp_HeapAlloc
0x1800067fe  mov     [rbp+57h+var_60], rax
0x180006802  test    rax, rax
0x180006805  jnz     short loc_180006811
0x180006807  mov     edx, 144h
0x18000680c  jmp     loc_180006752
0x180006811  mov     r9, [rbp+57h+pDacl]; pDacl
0x180006815  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x180006819  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000681d  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180006821  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x180006826  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000682a  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x18000682f  lea     rax, [rbp+57h+dwOwnerSize]
0x180006833  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180006838  mov     rax, [rbp+57h+var_78]
0x18000683c  mov     [rsp+0F0h+pOwner], rax; pOwner
0x180006841  lea     rax, [rbp+57h+dwSaclSize]
0x180006845  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000684a  mov     rax, [rbp+57h+var_70]
0x18000684e  mov     [rsp+0F0h+pSacl], rax; pSacl
0x180006853  lea     rax, [rbp+57h+dwDaclSize]
0x180006857  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000685c  call    cs:__imp_MakeAbsoluteSD
0x180006862  test    eax, eax
0x180006864  jnz     short loc_18000686D
0x180006866  mov     edx, 147h
0x18000686b  jmp     short loc_1800068B6
0x18000686d  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x180006871  xor     r9d, r9d; pReserved1
0x180006874  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x180006879  xor     r8d, r8d; asAuthSvc
0x18000687c  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x180006880  or      edx, 0FFFFFFFFh; cAuthSvc
0x180006883  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x180006888  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x180006890  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x180006894  call    cs:__imp_CoInitializeSecurity
0x18000689a  mov     ebx, eax
0x18000689c  test    eax, eax
0x18000689e  jns     short loc_1800068AD
0x1800068a0  mov     r9d, eax
0x1800068a3  mov     edx, 14Ah
0x1800068a8  jmp     loc_18000675A
0x1800068ad  mov     ebx, edi
0x1800068af  jmp     short loc_1800068C8
0x1800068b1  mov     edx, 134h; void *
0x1800068b6  mov     rcx, [rbp+5Fh]; this
0x1800068ba  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800068c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800068c6  mov     ebx, eax
0x1800068c8  lea     rcx, [rbp+57h+var_58]
0x1800068cc  mov     [rbp+57h+var_28], dil
0x1800068d0  call    ??R_lambda_bed1b5be4148163977e87fd2fb1bced4_@@QEBA@XZ; _lambda_bed1b5be4148163977e87fd2fb1bced4_::operator()(void)
0x1800068d5  mov     eax, ebx
0x1800068d7  add     rsp, 0D8h
0x1800068de  pop     rdi
0x1800068df  pop     rsi
0x1800068e0  pop     rbx
0x1800068e1  pop     rbp
0x1800068e2  retn
```
