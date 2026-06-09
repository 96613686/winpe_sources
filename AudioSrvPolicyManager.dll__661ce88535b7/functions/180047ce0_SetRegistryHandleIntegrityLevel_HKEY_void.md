# SetRegistryHandleIntegrityLevel(HKEY__ *,void *)

- ea: `0x180047ce0`
- end: `0x180047dc8`
- name: `?SetRegistryHandleIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(HKEY Handle, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f9d0`
- `0x1800101ac`
- `0x1800478e4`

## callees

- `0x1800109d0`
- `0x18001237c`
- `0x180047ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d93`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180047d72`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180047d72`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180047d57`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180047d57`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180047d89`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180047d89`

## pseudocode

```c
__int64 __fastcall SetRegistryHandleIntegrityLevel(HKEY Handle, void *a2)
{
  signed int v3; // ebx
  int v4; // eax
  signed int LastError; // eax
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  unsigned int v9; // [rsp+68h] [rbp+10h] BYREF
  PACL pSacl; // [rsp+70h] [rbp+18h] BYREF

  v3 = -2147024809;
  if ( a2 && Handle != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    pSacl = 0;
    v9 = 0;
    v4 = AddSidToSACL(Handle, a2, &pSacl, &v9);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      v8 = 0;
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        || !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, pSacl, 0)
        || !SetKernelObjectSecurity(Handle, 0x10u, pSecurityDescriptor) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( pSacl )
        operator delete(pSacl);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180047ce0  mov     rax, rsp
0x180047ce3  mov     [rax+8], rbx
0x180047ce7  mov     [rax+20h], rbp
0x180047ceb  push    rdi
0x180047cec  sub     rsp, 50h
0x180047cf0  mov     rdi, rcx
0x180047cf3  mov     ebx, 80070057h
0x180047cf8  test    rdx, rdx
0x180047cfb  jz      loc_180047DB6
0x180047d01  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180047d05  jz      loc_180047DB6
0x180047d0b  lea     r9, [rax+10h]; unsigned int *
0x180047d0f  mov     qword ptr [rax+18h], 0
0x180047d17  lea     r8, [rax+18h]; struct _ACL **
0x180047d1b  mov     dword ptr [rax+10h], 0
0x180047d22  call    ?AddSidToSACL@@YAKPEAUHKEY__@@PEAXPEAPEAU_ACL@@PEAK@Z; AddSidToSACL(HKEY__ *,void *,_ACL * *,ulong *)
0x180047d27  mov     ebx, eax
0x180047d29  mov     ebp, 80070000h
0x180047d2e  test    eax, eax
0x180047d30  jle     short loc_180047D37
0x180047d32  movzx   ebx, ax
0x180047d35  or      ebx, ebp
0x180047d37  test    ebx, ebx
0x180047d39  js      short loc_180047DB6
0x180047d3b  xor     eax, eax
0x180047d3d  lea     rcx, [rsp+58h+pSecurityDescriptor]; pSecurityDescriptor
0x180047d42  xorps   xmm0, xmm0
0x180047d45  mov     [rsp+58h+var_18], rax
0x180047d4a  movups  [rsp+58h+pSecurityDescriptor], xmm0
0x180047d4f  lea     edx, [rax+1]; dwRevision
0x180047d52  movups  [rsp+58h+var_28], xmm0
0x180047d57  call    cs:__imp_InitializeSecurityDescriptor
0x180047d5d  test    eax, eax
0x180047d5f  jz      short loc_180047D93
0x180047d61  mov     r8, [rsp+58h+pSacl]; pSacl
0x180047d66  lea     rcx, [rsp+58h+pSecurityDescriptor]; pSecurityDescriptor
0x180047d6b  xor     r9d, r9d; bSaclDefaulted
0x180047d6e  lea     edx, [r9+1]; bSaclPresent
0x180047d72  call    cs:__imp_SetSecurityDescriptorSacl
0x180047d78  test    eax, eax
0x180047d7a  jz      short loc_180047D93
0x180047d7c  lea     r8, [rsp+58h+pSecurityDescriptor]; SecurityDescriptor
0x180047d81  mov     edx, 10h; SecurityInformation
0x180047d86  mov     rcx, rdi; Handle
0x180047d89  call    cs:__imp_SetKernelObjectSecurity
0x180047d8f  test    eax, eax
0x180047d91  jnz     short loc_180047DA4
0x180047d93  call    cs:__imp_GetLastError
0x180047d99  mov     ebx, eax
0x180047d9b  test    eax, eax
0x180047d9d  jle     short loc_180047DA4
0x180047d9f  movzx   ebx, ax
0x180047da2  or      ebx, ebp
0x180047da4  cmp     [rsp+58h+pSacl], 0
0x180047daa  jz      short loc_180047DB6
0x180047dac  mov     rcx, [rsp+58h+pSacl]; void *
0x180047db1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047db6  mov     rbp, [rsp+58h+arg_18]
0x180047dbb  mov     eax, ebx
0x180047dbd  mov     rbx, [rsp+58h+arg_0]
0x180047dc2  add     rsp, 50h
0x180047dc6  pop     rdi
0x180047dc7  retn
```
