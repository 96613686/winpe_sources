# VstackBuffer512::appendSid(void * const)

- ea: `0x1800b5de0`
- end: `0x1800b5fb0`
- name: `?appendSid@VstackBuffer512@@QEAAAEAV1@QEAX@Z`
- size: `464`
- prototype: `struct VstackBuffer512 *(VstackBuffer512 *__hidden this, void *const)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180090204`
- `0x1800b5de0`
- `0x1800b6680`

## import_xrefs

- `ADVAPI32!GetSidSubAuthority` at `0x1800b5f5b`
- `ADVAPI32!GetSidSubAuthority` at `0x1800b5f5b`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800b5e26`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800b5e26`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1800b5e1a`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1800b5e1a`
- `ADVAPI32!IsValidSid` at `0x1800b5e06`
- `ADVAPI32!IsValidSid` at `0x1800b5e06`

## pseudocode

```c
struct VstackBuffer512 *__fastcall VstackBuffer512::appendSid(VstackBuffer512 *this, void *const a2)
{
  DWORD v4; // r12d
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v6; // r15d
  unsigned int v7; // r14d
  _WORD *v8; // rdi
  _BYTE *v9; // rdi
  _WORD *v10; // rdi
  char *v11; // rdi
  __int64 v12; // rcx
  int v13; // eax
  char *v14; // rdi
  unsigned int v15; // ebx
  PDWORD SidSubAuthority; // rax

  v4 = 0;
  if ( IsValidSid(a2) )
  {
    SidIdentifierAuthority = GetSidIdentifierAuthority(a2);
    v6 = *GetSidSubAuthorityCount(a2);
    v7 = 12 * v6 + 28;
    if ( v7 + *((_DWORD *)this + 131) > *((_DWORD *)this + 132) )
      VstackBuffer512::reallocate(this, v7);
    v8 = (_WORD *)(*(_QWORD *)this + *((unsigned int *)this + 131));
    *v8 = 11603;
    v9 = (char *)v8
       + (unsigned int)sub_180090204(
                         1,
                         (int)v8 + 2,
                         v7 + *(_DWORD *)this + *((_DWORD *)this + 131) - ((_DWORD)v8 + 2),
                         10,
                         0)
       + 2;
    *v9 = 45;
    v10 = v9 + 1;
    if ( SidIdentifierAuthority->Value[0] || SidIdentifierAuthority->Value[1] )
    {
      *v10 = 30768;
      v11 = (char *)(v10 + 1);
      v12 = 6;
      do
      {
        *(_WORD *)v11 = 12336;
        v11[2] = a0123456789abcd_0[(unsigned __int64)SidIdentifierAuthority->Value[0] >> 4];
        v13 = SidIdentifierAuthority->Value[0] & 0xF;
        SidIdentifierAuthority = (PSID_IDENTIFIER_AUTHORITY)((char *)SidIdentifierAuthority + 1);
        v11[3] = a0123456789abcd_0[v13];
        v11 += 4;
        --v12;
      }
      while ( v12 );
    }
    else
    {
      v11 = (char *)v10
          + (unsigned int)sub_180090204(
                            SidIdentifierAuthority->Value[5]
                          + (SidIdentifierAuthority->Value[4] << 8)
                          + (SidIdentifierAuthority->Value[3] << 16)
                          + (SidIdentifierAuthority->Value[2] << 24),
                            (_DWORD)v10,
                            v7 + *(_DWORD *)this + *((_DWORD *)this + 131) - (_DWORD)v10,
                            10,
                            0);
    }
    if ( v6 )
    {
      do
      {
        *v11 = 45;
        v14 = v11 + 1;
        v15 = v7 + *(_DWORD *)this + *((_DWORD *)this + 131) - (_DWORD)v14;
        SidSubAuthority = GetSidSubAuthority(a2, v4++);
        v11 = &v14[(unsigned int)sub_180090204(*SidSubAuthority, (_DWORD)v14, v15, 10, 0)];
      }
      while ( v4 < v6 );
    }
    *((_DWORD *)this + 131) = (_DWORD)v11 - *(_DWORD *)this;
  }
  return this;
}

```

## disassembly

