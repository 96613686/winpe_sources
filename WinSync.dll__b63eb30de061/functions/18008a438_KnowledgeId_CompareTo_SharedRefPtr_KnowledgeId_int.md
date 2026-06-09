# KnowledgeId::CompareTo(SharedRefPtr<KnowledgeId> &,int *)

- ea: `0x18008a438`
- end: `0x18008a750`
- name: `?CompareTo@KnowledgeId@@QEAAHAEAV?$SharedRefPtr@VKnowledgeId@@@@PEAH@Z`
- size: `792`
- prototype: `__int64 __fastcall(__int64, __int64 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180082ec4`

## callees

- `0x18001a038`
- `0x18008a438`
- `0x18008a840`

## string_xrefs

- `0x18008a476`: `KnowledgeId::CompareTo`

## pseudocode

```c
__int64 __fastcall KnowledgeId::CompareTo(__int64 a1, __int64 *a2, int *a3)
{
  PVOID *v5; // rsi
  __int64 v6; // r13
  int v7; // edx
  unsigned int v8; // ebx
  __int64 v10; // r11
  __int64 *v11; // r15
  unsigned int v12; // r12d
  __int16 v13; // r14
  unsigned int v14; // r10d
  unsigned int v15; // ebp
  __int64 v16; // r9
  __int64 v17; // r9
  __int16 v18; // ax
  unsigned __int16 v19; // r14
  __int16 v20; // cx
  __int16 v21; // r9
  __int16 v22; // cx
  __int16 v23; // r9

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_82d43572357d3e40b8f22864f5a78709_Traceguids,
      "KnowledgeId::CompareTo");
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = *a2;
  v7 = 0;
  if ( *(_DWORD *)(a1 + 24) == *(_DWORD *)(*a2 + 24) )
  {
    v8 = 1;
LABEL_7:
    *a3 = v7;
    goto LABEL_8;
  }
  v10 = *(_QWORD *)(a1 + 16);
  v11 = (__int64 *)(v6 + 16);
  v8 = 0;
  if ( !v10 && !*v11 )
    goto LABEL_8;
  v12 = *(unsigned __int16 *)(a1 + 28);
  v13 = 0;
  v14 = 0;
  if ( *(_WORD *)(a1 + 28) )
  {
    while ( 1 )
    {
      v15 = v14;
      if ( v14 >= *(unsigned __int16 *)(v6 + 28) )
        break;
      v16 = *v11;
      if ( *(_DWORD *)(v10 + 8LL * v14) != *(_DWORD *)(*v11 + 8LL * v14)
        || *(_WORD *)(v10 + 8LL * v14 + 4) != *(_WORD *)(v16 + 8LL * v14 + 4)
        || *(_WORD *)(v10 + 8LL * v14 + 6) != *(_WORD *)(v16 + 8LL * v14 + 6) )
      {
        goto LABEL_25;
      }
      ++v14;
      ++v13;
      v15 = v14;
      if ( v14 >= v12 )
        goto LABEL_23;
    }
  }
  else
  {
    v15 = 0;
LABEL_23:
    if ( v14 == v12 )
    {
      v21 = *(_WORD *)(*v11 + 8LL * v15 + 6);
      if ( *(_WORD *)(*v11 + 8LL * v15 + 4) )
      {
        if ( v21 )
          goto LABEL_8;
        v8 = 1;
        goto LABEL_55;
      }
      v8 = 1;
      if ( !v21 )
        goto LABEL_56;
LABEL_33:
      v7 = 1;
      goto LABEL_56;
    }
  }
  if ( v15 == *(unsigned __int16 *)(v6 + 28) )
  {
    v20 = *(_WORD *)(v10 + 8LL * v14 + 6);
    if ( !*(_WORD *)(v10 + 8LL * v14 + 4) )
    {
      v8 = 1;
      if ( !v20 )
        goto LABEL_56;
      goto LABEL_55;
    }
    if ( v20 )
      goto LABEL_8;
    v8 = 1;
    goto LABEL_33;
  }
LABEL_25:
  v17 = *v11;
  if ( *(_DWORD *)(v10 + 8LL * v14) == *(_DWORD *)(*v11 + 8LL * v15) )
  {
    v19 = *(_WORD *)(v17 + 8LL * v15 + 4);
    if ( *(_WORD *)(v10 + 8LL * v14 + 4) == v19 )
    {
      v7 = *(_WORD *)(v17 + 8LL * v15 + 6) < *(_WORD *)(v10 + 8LL * v14 + 6) ? -1 : 1;
    }
    else
    {
      if ( *(_WORD *)(v10 + 8LL * v14 + 6) != *(_WORD *)(v17 + 8LL * v15 + 6) )
        goto LABEL_8;
      v7 = v19 < *(_WORD *)(v10 + 8LL * v14 + 4) ? 1 : -1;
    }
    v8 = 1;
    goto LABEL_56;
  }
  if ( v13 )
  {
    v18 = *(_WORD *)(v10 + 8LL * v14 + 4);
    v8 = 1;
    if ( v18 || *(_WORD *)(v10 + 8LL * v14 + 6) )
    {
      if ( *(_WORD *)(v17 + 8LL * v15 + 4) || *(_WORD *)(v17 + 8LL * v15 + 6) )
        goto LABEL_38;
      if ( !*(_WORD *)(v10 + 8LL * v14 + 6) )
        goto LABEL_33;
      if ( v18 )
        goto LABEL_38;
    }
    else
    {
      if ( !*(_WORD *)(v17 + 8LL * v15 + 4) && !*(_WORD *)(v17 + 8LL * v15 + 6) )
      {
LABEL_56:
        while ( v14 < v12 )
        {
          v22 = *(_WORD *)(v10 + 8LL * v14 + 6);
          if ( *(_WORD *)(v10 + 8LL * v14 + 4) )
          {
            if ( v22 )
              goto LABEL_38;
            if ( v7 < 0 )
              v8 = 0;
          }
          else if ( v22 && v7 > 0 )
          {
            goto LABEL_38;
          }
          if ( !v8 )
            goto LABEL_8;
          ++v14;
        }
        while ( v15 < *(unsigned __int16 *)(v6 + 28) )
        {
          v23 = *(_WORD *)(*v11 + 8LL * v15 + 6);
          if ( *(_WORD *)(*v11 + 8LL * v15 + 4) )
          {
            if ( v23 )
              goto LABEL_38;
            if ( v7 > 0 )
              v8 = 0;
          }
          else if ( v23 && v7 < 0 )
          {
            goto LABEL_38;
          }
          if ( !v8 )
            goto LABEL_8;
          ++v15;
        }
        goto LABEL_7;
      }
      if ( *(_WORD *)(v17 + 8LL * v15 + 6) )
      {
        if ( !*(_WORD *)(v17 + 8LL * v15 + 4) )
          goto LABEL_33;
LABEL_38:
        v8 = 0;
        goto LABEL_8;
      }
    }
LABEL_55:
    v7 = -1;
    goto LABEL_56;
  }
LABEL_8:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 5u )
    WPP_SF_sdd(v5[2]);
  return v8;
}

```

