# ORProcessSecurityDescriptor

- ea: `0x180030e5c`
- end: `0x180030fa4`
- name: `ORProcessSecurityDescriptor`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c768`
- `0x18002d8e8`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x180002c48`
- `0x18002f03c`
- `0x180030e5c`
- `0x18003619c`
- `0x1800361a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180030ea2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180030ea2`

## pseudocode

```c
__int64 __fastcall ORProcessSecurityDescriptor(__int64 a1, void *a2, _QWORD *a3)
{
  _QWORD *i; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // r14
  size_t SecurityDescriptorLength; // rbp
  __int64 v9; // rcx
  _DWORD *v10; // r15
  _QWORD *v11; // rax

  i = 0;
  *a3 = 0;
  v6 = ORMakeSDRelative(a2);
  if ( !v6 )
  {
    v7 = (_QWORD *)(a1 + 64);
    SecurityDescriptorLength = GetSecurityDescriptorLength(0);
    for ( i = (_QWORD *)*v7; i != v7; i = (_QWORD *)*i )
    {
      v9 = i[2];
      if ( *(_DWORD *)(v9 + 16) == (_DWORD)SecurityDescriptorLength
        && !memcmp_0((const void *)(v9 + 20), 0, SecurityDescriptorLength) )
      {
        goto LABEL_13;
      }
    }
    i = o__aligned_malloc_0(0x28u, 0x10u);
    if ( !i
      || (v10 = o__aligned_malloc_0((unsigned int)(SecurityDescriptorLength + 20), 0x10u),
          memset_0(v10, 0, (unsigned int)(SecurityDescriptorLength + 20)),
          !v10) )
    {
      v6 = 8;
      goto LABEL_14;
    }
    *(_WORD *)v10 = 27507;
    v10[3] = 0;
    v10[4] = SecurityDescriptorLength;
    memcpy_0(v10 + 5, 0, SecurityDescriptorLength);
    i[2] = v10;
    v11 = (_QWORD *)v7[1];
    if ( (_QWORD *)*v11 != v7 )
      __fastfail(3u);
    *i = v7;
    i[1] = v11;
    *v11 = i;
    v7[1] = i;
LABEL_13:
    v6 = 0;
    *a3 = i;
    i = 0;
  }
LABEL_14:
  if ( i )
    aligned_free(i);
  return v6;
}

```

## disassembly

```asm
0x180030e5c  mov     rax, rsp
0x180030e5f  push    rbx
0x180030e60  push    rbp
0x180030e61  push    rsi
0x180030e62  push    rdi
0x180030e63  push    r12
0x180030e65  push    r13
0x180030e67  push    r14
0x180030e69  push    r15
0x180030e6b  sub     rsp, 28h
0x180030e6f  mov     r13, rdx
0x180030e72  mov     r14, rcx
0x180030e75  xor     edi, edi
0x180030e77  lea     rdx, [rax+18h]
0x180030e7b  mov     rcx, r13; pAbsoluteSecurityDescriptor
0x180030e7e  mov     [rax+18h], rdi
0x180030e82  mov     r12, r8
0x180030e85  mov     [r8], rdi
0x180030e88  call    ORMakeSDRelative
0x180030e8d  mov     rsi, [rsp+68h+pSecurityDescriptor]
0x180030e95  mov     ebx, eax
0x180030e97  test    eax, eax
0x180030e99  jnz     loc_180030F71
0x180030e9f  mov     rcx, rsi; pSecurityDescriptor
0x180030ea2  call    cs:__imp_GetSecurityDescriptorLength
0x180030ea9  nop     dword ptr [rax+rax+00h]
0x180030eae  add     r14, 40h ; '@'
0x180030eb2  mov     ebp, eax
0x180030eb4  mov     rdi, [r14]
0x180030eb7  cmp     rdi, r14
0x180030eba  jz      short loc_180030EE1
0x180030ebc  mov     rcx, [rdi+10h]
0x180030ec0  cmp     [rcx+10h], ebp
0x180030ec3  jnz     short loc_180030EDC
0x180030ec5  mov     r8, rbp; Size
0x180030ec8  add     rcx, 14h; Buf1
0x180030ecc  mov     rdx, rsi; Buf2
0x180030ecf  call    memcmp_0
0x180030ed4  test    eax, eax
0x180030ed6  jz      loc_180030F69
0x180030edc  mov     rdi, [rdi]
0x180030edf  jmp     short loc_180030EB7
0x180030ee1  mov     r15d, 10h
0x180030ee7  mov     edx, r15d; Alignment
0x180030eea  lea     ecx, [r15+18h]; Size
0x180030eee  call    _o__aligned_malloc_0
0x180030ef3  mov     rdi, rax
0x180030ef6  test    rax, rax
0x180030ef9  jnz     short loc_180030F02
0x180030efb  mov     ebx, 8
0x180030f00  jmp     short loc_180030F71
0x180030f02  lea     eax, [rbp+14h]
0x180030f05  mov     rdx, r15; Alignment
0x180030f08  mov     ecx, eax; Size
0x180030f0a  mov     ebx, eax
0x180030f0c  call    _o__aligned_malloc_0
0x180030f11  mov     r8d, ebx; Size
0x180030f14  xor     edx, edx; Val
0x180030f16  mov     rcx, rax; void *
0x180030f19  mov     r15, rax
0x180030f1c  call    memset_0
0x180030f21  test    r15, r15
0x180030f24  jz      short loc_180030EFB
0x180030f26  mov     r8, rbp; Size
0x180030f29  mov     word ptr [r15], 6B73h
0x180030f2f  lea     rcx, [r15+14h]; void *
0x180030f33  mov     dword ptr [r15+0Ch], 0
0x180030f3b  mov     rdx, rsi; Src
0x180030f3e  mov     [r15+10h], ebp
0x180030f42  call    memcpy_0
0x180030f47  mov     [rdi+10h], r15
0x180030f4b  mov     rax, [r14+8]
0x180030f4f  cmp     [rax], r14
0x180030f52  jz      short loc_180030F5B
0x180030f54  mov     ecx, 3
0x180030f59  int     29h; Win8: RtlFailFast(ecx)
0x180030f5b  mov     [rdi], r14
0x180030f5e  mov     [rdi+8], rax
0x180030f62  mov     [rax], rdi
0x180030f65  mov     [r14+8], rdi
0x180030f69  xor     ebx, ebx
0x180030f6b  mov     [r12], rdi
0x180030f6f  xor     edi, edi
0x180030f71  cmp     rsi, r13
0x180030f74  jz      short loc_180030F83
0x180030f76  test    rsi, rsi
0x180030f79  jz      short loc_180030F83
0x180030f7b  mov     rcx, rsi; Block
0x180030f7e  call    _aligned_free
0x180030f83  test    rdi, rdi
0x180030f86  jz      short loc_180030F90
0x180030f88  mov     rcx, rdi; Block
0x180030f8b  call    _aligned_free
0x180030f90  mov     eax, ebx
0x180030f92  add     rsp, 28h
0x180030f96  pop     r15
0x180030f98  pop     r14
0x180030f9a  pop     r13
0x180030f9c  pop     r12
0x180030f9e  pop     rdi
0x180030f9f  pop     rsi
0x180030fa0  pop     rbp
0x180030fa1  pop     rbx
0x180030fa2  retn
```
