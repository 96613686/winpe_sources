# renameEditSql

- ea: `0x18007dd08`
- end: `0x18007e024`
- name: `renameEditSql`
- size: `796`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x180065620`
- `0x18007d6a0`
- `0x18007e570`

## callees

- `0x180005810`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000eb10`
- `0x18000f720`
- `0x1800256c4`
- `0x180048d20`
- `0x180067b40`
- `0x18007dd08`
- `0x18008f510`
- `0x180099814`
- `0x180099820`

## pseudocode

```c
__int64 __fastcall renameEditSql(__int64 a1, __int64 *a2, const void *a3, const void *a4, int a5)
{
  const void *v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  const void *v10; // rsi
  __int64 v12; // r13
  char *v13; // rbx
  void *v14; // rbp
  void *v15; // r12
  __int64 v16; // rax
  unsigned int v17; // r15d
  _QWORD *v18; // rdx
  __int64 v19; // rdi
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  unsigned __int8 *v24; // rcx
  unsigned int v25; // ebp
  const void *v26; // rdx
  _DWORD *v27; // r14
  __int64 *v28; // rdx
  unsigned int v29; // eax
  int v30; // r12d
  int v31; // [rsp+30h] [rbp-78h]
  int v32; // [rsp+34h] [rbp-74h]
  unsigned int Size; // [rsp+38h] [rbp-70h]
  void *v34; // [rsp+40h] [rbp-68h]
  void *v35; // [rsp+48h] [rbp-60h]
  void *v36; // [rsp+50h] [rbp-58h]
  __int64 v37; // [rsp+58h] [rbp-50h]

  v6 = a4;
  Size = sqlite3Strlen30(a4);
  v32 = sqlite3Strlen30(v7);
  v37 = sqlite3_context_db_handle(v8);
  if ( v6 )
  {
    v9 = sqlite3MPrintf(v37, "\"%w\" ", v6);
    v10 = (const void *)v9;
    if ( !v9 )
      return 7;
    v12 = (int)(sqlite3Strlen30(v9) - 1);
    v13 = (char *)sqlite3DbMallocZero(v37, v32 + v12 * *((int *)a2 + 2) + 1);
    if ( v13 )
    {
      v14 = 0;
      v15 = 0;
LABEL_8:
      v17 = 0;
      v36 = v15;
      v35 = v14;
      memcpy_0(v13, a3, v32);
      v18 = a2;
      v19 = *a2;
      if ( *a2 )
      {
        v20 = v32;
        v31 = v32;
        do
        {
          v21 = *(_QWORD *)(v19 + 24);
          if ( v21 )
          {
            do
            {
              if ( *(_QWORD *)(v21 + 8) > *(_QWORD *)(v19 + 8) )
                v19 = v21;
              v21 = *(_QWORD *)(v21 + 24);
            }
            while ( v21 );
            v35 = v14;
            v36 = v15;
          }
          v22 = *v18;
          if ( *v18 == v19 )
          {
            v23 = v18;
          }
          else
          {
            do
            {
              v23 = (_QWORD *)(v22 + 24);
              v22 = *(_QWORD *)(v22 + 24);
            }
            while ( v22 != v19 );
          }
          *v23 = *(_QWORD *)(v19 + 24);
          if ( v6 )
          {
            v24 = *(unsigned __int8 **)(v19 + 8);
            if ( a5 || (*((_BYTE *)&qword_18009E630 + *v24) & 0x46) == 0 )
            {
              v27 = (_DWORD *)(v19 + 16);
              v26 = v10;
              v25 = v12;
              v34 = (void *)v10;
              if ( v24[*(unsigned int *)(v19 + 16)] == 34 )
                v25 = v12 + 1;
            }
            else
            {
              v25 = Size;
              v26 = v6;
              v34 = (void *)v6;
              v27 = (_DWORD *)(v19 + 16);
            }
          }
          else
          {
            v27 = (_DWORD *)(v19 + 16);
            memcpy_0(v14, *(const void **)(v19 + 8), *(unsigned int *)(v19 + 16));
            *((_BYTE *)v14 + *(unsigned int *)(v19 + 16)) = 0;
            sqlite3Dequote(v14);
            v28 = (__int64 *)" ";
            if ( *(_BYTE *)(*(unsigned int *)(v19 + 16) + *(_QWORD *)(v19 + 8)) != 39 )
              v28 = qword_18009EEF0;
            sqlite3_snprintf((unsigned int)(2 * v32), v15, "%Q%s", v14, v28);
            v34 = v15;
            v29 = sqlite3Strlen30(v15);
            v20 = v31;
            v25 = v29;
          }
          v30 = *(_DWORD *)(v19 + 8) - (_DWORD)a3;
          if ( *v27 != v25 )
          {
            memmove_0(&v13[v30 + v25], &v13[v30 + *v27], (unsigned int)(v20 - v30 - *v27));
            v26 = v34;
            v31 += v25 - *v27;
            v13[v31] = 0;
          }
          memcpy_0(&v13[v30], v26, v25);
          sqlite3DbFree(v37, v19);
          v18 = a2;
          v14 = v35;
          v15 = v36;
          v6 = a4;
          v19 = *a2;
          v20 = v31;
        }
        while ( *a2 );
        v17 = 0;
      }
      sqlite3_result_text(a1, v13, -1, -1);
      sqlite3DbFree(v37, v13);
      goto LABEL_34;
    }
  }
  else
  {
    v10 = 0;
    v16 = sqlite3DbMallocZero(v37, 6LL * v32 + 3);
    v13 = (char *)v16;
    if ( v16 )
    {
      LODWORD(v12) = 0;
      v14 = (void *)(v16 + 2LL * v32 + 1);
      v15 = (void *)(v16 + 4LL * v32 + 2);
      goto LABEL_8;
    }
  }
  v17 = 7;
LABEL_34:
  sqlite3_free(v10);
  return v17;
}

```

