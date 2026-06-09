# UnDecorator::getTemplateArgumentList(void)

- ea: `0x18002bafc`
- end: `0x18002bd61`
- name: `?getTemplateArgumentList@UnDecorator@@AEAA?AVDName@@XZ`
- size: `613`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180029938`
- `0x18002bd64`

## callees

- `0x180024564`
- `0x1800249b4`
- `0x180024bf8`
- `0x180024c70`
- `0x180024d28`
- `0x1800297b0`
- `0x18002bafc`
- `0x18002c07c`
- `0x18002c524`

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
0x18002bafc  mov     [rsp-28h+arg_8], rbx
0x18002bb01  mov     [rsp-28h+arg_10], rsi
0x18002bb06  mov     [rsp-28h+arg_18], rdi
0x18002bb0b  push    rbp
0x18002bb0c  push    r12
0x18002bb0e  push    r13
0x18002bb10  push    r14
0x18002bb12  push    r15
0x18002bb14  mov     rbp, rsp
0x18002bb17  sub     rsp, 80h
0x18002bb1e  xor     r14d, r14d
0x18002bb21  mov     [rbp+var_28], rcx
0x18002bb25  mov     r9b, 1
0x18002bb28  mov     [rbp+var_30], r14
0x18002bb2c  mov     [rbp+var_20], r14d
0x18002bb30  mov     rsi, rdx
0x18002bb33  mov     [rcx+115h], r9b
0x18002bb3a  mov     rbx, rcx
0x18002bb3d  mov     rdi, [rbx+100h]
0x18002bb44  mov     r13b, r9b
0x18002bb47  cmp     [rdi], r14b
0x18002bb4a  jz      loc_18002BD0E
0x18002bb50  cmp     byte ptr [rdi], 40h ; '@'
0x18002bb53  jz      loc_18002BD0E
0x18002bb59  movsx   r8d, byte ptr [rdi]
0x18002bb5d  mov     r9b, r14b
0x18002bb60  add     r8d, 0FFFFFFD0h
0x18002bb64  mov     [rbp+arg_0], r14b
0x18002bb68  mov     qword ptr [rbp+var_50+8], rbx
0x18002bb6c  mov     r12b, r14b
0x18002bb6f  mov     qword ptr [rbp+var_50], r14
0x18002bb73  mov     [rbp+var_40], r14d
0x18002bb77  cmp     r8d, 9
0x18002bb7b  ja      short loc_18002BBAF
0x18002bb7d  lfence
0x18002bb80  mov     rcx, [rbx+0D0h]
0x18002bb87  lea     rax, [rdi+1]
0x18002bb8b  lea     rdx, [rbp+var_18]
0x18002bb8f  mov     [rbx+100h], rax
0x18002bb96  call    ??AReplicator@@QEBA?AVDName@@H@Z; Replicator::operator[](int)
0x18002bb9b  mov     r14, [rax]
0x18002bb9e  mov     r15d, [rax+10h]
0x18002bba2  mov     qword ptr [rbp+var_50], r14
0x18002bba6  mov     [rbp+var_40], r15d
0x18002bbaa  jmp     loc_18002BCA3
0x18002bbaf  cmp     byte ptr [rdi], 24h ; '$'
0x18002bbb2  mov     rdx, rdi
0x18002bbb5  jnz     short loc_18002BBDA
0x18002bbb7  cmp     byte ptr [rdi+1], 24h ; '$'
0x18002bbbb  jnz     short loc_18002BBDA
0x18002bbbd  movsx   ecx, byte ptr [rdi+2]
0x18002bbc1  sub     ecx, 24h ; '$'
0x18002bbc4  jz      short loc_18002BC25
0x18002bbc6  sub     ecx, 31h ; '1'
0x18002bbc9  jz      short loc_18002BC08
0x18002bbcb  sub     ecx, 1
0x18002bbce  jz      short loc_18002BC15
0x18002bbd0  sub     ecx, 1
0x18002bbd3  jz      short loc_18002BC05
0x18002bbd5  cmp     ecx, 3
0x18002bbd8  jz      short loc_18002BC15
0x18002bbda  cmp     byte ptr [rdx], 24h ; '$'
0x18002bbdd  jnz     short loc_18002BC31
0x18002bbdf  mov     rax, [rbx+100h]
0x18002bbe6  cmp     byte ptr [rax+1], 24h ; '$'
0x18002bbea  jz      short loc_18002BC31
0x18002bbec  lea     rax, [rdx+1]
0x18002bbf0  mov     rcx, rbx
0x18002bbf3  lea     rdx, [rbp+var_18]
0x18002bbf7  mov     [rbx+100h], rax
0x18002bbfe  call    ?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateNonTypeArgument(void)
0x18002bc03  jmp     short loc_18002BC3D
0x18002bc05  mov     r12b, 1
0x18002bc08  lea     rdx, [rdi+3]
0x18002bc0c  mov     [rbx+100h], rdx
0x18002bc13  jmp     short loc_18002BBDA
0x18002bc15  lea     rax, [rdi+3]
0x18002bc19  mov     [rbx+100h], rax
0x18002bc20  jmp     loc_18002BD04
0x18002bc25  cmp     byte ptr [rdi+3], 56h ; 'V'
0x18002bc29  jnz     short loc_18002BBDA
0x18002bc2b  lea     rax, [rdi+4]
0x18002bc2f  jmp     short loc_18002BC19
0x18002bc31  lea     rdx, [rbp+var_18]
0x18002bc35  mov     rcx, rbx
0x18002bc38  call    ?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateTypeArgument(void)
0x18002bc3d  mov     r15d, [rax+10h]
0x18002bc41  mov     r14, [rax]
0x18002bc44  mov     rax, [rbx+100h]
0x18002bc4b  sub     rax, rdi
0x18002bc4e  mov     [rbp+var_40], r15d
0x18002bc52  mov     qword ptr [rbp+var_50], r14
0x18002bc56  cmp     rax, 1
0x18002bc5a  jle     short loc_18002BCA3
0x18002bc5c  mov     rdi, [rbx+0D0h]
0x18002bc63  cmp     dword ptr [rdi], 9
0x18002bc66  jz      short loc_18002BCA3
0x18002bc68  test    r14, r14
0x18002bc6b  jz      loc_18002BCF7
0x18002bc71  mov     rcx, [rdi+58h]
0x18002bc75  mov     edx, 18h; unsigned __int64
0x18002bc7a  add     rcx, 0D8h; this
0x18002bc81  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002bc86  test    rax, rax
0x18002bc89  jz      short loc_18002BCA3
0x18002bc8b  mov     [rax+8], rbx
0x18002bc8f  mov     [rax], r14
0x18002bc92  mov     [rax+10h], r15d
0x18002bc96  movsxd  rdx, dword ptr [rdi]
0x18002bc99  lea     ecx, [rdx+1]
0x18002bc9c  mov     [rdi], ecx
0x18002bc9e  mov     [rdi+rdx*8+10h], rax
0x18002bca3  test    r14, r14
0x18002bca6  jz      short loc_18002BCF7
0x18002bca8  xor     r14d, r14d
0x18002bcab  test    r13b, r13b
0x18002bcae  jnz     short loc_18002BCBB
0x18002bcb0  mov     dl, 2Ch ; ','
0x18002bcb2  lea     rcx, [rbp+var_30]
0x18002bcb6  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002bcbb  lea     rdx, [rbp+var_50]
0x18002bcbf  lea     rcx, [rbp+var_30]
0x18002bcc3  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002bcc8  test    r12b, r12b
0x18002bccb  jz      short loc_18002BD00
0x18002bccd  lea     rax, asc_18006A98C; "..."
0x18002bcd4  mov     dword ptr [rbp+var_60+8], 3
0x18002bcdb  mov     qword ptr [rbp+var_60], rax
0x18002bcdf  lea     rdx, [rbp+var_50]
0x18002bce3  movaps  xmm0, [rbp+var_60]
0x18002bce7  lea     rcx, [rbp+var_30]
0x18002bceb  movdqa  [rbp+var_50], xmm0
0x18002bcf0  call    ??YDName@@QEAAAEAV0@AEBUStringLiteral@@@Z; DName::operator+=(StringLiteral const &)
0x18002bcf5  jmp     short loc_18002BD00
0x18002bcf7  cmp     r15b, 1
0x18002bcfb  jg      short loc_18002BD4E
0x18002bcfd  xor     r14d, r14d
0x18002bd00  mov     r9b, [rbp+arg_0]
0x18002bd04  cmp     byte ptr [rbp+var_20], r14b
0x18002bd08  jz      loc_18002BB3D
0x18002bd0e  mov     rax, [rbp+var_28]
0x18002bd12  mov     [rbx+115h], r14b
0x18002bd19  mov     [rsi+8], rax
0x18002bd1d  mov     rax, [rbp+var_30]
0x18002bd21  mov     [rsi], rax
0x18002bd24  mov     eax, [rbp+var_20]
0x18002bd27  mov     [rsi+10h], eax
0x18002bd2a  lea     r11, [rsp+80h+var_s0]
0x18002bd32  mov     rax, rsi
0x18002bd35  mov     rbx, [r11+38h]
0x18002bd39  mov     rsi, [r11+40h]
0x18002bd3d  mov     rdi, [r11+48h]
0x18002bd41  mov     rsp, r11
0x18002bd44  pop     r15
0x18002bd46  pop     r14
0x18002bd48  pop     r13
0x18002bd4a  pop     r12
0x18002bd4c  pop     rbp
0x18002bd4d  retn
0x18002bd4e  mov     r8d, 2
0x18002bd54  mov     rdx, rbx
0x18002bd57  mov     rcx, rsi
0x18002bd5a  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002bd5f  jmp     short loc_18002BD2A
```
