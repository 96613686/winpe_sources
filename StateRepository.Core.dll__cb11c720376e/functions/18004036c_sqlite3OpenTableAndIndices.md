# sqlite3OpenTableAndIndices

- ea: `0x18004036c`
- end: `0x180040534`
- name: `sqlite3OpenTableAndIndices`
- size: `456`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1800167c0`
- `0x1800189c8`
- `0x180019e50`
- `0x180050420`

## callees

- `0x180005c54`
- `0x18000fa9c`
- `0x1800119e0`
- `0x18003ab18`
- `0x18003f6dc`
- `0x18004036c`
- `0x180053ecc`

## pseudocode

```c
__int64 __fastcall sqlite3OpenTableAndIndices(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int8 a4,
        int a5,
        _BYTE *a6,
        int *a7,
        int *a8)
{
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // r10
  unsigned int v14; // r13d
  int v15; // ebx
  int *v16; // rcx
  int v17; // edx
  int v18; // ebx
  bool v19; // zf
  unsigned int v20; // r14d
  __int64 v21; // rbp
  int v23; // r8d
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // [rsp+78h] [rbp+10h]

  if ( *(_BYTE *)(a2 + 63) == 1 )
  {
    *a8 = -999;
    *a7 = -999;
    return 0;
  }
  v11 = sqlite3SchemaToIndex(*(_QWORD *)a1, *(_QWORD *)(a2 + 96));
  v13 = *(_QWORD *)(a1 + 16);
  v14 = v11;
  v15 = a5;
  v26 = v13;
  if ( a5 < 0 )
    v15 = *(_DWORD *)(a1 + 56);
  v16 = a7;
  v17 = v15;
  v18 = v15 + 1;
  v19 = *(_BYTE *)(a2 + 48) >= 0;
  *a7 = v17;
  if ( v19 && (!a6 || *a6) )
  {
    sqlite3OpenTable((_QWORD *)a1, v17, v11, a2, a3);
  }
  else
  {
    if ( *(_BYTE *)(v12 + 111) )
      goto LABEL_6;
    LOBYTE(v12) = a3 == 113;
    sqlite3TableLock(a1, v11, *(unsigned int *)(a2 + 40), v12, *(_QWORD *)a2);
  }
  LODWORD(v13) = v26;
  v16 = a7;
LABEL_6:
  v20 = 0;
  v21 = *(_QWORD *)(a2 + 16);
  *a8 = v18;
  while ( v21 )
  {
    v23 = v18++;
    if ( (*(_DWORD *)(v21 + 100) & 3) == 2 && *(char *)(a2 + 48) < 0 )
    {
      *v16 = v23;
      a4 = 0;
    }
    if ( !a6 || a6[v20 + 1] )
    {
      sqlite3VdbeAddOp3(v13, a3, v23, *(_DWORD *)(v21 + 88), v14);
      sqlite3VdbeSetP4KeyInfo(a1, v21);
      sqlite3VdbeChangeP5(v26, a4, v24, v25);
    }
    v21 = *(_QWORD *)(v21 + 40);
    ++v20;
    v16 = a7;
  }
  if ( v18 > *(_DWORD *)(a1 + 56) )
    *(_DWORD *)(a1 + 56) = v18;
  return v20;
}

