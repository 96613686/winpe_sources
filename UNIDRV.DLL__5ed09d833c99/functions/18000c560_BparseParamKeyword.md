# BparseParamKeyword

- ea: `0x18000c560`
- end: `0x18000c6f1`
- name: `BparseParamKeyword`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c814`

## callees

- `0x180007150`
- `0x18000b364`
- `0x18000bce0`
- `0x18000c560`
- `0x18007458c`

## string_xrefs

- `0x18000c617`: `Command parameter: '(' must follow 'min' operator.`
- `0x18000c655`: `Command parameter: '(' must follow 'max' operator.`
- `0x18000c68f`: `Command parameter: '(' must follow 'max_repeat' operator.`

## pseudocode

```c
__int64 __fastcall BparseParamKeyword(unsigned __int64 a1, _DWORD *a2, __int64 a3)
{
  int v3; // r9d
  int v4; // r10d
  const char *v6; // rdx
  __int64 v8; // rsi
  unsigned int v9; // ebx
  __int64 v10; // rax
  const char *v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h]

  v3 = *(_DWORD *)(a1 + 8);
  v4 = 0;
  v13 = 0;
  v6 = *(const char **)a1;
  v12 = *(const char **)a1;
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
  if ( BcmpAARtoStr((__int64)&v12, "min") )
  {
    a2[1] = 2;
    v9 = BeatDelimiter(v8);
    if ( !v9 )
      WriteDbgTraceErrorGpd((__int64)"BparseParamKeyword", "Command parameter: '(' must follow 'min' operator.");
  }
  else if ( BcmpAARtoStr((__int64)&v12, "max") )
  {
    a2[1] = 3;
    v9 = BeatDelimiter(v8);
    if ( !v9 )
      WriteDbgTraceErrorGpd((__int64)"BparseParamKeyword", "Command parameter: '(' must follow 'max' operator.");
  }
  else if ( BcmpAARtoStr((__int64)&v12, "max_repeat") )
  {
    a2[1] = 9;
    v9 = BeatDelimiter(v8);
    if ( !v9 )
      WriteDbgTraceErrorGpd((__int64)"BparseParamKeyword", "Command parameter: '(' must follow 'max_repeat' operator.");
  }
  else if ( BcmpAARtoStr((__int64)&v12, "MOD") )
  {
    a2[1] = 8;
  }
  else
  {
    a2[1] = 1;
    return (unsigned int)BparseConstant(&v12, a2, 57, a3);
  }
  return v9;
}

