# renameTableFunc

- ea: `0x18007e570`
- end: `0x18007e9d9`
- name: `renameTableFunc`
- size: `1129`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x18000e5c0`
- `0x18000e790`
- `0x18000e7f0`
- `0x180014434`
- `0x180014b90`
- `0x180028540`
- `0x180039850`
- `0x180047bbc`
- `0x180047c2c`
- `0x180047fb0`
- `0x180048d20`
- `0x180065930`
- `0x180065bf4`
- `0x180065c94`
- `0x1800680a0`
- `0x180068880`
- `0x18006910e`
- `0x18007dd08`
- `0x18007e074`
- `0x18007e240`
- `0x18007e570`
- `0x18007ead8`
- `0x18007eb1c`
- `0x18007eca4`

## pseudocode

```c
__int64 __fastcall renameTableFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r15
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  _BYTE *v15; // r12
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 result; // rax
  int v20; // edi
  unsigned int v21; // ebx
  _QWORD *v22; // rdi
  int v23; // esi
  __int64 v24; // rax
  __int64 j; // r14
  _QWORD *v26; // rdi
  _QWORD *i; // rbx
  __int64 v28; // rdi
  int *v29; // rdx
  int v30; // edi
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // [rsp+30h] [rbp-D0h]
  __int128 v34; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+88h] [rbp-78h]
  __int128 *v41; // [rsp+98h] [rbp-68h]
  _OWORD v42[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  char v44[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-18h]
  unsigned int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+114h] [rbp+14h]
  __int64 v48; // [rsp+240h] [rbp+140h]
  _QWORD *v49; // [rsp+248h] [rbp+148h]
  _QWORD *v50; // [rsp+250h] [rbp+150h]

  v36 = a1;
  v4 = a1;
  v5 = sqlite3_context_db_handle(a1);
  LOBYTE(v6) = 1;
  v7 = v5;
  v8 = sqlite3ValueText(*a3, v6);
  LOBYTE(v9) = 1;
  v10 = v8;
  v11 = sqlite3ValueText(a3[3], v9);
  LOBYTE(v12) = 1;
  v33 = v11;
  v13 = sqlite3ValueText(a3[4], v12);
  LOBYTE(v14) = 1;
  v15 = (_BYTE *)v13;
  v16 = sqlite3ValueText(a3[5], v14);
  v17 = a3[6];
  v18 = v16;
  v37 = v16;
  result = sqlite3_value_int64(v17);
  v20 = result;
  if ( v33 && v15 && v18 )
  {
    memset_0(v44, 0, 0x1A8u);
    v38 = *(_QWORD *)(v7 + 512);
    *(_QWORD *)(v7 + 512) = 0;
    sqlite3BtreeEnterAll(v7);
    v34 = 0;
    v35 = 0;
    *(_QWORD *)&v35 = sqlite3FindTable(v7, v15, v10);
    v39[0] = v44;
    v39[1] = renameTableExprCb;
    v39[2] = renameTableSelectCb;
    v41 = &v34;
    v40 = 0;
    v21 = renameParseSql((__int64)v44, v10, v7, v33, v20);
    if ( v21 )
      goto LABEL_47;
    v22 = (_QWORD *)v48;
    v23 = *(_DWORD *)(v7 + 48) & 0x4000000;
    if ( !v48 )
    {
      if ( v49 )
      {
        renameTokenFind(v44, &v34, *v49);
        if ( !v23 )
          sqlite3WalkExpr(v39, v49[9]);
      }
      else
      {
        v26 = v50;
        if ( !(unsigned int)sqlite3_stricmp(v50[1], v15) && *(_QWORD *)(v35 + 96) == v26[6] )
          renameTokenFind(v44, &v34, v26[1]);
        if ( !v23 )
        {
          v21 = renameResolveTrigger(v44);
          if ( v21 )
            goto LABEL_47;
          renameWalkTrigger(v39);
          for ( i = (_QWORD *)v26[7]; i; i = (_QWORD *)i[10] )
          {
            v28 = i[3];
            if ( v28 && !(unsigned int)sqlite3_stricmp(i[3], v15) )
              renameTokenFind(v44, &v34, v28);
            v29 = (int *)i[4];
            if ( v29 && *v29 > 0 )
            {
              v30 = 0;
              do
              {
                v31 = *(_QWORD *)&v29[20 * v30 + 2];
                if ( !(unsigned int)sqlite3_stricmp(v31, v15) )
                  renameTokenFind(v44, &v34, v31);
                v29 = (int *)i[4];
                ++v30;
              }
              while ( v30 < *v29 );
            }
          }
        }
      }
      goto LABEL_46;
    }
    if ( *(_BYTE *)(v48 + 63) == 2 )
    {
      if ( !v23 )
      {
        v43 = 0;
        v42[0] = (unsigned __int64)v44;
        v24 = *(_QWORD *)(v48 + 64);
        memset(&v42[1], 0, 32);
        *(_DWORD *)(v24 + 4) &= ~0x200000u;
        sqlite3SelectPrep(v44, v22[8], v42);
        if ( v47 )
          v21 = v46;
        else
          sqlite3WalkSelect(v39, v22[8]);
        goto LABEL_24;
      }
    }
    else
    {
      if ( (!v23 || (*(_DWORD *)(v7 + 48) & 0x4000LL) != 0) && *(_BYTE *)(v48 + 63) != 1 )
      {
        for ( j = *(_QWORD *)(v48 + 72); j; j = *(_QWORD *)(j + 8) )
        {
          if ( !(unsigned int)sqlite3_stricmp(*(_QWORD *)(j + 16), v15) )
            renameTokenFind(v44, &v34, *(_QWORD *)(j + 16));
        }
        v4 = v36;
      }
      if ( !(unsigned int)sqlite3_stricmp(v15, *v22) )
      {
        *(_QWORD *)&v35 = v22;
        if ( !v23 )
          sqlite3WalkExprList(v39, v22[4]);
        renameTokenFind(v44, &v34, *v22);
LABEL_24:
        if ( v21 )
          goto LABEL_47;
      }
    }
LABEL_46:
    v21 = renameEditSql(v4, (unsigned int)&v34, v33, v37, 1);
    if ( !v21 )
    {
LABEL_53:
      renameParseCleanup(v44, v32);
      renameTokenFree(v7, v34);
      sqlite3BtreeLeaveAll(v7);
      result = v38;
      *(_QWORD *)(v7 + 512) = v38;
      return result;
    }
LABEL_47:
    if ( v21 == 1 && (*(_DWORD *)(v7 + 48) & 0x10000001) == 1 )
    {
      sqlite3_result_value(v4, a3[3]);
    }
    else if ( v45 )
    {
      renameColumnParseError(v4, (unsigned int)byte_18009EEF0, a3[1], a3[2], (__int64)v44);
    }
    else
    {
      sqlite3_result_error_code(v4, v21);
    }
    goto LABEL_53;
  }
  return result;
}

