# CSharedMemBlock::InitSD(void)

- ea: `0x180001c90`
- end: `0x180001ebc`
- name: `?InitSD@CSharedMemBlock@@QEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CSharedMemBlock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003248`

## callees

- `0x180001c90`
- `0x180001ec4`

## import_xrefs

- `msvcrt!malloc` at `0x180001d50`
- `msvcrt!malloc` at `0x180001d50`
- `msvcrt!free` at `0x180024b74`
- `msvcrt!free` at `0x180024b74`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180001e42`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180001e42`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180001e28`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180001e28`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001d96`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001db4`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001dd2`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001df0`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001e0e`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001d96`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001db4`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001dd2`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001df0`
- `ADVAPI32!AddAccessAllowedAce` at `0x180001e0e`
- `ADVAPI32!InitializeAcl` at `0x180001d72`
- `ADVAPI32!InitializeAcl` at `0x180001d72`
- `ADVAPI32!GetLengthSid` at `0x180001d09`
- `ADVAPI32!GetLengthSid` at `0x180001d16`
- `ADVAPI32!GetLengthSid` at `0x180001d23`
- `ADVAPI32!GetLengthSid` at `0x180001d30`
- `ADVAPI32!GetLengthSid` at `0x180001d3d`
- `ADVAPI32!GetLengthSid` at `0x180001d09`
- `ADVAPI32!GetLengthSid` at `0x180001d16`
- `ADVAPI32!GetLengthSid` at `0x180001d23`
- `ADVAPI32!GetLengthSid` at `0x180001d30`
- `ADVAPI32!GetLengthSid` at `0x180001d3d`
- `ADVAPI32!FreeSid` at `0x180001e6a`
- `ADVAPI32!FreeSid` at `0x180001e79`
- `ADVAPI32!FreeSid` at `0x180001e88`
- `ADVAPI32!FreeSid` at `0x180001e97`
- `ADVAPI32!FreeSid` at `0x180001e6a`
- `ADVAPI32!FreeSid` at `0x180001e79`
- `ADVAPI32!FreeSid` at `0x180001e88`
- `ADVAPI32!FreeSid` at `0x180001e97`
- `KERNEL32!LocalFree` at `0x180001e5b`
- `KERNEL32!LocalFree` at `0x180001e5b`
- `KERNEL32!GetLastError` at `0x180024b4a`
- `KERNEL32!GetLastError` at `0x180024b4a`

## pseudocode

```c
__int64 __fastcall CSharedMemBlock::InitSD(CSharedMemBlock *this)
{
  bool v1; // zf
  ACL *v3; // rbx
  signed int v4; // edi
  DWORD LengthSid; // r12d
  DWORD v6; // r12d
  DWORD v7; // r12d
  DWORD v8; // r12d
  DWORD v9; // r12d
  ACL *v10; // rax
  ACL *v11; // rsi
  signed int LastError; // eax
  PSID pSid; // [rsp+30h] [rbp-18h] BYREF
  PSID hMem; // [rsp+80h] [rbp+38h] BYREF
  PSID v16; // [rsp+88h] [rbp+40h] BYREF
  PSID v17; // [rsp+90h] [rbp+48h] BYREF
  PSID v18; // [rsp+98h] [rbp+50h] BYREF

  v1 = *((_QWORD *)this + 3) == 0;
  hMem = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  pSid = 0;
  if ( !v1 )
    return 0;
  v3 = 0;
  v4 = CSharedMemBlock::CreateSids(this, &v16, &v17, &hMem, &v18, &pSid);
  if ( v4 >= 0 )
  {
    LengthSid = GetLengthSid(pSid);
    v6 = GetLengthSid(v18) + LengthSid;
    v7 = GetLengthSid(v17) + v6;
    v8 = GetLengthSid(v16) + v7;
    v9 = GetLengthSid(hMem) + 48 + v8;
    v10 = (ACL *)malloc(v9 + 40LL);
    v3 = v10;
    if ( v10 )
    {
      v11 = v10 + 5;
      if ( !InitializeAcl(v10 + 5, v9, 2u)
        || !AddAccessAllowedAce(v11, 2u, 0xC0100000, hMem)
        || !AddAccessAllowedAce(v11, 2u, 0xC0100000, v17)
        || !AddAccessAllowedAce(v11, 2u, 0xC0100000, v16)
        || !AddAccessAllowedAce(v11, 2u, 0x80100000, v18)
        || !AddAccessAllowedAce(v11, 2u, 0x80100000, pSid)
        || !InitializeSecurityDescriptor(v3, 1u)
        || !SetSecurityDescriptorDacl(v3, 1, v11, 0) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v16 )
    FreeSid(v16);
  if ( v17 )
    FreeSid(v17);
  if ( v18 )
    FreeSid(v18);
  if ( pSid )
    FreeSid(pSid);
  if ( v4 < 0 )
  {
    if ( v3 )
    {
      free(v3);
      v3 = 0;
    }
  }
  *((_QWORD *)this + 3) = v3;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001c90  push    rbp
0x180001c92  push    rbx
0x180001c93  push    rsi
0x180001c94  push    rdi
0x180001c95  push    r12
0x180001c97  push    r15
0x180001c99  mov     rbp, rsp
0x180001c9c  sub     rsp, 48h
0x180001ca0  cmp     qword ptr [rcx+18h], 0
0x180001ca5  mov     r15, rcx
0x180001ca8  mov     [rbp+hMem], 0
0x180001cb0  mov     [rbp+arg_8], 0
0x180001cb8  mov     [rbp+arg_10], 0
0x180001cc0  mov     [rbp+arg_18], 0
0x180001cc8  mov     [rbp+pSid], 0
0x180001cd0  jnz     loc_180001EB8
0x180001cd6  lea     rax, [rbp+pSid]
0x180001cda  xor     ebx, ebx
0x180001cdc  mov     [rsp+48h+var_20], rax; void **
0x180001ce1  lea     r9, [rbp+hMem]; void **
0x180001ce5  lea     rax, [rbp+arg_18]
0x180001ce9  lea     r8, [rbp+arg_10]; void **
0x180001ced  mov     [rsp+48h+var_28], rax; void **
0x180001cf2  lea     rdx, [rbp+arg_8]; void **
0x180001cf6  call    ?CreateSids@CSharedMemBlock@@AEAAJPEAPEAX0000@Z; CSharedMemBlock::CreateSids(void * *,void * *,void * *,void * *,void * *)
0x180001cfb  mov     edi, eax
0x180001cfd  test    eax, eax
0x180001cff  js      loc_180001E50
0x180001d05  mov     rcx, [rbp+pSid]; pSid
0x180001d09  call    cs:__imp_GetLengthSid
0x180001d0f  mov     rcx, [rbp+arg_18]; pSid
0x180001d13  mov     r12d, eax
0x180001d16  call    cs:__imp_GetLengthSid
0x180001d1c  mov     rcx, [rbp+arg_10]; pSid
0x180001d20  add     r12d, eax
0x180001d23  call    cs:__imp_GetLengthSid
0x180001d29  mov     rcx, [rbp+arg_8]; pSid
0x180001d2d  add     r12d, eax
0x180001d30  call    cs:__imp_GetLengthSid
0x180001d36  mov     rcx, [rbp+hMem]; pSid
0x180001d3a  add     r12d, eax
0x180001d3d  call    cs:__imp_GetLengthSid
0x180001d43  add     eax, 30h ; '0'
0x180001d46  add     r12d, eax
0x180001d49  mov     ecx, r12d
0x180001d4c  add     rcx, 28h ; '('; Size
0x180001d50  call    cs:__imp_malloc
0x180001d56  mov     rbx, rax
0x180001d59  test    rax, rax
0x180001d5c  jz      loc_180024B40
0x180001d62  lea     rsi, [rax+28h]
0x180001d66  mov     r8d, 2; dwAclRevision
0x180001d6c  mov     rcx, rsi; pAcl
0x180001d6f  mov     edx, r12d; nAclLength
0x180001d72  call    cs:__imp_InitializeAcl
0x180001d78  test    eax, eax
0x180001d7a  jz      loc_180024B4A
0x180001d80  mov     r9, [rbp+hMem]; pSid
0x180001d84  mov     r12d, 2
0x180001d8a  mov     edx, r12d; dwAceRevision
0x180001d8d  mov     r8d, 0C0100000h; AccessMask
0x180001d93  mov     rcx, rsi; pAcl
0x180001d96  call    cs:__imp_AddAccessAllowedAce
0x180001d9c  test    eax, eax
0x180001d9e  jz      loc_180024B4A
0x180001da4  mov     r9, [rbp+arg_10]; pSid
0x180001da8  mov     r8d, 0C0100000h; AccessMask
0x180001dae  mov     edx, r12d; dwAceRevision
0x180001db1  mov     rcx, rsi; pAcl
0x180001db4  call    cs:__imp_AddAccessAllowedAce
0x180001dba  test    eax, eax
0x180001dbc  jz      loc_180024B4A
0x180001dc2  mov     r9, [rbp+arg_8]; pSid
0x180001dc6  mov     r8d, 0C0100000h; AccessMask
0x180001dcc  mov     edx, r12d; dwAceRevision
0x180001dcf  mov     rcx, rsi; pAcl
0x180001dd2  call    cs:__imp_AddAccessAllowedAce
0x180001dd8  test    eax, eax
0x180001dda  jz      loc_180024B4A
0x180001de0  mov     r9, [rbp+arg_18]; pSid
0x180001de4  mov     r8d, 80100000h; AccessMask
0x180001dea  mov     edx, r12d; dwAceRevision
0x180001ded  mov     rcx, rsi; pAcl
0x180001df0  call    cs:__imp_AddAccessAllowedAce
0x180001df6  test    eax, eax
0x180001df8  jz      loc_180024B4A
0x180001dfe  mov     r9, [rbp+pSid]; pSid
0x180001e02  mov     r8d, 80100000h; AccessMask
0x180001e08  mov     edx, r12d; dwAceRevision
0x180001e0b  mov     rcx, rsi; pAcl
0x180001e0e  call    cs:__imp_AddAccessAllowedAce
0x180001e14  test    eax, eax
0x180001e16  jz      loc_180024B4A
0x180001e1c  mov     r12d, 1
0x180001e22  mov     rcx, rbx; pSecurityDescriptor
0x180001e25  mov     edx, r12d; dwRevision
0x180001e28  call    cs:__imp_InitializeSecurityDescriptor
0x180001e2e  test    eax, eax
0x180001e30  jz      loc_180024B4A
0x180001e36  xor     r9d, r9d; bDaclDefaulted
0x180001e39  mov     r8, rsi; pDacl
0x180001e3c  mov     edx, r12d; bDaclPresent
0x180001e3f  mov     rcx, rbx; pSecurityDescriptor
0x180001e42  call    cs:__imp_SetSecurityDescriptorDacl
0x180001e48  test    eax, eax
0x180001e4a  jz      loc_180024B4A
0x180001e50  cmp     [rbp+hMem], 0
0x180001e55  jz      short loc_180001E61
0x180001e57  mov     rcx, [rbp+hMem]; hMem
0x180001e5b  call    cs:__imp_LocalFree
0x180001e61  mov     rcx, [rbp+arg_8]; pSid
0x180001e65  test    rcx, rcx
0x180001e68  jz      short loc_180001E70
0x180001e6a  call    cs:__imp_FreeSid
0x180001e70  mov     rcx, [rbp+arg_10]; pSid
0x180001e74  test    rcx, rcx
0x180001e77  jz      short loc_180001E7F
0x180001e79  call    cs:__imp_FreeSid
0x180001e7f  mov     rcx, [rbp+arg_18]; pSid
0x180001e83  test    rcx, rcx
0x180001e86  jz      short loc_180001E8E
0x180001e88  call    cs:__imp_FreeSid
0x180001e8e  mov     rcx, [rbp+pSid]; pSid
0x180001e92  test    rcx, rcx
0x180001e95  jz      short loc_180001E9D
0x180001e97  call    cs:__imp_FreeSid
0x180001e9d  test    edi, edi
0x180001e9f  js      loc_180024B68
0x180001ea5  mov     [r15+18h], rbx
0x180001ea9  mov     eax, edi
0x180001eab  add     rsp, 48h
0x180001eaf  pop     r15
0x180001eb1  pop     r12
0x180001eb3  pop     rdi
0x180001eb4  pop     rsi
0x180001eb5  pop     rbx
0x180001eb6  pop     rbp
0x180001eb7  retn
0x180001eb8  xor     eax, eax
0x180001eba  jmp     short loc_180001EAB
0x180024b40  mov     edi, 8007000Eh
0x180024b45  jmp     loc_180001E50
0x180024b4a  call    cs:__imp_GetLastError
0x180024b50  mov     edi, eax
0x180024b52  test    eax, eax
0x180024b54  jle     loc_180001E50
0x180024b5a  movzx   edi, ax
0x180024b5d  or      edi, 80070000h
0x180024b63  jmp     loc_180001E50
0x180024b68  test    rbx, rbx
0x180024b6b  jz      loc_180001EA5
0x180024b71  mov     rcx, rbx; Block
0x180024b74  call    cs:__imp_free
0x180024b7a  xor     ebx, ebx
0x180024b7c  jmp     loc_180001EA5
```
