# BparseParamKeyword

- ea: `0x18000c568`
- end: `0x18000c6f8`
- name: `BparseParamKeyword`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c818`

## callees

- `0x180007220`
- `0x18000b354`
- `0x18000bcf0`
- `0x18000c568`
- `0x180072508`

## string_xrefs

- `0x18000c61f`: `Command parameter: '(' must follow 'min' operator.`
- `0x18000c65d`: `Command parameter: '(' must follow 'max' operator.`
- `0x18000c697`: `Command parameter: '(' must follow 'max_repeat' operator.`

## pseudocode

```c
__int64 __fastcall BparseParamKeyword(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r9d
  int v4; // r10d
  _BYTE *v6; // rdx
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebx
  __int64 v10; // rax
  _BYTE *v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h]

  v3 = *(_DWORD *)(a1 + 8);
  v4 = 0;
  v13 = 0;
  v6 = *(_BYTE **)a1;
  v12 = *(_BYTE **)a1;
  v8 = a1;
  if ( !v3 )
    return 0;
  v9 = 0;
  do
  {
    if ( (unsigned __int8)(*v6 - 97) > 0x19u )
    {
      LOBYTE(a1) = *v6 - 48;
      if ( (unsigned __int8)a1 > 0x2Fu )
        break;
      v10 = 0x87FFFFFE83FFLL;
      if ( !_bittest64(&v10, a1) )
        break;
    }
    ++v6;
    ++v4;
    --v3;
    *(_QWORD *)v8 = v6;
    *(_DWORD *)(v8 + 8) = v3;
    v9 = 1;
  }
  while ( v3 );
  LODWORD(v13) = v4;
  if ( !v9 )
    return 0;
  if ( (unsigned int)BcmpAARtoStr(&v12, "min") )
  {
    *(_DWORD *)(a2 + 4) = 2;
    v9 = BeatDelimiter(v8, "(");
    if ( !v9 )
      WriteDbgTraceErrorGpd("BparseParamKeyword", "Command parameter: '(' must follow 'min' operator.");
  }
  else if ( (unsigned int)BcmpAARtoStr(&v12, "max") )
  {
    *(_DWORD *)(a2 + 4) = 3;
    v9 = BeatDelimiter(v8, "(");
    if ( !v9 )
      WriteDbgTraceErrorGpd("BparseParamKeyword", "Command parameter: '(' must follow 'max' operator.");
  }
  else if ( (unsigned int)BcmpAARtoStr(&v12, "max_repeat") )
  {
    *(_DWORD *)(a2 + 4) = 9;
    v9 = BeatDelimiter(v8, "(");
    if ( !v9 )
      WriteDbgTraceErrorGpd("BparseParamKeyword", "Command parameter: '(' must follow 'max_repeat' operator.");
  }
  else if ( (unsigned int)BcmpAARtoStr(&v12, "MOD") )
  {
    *(_DWORD *)(a2 + 4) = 8;
  }
  else
  {
    *(_DWORD *)(a2 + 4) = 1;
    return (unsigned int)BparseConstant(&v12, a2, 57, a3);
  }
  return v9;
}

