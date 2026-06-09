# DestroySecurityAttributes

- ea: `0x18002ea78`
- end: `0x18002ebdc`
- name: `DestroySecurityAttributes`
- size: `356`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d9ac`
- `0x180036f80`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002bb58`
- `0x18002ea78`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002ebb6`
- `KERNEL32!LocalFree` at `0x18002ebb6`
- `KERNEL32!GetLastError` at `0x18002eb13`
- `KERNEL32!GetLastError` at `0x18002eb84`
- `KERNEL32!GetLastError` at `0x18002eb13`
- `KERNEL32!GetLastError` at `0x18002eb84`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002eb5c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002eb5c`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18002eaeb`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18002eaeb`

## pseudocode

```c
__int64 __fastcall DestroySecurityAttributes(_QWORD *lpMem)
{
  void *v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // eax
  BOOL bOwnerDefaulted; // [rsp+40h] [rbp+8h] BYREF
  BOOL bDaclPresent; // [rsp+48h] [rbp+10h] BYREF
  PSID pOwner; // [rsp+50h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v2 = (void *)lpMem[1];
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  pOwner = 0;
  pDacl = 0;
  if ( GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted) )
  {
    pMemFree(pOwner);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
  }
  if ( GetSecurityDescriptorDacl(v2, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    LocalFree(pDacl);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_db036311db36307996a98c23702218b2_Traceguids, v4);
  }
  pMemFree(lpMem);
  return pMemFree(v2);
}

```

## disassembly

```asm
0x18002ea78  push    rbx
0x18002ea7a  push    rdi
0x18002ea7b  push    r14
0x18002ea7d  sub     rsp, 20h
0x18002ea81  mov     rdi, rcx
0x18002ea84  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea8b  lea     r14, WPP_GLOBAL_Control
0x18002ea92  cmp     rcx, r14
0x18002ea95  jz      short loc_18002EAB8
0x18002ea97  test    byte ptr [rcx+1Ch], 2
0x18002ea9b  jz      short loc_18002EAB8
0x18002ea9d  cmp     byte ptr [rcx+19h], 5
0x18002eaa1  jb      short loc_18002EAB8
0x18002eaa3  mov     rcx, [rcx+10h]
0x18002eaa7  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002eaae  mov     edx, 43h ; 'C'
0x18002eab3  call    WPP_SF_
0x18002eab8  mov     rbx, [rdi+8]
0x18002eabc  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18002eac1  mov     rcx, rbx; pSecurityDescriptor
0x18002eac4  mov     [rsp+38h+bOwnerDefaulted], 0
0x18002eacc  lea     rdx, [rsp+38h+pOwner]; pOwner
0x18002ead1  mov     [rsp+38h+bDaclPresent], 0
0x18002ead9  mov     [rsp+38h+pOwner], 0
0x18002eae2  mov     [rsp+38h+pDacl], 0
0x18002eaeb  call    cs:__imp_GetSecurityDescriptorOwner
0x18002eaf2  nop     dword ptr [rax+rax+00h]
0x18002eaf7  test    eax, eax
0x18002eaf9  jnz     short loc_18002EB40
0x18002eafb  mov     rax, cs:WPP_GLOBAL_Control
0x18002eb02  cmp     rax, r14
0x18002eb05  jz      short loc_18002EB4A
0x18002eb07  test    byte ptr [rax+1Ch], 2
0x18002eb0b  jz      short loc_18002EB4A
0x18002eb0d  cmp     byte ptr [rax+19h], 2
0x18002eb11  jb      short loc_18002EB4A
0x18002eb13  call    cs:__imp_GetLastError
0x18002eb1a  nop     dword ptr [rax+rax+00h]
0x18002eb1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb26  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002eb2d  mov     edx, 44h ; 'D'
0x18002eb32  mov     r9d, eax
0x18002eb35  mov     rcx, [rcx+10h]
0x18002eb39  call    WPP_SF_d
0x18002eb3e  jmp     short loc_18002EB4A
0x18002eb40  mov     rcx, [rsp+38h+pOwner]; lpMem
0x18002eb45  call    pMemFree
0x18002eb4a  lea     r9, [rsp+38h+bOwnerDefaulted]; lpbDaclDefaulted
0x18002eb4f  mov     rcx, rbx; pSecurityDescriptor
0x18002eb52  lea     r8, [rsp+38h+pDacl]; pDacl
0x18002eb57  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x18002eb5c  call    cs:__imp_GetSecurityDescriptorDacl
0x18002eb63  nop     dword ptr [rax+rax+00h]
0x18002eb68  test    eax, eax
0x18002eb6a  jnz     short loc_18002EBB1
0x18002eb6c  mov     rax, cs:WPP_GLOBAL_Control
0x18002eb73  cmp     rax, r14
0x18002eb76  jz      short loc_18002EBC2
0x18002eb78  test    byte ptr [rax+1Ch], 2
0x18002eb7c  jz      short loc_18002EBC2
0x18002eb7e  cmp     byte ptr [rax+19h], 2
0x18002eb82  jb      short loc_18002EBC2
0x18002eb84  call    cs:__imp_GetLastError
0x18002eb8b  nop     dword ptr [rax+rax+00h]
0x18002eb90  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb97  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002eb9e  mov     edx, 45h ; 'E'
0x18002eba3  mov     r9d, eax
0x18002eba6  mov     rcx, [rcx+10h]
0x18002ebaa  call    WPP_SF_d
0x18002ebaf  jmp     short loc_18002EBC2
0x18002ebb1  mov     rcx, [rsp+38h+pDacl]; hMem
0x18002ebb6  call    cs:__imp_LocalFree
0x18002ebbd  nop     dword ptr [rax+rax+00h]
0x18002ebc2  mov     rcx, rdi; lpMem
0x18002ebc5  call    pMemFree
0x18002ebca  mov     rcx, rbx; lpMem
0x18002ebcd  call    pMemFree
0x18002ebd2  add     rsp, 20h
0x18002ebd6  pop     r14
0x18002ebd8  pop     rdi
0x18002ebd9  pop     rbx
0x18002ebda  retn
```
