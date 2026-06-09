# renameQuotefixFunc

- ea: `0x1800774f0`
- end: `0x180077792`
- name: `renameQuotefixFunc`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x18000509c`
- `0x180018f60`
- `0x180018fd0`
- `0x1800191d0`
- `0x18001fe1c`
- `0x1800208bc`
- `0x180024b60`
- `0x180051fd0`
- `0x180070500`
- `0x1800774f0`
- `0x1800777a0`
- `0x180077ac4`
- `0x180078968`
- `0x1800789c0`
- `0x18008d078`
- `0x18008d3e4`
- `0x18008d5b0`
- `0x18008de78`
- `0x18008dff0`
- `0x18009d8b0`

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
  __int64 v16; // r9
  __int64 v17; // r8
  int i; // ebx
  __int64 v19; // rax
  __int64 v20; // rdx
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h]
  _OWORD *v24; // [rsp+58h] [rbp-A8h]
  _OWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[24]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+1E0h] [rbp+E0h]
  __int64 v29; // [rsp+1E8h] [rbp+E8h]

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
    memset_0(v26, 0, 0x1A8u);
    v14 = renameParseSql((__int64)v26, v10, v7, v13, 0);
    if ( v14 )
      goto LABEL_19;
    v22[0] = v26;
    v22[1] = renameQuotefixExprCb;
    v22[2] = renameColumnSelectCb;
    v24 = v25;
    memset(v25, 0, sizeof(v25));
    v23 = 0;
    if ( v28 )
    {
      if ( *(_BYTE *)(v28 + 63) == 2 )
      {
        v15 = *(_QWORD *)(v28 + 64);
        *(_DWORD *)(v15 + 4) &= ~0x200000u;
        v27 = 0;
        sqlite3SelectPrep(v26, v15, 0);
        if ( *(_BYTE *)(v7 + 103) )
        {
          v14 = 7;
          goto LABEL_18;
        }
        v14 = v27;
        if ( v27 )
        {
LABEL_18:
          renameTokenFree(v7, *(_QWORD *)&v25[0]);
          if ( !v14 )
          {
LABEL_23:
            renameParseCleanup(v26, v20);
            goto LABEL_24;
          }
LABEL_19:
          if ( (*(_DWORD *)(v7 + 48) & 0x10000001) == 1 && v14 == 1 )
            sqlite3_result_value(a1, a3[1]);
          else
            sqlite3_result_error_code(a1, v14);
          goto LABEL_23;
        }
        sqlite3WalkSelect(v22, v15);
      }
      else
      {
        sqlite3WalkExprList(v22, *(_QWORD *)(v28 + 32));
        v17 = v28;
        for ( i = 0; i < *(__int16 *)(v28 + 54); ++i )
        {
          v19 = sqlite3ColumnExpr(v17, *(_QWORD *)(v17 + 8) + 24LL * i, v17, v16);
          sqlite3WalkExpr(v22, v19);
          v17 = v28;
        }
      }
    }
    else if ( v29 )
    {
      sqlite3WalkExprList(v22, *(_QWORD *)(v29 + 80));
      sqlite3WalkExpr(v22, *(_QWORD *)(v29 + 72));
    }
    else
    {
      v14 = renameResolveTrigger(v26);
      if ( v14 )
        goto LABEL_18;
      renameWalkTrigger(v22);
    }
    v14 = renameEditSql(a1, (unsigned int)v25, v13, 0, 0);
    goto LABEL_18;
  }
LABEL_24:
  *(_QWORD *)(v7 + 512) = v12;
  return sqlite3BtreeLeaveAll(v7);
}

```

## disassembly

