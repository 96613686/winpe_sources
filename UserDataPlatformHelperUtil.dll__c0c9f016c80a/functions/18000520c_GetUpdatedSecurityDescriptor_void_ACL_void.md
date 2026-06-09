# GetUpdatedSecurityDescriptor(void *,_ACL *,void * *)

- ea: `0x18000520c`
- end: `0x18000549d`
- name: `?GetUpdatedSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX@Z`
- size: `657`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, PACL pDacl, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800055a0`

## callees

- `0x18000520c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000540a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000540a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800053a3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800053a3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800053bd`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180005400`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800053bd`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180005400`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000527b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005366`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000527b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005307`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000538b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000543a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005460`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005472`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005307`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000538b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000543a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005460`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005472`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000529d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005314`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800053d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000529d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005314`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800053d7`

## pseudocode

```c
__int64 __fastcall GetUpdatedSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        PACL pDacl,
        void **a3)
{
  HLOCAL v5; // rbx
  struct _ACL *v7; // r14
  struct _ACL *pSacl; // r15
  HLOCAL pOwner; // r12
  HLOCAL pPrimaryGroup; // rax
  void *v11; // rdi
  signed int v12; // eax
  unsigned int v13; // r13d
  HLOCAL v14; // rax
  void *v15; // rsi
  signed int LastError; // eax
  SIZE_T uBytes; // [rsp+60h] [rbp-20h] BYREF
  DWORD dwDaclSize; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp-14h] BYREF
  DWORD dwBufferLength[4]; // [rsp+70h] [rbp-10h] BYREF
  SIZE_T lpdwPrimaryGroupSize; // [rsp+D8h] [rbp+58h] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  uBytes = 0;
  LODWORD(lpdwPrimaryGroupSize) = 0;
  if ( !MakeAbsoluteSD(
          pSelfRelativeSecurityDescriptor,
          0,
          &dwAbsoluteSecurityDescriptorSize,
          0,
          &dwDaclSize,
          0,
          (LPDWORD)&uBytes + 1,
          0,
          (LPDWORD)&uBytes,
          0,
          (LPDWORD)&lpdwPrimaryGroupSize)
    && GetLastError() == 122 )
  {
    v5 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
    if ( !v5 )
      return 2147942414LL;
    v7 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
    if ( !v7 )
    {
LABEL_6:
      LocalFree(v5);
      return 2147942414LL;
    }
    pSacl = (struct _ACL *)LocalAlloc(0, HIDWORD(uBytes));
    if ( !pSacl )
    {
LABEL_8:
      LocalFree(v7);
      goto LABEL_6;
    }
    pOwner = LocalAlloc(0, (unsigned int)uBytes);
    if ( !pOwner )
    {
      LocalFree(pSacl);
      goto LABEL_8;
    }
    pPrimaryGroup = LocalAlloc(0, (unsigned int)lpdwPrimaryGroupSize);
    v11 = pPrimaryGroup;
    if ( !pPrimaryGroup )
      goto LABEL_21;
    if ( MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           v5,
           &dwAbsoluteSecurityDescriptorSize,
           v7,
           &dwDaclSize,
           pSacl,
           (LPDWORD)&uBytes + 1,
           pOwner,
           (LPDWORD)&uBytes,
           pPrimaryGroup,
           (LPDWORD)&lpdwPrimaryGroupSize)
      && SetSecurityDescriptorDacl(v5, 1, pDacl, 0) )
    {
      dwBufferLength[0] = 0;
      if ( MakeSelfRelativeSD(v5, 0, dwBufferLength) || GetLastError() != 122 )
      {
        LocalFree(v11);
        v13 = -2147418113;
        goto LABEL_28;
      }
      v14 = LocalAlloc(0, dwBufferLength[0]);
      v15 = v14;
      if ( !v14 )
      {
        LocalFree(v11);
LABEL_21:
        v13 = -2147024882;
        goto LABEL_28;
      }
      if ( MakeSelfRelativeSD(v5, v14, dwBufferLength) )
      {
        *a3 = v15;
        LocalFree(v11);
        v13 = 0;
        goto LABEL_28;
      }
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      LocalFree(v15);
    }
    else
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
    }
    LocalFree(v11);
LABEL_28:
    LocalFree(pOwner);
    LocalFree(pSacl);
    LocalFree(v7);
    LocalFree(v5);
    return v13;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000520c  mov     r11, rsp
0x18000520f  mov     [r11+8], rbx
0x180005213  mov     [r11+18h], r8
0x180005217  push    rbp
0x180005218  push    rsi
0x180005219  push    rdi
0x18000521a  push    r12
0x18000521c  push    r13
0x18000521e  push    r14
0x180005220  push    r15
0x180005222  mov     rbp, rsp
0x180005225  sub     rsp, 80h
0x18000522c  xor     edi, edi
0x18000522e  lea     rax, [rbp+arg_18]
0x180005232  mov     [r11-68h], rax
0x180005236  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000523a  mov     [r11-70h], rdi
0x18000523e  lea     rax, [rbp+uBytes]
0x180005242  mov     [r11-78h], rax
0x180005246  mov     r13, rdx
0x180005249  mov     [r11-80h], rdi
0x18000524d  lea     rax, [rbp+uBytes+4]
0x180005251  mov     [rsp+80h+lpdwSaclSize], rax; lpdwSaclSize
0x180005256  xor     r9d, r9d; pDacl
0x180005259  lea     rax, [rbp+dwDaclSize]
0x18000525d  mov     [rsp+80h+pSacl], rdi; pSacl
0x180005262  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180005264  mov     [rsp+80h+lpdwDaclSize], rax; lpdwDaclSize
0x180005269  mov     rsi, rcx
0x18000526c  mov     [rbp+dwAbsoluteSecurityDescriptorSize], edi
0x18000526f  mov     [rbp+dwDaclSize], edi
0x180005272  mov     dword ptr [rbp+uBytes+4], edi
0x180005275  mov     dword ptr [rbp+uBytes], edi
0x180005278  mov     dword ptr [rbp+arg_18], edi
0x18000527b  call    cs:__imp_MakeAbsoluteSD
0x180005281  test    eax, eax
0x180005283  jnz     loc_18000547D
0x180005289  call    cs:__imp_GetLastError
0x18000528f  cmp     eax, 7Ah ; 'z'
0x180005292  jnz     loc_18000547D
0x180005298  mov     edx, [rbp+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18000529b  xor     ecx, ecx; uFlags
0x18000529d  call    cs:__imp_LocalAlloc
0x1800052a3  mov     rbx, rax
0x1800052a6  test    rax, rax
0x1800052a9  jnz     short loc_1800052B5
0x1800052ab  mov     eax, 8007000Eh
0x1800052b0  jmp     loc_180005482
0x1800052b5  mov     edx, [rbp+dwDaclSize]; uBytes
0x1800052b8  xor     ecx, ecx; uFlags
0x1800052ba  call    cs:__imp_LocalAlloc
0x1800052c0  mov     r14, rax
0x1800052c3  test    rax, rax
0x1800052c6  jnz     short loc_1800052D3
0x1800052c8  mov     rcx, rbx; hMem
0x1800052cb  call    cs:__imp_LocalFree
0x1800052d1  jmp     short loc_1800052AB
0x1800052d3  mov     edx, dword ptr [rbp+uBytes+4]; uBytes
0x1800052d6  xor     ecx, ecx; uFlags
0x1800052d8  call    cs:__imp_LocalAlloc
0x1800052de  mov     r15, rax
0x1800052e1  test    rax, rax
0x1800052e4  jnz     short loc_1800052F1
0x1800052e6  mov     rcx, r14; hMem
0x1800052e9  call    cs:__imp_LocalFree
0x1800052ef  jmp     short loc_1800052C8
0x1800052f1  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x1800052f4  xor     ecx, ecx; uFlags
0x1800052f6  call    cs:__imp_LocalAlloc
0x1800052fc  mov     r12, rax
0x1800052ff  test    rax, rax
0x180005302  jnz     short loc_18000530F
0x180005304  mov     rcx, r15; hMem
0x180005307  call    cs:__imp_LocalFree
0x18000530d  jmp     short loc_1800052E6
0x18000530f  mov     edx, dword ptr [rbp+arg_18]; uBytes
0x180005312  xor     ecx, ecx; uFlags
0x180005314  call    cs:__imp_LocalAlloc
0x18000531a  mov     rdi, rax
0x18000531d  test    rax, rax
0x180005320  jz      loc_1800053EE
0x180005326  lea     rax, [rbp+arg_18]
0x18000532a  mov     r9, r14; pDacl
0x18000532d  mov     [rsp+80h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180005332  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180005336  mov     [rsp+80h+pPrimaryGroup], rdi; pPrimaryGroup
0x18000533b  lea     rax, [rbp+uBytes]
0x18000533f  mov     [rsp+80h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180005344  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x180005347  mov     [rsp+80h+pOwner], r12; pOwner
0x18000534c  lea     rax, [rbp+uBytes+4]
0x180005350  mov     [rsp+80h+lpdwSaclSize], rax; lpdwSaclSize
0x180005355  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x180005358  lea     rax, [rbp+dwDaclSize]
0x18000535c  mov     [rsp+80h+pSacl], r15; pSacl
0x180005361  mov     [rsp+80h+lpdwDaclSize], rax; lpdwDaclSize
0x180005366  call    cs:__imp_MakeAbsoluteSD
0x18000536c  test    eax, eax
0x18000536e  jnz     short loc_180005396
0x180005370  call    cs:__imp_GetLastError
0x180005376  mov     r13d, eax
0x180005379  test    eax, eax
0x18000537b  jle     short loc_180005388
0x18000537d  movzx   r13d, ax
0x180005381  or      r13d, 80070000h
0x180005388  mov     rcx, rdi; hMem
0x18000538b  call    cs:__imp_LocalFree
0x180005391  jmp     loc_180005454
0x180005396  xor     r9d, r9d; bDaclDefaulted
0x180005399  mov     r8, r13; pDacl
0x18000539c  mov     rcx, rbx; pSecurityDescriptor
0x18000539f  lea     edx, [r9+1]; bDaclPresent
0x1800053a3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800053a9  test    eax, eax
0x1800053ab  jz      short loc_180005370
0x1800053ad  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800053b1  mov     [rbp+dwBufferLength], 0
0x1800053b8  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800053ba  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800053bd  call    cs:__imp_MakeSelfRelativeSD
0x1800053c3  test    eax, eax
0x1800053c5  jnz     short loc_180005445
0x1800053c7  call    cs:__imp_GetLastError
0x1800053cd  cmp     eax, 7Ah ; 'z'
0x1800053d0  jnz     short loc_180005445
0x1800053d2  mov     edx, [rbp+dwBufferLength]; uBytes
0x1800053d5  xor     ecx, ecx; uFlags
0x1800053d7  call    cs:__imp_LocalAlloc
0x1800053dd  mov     rsi, rax
0x1800053e0  test    rax, rax
0x1800053e3  jnz     short loc_1800053F6
0x1800053e5  mov     rcx, rdi; hMem
0x1800053e8  call    cs:__imp_LocalFree
0x1800053ee  mov     r13d, 8007000Eh
0x1800053f4  jmp     short loc_180005454
0x1800053f6  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800053fa  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x1800053fd  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180005400  call    cs:__imp_MakeSelfRelativeSD
0x180005406  test    eax, eax
0x180005408  jnz     short loc_180005430
0x18000540a  call    cs:__imp_GetLastError
0x180005410  mov     r13d, eax
0x180005413  test    eax, eax
0x180005415  jle     short loc_180005422
0x180005417  movzx   r13d, ax
0x18000541b  or      r13d, 80070000h
0x180005422  mov     rcx, rsi; hMem
0x180005425  call    cs:__imp_LocalFree
0x18000542b  jmp     loc_180005388
0x180005430  mov     rax, [rbp+arg_10]
0x180005434  mov     rcx, rdi; hMem
0x180005437  mov     [rax], rsi
0x18000543a  call    cs:__imp_LocalFree
0x180005440  xor     r13d, r13d
0x180005443  jmp     short loc_180005454
0x180005445  mov     rcx, rdi; hMem
0x180005448  call    cs:__imp_LocalFree
0x18000544e  mov     r13d, 8000FFFFh
0x180005454  mov     rcx, r12; hMem
0x180005457  call    cs:__imp_LocalFree
0x18000545d  mov     rcx, r15; hMem
0x180005460  call    cs:__imp_LocalFree
0x180005466  mov     rcx, r14; hMem
0x180005469  call    cs:__imp_LocalFree
0x18000546f  mov     rcx, rbx; hMem
0x180005472  call    cs:__imp_LocalFree
0x180005478  mov     eax, r13d
0x18000547b  jmp     short loc_180005482
0x18000547d  mov     eax, 8000FFFFh
0x180005482  mov     rbx, [rsp+80h+arg_0]
0x18000548a  add     rsp, 80h
0x180005491  pop     r15
0x180005493  pop     r14
0x180005495  pop     r13
0x180005497  pop     r12
0x180005499  pop     rdi
0x18000549a  pop     rsi
0x18000549b  pop     rbp
0x18000549c  retn
```
