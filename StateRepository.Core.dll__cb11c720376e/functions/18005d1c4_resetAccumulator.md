# resetAccumulator

- ea: `0x18005d1c4`
- end: `0x18005d36f`
- name: `resetAccumulator`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180037194`

## callees

- `0x1800119e0`
- `0x180011d80`
- `0x180011fdc`
- `0x1800443c8`
- `0x18005d1c4`
- `0x180060ce8`

## string_xrefs

- `0x18005d272`: `USE TEMP B-TREE FOR %s(DISTINCT)`
- `0x18005d337`: `USE TEMP B-TREE FOR %s(ORDER BY)`

## pseudocode

```c
void __fastcall resetAccumulator(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // r12
  __int64 *v6; // rbx
  int i; // ebp
  _DWORD *v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // r14d
  _DWORD *v14; // r15
  __int64 v15; // rax

  v4 = *(_DWORD *)(a2 + 48) + *(_DWORD *)(a2 + 32);
  if ( v4 )
  {
    if ( !*(_DWORD *)(a1 + 52) )
    {
      v5 = *(_QWORD *)(a1 + 16);
      sqlite3VdbeAddOp3(v5, 75, 0, *(_DWORD *)(a2 + 12), v4 + *(_DWORD *)(a2 + 12) - 1);
      v6 = *(__int64 **)(a2 + 40);
      for ( i = 0; i < *(_DWORD *)(a2 + 48); v6 += 4 )
      {
        if ( *((int *)v6 + 4) >= 0 )
        {
          v8 = *(_DWORD **)(*v6 + 32);
          if ( v8 && *v8 == 1 )
          {
            v9 = sqlite3KeyInfoFromExprList(a1, v8, 0, 0);
            v10 = sqlite3VdbeAddOp4(v5, 117, *((_DWORD *)v6 + 4), 0, 0, v9, -8);
            v11 = v6[1];
            *((_DWORD *)v6 + 5) = v10;
            sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s(DISTINCT)", *(const char **)(v11 + 56));
          }
          else
          {
            sqlite3ErrorMsg(a1, "DISTINCT aggregates must have exactly one argument");
            *((_DWORD *)v6 + 4) = -1;
          }
        }
        if ( *((int *)v6 + 6) >= 0 )
        {
          v12 = *v6;
          v13 = *((_BYTE *)v6 + 29) == 0;
          v14 = *(_DWORD **)(*(_QWORD *)(*v6 + 16) + 32LL);
          if ( *((_BYTE *)v6 + 28) )
            v13 += **(_DWORD **)(v12 + 32);
          if ( *((_BYTE *)v6 + 30) )
            v13 += **(_DWORD **)(v12 + 32);
          v15 = sqlite3KeyInfoFromExprList(a1, v14, 0, v13);
          if ( !*((_BYTE *)v6 + 29) && !*(_DWORD *)(a1 + 52) )
            ++*(_WORD *)(v15 + 6);
          sqlite3VdbeAddOp4(v5, 117, *((_DWORD *)v6 + 6), v13 + *v14, 0, v15, -8);
          sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s(ORDER BY)", *(const char **)(v6[1] + 56));
        }
        ++i;
      }
    }
  }
}

