# sqlite3VtabCreateModule

- ea: `0x180089a9c`
- end: `0x180089b85`
- name: `sqlite3VtabCreateModule`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18006d1f0`
- `0x18008605c`

## callees

- `0x180005810`
- `0x18000a9e0`
- `0x18000bd90`
- `0x18000c500`
- `0x180064ef0`
- `0x180089a9c`
- `0x180089bc4`
- `0x180089fa8`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall sqlite3VtabCreateModule(__int64 a1, const void *a2, __int64 a3, __int64 a4, __int64 a5)
{
  const void *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // r15
  __int64 v12; // rax
  __int64 v14; // rax
  __int64 v15; // rsi

  if ( a3 )
  {
    v11 = (int)sqlite3Strlen30(a2, a2, a3);
    v12 = sqlite3Malloc(v11 + 49);
    v10 = v12;
    if ( !v12 )
    {
      sqlite3OomFault(a1);
      return 0;
    }
    v9 = (const void *)(v12 + 48);
    memcpy_0((void *)(v12 + 48), a2, (int)v11 + 1);
    *(_QWORD *)(v10 + 32) = a5;
    *(_QWORD *)(v10 + 8) = v9;
    *(_QWORD *)v10 = a3;
    *(_QWORD *)(v10 + 24) = a4;
    *(_QWORD *)(v10 + 40) = 0;
    *(_DWORD *)(v10 + 16) = 1;
  }
  else
  {
    v9 = a2;
    v10 = 0;
  }
  v14 = sqlite3HashInsert(a1 + 552, v9, v10);
  v15 = v14;
  if ( v14 )
  {
    if ( v14 == v10 )
    {
      sqlite3OomFault(a1);
      sqlite3DbFree(a1, v15);
      return 0;
    }
    else
    {
      sqlite3VtabEponymousTableClear(a1, v14);
      sqlite3VtabModuleUnref(a1, v15);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180089a9c  push    rbx
0x180089a9e  push    rbp
0x180089a9f  push    rsi
0x180089aa0  push    rdi
0x180089aa1  push    r12
0x180089aa3  push    r14
0x180089aa5  push    r15
0x180089aa7  sub     rsp, 20h
0x180089aab  mov     r12, r9
0x180089aae  mov     r14, r8
0x180089ab1  mov     rbp, rdx
0x180089ab4  mov     rdi, rcx
0x180089ab7  test    r8, r8
0x180089aba  jnz     short loc_180089AC3
0x180089abc  mov     rsi, rdx
0x180089abf  xor     ebx, ebx
0x180089ac1  jmp     short loc_180089B2A
0x180089ac3  mov     rcx, rbp
0x180089ac6  call    sqlite3Strlen30
0x180089acb  movsxd  r15, eax
0x180089ace  lea     rcx, [r15+31h]
0x180089ad2  call    sqlite3Malloc
0x180089ad7  mov     rbx, rax
0x180089ada  test    rax, rax
0x180089add  jnz     short loc_180089AEE
0x180089adf  mov     rcx, rdi
0x180089ae2  call    sqlite3OomFault
0x180089ae7  xor     eax, eax
0x180089ae9  jmp     loc_180089B76
0x180089aee  lea     rsi, [rax+30h]
0x180089af2  mov     rdx, rbp; Src
0x180089af5  lea     eax, [r15+1]
0x180089af9  mov     rcx, rsi; void *
0x180089afc  movsxd  r8, eax; Size
0x180089aff  call    memcpy_0
0x180089b04  mov     rax, [rsp+58h+arg_20]
0x180089b0c  mov     [rbx+20h], rax
0x180089b10  mov     [rbx+8], rsi
0x180089b14  mov     [rbx], r14
0x180089b17  mov     [rbx+18h], r12
0x180089b1b  mov     qword ptr [rbx+28h], 0
0x180089b23  mov     dword ptr [rbx+10h], 1
0x180089b2a  lea     rcx, [rdi+228h]
0x180089b31  mov     r8, rbx
0x180089b34  mov     rdx, rsi
0x180089b37  call    sqlite3HashInsert
0x180089b3c  mov     rsi, rax
0x180089b3f  test    rax, rax
0x180089b42  jz      short loc_180089B73
0x180089b44  mov     rcx, rdi
0x180089b47  cmp     rax, rbx
0x180089b4a  jnz     short loc_180089B60
0x180089b4c  call    sqlite3OomFault
0x180089b51  mov     rdx, rsi
0x180089b54  mov     rcx, rdi
0x180089b57  call    sqlite3DbFree
0x180089b5c  xor     ebx, ebx
0x180089b5e  jmp     short loc_180089B73
0x180089b60  mov     rdx, rsi
0x180089b63  call    sqlite3VtabEponymousTableClear
0x180089b68  mov     rdx, rsi
0x180089b6b  mov     rcx, rdi
0x180089b6e  call    sqlite3VtabModuleUnref
0x180089b73  mov     rax, rbx
0x180089b76  add     rsp, 20h
0x180089b7a  pop     r15
0x180089b7c  pop     r14
0x180089b7e  pop     r12
0x180089b80  pop     rdi
0x180089b81  pop     rsi
0x180089b82  pop     rbp
0x180089b83  pop     rbx
0x180089b84  retn
```
