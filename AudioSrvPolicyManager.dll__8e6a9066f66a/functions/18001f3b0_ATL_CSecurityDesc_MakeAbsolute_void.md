# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x18001f3b0`
- end: `0x18001f623`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `627`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x18001f3b0`
- `0x18002bd78`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f5f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f5fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f603`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f60c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f615`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f5f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f5fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f603`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f60c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f615`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f479`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f4bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f4d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f588`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f5ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f479`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f4bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f4d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f588`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f467`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001f3f5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001f3f5`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001f461`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001f52a`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001f461`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18001f52a`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::MakeAbsolute(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  struct _ACL *pSacl; // rsi
  void *v4; // rcx
  void *v5; // rdi
  void *pOwner; // r12
  void *pPrimaryGroup; // r15
  struct _ACL *v8; // rax
  struct _ACL *v9; // r14
  struct _ACL *v10; // rax
  void *v11; // rax
  void *v12; // rax
  int Error; // ebx
  DWORD dwDaclSize; // [rsp+68h] [rbp+17h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp+1Bh] BYREF
  DWORD dwRevision[2]; // [rsp+70h] [rbp+1Fh] BYREF
  WORD pControl; // [rsp+B8h] [rbp+67h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+C0h] [rbp+6Fh] BYREF
  DWORD dwOwnerSize; // [rsp+C8h] [rbp+77h] BYREF
  DWORD dwSaclSize; // [rsp+D0h] [rbp+7Fh] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    pSacl = 0;
    dwRevision[0] = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, dwRevision) )
      goto LABEL_6;
    if ( (pControl & 0x8000u) != 0 )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      dwSaclSize = 0;
      dwDaclSize = 0;
      dwPrimaryGroupSize = 0;
      dwOwnerSize = 0;
      dwAbsoluteSecurityDescriptorSize = 0;
      MakeAbsoluteSD(
        v4,
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
      v5 = malloc(dwAbsoluteSecurityDescriptorSize);
      if ( !v5 )
LABEL_6:
        ATL::AtlThrowImpl(-2147467259);
      if ( dwOwnerSize )
      {
        v11 = malloc(dwOwnerSize);
        pOwner = v11;
        if ( dwOwnerSize && !v11 )
          goto LABEL_6;
      }
      else
      {
        pOwner = 0;
      }
      if ( dwPrimaryGroupSize )
      {
        v12 = malloc(dwPrimaryGroupSize);
        pPrimaryGroup = v12;
        if ( dwPrimaryGroupSize && !v12 )
          goto LABEL_6;
      }
      else
      {
        pPrimaryGroup = 0;
      }
      if ( dwDaclSize )
      {
        v8 = (struct _ACL *)malloc(dwDaclSize);
        v9 = v8;
        if ( dwDaclSize && !v8 )
          goto LABEL_6;
      }
      else
      {
        v9 = 0;
      }
      if ( dwSaclSize )
      {
        v10 = (struct _ACL *)malloc(dwSaclSize);
        pSacl = v10;
        if ( dwSaclSize )
        {
          if ( !v10 )
            goto LABEL_6;
        }
      }
      if ( !MakeAbsoluteSD(
              *((PSECURITY_DESCRIPTOR *)this + 1),
              v5,
              &dwAbsoluteSecurityDescriptorSize,
              v9,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        Error = ATL::AtlHresultFromLastError();
        free(v5);
        free(pOwner);
        free(pPrimaryGroup);
        free(v9);
        free(pSacl);
        ATL::AtlThrowImpl(Error);
      }
      (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
      *((_QWORD *)this + 1) = v5;
    }
  }
}

```

## disassembly

