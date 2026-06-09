# ORCreateSecurityDescriptorsList

- ea: `0x180030c2c`
- end: `0x180030dd7`
- name: `ORCreateSecurityDescriptorsList`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003110c`

## callees

- `0x180002b34`
- `0x18002ec6c`
- `0x180030c2c`
- `0x180030de0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030c7a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030d1b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030c7a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030d1b`

## pseudocode

```c
__int64 __fastcall ORCreateSecurityDescriptorsList(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rbx
  _QWORD *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rbp
  _QWORD *v9; // rcx
  __int64 v10; // r15
  __int64 i; // rcx
  __int64 v12; // r14
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx

  v3 = ORConvertOffsetToAbsolute(*(unsigned int *)(a2 + 44), *(_QWORD *)(a1 + 16));
  v4 = v3;
  if ( !v3
    || *(int *)v3 > 0
    || (v5 = v3 + 4, *(_WORD *)(v3 + 4) != 27507)
    || !IsValidSecurityDescriptor((PSECURITY_DESCRIPTOR)(v3 + 24)) )
  {
LABEL_20:
    v7 = 1009;
    goto LABEL_21;
  }
  v6 = o__aligned_malloc_0(0x28u, 0x10u);
  if ( !v6 )
  {
LABEL_6:
    v7 = 8;
LABEL_21:
    ORFreeSecurityCellList(a1);
    return v7;
  }
  *v6 = 0;
  v8 = a1 + 64;
  v6[1] = 0;
  v6[3] = 0;
  v6[4] = 0;
  v6[2] = v5;
  v9 = *(_QWORD **)(a1 + 72);
  if ( *v9 != a1 + 64 )
LABEL_19:
    __fastfail(3u);
  *v6 = v8;
  v10 = v4;
  v6[1] = v9;
  *v9 = v6;
  *(_QWORD *)(a1 + 72) = v6;
  for ( i = *(unsigned int *)(v5 + 4); ; i = *(unsigned int *)(v16 + 8) )
  {
    v15 = ORConvertOffsetToAbsolute(i, *(_QWORD *)(a1 + 16));
    v16 = v15;
    if ( v15 == v4 )
      break;
    if ( !v15 )
      goto LABEL_20;
    if ( *(int *)v15 > 0 )
      goto LABEL_20;
    v12 = v15 + 4;
    if ( *(_WORD *)(v15 + 4) != 27507
      || !IsValidSecurityDescriptor((PSECURITY_DESCRIPTOR)(v15 + 24))
      || ORConvertOffsetToAbsolute(*(unsigned int *)(v16 + 12), *(_QWORD *)(a1 + 16)) != v10 )
    {
      goto LABEL_20;
    }
    v13 = o__aligned_malloc_0(0x28u, 0x10u);
    if ( !v13 )
      goto LABEL_6;
    *v13 = 0;
    v13[1] = 0;
    v13[3] = 0;
    v13[4] = 0;
    v13[2] = v12;
    v14 = *(_QWORD **)(a1 + 72);
    if ( *v14 != v8 )
      goto LABEL_19;
    *v13 = v8;
    v10 = v16;
    v13[1] = v14;
    *v14 = v13;
    *(_QWORD *)(a1 + 72) = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x180030c2c  push    rbx
0x180030c2e  push    rbp
0x180030c2f  push    rsi
0x180030c30  push    rdi
0x180030c31  push    r13
0x180030c33  push    r14
0x180030c35  push    r15
0x180030c37  sub     rsp, 20h
0x180030c3b  mov     rax, rdx
0x180030c3e  mov     rsi, rcx
0x180030c41  mov     rdx, [rcx+10h]
0x180030c45  mov     ecx, [rax+2Ch]
0x180030c48  call    ORConvertOffsetToAbsolute
0x180030c4d  mov     rdi, rax
0x180030c50  test    rax, rax
0x180030c53  jz      loc_180030DB8
0x180030c59  cmp     dword ptr [rax], 0
0x180030c5c  jg      loc_180030DB8
0x180030c62  lea     rbx, [rax+4]
0x180030c66  mov     r13d, 6B73h
0x180030c6c  cmp     [rbx], r13w
0x180030c70  jnz     loc_180030DB8
0x180030c76  lea     rcx, [rbx+14h]; pSecurityDescriptor
0x180030c7a  call    cs:__imp_IsValidSecurityDescriptor
0x180030c81  nop     dword ptr [rax+rax+00h]
0x180030c86  test    eax, eax
0x180030c88  jz      loc_180030DB8
0x180030c8e  mov     edx, 10h; Alignment
0x180030c93  lea     ecx, [rdx+18h]; Size
0x180030c96  call    _o__aligned_malloc_0
0x180030c9b  test    rax, rax
0x180030c9e  jnz     short loc_180030CAA
0x180030ca0  mov     ebx, 8
0x180030ca5  jmp     loc_180030DBD
0x180030caa  mov     qword ptr [rax], 0
0x180030cb1  lea     rbp, [rsi+40h]
0x180030cb5  mov     qword ptr [rax+8], 0
0x180030cbd  mov     qword ptr [rax+18h], 0
0x180030cc5  mov     qword ptr [rax+20h], 0
0x180030ccd  mov     [rax+10h], rbx
0x180030cd1  mov     rcx, [rbp+8]
0x180030cd5  cmp     [rcx], rbp
0x180030cd8  jnz     loc_180030DB1
0x180030cde  mov     [rax], rbp
0x180030ce1  mov     r15, rdi
0x180030ce4  mov     [rax+8], rcx
0x180030ce8  mov     [rcx], rax
0x180030ceb  mov     [rbp+8], rax
0x180030cef  mov     ecx, [rbx+4]
0x180030cf2  jmp     loc_180030D98
0x180030cf7  test    rbx, rbx
0x180030cfa  jz      loc_180030DB8
0x180030d00  cmp     dword ptr [rbx], 0
0x180030d03  jg      loc_180030DB8
0x180030d09  lea     r14, [rbx+4]
0x180030d0d  cmp     [r14], r13w
0x180030d11  jnz     loc_180030DB8
0x180030d17  lea     rcx, [rbx+18h]; pSecurityDescriptor
0x180030d1b  call    cs:__imp_IsValidSecurityDescriptor
0x180030d22  nop     dword ptr [rax+rax+00h]
0x180030d27  test    eax, eax
0x180030d29  jz      loc_180030DB8
0x180030d2f  mov     rdx, [rsi+10h]
0x180030d33  mov     ecx, [r14+8]
0x180030d37  call    ORConvertOffsetToAbsolute
0x180030d3c  cmp     rax, r15
0x180030d3f  jnz     short loc_180030DB8
0x180030d41  mov     edx, 10h; Alignment
0x180030d46  lea     ecx, [rdx+18h]; Size
0x180030d49  call    _o__aligned_malloc_0
0x180030d4e  test    rax, rax
0x180030d51  jz      loc_180030CA0
0x180030d57  mov     qword ptr [rax], 0
0x180030d5e  mov     qword ptr [rax+8], 0
0x180030d66  mov     qword ptr [rax+18h], 0
0x180030d6e  mov     qword ptr [rax+20h], 0
0x180030d76  mov     [rax+10h], r14
0x180030d7a  mov     rcx, [rbp+8]
0x180030d7e  cmp     [rcx], rbp
0x180030d81  jnz     short loc_180030DB1
0x180030d83  mov     [rax], rbp
0x180030d86  mov     r15, rbx
0x180030d89  mov     [rax+8], rcx
0x180030d8d  mov     [rcx], rax
0x180030d90  mov     [rbp+8], rax
0x180030d94  mov     ecx, [r14+4]
0x180030d98  mov     rdx, [rsi+10h]
0x180030d9c  call    ORConvertOffsetToAbsolute
0x180030da1  mov     rbx, rax
0x180030da4  cmp     rax, rdi
0x180030da7  jnz     loc_180030CF7
0x180030dad  xor     ebx, ebx
0x180030daf  jmp     short loc_180030DC5
0x180030db1  mov     ecx, 3
0x180030db6  int     29h; Win8: RtlFailFast(ecx)
0x180030db8  mov     ebx, 3F1h
0x180030dbd  mov     rcx, rsi
0x180030dc0  call    ORFreeSecurityCellList
0x180030dc5  mov     eax, ebx
0x180030dc7  add     rsp, 20h
0x180030dcb  pop     r15
0x180030dcd  pop     r14
0x180030dcf  pop     r13
0x180030dd1  pop     rdi
0x180030dd2  pop     rsi
0x180030dd3  pop     rbp
0x180030dd4  pop     rbx
0x180030dd5  retn
```