```

## disassembly

```asm
0x18000c560  push    rbx
0x18000c562  push    rbp
0x18000c563  push    rsi
0x18000c564  push    rdi
0x18000c565  sub     rsp, 38h
0x18000c569  mov     r9d, [rcx+8]
0x18000c56d  xor     r10d, r10d
0x18000c570  mov     [rsp+58h+var_30], 0
0x18000c579  mov     rdi, rdx
0x18000c57c  mov     rdx, [rcx]
0x18000c57f  mov     rbp, r8
0x18000c582  mov     [rsp+58h+var_38], rdx
0x18000c587  mov     rsi, rcx
0x18000c58a  mov     dword ptr [rsp+58h+var_30], r10d
0x18000c58f  test    r9d, r9d
0x18000c592  jz      loc_18000C6E5
0x18000c598  xor     ebx, ebx
0x18000c59a  mov     cl, [rdx]
0x18000c59c  lea     eax, [rcx-61h]
0x18000c59f  cmp     al, 19h
0x18000c5a1  jbe     short loc_18000C5BB
0x18000c5a3  sub     cl, 30h ; '0'
0x18000c5a6  cmp     cl, 2Fh ; '/'
0x18000c5a9  ja      short loc_18000C5D5
0x18000c5ab  mov     rax, 87FFFFFE83FFh
0x18000c5b5  bt      rax, rcx
0x18000c5b9  jnb     short loc_18000C5D5
0x18000c5bb  inc     rdx
0x18000c5be  inc     r10d
0x18000c5c1  dec     r9d
0x18000c5c4  mov     [rsi], rdx
0x18000c5c7  mov     [rsi+8], r9d
0x18000c5cb  mov     ebx, 1
0x18000c5d0  test    r9d, r9d
0x18000c5d3  jnz     short loc_18000C59A
0x18000c5d5  mov     dword ptr [rsp+58h+var_30], r10d
0x18000c5da  test    ebx, ebx
0x18000c5dc  jz      loc_18000C6E5
0x18000c5e2  lea     rdx, aMin; "min"
0x18000c5e9  lea     rcx, [rsp+58h+var_38]
0x18000c5ee  call    BcmpAARtoStr
0x18000c5f3  test    eax, eax
0x18000c5f5  jz      short loc_18000C620
0x18000c5f7  lea     rdx, asc_18007E82C; "("
0x18000c5fe  mov     dword ptr [rdi+4], 2
0x18000c605  mov     rcx, rsi
0x18000c608  call    BeatDelimiter
0x18000c60d  mov     ebx, eax
0x18000c60f  test    eax, eax
0x18000c611  jnz     loc_18000C6E1
0x18000c617  lea     rdx, aCommandParamet_10; "Command parameter: '(' must follow 'min"...
0x18000c61e  jmp     short loc_18000C696
0x18000c620  lea     rdx, aMax; "max"
0x18000c627  lea     rcx, [rsp+58h+var_38]
0x18000c62c  call    BcmpAARtoStr
0x18000c631  test    eax, eax
0x18000c633  jz      short loc_18000C65E
0x18000c635  lea     rdx, asc_18007E82C; "("
0x18000c63c  mov     dword ptr [rdi+4], 3
0x18000c643  mov     rcx, rsi
0x18000c646  call    BeatDelimiter
0x18000c64b  mov     ebx, eax
0x18000c64d  test    eax, eax
0x18000c64f  jnz     loc_18000C6E1
0x18000c655  lea     rdx, aCommandParamet_12; "Command parameter: '(' must follow 'max"...
0x18000c65c  jmp     short loc_18000C696
0x18000c65e  lea     rdx, aMaxRepeat; "max_repeat"
0x18000c665  lea     rcx, [rsp+58h+var_38]
0x18000c66a  call    BcmpAARtoStr
0x18000c66f  test    eax, eax
0x18000c671  jz      short loc_18000C6A4
0x18000c673  lea     rdx, asc_18007E82C; "("
0x18000c67a  mov     dword ptr [rdi+4], 9
0x18000c681  mov     rcx, rsi
0x18000c684  call    BeatDelimiter
0x18000c689  mov     ebx, eax
0x18000c68b  test    eax, eax
0x18000c68d  jnz     short loc_18000C6E1
0x18000c68f  lea     rdx, aCommandParamet_8; "Command parameter: '(' must follow 'max"...
0x18000c696  lea     rcx, aBparseparamkey; "BparseParamKeyword"
0x18000c69d  call    WriteDbgTraceErrorGpd
0x18000c6a2  jmp     short loc_18000C6E1
0x18000c6a4  lea     rdx, aMod; "MOD"
0x18000c6ab  lea     rcx, [rsp+58h+var_38]
0x18000c6b0  call    BcmpAARtoStr
0x18000c6b5  test    eax, eax
0x18000c6b7  jz      short loc_18000C6C2
0x18000c6b9  mov     dword ptr [rdi+4], 8
0x18000c6c0  jmp     short loc_18000C6E1
0x18000c6c2  mov     r9, rbp
0x18000c6c5  mov     dword ptr [rdi+4], 1
0x18000c6cc  mov     r8d, 39h ; '9'
0x18000c6d2  lea     rcx, [rsp+58h+var_38]
0x18000c6d7  mov     rdx, rdi
0x18000c6da  call    BparseConstant
0x18000c6df  mov     ebx, eax
0x18000c6e1  mov     eax, ebx
0x18000c6e3  jmp     short loc_18000C6E7
0x18000c6e5  xor     eax, eax
0x18000c6e7  add     rsp, 38h
0x18000c6eb  pop     rdi
0x18000c6ec  pop     rsi
0x18000c6ed  pop     rbp
0x18000c6ee  pop     rbx
0x18000c6ef  retn
```
