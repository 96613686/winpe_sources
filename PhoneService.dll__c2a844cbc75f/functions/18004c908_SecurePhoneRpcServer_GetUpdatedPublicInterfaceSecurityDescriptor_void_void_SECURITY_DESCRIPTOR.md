# SecurePhoneRpcServer::_GetUpdatedPublicInterfaceSecurityDescriptor(void *,void *,_SECURITY_DESCRIPTOR * *)

- ea: `0x18004c908`
- end: `0x18004cb03`
- name: `?_GetUpdatedPublicInterfaceSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAX0PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(SecurePhoneRpcServer *this, void *, void *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d180`

## callees

- `0x180006e94`
- `0x18004c528`
- `0x18004c908`
- `0x18004cb0c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ca37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ca96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cadf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ca37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ca96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cadf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c953`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c9ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c953`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c9ad`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004ca59`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004ca59`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004c9f6`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18004c9f6`

## string_xrefs

- `0x18004c97f`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004ca1a`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004ca7f`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`

## pseudocode

```c
__int64 __fastcall SecurePhoneRpcServer::_GetUpdatedPublicInterfaceSecurityDescriptor(
        SecurePhoneRpcServer *this,
        void *a2,
        void *a3,
        struct _SECURITY_DESCRIPTOR **a4)
{
  signed int LastError; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r9
  signed int v12; // eax
  BackTraceCollection *v13; // rcx
  signed int ExplicitEntriesFromAclW; // eax
  BackTraceCollection *v15; // rcx
  signed int v16; // eax
  BackTraceCollection *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  int UpdatedSecurityDescriptor; // eax
  BackTraceCollection *v21; // rcx
  PACL pacl; // [rsp+30h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-38h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  WINBOOL bDaclPresent; // [rsp+4Ch] [rbp-24h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+50h] [rbp-20h] BYREF
  PACL NewAcl; // [rsp+58h] [rbp-18h] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v8, v9);
    v10 = 246;
LABEL_5:
    Log_HREvent_8(v9, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", v10);
    return v9;
  }
  pacl = 0;
  if ( !GetSecurityDescriptorDacl(a3, &bDaclPresent, &pacl, &bDaclDefaulted) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    BackTraceCollection::Capture(v13, v9);
    v10 = 252;
    goto LABEL_5;
  }
  pcCountOfExplicitEntries = 0;
  pListOfExplicitEntries = 0;
  ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(pacl, &pcCountOfExplicitEntries, &pListOfExplicitEntries);
  v9 = ExplicitEntriesFromAclW;
  if ( ExplicitEntriesFromAclW )
  {
    if ( ExplicitEntriesFromAclW > 0 )
      v9 = (unsigned __int16)ExplicitEntriesFromAclW | 0x80070000;
    BackTraceCollection::Capture(v15, v9);
    Log_HREvent_8(v9, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 256);
LABEL_15:
    if ( pListOfExplicitEntries )
      LocalFree(pListOfExplicitEntries);
    return v9;
  }
  NewAcl = 0;
  v16 = SetEntriesInAclW(pcCountOfExplicitEntries, pListOfExplicitEntries, pDacl, &NewAcl);
  v9 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    BackTraceCollection::Capture(v17, v9);
    v18 = 261;
    v19 = 0;
    goto LABEL_21;
  }
  UpdatedSecurityDescriptor = SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(v17, a2, NewAcl, a4);
  v9 = UpdatedSecurityDescriptor;
  if ( UpdatedSecurityDescriptor < 0 )
  {
    BackTraceCollection::Capture(v21, UpdatedSecurityDescriptor);
    v18 = 266;
    v19 = 1;
LABEL_21:
    Log_HREvent_8(v9, v19, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", v18);
    if ( NewAcl )
      LocalFree(NewAcl);
    goto LABEL_15;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pListOfExplicitEntries )
    LocalFree(pListOfExplicitEntries);
  return 0;
}