## disassembly

```asm
0x18007dd08  mov     rax, rsp
0x18007dd0b  mov     [rax+20h], r9
0x18007dd0f  mov     [rax+18h], r8
0x18007dd13  mov     [rax+10h], rdx
0x18007dd17  mov     [rax+8], rcx
0x18007dd1b  push    rbx
0x18007dd1c  push    rbp
0x18007dd1d  push    rsi
0x18007dd1e  push    rdi
0x18007dd1f  push    r12
0x18007dd21  push    r13
0x18007dd23  push    r14
0x18007dd25  push    r15
0x18007dd27  sub     rsp, 68h
0x18007dd2b  mov     r15, rdx
0x18007dd2e  mov     r14, r9
0x18007dd31  mov     rdx, rcx
0x18007dd34  mov     rcx, r9
0x18007dd37  call    sqlite3Strlen30
0x18007dd3c  mov     rcx, r8
0x18007dd3f  mov     dword ptr [rsp+0A8h+Size], eax
0x18007dd43  call    sqlite3Strlen30
0x18007dd48  mov     rcx, rdx
0x18007dd4b  mov     [rsp+0A8h+var_74], eax
0x18007dd4f  movsxd  rdi, eax
0x18007dd52  call    sqlite3_context_db_handle
0x18007dd57  mov     [rsp+0A8h+var_50], rax
0x18007dd5c  mov     rbx, rax
0x18007dd5f  mov     rcx, rax
0x18007dd62  test    r14, r14
0x18007dd65  jz      short loc_18007DDBC
0x18007dd67  mov     r8, r14
0x18007dd6a  lea     rdx, aW; "\"%w\" "
0x18007dd71  call    sqlite3MPrintf
0x18007dd76  mov     rsi, rax
0x18007dd79  test    rax, rax
0x18007dd7c  jnz     short loc_18007DD86
0x18007dd7e  lea     eax, [rsi+7]
0x18007dd81  jmp     loc_18007E013
0x18007dd86  mov     rcx, rax
0x18007dd89  call    sqlite3Strlen30
0x18007dd8e  movsxd  rdx, dword ptr [r15+8]
0x18007dd92  dec     eax
0x18007dd94  movsxd  r13, eax
0x18007dd97  mov     rcx, rbx
0x18007dd9a  imul    rdx, r13
0x18007dd9e  inc     rdx
0x18007dda1  add     rdx, rdi
0x18007dda4  call    sqlite3DbMallocZero
0x18007dda9  mov     rbx, rax
0x18007ddac  test    rax, rax
0x18007ddaf  jz      loc_18007E002
0x18007ddb5  xor     ebp, ebp
0x18007ddb7  xor     r12d, r12d
0x18007ddba  jmp     short loc_18007DDF4
0x18007ddbc  lea     rdx, [rdi+rdi*2]
0x18007ddc0  xor     esi, esi
0x18007ddc2  lea     rdx, ds:3[rdx*2]
0x18007ddca  call    sqlite3DbMallocZero
0x18007ddcf  mov     rbx, rax
0x18007ddd2  test    rax, rax
0x18007ddd5  jz      loc_18007E002
0x18007dddb  lea     rbp, ds:1[rdi*2]
0x18007dde3  xor     r13d, r13d
0x18007dde6  add     rbp, rax
0x18007dde9  lea     r12, ds:2[rdi*4]
0x18007ddf1  add     r12, rax
0x18007ddf4  mov     rdx, [rsp+0A8h+Src]; Src
0x18007ddfc  xor     r15d, r15d
0x18007ddff  mov     r8, rdi; Size
0x18007de02  mov     dword ptr [rsp+0A8h+Size+4], r15d
0x18007de07  mov     rcx, rbx; void *
0x18007de0a  mov     [rsp+0A8h+var_58], r12
0x18007de0f  mov     [rsp+0A8h+var_60], rbp
0x18007de14  call    memcpy_0
0x18007de19  mov     rdx, [rsp+0A8h+arg_8]
0x18007de21  mov     rdi, [rdx]
0x18007de24  test    rdi, rdi
0x18007de27  jz      loc_18007DFDC
0x18007de2d  mov     r8d, [rsp+0A8h+var_74]
0x18007de32  mov     r15, [rsp+0A8h+var_50]
0x18007de37  mov     [rsp+0A8h+var_78], r8d
0x18007de3c  mov     rcx, [rdi+18h]
0x18007de40  test    rcx, rcx
0x18007de43  jz      short loc_18007DE64
0x18007de45  mov     rax, [rdi+8]
0x18007de49  cmp     [rcx+8], rax
0x18007de4d  cmova   rdi, rcx
0x18007de51  mov     rcx, [rcx+18h]
0x18007de55  test    rcx, rcx
0x18007de58  jnz     short loc_18007DE45
0x18007de5a  mov     [rsp+0A8h+var_60], rbp
0x18007de5f  mov     [rsp+0A8h+var_58], r12
0x18007de64  mov     rax, [rdx]
0x18007de67  cmp     rax, rdi
0x18007de6a  jz      short loc_18007DE7A
0x18007de6c  lea     rcx, [rax+18h]
0x18007de70  mov     rax, [rcx]
0x18007de73  cmp     rax, rdi
0x18007de76  jnz     short loc_18007DE6C
0x18007de78  jmp     short loc_18007DE7D
0x18007de7a  mov     rcx, rdx
0x18007de7d  mov     rax, [rdi+18h]
0x18007de81  mov     [rcx], rax
0x18007de84  test    r14, r14
0x18007de87  jz      short loc_18007DED8
0x18007de89  cmp     [rsp+0A8h+arg_20], 0
0x18007de91  mov     rcx, [rdi+8]
0x18007de95  jnz     short loc_18007DEBC
0x18007de97  movzx   eax, byte ptr [rcx]
0x18007de9a  lea     rdx, qword_18009E630
0x18007dea1  test    byte ptr [rax+rdx], 46h
0x18007dea5  jz      short loc_18007DEBC
0x18007dea7  mov     ebp, dword ptr [rsp+0A8h+Size]
0x18007deab  mov     rdx, r14
0x18007deae  mov     [rsp+0A8h+var_68], rdx
0x18007deb3  lea     r14, [rdi+10h]
0x18007deb7  jmp     loc_18007DF4C
0x18007debc  lea     r14, [rdi+10h]
0x18007dec0  mov     rdx, rsi
0x18007dec3  mov     eax, [r14]
0x18007dec6  mov     ebp, r13d
0x18007dec9  mov     [rsp+0A8h+var_68], rdx
0x18007dece  cmp     byte ptr [rax+rcx], 22h ; '"'
0x18007ded2  jnz     short loc_18007DF4C
0x18007ded4  inc     ebp
0x18007ded6  jmp     short loc_18007DF4C
0x18007ded8  mov     rdx, [rdi+8]; Src
0x18007dedc  lea     r14, [rdi+10h]
0x18007dee0  mov     r8d, [r14]; Size
0x18007dee3  mov     rcx, rbp; void *
0x18007dee6  call    memcpy_0
0x18007deeb  mov     eax, [r14]
0x18007deee  mov     rcx, rbp
0x18007def1  mov     byte ptr [rax+rbp], 0
0x18007def5  call    sqlite3Dequote
0x18007defa  mov     rax, [rdi+8]
0x18007defe  lea     r8, qword_18009EEF0
0x18007df05  mov     ecx, [r14]
0x18007df08  lea     rdx, asc_1800A2BB4; " "
0x18007df0f  mov     r9, rbp
0x18007df12  cmp     byte ptr [rcx+rax], 27h ; '''
0x18007df16  mov     eax, [rsp+0A8h+var_74]
0x18007df1a  cmovnz  rdx, r8
0x18007df1e  lea     r8, aQS; "%Q%s"
0x18007df25  mov     [rsp+0A8h+var_88], rdx
0x18007df2a  mov     rdx, r12
0x18007df2d  lea     ecx, [rax+rax]
0x18007df30  call    sqlite3_snprintf
0x18007df35  mov     rdx, r12
0x18007df38  mov     rcx, r12
0x18007df3b  mov     [rsp+0A8h+var_68], rdx
0x18007df40  call    sqlite3Strlen30
0x18007df45  mov     r8d, [rsp+0A8h+var_78]
0x18007df4a  mov     ebp, eax
0x18007df4c  mov     r12d, [rdi+8]
0x18007df50  sub     r12d, dword ptr [rsp+0A8h+Src]
0x18007df58  mov     eax, [r14]
0x18007df5b  cmp     eax, ebp
0x18007df5d  jz      short loc_18007DF93
0x18007df5f  sub     r8d, r12d
0x18007df62  lea     edx, [r12+rax]
0x18007df66  lea     ecx, [r12+rbp]
0x18007df6a  sub     r8d, eax; Size
0x18007df6d  add     rdx, rbx; Src
0x18007df70  add     rcx, rbx; void *
0x18007df73  call    memmove_0
0x18007df78  mov     ecx, [rsp+0A8h+var_78]
0x18007df7c  mov     eax, ebp
0x18007df7e  sub     eax, [r14]
0x18007df81  mov     rdx, [rsp+0A8h+var_68]; Src
0x18007df86  add     ecx, eax
0x18007df88  movsxd  rax, ecx
0x18007df8b  mov     [rsp+0A8h+var_78], ecx
0x18007df8f  mov     byte ptr [rax+rbx], 0
0x18007df93  movsxd  rcx, r12d
0x18007df96  add     rcx, rbx; void *
0x18007df99  mov     r8d, ebp; Size
0x18007df9c  call    memcpy_0
0x18007dfa1  mov     rdx, rdi
0x18007dfa4  mov     rcx, r15
0x18007dfa7  call    sqlite3DbFree
0x18007dfac  mov     rdx, [rsp+0A8h+arg_8]
0x18007dfb4  mov     rbp, [rsp+0A8h+var_60]
0x18007dfb9  mov     r12, [rsp+0A8h+var_58]
0x18007dfbe  mov     r14, [rsp+0A8h+arg_18]
0x18007dfc6  mov     rdi, [rdx]
0x18007dfc9  mov     r8d, [rsp+0A8h+var_78]
0x18007dfce  test    rdi, rdi
0x18007dfd1  jnz     loc_18007DE3C
0x18007dfd7  mov     r15d, dword ptr [rsp+0A8h+Size+4]
0x18007dfdc  mov     rcx, [rsp+0A8h+arg_0]
0x18007dfe4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007dfe8  mov     r9, r8
0x18007dfeb  mov     rdx, rbx
0x18007dfee  call    sqlite3_result_text
0x18007dff3  mov     rcx, [rsp+0A8h+var_50]
0x18007dff8  mov     rdx, rbx
0x18007dffb  call    sqlite3DbFree
0x18007e000  jmp     short loc_18007E008
0x18007e002  mov     r15d, 7
0x18007e008  mov     rcx, rsi
0x18007e00b  call    sqlite3_free
0x18007e010  mov     eax, r15d
0x18007e013  add     rsp, 68h
0x18007e017  pop     r15
0x18007e019  pop     r14
0x18007e01b  pop     r13
0x18007e01d  pop     r12
0x18007e01f  pop     rdi
0x18007e020  pop     rsi
0x18007e021  pop     rbp
0x18007e022  pop     rbx
0x18007e023  retn
```
