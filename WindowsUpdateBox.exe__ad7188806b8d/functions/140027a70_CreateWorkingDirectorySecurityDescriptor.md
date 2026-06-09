# CreateWorkingDirectorySecurityDescriptor

- ea: `0x140027a70`
- end: `0x140027f04`
- name: `CreateWorkingDirectorySecurityDescriptor`
- size: `1172`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009aa8`
- `0x14000a7d0`

## callees

- `0x140023ac4`
- `0x140027a70`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x140027bf7`
- `ADVAPI32!AddAccessAllowedAce` at `0x140027c37`
- `ADVAPI32!AddAccessAllowedAce` at `0x140027c7c`
- `ADVAPI32!AddAccessAllowedAce` at `0x140027bf7`
- `ADVAPI32!AddAccessAllowedAce` at `0x140027c37`
- `ADVAPI32!AddAccessAllowedAce` at `0x140027c7c`
- `ADVAPI32!GetLengthSid` at `0x140027b58`
- `ADVAPI32!GetLengthSid` at `0x140027b6b`
- `ADVAPI32!GetLengthSid` at `0x140027b7e`
- `ADVAPI32!GetLengthSid` at `0x140027b58`
- `ADVAPI32!GetLengthSid` at `0x140027b6b`
- `ADVAPI32!GetLengthSid` at `0x140027b7e`
- `ADVAPI32!InitializeAcl` at `0x140027bd4`
- `ADVAPI32!InitializeAcl` at `0x140027bd4`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140027cdc`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140027cdc`
- `ADVAPI32!FreeSid` at `0x140027e99`
- `ADVAPI32!FreeSid` at `0x140027ea9`
- `ADVAPI32!FreeSid` at `0x140027e99`
- `ADVAPI32!FreeSid` at `0x140027ea9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140027aeb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140027b2f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140027aeb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140027b2f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140027d3b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140027d3b`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140027cfb`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140027cfb`
- `ADVAPI32!GetAce` at `0x140027c14`
- `ADVAPI32!GetAce` at `0x140027c59`
- `ADVAPI32!GetAce` at `0x140027c99`
- `ADVAPI32!GetAce` at `0x140027c14`
- `ADVAPI32!GetAce` at `0x140027c59`
- `ADVAPI32!GetAce` at `0x140027c99`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x140027d5b`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x140027d5b`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140027d7c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140027ddc`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140027d7c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140027ddc`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140027d1a`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140027d1a`
- `KERNEL32!HeapFree` at `0x140027e14`
- `KERNEL32!HeapFree` at `0x140027e62`
- `KERNEL32!HeapFree` at `0x140027e89`
- `KERNEL32!HeapFree` at `0x140027e14`
- `KERNEL32!HeapFree` at `0x140027e62`
- `KERNEL32!HeapFree` at `0x140027e89`
- `KERNEL32!HeapAlloc` at `0x140027ba4`
- `KERNEL32!HeapAlloc` at `0x140027dbd`
- `KERNEL32!HeapAlloc` at `0x140027ba4`
- `KERNEL32!HeapAlloc` at `0x140027dbd`
- `KERNEL32!GetProcessHeap` at `0x140027b8f`
- `KERNEL32!GetProcessHeap` at `0x140027da8`
- `KERNEL32!GetProcessHeap` at `0x140027e00`
- `KERNEL32!GetProcessHeap` at `0x140027e4e`
- `KERNEL32!GetProcessHeap` at `0x140027e74`
- `KERNEL32!GetProcessHeap` at `0x140027b8f`
- `KERNEL32!GetProcessHeap` at `0x140027da8`
- `KERNEL32!GetProcessHeap` at `0x140027e00`
- `KERNEL32!GetProcessHeap` at `0x140027e4e`
- `KERNEL32!GetProcessHeap` at `0x140027e74`
- `KERNEL32!GetLastError` at `0x140027d90`
- `KERNEL32!GetLastError` at `0x140027df2`
- `KERNEL32!GetLastError` at `0x140027e29`
- `KERNEL32!GetLastError` at `0x140027e40`
- `KERNEL32!GetLastError` at `0x140027eb7`
- `KERNEL32!GetLastError` at `0x140027d90`
- `KERNEL32!GetLastError` at `0x140027df2`
- `KERNEL32!GetLastError` at `0x140027e29`
- `KERNEL32!GetLastError` at `0x140027e40`
- `KERNEL32!GetLastError` at `0x140027eb7`
- `KERNEL32!SetLastError` at `0x140027ec7`
- `KERNEL32!SetLastError` at `0x140027ec7`

