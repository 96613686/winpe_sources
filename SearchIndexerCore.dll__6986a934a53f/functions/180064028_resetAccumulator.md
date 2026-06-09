# resetAccumulator

- ea: `0x180064028`
- end: `0x1800641d3`
- name: `resetAccumulator`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005650`

## callees

- `0x180011bcc`
- `0x180015700`
- `0x1800168c0`
- `0x18005279c`
- `0x180064028`
- `0x18006e790`

## string_xrefs

- `0x1800640d6`: `USE TEMP B-TREE FOR %s(DISTINCT)`
- `0x18006419b`: `USE TEMP B-TREE FOR %s(ORDER BY)`

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
    if ( !*(_DWORD *)(a1 + 48) )
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
            v10 = sqlite3VdbeAddOp4(v5, 118, *((_DWORD *)v6 + 4), 0, 0, v9, -8);
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
          if ( !*((_BYTE *)v6 + 29) && !*(_DWORD *)(a1 + 48) )
            ++*(_WORD *)(v15 + 6);
          sqlite3VdbeAddOp4(v5, 118, *((_DWORD *)v6 + 6), v13 + *v14, 0, v15, -8);
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
0x180064028  push    rbx
0x18006402a  push    rbp
0x18006402b  push    rsi
0x18006402c  push    rdi
0x18006402d  push    r12
0x18006402f  push    r14
0x180064031  push    r15
0x180064033  sub     rsp, 40h
0x180064037  mov     rdi, rcx
0x18006403a  mov     rsi, rdx
0x18006403d  mov     ecx, [rdx+20h]
0x180064040  add     ecx, [rdx+30h]
0x180064043  jz      loc_1800641C4
0x180064049  cmp     dword ptr [rdi+30h], 0
0x18006404d  jnz     loc_1800641C4
0x180064053  mov     r9d, [rdx+0Ch]
0x180064057  xor     r8d, r8d
0x18006405a  mov     r12, [rdi+10h]
0x18006405e  lea     eax, [r9-1]
0x180064062  add     eax, ecx
0x180064064  lea     edx, [r8+4Bh]
0x180064068  mov     rcx, r12
0x18006406b  mov     [rsp+78h+var_58], eax
0x18006406f  call    sqlite3VdbeAddOp3
0x180064074  mov     rbx, [rsi+28h]
0x180064078  xor     ebp, ebp
0x18006407a  cmp     [rsi+30h], ebp
0x18006407d  jle     loc_1800641C4
0x180064083  lea     ecx, [rbp+1]
0x180064086  cmp     dword ptr [rbx+10h], 0
0x18006408a  jl      short loc_18006410B
0x18006408c  mov     rax, [rbx]
0x18006408f  mov     rdx, [rax+20h]
0x180064093  test    rdx, rdx
0x180064096  jz      short loc_1800640F0
0x180064098  cmp     [rdx], ecx
0x18006409a  jnz     short loc_1800640F0
0x18006409c  xor     r9d, r9d
0x18006409f  xor     r8d, r8d
0x1800640a2  mov     rcx, rdi
0x1800640a5  call    sqlite3KeyInfoFromExprList
0x1800640aa  mov     r8d, [rbx+10h]
0x1800640ae  xor     r9d, r9d
0x1800640b1  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x1800640b9  mov     rcx, r12
0x1800640bc  mov     [rsp+78h+var_50], rax
0x1800640c1  mov     [rsp+78h+var_58], 0
0x1800640c9  lea     edx, [r9+76h]
0x1800640cd  call    sqlite3VdbeAddOp4
0x1800640d2  mov     r9, [rbx+8]
0x1800640d6  lea     r8, aUseTempBTreeFo_0; "USE TEMP B-TREE FOR %s(DISTINCT)"
0x1800640dd  mov     [rbx+14h], eax
0x1800640e0  xor     edx, edx
0x1800640e2  mov     rcx, rdi
0x1800640e5  mov     r9, [r9+38h]
0x1800640e9  call    sqlite3VdbeExplain
0x1800640ee  jmp     short loc_180064106
0x1800640f0  lea     rdx, aDistinctAggreg; "DISTINCT aggregates must have exactly o"...
0x1800640f7  mov     rcx, rdi
0x1800640fa  call    sqlite3ErrorMsg
0x1800640ff  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180064106  mov     ecx, 1
0x18006410b  cmp     dword ptr [rbx+18h], 0
0x18006410f  jl      loc_1800641B5
0x180064115  mov     rcx, [rbx]
0x180064118  xor     r14d, r14d
0x18006411b  cmp     [rbx+1Dh], r14b
0x18006411f  setz    r14b
0x180064123  cmp     byte ptr [rbx+1Ch], 0
0x180064127  mov     rax, [rcx+10h]
0x18006412b  mov     r15, [rax+20h]
0x18006412f  jz      short loc_180064138
0x180064131  mov     rax, [rcx+20h]
0x180064135  add     r14d, [rax]
0x180064138  cmp     byte ptr [rbx+1Eh], 0
0x18006413c  jz      short loc_180064145
0x18006413e  mov     rax, [rcx+20h]
0x180064142  add     r14d, [rax]
0x180064145  mov     r9d, r14d
0x180064148  xor     r8d, r8d
0x18006414b  mov     rdx, r15
0x18006414e  mov     rcx, rdi
0x180064151  call    sqlite3KeyInfoFromExprList
0x180064156  cmp     byte ptr [rbx+1Dh], 0
0x18006415a  jnz     short loc_18006416B
0x18006415c  cmp     dword ptr [rdi+30h], 0
0x180064160  jnz     short loc_18006416B
0x180064162  mov     ecx, 1
0x180064167  add     [rax+6], cx
0x18006416b  mov     r9d, [r15]
0x18006416e  mov     edx, 76h ; 'v'
0x180064173  mov     r8d, [rbx+18h]
0x180064177  add     r9d, r14d
0x18006417a  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x180064182  mov     rcx, r12
0x180064185  mov     [rsp+78h+var_50], rax
0x18006418a  mov     [rsp+78h+var_58], 0
0x180064192  call    sqlite3VdbeAddOp4
0x180064197  mov     r9, [rbx+8]
0x18006419b  lea     r8, aUseTempBTreeFo_2; "USE TEMP B-TREE FOR %s(ORDER BY)"
0x1800641a2  xor     edx, edx
0x1800641a4  mov     rcx, rdi
0x1800641a7  mov     r9, [r9+38h]
0x1800641ab  call    sqlite3VdbeExplain
0x1800641b0  mov     ecx, 1
0x1800641b5  add     ebp, ecx
0x1800641b7  add     rbx, 20h ; ' '
0x1800641bb  cmp     ebp, [rsi+30h]
0x1800641be  jl      loc_180064086
0x1800641c4  add     rsp, 40h
0x1800641c8  pop     r15
0x1800641ca  pop     r14
0x1800641cc  pop     r12
0x1800641ce  pop     rdi
0x1800641cf  pop     rsi
0x1800641d0  pop     rbp
0x1800641d1  pop     rbx
0x1800641d2  retn
```
