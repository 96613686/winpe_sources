# renameQuotefixFunc

- ea: `0x180065620`
- end: `0x1800658c2`
- name: `renameQuotefixFunc`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x18000e5c0`
- `0x18000e790`
- `0x18000e7f0`
- `0x180028540`
- `0x180039850`
- `0x180047bbc`
- `0x180047c2c`
- `0x180048d20`
- `0x18006170c`
- `0x180065620`
- `0x180065930`
- `0x180065c94`
- `0x1800680a0`
- `0x180068880`
- `0x18006910e`
- `0x18007dd08`
- `0x18007e074`
- `0x18007e240`
- `0x18007eb1c`
- `0x18007eca4`

## pseudocode

```c
__int64 __fastcall renameQuotefixFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r13
  __int64 v13; // r15
  unsigned int v14; // ebx
  __int64 v15; // rsi
  __int64 v16; // r8
  int i; // ebx
  __int64 v18; // rax
  __int64 v19; // rdx
  _QWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h]
  _OWORD *v23; // [rsp+58h] [rbp-A8h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[24]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+1E0h] [rbp+E0h]
  __int64 v28; // [rsp+1E8h] [rbp+E8h]

  v5 = sqlite3_context_db_handle(a1);
  LOBYTE(v6) = 1;
  v7 = v5;
  v8 = sqlite3ValueText(*a3, v6);
  LOBYTE(v9) = 1;
  v10 = v8;
  v11 = sqlite3ValueText(a3[1], v9);
  v12 = *(_QWORD *)(v7 + 512);
  v13 = v11;
  *(_QWORD *)(v7 + 512) = 0;
  sqlite3BtreeEnterAll(v7);
  if ( v10 && v13 )
  {
    memset_0(v25, 0, 0x1A8u);
    v14 = renameParseSql((__int64)v25, v10, v7, v13, 0);
    if ( v14 )
      goto LABEL_19;
    v21[0] = v25;
    v21[1] = renameQuotefixExprCb;
    v21[2] = renameColumnSelectCb;
    v23 = v24;
    memset(v24, 0, sizeof(v24));
    v22 = 0;
    if ( v27 )
    {
      if ( *(_BYTE *)(v27 + 63) == 2 )
      {
        v15 = *(_QWORD *)(v27 + 64);
        *(_DWORD *)(v15 + 4) &= ~0x200000u;
        v26 = 0;
        sqlite3SelectPrep(v25, v15, 0);
        if ( *(_BYTE *)(v7 + 103) )
        {
          v14 = 7;
          goto LABEL_18;
        }
        v14 = v26;
        if ( v26 )
        {
LABEL_18:
          renameTokenFree(v7, *(_QWORD *)&v24[0]);
          if ( !v14 )
          {
LABEL_23:
            renameParseCleanup(v25, v19);
            goto LABEL_24;
          }
LABEL_19:
          if ( (*(_DWORD *)(v7 + 48) & 0x10000001) == 1 && v14 == 1 )
            sqlite3_result_value(a1, a3[1]);
          else
            sqlite3_result_error_code(a1, v14);
          goto LABEL_23;
        }
        sqlite3WalkSelect(v21, v15);
      }
      else
      {
        sqlite3WalkExprList(v21, *(_QWORD *)(v27 + 32));
        v16 = v27;
        for ( i = 0; i < *(__int16 *)(v27 + 54); ++i )
        {
          v18 = sqlite3ColumnExpr(v16);
          sqlite3WalkExpr(v21, v18);
          v16 = v27;
        }
      }
    }
    else if ( v28 )
    {
      sqlite3WalkExprList(v21, *(_QWORD *)(v28 + 80));
      sqlite3WalkExpr(v21, *(_QWORD *)(v28 + 72));
    }
    else
    {
      v14 = renameResolveTrigger(v25);
      if ( v14 )
        goto LABEL_18;
      renameWalkTrigger(v21);
    }
    v14 = renameEditSql(a1, (unsigned int)v24, v13, 0, 0);
    goto LABEL_18;
  }
LABEL_24:
  *(_QWORD *)(v7 + 512) = v12;
  return sqlite3BtreeLeaveAll(v7);
}