## pseudocode

```c
__int64 __fastcall CreateWorkingDirectorySecurityDescriptor(_QWORD *a1)
{
  unsigned int v1; // edi
  DWORD LastError; // esi
  DWORD LengthSid; // r12d
  DWORD v5; // r12d
  DWORD v6; // r12d
  HANDLE ProcessHeap; // rax
  struct _ACL *v8; // rax
  struct _ACL *v9; // r14
  DWORD v10; // ebx
  HANDLE v11; // rax
  void *v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD dwBufferLength; // [rsp+60h] [rbp-39h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-31h] BYREF
  PSID lpMem; // [rsp+70h] [rbp-29h] BYREF
  PSID pSid; // [rsp+78h] [rbp-21h] BYREF
  LPVOID pAce; // [rsp+80h] [rbp-19h] BYREF
  LPVOID v23; // [rsp+88h] [rbp-11h] BYREF
  LPVOID v24; // [rsp+90h] [rbp-9h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-1h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp+27h] BYREF

  v1 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  LastError = 0;
  pOwner = 0;
  pSid = 0;
  lpMem = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &pSid)
    && (unsigned int)GetCurrentUserSID(&lpMem) )
  {
    LengthSid = GetLengthSid(lpMem);
    v5 = GetLengthSid(pSid) + LengthSid;
    v6 = GetLengthSid(pOwner) + 32 + v5;
    ProcessHeap = GetProcessHeap();
    v8 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v6);
    v9 = v8;
    if ( v8 )
    {
      pAce = 0;
      v23 = 0;
      v24 = 0;
      if ( InitializeAcl(v8, v6, 2u)
        && AddAccessAllowedAce(v9, 2u, 0x10000000u, pOwner)
        && GetAce(v9, 0, &pAce)
        && AddAccessAllowedAce(v9, 2u, 0xA0000000, pSid)
        && GetAce(v9, 1u, &v23)
        && AddAccessAllowedAce(v9, 2u, 0xA0000000, lpMem)
        && GetAce(v9, 2u, &v24)
        && (v26 = 0,
            memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor)),
            *((_BYTE *)pAce + 1) |= 3u,
            *((_BYTE *)v23 + 1) |= 3u,
            *((_BYTE *)v24 + 1) |= 3u,
            InitializeSecurityDescriptor(pSecurityDescriptor, 1u))
        && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0)
        && SetSecurityDescriptorControl(pSecurityDescriptor, 0x3000u, 0x3000u) )
      {
        dwBufferLength = 0;
        if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength) || GetLastError() != 122 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
        else
        {
          v10 = dwBufferLength;
          v11 = GetProcessHeap();
          v12 = HeapAlloc(v11, 8u, v10);
          v13 = v12;
          if ( v12 )
          {
            if ( MakeSelfRelativeSD(pSecurityDescriptor, v12, &dwBufferLength) )
            {
              *a1 = v13;
            }
            else
            {
              LastError = GetLastError();
              v14 = GetProcessHeap();
              HeapFree(v14, 0, v13);
            }
          }
          else
          {
            LastError = 14;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v9);
    }
    if ( lpMem )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, lpMem);
    }
    FreeSid(pSid);
    FreeSid(pOwner);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  LOBYTE(v1) = LastError == 0;
  return v1;
}

```

## disassembly

