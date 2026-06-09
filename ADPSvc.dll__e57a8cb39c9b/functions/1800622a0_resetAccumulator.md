# resetAccumulator

- ea: `0x1800622a0`
- end: `0x180062468`
- name: `resetAccumulator`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18008b73c`

## callees

- `0x1800622a0`
- `0x180073aec`
- `0x18007fcc4`
- `0x1800923d8`
- `0x1800927e0`
- `0x1800998c0`

## string_xrefs

- `0x180062360`: `USE TEMP B-TREE FOR %s(DISTINCT)`
- `0x18006242c`: `USE TEMP B-TREE FOR %s(ORDER BY)`

## pseudocode

```c
void __fastcall resetAccumulator(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // r12
  int v6; // r15d
  __int64 *i; // rsi
  _DWORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // ebx
  _DWORD *v14; // r13
  __int64 v15; // rdi
  unsigned int v16; // eax

  v4 = *(_DWORD *)(a2 + 48) + *(_DWORD *)(a2 + 32);
  if ( v4 )
  {
    if ( !*(_DWORD *)(a1 + 48) )
    {
      v5 = *(_QWORD *)(a1 + 16);
      sqlite3VdbeAddOp3(v5, 75, 0, *(_DWORD *)(a2 + 12), v4 + *(_DWORD *)(a2 + 12) - 1);
      v6 = 0;
      for ( i = *(__int64 **)(a2 + 40); v6 < *(_DWORD *)(a2 + 48); i += 4 )
      {
        if ( *((int *)i + 4) >= 0 )
        {
          v8 = *(_DWORD **)(*i + 32);
          if ( v8 && *v8 == 1 )
          {
            v9 = sqlite3KeyInfoFromExprList(a1, v8, 0, 0);
            v10 = (unsigned int)sqlite3VdbeAddOp3(v5, 118, *((_DWORD *)i + 4), 0, 0);
            sqlite3VdbeChangeP4(v5, v10, v9, 4294967288LL);
            v11 = i[1];
            *((_DWORD *)i + 5) = v10;
            sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s(DISTINCT)", *(const char **)(v11 + 56));
          }
          else
          {
            sqlite3ErrorMsg(a1, "DISTINCT aggregates must have exactly one argument");
            *((_DWORD *)i + 4) = -1;
          }
        }
        if ( *((int *)i + 6) >= 0 )
        {
          v12 = *i;
          v13 = *((_BYTE *)i + 29) == 0;
          v14 = *(_DWORD **)(*(_QWORD *)(*i + 16) + 32LL);
          if ( *((_BYTE *)i + 28) )
            v13 += **(_DWORD **)(v12 + 32);
          if ( *((_BYTE *)i + 30) )
            v13 += **(_DWORD **)(v12 + 32);
          v15 = sqlite3KeyInfoFromExprList(a1, v14, 0, v13);
          if ( !*((_BYTE *)i + 29) && !*(_DWORD *)(a1 + 48) )
            ++*(_WORD *)(v15 + 6);
          v16 = sqlite3VdbeAddOp3(v5, 118, *((_DWORD *)i + 6), v13 + *v14, 0);
          sqlite3VdbeChangeP4(v5, v16, v15, 4294967288LL);
          sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s(ORDER BY)", *(const char **)(i[1] + 56));
        }
        ++v6;
      }
    }
  }
}

