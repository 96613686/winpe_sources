# resetAccumulator

- ea: `0x18003ea4c`
- end: `0x18003ebf7`
- name: `resetAccumulator`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008860`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x18003b410`
- `0x18003be78`
- `0x18003ea4c`
- `0x18008d4bc`

## string_xrefs

- `0x18003eafa`: `USE TEMP B-TREE FOR %s(DISTINCT)`
- `0x18003ebbf`: `USE TEMP B-TREE FOR %s(ORDER BY)`

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
0x18003ea4c  push    rbx
0x18003ea4e  push    rbp
0x18003ea4f  push    rsi
0x18003ea50  push    rdi
0x18003ea51  push    r12
0x18003ea53  push    r14
0x18003ea55  push    r15
0x18003ea57  sub     rsp, 40h
0x18003ea5b  mov     rdi, rcx
0x18003ea5e  mov     rsi, rdx
0x18003ea61  mov     ecx, [rdx+20h]
0x18003ea64  add     ecx, [rdx+30h]
0x18003ea67  jz      loc_18003EBE8
0x18003ea6d  cmp     dword ptr [rdi+30h], 0
0x18003ea71  jnz     loc_18003EBE8
0x18003ea77  mov     r9d, [rdx+0Ch]
0x18003ea7b  xor     r8d, r8d
0x18003ea7e  mov     r12, [rdi+10h]
0x18003ea82  lea     eax, [r9-1]
0x18003ea86  add     eax, ecx
0x18003ea88  lea     edx, [r8+4Bh]
0x18003ea8c  mov     rcx, r12
0x18003ea8f  mov     [rsp+78h+var_58], eax
0x18003ea93  call    sqlite3VdbeAddOp3
0x18003ea98  mov     rbx, [rsi+28h]
0x18003ea9c  xor     ebp, ebp
0x18003ea9e  cmp     [rsi+30h], ebp
0x18003eaa1  jle     loc_18003EBE8
0x18003eaa7  lea     ecx, [rbp+1]
0x18003eaaa  cmp     dword ptr [rbx+10h], 0
0x18003eaae  jl      short loc_18003EB2F
0x18003eab0  mov     rax, [rbx]
0x18003eab3  mov     rdx, [rax+20h]
0x18003eab7  test    rdx, rdx
0x18003eaba  jz      short loc_18003EB14
0x18003eabc  cmp     [rdx], ecx
0x18003eabe  jnz     short loc_18003EB14
0x18003eac0  xor     r9d, r9d
0x18003eac3  xor     r8d, r8d
0x18003eac6  mov     rcx, rdi
0x18003eac9  call    sqlite3KeyInfoFromExprList
0x18003eace  mov     r8d, [rbx+10h]
0x18003ead2  xor     r9d, r9d
0x18003ead5  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x18003eadd  mov     rcx, r12
0x18003eae0  mov     [rsp+78h+var_50], rax
0x18003eae5  mov     [rsp+78h+var_58], 0
0x18003eaed  lea     edx, [r9+76h]
0x18003eaf1  call    sqlite3VdbeAddOp4
0x18003eaf6  mov     r9, [rbx+8]
0x18003eafa  lea     r8, aUseTempBTreeFo_0; "USE TEMP B-TREE FOR %s(DISTINCT)"
0x18003eb01  mov     [rbx+14h], eax
0x18003eb04  xor     edx, edx
0x18003eb06  mov     rcx, rdi
0x18003eb09  mov     r9, [r9+38h]
0x18003eb0d  call    sqlite3VdbeExplain
0x18003eb12  jmp     short loc_18003EB2A
0x18003eb14  lea     rdx, aDistinctAggreg; "DISTINCT aggregates must have exactly o"...
0x18003eb1b  mov     rcx, rdi
0x18003eb1e  call    sqlite3ErrorMsg
0x18003eb23  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18003eb2a  mov     ecx, 1
0x18003eb2f  cmp     dword ptr [rbx+18h], 0
0x18003eb33  jl      loc_18003EBD9
0x18003eb39  mov     rcx, [rbx]
0x18003eb3c  xor     r14d, r14d
0x18003eb3f  cmp     [rbx+1Dh], r14b
0x18003eb43  setz    r14b
0x18003eb47  cmp     byte ptr [rbx+1Ch], 0
0x18003eb4b  mov     rax, [rcx+10h]
0x18003eb4f  mov     r15, [rax+20h]
0x18003eb53  jz      short loc_18003EB5C
0x18003eb55  mov     rax, [rcx+20h]
0x18003eb59  add     r14d, [rax]
0x18003eb5c  cmp     byte ptr [rbx+1Eh], 0
0x18003eb60  jz      short loc_18003EB69
0x18003eb62  mov     rax, [rcx+20h]
0x18003eb66  add     r14d, [rax]
0x18003eb69  mov     r9d, r14d
0x18003eb6c  xor     r8d, r8d
0x18003eb6f  mov     rdx, r15
0x18003eb72  mov     rcx, rdi
0x18003eb75  call    sqlite3KeyInfoFromExprList
0x18003eb7a  cmp     byte ptr [rbx+1Dh], 0
0x18003eb7e  jnz     short loc_18003EB8F
0x18003eb80  cmp     dword ptr [rdi+30h], 0
0x18003eb84  jnz     short loc_18003EB8F
0x18003eb86  mov     ecx, 1
0x18003eb8b  add     [rax+6], cx
0x18003eb8f  mov     r9d, [r15]
0x18003eb92  mov     edx, 76h ; 'v'
0x18003eb97  mov     r8d, [rbx+18h]
0x18003eb9b  add     r9d, r14d
0x18003eb9e  mov     [rsp+78h+var_48], 0FFFFFFF8h
0x18003eba6  mov     rcx, r12
0x18003eba9  mov     [rsp+78h+var_50], rax
0x18003ebae  mov     [rsp+78h+var_58], 0
0x18003ebb6  call    sqlite3VdbeAddOp4
0x18003ebbb  mov     r9, [rbx+8]
0x18003ebbf  lea     r8, aUseTempBTreeFo_2; "USE TEMP B-TREE FOR %s(ORDER BY)"
0x18003ebc6  xor     edx, edx
0x18003ebc8  mov     rcx, rdi
0x18003ebcb  mov     r9, [r9+38h]
0x18003ebcf  call    sqlite3VdbeExplain
0x18003ebd4  mov     ecx, 1
0x18003ebd9  add     ebp, ecx
0x18003ebdb  add     rbx, 20h ; ' '
0x18003ebdf  cmp     ebp, [rsi+30h]
0x18003ebe2  jl      loc_18003EAAA
0x18003ebe8  add     rsp, 40h
0x18003ebec  pop     r15
0x18003ebee  pop     r14
0x18003ebf0  pop     r12
0x18003ebf2  pop     rdi
0x18003ebf3  pop     rsi
0x18003ebf4  pop     rbp
0x18003ebf5  pop     rbx
0x18003ebf6  retn
```
