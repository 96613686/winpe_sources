# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x140010a58`
- end: `0x140010c97`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `575`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012754`
- `0x140012fa8`
- `0x140013104`

## callees

- `0x14000a220`
- `0x14000a2e8`
- `0x14000a310`
- `0x140010a58`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x140010b1b`
- `ADVAPI32!MakeAbsoluteSD` at `0x140010c1e`
- `ADVAPI32!MakeAbsoluteSD` at `0x140010b1b`
- `ADVAPI32!MakeAbsoluteSD` at `0x140010c1e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140010a8f`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140010a8f`
- `KERNEL32!GetLastError` at `0x140010b21`
- `KERNEL32!GetLastError` at `0x140010b21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c78`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140010c78`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b4c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b73`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b9a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010bc0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b4c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b73`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010b9a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140010bc0`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::MakeAbsolute(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // r12
  DWORD v5; // ecx
  void *v6; // rax
  void *pOwner; // r15
  DWORD v8; // eax
  void *pPrimaryGroup; // r14
  DWORD v10; // eax
  ACL *v11; // rsi
  DWORD v12; // eax
  ACL *pSacl; // rdi
  int Error; // ebx
  DWORD dwDaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+64h] [rbp-Ch] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp-8h] BYREF
  WORD pControl; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+B8h] [rbp+48h] BYREF
  DWORD dwOwnerSize; // [rsp+C0h] [rbp+50h] BYREF
  DWORD dwSaclSize; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, &dwRevision) )
      goto LABEL_30;
    if ( (pControl & 0x8000u) == 0 )
      return;
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
    if ( !v4 )
      goto LABEL_30;
    v5 = dwOwnerSize;
    if ( dwOwnerSize )
    {
      v6 = malloc(dwOwnerSize);
      v5 = dwOwnerSize;
      pOwner = v6;
    }
    else
    {
      pOwner = 0;
    }
    if ( v5 && !pOwner )
      goto LABEL_30;
    v8 = dwPrimaryGroupSize;
    if ( dwPrimaryGroupSize )
    {
      pPrimaryGroup = malloc(dwPrimaryGroupSize);
      v8 = dwPrimaryGroupSize;
    }
    else
    {
      pPrimaryGroup = 0;
    }
    if ( v8 && !pPrimaryGroup
      || ((v10 = dwDaclSize) == 0 ? (v11 = 0) : (ACL *)(v11 = (ACL *)malloc(dwDaclSize), v10 = dwDaclSize),
          v10 && !v11
       || ((v12 = dwSaclSize) == 0 ? (pSacl = 0) : (ACL *)(pSacl = (ACL *)malloc(dwSaclSize), v12 = dwSaclSize),
           v12 && !pSacl)) )
    {
LABEL_30:
      ATL::AtlThrowImpl(-2147467259);
    }
    if ( !MakeAbsoluteSD(
            *((PSECURITY_DESCRIPTOR *)this + 1),
            v4,
            &dwAbsoluteSecurityDescriptorSize,
            v11,
            &dwDaclSize,
            pSacl,
            &dwSaclSize,
            pOwner,
            &dwOwnerSize,
            pPrimaryGroup,
            &dwPrimaryGroupSize) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(v4);
      free(pOwner);
      free(pPrimaryGroup);
      free(v11);
      free(pSacl);
      ATL::AtlThrowImpl(Error);
    }
    (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
    *((_QWORD *)this + 1) = v4;
  }
}

```

## disassembly

