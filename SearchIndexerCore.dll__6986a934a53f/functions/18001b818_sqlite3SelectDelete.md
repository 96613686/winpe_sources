# sqlite3SelectDelete

- ea: `0x18001b818`
- end: `0x18001bb57`
- name: `sqlite3SelectDelete`
- size: `831`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180001214`
- `0x18000213c`
- `0x180005190`
- `0x18000a754`
- `0x18001b4b0`
- `0x18001b818`
- `0x18001bb70`
- `0x1800504a8`
- `0x180058b64`
- `0x18005a258`
- `0x18005e21c`
- `0x180060434`
- `0x1800656dc`
- `0x180066cb0`
- `0x18006a580`
- `0x18006ac58`
- `0x18006b084`
- `0x1800707f8`
- `0x18007243c`
- `0x180074ce4`
- `0x180076a98`
- `0x180077098`
- `0x18007be68`
- `0x18007ca00`
- `0x18007f76c`
- `0x18008d5b0`
- `0x180090b7c`

## callees

- `0x18001b818`
- `0x18001bb60`
- `0x18001bc40`
- `0x18001bc5c`
- `0x180025770`
- `0x180041d10`
- `0x180041eb0`
- `0x1800516e4`
- `0x18005a258`
- `0x180073058`
- `0x180076e34`
- `0x180077180`
- `0x18007743c`

## pseudocode

```c
__int64 __fastcall sqlite3SelectDelete(_QWORD *a1, __int64 *a2)
{
  __int64 *v2; // rdi
  _DWORD *v4; // rdx
  __int64 *v5; // r15
  int *v6; // rsi
  int v7; // r14d
  _DWORD *v8; // rbp
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  bool v13; // zf
  __int64 v14; // rdx
  __int64 v15; // rdx
  _DWORD *v16; // rdx
  _DWORD *v17; // rdx
  __int64 v18; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    v2 = a2;
    do
    {
      v4 = (_DWORD *)v2[4];
      v5 = (__int64 *)v2[10];
      if ( v4 )
        exprListDeleteNN(a1, v4);
      v6 = (int *)v2[5];
      if ( v6 )
      {
        v7 = 0;
        v8 = v6 + 2;
        if ( *v6 > 0 )
        {
          while ( 1 )
          {
            v9 = *((_QWORD *)v8 + 1);
            if ( v9 )
              sqlite3DbNNFreeNN(a1, v9);
            v10 = (_QWORD *)*((_QWORD *)v8 + 2);
            if ( !v10 )
              goto LABEL_13;
            if ( (unsigned __int64)v10 >= a1[62] )
              break;
            if ( (unsigned __int64)v10 < a1[60] )
            {
              if ( (unsigned __int64)v10 < a1[61] )
                break;
              *v10 = a1[57];
              a1[57] = v10;
            }
            else
            {
              *v10 = a1[59];
              a1[59] = v10;
            }
LABEL_13:
            v11 = *((_QWORD *)v8 + 3);
            if ( v11 )
              sqlite3DbNNFreeNN(a1, v11);
            if ( (v8[16] & 2) != 0 )
              sqlite3DbFree(a1, *((_QWORD *)v8 + 11));
            if ( (v8[16] & 4) != 0 )
              sqlite3ExprListDeleteGeneric(a1, *((_QWORD *)v8 + 11));
            v12 = *((_QWORD *)v8 + 4);
            if ( v12 )
            {
              if ( a1[97] || (v13 = *(_DWORD *)(v12 + 44) == 1, --*(_DWORD *)(v12 + 44), v13) )
                deleteTable((__int64)a1, v12);
            }
            v14 = *((_QWORD *)v8 + 5);
            if ( v14 )
              sqlite3SelectDelete(a1, v14);
            v15 = *((_QWORD *)v8 + 9);
            if ( (v8[16] & 0x400) != 0 )
            {
              sqlite3IdListDelete(a1, v15);
            }
            else if ( v15 )
            {
              sqlite3ExprDelete(a1, v15);
            }
            ++v7;
            v8 += 26;
            if ( v7 >= *v6 )
              goto LABEL_28;
          }
          if ( a1[97] )
            measureAllocationSize(a1, *((_QWORD *)v8 + 2));
          else
            sqlite3_free(v10);
          goto LABEL_13;
        }
LABEL_28:
        if ( (unsigned __int64)v6 >= a1[62] )
          goto LABEL_65;
        if ( (unsigned __int64)v6 >= a1[60] )
        {
          *(_QWORD *)v6 = a1[59];
          a1[59] = v6;
          goto LABEL_31;
        }
        if ( (unsigned __int64)v6 < a1[61] )
        {
LABEL_65:
          if ( a1[97] )
            measureAllocationSize(a1, v6);
          else
            sqlite3_free(v6);
        }
        else
        {
          *(_QWORD *)v6 = a1[57];
          a1[57] = v6;
        }
      }
LABEL_31:
      sqlite3ExprDelete(a1, v2[6]);
      v16 = (_DWORD *)v2[7];
      if ( v16 )
        exprListDeleteNN(a1, v16);
      sqlite3ExprDelete(a1, v2[8]);
      v17 = (_DWORD *)v2[9];
      if ( v17 )
        exprListDeleteNN(a1, v17);
      sqlite3ExprDelete(a1, v2[12]);
      if ( v2[13] )
        sqlite3WithDelete(a1);
      v18 = v2[15];
      if ( v18 )
        sqlite3WindowListDelete(a1, v18);
      while ( v2[14] )
        sqlite3WindowUnlinkFromSelect();
      if ( (unsigned __int64)v2 >= a1[62] )
      {
LABEL_51:
        if ( a1[97] )
          result = measureAllocationSize(a1, v2);
        else
          result = sqlite3_free(v2);
        goto LABEL_43;
      }
      if ( (unsigned __int64)v2 < a1[60] )
      {
        if ( (unsigned __int64)v2 < a1[61] )
          goto LABEL_51;
        result = a1[57];
        *v2 = result;
        a1[57] = v2;
      }
      else
      {
        result = a1[59];
        *v2 = result;
        a1[59] = v2;
      }
LABEL_43:
      v2 = v5;
    }
    while ( v5 );
  }
  return result;
}

