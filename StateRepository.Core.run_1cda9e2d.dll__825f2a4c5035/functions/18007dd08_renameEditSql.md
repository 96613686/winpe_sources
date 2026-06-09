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
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  const void *v13; // rsi
  __int64 v15; // r13
  char *v16; // rbx
  void *v17; // rbp
  void *v18; // r12
  __int64 v19; // rax
  unsigned int v20; // r15d
  _QWORD *v21; // rdx
  __int64 v22; // rdi
  int v23; // r8d
  __int64 v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rcx
  unsigned __int8 *v27; // rcx
  unsigned int v28; // ebp
  const void *v29; // rdx
  _DWORD *v30; // r14
  const char *v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // eax
  int v34; // r12d
  int v35; // [rsp+30h] [rbp-78h]
  int v36; // [rsp+34h] [rbp-74h]
  unsigned int Size; // [rsp+38h] [rbp-70h]
  void *v38; // [rsp+40h] [rbp-68h]
  void *v39; // [rsp+48h] [rbp-60h]
  void *v40; // [rsp+50h] [rbp-58h]
  __int64 v41; // [rsp+58h] [rbp-50h]

  v6 = a4;
  Size = sqlite3Strlen30(a4, a1, a3);
  v36 = sqlite3Strlen30(v8, v7, v8);
  v41 = sqlite3_context_db_handle(v9);
  if ( v6 )
  {
    v10 = sqlite3MPrintf(v41, "\"%w\" ", v6);
    v13 = (const void *)v10;
    if ( !v10 )
      return 7;
    v15 = (int)(sqlite3Strlen30(v10, v11, v12) - 1);
    v16 = (char *)sqlite3DbMallocZero(v41, v36 + v15 * *((int *)a2 + 2) + 1);
    if ( v16 )
    {
      v17 = 0;
      v18 = 0;
LABEL_8:
      v20 = 0;
      v40 = v18;
      v39 = v17;
      memcpy_0(v16, a3, v36);
      v21 = a2;
      v22 = *a2;
      if ( *a2 )
      {
        v23 = v36;
        v35 = v36;
        do
        {
          v24 = *(_QWORD *)(v22 + 24);
          if ( v24 )
          {
            do
            {
              if ( *(_QWORD *)(v24 + 8) > *(_QWORD *)(v22 + 8) )
                v22 = v24;
              v24 = *(_QWORD *)(v24 + 24);
            }
            while ( v24 );
            v39 = v17;
            v40 = v18;
          }
          v25 = *v21;
          if ( *v21 == v22 )
          {
            v26 = v21;
          }
          else
          {
            do
            {
              v26 = (_QWORD *)(v25 + 24);
              v25 = *(_QWORD *)(v25 + 24);
            }
            while ( v25 != v22 );
          }
          *v26 = *(_QWORD *)(v22 + 24);
          if ( v6 )
          {
            v27 = *(unsigned __int8 **)(v22 + 8);
            if ( a5 || (byte_18009E630[*v27] & 0x46) == 0 )
            {
              v30 = (_DWORD *)(v22 + 16);
              v29 = v13;
              v28 = v15;
              v38 = (void *)v13;
              if ( v27[*(unsigned int *)(v22 + 16)] == 34 )
                v28 = v15 + 1;
            }
            else
            {
              v28 = Size;
              v29 = v6;
              v38 = (void *)v6;
              v30 = (_DWORD *)(v22 + 16);
            }
          }
          else
          {
            v30 = (_DWORD *)(v22 + 16);
            memcpy_0(v17, *(const void **)(v22 + 8), *(unsigned int *)(v22 + 16));
            *((_BYTE *)v17 + *(unsigned int *)(v22 + 16)) = 0;
            sqlite3Dequote(v17);
            v31 = " ";
            if ( *(_BYTE *)(*(unsigned int *)(v22 + 16) + *(_QWORD *)(v22 + 8)) != 39 )
              v31 = byte_18009EEF0;
            sqlite3_snprintf((unsigned int)(2 * v36), v18, "%Q%s", v17, v31);
            v38 = v18;
            v33 = sqlite3Strlen30(v18, v18, v32);
            v23 = v35;
            v28 = v33;
          }
          v34 = *(_DWORD *)(v22 + 8) - (_DWORD)a3;
          if ( *v30 != v28 )
          {
            memmove_0(&v16[v34 + v28], &v16[v34 + *v30], (unsigned int)(v23 - v34 - *v30));
            v29 = v38;
            v35 += v28 - *v30;
            v16[v35] = 0;
          }
          memcpy_0(&v16[v34], v29, v28);
          sqlite3DbFree(v41, v22);
          v21 = a2;
          v17 = v39;
          v18 = v40;
          v6 = a4;
          v22 = *a2;
          v23 = v35;
        }
        while ( *a2 );
        v20 = 0;
      }
      sqlite3_result_text(a1, v16, -1, -1);
      sqlite3DbFree(v41, v16);
      goto LABEL_34;
    }
  }
  else
  {
    v13 = 0;
    v19 = sqlite3DbMallocZero(v41, 6LL * v36 + 3);
    v16 = (char *)v19;
    if ( v19 )
    {
      LODWORD(v15) = 0;
      v17 = (void *)(v19 + 2LL * v36 + 1);
      v18 = (void *)(v19 + 4LL * v36 + 2);
      goto LABEL_8;
    }
  }
  v20 = 7;
LABEL_34:
  sqlite3_free(v13);
  return v20;
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
0x18007de9a  lea     rdx, byte_18009E630
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
0x18007defe  lea     r8, byte_18009EEF0
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
