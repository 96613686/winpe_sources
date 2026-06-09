# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x140011de4`
- end: `0x140012049`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `613`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400121e0`

## callees

- `0x140002e74`
- `0x14000914c`
- `0x14000916c`
- `0x140011de4`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140011eac`
- `KERNEL32!GetLastError` at `0x140011eac`
- `ADVAPI32!MakeAbsoluteSD` at `0x140011ea6`
- `ADVAPI32!MakeAbsoluteSD` at `0x140011faa`
- `ADVAPI32!MakeAbsoluteSD` at `0x140011ea6`
- `ADVAPI32!MakeAbsoluteSD` at `0x140011faa`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140011e35`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140011e35`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ebe`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ece`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ee5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011efc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011f14`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ebe`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ece`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011ee5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011efc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011f14`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001200c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012015`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001201e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012027`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012030`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001200c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012015`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001201e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012027`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012030`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140011de4  mov     rax, rsp
0x140011de7  mov     [rax+10h], rbx
0x140011deb  mov     [rax+18h], rsi
0x140011def  mov     [rax+20h], rdi
0x140011df3  push    rbp
0x140011df4  push    r12
0x140011df6  push    r13
0x140011df8  push    r14
0x140011dfa  push    r15
0x140011dfc  lea     rbp, [rax-5Fh]
0x140011e00  sub     rsp, 90h
0x140011e07  mov     rax, cs:__security_cookie
0x140011e0e  xor     rax, rsp
0x140011e11  mov     [rbp+57h+var_30], rax
0x140011e15  mov     rbx, rcx
0x140011e18  xor     r13d, r13d
0x140011e1b  mov     rcx, [rcx+8]; pSecurityDescriptor
0x140011e1f  test    rcx, rcx
0x140011e22  jz      loc_140011FD1
0x140011e28  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x140011e2c  mov     [rbp+57h+pControl], r13w
0x140011e31  lea     rdx, [rbp+57h+pControl]; pControl
0x140011e35  call    cs:__imp_GetSecurityDescriptorControl
0x140011e3b  test    eax, eax
0x140011e3d  jz      loc_14001203E
0x140011e43  mov     eax, 8000h
0x140011e48  test    [rbp+57h+pControl], ax
0x140011e4c  jz      loc_140011FD1
0x140011e52  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140011e56  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140011e5a  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140011e5f  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140011e63  mov     [rsp+0B0h+pPrimaryGroup], r13; pPrimaryGroup
0x140011e68  lea     rax, [rbp+57h+dwOwnerSize]
0x140011e6c  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140011e71  xor     r9d, r9d; pDacl
0x140011e74  mov     [rsp+0B0h+pOwner], r13; pOwner
0x140011e79  lea     rax, [rbp+57h+dwSaclSize]
0x140011e7d  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x140011e82  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140011e84  lea     rax, [rbp+57h+dwDaclSize]
0x140011e88  mov     [rsp+0B0h+pSacl], r13; pSacl
0x140011e8d  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x140011e92  mov     [rbp+57h+dwSaclSize], r13d
0x140011e96  mov     [rbp+57h+dwDaclSize], r13d
0x140011e9a  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x140011e9e  mov     [rbp+57h+dwOwnerSize], r13d
0x140011ea2  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x140011ea6  call    cs:__imp_MakeAbsoluteSD
0x140011eac  call    cs:__imp_GetLastError
0x140011eb2  cmp     eax, 7Ah ; 'z'
0x140011eb5  jnz     loc_140011FFE
0x140011ebb  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x140011ebe  call    cs:__imp_malloc
0x140011ec4  mov     ecx, [rbp+57h+dwOwnerSize]; Size
0x140011ec7  mov     r12, rax
0x140011eca  test    ecx, ecx
0x140011ecc  jz      short loc_140011ED9
0x140011ece  call    cs:__imp_malloc
0x140011ed4  mov     r15, rax
0x140011ed7  jmp     short loc_140011EDC
0x140011ed9  mov     r15, r13
0x140011edc  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x140011edf  test    eax, eax
0x140011ee1  jz      short loc_140011EF0
0x140011ee3  mov     ecx, eax; Size
0x140011ee5  call    cs:__imp_malloc
0x140011eeb  mov     r14, rax
0x140011eee  jmp     short loc_140011EF3
0x140011ef0  mov     r14, r13
0x140011ef3  mov     eax, [rbp+57h+dwDaclSize]
0x140011ef6  test    eax, eax
0x140011ef8  jz      short loc_140011F0A
0x140011efa  mov     ecx, eax; Size
0x140011efc  call    cs:__imp_malloc
0x140011f02  mov     rsi, rax
0x140011f05  mov     eax, [rbp+57h+dwDaclSize]
0x140011f08  jmp     short loc_140011F0D
0x140011f0a  mov     rsi, r13
0x140011f0d  mov     ecx, [rbp+57h+dwSaclSize]; Size
0x140011f10  test    ecx, ecx
0x140011f12  jz      short loc_140011F25
0x140011f14  call    cs:__imp_malloc
0x140011f1a  mov     ecx, [rbp+57h+dwSaclSize]
0x140011f1d  mov     rdi, rax
0x140011f20  mov     eax, [rbp+57h+dwDaclSize]
0x140011f23  jmp     short loc_140011F28
0x140011f25  mov     rdi, r13
0x140011f28  test    r12, r12
0x140011f2b  jz      loc_140012004
0x140011f31  cmp     [rbp+57h+dwOwnerSize], r13d
0x140011f35  jz      short loc_140011F40
0x140011f37  test    r15, r15
0x140011f3a  jz      loc_140012004
0x140011f40  cmp     [rbp+57h+dwPrimaryGroupSize], r13d
0x140011f44  jz      short loc_140011F4F
0x140011f46  test    r14, r14
0x140011f49  jz      loc_140012004
0x140011f4f  test    eax, eax
0x140011f51  jz      short loc_140011F5C
0x140011f53  test    rsi, rsi
0x140011f56  jz      loc_140012004
0x140011f5c  test    ecx, ecx
0x140011f5e  jz      short loc_140011F69
0x140011f60  test    rdi, rdi
0x140011f63  jz      loc_140012004
0x140011f69  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140011f6d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140011f71  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140011f76  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140011f7a  mov     [rsp+0B0h+pPrimaryGroup], r14; pPrimaryGroup
0x140011f7f  lea     rax, [rbp+57h+dwOwnerSize]
0x140011f83  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140011f88  mov     r9, rsi; pDacl
0x140011f8b  mov     [rsp+0B0h+pOwner], r15; pOwner
0x140011f90  lea     rax, [rbp+57h+dwSaclSize]
0x140011f94  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x140011f99  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x140011f9c  lea     rax, [rbp+57h+dwDaclSize]
0x140011fa0  mov     [rsp+0B0h+pSacl], rdi; pSacl
0x140011fa5  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x140011faa  call    cs:__imp_MakeAbsoluteSD
0x140011fb0  test    eax, eax
0x140011fb2  jnz     short loc_140011FBD
0x140011fb4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140011fb9  mov     ebx, eax
0x140011fbb  jmp     short loc_140012009
0x140011fbd  mov     rax, [rbx]
0x140011fc0  mov     rcx, rbx
0x140011fc3  mov     rax, [rax+8]
0x140011fc7  call    cs:__guard_dispatch_icall_fptr
0x140011fcd  mov     [rbx+8], r12
0x140011fd1  mov     rcx, [rbp+57h+var_30]
0x140011fd5  xor     rcx, rsp; StackCookie
0x140011fd8  call    __security_check_cookie
0x140011fdd  lea     r11, [rsp+0B0h+var_20]
0x140011fe5  mov     rbx, [r11+38h]
0x140011fe9  mov     rsi, [r11+40h]
0x140011fed  mov     rdi, [r11+48h]
0x140011ff1  mov     rsp, r11
0x140011ff4  pop     r15
0x140011ff6  pop     r14
0x140011ff8  pop     r13
0x140011ffa  pop     r12
0x140011ffc  pop     rbp
0x140011ffd  retn
0x140011ffe  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140012004  mov     ebx, 8007000Eh
0x140012009  mov     rcx, r12; Block
0x14001200c  call    cs:__imp_free
0x140012012  mov     rcx, r15; Block
0x140012015  call    cs:__imp_free
0x14001201b  mov     rcx, r14; Block
0x14001201e  call    cs:__imp_free
0x140012024  mov     rcx, rsi; Block
0x140012027  call    cs:__imp_free
0x14001202d  mov     rcx, rdi; Block
0x140012030  call    cs:__imp_free
0x140012036  mov     ecx, ebx; int
0x140012038  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001203e  mov     ecx, 80004005h; int
0x140012043  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