```

## disassembly

```asm
0x18004036c  mov     [rsp+arg_0], rbx
0x180040371  mov     [rsp+arg_18], r9b
0x180040376  push    rbp
0x180040377  push    rsi
0x180040378  push    rdi
0x180040379  push    r12
0x18004037b  push    r13
0x18004037d  push    r14
0x18004037f  push    r15
0x180040381  sub     rsp, 30h
0x180040385  cmp     byte ptr [rdx+3Fh], 1
0x180040389  mov     r12d, r8d
0x18004038c  mov     rsi, rdx
0x18004038f  mov     rdi, rcx
0x180040392  jz      loc_18004045F
0x180040398  mov     r9, [rcx]
0x18004039b  mov     rdx, [rdx+60h]
0x18004039f  mov     rcx, r9
0x1800403a2  call    sqlite3SchemaToIndex
0x1800403a7  mov     r10, [rdi+10h]
0x1800403ab  mov     r13d, eax
0x1800403ae  mov     ebx, [rsp+68h+arg_20]
0x1800403b5  mov     [rsp+68h+arg_8], r10
0x1800403ba  test    ebx, ebx
0x1800403bc  js      loc_18004047C
0x1800403c2  mov     rcx, [rsp+68h+arg_30]
0x1800403ca  mov     edx, ebx
0x1800403cc  mov     r15, [rsp+68h+arg_28]
0x1800403d4  inc     ebx
0x1800403d6  test    byte ptr [rsi+30h], 80h
0x1800403da  mov     [rcx], edx
0x1800403dc  jz      loc_180040484
0x1800403e2  cmp     byte ptr [r9+6Fh], 0
0x1800403e7  jz      loc_1800404A8
0x1800403ed  mov     rax, [rsp+68h+arg_38]
0x1800403f5  xor     r14d, r14d
0x1800403f8  mov     rbp, [rsi+10h]
0x1800403fc  mov     [rax], ebx
0x1800403fe  test    rbp, rbp
0x180040401  jnz     short loc_180040424
0x180040403  cmp     ebx, [rdi+38h]
0x180040406  jg      loc_18004052C
0x18004040c  mov     eax, r14d
0x18004040f  mov     rbx, [rsp+68h+arg_0]
0x180040414  add     rsp, 30h
0x180040418  pop     r15
0x18004041a  pop     r14
0x18004041c  pop     r13
0x18004041e  pop     r12
0x180040420  pop     rdi
0x180040421  pop     rsi
0x180040422  pop     rbp
0x180040423  retn
0x180040424  mov     eax, [rbp+64h]
0x180040427  mov     r8d, ebx
0x18004042a  and     al, 3
0x18004042c  inc     ebx
0x18004042e  cmp     al, 2
0x180040430  jz      loc_1800404D9
0x180040436  test    r15, r15
0x180040439  jz      loc_1800404F3
0x18004043f  movsxd  rax, r14d
0x180040442  cmp     byte ptr [rax+r15+1], 0
0x180040448  jnz     loc_1800404F3
0x18004044e  mov     rbp, [rbp+28h]
0x180040452  inc     r14d
0x180040455  mov     rcx, [rsp+68h+arg_30]
0x18004045d  jmp     short loc_1800403FE
0x18004045f  mov     rax, [rsp+68h+arg_38]
0x180040467  mov     ecx, 0FFFFFC19h
0x18004046c  mov     [rax], ecx
0x18004046e  mov     rax, [rsp+68h+arg_30]
0x180040476  mov     [rax], ecx
0x180040478  xor     eax, eax
0x18004047a  jmp     short loc_18004040F
0x18004047c  mov     ebx, [rdi+38h]
0x18004047f  jmp     loc_1800403C2
0x180040484  test    r15, r15
0x180040487  jz      short loc_180040493
0x180040489  cmp     byte ptr [r15], 0
0x18004048d  jz      loc_1800403E2
0x180040493  mov     r9, rsi
0x180040496  mov     dword ptr [rsp+68h+var_48], r12d
0x18004049b  mov     r8d, r13d
0x18004049e  mov     rcx, rdi
0x1800404a1  call    sqlite3OpenTable
0x1800404a6  jmp     short loc_1800404C7
0x1800404a8  mov     rax, [rsi]
0x1800404ab  cmp     r12d, 71h ; 'q'
0x1800404af  mov     r8d, [rsi+28h]
0x1800404b3  mov     edx, r13d
0x1800404b6  setz    r9b
0x1800404ba  mov     [rsp+68h+var_48], rax
0x1800404bf  mov     rcx, rdi
0x1800404c2  call    sqlite3TableLock
0x1800404c7  mov     r10, [rsp+68h+arg_8]
0x1800404cc  mov     rcx, [rsp+68h+arg_30]
0x1800404d4  jmp     loc_1800403ED
0x1800404d9  test    byte ptr [rsi+30h], 80h
0x1800404dd  jz      loc_180040436
0x1800404e3  mov     [rcx], r8d
0x1800404e6  mov     [rsp+68h+arg_18], 0
0x1800404ee  jmp     loc_180040436
0x1800404f3  mov     r9d, [rbp+58h]
0x1800404f7  mov     edx, r12d
0x1800404fa  mov     rcx, r10
0x1800404fd  mov     dword ptr [rsp+68h+var_48], r13d
0x180040502  call    sqlite3VdbeAddOp3
0x180040507  mov     rdx, rbp
0x18004050a  mov     rcx, rdi
0x18004050d  call    sqlite3VdbeSetP4KeyInfo
0x180040512  mov     r10, [rsp+68h+arg_8]
0x180040517  movzx   edx, [rsp+68h+arg_18]
0x18004051f  mov     rcx, r10
0x180040522  call    sqlite3VdbeChangeP5
0x180040527  jmp     loc_18004044E
0x18004052c  mov     [rdi+38h], ebx
0x18004052f  jmp     loc_18004040C
```