```

## disassembly

```asm
0x18001b818  test    rdx, rdx
0x18001b81b  jz      locret_18001B9F6
0x18001b821  push    rbx
0x18001b822  push    rbp
0x18001b823  push    rsi
0x18001b824  push    rdi
0x18001b825  push    r14
0x18001b827  push    r15
0x18001b829  sub     rsp, 28h
0x18001b82d  mov     rdi, rdx
0x18001b830  mov     rbx, rcx
0x18001b833  mov     rdx, [rdi+20h]
0x18001b837  mov     r15, [rdi+50h]
0x18001b83b  test    rdx, rdx
0x18001b83e  jz      short loc_18001B848
0x18001b840  mov     rcx, rbx
0x18001b843  call    exprListDeleteNN
0x18001b848  mov     rsi, [rdi+28h]
0x18001b84c  test    rsi, rsi
0x18001b84f  jz      loc_18001B94A
0x18001b855  xor     r14d, r14d
0x18001b858  lea     rbp, [rsi+8]
0x18001b85c  cmp     [rsi], r14d
0x18001b85f  jle     loc_18001B91F
0x18001b865  mov     rdx, [rbp+8]
0x18001b869  test    rdx, rdx
0x18001b86c  jnz     loc_18001BAEA
0x18001b872  mov     rcx, [rbp+10h]
0x18001b876  test    rcx, rcx
0x18001b879  jz      short loc_18001B8A6
0x18001b87b  cmp     rcx, [rbx+1F0h]
0x18001b882  jnb     loc_18001BA9F
0x18001b888  cmp     rcx, [rbx+1E0h]
0x18001b88f  jb      loc_18001BA32
0x18001b895  mov     rax, [rbx+1D8h]
0x18001b89c  mov     [rcx], rax
0x18001b89f  mov     [rbx+1D8h], rcx
0x18001b8a6  mov     rdx, [rbp+18h]
0x18001b8aa  test    rdx, rdx
0x18001b8ad  jnz     loc_18001BB01
0x18001b8b3  test    byte ptr [rbp+40h], 2
0x18001b8b7  jnz     loc_18001BB0E
0x18001b8bd  test    byte ptr [rbp+40h], 4
0x18001b8c1  jnz     loc_18001BB1F
0x18001b8c7  mov     rdx, [rbp+20h]
0x18001b8cb  test    rdx, rdx
0x18001b8ce  jz      short loc_18001B8E8
0x18001b8d0  cmp     qword ptr [rbx+308h], 0
0x18001b8d8  jnz     loc_18001BAD3
0x18001b8de  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x18001b8e2  jz      loc_18001BAD3
0x18001b8e8  mov     rdx, [rbp+28h]
0x18001b8ec  test    rdx, rdx
0x18001b8ef  jnz     loc_18001BB30
0x18001b8f5  test    dword ptr [rbp+40h], 400h
0x18001b8fc  mov     rdx, [rbp+48h]
0x18001b900  jnz     loc_18001BB3D
0x18001b906  test    rdx, rdx
0x18001b909  jnz     loc_18001BB4A
0x18001b90f  inc     r14d
0x18001b912  add     rbp, 68h ; 'h'
0x18001b916  cmp     r14d, [rsi]
0x18001b919  jl      loc_18001B865
0x18001b91f  cmp     rsi, [rbx+1F0h]
0x18001b926  jnb     loc_18001BA85
0x18001b92c  cmp     rsi, [rbx+1E0h]
0x18001b933  jb      loc_18001BA13
0x18001b939  mov     rax, [rbx+1D8h]
0x18001b940  mov     [rsi], rax
0x18001b943  mov     [rbx+1D8h], rsi
0x18001b94a  mov     rdx, [rdi+30h]
0x18001b94e  mov     rcx, rbx
0x18001b951  call    sqlite3ExprDelete
0x18001b956  mov     rdx, [rdi+38h]
0x18001b95a  test    rdx, rdx
0x18001b95d  jz      short loc_18001B967
0x18001b95f  mov     rcx, rbx
0x18001b962  call    exprListDeleteNN
0x18001b967  mov     rdx, [rdi+40h]
0x18001b96b  mov     rcx, rbx
0x18001b96e  call    sqlite3ExprDelete
0x18001b973  mov     rdx, [rdi+48h]
0x18001b977  test    rdx, rdx
0x18001b97a  jz      short loc_18001B984
0x18001b97c  mov     rcx, rbx
0x18001b97f  call    exprListDeleteNN
0x18001b984  mov     rdx, [rdi+60h]
0x18001b988  mov     rcx, rbx
0x18001b98b  call    sqlite3ExprDelete
0x18001b990  mov     rdx, [rdi+68h]
0x18001b994  test    rdx, rdx
0x18001b997  jnz     loc_18001BA5E
0x18001b99d  mov     rdx, [rdi+78h]
0x18001b9a1  test    rdx, rdx
0x18001b9a4  jnz     loc_18001BA51
0x18001b9aa  mov     rcx, [rdi+70h]
0x18001b9ae  test    rcx, rcx
0x18001b9b1  jnz     loc_18001BAF7
0x18001b9b7  cmp     rdi, [rbx+1F0h]
0x18001b9be  jnb     loc_18001BA6B
0x18001b9c4  cmp     rdi, [rbx+1E0h]
0x18001b9cb  jb      short loc_18001B9F7
0x18001b9cd  mov     rax, [rbx+1D8h]
0x18001b9d4  mov     [rdi], rax
0x18001b9d7  mov     [rbx+1D8h], rdi
0x18001b9de  mov     rdi, r15
0x18001b9e1  test    r15, r15
0x18001b9e4  jnz     loc_18001B833
0x18001b9ea  add     rsp, 28h
0x18001b9ee  pop     r15
0x18001b9f0  pop     r14
0x18001b9f2  pop     rdi
0x18001b9f3  pop     rsi
0x18001b9f4  pop     rbp
0x18001b9f5  pop     rbx
0x18001b9f6  retn
0x18001b9f7  cmp     rdi, [rbx+1E8h]
0x18001b9fe  jb      short loc_18001BA6B
0x18001ba00  mov     rax, [rbx+1C8h]
0x18001ba07  mov     [rdi], rax
0x18001ba0a  mov     [rbx+1C8h], rdi
0x18001ba11  jmp     short loc_18001B9DE
0x18001ba13  cmp     rsi, [rbx+1E8h]
0x18001ba1a  jb      short loc_18001BA85
0x18001ba1c  mov     rax, [rbx+1C8h]
0x18001ba23  mov     [rsi], rax
0x18001ba26  mov     [rbx+1C8h], rsi
0x18001ba2d  jmp     loc_18001B94A
0x18001ba32  cmp     rcx, [rbx+1E8h]
0x18001ba39  jb      short loc_18001BA9F
0x18001ba3b  mov     rax, [rbx+1C8h]
0x18001ba42  mov     [rcx], rax
0x18001ba45  mov     [rbx+1C8h], rcx
0x18001ba4c  jmp     loc_18001B8A6
0x18001ba51  mov     rcx, rbx
0x18001ba54  call    sqlite3WindowListDelete
0x18001ba59  jmp     loc_18001B9AA
0x18001ba5e  mov     rcx, rbx
0x18001ba61  call    sqlite3WithDelete
0x18001ba66  jmp     loc_18001B99D
0x18001ba6b  cmp     qword ptr [rbx+308h], 0
0x18001ba73  jz      short loc_18001BAB9
0x18001ba75  mov     rdx, rdi
0x18001ba78  mov     rcx, rbx
0x18001ba7b  call    measureAllocationSize
0x18001ba80  jmp     loc_18001B9DE
0x18001ba85  cmp     qword ptr [rbx+308h], 0
0x18001ba8d  jz      short loc_18001BAC6
0x18001ba8f  mov     rdx, rsi
0x18001ba92  mov     rcx, rbx
0x18001ba95  call    measureAllocationSize
0x18001ba9a  jmp     loc_18001B94A
0x18001ba9f  cmp     qword ptr [rbx+308h], 0
0x18001baa7  jz      short loc_18001BAE0
0x18001baa9  mov     rdx, rcx
0x18001baac  mov     rcx, rbx
0x18001baaf  call    measureAllocationSize
0x18001bab4  jmp     loc_18001B8A6
0x18001bab9  mov     rcx, rdi
0x18001babc  call    sqlite3_free
0x18001bac1  jmp     loc_18001B9DE
0x18001bac6  mov     rcx, rsi
0x18001bac9  call    sqlite3_free
0x18001bace  jmp     loc_18001B94A
0x18001bad3  mov     rcx, rbx
0x18001bad6  call    deleteTable
0x18001badb  jmp     loc_18001B8E8
0x18001bae0  call    sqlite3_free
0x18001bae5  jmp     loc_18001B8A6
0x18001baea  mov     rcx, rbx
0x18001baed  call    sqlite3DbNNFreeNN
0x18001baf2  jmp     loc_18001B872
0x18001baf7  call    sqlite3WindowUnlinkFromSelect
0x18001bafc  jmp     loc_18001B9AA
0x18001bb01  mov     rcx, rbx
0x18001bb04  call    sqlite3DbNNFreeNN
0x18001bb09  jmp     loc_18001B8B3
0x18001bb0e  mov     rdx, [rbp+58h]
0x18001bb12  mov     rcx, rbx
0x18001bb15  call    sqlite3DbFree
0x18001bb1a  jmp     loc_18001B8BD
0x18001bb1f  mov     rdx, [rbp+58h]
0x18001bb23  mov     rcx, rbx
0x18001bb26  call    sqlite3ExprListDeleteGeneric
0x18001bb2b  jmp     loc_18001B8C7
0x18001bb30  mov     rcx, rbx
0x18001bb33  call    sqlite3SelectDelete
0x18001bb38  jmp     loc_18001B8F5
0x18001bb3d  mov     rcx, rbx
0x18001bb40  call    sqlite3IdListDelete
0x18001bb45  jmp     loc_18001B90F
0x18001bb4a  mov     rcx, rbx
0x18001bb4d  call    sqlite3ExprDelete
0x18001bb52  jmp     loc_18001B90F
```