```

## disassembly

```asm
0x18005d1c4  push    rbx
0x18005d1c6  push    rbp
0x18005d1c7  push    rsi
0x18005d1c8  push    rdi
0x18005d1c9  push    r12
0x18005d1cb  push    r14
0x18005d1cd  push    r15
0x18005d1cf  sub     rsp, 40h
0x18005d1d3  mov     rdi, rcx
0x18005d1d6  mov     rsi, rdx
0x18005d1d9  mov     ecx, [rdx+20h]
0x18005d1dc  add     ecx, [rdx+30h]
0x18005d1df  jz      loc_18005D360
0x18005d1e5  cmp     dword ptr [rdi+34h], 0
0x18005d1e9  jnz     loc_18005D360
0x18005d1ef  mov     r9d, [rdx+0Ch]
0x18005d1f3  xor     r8d, r8d
0x18005d1f6  mov     r12, [rdi+10h]
0x18005d1fa  lea     eax, [r9-1]
0x18005d1fe  add     eax, ecx
0x18005d200  lea     edx, [r8+4Bh]
0x18005d204  mov     rcx, r12
0x18005d207  mov     [rsp+78h+var_58], eax
0x18005d20b  call    sqlite3VdbeAddOp3
0x18005d210  mov     rbx, [rsi+28h]
0x18005d214  xor     ebp, ebp
0x18005d216  cmp     [rsi+30h], ebp
0x18005d219  jle     loc_18005D360
0x18005d21f  lea     ecx, [rbp+1]
0x18005d222  cmp     dword ptr [rbx+10h], 0
0x18005d226  jl      short loc_18005D2A7
0x18005d228  mov     rax, [rbx]
0x18005d22b  mov     rdx, [rax+20h]
0x18005d22f  test    rdx, rdx
0x18005d232  jz      short loc_18005D28C
0x18005d234  cmp     [rdx], ecx
0x18005d236  jnz     short loc_18005D28C
0x18005d238  xor     r9d, r9d
0x18005d23b  xor     r8d, r8d
0x18005d23e  mov     rcx, rdi
0x18005d241  call    sqlite3KeyInfoFromExprList
0x18005d246  mov     r8d, [rbx+10h]
0x18005d24a  xor     r9d, r9d
0x18005d24d  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x18005d255  mov     rcx, r12
0x18005d258  mov     [rsp+78h+var_50], rax
0x18005d25d  mov     [rsp+78h+var_58], 0
0x18005d265  lea     edx, [r9+75h]
0x18005d269  call    sqlite3VdbeAddOp4
0x18005d26e  mov     r9, [rbx+8]
0x18005d272  lea     r8, aUseTempBTreeFo_0; "USE TEMP B-TREE FOR %s(DISTINCT)"
0x18005d279  mov     [rbx+14h], eax
0x18005d27c  xor     edx, edx
0x18005d27e  mov     rcx, rdi
0x18005d281  mov     r9, [r9+38h]
0x18005d285  call    sqlite3VdbeExplain
0x18005d28a  jmp     short loc_18005D2A2
0x18005d28c  lea     rdx, aDistinctAggreg; "DISTINCT aggregates must have exactly o"...
0x18005d293  mov     rcx, rdi
0x18005d296  call    sqlite3ErrorMsg
0x18005d29b  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18005d2a2  mov     ecx, 1
0x18005d2a7  cmp     dword ptr [rbx+18h], 0
0x18005d2ab  jl      loc_18005D351
0x18005d2b1  mov     rcx, [rbx]
0x18005d2b4  xor     r14d, r14d
0x18005d2b7  cmp     [rbx+1Dh], r14b
0x18005d2bb  setz    r14b
0x18005d2bf  cmp     byte ptr [rbx+1Ch], 0
0x18005d2c3  mov     rax, [rcx+10h]
0x18005d2c7  mov     r15, [rax+20h]
0x18005d2cb  jz      short loc_18005D2D4
0x18005d2cd  mov     rax, [rcx+20h]
0x18005d2d1  add     r14d, [rax]
0x18005d2d4  cmp     byte ptr [rbx+1Eh], 0
0x18005d2d8  jz      short loc_18005D2E1
0x18005d2da  mov     rax, [rcx+20h]
0x18005d2de  add     r14d, [rax]
0x18005d2e1  mov     r9d, r14d
0x18005d2e4  xor     r8d, r8d
0x18005d2e7  mov     rdx, r15
0x18005d2ea  mov     rcx, rdi
0x18005d2ed  call    sqlite3KeyInfoFromExprList
0x18005d2f2  cmp     byte ptr [rbx+1Dh], 0
0x18005d2f6  jnz     short loc_18005D307
0x18005d2f8  cmp     dword ptr [rdi+34h], 0
0x18005d2fc  jnz     short loc_18005D307
0x18005d2fe  mov     ecx, 1
0x18005d303  add     [rax+6], cx
0x18005d307  mov     r9d, [r15]
0x18005d30a  mov     edx, 75h ; 'u'
0x18005d30f  mov     r8d, [rbx+18h]
0x18005d313  add     r9d, r14d
0x18005d316  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x18005d31e  mov     rcx, r12
0x18005d321  mov     [rsp+78h+var_50], rax
0x18005d326  mov     [rsp+78h+var_58], 0
0x18005d32e  call    sqlite3VdbeAddOp4
0x18005d333  mov     r9, [rbx+8]
0x18005d337  lea     r8, aUseTempBTreeFo_2; "USE TEMP B-TREE FOR %s(ORDER BY)"
0x18005d33e  xor     edx, edx
0x18005d340  mov     rcx, rdi
0x18005d343  mov     r9, [r9+38h]
0x18005d347  call    sqlite3VdbeExplain
0x18005d34c  mov     ecx, 1
0x18005d351  add     ebp, ecx
0x18005d353  add     rbx, 20h ; ' '
0x18005d357  cmp     ebp, [rsi+30h]
0x18005d35a  jl      loc_18005D222
0x18005d360  add     rsp, 40h
0x18005d364  pop     r15
0x18005d366  pop     r14
0x18005d368  pop     r12
0x18005d36a  pop     rdi
0x18005d36b  pop     rsi
0x18005d36c  pop     rbp
0x18005d36d  pop     rbx
0x18005d36e  retn
```