```

## disassembly

```asm
0x18000c568  push    rbx
0x18000c56a  push    rbp
0x18000c56b  push    rsi
0x18000c56c  push    rdi
0x18000c56d  sub     rsp, 38h
0x18000c571  mov     r9d, [rcx+8]
0x18000c575  xor     r10d, r10d
0x18000c578  mov     [rsp+58h+var_30], 0
0x18000c581  mov     rdi, rdx
0x18000c584  mov     rdx, [rcx]
0x18000c587  mov     rbp, r8
0x18000c58a  mov     [rsp+58h+var_38], rdx
0x18000c58f  mov     rsi, rcx
0x18000c592  mov     dword ptr [rsp+58h+var_30], r10d
0x18000c597  test    r9d, r9d
0x18000c59a  jz      loc_18000C6ED
0x18000c5a0  xor     ebx, ebx
0x18000c5a2  mov     cl, [rdx]
0x18000c5a4  lea     eax, [rcx-61h]
0x18000c5a7  cmp     al, 19h
0x18000c5a9  jbe     short loc_18000C5C3
0x18000c5ab  sub     cl, 30h ; '0'
0x18000c5ae  cmp     cl, 2Fh ; '/'
0x18000c5b1  ja      short loc_18000C5DD
0x18000c5b3  mov     rax, 87FFFFFE83FFh
0x18000c5bd  bt      rax, rcx
0x18000c5c1  jnb     short loc_18000C5DD
0x18000c5c3  inc     rdx
0x18000c5c6  inc     r10d
0x18000c5c9  dec     r9d
0x18000c5cc  mov     [rsi], rdx
0x18000c5cf  mov     [rsi+8], r9d
0x18000c5d3  mov     ebx, 1
0x18000c5d8  test    r9d, r9d
0x18000c5db  jnz     short loc_18000C5A2
0x18000c5dd  mov     dword ptr [rsp+58h+var_30], r10d
0x18000c5e2  test    ebx, ebx
0x18000c5e4  jz      loc_18000C6ED
0x18000c5ea  lea     rdx, aMin; "min"
0x18000c5f1  lea     rcx, [rsp+58h+var_38]
0x18000c5f6  call    BcmpAARtoStr
0x18000c5fb  test    eax, eax
0x18000c5fd  jz      short loc_18000C628
0x18000c5ff  lea     rdx, asc_18007C82C; "("
0x18000c606  mov     dword ptr [rdi+4], 2
0x18000c60d  mov     rcx, rsi
0x18000c610  call    BeatDelimiter
0x18000c615  mov     ebx, eax
0x18000c617  test    eax, eax
0x18000c619  jnz     loc_18000C6E9
0x18000c61f  lea     rdx, aCommandParamet_10; "Command parameter: '(' must follow 'min"...
0x18000c626  jmp     short loc_18000C69E
0x18000c628  lea     rdx, aMax; "max"
0x18000c62f  lea     rcx, [rsp+58h+var_38]
0x18000c634  call    BcmpAARtoStr
0x18000c639  test    eax, eax
0x18000c63b  jz      short loc_18000C666
0x18000c63d  lea     rdx, asc_18007C82C; "("
0x18000c644  mov     dword ptr [rdi+4], 3
0x18000c64b  mov     rcx, rsi
0x18000c64e  call    BeatDelimiter
0x18000c653  mov     ebx, eax
0x18000c655  test    eax, eax
0x18000c657  jnz     loc_18000C6E9
0x18000c65d  lea     rdx, aCommandParamet_12; "Command parameter: '(' must follow 'max"...
0x18000c664  jmp     short loc_18000C69E
0x18000c666  lea     rdx, aMaxRepeat; "max_repeat"
0x18000c66d  lea     rcx, [rsp+58h+var_38]
0x18000c672  call    BcmpAARtoStr
0x18000c677  test    eax, eax
0x18000c679  jz      short loc_18000C6AC
0x18000c67b  lea     rdx, asc_18007C82C; "("
0x18000c682  mov     dword ptr [rdi+4], 9
0x18000c689  mov     rcx, rsi
0x18000c68c  call    BeatDelimiter
0x18000c691  mov     ebx, eax
0x18000c693  test    eax, eax
0x18000c695  jnz     short loc_18000C6E9
0x18000c697  lea     rdx, aCommandParamet_8; "Command parameter: '(' must follow 'max"...
0x18000c69e  lea     rcx, aBparseparamkey; "BparseParamKeyword"
0x18000c6a5  call    WriteDbgTraceErrorGpd
0x18000c6aa  jmp     short loc_18000C6E9
0x18000c6ac  lea     rdx, aMod; "MOD"
0x18000c6b3  lea     rcx, [rsp+58h+var_38]
0x18000c6b8  call    BcmpAARtoStr
0x18000c6bd  test    eax, eax
0x18000c6bf  jz      short loc_18000C6CA
0x18000c6c1  mov     dword ptr [rdi+4], 8
0x18000c6c8  jmp     short loc_18000C6E9
0x18000c6ca  mov     r9, rbp
0x18000c6cd  mov     dword ptr [rdi+4], 1
0x18000c6d4  mov     r8d, 39h ; '9'
0x18000c6da  lea     rcx, [rsp+58h+var_38]
0x18000c6df  mov     rdx, rdi
0x18000c6e2  call    BparseConstant
0x18000c6e7  mov     ebx, eax
0x18000c6e9  mov     eax, ebx
0x18000c6eb  jmp     short loc_18000C6EF
0x18000c6ed  xor     eax, eax
0x18000c6ef  add     rsp, 38h
0x18000c6f3  pop     rdi
0x18000c6f4  pop     rsi
0x18000c6f5  pop     rbp
0x18000c6f6  pop     rbx
0x18000c6f7  retn
```
