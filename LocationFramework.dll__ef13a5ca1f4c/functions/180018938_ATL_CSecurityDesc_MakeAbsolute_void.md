# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x180018938`
- end: `0x180018b9f`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `615`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800187c0`
- `0x18001e4dc`

## callees

- `0x180018938`
- `0x18001e838`
- `0x18009e0f8`
- `0x18009e2e4`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b67`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b67`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b79`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a56`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a6f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a96`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018abd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018ae3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a56`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a6f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018a96`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018abd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a42`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018985`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018985`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180018a3c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180018b41`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180018a3c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180018b41`

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
  struct _ACL *v11; // rsi
  DWORD v12; // eax
  struct _ACL *pSacl; // rdi
  int LastErrorAsHResult; // ebx
  DWORD dwPrimaryGroupSize; // [rsp+60h] [rbp+7h] BYREF
  DWORD dwOwnerSize; // [rsp+64h] [rbp+Bh] BYREF
  DWORD dwSaclSize; // [rsp+68h] [rbp+Fh] BYREF
  DWORD dwDaclSize; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp+17h] BYREF
  WORD pControl; // [rsp+74h] [rbp+1Bh] BYREF
  DWORD dwRevision; // [rsp+78h] [rbp+1Fh] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, &dwRevision) )
      goto LABEL_3;
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
      if ( !v4 )
        goto LABEL_3;
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
        goto LABEL_3;
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
        || ((v10 = dwDaclSize) == 0
          ? (v11 = 0)
          : (struct _ACL *)(v11 = (struct _ACL *)malloc(dwDaclSize), v10 = dwDaclSize),
            v10 && !v11
         || ((v12 = dwSaclSize) == 0
           ? (pSacl = 0)
           : (struct _ACL *)(pSacl = (struct _ACL *)malloc(dwSaclSize), v12 = dwSaclSize),
             v12 && !pSacl)) )
      {
LABEL_3:
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
        LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
        free(v4);
        free(pOwner);
        free(pPrimaryGroup);
        free(v11);
        free(pSacl);
        ATL::AtlThrowImpl(LastErrorAsHResult);
      }
      (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
      *((_QWORD *)this + 1) = v4;
    }
  }
}

```

## disassembly

