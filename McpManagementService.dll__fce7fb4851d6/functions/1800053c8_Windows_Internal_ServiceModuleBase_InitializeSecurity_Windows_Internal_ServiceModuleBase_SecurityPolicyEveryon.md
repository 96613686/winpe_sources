# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)

- ea: `0x1800053c8`
- end: `0x180005673`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800050e4`

## callees

- `0x1800053c8`
- `0x180007bac`
- `0x18000c4ac`
- `0x18000c4cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180005624`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180005624`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000549b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800055ec`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000549b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800055ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005550`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000557a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005550`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000557a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005537`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000555e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005588`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005537`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000555e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005447`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005447`

## string_xrefs

- `0x1800054ee`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000564a`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  v28 = 0;
  _lambda_f43ef05b8ea00435162459fb60b25850_::operator()(v27);
  return LastError;
}

```

## disassembly

```asm
0x1800053c8  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x1800053cd  push    rbp
0x1800053ce  push    rbx
0x1800053cf  push    rsi
0x1800053d0  push    rdi
0x1800053d1  lea     rbp, [rsp-3Fh]
0x1800053d6  sub     rsp, 0D8h
0x1800053dd  xor     edi, edi
0x1800053df  lea     rax, [rbp+57h+pDacl]
0x1800053e3  mov     [rbp+57h+var_58], rax
0x1800053e7  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800053eb  lea     rax, [rbp+57h+var_70]
0x1800053ef  mov     [rbp+57h+pDacl], rdi
0x1800053f3  mov     [rbp+57h+var_50], rax
0x1800053f7  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:("...
0x1800053fe  lea     rax, [rbp+57h+var_78]
0x180005402  mov     [rbp+57h+var_70], rdi
0x180005406  mov     [rbp+57h+var_48], rax
0x18000540a  lea     edx, [rdi+1]; StringSDRevision
0x18000540d  lea     rax, [rbp+57h+var_60]
0x180005411  mov     [rbp+57h+var_78], rdi
0x180005415  mov     [rbp+57h+var_40], rax
0x180005419  xor     r9d, r9d; SecurityDescriptorSize
0x18000541c  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180005420  mov     [rbp+57h+var_60], rdi
0x180005424  mov     [rbp+57h+var_38], rax
0x180005428  lea     rax, [rbp+57h+SecurityDescriptor]
0x18000542c  mov     [rbp+57h+var_30], rax
0x180005430  mov     [rbp+57h+SecurityDescriptor], rdi
0x180005434  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x180005438  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18000543b  mov     [rbp+57h+dwDaclSize], edi
0x18000543e  mov     [rbp+57h+dwSaclSize], edi
0x180005441  mov     [rbp+57h+dwOwnerSize], edi
0x180005444  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x180005447  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000544d  test    eax, eax
0x18000544f  jnz     short loc_18000545B
0x180005451  mov     edx, 130h
0x180005456  jmp     loc_180005646
0x18000545b  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000545f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180005463  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180005468  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000546c  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x180005471  lea     rax, [rbp+57h+dwOwnerSize]
0x180005475  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000547a  xor     r9d, r9d; pDacl
0x18000547d  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x180005482  lea     rax, [rbp+57h+dwSaclSize]
0x180005486  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000548b  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18000548d  lea     rax, [rbp+57h+dwDaclSize]
0x180005491  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x180005496  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x18000549b  call    cs:__imp_MakeAbsoluteSD
0x1800054a1  test    eax, eax
0x1800054a3  jnz     loc_180005641
0x1800054a9  call    cs:__imp_GetLastError
0x1800054af  cmp     eax, 7Ah ; 'z'
0x1800054b2  jnz     loc_180005641
0x1800054b8  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x1800054bb  call    cs:__imp_GetProcessHeap
0x1800054c1  mov     esi, 8
0x1800054c6  mov     r8d, ebx; dwBytes
0x1800054c9  mov     edx, esi; dwFlags
0x1800054cb  mov     rcx, rax; hHeap
0x1800054ce  call    cs:__imp_HeapAlloc
0x1800054d4  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x1800054d8  test    rax, rax
0x1800054db  jnz     short loc_1800054FF
0x1800054dd  mov     edx, 138h; void *
0x1800054e2  mov     ebx, 8007000Eh
0x1800054e7  mov     r9d, ebx; char *
0x1800054ea  mov     rcx, [rbp+5Fh]; this
0x1800054ee  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800054f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054fa  jmp     loc_180005658
0x1800054ff  mov     ebx, [rbp+57h+dwDaclSize]
0x180005502  call    cs:__imp_GetProcessHeap
0x180005508  mov     r8d, ebx; dwBytes
0x18000550b  mov     edx, esi; dwFlags
0x18000550d  mov     rcx, rax; hHeap
0x180005510  call    cs:__imp_HeapAlloc
0x180005516  mov     [rbp+57h+pDacl], rax
0x18000551a  test    rax, rax
0x18000551d  jnz     short loc_180005526
0x18000551f  mov     edx, 13Bh
0x180005524  jmp     short loc_1800054E2
0x180005526  mov     ebx, [rbp+57h+dwSaclSize]
0x180005529  call    cs:__imp_GetProcessHeap
0x18000552f  mov     r8d, ebx; dwBytes
0x180005532  mov     edx, esi; dwFlags
0x180005534  mov     rcx, rax; hHeap
0x180005537  call    cs:__imp_HeapAlloc
0x18000553d  mov     [rbp+57h+var_70], rax
0x180005541  test    rax, rax
0x180005544  jnz     short loc_18000554D
0x180005546  mov     edx, 13Eh
0x18000554b  jmp     short loc_1800054E2
0x18000554d  mov     ebx, [rbp+57h+dwOwnerSize]
0x180005550  call    cs:__imp_GetProcessHeap
0x180005556  mov     r8d, ebx; dwBytes
0x180005559  mov     edx, esi; dwFlags
0x18000555b  mov     rcx, rax; hHeap
0x18000555e  call    cs:__imp_HeapAlloc
0x180005564  mov     [rbp+57h+var_78], rax
0x180005568  test    rax, rax
0x18000556b  jnz     short loc_180005577
0x18000556d  mov     edx, 141h
0x180005572  jmp     loc_1800054E2
0x180005577  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x18000557a  call    cs:__imp_GetProcessHeap
0x180005580  mov     r8d, ebx; dwBytes
0x180005583  mov     edx, esi; dwFlags
0x180005585  mov     rcx, rax; hHeap
0x180005588  call    cs:__imp_HeapAlloc
0x18000558e  mov     [rbp+57h+var_60], rax
0x180005592  test    rax, rax
0x180005595  jnz     short loc_1800055A1
0x180005597  mov     edx, 144h
0x18000559c  jmp     loc_1800054E2
0x1800055a1  mov     r9, [rbp+57h+pDacl]; pDacl
0x1800055a5  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x1800055a9  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800055ad  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800055b1  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x1800055b6  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800055ba  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x1800055bf  lea     rax, [rbp+57h+dwOwnerSize]
0x1800055c3  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800055c8  mov     rax, [rbp+57h+var_78]
0x1800055cc  mov     [rsp+0F0h+pOwner], rax; pOwner
0x1800055d1  lea     rax, [rbp+57h+dwSaclSize]
0x1800055d5  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800055da  mov     rax, [rbp+57h+var_70]
0x1800055de  mov     [rsp+0F0h+pSacl], rax; pSacl
0x1800055e3  lea     rax, [rbp+57h+dwDaclSize]
0x1800055e7  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800055ec  call    cs:__imp_MakeAbsoluteSD
0x1800055f2  test    eax, eax
0x1800055f4  jnz     short loc_1800055FD
0x1800055f6  mov     edx, 147h
0x1800055fb  jmp     short loc_180005646
0x1800055fd  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x180005601  xor     r9d, r9d; pReserved1
0x180005604  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x180005609  xor     r8d, r8d; asAuthSvc
0x18000560c  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x180005610  or      edx, 0FFFFFFFFh; cAuthSvc
0x180005613  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x180005618  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x180005620  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x180005624  call    cs:__imp_CoInitializeSecurity
0x18000562a  mov     ebx, eax
0x18000562c  test    eax, eax
0x18000562e  jns     short loc_18000563D
0x180005630  mov     r9d, eax
0x180005633  mov     edx, 14Ah
0x180005638  jmp     loc_1800054EA
0x18000563d  mov     ebx, edi
0x18000563f  jmp     short loc_180005658
0x180005641  mov     edx, 134h; void *
0x180005646  mov     rcx, [rbp+5Fh]; this
0x18000564a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180005651  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005656  mov     ebx, eax
0x180005658  lea     rcx, [rbp+57h+var_58]
0x18000565c  mov     [rbp+57h+var_28], dil
0x180005660  call    ??R_lambda_f43ef05b8ea00435162459fb60b25850_@@QEBA@XZ; _lambda_f43ef05b8ea00435162459fb60b25850_::operator()(void)
0x180005665  mov     eax, ebx
0x180005667  add     rsp, 0D8h
0x18000566e  pop     rdi
0x18000566f  pop     rsi
0x180005670  pop     rbx
0x180005671  pop     rbp
0x180005672  retn
```