```asm
0x1800774f0  mov     [rsp-8+arg_8], rbx
0x1800774f5  push    rbp
0x1800774f6  push    rsi
0x1800774f7  push    rdi
0x1800774f8  push    r12
0x1800774fa  push    r13
0x1800774fc  push    r14
0x1800774fe  push    r15
0x180077500  lea     rbp, [rsp-140h]
0x180077508  sub     rsp, 240h
0x18007750f  mov     rax, cs:__security_cookie
0x180077516  xor     rax, rsp
0x180077519  mov     [rbp+170h+var_40], rax
0x180077520  mov     r12, r8
0x180077523  mov     r14, rcx
0x180077526  call    sqlite3_context_db_handle
0x18007752b  mov     rcx, [r12]
0x18007752f  mov     dl, 1
0x180077531  mov     rdi, rax
0x180077534  call    sqlite3ValueText
0x180077539  mov     rcx, [r12+8]
0x18007753e  mov     dl, 1
0x180077540  mov     rbx, rax
0x180077543  call    sqlite3ValueText
0x180077548  mov     r13, [rdi+200h]
0x18007754f  mov     rcx, rdi
0x180077552  mov     r15, rax
0x180077555  mov     qword ptr [rdi+200h], 0
0x180077560  call    sqlite3BtreeEnterAll
0x180077565  test    rbx, rbx
0x180077568  jz      loc_180077759
0x18007756e  test    r15, r15
0x180077571  jz      loc_180077759
0x180077577  xor     edx, edx; Val
0x180077579  lea     rcx, [rbp+170h+var_1F0]; void *
0x18007757d  mov     r8d, 1A8h; Size
0x180077583  call    memset_0
0x180077588  mov     r9, r15
0x18007758b  mov     [rsp+270h+var_250], 0
0x180077593  mov     r8, rdi
0x180077596  lea     rcx, [rbp+170h+var_1F0]
0x18007759a  mov     rdx, rbx
0x18007759d  call    renameParseSql
0x1800775a2  mov     ebx, eax
0x1800775a4  test    eax, eax
0x1800775a6  jnz     loc_180077725
0x1800775ac  mov     rdx, [rbp+170h+var_90]
0x1800775b3  lea     rax, [rbp+170h+var_1F0]
0x1800775b7  mov     [rsp+270h+var_240], rax
0x1800775bc  lea     rax, renameQuotefixExprCb
0x1800775c3  mov     [rsp+270h+var_238], rax
0x1800775c8  lea     rax, renameColumnSelectCb
0x1800775cf  mov     [rsp+270h+var_230], rax
0x1800775d4  xorps   xmm0, xmm0
0x1800775d7  lea     rax, [rsp+270h+var_210]
0x1800775dc  xorps   xmm1, xmm1
0x1800775df  mov     [rsp+270h+var_218], rax
0x1800775e4  movups  [rsp+270h+var_210], xmm0
0x1800775e9  movups  [rsp+270h+var_200], xmm0
0x1800775ee  movdqu  [rsp+270h+var_228], xmm1
0x1800775f4  test    rdx, rdx
0x1800775f7  jz      loc_1800776A6
0x1800775fd  cmp     byte ptr [rdx+3Fh], 2
0x180077601  jnz     short loc_18007764A
0x180077603  mov     rsi, [rdx+40h]
0x180077607  lea     rcx, [rbp+170h+var_1F0]
0x18007760b  xor     r8d, r8d
0x18007760e  mov     rdx, rsi
0x180077611  btr     dword ptr [rsi+4], 15h
0x180077616  mov     [rbp+170h+var_1D8], ebx
0x180077619  call    sqlite3SelectPrep
0x18007761e  cmp     [rdi+67h], bl
0x180077621  jz      short loc_18007762D
0x180077623  mov     ebx, 7
0x180077628  jmp     loc_180077714
0x18007762d  mov     ebx, [rbp+170h+var_1D8]
0x180077630  test    ebx, ebx
0x180077632  jnz     loc_180077714
0x180077638  mov     rdx, rsi
0x18007763b  lea     rcx, [rsp+270h+var_240]
0x180077640  call    sqlite3WalkSelect
0x180077645  jmp     loc_1800776F7
0x18007764a  mov     rdx, [rdx+20h]
0x18007764e  lea     rcx, [rsp+270h+var_240]
0x180077653  call    sqlite3WalkExprList
0x180077658  mov     r8, [rbp+170h+var_90]
0x18007765f  xor     ebx, ebx
0x180077661  xor     eax, eax
0x180077663  cmp     ax, [r8+36h]
0x180077668  jge     loc_1800776F7
0x18007766e  movsxd  rax, ebx
0x180077671  lea     rcx, [rax+rax*2]
0x180077675  mov     rax, [r8+8]
0x180077679  lea     rdx, [rax+rcx*8]
0x18007767d  mov     rcx, r8
0x180077680  call    sqlite3ColumnExpr
0x180077685  mov     rdx, rax
0x180077688  lea     rcx, [rsp+270h+var_240]
0x18007768d  call    sqlite3WalkExpr
0x180077692  mov     r8, [rbp+170h+var_90]
0x180077699  inc     ebx
0x18007769b  movsx   eax, word ptr [r8+36h]
0x1800776a0  cmp     ebx, eax
0x1800776a2  jl      short loc_18007766E
0x1800776a4  jmp     short loc_1800776F7
0x1800776a6  mov     rdx, [rbp+170h+var_88]
0x1800776ad  test    rdx, rdx
0x1800776b0  jz      short loc_1800776D7
0x1800776b2  mov     rdx, [rdx+50h]
0x1800776b6  lea     rcx, [rsp+270h+var_240]
0x1800776bb  call    sqlite3WalkExprList
0x1800776c0  mov     rdx, [rbp+170h+var_88]
0x1800776c7  lea     rcx, [rsp+270h+var_240]
0x1800776cc  mov     rdx, [rdx+48h]
0x1800776d0  call    sqlite3WalkExpr
0x1800776d5  jmp     short loc_1800776F7
0x1800776d7  lea     rcx, [rbp+170h+var_1F0]
0x1800776db  call    renameResolveTrigger
0x1800776e0  mov     ebx, eax
0x1800776e2  test    eax, eax
0x1800776e4  jnz     short loc_180077714
0x1800776e6  mov     rdx, [rbp+170h+var_80]
0x1800776ed  lea     rcx, [rsp+270h+var_240]
0x1800776f2  call    renameWalkTrigger
0x1800776f7  xor     r9d, r9d
0x1800776fa  mov     [rsp+270h+var_250], 0
0x180077702  mov     r8, r15
0x180077705  lea     rdx, [rsp+270h+var_210]
0x18007770a  mov     rcx, r14
0x18007770d  call    renameEditSql
0x180077712  mov     ebx, eax
0x180077714  mov     rdx, qword ptr [rsp+270h+var_210]
0x180077719  mov     rcx, rdi
0x18007771c  call    renameTokenFree
0x180077721  test    ebx, ebx
0x180077723  jz      short loc_180077750
0x180077725  mov     eax, [rdi+30h]
0x180077728  and     eax, 10000001h
0x18007772d  cmp     rax, 1
0x180077731  jnz     short loc_180077746
0x180077733  cmp     ebx, eax
0x180077735  jnz     short loc_180077746
0x180077737  mov     rdx, [r12+8]
0x18007773c  mov     rcx, r14
0x18007773f  call    sqlite3_result_value
0x180077744  jmp     short loc_180077750
0x180077746  mov     edx, ebx
0x180077748  mov     rcx, r14
0x18007774b  call    sqlite3_result_error_code
0x180077750  lea     rcx, [rbp+170h+var_1F0]
0x180077754  call    renameParseCleanup
0x180077759  mov     rcx, rdi
0x18007775c  mov     [rdi+200h], r13
0x180077763  call    sqlite3BtreeLeaveAll
0x180077768  mov     rcx, [rbp+170h+var_40]
0x18007776f  xor     rcx, rsp; StackCookie
0x180077772  call    __security_check_cookie
0x180077777  mov     rbx, [rsp+270h+arg_8]
0x18007777f  add     rsp, 240h
0x180077786  pop     r15
0x180077788  pop     r14
0x18007778a  pop     r13
0x18007778c  pop     r12
0x18007778e  pop     rdi
0x18007778f  pop     rsi
0x180077790  pop     rbp
0x180077791  retn
```
