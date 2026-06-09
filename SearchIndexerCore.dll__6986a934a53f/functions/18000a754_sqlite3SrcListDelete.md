# sqlite3SrcListDelete

- ea: `0x18000a754`
- end: `0x18000a94d`
- name: `sqlite3SrcListDelete`
- size: `505`
- prototype: ``
- caller_count: `21`
- callee_count: `10`
- tags: ``

## callers

- `0x180001214`
- `0x18000213c`
- `0x180008c0c`
- `0x18000a954`
- `0x1800142d0`
- `0x18001d1c8`
- `0x18004a49c`
- `0x1800504a8`
- `0x18005851c`
- `0x18005d15c`
- `0x18006af8c`
- `0x180072cf0`
- `0x180073c34`
- `0x1800746ec`
- `0x18007498c`
- `0x180074d48`
- `0x180076a98`
- `0x18008d5b0`
- `0x18008f450`
- `0x18008fcd0`
- `0x1800923ec`

## callees

- `0x18000a754`
- `0x18001b818`
- `0x18001bb60`
- `0x18001bc40`
- `0x180025770`
- `0x180041d10`
- `0x180041eb0`
- `0x1800516e4`
- `0x18005a258`
- `0x180077180`

## pseudocode

```c
__int64 __fastcall sqlite3SrcListDelete(_QWORD *a1, int *a2)
{
  int v2; // ebp
  _DWORD *v3; // rsi
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  bool v10; // zf
  __int64 *v11; // rdx
  __int64 v12; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    v2 = 0;
    v3 = a2 + 2;
    if ( *a2 > 0 )
    {
      while ( 1 )
      {
        v6 = *((_QWORD *)v3 + 1);
        if ( v6 )
          sqlite3DbNNFreeNN(a1, v6);
        v7 = (_QWORD *)*((_QWORD *)v3 + 2);
        if ( !v7 )
          goto LABEL_9;
        if ( (unsigned __int64)v7 >= a1[62] )
          break;
        if ( (unsigned __int64)v7 < a1[60] )
        {
          if ( (unsigned __int64)v7 < a1[61] )
            break;
          *v7 = a1[57];
          a1[57] = v7;
        }
        else
        {
          *v7 = a1[59];
          a1[59] = v7;
        }
LABEL_9:
        v8 = *((_QWORD *)v3 + 3);
        if ( v8 )
          sqlite3DbNNFreeNN(a1, v8);
        if ( (v3[16] & 2) != 0 )
          sqlite3DbFree(a1, *((_QWORD *)v3 + 11));
        if ( (v3[16] & 4) != 0 )
          sqlite3ExprListDeleteGeneric(a1, *((_QWORD *)v3 + 11));
        v9 = *((_QWORD *)v3 + 4);
        if ( v9 )
        {
          if ( a1[97] || (v10 = *(_DWORD *)(v9 + 44) == 1, --*(_DWORD *)(v9 + 44), v10) )
            deleteTable((__int64)a1, v9);
        }
        v11 = (__int64 *)*((_QWORD *)v3 + 5);
        if ( v11 )
          sqlite3SelectDelete(a1, v11);
        v12 = *((_QWORD *)v3 + 9);
        if ( (v3[16] & 0x400) != 0 )
        {
          sqlite3IdListDelete(a1, v12);
        }
        else if ( v12 )
        {
          sqlite3ExprDelete(a1, v12);
        }
        ++v2;
        v3 += 26;
        if ( v2 >= *a2 )
          goto LABEL_24;
      }
      if ( a1[97] )
        measureAllocationSize(a1, *((_QWORD *)v3 + 2));
      else
        sqlite3_free(v7);
      goto LABEL_9;
    }
LABEL_24:
    if ( (unsigned __int64)a2 < a1[62] )
    {
      if ( (unsigned __int64)a2 >= a1[60] )
      {
        result = a1[59];
        *(_QWORD *)a2 = result;
        a1[59] = a2;
        return result;
      }
      if ( (unsigned __int64)a2 >= a1[61] )
      {
        result = a1[57];
        *(_QWORD *)a2 = result;
        a1[57] = a2;
        return result;
      }
    }
    if ( a1[97] )
      return measureAllocationSize(a1, a2);
    else
      return sqlite3_free(a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a754  test    rdx, rdx
0x18000a757  jz      locret_18000A85C
0x18000a75d  push    rbx
0x18000a75e  push    rbp
0x18000a75f  push    rsi
0x18000a760  push    rdi
0x18000a761  sub     rsp, 28h
0x18000a765  xor     ebp, ebp
0x18000a767  lea     rsi, [rdx+8]
0x18000a76b  mov     rdi, rdx
0x18000a76e  mov     rbx, rcx
0x18000a771  cmp     [rdx], ebp
0x18000a773  jle     loc_18000A831
0x18000a779  mov     rdx, [rsi+8]
0x18000a77d  test    rdx, rdx
0x18000a780  jnz     loc_18000A8EA
0x18000a786  mov     rcx, [rsi+10h]
0x18000a78a  test    rcx, rcx
0x18000a78d  jz      short loc_18000A7BA
0x18000a78f  cmp     rcx, [rbx+1F0h]
0x18000a796  jnb     loc_18000A8AF
0x18000a79c  cmp     rcx, [rbx+1E0h]
0x18000a7a3  jb      loc_18000A879
0x18000a7a9  mov     rax, [rbx+1D8h]
0x18000a7b0  mov     [rcx], rax
0x18000a7b3  mov     [rbx+1D8h], rcx
0x18000a7ba  mov     rdx, [rsi+18h]
0x18000a7be  test    rdx, rdx
0x18000a7c1  jnz     loc_18000A8F7
0x18000a7c7  test    byte ptr [rsi+40h], 2
0x18000a7cb  jnz     loc_18000A904
0x18000a7d1  test    byte ptr [rsi+40h], 4
0x18000a7d5  jnz     loc_18000A915
0x18000a7db  mov     rdx, [rsi+20h]
0x18000a7df  test    rdx, rdx
0x18000a7e2  jz      short loc_18000A7FC
0x18000a7e4  cmp     qword ptr [rbx+308h], 0
0x18000a7ec  jnz     loc_18000A8D3
0x18000a7f2  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x18000a7f6  jz      loc_18000A8D3
0x18000a7fc  mov     rdx, [rsi+28h]
0x18000a800  test    rdx, rdx
0x18000a803  jnz     loc_18000A926
0x18000a809  test    dword ptr [rsi+40h], 400h
0x18000a810  mov     rdx, [rsi+48h]
0x18000a814  jnz     loc_18000A933
0x18000a81a  test    rdx, rdx
0x18000a81d  jnz     loc_18000A940
0x18000a823  inc     ebp
0x18000a825  add     rsi, 68h ; 'h'
0x18000a829  cmp     ebp, [rdi]
0x18000a82b  jl      loc_18000A779
0x18000a831  cmp     rdi, [rbx+1F0h]
0x18000a838  jnb     short loc_18000A898
0x18000a83a  cmp     rdi, [rbx+1E0h]
0x18000a841  jb      short loc_18000A85D
0x18000a843  mov     rax, [rbx+1D8h]
0x18000a84a  mov     [rdi], rax
0x18000a84d  mov     [rbx+1D8h], rdi
0x18000a854  add     rsp, 28h
0x18000a858  pop     rdi
0x18000a859  pop     rsi
0x18000a85a  pop     rbp
0x18000a85b  pop     rbx
0x18000a85c  retn
0x18000a85d  cmp     rdi, [rbx+1E8h]
0x18000a864  jb      short loc_18000A898
0x18000a866  mov     rax, [rbx+1C8h]
0x18000a86d  mov     [rdi], rax
0x18000a870  mov     [rbx+1C8h], rdi
0x18000a877  jmp     short loc_18000A854
0x18000a879  cmp     rcx, [rbx+1E8h]
0x18000a880  jb      short loc_18000A8AF
0x18000a882  mov     rax, [rbx+1C8h]
0x18000a889  mov     [rcx], rax
0x18000a88c  mov     [rbx+1C8h], rcx
0x18000a893  jmp     loc_18000A7BA
0x18000a898  cmp     qword ptr [rbx+308h], 0
0x18000a8a0  jz      short loc_18000A8C9
0x18000a8a2  mov     rdx, rdi
0x18000a8a5  mov     rcx, rbx
0x18000a8a8  call    measureAllocationSize
0x18000a8ad  jmp     short loc_18000A854
0x18000a8af  cmp     qword ptr [rbx+308h], 0
0x18000a8b7  jz      short loc_18000A8E0
0x18000a8b9  mov     rdx, rcx
0x18000a8bc  mov     rcx, rbx
0x18000a8bf  call    measureAllocationSize
0x18000a8c4  jmp     loc_18000A7BA
0x18000a8c9  mov     rcx, rdi
0x18000a8cc  call    sqlite3_free
0x18000a8d1  jmp     short loc_18000A854
0x18000a8d3  mov     rcx, rbx
0x18000a8d6  call    deleteTable
0x18000a8db  jmp     loc_18000A7FC
0x18000a8e0  call    sqlite3_free
0x18000a8e5  jmp     loc_18000A7BA
0x18000a8ea  mov     rcx, rbx
0x18000a8ed  call    sqlite3DbNNFreeNN
0x18000a8f2  jmp     loc_18000A786
0x18000a8f7  mov     rcx, rbx
0x18000a8fa  call    sqlite3DbNNFreeNN
0x18000a8ff  jmp     loc_18000A7C7
0x18000a904  mov     rdx, [rsi+58h]
0x18000a908  mov     rcx, rbx
0x18000a90b  call    sqlite3DbFree
0x18000a910  jmp     loc_18000A7D1
0x18000a915  mov     rdx, [rsi+58h]
0x18000a919  mov     rcx, rbx
0x18000a91c  call    sqlite3ExprListDeleteGeneric
0x18000a921  jmp     loc_18000A7DB
0x18000a926  mov     rcx, rbx
0x18000a929  call    sqlite3SelectDelete
0x18000a92e  jmp     loc_18000A809
0x18000a933  mov     rcx, rbx
0x18000a936  call    sqlite3IdListDelete
0x18000a93b  jmp     loc_18000A823
0x18000a940  mov     rcx, rbx
0x18000a943  call    sqlite3ExprDelete
0x18000a948  jmp     loc_18000A823
```