```asm
0x140027a70  mov     [rsp-8+arg_8], rbx
0x140027a75  mov     [rsp-8+arg_10], rsi
0x140027a7a  push    rbp
0x140027a7b  push    rdi
0x140027a7c  push    r12
0x140027a7e  push    r13
0x140027a80  push    r14
0x140027a82  lea     rbp, [rsp-37h]
0x140027a87  sub     rsp, 0D0h
0x140027a8e  mov     rax, cs:__security_cookie
0x140027a95  xor     rax, rsp
0x140027a98  mov     [rbp+57h+var_28], rax
0x140027a9c  xor     edi, edi
0x140027a9e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140027aa4  lea     rax, [rbp+57h+pOwner]
0x140027aa8  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140027aab  mov     [rsp+0F0h+pSid], rax; pSid
0x140027ab0  mov     r13, rcx
0x140027ab3  mov     [rsp+0F0h+nSubAuthority7], edi; nSubAuthority7
0x140027ab7  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140027abb  mov     [rsp+0F0h+nSubAuthority6], edi; nSubAuthority6
0x140027abf  lea     ebx, [rdi+20h]
0x140027ac2  mov     [rsp+0F0h+nSubAuthority5], edi; nSubAuthority5
0x140027ac6  mov     r8d, ebx; nSubAuthority0
0x140027ac9  mov     [rsp+0F0h+nSubAuthority4], edi; nSubAuthority4
0x140027acd  mov     r9d, 220h; nSubAuthority1
0x140027ad3  mov     [rsp+0F0h+nSubAuthority3], edi; nSubAuthority3
0x140027ad7  mov     dl, 2; nSubAuthorityCount
0x140027ad9  mov     [rsp+0F0h+nSubAuthority2], edi; nSubAuthority2
0x140027add  mov     esi, edi
0x140027adf  mov     [rbp+57h+pOwner], rdi
0x140027ae3  mov     [rbp+57h+var_78], rdi
0x140027ae7  mov     [rbp+57h+lpMem], rdi
0x140027aeb  call    cs:__imp_AllocateAndInitializeSid
0x140027af2  nop     dword ptr [rax+rax+00h]
0x140027af7  test    eax, eax
0x140027af9  jz      loc_140027EB7
0x140027aff  lea     rax, [rbp+57h+var_78]
0x140027b03  mov     r9d, 221h; nSubAuthority1
0x140027b09  mov     [rsp+0F0h+pSid], rax; pSid
0x140027b0e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140027b12  mov     [rsp+0F0h+nSubAuthority7], edi; nSubAuthority7
0x140027b16  mov     r8d, ebx; nSubAuthority0
0x140027b19  mov     [rsp+0F0h+nSubAuthority6], edi; nSubAuthority6
0x140027b1d  mov     dl, 2; nSubAuthorityCount
0x140027b1f  mov     [rsp+0F0h+nSubAuthority5], edi; nSubAuthority5
0x140027b23  mov     [rsp+0F0h+nSubAuthority4], edi; nSubAuthority4
0x140027b27  mov     [rsp+0F0h+nSubAuthority3], edi; nSubAuthority3
0x140027b2b  mov     [rsp+0F0h+nSubAuthority2], edi; nSubAuthority2
0x140027b2f  call    cs:__imp_AllocateAndInitializeSid
0x140027b36  nop     dword ptr [rax+rax+00h]
0x140027b3b  test    eax, eax
0x140027b3d  jz      loc_140027EB7
0x140027b43  lea     rcx, [rbp+57h+lpMem]
0x140027b47  call    GetCurrentUserSID
0x140027b4c  test    eax, eax
0x140027b4e  jz      loc_140027EB7
0x140027b54  mov     rcx, [rbp+57h+lpMem]; pSid
0x140027b58  call    cs:__imp_GetLengthSid
0x140027b5f  nop     dword ptr [rax+rax+00h]
0x140027b64  mov     rcx, [rbp+57h+var_78]; pSid
0x140027b68  mov     r12d, eax
0x140027b6b  call    cs:__imp_GetLengthSid
0x140027b72  nop     dword ptr [rax+rax+00h]
0x140027b77  mov     rcx, [rbp+57h+pOwner]; pSid
0x140027b7b  add     r12d, eax
0x140027b7e  call    cs:__imp_GetLengthSid
0x140027b85  nop     dword ptr [rax+rax+00h]
0x140027b8a  add     eax, ebx
0x140027b8c  add     r12d, eax
0x140027b8f  call    cs:__imp_GetProcessHeap
0x140027b96  nop     dword ptr [rax+rax+00h]
0x140027b9b  mov     r8d, r12d; dwBytes
0x140027b9e  lea     edx, [rdi+8]; dwFlags
0x140027ba1  mov     rcx, rax; hHeap
0x140027ba4  call    cs:__imp_HeapAlloc
0x140027bab  nop     dword ptr [rax+rax+00h]
0x140027bb0  mov     r14, rax
0x140027bb3  test    rax, rax
0x140027bb6  jz      loc_140027E6E
0x140027bbc  lea     ebx, [rdi+2]
0x140027bbf  mov     [rbp+57h+pAce], rdi
0x140027bc3  mov     r8d, ebx; dwAclRevision
0x140027bc6  mov     [rbp+57h+var_68], rdi
0x140027bca  mov     edx, r12d; nAclLength
0x140027bcd  mov     [rbp+57h+var_60], rdi
0x140027bd1  mov     rcx, rax; pAcl
0x140027bd4  call    cs:__imp_InitializeAcl
0x140027bdb  nop     dword ptr [rax+rax+00h]
0x140027be0  test    eax, eax
0x140027be2  jz      loc_140027E40
0x140027be8  mov     r9, [rbp+57h+pOwner]; pSid
0x140027bec  mov     r8d, 10000000h; AccessMask
0x140027bf2  mov     edx, ebx; dwAceRevision
0x140027bf4  mov     rcx, r14; pAcl
0x140027bf7  call    cs:__imp_AddAccessAllowedAce
0x140027bfe  nop     dword ptr [rax+rax+00h]
0x140027c03  test    eax, eax
0x140027c05  jz      loc_140027E40
0x140027c0b  lea     r8, [rbp+57h+pAce]; pAce
0x140027c0f  xor     edx, edx; dwAceIndex
0x140027c11  mov     rcx, r14; pAcl
0x140027c14  call    cs:__imp_GetAce
0x140027c1b  nop     dword ptr [rax+rax+00h]
0x140027c20  test    eax, eax
0x140027c22  jz      loc_140027E40
0x140027c28  mov     r9, [rbp+57h+var_78]; pSid
0x140027c2c  mov     r8d, 0A0000000h; AccessMask
0x140027c32  mov     edx, ebx; dwAceRevision
0x140027c34  mov     rcx, r14; pAcl
0x140027c37  call    cs:__imp_AddAccessAllowedAce
0x140027c3e  nop     dword ptr [rax+rax+00h]
0x140027c43  test    eax, eax
0x140027c45  jz      loc_140027E40
0x140027c4b  lea     r12d, [rdi+1]
0x140027c4f  mov     rcx, r14; pAcl
0x140027c52  mov     edx, r12d; dwAceIndex
0x140027c55  lea     r8, [rbp+57h+var_68]; pAce
0x140027c59  call    cs:__imp_GetAce
0x140027c60  nop     dword ptr [rax+rax+00h]
0x140027c65  test    eax, eax
0x140027c67  jz      loc_140027E40
0x140027c6d  mov     r9, [rbp+57h+lpMem]; pSid
0x140027c71  mov     r8d, 0A0000000h; AccessMask
0x140027c77  mov     edx, ebx; dwAceRevision
0x140027c79  mov     rcx, r14; pAcl
0x140027c7c  call    cs:__imp_AddAccessAllowedAce
0x140027c83  nop     dword ptr [rax+rax+00h]
0x140027c88  test    eax, eax
0x140027c8a  jz      loc_140027E40
0x140027c90  lea     r8, [rbp+57h+var_60]; pAce
0x140027c94  mov     edx, ebx; dwAceIndex
0x140027c96  mov     rcx, r14; pAcl
0x140027c99  call    cs:__imp_GetAce
0x140027ca0  nop     dword ptr [rax+rax+00h]
0x140027ca5  test    eax, eax
0x140027ca7  jz      loc_140027E40
0x140027cad  xor     eax, eax
0x140027caf  mov     cl, 3
0x140027cb1  mov     [rbp+57h+var_38], rax
0x140027cb5  xorps   xmm0, xmm0
0x140027cb8  mov     rax, [rbp+57h+pAce]
0x140027cbc  mov     edx, r12d; dwRevision
0x140027cbf  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x140027cc3  movups  [rbp+57h+var_48], xmm0
0x140027cc7  or      [rax+1], cl
0x140027cca  mov     rax, [rbp+57h+var_68]
0x140027cce  or      [rax+1], cl
0x140027cd1  mov     rax, [rbp+57h+var_60]
0x140027cd5  or      [rax+1], cl
0x140027cd8  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140027cdc  call    cs:__imp_InitializeSecurityDescriptor
0x140027ce3  nop     dword ptr [rax+rax+00h]
0x140027ce8  test    eax, eax
0x140027cea  jz      loc_140027E40
0x140027cf0  mov     rdx, [rbp+57h+pOwner]; pOwner
0x140027cf4  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140027cf8  xor     r8d, r8d; bOwnerDefaulted
0x140027cfb  call    cs:__imp_SetSecurityDescriptorOwner
0x140027d02  nop     dword ptr [rax+rax+00h]
0x140027d07  test    eax, eax
0x140027d09  jz      loc_140027E40
0x140027d0f  mov     rdx, [rbp+57h+pOwner]; pGroup
0x140027d13  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140027d17  xor     r8d, r8d; bGroupDefaulted
0x140027d1a  call    cs:__imp_SetSecurityDescriptorGroup
0x140027d21  nop     dword ptr [rax+rax+00h]
0x140027d26  test    eax, eax
0x140027d28  jz      loc_140027E40
0x140027d2e  xor     r9d, r9d; bDaclDefaulted
0x140027d31  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140027d35  mov     r8, r14; pDacl
0x140027d38  mov     edx, r12d; bDaclPresent
0x140027d3b  call    cs:__imp_SetSecurityDescriptorDacl
0x140027d42  nop     dword ptr [rax+rax+00h]
0x140027d47  test    eax, eax
0x140027d49  jz      loc_140027E40
0x140027d4f  mov     edx, 3000h; ControlBitsOfInterest
0x140027d54  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140027d58  mov     r8d, edx; ControlBitsToSet
0x140027d5b  call    cs:__imp_SetSecurityDescriptorControl
0x140027d62  nop     dword ptr [rax+rax+00h]
0x140027d67  test    eax, eax
0x140027d69  jz      loc_140027E40
0x140027d6f  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x140027d73  mov     [rbp+57h+dwBufferLength], edi
0x140027d76  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x140027d78  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140027d7c  call    cs:__imp_MakeSelfRelativeSD
0x140027d83  nop     dword ptr [rax+rax+00h]
0x140027d88  test    eax, eax
0x140027d8a  jnz     loc_140027E29
0x140027d90  call    cs:__imp_GetLastError
0x140027d97  nop     dword ptr [rax+rax+00h]
0x140027d9c  cmp     eax, 7Ah ; 'z'
0x140027d9f  jnz     loc_140027E29
0x140027da5  mov     ebx, [rbp+57h+dwBufferLength]
0x140027da8  call    cs:__imp_GetProcessHeap
0x140027daf  nop     dword ptr [rax+rax+00h]
0x140027db4  mov     r8d, ebx; dwBytes
0x140027db7  lea     edx, [rdi+8]; dwFlags
0x140027dba  mov     rcx, rax; hHeap
0x140027dbd  call    cs:__imp_HeapAlloc
0x140027dc4  nop     dword ptr [rax+rax+00h]
0x140027dc9  mov     rbx, rax
0x140027dcc  test    rax, rax
0x140027dcf  jz      short loc_140027E22
0x140027dd1  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x140027dd5  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x140027dd8  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x140027ddc  call    cs:__imp_MakeSelfRelativeSD
0x140027de3  nop     dword ptr [rax+rax+00h]
0x140027de8  test    eax, eax
0x140027dea  jz      short loc_140027DF2
0x140027dec  mov     [r13+0], rbx
0x140027df0  jmp     short loc_140027E4E
0x140027df2  call    cs:__imp_GetLastError
0x140027df9  nop     dword ptr [rax+rax+00h]
0x140027dfe  mov     esi, eax
0x140027e00  call    cs:__imp_GetProcessHeap
0x140027e07  nop     dword ptr [rax+rax+00h]
0x140027e0c  mov     r8, rbx; lpMem
0x140027e0f  xor     edx, edx; dwFlags
0x140027e11  mov     rcx, rax; hHeap
0x140027e14  call    cs:__imp_HeapFree
0x140027e1b  nop     dword ptr [rax+rax+00h]
0x140027e20  jmp     short loc_140027E4E
0x140027e22  mov     esi, 0Eh
0x140027e27  jmp     short loc_140027E4E
0x140027e29  call    cs:__imp_GetLastError
0x140027e30  nop     dword ptr [rax+rax+00h]
0x140027e35  mov     esi, eax
0x140027e37  test    eax, eax
0x140027e39  jnz     short loc_140027E4E
0x140027e3b  lea     esi, [rax+1Fh]
0x140027e3e  jmp     short loc_140027E4E
0x140027e40  call    cs:__imp_GetLastError
0x140027e47  nop     dword ptr [rax+rax+00h]
0x140027e4c  mov     esi, eax
0x140027e4e  call    cs:__imp_GetProcessHeap
0x140027e55  nop     dword ptr [rax+rax+00h]
0x140027e5a  mov     r8, r14; lpMem
0x140027e5d  xor     edx, edx; dwFlags
0x140027e5f  mov     rcx, rax; hHeap
0x140027e62  call    cs:__imp_HeapFree
0x140027e69  nop     dword ptr [rax+rax+00h]
0x140027e6e  cmp     [rbp+57h+lpMem], rdi
0x140027e72  jz      short loc_140027E95
0x140027e74  call    cs:__imp_GetProcessHeap
0x140027e7b  nop     dword ptr [rax+rax+00h]
0x140027e80  mov     r8, [rbp+57h+lpMem]; lpMem
0x140027e84  xor     edx, edx; dwFlags
0x140027e86  mov     rcx, rax; hHeap
0x140027e89  call    cs:__imp_HeapFree
0x140027e90  nop     dword ptr [rax+rax+00h]
0x140027e95  mov     rcx, [rbp+57h+var_78]; pSid
0x140027e99  call    cs:__imp_FreeSid
0x140027ea0  nop     dword ptr [rax+rax+00h]
0x140027ea5  mov     rcx, [rbp+57h+pOwner]; pSid
0x140027ea9  call    cs:__imp_FreeSid
0x140027eb0  nop     dword ptr [rax+rax+00h]
0x140027eb5  jmp     short loc_140027EC5
0x140027eb7  call    cs:__imp_GetLastError
0x140027ebe  nop     dword ptr [rax+rax+00h]
0x140027ec3  mov     esi, eax
0x140027ec5  mov     ecx, esi; dwErrCode
0x140027ec7  call    cs:__imp_SetLastError
0x140027ece  nop     dword ptr [rax+rax+00h]
0x140027ed3  test    esi, esi
0x140027ed5  setz    dil
0x140027ed9  mov     eax, edi
0x140027edb  mov     rcx, [rbp+57h+var_28]
0x140027edf  xor     rcx, rsp; StackCookie
0x140027ee2  call    __security_check_cookie
0x140027ee7  lea     r11, [rsp+0F0h+var_20]
0x140027eef  mov     rbx, [r11+38h]
0x140027ef3  mov     rsi, [r11+40h]
0x140027ef7  mov     rsp, r11
0x140027efa  pop     r14
0x140027efc  pop     r13
0x140027efe  pop     r12
0x140027f00  pop     rdi
0x140027f01  pop     rbp
0x140027f02  retn
```
