# sqlite3FindTable

- ea: `0x18002817c`
- end: `0x1800283f6`
- name: `sqlite3FindTable`
- size: `634`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: ``

## callers

- `0x180014750`
- `0x180016bf4`
- `0x180027eb0`
- `0x18002d694`
- `0x180039494`
- `0x180052cd0`
- `0x18006d36c`
- `0x180072d70`
- `0x180073910`
- `0x180073c30`
- `0x18007732c`
- `0x180077910`
- `0x180077c74`
- `0x18007b4bc`
- `0x180081db4`
- `0x180089678`
- `0x18008f9d4`
- `0x18008fac0`
- `0x180097f10`

## callees

- `0x18002817c`
- `0x18002b840`
- `0x18002e290`
- `0x1800367a0`
- `0x18003bb08`

## string_xrefs

- `0x1800283cb`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, unsigned __int8 *a2, __int64 a3)
{
  int v6; // edi
  int v7; // ebx
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 v10; // rdi
  unsigned __int8 *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // rdx
  __int64 result; // rax
  __int64 v16; // rcx
  const char *v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // r9
  unsigned int v20; // eax
  _DWORD *v21; // r9
  __int64 v22; // r10
  int v23; // r8d
  __int64 *v24; // rdx
  _BYTE *v25; // r9
  unsigned __int8 *i; // r10
  __int64 v27; // r11
  __int64 v28; // rax
  int v29; // ebx

  if ( a3 )
  {
    v6 = *(_DWORD *)(a1 + 40);
    v7 = 0;
    if ( v6 <= 0 )
    {
LABEL_6:
      if ( v7 >= v6 )
      {
        if ( (unsigned int)sqlite3StrICmp(a3, "main") )
          return 0;
        v7 = 0;
      }
    }
    else
    {
      v8 = *(_QWORD *)(a1 + 32);
      while ( (unsigned int)sqlite3StrICmp(a3, *(_QWORD *)(32LL * (unsigned int)v7 + v8)) )
      {
        if ( ++v7 >= v6 )
          goto LABEL_6;
      }
    }
    v9 = 32LL * v7;
    v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
    if ( v10 || (unsigned int)sqlite3_strnicmp(a2, "sqlite_", 7) )
      return v10;
    v11 = a2 + 7;
    if ( v7 == 1 )
    {
      if ( !(unsigned int)sqlite3StrICmp(v11, "temp_schema") || !(unsigned int)sqlite3StrICmp(v12, "schema") )
        goto LABEL_42;
      v14 = "master";
LABEL_41:
      if ( !(unsigned int)sqlite3StrICmp(v13, v14) )
      {
LABEL_42:
        v17 = "sqlite_temp_master";
        v16 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
        return *(_QWORD *)(findElementWithHash(v16 + 8, v17, 0) + 16);
      }
      return v10;
    }
    if ( (unsigned int)sqlite3StrICmp(v11, "schema") )
      return v10;
    v16 = *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 24);
    goto LABEL_18;
  }
  v18 = *(_QWORD *)(a1 + 32);
  v19 = *(_QWORD *)(v18 + 56) + 8LL;
  if ( *(_QWORD *)(*(_QWORD *)(v18 + 56) + 24LL) )
  {
    v20 = strHash(a2);
    v19 = v22 + 16LL * (v20 % *v21);
    v23 = *(_DWORD *)v19;
  }
  else
  {
    v23 = *(_DWORD *)(*(_QWORD *)(v18 + 56) + 12LL);
  }
  v24 = *(__int64 **)(v19 + 8);
LABEL_23:
  if ( v23 )
  {
    v25 = (_BYTE *)v24[3];
    for ( i = a2; ; ++i )
    {
      v27 = (unsigned __int8)*v25;
      v28 = *i;
      if ( (_DWORD)v27 == (_DWORD)v28 )
      {
        if ( !*v25 )
          goto LABEL_32;
      }
      else if ( *((unsigned __int8 *)qword_1800ADCF0 + v27) != *((unsigned __int8 *)qword_1800ADCF0 + v28) )
      {
        v24 = (__int64 *)*v24;
        --v23;
        goto LABEL_23;
      }
      ++v25;
    }
  }
  v24 = qword_1800C78E8;
