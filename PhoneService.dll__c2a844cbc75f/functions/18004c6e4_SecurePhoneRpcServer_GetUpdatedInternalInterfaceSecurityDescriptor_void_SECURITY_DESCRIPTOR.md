# SecurePhoneRpcServer::_GetUpdatedInternalInterfaceSecurityDescriptor(void *,_SECURITY_DESCRIPTOR * *)

- ea: `0x18004c6e4`
- end: `0x18004c902`
- name: `?_GetUpdatedInternalInterfaceSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(SecurePhoneRpcServer *this, void *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d180`

## callees

- `0x180006e94`
- `0x18004c528`
- `0x18004c6e4`
- `0x18004cb0c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c7fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c88a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c7fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c88a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c730`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004c730`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004c7b5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004c7b5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004c849`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004c849`

## string_xrefs

- `0x18004c75c`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004c7e1`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004c86f`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`

## pseudocode

```c
__int64 __fastcall SecurePhoneRpcServer::_GetUpdatedInternalInterfaceSecurityDescriptor(
        SecurePhoneRpcServer *this,
        void *a2,
        struct _SECURITY_DESCRIPTOR **a3)
{
  signed int LastError; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  signed int v9; // eax
  BackTraceCollection *v10; // rcx
  signed int v11; // eax
  BackTraceCollection *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rdx
  int UpdatedSecurityDescriptor; // eax
  BackTraceCollection *v16; // rcx
  PACL pDacl; // [rsp+60h] [rbp-19h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp+1Fh] BYREF
  PSID hMem; // [rsp+A0h] [rbp+27h] BYREF
  PACL NewAcl; // [rsp+A8h] [rbp+2Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+B0h] [rbp+37h] BYREF
  WINBOOL bDaclPresent; // [rsp+B4h] [rbp+3Bh] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v6, v7);
    Log_HREvent_8(v7, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 190);
    return v7;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 6u, 0x54u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    BackTraceCollection::Capture(v10, v7);
    Log_HREvent_8(v7, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 207);
LABEL_10:
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)hMem;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  pListOfExplicitEntries.grfAccessPermissions = 2031616;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
  NewAcl = 0;
  v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
  v7 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    BackTraceCollection::Capture(v12, v7);
    v13 = 223;
    v14 = 0;
    goto LABEL_16;
  }
  UpdatedSecurityDescriptor = SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(v12, a2, NewAcl, a3);
  v7 = UpdatedSecurityDescriptor;
  if ( UpdatedSecurityDescriptor < 0 )
  {
    BackTraceCollection::Capture(v16, UpdatedSecurityDescriptor);
    v13 = 228;
    v14 = 1;
LABEL_16:
    Log_HREvent_8(v7, v14, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", v13);
    if ( NewAcl )
      LocalFree(NewAcl);
    goto LABEL_10;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18004c6e4  mov     [rsp-8+arg_0], rbx
0x18004c6e9  mov     [rsp-8+arg_18], rsi
0x18004c6ee  push    rbp
0x18004c6ef  push    rdi
0x18004c6f0  push    r14
0x18004c6f2  lea     rbp, [rsp-47h]
0x18004c6f7  sub     rsp, 0C0h
0x18004c6fe  mov     rax, cs:__security_cookie
0x18004c705  xor     rax, rsp
0x18004c708  mov     [rbp+57h+var_18], rax
0x18004c70c  mov     rdi, rdx
0x18004c70f  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18004c713  xor     r14d, r14d
0x18004c716  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18004c71a  mov     rsi, r8
0x18004c71d  mov     [rbp+57h+pDacl], r14
0x18004c721  mov     rcx, rdi; pSecurityDescriptor
0x18004c724  mov     [rbp+57h+bDaclPresent], r14d
0x18004c728  lea     r8, [rbp+57h+pDacl]; pDacl
0x18004c72c  mov     [rbp+57h+bDaclDefaulted], r14d
0x18004c730  call    cs:__imp_GetSecurityDescriptorDacl
0x18004c736  test    eax, eax
0x18004c738  jnz     short loc_18004C773
0x18004c73a  call    cs:__imp_GetLastError
0x18004c740  mov     ebx, eax
0x18004c742  test    eax, eax
0x18004c744  jle     short loc_18004C74F
0x18004c746  movzx   ebx, ax
0x18004c749  or      ebx, 80070000h
0x18004c74f  mov     edx, ebx; int
0x18004c751  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c756  mov     r9d, 0BEh
0x18004c75c  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004c763  xor     edx, edx
0x18004c765  mov     ecx, ebx
0x18004c767  call    Log_HREvent_8
0x18004c76c  mov     eax, ebx
0x18004c76e  jmp     loc_18004C8DE
0x18004c773  lea     rax, [rbp+57h+hMem]
0x18004c777  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18004c77b  mov     [rsp+0D0h+pSid], rax; pSid
0x18004c780  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004c784  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18004c789  xor     r9d, r9d; nSubAuthority1
0x18004c78c  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x18004c791  mov     dl, 6; nSubAuthorityCount
0x18004c793  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x18004c798  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18004c79d  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18004c7a2  lea     r8d, [r9+54h]; nSubAuthority0
0x18004c7a6  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x18004c7ab  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18004c7b1  mov     [rbp+57h+hMem], r14
0x18004c7b5  call    cs:__imp_AllocateAndInitializeSid
0x18004c7bb  test    eax, eax
0x18004c7bd  jnz     short loc_18004C809
0x18004c7bf  call    cs:__imp_GetLastError
0x18004c7c5  mov     ebx, eax
0x18004c7c7  test    eax, eax
0x18004c7c9  jle     short loc_18004C7D4
0x18004c7cb  movzx   ebx, ax
0x18004c7ce  or      ebx, 80070000h
0x18004c7d4  mov     edx, ebx; int
0x18004c7d6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c7db  mov     r9d, 0CFh
0x18004c7e1  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004c7e8  xor     edx, edx
0x18004c7ea  mov     ecx, ebx
0x18004c7ec  call    Log_HREvent_8
0x18004c7f1  mov     rcx, [rbp+57h+hMem]; hMem
0x18004c7f5  test    rcx, rcx
0x18004c7f8  jz      loc_18004C76C
0x18004c7fe  call    cs:__imp_LocalFree
0x18004c804  jmp     loc_18004C76C
0x18004c809  mov     rax, [rbp+57h+hMem]
0x18004c80d  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18004c811  mov     r8, [rbp+57h+pDacl]; OldAcl
0x18004c815  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004c819  xorps   xmm0, xmm0
0x18004c81c  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18004c820  mov     ecx, 1; cCountOfExplicitEntries
0x18004c825  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x18004c82d  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x18004c832  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 1F0000h
0x18004c839  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x18004c841  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18004c845  mov     [rbp+57h+NewAcl], r14
0x18004c849  call    cs:__imp_SetEntriesInAclW
0x18004c84f  mov     ebx, eax
0x18004c851  test    eax, eax
0x18004c853  jz      short loc_18004C895
0x18004c855  jle     short loc_18004C860
0x18004c857  movzx   ebx, ax
0x18004c85a  or      ebx, 80070000h
0x18004c860  mov     edx, ebx; int
0x18004c862  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c867  mov     r9d, 0DFh
0x18004c86d  xor     edx, edx
0x18004c86f  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004c876  mov     ecx, ebx
0x18004c878  call    Log_HREvent_8
0x18004c87d  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18004c881  test    rcx, rcx
0x18004c884  jz      loc_18004C7F1
0x18004c88a  call    cs:__imp_LocalFree
0x18004c890  jmp     loc_18004C7F1
0x18004c895  mov     r8, [rbp+57h+NewAcl]; struct _ACL *
0x18004c899  mov     r9, rsi; struct _SECURITY_DESCRIPTOR **
0x18004c89c  mov     rdx, rdi; void *
0x18004c89f  call    ?_GetUpdatedSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAXPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z; SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(void *,_ACL *,_SECURITY_DESCRIPTOR * *)
0x18004c8a4  mov     ebx, eax
0x18004c8a6  test    eax, eax
0x18004c8a8  jns     short loc_18004C8BE
0x18004c8aa  mov     edx, eax; int
0x18004c8ac  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004c8b1  mov     r9d, 0E4h
0x18004c8b7  mov     edx, 1
0x18004c8bc  jmp     short loc_18004C86F
0x18004c8be  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18004c8c2  test    rcx, rcx
0x18004c8c5  jz      short loc_18004C8CD
0x18004c8c7  call    cs:__imp_LocalFree
0x18004c8cd  mov     rcx, [rbp+57h+hMem]; hMem
0x18004c8d1  test    rcx, rcx
0x18004c8d4  jz      short loc_18004C8DC
0x18004c8d6  call    cs:__imp_LocalFree
0x18004c8dc  xor     eax, eax
0x18004c8de  mov     rcx, [rbp+57h+var_18]
0x18004c8e2  xor     rcx, rsp; StackCookie
0x18004c8e5  call    __security_check_cookie
0x18004c8ea  lea     r11, [rsp+0D0h+var_10]
0x18004c8f2  mov     rbx, [r11+20h]
0x18004c8f6  mov     rsi, [r11+38h]
0x18004c8fa  mov     rsp, r11
0x18004c8fd  pop     r14
0x18004c8ff  pop     rdi
0x18004c900  pop     rbp
0x18004c901  retn
```