## disassembly

```asm
0x18008a438  mov     [rsp+arg_10], r8
0x18008a43d  push    rbx
0x18008a43e  push    rbp
0x18008a43f  push    rsi
0x18008a440  push    rdi
0x18008a441  push    r12
0x18008a443  push    r13
0x18008a445  push    r14
0x18008a447  push    r15
0x18008a449  sub     rsp, 38h
0x18008a44d  mov     rbx, rdx
0x18008a450  mov     rdi, rcx
0x18008a453  mov     rsi, cs:WPP_GLOBAL_Control
0x18008a45a  lea     rax, WPP_GLOBAL_Control
0x18008a461  cmp     rsi, rax
0x18008a464  jz      short loc_18008A495
0x18008a466  test    byte ptr [rsi+1Ch], 40h
0x18008a46a  jz      short loc_18008A495
0x18008a46c  cmp     byte ptr [rsi+19h], 5
0x18008a470  jb      short loc_18008A495
0x18008a472  mov     rcx, [rsi+10h]
0x18008a476  lea     r9, aKnowledgeidCom; "KnowledgeId::CompareTo"
0x18008a47d  mov     edx, 0Eh
0x18008a482  lea     r8, WPP_82d43572357d3e40b8f22864f5a78709_Traceguids
0x18008a489  call    WPP_SF_s
0x18008a48e  mov     rsi, cs:WPP_GLOBAL_Control
0x18008a495  mov     r13, [rbx]
0x18008a498  xor     ecx, ecx
0x18008a49a  mov     edx, ecx
0x18008a49c  mov     eax, [r13+18h]
0x18008a4a0  cmp     [rdi+18h], eax
0x18008a4a3  jnz     short loc_18008A4EE
0x18008a4a5  lea     ebx, [rcx+1]
0x18008a4a8  mov     rax, [rsp+78h+arg_10]
0x18008a4b0  mov     [rax], edx
0x18008a4b2  lea     rax, WPP_GLOBAL_Control
0x18008a4b9  cmp     rsi, rax
0x18008a4bc  jz      short loc_18008A4DB
0x18008a4be  test    byte ptr [rsi+1Ch], 40h
0x18008a4c2  jz      short loc_18008A4DB
0x18008a4c4  cmp     byte ptr [rsi+19h], 5
0x18008a4c8  jb      short loc_18008A4DB
0x18008a4ca  mov     rcx, [rsi+10h]
0x18008a4ce  mov     [rsp+78h+var_50], edx
0x18008a4d2  mov     [rsp+78h+var_58], ebx
0x18008a4d6  call    WPP_SF_sdd
0x18008a4db  mov     eax, ebx
0x18008a4dd  add     rsp, 38h
0x18008a4e1  pop     r15
0x18008a4e3  pop     r14
0x18008a4e5  pop     r13
0x18008a4e7  pop     r12
0x18008a4e9  pop     rdi
0x18008a4ea  pop     rsi
0x18008a4eb  pop     rbp
0x18008a4ec  pop     rbx
0x18008a4ed  retn
0x18008a4ee  mov     r11, [rdi+10h]
0x18008a4f2  lea     r15, [r13+10h]
0x18008a4f6  mov     ebx, ecx
0x18008a4f8  test    r11, r11
0x18008a4fb  jnz     short loc_18008A502
0x18008a4fd  cmp     [r15], rcx
0x18008a500  jz      short loc_18008A4B2
0x18008a502  movzx   r12d, word ptr [rdi+1Ch]
0x18008a507  mov     r14d, ecx
0x18008a50a  mov     r10d, ecx
0x18008a50d  mov     r8d, 1
0x18008a513  test    r12d, r12d
0x18008a516  jz      short loc_18008A562
0x18008a518  movzx   edi, word ptr [r13+1Ch]
0x18008a51d  mov     ebp, r10d
0x18008a520  cmp     r10d, edi
0x18008a523  jnb     short loc_18008A56D
0x18008a525  mov     r9, [r15]
0x18008a528  mov     ecx, r10d
0x18008a52b  mov     eax, [r9+rcx*8]
0x18008a52f  cmp     [r11+rcx*8], eax
0x18008a533  jnz     short loc_18008A57A
0x18008a535  movzx   eax, word ptr [r9+rcx*8+4]
0x18008a53b  cmp     [r11+rcx*8+4], ax
0x18008a541  jnz     short loc_18008A57A
0x18008a543  movzx   eax, word ptr [r9+rcx*8+6]
0x18008a549  cmp     [r11+rcx*8+6], ax
0x18008a54f  jnz     short loc_18008A57A
0x18008a551  add     r10d, r8d
0x18008a554  add     r14w, r8w
0x18008a558  mov     ebp, r10d
0x18008a55b  cmp     r10d, r12d
0x18008a55e  jb      short loc_18008A51D
0x18008a560  jmp     short loc_18008A564
0x18008a562  mov     ebp, ecx
0x18008a564  cmp     r10d, r12d
0x18008a567  jz      loc_18008A68B
0x18008a56d  movzx   eax, word ptr [r13+1Ch]
0x18008a572  cmp     ebp, eax
0x18008a574  jz      loc_18008A65C
0x18008a57a  mov     r9, [r15]
0x18008a57d  mov     ecx, ebp
0x18008a57f  mov     edi, r10d
0x18008a582  mov     eax, [r9+rcx*8]
0x18008a586  cmp     [r11+rdi*8], eax
0x18008a58a  jz      short loc_18008A608
0x18008a58c  test    r14w, r14w
0x18008a590  jz      loc_18008A4B2
0x18008a596  movzx   eax, word ptr [r11+rdi*8+4]
0x18008a59c  xor     r14d, r14d
0x18008a59f  mov     ebx, r8d
0x18008a5a2  test    ax, ax
0x18008a5a5  jnz     short loc_18008A5DF
0x18008a5a7  cmp     [r11+rdi*8+6], r14w
0x18008a5ad  jnz     short loc_18008A5DF
0x18008a5af  cmp     [r9+rcx*8+4], r14w
0x18008a5b5  jnz     short loc_18008A5C3
0x18008a5b7  cmp     [r9+rcx*8+6], r14w
0x18008a5bd  jz      loc_18008A6BF
0x18008a5c3  cmp     [r9+rcx*8+6], r14w
0x18008a5c9  jz      loc_18008A6BC
0x18008a5cf  cmp     [r9+rcx*8+4], r14w
0x18008a5d5  jnz     short loc_18008A600
0x18008a5d7  mov     edx, r8d
0x18008a5da  jmp     loc_18008A6BF
0x18008a5df  cmp     [r9+rcx*8+4], r14w
0x18008a5e5  jnz     short loc_18008A600
0x18008a5e7  cmp     [r9+rcx*8+6], r14w
0x18008a5ed  jnz     short loc_18008A600
0x18008a5ef  cmp     [r11+rdi*8+6], r14w
0x18008a5f5  jz      short loc_18008A5D7
0x18008a5f7  test    ax, ax
0x18008a5fa  jz      loc_18008A6BC
0x18008a600  mov     ebx, r14d
0x18008a603  jmp     loc_18008A4B2
0x18008a608  movzx   r14d, word ptr [r9+rcx*8+4]
0x18008a60e  cmp     [r11+rdi*8+4], r14w
0x18008a614  jz      short loc_18008A646
0x18008a616  movzx   eax, word ptr [r9+rcx*8+6]
0x18008a61c  cmp     [r11+rdi*8+6], ax
0x18008a622  jnz     short loc_18008A63F
0x18008a624  cmp     r14w, [r11+rdi*8+4]
0x18008a62a  sbb     eax, eax
0x18008a62c  or      edx, 0FFFFFFFFh
0x18008a62f  and     eax, 2
0x18008a632  add     edx, eax
0x18008a634  mov     ebx, r8d
0x18008a637  xor     r14d, r14d
0x18008a63a  jmp     loc_18008A6BF
0x18008a63f  xor     eax, eax
0x18008a641  jmp     loc_18008A4B2
0x18008a646  movzx   eax, word ptr [r11+rdi*8+6]
0x18008a64c  cmp     [r9+rcx*8+6], ax
0x18008a652  sbb     edx, edx
0x18008a654  and     edx, 0FFFFFFFEh
0x18008a657  add     edx, r8d
0x18008a65a  jmp     short loc_18008A634
0x18008a65c  mov     eax, r10d
0x18008a65f  xor     r14d, r14d
0x18008a662  movzx   ecx, word ptr [r11+rax*8+6]
0x18008a668  cmp     [r11+rax*8+4], r14w
0x18008a66e  jnz     short loc_18008A67A
0x18008a670  mov     ebx, r8d
0x18008a673  test    cx, cx
0x18008a676  jz      short loc_18008A6BF
0x18008a678  jmp     short loc_18008A6BC
0x18008a67a  test    cx, cx
0x18008a67d  jnz     loc_18008A4B2
0x18008a683  mov     ebx, r8d
0x18008a686  jmp     loc_18008A5D7
0x18008a68b  mov     rax, [r15]
0x18008a68e  xor     r14d, r14d
0x18008a691  mov     ecx, ebp
0x18008a693  movzx   r9d, word ptr [rax+rcx*8+6]
0x18008a699  cmp     [rax+rcx*8+4], r14w
0x18008a69f  jnz     short loc_18008A6AF
0x18008a6a1  mov     ebx, r8d
0x18008a6a4  test    r9w, r9w
0x18008a6a8  jz      short loc_18008A6BF
0x18008a6aa  jmp     loc_18008A5D7
0x18008a6af  test    r9w, r9w
0x18008a6b3  jnz     loc_18008A4B2
0x18008a6b9  mov     ebx, r8d
0x18008a6bc  or      edx, 0FFFFFFFFh
0x18008a6bf  cmp     r10d, r12d
0x18008a6c2  jnb     short loc_18008A701
0x18008a6c4  mov     eax, r10d
0x18008a6c7  movzx   ecx, word ptr [r11+rax*8+6]
0x18008a6cd  cmp     [r11+rax*8+4], r14w
0x18008a6d3  jz      short loc_18008A6E7
0x18008a6d5  test    cx, cx
0x18008a6d8  jnz     loc_18008A600
0x18008a6de  test    edx, edx
0x18008a6e0  jns     short loc_18008A6F4
0x18008a6e2  mov     ebx, r14d
0x18008a6e5  jmp     short loc_18008A6F4
0x18008a6e7  test    cx, cx
0x18008a6ea  jz      short loc_18008A6F4
0x18008a6ec  test    edx, edx
0x18008a6ee  jg      loc_18008A600
0x18008a6f4  test    ebx, ebx
0x18008a6f6  jz      loc_18008A4B2
0x18008a6fc  add     r10d, r8d
0x18008a6ff  jmp     short loc_18008A6BF
0x18008a701  movzx   r10d, word ptr [r13+1Ch]
0x18008a706  cmp     ebp, r10d
0x18008a709  jnb     loc_18008A4A8
0x18008a70f  mov     rax, [r15]
0x18008a712  mov     ecx, ebp
0x18008a714  movzx   r9d, word ptr [rax+rcx*8+6]
0x18008a71a  cmp     [rax+rcx*8+4], r14w
0x18008a720  jz      short loc_18008A735
0x18008a722  test    r9w, r9w
0x18008a726  jnz     loc_18008A600
0x18008a72c  test    edx, edx
0x18008a72e  jle     short loc_18008A743
0x18008a730  mov     ebx, r14d
0x18008a733  jmp     short loc_18008A743
0x18008a735  test    r9w, r9w
0x18008a739  jz      short loc_18008A743
0x18008a73b  test    edx, edx
0x18008a73d  js      loc_18008A600
0x18008a743  test    ebx, ebx
0x18008a745  jz      loc_18008A4B2
0x18008a74b  add     ebp, r8d
0x18008a74e  jmp     short loc_18008A706
```
