# UnDecorator::getTemplateArgumentList(void)

- ea: `0x18002c25c`
- end: `0x18002c4c1`
- name: `?getTemplateArgumentList@UnDecorator@@AEAA?AVDName@@XZ`
- size: `613`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18002a098`
- `0x18002c4c4`

## callees

- `0x180024cc4`
- `0x180025114`
- `0x180025358`
- `0x1800253d0`
- `0x180025488`
- `0x180029f10`
- `0x18002c25c`
- `0x18002c7dc`
- `0x18002cc84`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateArgumentList(__int64 a1, __int64 a2)
{
  char v2; // r9
  char *v5; // rdi
  char v6; // r13
  unsigned int v7; // r8d
  char v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r14
  int v15; // r15d
  _BYTE *v16; // rdx
  __int64 TemplateTypeArgument; // rax
  char *v18; // rax
  __int64 v19; // rax
  int *v20; // rdi
  _QWORD *MemoryWithBuffer; // rax
  __int64 v22; // rax
  __int128 v24; // [rsp+20h] [rbp-60h]
  __int128 v25; // [rsp+30h] [rbp-50h] BYREF
  int v26; // [rsp+40h] [rbp-40h]
  __int64 v27; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h]
  int v29; // [rsp+60h] [rbp-20h]
  _BYTE v30[24]; // [rsp+68h] [rbp-18h] BYREF

  v28 = a1;
  v2 = 1;
  v27 = 0;
  v29 = 0;
  *(_BYTE *)(a1 + 277) = 1;
  while ( 1 )
  {
    v5 = *(char **)(a1 + 256);
    v6 = v2;
    if ( !*v5 || *v5 == 64 )
    {
LABEL_36:
      v22 = v28;
      *(_BYTE *)(a1 + 277) = 0;
      *(_QWORD *)(a2 + 8) = v22;
      *(_QWORD *)a2 = v27;
      *(_DWORD *)(a2 + 16) = v29;
      return a2;
    }
    v2 = 0;
    v7 = *v5 - 48;
    *((_QWORD *)&v25 + 1) = a1;
    v8 = 0;
    *(_QWORD *)&v25 = 0;
    v26 = 0;
    if ( v7 <= 9 )
    {
      _mm_lfence();
      v9 = *(_QWORD *)(a1 + 208);
      *(_QWORD *)(a1 + 256) = v5 + 1;
      v10 = Replicator::operator[](v9, v30);
      v14 = *(_QWORD *)v10;
      v15 = *(_DWORD *)(v10 + 16);
      *(_QWORD *)&v25 = *(_QWORD *)v10;
      v26 = v15;
      goto LABEL_28;
    }
    v16 = v5;
    if ( *v5 != 36 || v5[1] != 36 )
      goto LABEL_13;
    if ( v5[2] != 36 )
      break;
    if ( v5[3] != 86 )
      goto LABEL_13;
    v18 = v5 + 4;
LABEL_19:
    *(_QWORD *)(a1 + 256) = v18;
LABEL_35:
    if ( (_BYTE)v29 )
      goto LABEL_36;
  }
  if ( v5[2] == 85 )
    goto LABEL_17;
  if ( v5[2] == 86 )
  {
LABEL_18:
    v18 = v5 + 3;
    goto LABEL_19;
  }
  if ( v5[2] != 87 )
  {
    if ( v5[2] != 90 )
      goto LABEL_13;
    goto LABEL_18;
  }
  v8 = 1;
LABEL_17:
  v16 = v5 + 3;
  *(_QWORD *)(a1 + 256) = v5 + 3;
LABEL_13:
  if ( *v16 != 36 || *(_BYTE *)(*(_QWORD *)(a1 + 256) + 1LL) == 36 )
  {
    TemplateTypeArgument = (__int64)UnDecorator::getTemplateTypeArgument(a1, (DName *)v30);
  }
  else
  {
    *(_QWORD *)(a1 + 256) = v16 + 1;
    TemplateTypeArgument = UnDecorator::getTemplateNonTypeArgument(a1, (__int64)v30);
  }
  v15 = *(_DWORD *)(TemplateTypeArgument + 16);
  v14 = *(_QWORD *)TemplateTypeArgument;
  v19 = *(_QWORD *)(a1 + 256) - (_QWORD)v5;
  v26 = v15;
  *(_QWORD *)&v25 = v14;
  if ( v19 <= 1 || (v20 = *(int **)(a1 + 208), *v20 == 9) )
  {
LABEL_28:
    if ( !v14 )
      goto LABEL_33;
    if ( !v6 )
    {
      LOBYTE(v11) = 44;
      DName::operator+=(&v27, v11);
    }
    DName::operator+=(&v27, &v25, v12, v13);
    if ( v8 )
    {
      DWORD2(v24) = 3;
      *(_QWORD *)&v24 = "...";
      v25 = v24;
      DName::operator+=(&v27, &v25);
    }
LABEL_34:
    v2 = 0;
    goto LABEL_35;
  }
  if ( v14 )
  {
    MemoryWithBuffer = _HeapManager::getMemoryWithBuffer((_HeapManager *)(*((_QWORD *)v20 + 11) + 216LL), 0x18u);
    if ( MemoryWithBuffer )
    {
      MemoryWithBuffer[1] = a1;
      *MemoryWithBuffer = v14;
      *((_DWORD *)MemoryWithBuffer + 4) = v15;
      v11 = *v20;
      *v20 = v11 + 1;
      *(_QWORD *)&v20[2 * v11 + 4] = MemoryWithBuffer;
    }
    goto LABEL_28;
  }
LABEL_33:
  if ( (char)v15 <= 1 )
    goto LABEL_34;
  DName::DName(a2, a1, 2);
  return a2;
}

```

