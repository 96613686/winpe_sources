# sqlite3SrcListDelete

- ea: `0x18000ca30`
- end: `0x18000cb5b`
- name: `sqlite3SrcListDelete`
- size: `299`
- prototype: ``
- caller_count: `25`
- callee_count: `8`
- tags: ``

## callers

- `0x180003128`
- `0x18000c454`
- `0x18000c850`
- `0x18000fe40`
- `0x1800167c0`
- `0x180017fac`
- `0x1800189c8`
- `0x180019e50`
- `0x18001c6f8`
- `0x180031b38`
- `0x180059ff8`
- `0x18005dae0`
- `0x18005dd88`
- `0x18005fae0`
- `0x18006052c`
- `0x18006cc50`
- `0x18007e240`
- `0x18007ff60`
- `0x180080120`
- `0x1800809a0`
- `0x180080c08`
- `0x1800830cc`
- `0x1800832c0`
- `0x1800834e0`
- `0x180087768`

## callees

- `0x18000a9e0`
- `0x18000c850`
- `0x18000c930`
- `0x18000c950`
- `0x18000ca30`
- `0x18000cbb8`
- `0x18004660c`
- `0x18005fbb8`

## pseudocode

```c
__int64 __fastcall sqlite3SrcListDelete(__int64 a1, _DWORD *a2)
{
  int v2; // r14d
  _DWORD *i; // rdi
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rbx

  if ( a2 )
  {
    v2 = 0;
    for ( i = a2 + 2; v2 < *a2; i += 20 )
    {
      if ( *(_QWORD *)i )
        sqlite3DbNNFreeNN(a1, *(_QWORD *)i);
      v6 = *((_QWORD *)i + 1);
      if ( v6 )
        sqlite3DbNNFreeNN(a1, v6);
      if ( (i[7] & 4) != 0 )
      {
        v10 = (_QWORD *)*((_QWORD *)i + 9);
        sqlite3SelectDelete(a1, *v10);
        sqlite3DbFree(a1, v10);
      }
      else if ( (i[7] & 0x10000) == 0 )
      {
        v9 = *((_QWORD *)i + 9);
        if ( v9 )
          sqlite3DbNNFreeNN(a1, v9);
      }
      if ( (i[7] & 2) != 0 )
        sqlite3DbFree(a1, *((_QWORD *)i + 6));
      if ( (i[7] & 8) != 0 )
        sqlite3ExprListDeleteGeneric(a1, *((_QWORD *)i + 6));
      sqlite3DeleteTable(a1, *((_QWORD *)i + 2));
      v7 = *((_QWORD *)i + 8);
      if ( (i[7] & 0x800) != 0 )
      {
        sqlite3IdListDelete(a1, v7);
      }
      else if ( v7 )
      {
        sqlite3ExprDelete(a1, v7);
      }
      ++v2;
    }
    return sqlite3DbNNFreeNN(a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000ca30  test    rdx, rdx
0x18000ca33  jz      locret_18000CAD5
0x18000ca39  push    rbx
0x18000ca3a  push    rbp
0x18000ca3b  push    rsi
0x18000ca3c  push    rdi
0x18000ca3d  push    r14
0x18000ca3f  sub     rsp, 20h
0x18000ca43  xor     r14d, r14d
0x18000ca46  lea     rdi, [rdx+8]
0x18000ca4a  mov     rbp, rdx
0x18000ca4d  mov     rsi, rcx
0x18000ca50  cmp     [rdx], r14d
0x18000ca53  jle     short loc_18000CAC0
0x18000ca55  mov     rdx, [rdi]
0x18000ca58  test    rdx, rdx
0x18000ca5b  jnz     short loc_18000CAD6
0x18000ca5d  mov     rdx, [rdi+8]
0x18000ca61  test    rdx, rdx
0x18000ca64  jnz     loc_18000CAF6
0x18000ca6a  test    byte ptr [rdi+1Ch], 4
0x18000ca6e  jnz     loc_18000CB0D
0x18000ca74  test    dword ptr [rdi+1Ch], 10000h
0x18000ca7b  jz      short loc_18000CAE3
0x18000ca7d  test    byte ptr [rdi+1Ch], 2
0x18000ca81  jnz     loc_18000CB2C
0x18000ca87  test    byte ptr [rdi+1Ch], 8
0x18000ca8b  jnz     loc_18000CB3D
0x18000ca91  mov     rdx, [rdi+10h]
0x18000ca95  mov     rcx, rsi
0x18000ca98  call    sqlite3DeleteTable
0x18000ca9d  test    dword ptr [rdi+1Ch], 800h
0x18000caa4  mov     rdx, [rdi+40h]
0x18000caa8  jnz     loc_18000CB4E
0x18000caae  test    rdx, rdx
0x18000cab1  jnz     short loc_18000CB03
0x18000cab3  inc     r14d
0x18000cab6  add     rdi, 50h ; 'P'
0x18000caba  cmp     r14d, [rbp+0]
0x18000cabe  jl      short loc_18000CA55
0x18000cac0  mov     rdx, rbp
0x18000cac3  mov     rcx, rsi
0x18000cac6  call    sqlite3DbNNFreeNN
0x18000cacb  add     rsp, 20h
0x18000cacf  pop     r14
0x18000cad1  pop     rdi
0x18000cad2  pop     rsi
0x18000cad3  pop     rbp
0x18000cad4  pop     rbx
0x18000cad5  retn
0x18000cad6  mov     rcx, rsi
0x18000cad9  call    sqlite3DbNNFreeNN
0x18000cade  jmp     loc_18000CA5D
0x18000cae3  mov     rdx, [rdi+48h]
0x18000cae7  test    rdx, rdx
0x18000caea  jz      short loc_18000CA7D
0x18000caec  mov     rcx, rsi
0x18000caef  call    sqlite3DbNNFreeNN
0x18000caf4  jmp     short loc_18000CA7D
0x18000caf6  mov     rcx, rsi
0x18000caf9  call    sqlite3DbNNFreeNN
0x18000cafe  jmp     loc_18000CA6A
0x18000cb03  mov     rcx, rsi
0x18000cb06  call    sqlite3ExprDelete
0x18000cb0b  jmp     short loc_18000CAB3
0x18000cb0d  mov     rbx, [rdi+48h]
0x18000cb11  mov     rcx, rsi
0x18000cb14  mov     rdx, [rbx]
0x18000cb17  call    sqlite3SelectDelete
0x18000cb1c  mov     rdx, rbx
0x18000cb1f  mov     rcx, rsi
0x18000cb22  call    sqlite3DbFree
0x18000cb27  jmp     loc_18000CA7D
0x18000cb2c  mov     rdx, [rdi+30h]
0x18000cb30  mov     rcx, rsi
0x18000cb33  call    sqlite3DbFree
0x18000cb38  jmp     loc_18000CA87
0x18000cb3d  mov     rdx, [rdi+30h]
0x18000cb41  mov     rcx, rsi
0x18000cb44  call    sqlite3ExprListDeleteGeneric
0x18000cb49  jmp     loc_18000CA91
0x18000cb4e  mov     rcx, rsi
0x18000cb51  call    sqlite3IdListDelete
0x18000cb56  jmp     loc_18000CAB3
```