```

## disassembly

```asm
0x18004c908  mov     [rsp-18h+arg_0], rbx
0x18004c90d  push    rbp
0x18004c90e  push    rsi
0x18004c90f  push    rdi
0x18004c910  mov     rbp, rsp
0x18004c913  sub     rsp, 70h
0x18004c917  mov     rax, cs:__security_cookie
0x18004c91e  xor     rax, rsp
0x18004c921  mov     [rbp+var_10], rax
0x18004c925  mov     rdi, rdx
0x18004c928  mov     [rbp+pDacl], 0
0x18004c930  mov     rsi, r9
0x18004c933  mov     [rbp+bDaclPresent], 0
0x18004c93a  mov     rbx, r8
0x18004c93d  mov     [rbp+bDaclDefaulted], 0
0x18004c944  mov     rcx, rdi; pSecurityDescriptor
0x18004c947  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18004c94b  lea     r8, [rbp+pDacl]; pDacl
0x18004c94f  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004c953  call    cs:__imp_GetSecurityDescriptorDacl
0x18004c959  test    eax, eax
0x18004c95b  jnz     short loc_18004C996
0x18004c95d  call    cs:__imp_GetLastError
0x18004c963  mov     ebx, eax
0x18004c965  test    eax, eax
0x18004c967  jle     short loc_18004C972
0x18004c969  movzx   ebx, ax
0x18004c96c  or      ebx, 80070000h
0x18004c972  mov     edx, ebx; int
0x18004c974  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c979  mov     r9d, 0F6h
0x18004c97f  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004c986  xor     edx, edx
0x18004c988  mov     ecx, ebx
0x18004c98a  call    Log_HREvent_8
0x18004c98f  mov     eax, ebx
0x18004c991  jmp     loc_18004CAE7
0x18004c996  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18004c99a  mov     [rbp+pacl], 0
0x18004c9a2  lea     r8, [rbp+pacl]; pDacl
0x18004c9a6  mov     rcx, rbx; pSecurityDescriptor
0x18004c9a9  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004c9ad  call    cs:__imp_GetSecurityDescriptorDacl
0x18004c9b3  test    eax, eax
0x18004c9b5  jnz     short loc_18004C9DB
0x18004c9b7  call    cs:__imp_GetLastError
0x18004c9bd  mov     ebx, eax
0x18004c9bf  test    eax, eax
0x18004c9c1  jle     short loc_18004C9CC
0x18004c9c3  movzx   ebx, ax
0x18004c9c6  or      ebx, 80070000h
0x18004c9cc  mov     edx, ebx; int
0x18004c9ce  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c9d3  mov     r9d, 0FCh
0x18004c9d9  jmp     short loc_18004C97F
0x18004c9db  mov     rcx, [rbp+pacl]; pacl
0x18004c9df  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004c9e3  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18004c9e7  mov     [rbp+pcCountOfExplicitEntries], 0
0x18004c9ee  mov     [rbp+pListOfExplicitEntries], 0
0x18004c9f6  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004c9fc  mov     ebx, eax
0x18004c9fe  test    eax, eax
0x18004ca00  jz      short loc_18004CA42
0x18004ca02  jle     short loc_18004CA0D
0x18004ca04  movzx   ebx, ax
0x18004ca07  or      ebx, 80070000h
0x18004ca0d  mov     edx, ebx; int
0x18004ca0f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004ca14  mov     r9d, 100h
0x18004ca1a  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004ca21  xor     edx, edx
0x18004ca23  mov     ecx, ebx
0x18004ca25  call    Log_HREvent_8
0x18004ca2a  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x18004ca2e  test    rcx, rcx
0x18004ca31  jz      loc_18004C98F
0x18004ca37  call    cs:__imp_LocalFree
0x18004ca3d  jmp     loc_18004C98F
0x18004ca42  mov     r8, [rbp+pDacl]; OldAcl
0x18004ca46  lea     r9, [rbp+NewAcl]; NewAcl
0x18004ca4a  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004ca4e  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x18004ca51  mov     [rbp+NewAcl], 0
0x18004ca59  call    cs:__imp_SetEntriesInAclW
0x18004ca5f  mov     ebx, eax
0x18004ca61  test    eax, eax
0x18004ca63  jz      short loc_18004CA9E
0x18004ca65  jle     short loc_18004CA70
0x18004ca67  movzx   ebx, ax
0x18004ca6a  or      ebx, 80070000h
0x18004ca70  mov     edx, ebx; int
0x18004ca72  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004ca77  mov     r9d, 105h
0x18004ca7d  xor     edx, edx
0x18004ca7f  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004ca86  mov     ecx, ebx
0x18004ca88  call    Log_HREvent_8
0x18004ca8d  mov     rcx, [rbp+NewAcl]; hMem
0x18004ca91  test    rcx, rcx
0x18004ca94  jz      short loc_18004CA2A
0x18004ca96  call    cs:__imp_LocalFree
0x18004ca9c  jmp     short loc_18004CA2A
0x18004ca9e  mov     r8, [rbp+NewAcl]; struct _ACL *
0x18004caa2  mov     r9, rsi; struct _SECURITY_DESCRIPTOR **
0x18004caa5  mov     rdx, rdi; void *
0x18004caa8  call    ?_GetUpdatedSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAXPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z; SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(void *,_ACL *,_SECURITY_DESCRIPTOR * *)
0x18004caad  mov     ebx, eax
0x18004caaf  test    eax, eax
0x18004cab1  jns     short loc_18004CAC7
0x18004cab3  mov     edx, eax; int
0x18004cab5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004caba  mov     r9d, 10Ah
0x18004cac0  mov     edx, 1
0x18004cac5  jmp     short loc_18004CA7F
0x18004cac7  mov     rcx, [rbp+NewAcl]; hMem
0x18004cacb  test    rcx, rcx
0x18004cace  jz      short loc_18004CAD6
0x18004cad0  call    cs:__imp_LocalFree
0x18004cad6  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x18004cada  test    rcx, rcx
0x18004cadd  jz      short loc_18004CAE5
0x18004cadf  call    cs:__imp_LocalFree
0x18004cae5  xor     eax, eax
0x18004cae7  mov     rcx, [rbp+var_10]
0x18004caeb  xor     rcx, rsp; StackCookie
0x18004caee  call    __security_check_cookie
0x18004caf3  mov     rbx, [rsp+70h+arg_0]
0x18004cafb  add     rsp, 70h
0x18004caff  pop     rdi
0x18004cb00  pop     rsi
0x18004cb01  pop     rbp
0x18004cb02  retn
```