```

## disassembly

```asm
0x1800622a0  push    rbx
0x1800622a2  push    rbp
0x1800622a3  push    rsi
0x1800622a4  push    rdi
0x1800622a5  push    r12
0x1800622a7  push    r13
0x1800622a9  push    r14
0x1800622ab  push    r15
0x1800622ad  sub     rsp, 38h
0x1800622b1  mov     rbp, rcx
0x1800622b4  xor     edi, edi
0x1800622b6  mov     ecx, [rdx+20h]
0x1800622b9  mov     r14, rdx
0x1800622bc  add     ecx, [rdx+30h]
0x1800622bf  jz      loc_180062457
0x1800622c5  cmp     [rbp+30h], edi
0x1800622c8  jnz     loc_180062457
0x1800622ce  mov     r9d, [rdx+0Ch]
0x1800622d2  xor     r8d, r8d
0x1800622d5  mov     r12, [rbp+10h]
0x1800622d9  lea     edx, [rdi+4Bh]
0x1800622dc  lea     eax, [r9-1]
0x1800622e0  add     eax, ecx
0x1800622e2  mov     rcx, r12
0x1800622e5  mov     [rsp+78h+var_58], eax
0x1800622e9  call    sqlite3VdbeAddOp3
0x1800622ee  mov     r15d, edi
0x1800622f1  mov     rsi, [r14+28h]
0x1800622f5  cmp     [r14+30h], edi
0x1800622f9  jle     loc_180062457
0x1800622ff  lea     ecx, [rdi+1]
0x180062302  cmp     [rsi+10h], edi
0x180062305  jl      loc_180062397
0x18006230b  mov     rax, [rsi]
0x18006230e  mov     rdx, [rax+20h]
0x180062312  test    rdx, rdx
0x180062315  jz      short loc_18006237C
0x180062317  cmp     [rdx], ecx
0x180062319  jnz     short loc_18006237C
0x18006231b  xor     r9d, r9d
0x18006231e  xor     r8d, r8d
0x180062321  mov     rcx, rbp
0x180062324  call    sqlite3KeyInfoFromExprList
0x180062329  mov     r8d, [rsi+10h]
0x18006232d  xor     r9d, r9d
0x180062330  mov     rcx, r12
0x180062333  mov     [rsp+78h+var_58], 0
0x18006233b  mov     rdi, rax
0x18006233e  lea     edx, [r9+76h]
0x180062342  call    sqlite3VdbeAddOp3
0x180062347  mov     r9d, 0FFFFFFF8h
0x18006234d  mov     r8, rdi
0x180062350  mov     edx, eax
0x180062352  mov     rcx, r12
0x180062355  mov     ebx, eax
0x180062357  call    sqlite3VdbeChangeP4
0x18006235c  mov     r9, [rsi+8]
0x180062360  lea     r8, aUseTempBTreeFo_0; "USE TEMP B-TREE FOR %s(DISTINCT)"
0x180062367  mov     [rsi+14h], ebx
0x18006236a  xor     edx, edx
0x18006236c  mov     rcx, rbp
0x18006236f  mov     r9, [r9+38h]
0x180062373  call    sqlite3VdbeExplain
0x180062378  xor     edi, edi
0x18006237a  jmp     short loc_180062392
0x18006237c  lea     rdx, aDistinctAggreg; "DISTINCT aggregates must have exactly o"...
0x180062383  mov     rcx, rbp
0x180062386  call    sqlite3ErrorMsg
0x18006238b  mov     dword ptr [rsi+10h], 0FFFFFFFFh
0x180062392  mov     ecx, 1
0x180062397  cmp     [rsi+18h], edi
0x18006239a  jl      loc_180062446
0x1800623a0  cmp     [rsi+1Dh], dil
0x1800623a4  mov     ebx, edi
0x1800623a6  mov     rcx, [rsi]
0x1800623a9  setz    bl
0x1800623ac  mov     rax, [rcx+10h]
0x1800623b0  mov     r13, [rax+20h]
0x1800623b4  cmp     [rsi+1Ch], dil
0x1800623b8  jz      short loc_1800623C0
0x1800623ba  mov     rax, [rcx+20h]
0x1800623be  add     ebx, [rax]
0x1800623c0  cmp     [rsi+1Eh], dil
0x1800623c4  jz      short loc_1800623CC
0x1800623c6  mov     rax, [rcx+20h]
0x1800623ca  add     ebx, [rax]
0x1800623cc  mov     r9d, ebx
0x1800623cf  xor     r8d, r8d
0x1800623d2  mov     rdx, r13
0x1800623d5  mov     rcx, rbp
0x1800623d8  call    sqlite3KeyInfoFromExprList
0x1800623dd  cmp     byte ptr [rsi+1Dh], 0
0x1800623e1  mov     rdi, rax
0x1800623e4  jnz     short loc_1800623F5
0x1800623e6  cmp     dword ptr [rbp+30h], 0
0x1800623ea  jnz     short loc_1800623F5
0x1800623ec  mov     eax, 1
0x1800623f1  add     [rdi+6], ax
0x1800623f5  mov     r9d, [r13+0]
0x1800623f9  mov     edx, 76h ; 'v'
0x1800623fe  mov     r8d, [rsi+18h]
0x180062402  add     r9d, ebx
0x180062405  mov     rcx, r12
0x180062408  mov     [rsp+78h+var_58], 0
0x180062410  call    sqlite3VdbeAddOp3
0x180062415  mov     r9d, 0FFFFFFF8h
0x18006241b  mov     r8, rdi
0x18006241e  mov     edx, eax
0x180062420  mov     rcx, r12
0x180062423  call    sqlite3VdbeChangeP4
0x180062428  mov     r9, [rsi+8]
0x18006242c  lea     r8, aUseTempBTreeFo_2; "USE TEMP B-TREE FOR %s(ORDER BY)"
0x180062433  xor     edx, edx
0x180062435  mov     rcx, rbp
0x180062438  mov     r9, [r9+38h]
0x18006243c  call    sqlite3VdbeExplain
0x180062441  xor     edi, edi
0x180062443  lea     ecx, [rdi+1]
0x180062446  add     r15d, ecx
0x180062449  add     rsi, 20h ; ' '
0x18006244d  cmp     r15d, [r14+30h]
0x180062451  jl      loc_180062302
0x180062457  add     rsp, 38h
0x18006245b  pop     r15
0x18006245d  pop     r14
0x18006245f  pop     r13
0x180062461  pop     r12
0x180062463  pop     rdi
0x180062464  pop     rsi
0x180062465  pop     rbp
0x180062466  pop     rbx
0x180062467  retn
```
