# AmiFixKeyPermissionsRecursive(HKEY__ *)

- ea: `0x18003a5a8`
- end: `0x18003a705`
- name: `?AmiFixKeyPermissionsRecursive@@YAKPEAUHKEY__@@@Z`
- size: `349`
- prototype: `unsigned int __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003aefc`

## callees

- `0x180005890`
- `0x1800295dc`
- `0x180039c00`
- `0x18003a5a8`
- `0x18003a70c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18003a646`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18003a646`
- `ntdll!RtlNtStatusToDosError` at `0x18003a652`
- `ntdll!RtlNtStatusToDosError` at `0x18003a652`
- `ntdll!RtlFreeSid` at `0x18003a6e5`
- `ntdll!RtlFreeSid` at `0x18003a6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a67e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a67e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6d2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003a674`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003a674`

## string_xrefs

- `0x18003a658`: `RtlAllocateAndInitializeSid failed [%d]`
- `0x18003a601`: `AmiUtilityInitSecurityDescriptor failed [%d]`
- `0x18003a684`: `SetSecurityDescriptorOwner failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiFixKeyPermissionsRecursive(HKEY a1)
{
  unsigned int inited; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  int v6; // eax
  __int64 SubAuthority2; // [rsp+20h] [rbp-59h]
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-11h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v12; // [rsp+90h] [rbp+17h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp+1Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  pOwner = 0;
  v12 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  inited = AmiUtilityInitSecurityDescriptor(pSecurityDescriptor, (PACL *)&hMem);
  v3 = inited;
  if ( inited )
  {
    v4 = "AmiUtilityInitSecurityDescriptor failed [%d]";
    v5 = 1026;
  }
  else
  {
    v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner);
    if ( v6 >= 0 )
    {
      if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
      {
        inited = AmiFixKeyPermissionsRecursiveHelper(a1, pSecurityDescriptor);
        v3 = inited;
        if ( !inited )
          goto LABEL_10;
        v4 = "AmiFixKeyPermissionsRecursiveHelper failed [%d]";
        v5 = 1061;
      }
      else
      {
        inited = GetLastError();
        v4 = "SetSecurityDescriptorOwner failed [%d]";
        v5 = 1054;
        v3 = inited;
      }
    }
    else
    {
      inited = RtlNtStatusToDosError(v6);
      v4 = "RtlAllocateAndInitializeSid failed [%d]";
      v5 = 1047;
      v3 = inited;
    }
  }
  LODWORD(SubAuthority2) = inited;
  AslLogCallPrintf(1, "AmiFixKeyPermissionsRecursive", v5, v4, SubAuthority2);
LABEL_10:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( pOwner )
    RtlFreeSid(pOwner);
  return v3;
}

```

## disassembly

