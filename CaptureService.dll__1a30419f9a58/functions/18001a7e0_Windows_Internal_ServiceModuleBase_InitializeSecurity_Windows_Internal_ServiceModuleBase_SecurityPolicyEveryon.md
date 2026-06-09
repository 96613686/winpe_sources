# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)

- ea: `0x18001a7e0`
- end: `0x18001aa8b`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a538`

## callees

- `0x18000905c`
- `0x18000907c`
- `0x18001a7e0`
- `0x18001af88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001aa3c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001aa3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a8e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a928`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a94f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a976`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a9a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a8e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a928`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a94f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a976`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a8d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a91a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a968`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a8d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a91a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a968`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8c1`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001a8b3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001aa04`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001a8b3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001aa04`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a85f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a85f`

## string_xrefs

- `0x18001a906`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001aa62`: `onecore\internal\com\inc\comservicehelper.h`

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
0x18001a7e0  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x18001a7e5  push    rbp
0x18001a7e6  push    rbx
0x18001a7e7  push    rsi
0x18001a7e8  push    rdi
0x18001a7e9  lea     rbp, [rsp-3Fh]
0x18001a7ee  sub     rsp, 0D8h
0x18001a7f5  xor     edi, edi
0x18001a7f7  lea     rax, [rbp+57h+pDacl]
0x18001a7fb  mov     [rbp+57h+var_58], rax
0x18001a7ff  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001a803  lea     rax, [rbp+57h+var_70]
0x18001a807  mov     [rbp+57h+pDacl], rdi
0x18001a80b  mov     [rbp+57h+var_50], rax
0x18001a80f  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0xB;;;AC)(A;;0xB;;;WD)S:("...
0x18001a816  lea     rax, [rbp+57h+var_78]
0x18001a81a  mov     [rbp+57h+var_70], rdi
0x18001a81e  mov     [rbp+57h+var_48], rax
0x18001a822  lea     edx, [rdi+1]; StringSDRevision
0x18001a825  lea     rax, [rbp+57h+var_60]
0x18001a829  mov     [rbp+57h+var_78], rdi
0x18001a82d  mov     [rbp+57h+var_40], rax
0x18001a831  xor     r9d, r9d; SecurityDescriptorSize
0x18001a834  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x18001a838  mov     [rbp+57h+var_60], rdi
0x18001a83c  mov     [rbp+57h+var_38], rax
0x18001a840  lea     rax, [rbp+57h+SecurityDescriptor]
0x18001a844  mov     [rbp+57h+var_30], rax
0x18001a848  mov     [rbp+57h+SecurityDescriptor], rdi
0x18001a84c  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x18001a850  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18001a853  mov     [rbp+57h+dwDaclSize], edi
0x18001a856  mov     [rbp+57h+dwSaclSize], edi
0x18001a859  mov     [rbp+57h+dwOwnerSize], edi
0x18001a85c  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x18001a85f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a865  test    eax, eax
0x18001a867  jnz     short loc_18001A873
0x18001a869  mov     edx, 130h
0x18001a86e  jmp     loc_18001AA5E
0x18001a873  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18001a877  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18001a87b  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18001a880  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001a884  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x18001a889  lea     rax, [rbp+57h+dwOwnerSize]
0x18001a88d  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001a892  xor     r9d, r9d; pDacl
0x18001a895  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x18001a89a  lea     rax, [rbp+57h+dwSaclSize]
0x18001a89e  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001a8a3  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18001a8a5  lea     rax, [rbp+57h+dwDaclSize]
0x18001a8a9  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x18001a8ae  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x18001a8b3  call    cs:__imp_MakeAbsoluteSD
0x18001a8b9  test    eax, eax
0x18001a8bb  jnz     loc_18001AA59
0x18001a8c1  call    cs:__imp_GetLastError
0x18001a8c7  cmp     eax, 7Ah ; 'z'
0x18001a8ca  jnz     loc_18001AA59
0x18001a8d0  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18001a8d3  call    cs:__imp_GetProcessHeap
0x18001a8d9  mov     esi, 8
0x18001a8de  mov     r8d, ebx; dwBytes
0x18001a8e1  mov     edx, esi; dwFlags
0x18001a8e3  mov     rcx, rax; hHeap
0x18001a8e6  call    cs:__imp_HeapAlloc
0x18001a8ec  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x18001a8f0  test    rax, rax
0x18001a8f3  jnz     short loc_18001A917
0x18001a8f5  mov     edx, 138h; void *
0x18001a8fa  mov     ebx, 8007000Eh
0x18001a8ff  mov     r9d, ebx; char *
0x18001a902  mov     rcx, [rbp+5Fh]; this
0x18001a906  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a912  jmp     loc_18001AA70
0x18001a917  mov     ebx, [rbp+57h+dwDaclSize]
0x18001a91a  call    cs:__imp_GetProcessHeap
0x18001a920  mov     r8d, ebx; dwBytes
0x18001a923  mov     edx, esi; dwFlags
0x18001a925  mov     rcx, rax; hHeap
0x18001a928  call    cs:__imp_HeapAlloc
0x18001a92e  mov     [rbp+57h+pDacl], rax
0x18001a932  test    rax, rax
0x18001a935  jnz     short loc_18001A93E
0x18001a937  mov     edx, 13Bh
0x18001a93c  jmp     short loc_18001A8FA
0x18001a93e  mov     ebx, [rbp+57h+dwSaclSize]
0x18001a941  call    cs:__imp_GetProcessHeap
0x18001a947  mov     r8d, ebx; dwBytes
0x18001a94a  mov     edx, esi; dwFlags
0x18001a94c  mov     rcx, rax; hHeap
0x18001a94f  call    cs:__imp_HeapAlloc
0x18001a955  mov     [rbp+57h+var_70], rax
0x18001a959  test    rax, rax
0x18001a95c  jnz     short loc_18001A965
0x18001a95e  mov     edx, 13Eh
0x18001a963  jmp     short loc_18001A8FA
0x18001a965  mov     ebx, [rbp+57h+dwOwnerSize]
0x18001a968  call    cs:__imp_GetProcessHeap
0x18001a96e  mov     r8d, ebx; dwBytes
0x18001a971  mov     edx, esi; dwFlags
0x18001a973  mov     rcx, rax; hHeap
0x18001a976  call    cs:__imp_HeapAlloc
0x18001a97c  mov     [rbp+57h+var_78], rax
0x18001a980  test    rax, rax
0x18001a983  jnz     short loc_18001A98F
0x18001a985  mov     edx, 141h
0x18001a98a  jmp     loc_18001A8FA
0x18001a98f  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x18001a992  call    cs:__imp_GetProcessHeap
0x18001a998  mov     r8d, ebx; dwBytes
0x18001a99b  mov     edx, esi; dwFlags
0x18001a99d  mov     rcx, rax; hHeap
0x18001a9a0  call    cs:__imp_HeapAlloc
0x18001a9a6  mov     [rbp+57h+var_60], rax
0x18001a9aa  test    rax, rax
0x18001a9ad  jnz     short loc_18001A9B9
0x18001a9af  mov     edx, 144h
0x18001a9b4  jmp     loc_18001A8FA
0x18001a9b9  mov     r9, [rbp+57h+pDacl]; pDacl
0x18001a9bd  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x18001a9c1  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18001a9c5  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001a9c9  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18001a9ce  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18001a9d2  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x18001a9d7  lea     rax, [rbp+57h+dwOwnerSize]
0x18001a9db  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001a9e0  mov     rax, [rbp+57h+var_78]
0x18001a9e4  mov     [rsp+0F0h+pOwner], rax; pOwner
0x18001a9e9  lea     rax, [rbp+57h+dwSaclSize]
0x18001a9ed  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001a9f2  mov     rax, [rbp+57h+var_70]
0x18001a9f6  mov     [rsp+0F0h+pSacl], rax; pSacl
0x18001a9fb  lea     rax, [rbp+57h+dwDaclSize]
0x18001a9ff  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x18001aa04  call    cs:__imp_MakeAbsoluteSD
0x18001aa0a  test    eax, eax
0x18001aa0c  jnz     short loc_18001AA15
0x18001aa0e  mov     edx, 147h
0x18001aa13  jmp     short loc_18001AA5E
0x18001aa15  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x18001aa19  xor     r9d, r9d; pReserved1
0x18001aa1c  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x18001aa21  xor     r8d, r8d; asAuthSvc
0x18001aa24  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x18001aa28  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001aa2b  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x18001aa30  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x18001aa38  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x18001aa3c  call    cs:__imp_CoInitializeSecurity
0x18001aa42  mov     ebx, eax
0x18001aa44  test    eax, eax
0x18001aa46  jns     short loc_18001AA55
0x18001aa48  mov     r9d, eax
0x18001aa4b  mov     edx, 14Ah
0x18001aa50  jmp     loc_18001A902
0x18001aa55  mov     ebx, edi
0x18001aa57  jmp     short loc_18001AA70
0x18001aa59  mov     edx, 134h; void *
0x18001aa5e  mov     rcx, [rbp+5Fh]; this
0x18001aa62  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001aa69  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001aa6e  mov     ebx, eax
0x18001aa70  lea     rcx, [rbp+57h+var_58]
0x18001aa74  mov     [rbp+57h+var_28], dil
0x18001aa78  call    ??R_lambda_f43ef05b8ea00435162459fb60b25850_@@QEBA@XZ; _lambda_f43ef05b8ea00435162459fb60b25850_::operator()(void)
0x18001aa7d  mov     eax, ebx
0x18001aa7f  add     rsp, 0D8h
0x18001aa86  pop     rdi
0x18001aa87  pop     rsi
0x18001aa88  pop     rbx
0x18001aa89  pop     rbp
0x18001aa8a  retn
```
