# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x18002f3d4`
- end: `0x18002f639`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `613`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f7d0`

## callees

- `0x180002604`
- `0x18002f3d4`
- `0x180031264`
- `0x18003151c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f49c`
- `KERNEL32!GetLastError` at `0x18002f49c`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002f425`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002f425`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002f496`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002f59a`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002f496`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002f59a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f5fc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f605`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f60e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f617`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f620`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f5fc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f605`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f60e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f617`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f620`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4ae`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4be`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4d5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4ec`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f504`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4ae`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4be`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4d5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f4ec`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f504`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::MakeAbsolute(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // r12
  void *pOwner; // r15
  void *pPrimaryGroup; // r14
  DWORD v7; // eax
  ACL *v8; // rsi
  DWORD v9; // ecx
  ACL *v10; // rax
  ACL *pSacl; // rdi
  int Error; // ebx
  DWORD dwDaclSize; // [rsp+68h] [rbp+7h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+6Ch] [rbp+Bh] BYREF
  DWORD dwOwnerSize; // [rsp+70h] [rbp+Fh] BYREF
  DWORD dwSaclSize; // [rsp+74h] [rbp+13h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+78h] [rbp+17h] BYREF
  WORD pControl; // [rsp+7Ch] [rbp+1Bh] BYREF
  DWORD dwRevision; // [rsp+80h] [rbp+1Fh] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, &dwRevision) )
      ATL::AtlThrowImpl(-2147467259);
    if ( (pControl & 0x8000u) != 0 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      dwSaclSize = 0;
      dwDaclSize = 0;
      dwPrimaryGroupSize = 0;
      dwOwnerSize = 0;
      dwAbsoluteSecurityDescriptorSize = 0;
      MakeAbsoluteSD(
        v3,
        0,
        &dwAbsoluteSecurityDescriptorSize,
        0,
        &dwDaclSize,
        0,
        &dwSaclSize,
        0,
        &dwOwnerSize,
        0,
        &dwPrimaryGroupSize);
      if ( GetLastError() != 122 )
        ATL::AtlThrowLastWin32();
      v4 = malloc(dwAbsoluteSecurityDescriptorSize);
      if ( dwOwnerSize )
        pOwner = malloc(dwOwnerSize);
      else
        pOwner = 0;
      if ( dwPrimaryGroupSize )
        pPrimaryGroup = malloc(dwPrimaryGroupSize);
      else
        pPrimaryGroup = 0;
      v7 = dwDaclSize;
      if ( dwDaclSize )
      {
        v8 = (ACL *)malloc(dwDaclSize);
        v7 = dwDaclSize;
      }
      else
      {
        v8 = 0;
      }
      v9 = dwSaclSize;
      if ( dwSaclSize )
      {
        v10 = (ACL *)malloc(dwSaclSize);
        v9 = dwSaclSize;
        pSacl = v10;
        v7 = dwDaclSize;
      }
      else
      {
        pSacl = 0;
      }
      if ( !v4 || dwOwnerSize && !pOwner || dwPrimaryGroupSize && !pPrimaryGroup || v7 && !v8 || v9 && !pSacl )
      {
        Error = -2147024882;
LABEL_32:
        free(v4);
        free(pOwner);
        free(pPrimaryGroup);
        free(v8);
        free(pSacl);
        ATL::AtlThrowImpl(Error);
      }
      if ( !MakeAbsoluteSD(
              *((PSECURITY_DESCRIPTOR *)this + 1),
              v4,
              &dwAbsoluteSecurityDescriptorSize,
              v8,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        Error = ATL::AtlHresultFromLastError();
        goto LABEL_32;
      }
      (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
      *((_QWORD *)this + 1) = v4;
    }
  }
}

```

## disassembly

```asm
0x18002f3d4  mov     rax, rsp
0x18002f3d7  mov     [rax+10h], rbx
0x18002f3db  mov     [rax+18h], rsi
0x18002f3df  mov     [rax+20h], rdi
0x18002f3e3  push    rbp
0x18002f3e4  push    r12
0x18002f3e6  push    r13
0x18002f3e8  push    r14
0x18002f3ea  push    r15
0x18002f3ec  lea     rbp, [rax-5Fh]
0x18002f3f0  sub     rsp, 90h
0x18002f3f7  mov     rax, cs:__security_cookie
0x18002f3fe  xor     rax, rsp
0x18002f401  mov     [rbp+57h+var_30], rax
0x18002f405  mov     rbx, rcx
0x18002f408  xor     r13d, r13d
0x18002f40b  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18002f40f  test    rcx, rcx
0x18002f412  jz      loc_18002F5C1
0x18002f418  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18002f41c  mov     [rbp+57h+pControl], r13w
0x18002f421  lea     rdx, [rbp+57h+pControl]; pControl
0x18002f425  call    cs:__imp_GetSecurityDescriptorControl
0x18002f42b  test    eax, eax
0x18002f42d  jz      loc_18002F62E
0x18002f433  mov     eax, 8000h
0x18002f438  test    [rbp+57h+pControl], ax
0x18002f43c  jz      loc_18002F5C1
0x18002f442  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x18002f446  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18002f44a  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18002f44f  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18002f453  mov     [rsp+0B0h+pPrimaryGroup], r13; pPrimaryGroup
0x18002f458  lea     rax, [rbp+57h+dwOwnerSize]
0x18002f45c  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18002f461  xor     r9d, r9d; pDacl
0x18002f464  mov     [rsp+0B0h+pOwner], r13; pOwner
0x18002f469  lea     rax, [rbp+57h+dwSaclSize]
0x18002f46d  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x18002f472  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18002f474  lea     rax, [rbp+57h+dwDaclSize]
0x18002f478  mov     [rsp+0B0h+pSacl], r13; pSacl
0x18002f47d  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x18002f482  mov     [rbp+57h+dwSaclSize], r13d
0x18002f486  mov     [rbp+57h+dwDaclSize], r13d
0x18002f48a  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x18002f48e  mov     [rbp+57h+dwOwnerSize], r13d
0x18002f492  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x18002f496  call    cs:__imp_MakeAbsoluteSD
0x18002f49c  call    cs:__imp_GetLastError
0x18002f4a2  cmp     eax, 7Ah ; 'z'
0x18002f4a5  jnz     loc_18002F5EE
0x18002f4ab  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x18002f4ae  call    cs:__imp_malloc
0x18002f4b4  mov     ecx, [rbp+57h+dwOwnerSize]; Size
0x18002f4b7  mov     r12, rax
0x18002f4ba  test    ecx, ecx
0x18002f4bc  jz      short loc_18002F4C9
0x18002f4be  call    cs:__imp_malloc
0x18002f4c4  mov     r15, rax
0x18002f4c7  jmp     short loc_18002F4CC
0x18002f4c9  mov     r15, r13
0x18002f4cc  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x18002f4cf  test    eax, eax
0x18002f4d1  jz      short loc_18002F4E0
0x18002f4d3  mov     ecx, eax; Size
0x18002f4d5  call    cs:__imp_malloc
0x18002f4db  mov     r14, rax
0x18002f4de  jmp     short loc_18002F4E3
0x18002f4e0  mov     r14, r13
0x18002f4e3  mov     eax, [rbp+57h+dwDaclSize]
0x18002f4e6  test    eax, eax
0x18002f4e8  jz      short loc_18002F4FA
0x18002f4ea  mov     ecx, eax; Size
0x18002f4ec  call    cs:__imp_malloc
0x18002f4f2  mov     rsi, rax
0x18002f4f5  mov     eax, [rbp+57h+dwDaclSize]
0x18002f4f8  jmp     short loc_18002F4FD
0x18002f4fa  mov     rsi, r13
0x18002f4fd  mov     ecx, [rbp+57h+dwSaclSize]; Size
0x18002f500  test    ecx, ecx
0x18002f502  jz      short loc_18002F515
0x18002f504  call    cs:__imp_malloc
0x18002f50a  mov     ecx, [rbp+57h+dwSaclSize]
0x18002f50d  mov     rdi, rax
0x18002f510  mov     eax, [rbp+57h+dwDaclSize]
0x18002f513  jmp     short loc_18002F518
0x18002f515  mov     rdi, r13
0x18002f518  test    r12, r12
0x18002f51b  jz      loc_18002F5F4
0x18002f521  cmp     [rbp+57h+dwOwnerSize], r13d
0x18002f525  jz      short loc_18002F530
0x18002f527  test    r15, r15
0x18002f52a  jz      loc_18002F5F4
0x18002f530  cmp     [rbp+57h+dwPrimaryGroupSize], r13d
0x18002f534  jz      short loc_18002F53F
0x18002f536  test    r14, r14
0x18002f539  jz      loc_18002F5F4
0x18002f53f  test    eax, eax
0x18002f541  jz      short loc_18002F54C
0x18002f543  test    rsi, rsi
0x18002f546  jz      loc_18002F5F4
0x18002f54c  test    ecx, ecx
0x18002f54e  jz      short loc_18002F559
0x18002f550  test    rdi, rdi
0x18002f553  jz      loc_18002F5F4
0x18002f559  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x18002f55d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18002f561  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18002f566  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18002f56a  mov     [rsp+0B0h+pPrimaryGroup], r14; pPrimaryGroup
0x18002f56f  lea     rax, [rbp+57h+dwOwnerSize]
0x18002f573  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18002f578  mov     r9, rsi; pDacl
0x18002f57b  mov     [rsp+0B0h+pOwner], r15; pOwner
0x18002f580  lea     rax, [rbp+57h+dwSaclSize]
0x18002f584  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x18002f589  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x18002f58c  lea     rax, [rbp+57h+dwDaclSize]
0x18002f590  mov     [rsp+0B0h+pSacl], rdi; pSacl
0x18002f595  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x18002f59a  call    cs:__imp_MakeAbsoluteSD
0x18002f5a0  test    eax, eax
0x18002f5a2  jnz     short loc_18002F5AD
0x18002f5a4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f5a9  mov     ebx, eax
0x18002f5ab  jmp     short loc_18002F5F9
0x18002f5ad  mov     rax, [rbx]
0x18002f5b0  mov     rcx, rbx
0x18002f5b3  mov     rax, [rax+8]
0x18002f5b7  call    cs:__guard_dispatch_icall_fptr
0x18002f5bd  mov     [rbx+8], r12
0x18002f5c1  mov     rcx, [rbp+57h+var_30]
0x18002f5c5  xor     rcx, rsp; StackCookie
0x18002f5c8  call    __security_check_cookie
0x18002f5cd  lea     r11, [rsp+0B0h+var_20]
0x18002f5d5  mov     rbx, [r11+38h]
0x18002f5d9  mov     rsi, [r11+40h]
0x18002f5dd  mov     rdi, [r11+48h]
0x18002f5e1  mov     rsp, r11
0x18002f5e4  pop     r15
0x18002f5e6  pop     r14
0x18002f5e8  pop     r13
0x18002f5ea  pop     r12
0x18002f5ec  pop     rbp
0x18002f5ed  retn
0x18002f5ee  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002f5f4  mov     ebx, 8007000Eh
0x18002f5f9  mov     rcx, r12; Block
0x18002f5fc  call    cs:__imp_free
0x18002f602  mov     rcx, r15; Block
0x18002f605  call    cs:__imp_free
0x18002f60b  mov     rcx, r14; Block
0x18002f60e  call    cs:__imp_free
0x18002f614  mov     rcx, rsi; Block
0x18002f617  call    cs:__imp_free
0x18002f61d  mov     rcx, rdi; Block
0x18002f620  call    cs:__imp_free
0x18002f626  mov     ecx, ebx; int
0x18002f628  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f62e  mov     ecx, 80004005h; int
0x18002f633  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