```

## disassembly

```asm
0x180065620  mov     [rsp-8+arg_8], rbx
0x180065625  push    rbp
0x180065626  push    rsi
0x180065627  push    rdi
0x180065628  push    r12
0x18006562a  push    r13
0x18006562c  push    r14
0x18006562e  push    r15
0x180065630  lea     rbp, [rsp-140h]
0x180065638  sub     rsp, 240h
0x18006563f  mov     rax, cs:__security_cookie
0x180065646  xor     rax, rsp
0x180065649  mov     [rbp+170h+var_40], rax
0x180065650  mov     r12, r8
0x180065653  mov     r14, rcx
0x180065656  call    sqlite3_context_db_handle
0x18006565b  mov     rcx, [r12]
0x18006565f  mov     dl, 1
0x180065661  mov     rdi, rax
0x180065664  call    sqlite3ValueText
0x180065669  mov     rcx, [r12+8]
0x18006566e  mov     dl, 1
0x180065670  mov     rbx, rax
0x180065673  call    sqlite3ValueText
0x180065678  mov     r13, [rdi+200h]
0x18006567f  mov     rcx, rdi
0x180065682  mov     r15, rax
0x180065685  mov     qword ptr [rdi+200h], 0
0x180065690  call    sqlite3BtreeEnterAll
0x180065695  test    rbx, rbx
0x180065698  jz      loc_180065889
0x18006569e  test    r15, r15
0x1800656a1  jz      loc_180065889
0x1800656a7  xor     edx, edx; Val
0x1800656a9  lea     rcx, [rbp+170h+var_1F0]; void *
0x1800656ad  mov     r8d, 1A8h; Size
0x1800656b3  call    memset_0
0x1800656b8  mov     r9, r15
0x1800656bb  mov     [rsp+270h+var_250], 0
0x1800656c3  mov     r8, rdi
0x1800656c6  lea     rcx, [rbp+170h+var_1F0]
0x1800656ca  mov     rdx, rbx
0x1800656cd  call    renameParseSql
0x1800656d2  mov     ebx, eax
0x1800656d4  test    eax, eax
0x1800656d6  jnz     loc_180065855
0x1800656dc  mov     rdx, [rbp+170h+var_90]
0x1800656e3  lea     rax, [rbp+170h+var_1F0]
0x1800656e7  mov     [rsp+270h+var_240], rax
0x1800656ec  lea     rax, renameQuotefixExprCb
0x1800656f3  mov     [rsp+270h+var_238], rax
0x1800656f8  lea     rax, renameColumnSelectCb
0x1800656ff  mov     [rsp+270h+var_230], rax
0x180065704  xorps   xmm0, xmm0
0x180065707  lea     rax, [rsp+270h+var_210]
0x18006570c  xorps   xmm1, xmm1
0x18006570f  mov     [rsp+270h+var_218], rax
0x180065714  movups  [rsp+270h+var_210], xmm0
0x180065719  movups  [rsp+270h+var_200], xmm0
0x18006571e  movdqu  [rsp+270h+var_228], xmm1
0x180065724  test    rdx, rdx
0x180065727  jz      loc_1800657D6
0x18006572d  cmp     byte ptr [rdx+3Fh], 2
0x180065731  jnz     short loc_18006577A
0x180065733  mov     rsi, [rdx+40h]
0x180065737  lea     rcx, [rbp+170h+var_1F0]
0x18006573b  xor     r8d, r8d
0x18006573e  mov     rdx, rsi
0x180065741  btr     dword ptr [rsi+4], 15h
0x180065746  mov     [rbp+170h+var_1D8], ebx
0x180065749  call    sqlite3SelectPrep
0x18006574e  cmp     [rdi+67h], bl
0x180065751  jz      short loc_18006575D
0x180065753  mov     ebx, 7
0x180065758  jmp     loc_180065844
0x18006575d  mov     ebx, [rbp+170h+var_1D8]
0x180065760  test    ebx, ebx
0x180065762  jnz     loc_180065844
0x180065768  mov     rdx, rsi
0x18006576b  lea     rcx, [rsp+270h+var_240]
0x180065770  call    sqlite3WalkSelect
0x180065775  jmp     loc_180065827
0x18006577a  mov     rdx, [rdx+20h]
0x18006577e  lea     rcx, [rsp+270h+var_240]
0x180065783  call    sqlite3WalkExprList
0x180065788  mov     r8, [rbp+170h+var_90]
0x18006578f  xor     ebx, ebx
0x180065791  xor     eax, eax
0x180065793  cmp     ax, [r8+36h]
0x180065798  jge     loc_180065827
0x18006579e  movsxd  rax, ebx
0x1800657a1  lea     rcx, [rax+rax*2]
0x1800657a5  mov     rax, [r8+8]
0x1800657a9  lea     rdx, [rax+rcx*8]
0x1800657ad  mov     rcx, r8
0x1800657b0  call    sqlite3ColumnExpr
0x1800657b5  mov     rdx, rax
0x1800657b8  lea     rcx, [rsp+270h+var_240]
0x1800657bd  call    sqlite3WalkExpr
0x1800657c2  mov     r8, [rbp+170h+var_90]
0x1800657c9  inc     ebx
0x1800657cb  movsx   eax, word ptr [r8+36h]
0x1800657d0  cmp     ebx, eax
0x1800657d2  jl      short loc_18006579E
0x1800657d4  jmp     short loc_180065827
0x1800657d6  mov     rdx, [rbp+170h+var_88]
0x1800657dd  test    rdx, rdx
0x1800657e0  jz      short loc_180065807
0x1800657e2  mov     rdx, [rdx+50h]
0x1800657e6  lea     rcx, [rsp+270h+var_240]
0x1800657eb  call    sqlite3WalkExprList
0x1800657f0  mov     rdx, [rbp+170h+var_88]
0x1800657f7  lea     rcx, [rsp+270h+var_240]
0x1800657fc  mov     rdx, [rdx+48h]
0x180065800  call    sqlite3WalkExpr
0x180065805  jmp     short loc_180065827
0x180065807  lea     rcx, [rbp+170h+var_1F0]
0x18006580b  call    renameResolveTrigger
0x180065810  mov     ebx, eax
0x180065812  test    eax, eax
0x180065814  jnz     short loc_180065844
0x180065816  mov     rdx, [rbp+170h+var_80]
0x18006581d  lea     rcx, [rsp+270h+var_240]
0x180065822  call    renameWalkTrigger
0x180065827  xor     r9d, r9d
0x18006582a  mov     [rsp+270h+var_250], 0
0x180065832  mov     r8, r15
0x180065835  lea     rdx, [rsp+270h+var_210]
0x18006583a  mov     rcx, r14
0x18006583d  call    renameEditSql
0x180065842  mov     ebx, eax
0x180065844  mov     rdx, qword ptr [rsp+270h+var_210]
0x180065849  mov     rcx, rdi
0x18006584c  call    renameTokenFree
0x180065851  test    ebx, ebx
0x180065853  jz      short loc_180065880
0x180065855  mov     eax, [rdi+30h]
0x180065858  and     eax, 10000001h
0x18006585d  cmp     rax, 1
0x180065861  jnz     short loc_180065876
0x180065863  cmp     ebx, eax
0x180065865  jnz     short loc_180065876
0x180065867  mov     rdx, [r12+8]
0x18006586c  mov     rcx, r14
0x18006586f  call    sqlite3_result_value
0x180065874  jmp     short loc_180065880
0x180065876  mov     edx, ebx
0x180065878  mov     rcx, r14
0x18006587b  call    sqlite3_result_error_code
0x180065880  lea     rcx, [rbp+170h+var_1F0]
0x180065884  call    renameParseCleanup
0x180065889  mov     rcx, rdi
0x18006588c  mov     [rdi+200h], r13
0x180065893  call    sqlite3BtreeLeaveAll
0x180065898  mov     rcx, [rbp+170h+var_40]
0x18006589f  xor     rcx, rsp; StackCookie
0x1800658a2  call    __security_check_cookie
0x1800658a7  mov     rbx, [rsp+270h+arg_8]
0x1800658af  add     rsp, 240h
0x1800658b6  pop     r15
0x1800658b8  pop     r14
0x1800658ba  pop     r13
0x1800658bc  pop     r12
0x1800658be  pop     rdi
0x1800658bf  pop     rsi
0x1800658c0  pop     rbp
0x1800658c1  retn
```