```asm
0x18003a5a8  push    rbp
0x18003a5aa  push    rbx
0x18003a5ab  push    rsi
0x18003a5ac  push    rdi
0x18003a5ad  lea     rbp, [rsp-3Fh]
0x18003a5b2  sub     rsp, 0B8h
0x18003a5b9  mov     rax, cs:__security_cookie
0x18003a5c0  xor     rax, rsp
0x18003a5c3  mov     [rbp+57h+var_30], rax
0x18003a5c7  xorps   xmm0, xmm0
0x18003a5ca  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18003a5d0  xor     esi, esi
0x18003a5d2  lea     rdx, [rbp+57h+hMem]; NewAcl
0x18003a5d6  mov     rdi, rcx
0x18003a5d9  mov     [rbp+57h+hMem], rsi
0x18003a5dd  xor     eax, eax
0x18003a5df  mov     [rbp+57h+pOwner], rsi
0x18003a5e3  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18003a5e7  mov     [rbp+57h+var_40], rax
0x18003a5eb  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18003a5ef  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x18003a5f2  movups  [rbp+57h+var_50], xmm0
0x18003a5f6  call    ?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)
0x18003a5fb  mov     ebx, eax
0x18003a5fd  test    eax, eax
0x18003a5ff  jz      short loc_18003A613
0x18003a601  lea     r9, aAmiutilityinit_0; "AmiUtilityInitSecurityDescriptor failed"...
0x18003a608  mov     r8d, 402h
0x18003a60e  jmp     loc_18003A6B4
0x18003a613  lea     rax, [rbp+57h+pOwner]
0x18003a617  mov     r9d, 220h; SubAuthority1
0x18003a61d  mov     [rsp+0D0h+Sid], rax; Sid
0x18003a622  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18003a626  mov     [rsp+0D0h+SubAuthority7], esi; SubAuthority7
0x18003a62a  mov     r8d, 20h ; ' '; SubAuthority0
0x18003a630  mov     [rsp+0D0h+SubAuthority6], esi; SubAuthority6
0x18003a634  mov     dl, 2; SubAuthorityCount
0x18003a636  mov     [rsp+0D0h+SubAuthority5], esi; SubAuthority5
0x18003a63a  mov     [rsp+0D0h+SubAuthority4], esi; SubAuthority4
0x18003a63e  mov     [rsp+0D0h+SubAuthority3], esi; SubAuthority3
0x18003a642  mov     dword ptr [rsp+0D0h+SubAuthority2], esi; SubAuthority2
0x18003a646  call    cs:__imp_RtlAllocateAndInitializeSid
0x18003a64c  test    eax, eax
0x18003a64e  jns     short loc_18003A669
0x18003a650  mov     ecx, eax; Status
0x18003a652  call    cs:__imp_RtlNtStatusToDosError
0x18003a658  lea     r9, aRtlallocateand; "RtlAllocateAndInitializeSid failed [%d]"
0x18003a65f  mov     r8d, 417h
0x18003a665  mov     ebx, eax
0x18003a667  jmp     short loc_18003A6B4
0x18003a669  mov     rdx, [rbp+57h+pOwner]; pOwner
0x18003a66d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18003a671  xor     r8d, r8d; bOwnerDefaulted
0x18003a674  call    cs:__imp_SetSecurityDescriptorOwner
0x18003a67a  test    eax, eax
0x18003a67c  jnz     short loc_18003A695
0x18003a67e  call    cs:__imp_GetLastError
0x18003a684  lea     r9, aSetsecuritydes; "SetSecurityDescriptorOwner failed [%d]"
0x18003a68b  mov     r8d, 41Eh
0x18003a691  mov     ebx, eax
0x18003a693  jmp     short loc_18003A6B4
0x18003a695  lea     rdx, [rbp+57h+pSecurityDescriptor]; void *
0x18003a699  mov     rcx, rdi; HKEY
0x18003a69c  call    ?AmiFixKeyPermissionsRecursiveHelper@@YAKPEAUHKEY__@@PEAX@Z; AmiFixKeyPermissionsRecursiveHelper(HKEY__ *,void *)
0x18003a6a1  mov     ebx, eax
0x18003a6a3  test    eax, eax
0x18003a6a5  jz      short loc_18003A6C9
0x18003a6a7  lea     r9, aAmifixkeypermi_0; "AmiFixKeyPermissionsRecursiveHelper fai"...
0x18003a6ae  mov     r8d, 425h
0x18003a6b4  lea     rdx, aAmifixkeypermi_2; "AmiFixKeyPermissionsRecursive"
0x18003a6bb  mov     dword ptr [rsp+0D0h+SubAuthority2], eax
0x18003a6bf  mov     ecx, 1
0x18003a6c4  call    AslLogCallPrintf
0x18003a6c9  mov     rcx, [rbp+57h+hMem]; hMem
0x18003a6cd  test    rcx, rcx
0x18003a6d0  jz      short loc_18003A6DC
0x18003a6d2  call    cs:__imp_LocalFree
0x18003a6d8  mov     [rbp+57h+hMem], rsi
0x18003a6dc  mov     rcx, [rbp+57h+pOwner]; Sid
0x18003a6e0  test    rcx, rcx
0x18003a6e3  jz      short loc_18003A6EB
0x18003a6e5  call    cs:__imp_RtlFreeSid
0x18003a6eb  mov     eax, ebx
0x18003a6ed  mov     rcx, [rbp+57h+var_30]
0x18003a6f1  xor     rcx, rsp; StackCookie
0x18003a6f4  call    __security_check_cookie
0x18003a6f9  add     rsp, 0B8h
0x18003a700  pop     rdi
0x18003a701  pop     rsi
0x18003a702  pop     rbx
0x18003a703  pop     rbp
0x18003a704  retn
```