## disassembly

```asm
0x18002c25c  mov     [rsp-28h+arg_8], rbx
0x18002c261  mov     [rsp-28h+arg_10], rsi
0x18002c266  mov     [rsp-28h+arg_18], rdi
0x18002c26b  push    rbp
0x18002c26c  push    r12
0x18002c26e  push    r13
0x18002c270  push    r14
0x18002c272  push    r15
0x18002c274  mov     rbp, rsp
0x18002c277  sub     rsp, 80h
0x18002c27e  xor     r14d, r14d
0x18002c281  mov     [rbp+var_28], rcx
0x18002c285  mov     r9b, 1
0x18002c288  mov     [rbp+var_30], r14
0x18002c28c  mov     [rbp+var_20], r14d
0x18002c290  mov     rsi, rdx
0x18002c293  mov     [rcx+115h], r9b
0x18002c29a  mov     rbx, rcx
0x18002c29d  mov     rdi, [rbx+100h]
0x18002c2a4  mov     r13b, r9b
0x18002c2a7  cmp     [rdi], r14b
0x18002c2aa  jz      loc_18002C46E
0x18002c2b0  cmp     byte ptr [rdi], 40h ; '@'
0x18002c2b3  jz      loc_18002C46E
0x18002c2b9  movsx   r8d, byte ptr [rdi]
0x18002c2bd  mov     r9b, r14b
0x18002c2c0  add     r8d, 0FFFFFFD0h
0x18002c2c4  mov     [rbp+arg_0], r14b
0x18002c2c8  mov     qword ptr [rbp+var_50+8], rbx
0x18002c2cc  mov     r12b, r14b
0x18002c2cf  mov     qword ptr [rbp+var_50], r14
0x18002c2d3  mov     [rbp+var_40], r14d
0x18002c2d7  cmp     r8d, 9
0x18002c2db  ja      short loc_18002C30F
0x18002c2dd  lfence
0x18002c2e0  mov     rcx, [rbx+0D0h]
0x18002c2e7  lea     rax, [rdi+1]
0x18002c2eb  lea     rdx, [rbp+var_18]
0x18002c2ef  mov     [rbx+100h], rax
0x18002c2f6  call    ??AReplicator@@QEBA?AVDName@@H@Z; Replicator::operator[](int)
0x18002c2fb  mov     r14, [rax]
0x18002c2fe  mov     r15d, [rax+10h]
0x18002c302  mov     qword ptr [rbp+var_50], r14
0x18002c306  mov     [rbp+var_40], r15d
0x18002c30a  jmp     loc_18002C403
0x18002c30f  cmp     byte ptr [rdi], 24h ; '$'
0x18002c312  mov     rdx, rdi
0x18002c315  jnz     short loc_18002C33A
0x18002c317  cmp     byte ptr [rdi+1], 24h ; '$'
0x18002c31b  jnz     short loc_18002C33A
0x18002c31d  movsx   ecx, byte ptr [rdi+2]
0x18002c321  sub     ecx, 24h ; '$'
0x18002c324  jz      short loc_18002C385
0x18002c326  sub     ecx, 31h ; '1'
0x18002c329  jz      short loc_18002C368
0x18002c32b  sub     ecx, 1
0x18002c32e  jz      short loc_18002C375
0x18002c330  sub     ecx, 1
0x18002c333  jz      short loc_18002C365
0x18002c335  cmp     ecx, 3
0x18002c338  jz      short loc_18002C375
0x18002c33a  cmp     byte ptr [rdx], 24h ; '$'
0x18002c33d  jnz     short loc_18002C391
0x18002c33f  mov     rax, [rbx+100h]
0x18002c346  cmp     byte ptr [rax+1], 24h ; '$'
0x18002c34a  jz      short loc_18002C391
0x18002c34c  lea     rax, [rdx+1]
0x18002c350  mov     rcx, rbx
0x18002c353  lea     rdx, [rbp+var_18]
0x18002c357  mov     [rbx+100h], rax
0x18002c35e  call    ?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateNonTypeArgument(void)
0x18002c363  jmp     short loc_18002C39D
0x18002c365  mov     r12b, 1
0x18002c368  lea     rdx, [rdi+3]
0x18002c36c  mov     [rbx+100h], rdx
0x18002c373  jmp     short loc_18002C33A
0x18002c375  lea     rax, [rdi+3]
0x18002c379  mov     [rbx+100h], rax
0x18002c380  jmp     loc_18002C464
0x18002c385  cmp     byte ptr [rdi+3], 56h ; 'V'
0x18002c389  jnz     short loc_18002C33A
0x18002c38b  lea     rax, [rdi+4]
0x18002c38f  jmp     short loc_18002C379
0x18002c391  lea     rdx, [rbp+var_18]
0x18002c395  mov     rcx, rbx
0x18002c398  call    ?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateTypeArgument(void)
0x18002c39d  mov     r15d, [rax+10h]
0x18002c3a1  mov     r14, [rax]
0x18002c3a4  mov     rax, [rbx+100h]
0x18002c3ab  sub     rax, rdi
0x18002c3ae  mov     [rbp+var_40], r15d
0x18002c3b2  mov     qword ptr [rbp+var_50], r14
0x18002c3b6  cmp     rax, 1
0x18002c3ba  jle     short loc_18002C403
0x18002c3bc  mov     rdi, [rbx+0D0h]
0x18002c3c3  cmp     dword ptr [rdi], 9
0x18002c3c6  jz      short loc_18002C403
0x18002c3c8  test    r14, r14
0x18002c3cb  jz      loc_18002C457
0x18002c3d1  mov     rcx, [rdi+58h]
0x18002c3d5  mov     edx, 18h; unsigned __int64
0x18002c3da  add     rcx, 0D8h; this
0x18002c3e1  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002c3e6  test    rax, rax
0x18002c3e9  jz      short loc_18002C403
0x18002c3eb  mov     [rax+8], rbx
0x18002c3ef  mov     [rax], r14
0x18002c3f2  mov     [rax+10h], r15d
0x18002c3f6  movsxd  rdx, dword ptr [rdi]
0x18002c3f9  lea     ecx, [rdx+1]
0x18002c3fc  mov     [rdi], ecx
0x18002c3fe  mov     [rdi+rdx*8+10h], rax
0x18002c403  test    r14, r14
0x18002c406  jz      short loc_18002C457
0x18002c408  xor     r14d, r14d
0x18002c40b  test    r13b, r13b
0x18002c40e  jnz     short loc_18002C41B
0x18002c410  mov     dl, 2Ch ; ','
0x18002c412  lea     rcx, [rbp+var_30]
0x18002c416  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002c41b  lea     rdx, [rbp+var_50]
0x18002c41f  lea     rcx, [rbp+var_30]
0x18002c423  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c428  test    r12b, r12b
0x18002c42b  jz      short loc_18002C460
0x18002c42d  lea     rax, asc_18006E06C; "..."
0x18002c434  mov     dword ptr [rbp+var_60+8], 3
0x18002c43b  mov     qword ptr [rbp+var_60], rax
0x18002c43f  lea     rdx, [rbp+var_50]
0x18002c443  movaps  xmm0, [rbp+var_60]
0x18002c447  lea     rcx, [rbp+var_30]
0x18002c44b  movdqa  [rbp+var_50], xmm0
0x18002c450  call    ??YDName@@QEAAAEAV0@AEBUStringLiteral@@@Z; DName::operator+=(StringLiteral const &)
0x18002c455  jmp     short loc_18002C460
0x18002c457  cmp     r15b, 1
0x18002c45b  jg      short loc_18002C4AE
0x18002c45d  xor     r14d, r14d
0x18002c460  mov     r9b, [rbp+arg_0]
0x18002c464  cmp     byte ptr [rbp+var_20], r14b
0x18002c468  jz      loc_18002C29D
0x18002c46e  mov     rax, [rbp+var_28]
0x18002c472  mov     [rbx+115h], r14b
0x18002c479  mov     [rsi+8], rax
0x18002c47d  mov     rax, [rbp+var_30]
0x18002c481  mov     [rsi], rax
0x18002c484  mov     eax, [rbp+var_20]
0x18002c487  mov     [rsi+10h], eax
0x18002c48a  lea     r11, [rsp+80h+var_s0]
0x18002c492  mov     rax, rsi
0x18002c495  mov     rbx, [r11+38h]
0x18002c499  mov     rsi, [r11+40h]
0x18002c49d  mov     rdi, [r11+48h]
0x18002c4a1  mov     rsp, r11
0x18002c4a4  pop     r15
0x18002c4a6  pop     r14
0x18002c4a8  pop     r13
0x18002c4aa  pop     r12
0x18002c4ac  pop     rbp
0x18002c4ad  retn
0x18002c4ae  mov     r8d, 2
0x18002c4b4  mov     rdx, rbx
0x18002c4b7  mov     rcx, rsi
0x18002c4ba  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002c4bf  jmp     short loc_18002C48A
```