```

## disassembly

```asm
0x18007e570  mov     [rsp-8+arg_8], rbx
0x18007e575  push    rbp
0x18007e576  push    rsi
0x18007e577  push    rdi
0x18007e578  push    r12
0x18007e57a  push    r13
0x18007e57c  push    r14
0x18007e57e  push    r15
0x18007e580  lea     rbp, [rsp-1A0h]
0x18007e588  sub     rsp, 2A0h
0x18007e58f  mov     rax, cs:__security_cookie
0x18007e596  xor     rax, rsp
0x18007e599  mov     [rbp+1D0h+var_40], rax
0x18007e5a0  mov     r13, r8
0x18007e5a3  mov     [rsp+2D0h+var_278], rcx
0x18007e5a8  mov     r14, rcx
0x18007e5ab  call    sqlite3_context_db_handle
0x18007e5b0  mov     rcx, [r13+0]
0x18007e5b4  mov     dl, 1
0x18007e5b6  mov     r15, rax
0x18007e5b9  call    sqlite3ValueText
0x18007e5be  mov     rcx, [r13+18h]
0x18007e5c2  mov     dl, 1
0x18007e5c4  mov     rbx, rax
0x18007e5c7  call    sqlite3ValueText
0x18007e5cc  mov     rcx, [r13+20h]
0x18007e5d0  mov     dl, 1
0x18007e5d2  mov     [rsp+2D0h+var_2A0], rax
0x18007e5d7  call    sqlite3ValueText
0x18007e5dc  mov     rcx, [r13+28h]
0x18007e5e0  mov     dl, 1
0x18007e5e2  mov     r12, rax
0x18007e5e5  call    sqlite3ValueText
0x18007e5ea  mov     rcx, [r13+30h]
0x18007e5ee  mov     rsi, rax
0x18007e5f1  mov     [rsp+2D0h+var_270], rax
0x18007e5f6  call    sqlite3_value_int64
0x18007e5fb  cmp     [rsp+2D0h+var_2A0], 0
0x18007e601  mov     rdi, rax
0x18007e604  jz      loc_18007E9AF
0x18007e60a  test    r12, r12
0x18007e60d  jz      loc_18007E9AF
0x18007e613  test    rsi, rsi
0x18007e616  jz      loc_18007E9AF
0x18007e61c  xor     edx, edx; Val
0x18007e61e  lea     rcx, [rbp+1D0h+var_1F0]; void *
0x18007e622  mov     r8d, 1A8h; Size
0x18007e628  call    memset_0
0x18007e62d  mov     rax, [r15+200h]
0x18007e634  xorps   xmm1, xmm1
0x18007e637  xorps   xmm0, xmm0
0x18007e63a  mov     [rsp+2D0h+var_268], rax
0x18007e63f  mov     rcx, r15
0x18007e642  mov     qword ptr [r15+200h], 0
0x18007e64d  movups  [rsp+2D0h+var_298], xmm0
0x18007e652  movups  [rsp+2D0h+var_288], xmm0
0x18007e657  movups  [rsp+2D0h+var_260], xmm1
0x18007e65c  movups  [rbp+1D0h+var_250], xmm1
0x18007e660  movups  [rbp+1D0h+var_240], xmm1
0x18007e664  call    sqlite3BtreeEnterAll
0x18007e669  xorps   xmm0, xmm0
0x18007e66c  mov     r8, rbx
0x18007e66f  mov     rdx, r12
0x18007e672  mov     rcx, r15
0x18007e675  movups  [rsp+2D0h+var_298], xmm0
0x18007e67a  movups  [rsp+2D0h+var_288], xmm0
0x18007e67f  call    sqlite3FindTable
0x18007e684  mov     r9, [rsp+2D0h+var_2A0]
0x18007e689  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e68d  mov     qword ptr [rsp+2D0h+var_288], rax
0x18007e692  xorps   xmm0, xmm0
0x18007e695  lea     rax, [rbp+1D0h+var_1F0]
0x18007e699  mov     dword ptr [rsp+2D0h+var_2B0], edi
0x18007e69d  mov     qword ptr [rsp+2D0h+var_260], rax
0x18007e6a2  mov     r8, r15
0x18007e6a5  lea     rax, renameTableExprCb
0x18007e6ac  mov     rdx, rbx
0x18007e6af  mov     qword ptr [rsp+2D0h+var_260+8], rax
0x18007e6b4  lea     rax, renameTableSelectCb
0x18007e6bb  mov     qword ptr [rbp+1D0h+var_250], rax
0x18007e6bf  lea     rax, [rsp+2D0h+var_298]
0x18007e6c4  mov     qword ptr [rbp+1D0h+var_240+8], rax
0x18007e6c8  movdqu  [rbp+1D0h+var_250+8], xmm0
0x18007e6cd  call    renameParseSql
0x18007e6d2  mov     ebx, eax
0x18007e6d4  test    eax, eax
0x18007e6d6  jnz     loc_18007E933
0x18007e6dc  mov     esi, [r15+30h]
0x18007e6e0  mov     rdi, [rbp+1D0h+var_90]
0x18007e6e7  and     esi, 4000000h
0x18007e6ed  test    rdi, rdi
0x18007e6f0  jz      loc_18007E7EE
0x18007e6f6  cmp     byte ptr [rdi+3Fh], 2
0x18007e6fa  jnz     short loc_18007E75B
0x18007e6fc  test    esi, esi
0x18007e6fe  jnz     loc_18007E90E
0x18007e704  xor     eax, eax
0x18007e706  lea     r8, [rbp+1D0h+var_230]
0x18007e70a  mov     [rbp+1D0h+var_200], rax
0x18007e70e  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e712  xorps   xmm0, xmm0
0x18007e715  lea     rax, [rbp+1D0h+var_1F0]
0x18007e719  movups  [rbp+1D0h+var_230], xmm0
0x18007e71d  mov     qword ptr [rbp+1D0h+var_230], rax
0x18007e721  mov     rax, [rdi+40h]
0x18007e725  movups  [rbp+1D0h+var_220], xmm0
0x18007e729  movups  [rbp+1D0h+var_210], xmm0
0x18007e72d  btr     dword ptr [rax+4], 15h
0x18007e732  mov     rdx, [rdi+40h]
0x18007e736  call    sqlite3SelectPrep
0x18007e73b  cmp     [rbp+1D0h+var_1BC], esi
0x18007e73e  jz      short loc_18007E748
0x18007e740  mov     ebx, [rbp+1D0h+var_1D8]
0x18007e743  jmp     loc_18007E7E1
0x18007e748  mov     rdx, [rdi+40h]
0x18007e74c  lea     rcx, [rsp+2D0h+var_260]
0x18007e751  call    sqlite3WalkSelect
0x18007e756  jmp     loc_18007E7E1
0x18007e75b  test    esi, esi
0x18007e75d  jz      short loc_18007E76A
0x18007e75f  mov     eax, [r15+30h]
0x18007e763  bt      rax, 0Eh
0x18007e768  jnb     short loc_18007E7A6
0x18007e76a  cmp     byte ptr [rdi+3Fh], 1
0x18007e76e  jz      short loc_18007E7A6
0x18007e770  mov     r14, [rdi+48h]
0x18007e774  test    r14, r14
0x18007e777  jz      short loc_18007E7A1
0x18007e779  mov     rcx, [r14+10h]
0x18007e77d  mov     rdx, r12
0x18007e780  call    sqlite3_stricmp
0x18007e785  test    eax, eax
0x18007e787  jnz     short loc_18007E79B
0x18007e789  mov     r8, [r14+10h]
0x18007e78d  lea     rdx, [rsp+2D0h+var_298]
0x18007e792  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e796  call    renameTokenFind
0x18007e79b  mov     r14, [r14+8]
0x18007e79f  jmp     short loc_18007E774
0x18007e7a1  mov     r14, [rsp+2D0h+var_278]
0x18007e7a6  mov     rdx, [rdi]
0x18007e7a9  mov     rcx, r12
0x18007e7ac  call    sqlite3_stricmp
0x18007e7b1  test    eax, eax
0x18007e7b3  jnz     loc_18007E90E
0x18007e7b9  mov     qword ptr [rsp+2D0h+var_288], rdi
0x18007e7be  test    esi, esi
0x18007e7c0  jnz     short loc_18007E7D0
0x18007e7c2  mov     rdx, [rdi+20h]
0x18007e7c6  lea     rcx, [rsp+2D0h+var_260]
0x18007e7cb  call    sqlite3WalkExprList
0x18007e7d0  mov     r8, [rdi]
0x18007e7d3  lea     rdx, [rsp+2D0h+var_298]
0x18007e7d8  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e7dc  call    renameTokenFind
0x18007e7e1  test    ebx, ebx
0x18007e7e3  jz      loc_18007E90E
0x18007e7e9  jmp     loc_18007E933
0x18007e7ee  mov     r8, [rbp+1D0h+var_88]
0x18007e7f5  test    r8, r8
0x18007e7f8  jz      short loc_18007E82D
0x18007e7fa  mov     r8, [r8]
0x18007e7fd  lea     rdx, [rsp+2D0h+var_298]
0x18007e802  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e806  call    renameTokenFind
0x18007e80b  test    esi, esi
0x18007e80d  jnz     loc_18007E90E
0x18007e813  mov     rdx, [rbp+1D0h+var_88]
0x18007e81a  lea     rcx, [rsp+2D0h+var_260]
0x18007e81f  mov     rdx, [rdx+48h]
0x18007e823  call    sqlite3WalkExpr
0x18007e828  jmp     loc_18007E90E
0x18007e82d  mov     rdi, [rbp+1D0h+var_80]
0x18007e834  mov     rdx, r12
0x18007e837  mov     rcx, [rdi+8]
0x18007e83b  call    sqlite3_stricmp
0x18007e840  test    eax, eax
0x18007e842  jnz     short loc_18007E865
0x18007e844  mov     rax, qword ptr [rsp+2D0h+var_288]
0x18007e849  mov     rcx, [rdi+30h]
0x18007e84d  cmp     [rax+60h], rcx
0x18007e851  jnz     short loc_18007E865
0x18007e853  mov     r8, [rdi+8]
0x18007e857  lea     rdx, [rsp+2D0h+var_298]
0x18007e85c  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e860  call    renameTokenFind
0x18007e865  test    esi, esi
0x18007e867  jnz     loc_18007E90E
0x18007e86d  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e871  call    renameResolveTrigger
0x18007e876  mov     ebx, eax
0x18007e878  test    eax, eax
0x18007e87a  jnz     loc_18007E933
0x18007e880  mov     rdx, rdi
0x18007e883  lea     rcx, [rsp+2D0h+var_260]
0x18007e888  call    renameWalkTrigger
0x18007e88d  mov     rbx, [rdi+38h]
0x18007e891  jmp     short loc_18007E909
0x18007e893  mov     rdi, [rbx+18h]
0x18007e897  test    rdi, rdi
0x18007e89a  jz      short loc_18007E8BC
0x18007e89c  mov     rdx, r12
0x18007e89f  mov     rcx, rdi
0x18007e8a2  call    sqlite3_stricmp
0x18007e8a7  test    eax, eax
0x18007e8a9  jnz     short loc_18007E8BC
0x18007e8ab  mov     r8, rdi
0x18007e8ae  lea     rdx, [rsp+2D0h+var_298]
0x18007e8b3  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e8b7  call    renameTokenFind
0x18007e8bc  mov     rdx, [rbx+20h]
0x18007e8c0  test    rdx, rdx
0x18007e8c3  jz      short loc_18007E905
0x18007e8c5  cmp     dword ptr [rdx], 0
0x18007e8c8  jle     short loc_18007E905
0x18007e8ca  xor     edi, edi
0x18007e8cc  movsxd  rax, edi
0x18007e8cf  lea     rcx, [rax+rax*4]
0x18007e8d3  add     rcx, rcx
0x18007e8d6  mov     rsi, [rdx+rcx*8+8]
0x18007e8db  mov     rdx, r12
0x18007e8de  mov     rcx, rsi
0x18007e8e1  call    sqlite3_stricmp
0x18007e8e6  test    eax, eax
0x18007e8e8  jnz     short loc_18007E8FB
0x18007e8ea  mov     r8, rsi
0x18007e8ed  lea     rdx, [rsp+2D0h+var_298]
0x18007e8f2  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e8f6  call    renameTokenFind
0x18007e8fb  mov     rdx, [rbx+20h]
0x18007e8ff  inc     edi
0x18007e901  cmp     edi, [rdx]
0x18007e903  jl      short loc_18007E8CC
0x18007e905  mov     rbx, [rbx+50h]
0x18007e909  test    rbx, rbx
0x18007e90c  jnz     short loc_18007E893
0x18007e90e  mov     r9, [rsp+2D0h+var_270]
0x18007e913  lea     rdx, [rsp+2D0h+var_298]
0x18007e918  mov     r8, [rsp+2D0h+var_2A0]
0x18007e91d  mov     rcx, r14
0x18007e920  mov     dword ptr [rsp+2D0h+var_2B0], 1
0x18007e928  call    renameEditSql
0x18007e92d  mov     ebx, eax
0x18007e92f  test    eax, eax
0x18007e931  jz      short loc_18007E985
0x18007e933  cmp     ebx, 1
0x18007e936  jnz     short loc_18007E955
0x18007e938  mov     eax, [r15+30h]
0x18007e93c  and     eax, 10000001h
0x18007e941  cmp     rax, 1
0x18007e945  jnz     short loc_18007E955
0x18007e947  mov     rdx, [r13+18h]
0x18007e94b  mov     rcx, r14
0x18007e94e  call    sqlite3_result_value
0x18007e953  jmp     short loc_18007E985
0x18007e955  cmp     [rbp+1D0h+var_1E8], 0
0x18007e95a  mov     rcx, r14
0x18007e95d  jz      short loc_18007E97E
0x18007e95f  mov     r9, [r13+10h]
0x18007e963  lea     rax, [rbp+1D0h+var_1F0]
0x18007e967  mov     r8, [r13+8]
0x18007e96b  lea     rdx, byte_18009EEF0
0x18007e972  mov     [rsp+2D0h+var_2B0], rax
0x18007e977  call    renameColumnParseError
0x18007e97c  jmp     short loc_18007E985
0x18007e97e  mov     edx, ebx
0x18007e980  call    sqlite3_result_error_code
0x18007e985  lea     rcx, [rbp+1D0h+var_1F0]
0x18007e989  call    renameParseCleanup
0x18007e98e  mov     rdx, qword ptr [rsp+2D0h+var_298]
0x18007e993  mov     rcx, r15
0x18007e996  call    renameTokenFree
0x18007e99b  mov     rcx, r15
0x18007e99e  call    sqlite3BtreeLeaveAll
0x18007e9a3  mov     rax, [rsp+2D0h+var_268]
0x18007e9a8  mov     [r15+200h], rax
0x18007e9af  mov     rcx, [rbp+1D0h+var_40]
0x18007e9b6  xor     rcx, rsp; StackCookie
0x18007e9b9  call    __security_check_cookie
0x18007e9be  mov     rbx, [rsp+2D0h+arg_8]
0x18007e9c6  add     rsp, 2A0h
0x18007e9cd  pop     r15
0x18007e9cf  pop     r14
0x18007e9d1  pop     r13
0x18007e9d3  pop     r12
0x18007e9d5  pop     rdi
0x18007e9d6  pop     rsi
0x18007e9d7  pop     rbp
0x18007e9d8  retn
```