```asm
0x180018938  mov     [rsp-8+arg_8], rbx
0x18001893d  mov     [rsp-8+arg_10], rsi
0x180018942  push    rbp
0x180018943  push    rdi
0x180018944  push    r12
0x180018946  push    r14
0x180018948  push    r15
0x18001894a  lea     rbp, [rsp-37h]
0x18001894f  sub     rsp, 90h
0x180018956  mov     rax, cs:__security_cookie
0x18001895d  xor     rax, rsp
0x180018960  mov     [rbp+57h+var_30], rax
0x180018964  mov     rbx, rcx
0x180018967  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18001896b  test    rcx, rcx
0x18001896e  jz      short loc_1800189A5
0x180018970  xor     eax, eax
0x180018972  mov     [rbp+57h+dwRevision], 0
0x180018979  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18001897d  mov     [rbp+57h+pControl], ax
0x180018981  lea     rdx, [rbp+57h+pControl]; pControl
0x180018985  call    cs:__imp_GetSecurityDescriptorControl
0x18001898b  test    eax, eax
0x18001898d  jnz     short loc_18001899A
0x18001898f  mov     ecx, 80004005h; int
0x180018994  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001899a  mov     eax, 8000h
0x18001899f  test    [rbp+57h+pControl], ax
0x1800189a3  jnz     short loc_1800189CD
0x1800189a5  mov     rcx, [rbp+57h+var_30]
0x1800189a9  xor     rcx, rsp; StackCookie
0x1800189ac  call    __security_check_cookie
0x1800189b1  lea     r11, [rsp+0B0h+var_20]
0x1800189b9  mov     rbx, [r11+38h]
0x1800189bd  mov     rsi, [r11+40h]
0x1800189c1  mov     rsp, r11
0x1800189c4  pop     r15
0x1800189c6  pop     r14
0x1800189c8  pop     r12
0x1800189ca  pop     rdi
0x1800189cb  pop     rbp
0x1800189cc  retn
0x1800189cd  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x1800189d1  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800189d5  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800189da  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800189de  mov     [rsp+0B0h+pPrimaryGroup], 0; pPrimaryGroup
0x1800189e7  lea     rax, [rbp+57h+dwOwnerSize]
0x1800189eb  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800189f0  xor     r9d, r9d; pDacl
0x1800189f3  mov     [rsp+0B0h+pOwner], 0; pOwner
0x1800189fc  lea     rax, [rbp+57h+dwSaclSize]
0x180018a00  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x180018a05  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180018a07  lea     rax, [rbp+57h+dwDaclSize]
0x180018a0b  mov     [rsp+0B0h+pSacl], 0; pSacl
0x180018a14  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x180018a19  mov     [rbp+57h+dwSaclSize], 0
0x180018a20  mov     [rbp+57h+dwDaclSize], 0
0x180018a27  mov     [rbp+57h+dwPrimaryGroupSize], 0
0x180018a2e  mov     [rbp+57h+dwOwnerSize], 0
0x180018a35  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 0
0x180018a3c  call    cs:__imp_MakeAbsoluteSD
0x180018a42  call    cs:__imp_GetLastError
0x180018a48  cmp     eax, 7Ah ; 'z'
0x180018a4b  jz      short loc_180018A53
0x180018a4d  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180018a53  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x180018a56  call    cs:__imp_malloc
0x180018a5c  mov     r12, rax
0x180018a5f  test    rax, rax
0x180018a62  jz      loc_18001898F
0x180018a68  mov     ecx, [rbp+57h+dwOwnerSize]; Size
0x180018a6b  test    ecx, ecx
0x180018a6d  jz      short loc_180018A7D
0x180018a6f  call    cs:__imp_malloc
0x180018a75  mov     ecx, [rbp+57h+dwOwnerSize]
0x180018a78  mov     r15, rax
0x180018a7b  jmp     short loc_180018A80
0x180018a7d  xor     r15d, r15d
0x180018a80  test    ecx, ecx
0x180018a82  jz      short loc_180018A8D
0x180018a84  test    r15, r15
0x180018a87  jz      loc_18001898F
0x180018a8d  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x180018a90  test    eax, eax
0x180018a92  jz      short loc_180018AA4
0x180018a94  mov     ecx, eax; Size
0x180018a96  call    cs:__imp_malloc
0x180018a9c  mov     r14, rax
0x180018a9f  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x180018aa2  jmp     short loc_180018AA7
0x180018aa4  xor     r14d, r14d
0x180018aa7  test    eax, eax
0x180018aa9  jz      short loc_180018AB4
0x180018aab  test    r14, r14
0x180018aae  jz      loc_18001898F
0x180018ab4  mov     eax, [rbp+57h+dwDaclSize]
0x180018ab7  test    eax, eax
0x180018ab9  jz      short loc_180018ACB
0x180018abb  mov     ecx, eax; Size
0x180018abd  call    cs:__imp_malloc
0x180018ac3  mov     rsi, rax
0x180018ac6  mov     eax, [rbp+57h+dwDaclSize]
0x180018ac9  jmp     short loc_180018ACD
0x180018acb  xor     esi, esi
0x180018acd  test    eax, eax
0x180018acf  jz      short loc_180018ADA
0x180018ad1  test    rsi, rsi
0x180018ad4  jz      loc_18001898F
0x180018ada  mov     eax, [rbp+57h+dwSaclSize]
0x180018add  test    eax, eax
0x180018adf  jz      short loc_180018AF1
0x180018ae1  mov     ecx, eax; Size
0x180018ae3  call    cs:__imp_malloc
0x180018ae9  mov     rdi, rax
0x180018aec  mov     eax, [rbp+57h+dwSaclSize]
0x180018aef  jmp     short loc_180018AF3
0x180018af1  xor     edi, edi
0x180018af3  test    eax, eax
0x180018af5  jz      short loc_180018B00
0x180018af7  test    rdi, rdi
0x180018afa  jz      loc_18001898F
0x180018b00  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x180018b04  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180018b08  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180018b0d  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180018b11  mov     [rsp+0B0h+pPrimaryGroup], r14; pPrimaryGroup
0x180018b16  lea     rax, [rbp+57h+dwOwnerSize]
0x180018b1a  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180018b1f  mov     r9, rsi; pDacl
0x180018b22  mov     [rsp+0B0h+pOwner], r15; pOwner
0x180018b27  lea     rax, [rbp+57h+dwSaclSize]
0x180018b2b  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x180018b30  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x180018b33  lea     rax, [rbp+57h+dwDaclSize]
0x180018b37  mov     [rsp+0B0h+pSacl], rdi; pSacl
0x180018b3c  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x180018b41  call    cs:__imp_MakeAbsoluteSD
0x180018b47  test    eax, eax
0x180018b49  jnz     short loc_180018B87
0x180018b4b  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x180018b50  mov     rcx, r12; Block
0x180018b53  mov     ebx, eax
0x180018b55  call    cs:__imp_free
0x180018b5b  mov     rcx, r15; Block
0x180018b5e  call    cs:__imp_free
0x180018b64  mov     rcx, r14; Block
0x180018b67  call    cs:__imp_free
0x180018b6d  mov     rcx, rsi; Block
0x180018b70  call    cs:__imp_free
0x180018b76  mov     rcx, rdi; Block
0x180018b79  call    cs:__imp_free
0x180018b7f  mov     ecx, ebx; int
0x180018b81  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018b87  mov     rax, [rbx]
0x180018b8a  mov     rcx, rbx
0x180018b8d  mov     rax, [rax+8]
0x180018b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b96  mov     [rbx+8], r12
0x180018b9a  jmp     loc_1800189A5
```