LABEL_32:
  result = v24[2];
  if ( !result )
  {
    v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(v18 + 24) + 8LL, a2, 0) + 16);
    if ( v10 )
      return v10;
    v29 = 2;
    if ( *(int *)(a1 + 40) > 2 )
    {
      do
      {
        v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v29 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
        if ( v10 )
          return v10;
      }
      while ( ++v29 < *(_DWORD *)(a1 + 40) );
    }
    if ( (unsigned int)sqlite3_strnicmp(a2, "sqlite_", 7) )
      return v10;
    if ( (unsigned int)sqlite3StrICmp(a2 + 7, "schema") )
    {
      v14 = "temp_schema";
      goto LABEL_41;
    }
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
LABEL_18:
    v17 = "sqlite_master";
    return *(_QWORD *)(findElementWithHash(v16 + 8, v17, 0) + 16);
  }
  return result;
}

```

## disassembly

```asm
0x18002817c  push    rbx
0x18002817e  push    rbp
0x18002817f  push    rsi
0x180028180  push    rdi
0x180028181  push    r14
0x180028183  push    r15
0x180028185  sub     rsp, 28h
0x180028189  mov     r14, r8
0x18002818c  mov     rbp, rdx
0x18002818f  mov     rsi, rcx
0x180028192  test    r8, r8
0x180028195  jz      loc_180028295
0x18002819b  mov     edi, [rcx+28h]
0x18002819e  xor     ebx, ebx
0x1800281a0  test    edi, edi
0x1800281a2  jle     short loc_1800281C4
0x1800281a4  mov     r15, [rcx+20h]
0x1800281a8  mov     edx, ebx
0x1800281aa  mov     rcx, r14
0x1800281ad  shl     rdx, 5
0x1800281b1  mov     rdx, [rdx+r15]
0x1800281b5  call    sqlite3StrICmp
0x1800281ba  test    eax, eax
0x1800281bc  jz      short loc_1800281E1
0x1800281be  inc     ebx
0x1800281c0  cmp     ebx, edi
0x1800281c2  jl      short loc_1800281A8
0x1800281c4  cmp     ebx, edi
0x1800281c6  jl      short loc_1800281E1
0x1800281c8  lea     rdx, aMain; "main"
0x1800281cf  mov     rcx, r14
0x1800281d2  call    sqlite3StrICmp
0x1800281d7  test    eax, eax
0x1800281d9  jnz     loc_180028265
0x1800281df  xor     ebx, ebx
0x1800281e1  mov     rax, [rsi+20h]
0x1800281e5  xor     r8d, r8d
0x1800281e8  movsxd  r14, ebx
0x1800281eb  mov     rdx, rbp
0x1800281ee  shl     r14, 5
0x1800281f2  mov     rcx, [r14+rax+18h]
0x1800281f7  add     rcx, 8
0x1800281fb  call    findElementWithHash
0x180028200  mov     rdi, [rax+10h]
0x180028204  test    rdi, rdi
0x180028207  jnz     loc_1800283E6
0x18002820d  lea     r8d, [rdi+7]
0x180028211  mov     rcx, rbp
0x180028214  lea     rdx, aSqlite_0; "sqlite_"
0x18002821b  call    sqlite3_strnicmp
0x180028220  test    eax, eax
0x180028222  jnz     loc_1800283E6
0x180028228  lea     rcx, [rbp+7]
0x18002822c  cmp     ebx, 1
0x18002822f  jnz     short loc_18002826C
0x180028231  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x180028238  call    sqlite3StrICmp
0x18002823d  test    eax, eax
0x18002823f  jz      loc_1800283C7
0x180028245  lea     rdx, aSqliteSchema+7; "schema"
0x18002824c  call    sqlite3StrICmp
0x180028251  test    eax, eax
0x180028253  jz      loc_1800283C7
0x180028259  lea     rdx, aSqliteMaster+7; "master"
0x180028260  jmp     loc_1800283BE
0x180028265  xor     eax, eax
0x180028267  jmp     loc_1800283E9
0x18002826c  lea     rdx, aSqliteSchema+7; "schema"
0x180028273  call    sqlite3StrICmp
0x180028278  test    eax, eax
0x18002827a  jnz     loc_1800283E6
0x180028280  mov     rax, [rsi+20h]
0x180028284  mov     rcx, [r14+rax+18h]
0x180028289  lea     rdx, aSqliteMaster; "sqlite_master"
0x180028290  jmp     loc_1800283D6
0x180028295  mov     rbx, [rcx+20h]
0x180028299  mov     r9, [rbx+38h]
0x18002829d  add     r9, 8
0x1800282a1  mov     r10, [r9+10h]
0x1800282a5  test    r10, r10
0x1800282a8  jz      short loc_1800282C6
0x1800282aa  mov     rcx, rbp
0x1800282ad  call    strHash
0x1800282b2  xor     edx, edx
0x1800282b4  div     dword ptr [r9]
0x1800282b7  mov     r9d, edx
0x1800282ba  shl     r9, 4
0x1800282be  add     r9, r10
0x1800282c1  mov     r8d, [r9]
0x1800282c4  jmp     short loc_1800282CA
0x1800282c6  mov     r8d, [r9+4]
0x1800282ca  mov     rdx, [r9+8]
0x1800282ce  lea     rdi, qword_1800ADCF0
0x1800282d5  test    r8d, r8d
0x1800282d8  jz      short loc_180028312
0x1800282da  mov     r9, [rdx+18h]
0x1800282de  mov     r10, rbp
0x1800282e1  movzx   r11d, byte ptr [r9]
0x1800282e5  movzx   eax, byte ptr [r10]
0x1800282e9  cmp     r11d, eax
0x1800282ec  jnz     short loc_1800282F5
0x1800282ee  test    r11d, r11d
0x1800282f1  jnz     short loc_180028302
0x1800282f3  jmp     short loc_180028319
0x1800282f5  movzx   ecx, byte ptr [rax+rdi]
0x1800282f9  movzx   eax, byte ptr [r11+rdi]
0x1800282fe  cmp     eax, ecx
0x180028300  jnz     short loc_18002830A
0x180028302  inc     r9
0x180028305  inc     r10
0x180028308  jmp     short loc_1800282E1
0x18002830a  mov     rdx, [rdx]
0x18002830d  dec     r8d
0x180028310  jmp     short loc_1800282D5
0x180028312  lea     rdx, qword_1800C78E8
0x180028319  mov     rax, [rdx+10h]
0x18002831d  test    rax, rax
0x180028320  jnz     loc_1800283E9
0x180028326  mov     rcx, [rbx+18h]
0x18002832a  xor     r8d, r8d
0x18002832d  add     rcx, 8
0x180028331  mov     rdx, rbp
0x180028334  call    findElementWithHash
0x180028339  mov     rdi, [rax+10h]
0x18002833d  test    rdi, rdi
0x180028340  jnz     loc_1800283E6
0x180028346  lea     ebx, [rdi+2]
0x180028349  cmp     [rsi+28h], ebx
0x18002834c  jle     short loc_18002837D
0x18002834e  mov     rax, [rsi+20h]
0x180028352  xor     r8d, r8d
0x180028355  movsxd  rcx, ebx
0x180028358  mov     rdx, rbp
0x18002835b  shl     rcx, 5
0x18002835f  mov     rcx, [rcx+rax+18h]
0x180028364  add     rcx, 8
0x180028368  call    findElementWithHash
0x18002836d  mov     rdi, [rax+10h]
0x180028371  test    rdi, rdi
0x180028374  jnz     short loc_1800283E6
0x180028376  inc     ebx
0x180028378  cmp     ebx, [rsi+28h]
0x18002837b  jl      short loc_18002834E
0x18002837d  mov     r8d, 7
0x180028383  lea     rdx, aSqlite_0; "sqlite_"
0x18002838a  mov     rcx, rbp
0x18002838d  call    sqlite3_strnicmp
0x180028392  test    eax, eax
0x180028394  jnz     short loc_1800283E6
0x180028396  lea     rcx, [rbp+7]
0x18002839a  lea     rdx, aSqliteSchema+7; "schema"
0x1800283a1  call    sqlite3StrICmp
0x1800283a6  test    eax, eax
0x1800283a8  jnz     short loc_1800283B7
0x1800283aa  mov     rax, [rsi+20h]
0x1800283ae  mov     rcx, [rax+18h]
0x1800283b2  jmp     loc_180028289
0x1800283b7  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x1800283be  call    sqlite3StrICmp
0x1800283c3  test    eax, eax
0x1800283c5  jnz     short loc_1800283E6
0x1800283c7  mov     rax, [rsi+20h]
0x1800283cb  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x1800283d2  mov     rcx, [rax+38h]
0x1800283d6  xor     r8d, r8d
0x1800283d9  add     rcx, 8
0x1800283dd  call    findElementWithHash
0x1800283e2  mov     rdi, [rax+10h]
0x1800283e6  mov     rax, rdi
0x1800283e9  add     rsp, 28h
0x1800283ed  pop     r15
0x1800283ef  pop     r14
0x1800283f1  pop     rdi
0x1800283f2  pop     rsi
0x1800283f3  pop     rbp
0x1800283f4  pop     rbx
0x1800283f5  retn
```
