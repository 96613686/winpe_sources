# SrpSetAttributeOnToken

- ea: `0x140006464`
- end: `0x1400065be`
- name: `SrpSetAttributeOnToken`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006798`
- `0x1400067c0`

## callees

- `0x140006464`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006585`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000659b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006585`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000659b`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x140006572`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x140006572`
- `ntoskrnl!ExAllocatePool2` at `0x1400064a8`
- `ntoskrnl!ExAllocatePool2` at `0x140006541`
- `ntoskrnl!ExAllocatePool2` at `0x1400064a8`
- `ntoskrnl!ExAllocatePool2` at `0x140006541`

## pseudocode

```c
__int64 __fastcall SrpSetAttributeOnToken(__int64 a1, __int64 a2, __int16 a3, __int64 a4, char a5)
{
  __int64 Pool2; // rax
  void *v10; // rdi
  unsigned int v11; // ebx
  void *v12; // rsi
  __int64 v13; // rax
  int v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 4;
  if ( a1 && a2 )
  {
    Pool2 = ExAllocatePool2(66, 40, 1097884741);
    v10 = (void *)Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    *(_QWORD *)(Pool2 + 8) = *(_QWORD *)(a2 + 8);
    *(_WORD *)Pool2 = *(_WORD *)a2;
    *(_WORD *)(Pool2 + 2) = *(_WORD *)(a2 + 2);
    if ( a3 )
    {
      if ( a3 != 3 )
        goto LABEL_12;
      *(_DWORD *)(Pool2 + 20) = 65;
      *(_QWORD *)(Pool2 + 32) = &a5;
      *(_DWORD *)(Pool2 + 16) = 2;
    }
    else
    {
      if ( !a4 )
      {
        v12 = 0;
        v11 = -1073741811;
LABEL_15:
        ExFreePoolWithTag(v10, 0);
        if ( v12 )
          ExFreePoolWithTag(v12, 0);
        return v11;
      }
      *(_DWORD *)(Pool2 + 20) = 67;
      *(_DWORD *)(Pool2 + 16) = 3;
      *(_QWORD *)(Pool2 + 32) = a4;
    }
    *(_DWORD *)(Pool2 + 24) = 1;
LABEL_12:
    v13 = ExAllocatePool2(66, 16, 1097884741);
    v12 = (void *)v13;
    if ( v13 )
    {
      *(_DWORD *)v13 = 1;
      *(_DWORD *)(v13 + 4) = 1;
      *(_QWORD *)(v13 + 8) = v10;
      v11 = SeSetSecurityAttributesToken(a1, 0, &v15, v13);
    }
    else
    {
      v11 = -1073741801;
    }
    goto LABEL_15;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140006464  push    rbx
0x140006466  push    rbp
0x140006467  push    rsi
0x140006468  push    rdi
0x140006469  push    r14
0x14000646b  push    r15
0x14000646d  sub     rsp, 28h
0x140006471  xor     r15d, r15d
0x140006474  mov     [rsp+58h+arg_0], 4
0x14000647c  mov     rsi, r9
0x14000647f  movzx   ebp, r8w
0x140006483  mov     rbx, rdx
0x140006486  mov     r14, rcx
0x140006489  test    rcx, rcx
0x14000648c  jz      loc_1400065AB
0x140006492  test    rdx, rdx
0x140006495  jz      loc_1400065AB
0x14000649b  lea     edx, [r15+28h]
0x14000649f  mov     r8d, 41706445h
0x1400064a5  lea     ecx, [rdx+1Ah]
0x1400064a8  call    cs:__imp_ExAllocatePool2
0x1400064af  nop     dword ptr [rax+rax+00h]
0x1400064b4  mov     rdi, rax
0x1400064b7  test    rax, rax
0x1400064ba  jnz     short loc_1400064C6
0x1400064bc  mov     ebx, 0C0000017h
0x1400064c1  jmp     loc_1400065A7
0x1400064c6  mov     rax, [rbx+8]
0x1400064ca  mov     [rdi+8], rax
0x1400064ce  movzx   eax, word ptr [rbx]
0x1400064d1  mov     [rdi], ax
0x1400064d4  movzx   eax, word ptr [rbx+2]
0x1400064d8  mov     ebx, 1
0x1400064dd  mov     [rdi+2], ax
0x1400064e1  test    bp, bp
0x1400064e4  jnz     short loc_14000650C
0x1400064e6  test    rsi, rsi
0x1400064e9  jnz     short loc_1400064F8
0x1400064eb  mov     rsi, r15
0x1400064ee  mov     ebx, 0C000000Dh
0x1400064f3  jmp     loc_140006580
0x1400064f8  mov     dword ptr [rdi+14h], 43h ; 'C'
0x1400064ff  mov     dword ptr [rdi+10h], 3
0x140006506  mov     [rdi+20h], rsi
0x14000650a  jmp     short loc_140006530
0x14000650c  mov     eax, 3
0x140006511  cmp     bp, ax
0x140006514  jnz     short loc_140006533
0x140006516  lea     rax, [rsp+58h+arg_20]
0x14000651e  mov     dword ptr [rdi+14h], 41h ; 'A'
0x140006525  mov     [rdi+20h], rax
0x140006529  mov     dword ptr [rdi+10h], 2
0x140006530  mov     [rdi+18h], ebx
0x140006533  mov     edx, 10h
0x140006538  mov     r8d, 41706445h
0x14000653e  lea     ecx, [rdx+32h]
0x140006541  call    cs:__imp_ExAllocatePool2
0x140006548  nop     dword ptr [rax+rax+00h]
0x14000654d  mov     rsi, rax
0x140006550  test    rax, rax
0x140006553  jnz     short loc_14000655C
0x140006555  mov     ebx, 0C0000017h
0x14000655a  jmp     short loc_140006580
0x14000655c  mov     r9, rax
0x14000655f  mov     [rax], ebx
0x140006561  lea     r8, [rsp+58h+arg_0]
0x140006566  mov     [rax+4], ebx
0x140006569  xor     edx, edx
0x14000656b  mov     [rax+8], rdi
0x14000656f  mov     rcx, r14
0x140006572  call    cs:__imp_SeSetSecurityAttributesToken
0x140006579  nop     dword ptr [rax+rax+00h]
0x14000657e  mov     ebx, eax
0x140006580  xor     edx, edx; Tag
0x140006582  mov     rcx, rdi; P
0x140006585  call    cs:__imp_ExFreePoolWithTag
0x14000658c  nop     dword ptr [rax+rax+00h]
0x140006591  test    rsi, rsi
0x140006594  jz      short loc_1400065A7
0x140006596  xor     edx, edx; Tag
0x140006598  mov     rcx, rsi; P
0x14000659b  call    cs:__imp_ExFreePoolWithTag
0x1400065a2  nop     dword ptr [rax+rax+00h]
0x1400065a7  mov     eax, ebx
0x1400065a9  jmp     short loc_1400065B0
0x1400065ab  mov     eax, 0C000000Dh
0x1400065b0  add     rsp, 28h
0x1400065b4  pop     r15
0x1400065b6  pop     r14
0x1400065b8  pop     rdi
0x1400065b9  pop     rsi
0x1400065ba  pop     rbp
0x1400065bb  pop     rbx
0x1400065bc  retn
```