```asm
0x1800b5de0  mov     rax, rsp
0x1800b5de3  mov     [rax+8], rbx
0x1800b5de7  mov     [rax+10h], rbp
0x1800b5deb  mov     [rax+18h], rsi
0x1800b5def  mov     [rax+20h], rdi
0x1800b5df3  push    r12
0x1800b5df5  push    r14
0x1800b5df7  push    r15
0x1800b5df9  sub     rsp, 30h
0x1800b5dfd  mov     rsi, rcx
0x1800b5e00  mov     rbp, rdx
0x1800b5e03  mov     rcx, rdx; pSid
0x1800b5e06  call    cs:IsValidSid
0x1800b5e0c  xor     r12d, r12d
0x1800b5e0f  test    eax, eax
0x1800b5e11  jz      loc_1800B5F8E
0x1800b5e17  mov     rcx, rbp; pSid
0x1800b5e1a  call    cs:GetSidIdentifierAuthority
0x1800b5e20  mov     rcx, rbp; pSid
0x1800b5e23  mov     rbx, rax
0x1800b5e26  call    cs:GetSidSubAuthorityCount
0x1800b5e2c  mov     edx, [rsi+20Ch]
0x1800b5e32  movzx   r15d, byte ptr [rax]
0x1800b5e36  lea     ecx, [r15+r15*2]
0x1800b5e3a  lea     r14d, ds:1Ch[rcx*4]
0x1800b5e42  add     edx, r14d
0x1800b5e45  cmp     edx, [rsi+210h]
0x1800b5e4b  jbe     short loc_1800B5E58
0x1800b5e4d  mov     edx, r14d; unsigned int
0x1800b5e50  mov     rcx, rsi; this
0x1800b5e53  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x1800b5e58  mov     edi, [rsi+20Ch]
0x1800b5e5e  mov     r9d, 0Ah
0x1800b5e64  add     rdi, [rsi]
0x1800b5e67  mov     [rsp+48h+var_28], r12d
0x1800b5e6c  lea     ecx, [r9-9]
0x1800b5e70  mov     word ptr [rdi], 2D53h
0x1800b5e75  add     rdi, 2
0x1800b5e79  mov     r8d, [rsi+20Ch]
0x1800b5e80  mov     rdx, rdi
0x1800b5e83  sub     r8d, edi
0x1800b5e86  add     r8d, [rsi]
0x1800b5e89  add     r8d, r14d
0x1800b5e8c  call    sub_180090204
0x1800b5e91  mov     eax, eax
0x1800b5e93  add     rdi, rax
0x1800b5e96  mov     byte ptr [rdi], 2Dh ; '-'
0x1800b5e99  inc     rdi
0x1800b5e9c  cmp     [rbx], r12b
0x1800b5e9f  jnz     short loc_1800B5EF0
0x1800b5ea1  cmp     [rbx+1], r12b
0x1800b5ea5  jnz     short loc_1800B5EF0
0x1800b5ea7  movzx   ecx, byte ptr [rbx+2]
0x1800b5eab  mov     r9d, 0Ah
0x1800b5eb1  movzx   eax, byte ptr [rbx+3]
0x1800b5eb5  mov     rdx, rdi
0x1800b5eb8  mov     r8d, [rsi+20Ch]
0x1800b5ebf  shl     eax, 10h
0x1800b5ec2  sub     r8d, edi
0x1800b5ec5  add     r8d, [rsi]
0x1800b5ec8  shl     ecx, 18h
0x1800b5ecb  add     r8d, r14d
0x1800b5ece  add     ecx, eax
0x1800b5ed0  mov     [rsp+48h+var_28], r12d
0x1800b5ed5  movzx   eax, byte ptr [rbx+4]
0x1800b5ed9  shl     eax, 8
0x1800b5edc  add     ecx, eax
0x1800b5ede  movzx   eax, byte ptr [rbx+5]
0x1800b5ee2  add     ecx, eax
0x1800b5ee4  call    sub_180090204
0x1800b5ee9  mov     eax, eax
0x1800b5eeb  add     rdi, rax
0x1800b5eee  jmp     short loc_1800B5F3D
0x1800b5ef0  mov     word ptr [rdi], 7830h
0x1800b5ef5  lea     rdx, a0123456789abcd_0; "0123456789ABCDEF"
0x1800b5efc  add     rdi, 2
0x1800b5f00  mov     ecx, 6
0x1800b5f05  mov     word ptr [rdi], 3030h
0x1800b5f0a  movzx   eax, byte ptr [rbx]
0x1800b5f0d  shr     rax, 4
0x1800b5f11  mov     al, [rax+rdx]
0x1800b5f14  mov     [rdi+2], al
0x1800b5f17  movzx   eax, byte ptr [rbx]
0x1800b5f1a  and     eax, 8000000Fh
0x1800b5f1f  jge     short loc_1800B5F28
0x1800b5f21  dec     eax
0x1800b5f23  or      eax, 0FFFFFFF0h
0x1800b5f26  inc     eax
0x1800b5f28  cdqe
0x1800b5f2a  inc     rbx
0x1800b5f2d  mov     al, [rax+rdx]
0x1800b5f30  mov     [rdi+3], al
0x1800b5f33  add     rdi, 4
0x1800b5f37  sub     rcx, 1
0x1800b5f3b  jnz     short loc_1800B5F05
0x1800b5f3d  test    r15d, r15d
0x1800b5f40  jz      short loc_1800B5F86
0x1800b5f42  mov     byte ptr [rdi], 2Dh ; '-'
0x1800b5f45  mov     edx, r12d; nSubAuthority
0x1800b5f48  mov     ebx, [rsi+20Ch]
0x1800b5f4e  inc     rdi
0x1800b5f51  sub     ebx, edi
0x1800b5f53  mov     rcx, rbp; pSid
0x1800b5f56  add     ebx, [rsi]
0x1800b5f58  add     ebx, r14d
0x1800b5f5b  call    cs:GetSidSubAuthority
0x1800b5f61  and     [rsp+48h+var_28], 0
0x1800b5f66  mov     r9d, 0Ah
0x1800b5f6c  mov     r8d, ebx
0x1800b5f6f  mov     rdx, rdi
0x1800b5f72  mov     ecx, [rax]
0x1800b5f74  call    sub_180090204
0x1800b5f79  mov     eax, eax
0x1800b5f7b  inc     r12d
0x1800b5f7e  add     rdi, rax
0x1800b5f81  cmp     r12d, r15d
0x1800b5f84  jb      short loc_1800B5F42
0x1800b5f86  sub     edi, [rsi]
0x1800b5f88  mov     [rsi+20Ch], edi
0x1800b5f8e  mov     rbx, [rsp+48h+arg_0]
0x1800b5f93  mov     rax, rsi
0x1800b5f96  mov     rsi, [rsp+48h+arg_10]
0x1800b5f9b  mov     rbp, [rsp+48h+arg_8]
0x1800b5fa0  mov     rdi, [rsp+48h+arg_18]
0x1800b5fa5  add     rsp, 30h
0x1800b5fa9  pop     r15
0x1800b5fab  pop     r14
0x1800b5fad  pop     r12
0x1800b5faf  retn
```