```asm
0x140010a58  push    rbp
0x140010a5a  push    rbx
0x140010a5b  push    rsi
0x140010a5c  push    rdi
0x140010a5d  push    r12
0x140010a5f  push    r14
0x140010a61  push    r15
0x140010a63  mov     rbp, rsp
0x140010a66  sub     rsp, 70h
0x140010a6a  mov     rbx, rcx
0x140010a6d  mov     rcx, [rcx+8]; pSecurityDescriptor
0x140010a71  test    rcx, rcx
0x140010a74  jz      loc_140010C3B
0x140010a7a  xor     eax, eax
0x140010a7c  mov     [rbp+dwRevision], 0
0x140010a83  lea     r8, [rbp+dwRevision]; lpdwRevision
0x140010a87  mov     [rbp+pControl], ax
0x140010a8b  lea     rdx, [rbp+pControl]; pControl
0x140010a8f  call    cs:__imp_GetSecurityDescriptorControl
0x140010a95  test    eax, eax
0x140010a97  jz      loc_140010C86
0x140010a9d  mov     eax, 8000h
0x140010aa2  test    [rbp+pControl], ax
0x140010aa6  jz      loc_140010C3B
0x140010aac  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140010ab0  lea     rax, [rbp+dwPrimaryGroupSize]
0x140010ab4  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140010ab9  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140010abd  mov     [rsp+70h+pPrimaryGroup], 0; pPrimaryGroup
0x140010ac6  lea     rax, [rbp+dwOwnerSize]
0x140010aca  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140010acf  xor     r9d, r9d; pDacl
0x140010ad2  mov     [rsp+70h+pOwner], 0; pOwner
0x140010adb  lea     rax, [rbp+dwSaclSize]
0x140010adf  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x140010ae4  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140010ae6  lea     rax, [rbp+dwDaclSize]
0x140010aea  mov     [rsp+70h+pSacl], 0; pSacl
0x140010af3  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x140010af8  mov     [rbp+dwSaclSize], 0
0x140010aff  mov     [rbp+dwDaclSize], 0
0x140010b06  mov     [rbp+dwPrimaryGroupSize], 0
0x140010b0d  mov     [rbp+dwOwnerSize], 0
0x140010b14  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 0
0x140010b1b  call    cs:__imp_MakeAbsoluteSD
0x140010b21  call    cs:__imp_GetLastError
0x140010b27  cmp     eax, 7Ah ; 'z'
0x140010b2a  jnz     loc_140010C91
0x140010b30  mov     ecx, [rbp+dwAbsoluteSecurityDescriptorSize]; Size
0x140010b33  call    cs:__imp_malloc
0x140010b39  mov     r12, rax
0x140010b3c  test    rax, rax
0x140010b3f  jz      loc_140010C86
0x140010b45  mov     ecx, [rbp+dwOwnerSize]; Size
0x140010b48  test    ecx, ecx
0x140010b4a  jz      short loc_140010B5A
0x140010b4c  call    cs:__imp_malloc
0x140010b52  mov     ecx, [rbp+dwOwnerSize]
0x140010b55  mov     r15, rax
0x140010b58  jmp     short loc_140010B5D
0x140010b5a  xor     r15d, r15d
0x140010b5d  test    ecx, ecx
0x140010b5f  jz      short loc_140010B6A
0x140010b61  test    r15, r15
0x140010b64  jz      loc_140010C86
0x140010b6a  mov     eax, [rbp+dwPrimaryGroupSize]
0x140010b6d  test    eax, eax
0x140010b6f  jz      short loc_140010B81
0x140010b71  mov     ecx, eax; Size
0x140010b73  call    cs:__imp_malloc
0x140010b79  mov     r14, rax
0x140010b7c  mov     eax, [rbp+dwPrimaryGroupSize]
0x140010b7f  jmp     short loc_140010B84
0x140010b81  xor     r14d, r14d
0x140010b84  test    eax, eax
0x140010b86  jz      short loc_140010B91
0x140010b88  test    r14, r14
0x140010b8b  jz      loc_140010C86
0x140010b91  mov     eax, [rbp+dwDaclSize]
0x140010b94  test    eax, eax
0x140010b96  jz      short loc_140010BA8
0x140010b98  mov     ecx, eax; Size
0x140010b9a  call    cs:__imp_malloc
0x140010ba0  mov     rsi, rax
0x140010ba3  mov     eax, [rbp+dwDaclSize]
0x140010ba6  jmp     short loc_140010BAA
0x140010ba8  xor     esi, esi
0x140010baa  test    eax, eax
0x140010bac  jz      short loc_140010BB7
0x140010bae  test    rsi, rsi
0x140010bb1  jz      loc_140010C86
0x140010bb7  mov     eax, [rbp+dwSaclSize]
0x140010bba  test    eax, eax
0x140010bbc  jz      short loc_140010BCE
0x140010bbe  mov     ecx, eax; Size
0x140010bc0  call    cs:__imp_malloc
0x140010bc6  mov     rdi, rax
0x140010bc9  mov     eax, [rbp+dwSaclSize]
0x140010bcc  jmp     short loc_140010BD0
0x140010bce  xor     edi, edi
0x140010bd0  test    eax, eax
0x140010bd2  jz      short loc_140010BDD
0x140010bd4  test    rdi, rdi
0x140010bd7  jz      loc_140010C86
0x140010bdd  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140010be1  lea     rax, [rbp+dwPrimaryGroupSize]
0x140010be5  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140010bea  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140010bee  mov     [rsp+70h+pPrimaryGroup], r14; pPrimaryGroup
0x140010bf3  lea     rax, [rbp+dwOwnerSize]
0x140010bf7  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140010bfc  mov     r9, rsi; pDacl
0x140010bff  mov     [rsp+70h+pOwner], r15; pOwner
0x140010c04  lea     rax, [rbp+dwSaclSize]
0x140010c08  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x140010c0d  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x140010c10  lea     rax, [rbp+dwDaclSize]
0x140010c14  mov     [rsp+70h+pSacl], rdi; pSacl
0x140010c19  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x140010c1e  call    cs:__imp_MakeAbsoluteSD
0x140010c24  test    eax, eax
0x140010c26  jz      short loc_140010C4A
0x140010c28  mov     rax, [rbx]
0x140010c2b  mov     rcx, rbx
0x140010c2e  mov     rax, [rax+8]
0x140010c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c37  mov     [rbx+8], r12
0x140010c3b  add     rsp, 70h
0x140010c3f  pop     r15
0x140010c41  pop     r14
0x140010c43  pop     r12
0x140010c45  pop     rdi
0x140010c46  pop     rsi
0x140010c47  pop     rbx
0x140010c48  pop     rbp
0x140010c49  retn
0x140010c4a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140010c4f  mov     rcx, r12; Block
0x140010c52  mov     ebx, eax
0x140010c54  call    cs:__imp_free
0x140010c5a  mov     rcx, r15; Block
0x140010c5d  call    cs:__imp_free
0x140010c63  mov     rcx, r14; Block
0x140010c66  call    cs:__imp_free
0x140010c6c  mov     rcx, rsi; Block
0x140010c6f  call    cs:__imp_free
0x140010c75  mov     rcx, rdi; Block
0x140010c78  call    cs:__imp_free
0x140010c7e  mov     ecx, ebx; int
0x140010c80  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140010c86  mov     ecx, 80004005h; int
0x140010c8b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140010c91  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