```asm
0x18001f3b0  mov     rax, rsp
0x18001f3b3  push    rbp
0x18001f3b4  push    rbx
0x18001f3b5  lea     rbp, [rax-5Fh]
0x18001f3b9  sub     rsp, 98h
0x18001f3c0  mov     rbx, rcx
0x18001f3c3  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18001f3c7  test    rcx, rcx
0x18001f3ca  jz      loc_18001F56D
0x18001f3d0  mov     [rax-18h], rsi
0x18001f3d4  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18001f3d8  mov     [rax-20h], rdi
0x18001f3dc  lea     rdx, [rbp+57h+pControl]; pControl
0x18001f3e0  mov     [rax-28h], r12
0x18001f3e4  xor     esi, esi
0x18001f3e6  mov     [rax-30h], r14
0x18001f3ea  mov     [rax-38h], r15
0x18001f3ee  mov     [rbp+57h+dwRevision], esi
0x18001f3f1  mov     [rbp+57h+pControl], si
0x18001f3f5  call    cs:__imp_GetSecurityDescriptorControl
0x18001f3fb  test    eax, eax
0x18001f3fd  jz      loc_18001F487
0x18001f403  mov     eax, 8000h
0x18001f408  test    [rbp+57h+pControl], ax
0x18001f40c  jz      loc_18001F54B
0x18001f412  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x18001f416  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18001f41a  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18001f41f  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001f423  mov     [rsp+0A0h+pPrimaryGroup], rsi; pPrimaryGroup
0x18001f428  lea     rax, [rbp+57h+dwOwnerSize]
0x18001f42c  mov     [rsp+0A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001f431  xor     r9d, r9d; pDacl
0x18001f434  mov     [rsp+0A0h+pOwner], rsi; pOwner
0x18001f439  lea     rax, [rbp+57h+dwSaclSize]
0x18001f43d  mov     [rsp+0A0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001f442  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18001f444  lea     rax, [rbp+57h+dwDaclSize]
0x18001f448  mov     [rsp+0A0h+pSacl], rsi; pSacl
0x18001f44d  mov     [rsp+0A0h+lpdwDaclSize], rax; lpdwDaclSize
0x18001f452  mov     [rbp+57h+dwSaclSize], esi
0x18001f455  mov     [rbp+57h+dwDaclSize], esi
0x18001f458  mov     [rbp+57h+dwPrimaryGroupSize], esi
0x18001f45b  mov     [rbp+57h+dwOwnerSize], esi
0x18001f45e  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], esi
0x18001f461  call    cs:__imp_MakeAbsoluteSD
0x18001f467  call    cs:__imp_GetLastError
0x18001f46d  cmp     eax, 7Ah ; 'z'
0x18001f470  jnz     loc_18001F57F
0x18001f476  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x18001f479  call    cs:__imp_malloc
0x18001f47f  mov     rdi, rax
0x18001f482  test    rax, rax
0x18001f485  jnz     short loc_18001F492
0x18001f487  mov     ecx, 80004005h; int
0x18001f48c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f492  mov     eax, [rbp+57h+dwOwnerSize]
0x18001f495  test    eax, eax
0x18001f497  jnz     loc_18001F585
0x18001f49d  mov     r12, rsi
0x18001f4a0  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x18001f4a3  test    eax, eax
0x18001f4a5  jnz     loc_18001F5A8
0x18001f4ab  mov     r15, rsi
0x18001f4ae  mov     eax, [rbp+57h+dwDaclSize]
0x18001f4b1  test    eax, eax
0x18001f4b3  jz      loc_18001F577
0x18001f4b9  mov     ecx, eax; Size
0x18001f4bb  call    cs:__imp_malloc
0x18001f4c1  mov     r14, rax
0x18001f4c4  cmp     [rbp+57h+dwDaclSize], esi
0x18001f4c7  jnz     loc_18001F5CB
0x18001f4cd  mov     eax, [rbp+57h+dwSaclSize]
0x18001f4d0  test    eax, eax
0x18001f4d2  jz      short loc_18001F4E9
0x18001f4d4  mov     ecx, eax; Size
0x18001f4d6  call    cs:__imp_malloc
0x18001f4dc  cmp     [rbp+57h+dwSaclSize], 0
0x18001f4e0  mov     rsi, rax
0x18001f4e3  jnz     loc_18001F5D9
0x18001f4e9  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x18001f4ed  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18001f4f1  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18001f4f6  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001f4fa  mov     [rsp+0A0h+pPrimaryGroup], r15; pPrimaryGroup
0x18001f4ff  lea     rax, [rbp+57h+dwOwnerSize]
0x18001f503  mov     [rsp+0A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001f508  mov     r9, r14; pDacl
0x18001f50b  mov     [rsp+0A0h+pOwner], r12; pOwner
0x18001f510  lea     rax, [rbp+57h+dwSaclSize]
0x18001f514  mov     [rsp+0A0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001f519  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x18001f51c  lea     rax, [rbp+57h+dwDaclSize]
0x18001f520  mov     [rsp+0A0h+pSacl], rsi; pSacl
0x18001f525  mov     [rsp+0A0h+lpdwDaclSize], rax; lpdwDaclSize
0x18001f52a  call    cs:__imp_MakeAbsoluteSD
0x18001f530  test    eax, eax
0x18001f532  jz      loc_18001F5E7
0x18001f538  mov     rax, [rbx]
0x18001f53b  mov     rcx, rbx
0x18001f53e  mov     rax, [rax+8]
0x18001f542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f547  mov     [rbx+8], rdi
0x18001f54b  mov     r14, [rsp+0A0h+var_28]
0x18001f550  mov     r12, [rsp+0A0h+var_20]
0x18001f558  mov     rdi, [rsp+0A0h+var_18]
0x18001f560  mov     r15, [rsp+0A0h+var_30]
0x18001f565  mov     rsi, [rsp+90h]
0x18001f56d  add     rsp, 98h
0x18001f574  pop     rbx
0x18001f575  pop     rbp
0x18001f576  retn
0x18001f577  mov     r14, rsi
0x18001f57a  jmp     loc_18001F4CD
0x18001f57f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18001f585  mov     rcx, rax; Size
0x18001f588  call    cs:__imp_malloc
0x18001f58e  mov     r12, rax
0x18001f591  cmp     [rbp+57h+dwOwnerSize], esi
0x18001f594  jz      loc_18001F4A0
0x18001f59a  test    rax, rax
0x18001f59d  jz      loc_18001F487
0x18001f5a3  jmp     loc_18001F4A0
0x18001f5a8  mov     rcx, rax; Size
0x18001f5ab  call    cs:__imp_malloc
0x18001f5b1  mov     r15, rax
0x18001f5b4  cmp     [rbp+57h+dwPrimaryGroupSize], esi
0x18001f5b7  jz      loc_18001F4AE
0x18001f5bd  test    rax, rax
0x18001f5c0  jz      loc_18001F487
0x18001f5c6  jmp     loc_18001F4AE
0x18001f5cb  test    rax, rax
0x18001f5ce  jz      loc_18001F487
0x18001f5d4  jmp     loc_18001F4CD
0x18001f5d9  test    rax, rax
0x18001f5dc  jz      loc_18001F487
0x18001f5e2  jmp     loc_18001F4E9
0x18001f5e7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001f5ec  mov     rcx, rdi; Block
0x18001f5ef  mov     ebx, eax
0x18001f5f1  call    cs:__imp_free
0x18001f5f7  mov     rcx, r12; Block
0x18001f5fa  call    cs:__imp_free
0x18001f600  mov     rcx, r15; Block
0x18001f603  call    cs:__imp_free
0x18001f609  mov     rcx, r14; Block
0x18001f60c  call    cs:__imp_free
0x18001f612  mov     rcx, rsi; Block
0x18001f615  call    cs:__imp_free
0x18001f61b  mov     ecx, ebx; int
0x18001f61d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
