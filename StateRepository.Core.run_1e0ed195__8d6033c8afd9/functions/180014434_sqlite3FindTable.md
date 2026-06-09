# sqlite3FindTable

- ea: `0x180014434`
- end: `0x1800146b1`
- name: `sqlite3FindTable`
- size: `637`
- prototype: ``
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x180003128`
- `0x18000ded0`
- `0x180013c28`
- `0x180013e30`
- `0x1800155e4`
- `0x18001c6f8`
- `0x180050420`
- `0x18005952c`
- `0x1800655a8`
- `0x18007d6a0`
- `0x18007e240`
- `0x18007e570`
- `0x180080628`
- `0x180080c08`
- `0x1800825e0`
- `0x180086c1c`
- `0x180089870`
- `0x18008995c`
- `0x180090110`

## callees

- `0x1800143f0`
- `0x180014434`
- `0x180016250`
- `0x18004b050`

## string_xrefs

- `0x180014574`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, _BYTE *a2, __int64 a3)
{
  __int64 result; // rax
  int v7; // r11d
  int v8; // edi
  __int64 v9; // r14
  __int64 v10; // r14
  __int64 v11; // rsi
  int v12; // edi
  char *v13; // rdx
  _BYTE *v14; // rcx
  const char *v15; // rdx
  __int64 v16; // rcx
  int v17; // r8d
  const char *v18; // rdx
  _BYTE *v19; // r9
  _BYTE *v20; // rbp

  if ( a3 )
  {
    v7 = *(_DWORD *)(a1 + 40);
    v8 = 0;
    if ( v7 <= 0 )
    {
LABEL_19:
      if ( v8 >= v7 )
      {
        if ( (unsigned int)sqlite3StrICmp(a3, "main") )
          return 0;
        v8 = 0;
      }
    }
    else
    {
      v9 = *(_QWORD *)(a1 + 32);
      while ( (unsigned int)sqlite3StrICmp(a3, *(_QWORD *)(32LL * (unsigned int)v8 + v9)) )
      {
        if ( ++v8 >= v7 )
          goto LABEL_19;
      }
    }
    v10 = 32LL * v8;
    v11 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(v10 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
    if ( v11 || !a2 )
      return v11;
    v17 = 7;
    v18 = "sqlite_";
    v19 = a2;
    while ( 1 )
    {
      --v17;
      if ( !*v19
        || *((_BYTE *)qword_18009E760 + (unsigned __int8)*v19) != *((_BYTE *)qword_18009E760 + *(unsigned __int8 *)v18) )
      {
        break;
      }
      ++v19;
      ++v18;
      if ( v17 <= 0 )
      {
        --v17;
        break;
      }
    }
    if ( v17 >= 0
      && *((unsigned __int8 *)qword_18009E760 + (unsigned __int8)*v19) != *((unsigned __int8 *)qword_18009E760
                                                                          + *(unsigned __int8 *)v18) )
    {
      return v11;
    }
    v20 = a2 + 7;
    if ( v8 == 1 )
    {
      if ( !(unsigned int)sqlite3StrICmp(v20, "temp_schema") || !(unsigned int)sqlite3StrICmp(v20, "schema") )
        goto LABEL_17;
      v13 = "master";
      v14 = v20;
LABEL_16:
      if ( !(unsigned int)sqlite3StrICmp(v14, v13) )
      {
LABEL_17:
        v15 = "sqlite_temp_master";
        v16 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
        return *(_QWORD *)(findElementWithHash(v16 + 8, v15, 0) + 16);
      }
      return v11;
    }
    if ( (unsigned int)sqlite3StrICmp(v20, "schema") )
      return v11;
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + v10 + 24);
LABEL_40:
    v15 = "sqlite_master";
    return *(_QWORD *)(findElementWithHash(v16 + 8, v15, 0) + 16);
  }
  result = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL) + 8LL, a2, 0) + 16);
  if ( !result )
  {
    v11 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL, a2, 0) + 16);
    if ( v11 )
      return v11;
    v12 = 2;
    if ( *(int *)(a1 + 40) > 2 )
    {
      do
      {
        v11 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v12 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
        if ( v11 )
          return v11;
      }
      while ( ++v12 < *(_DWORD *)(a1 + 40) );
    }
    if ( (unsigned int)sqlite3_strnicmp(a2, "sqlite_") )
      return v11;
    if ( (unsigned int)sqlite3StrICmp(a2 + 7, "schema") )
    {
      v13 = "temp_schema";
      v14 = a2 + 7;
      goto LABEL_16;
    }
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
    goto LABEL_40;
  }
  return result;
}

```

## disassembly

```asm
0x180014434  push    rbx
0x180014436  push    rbp
0x180014437  push    rsi
0x180014438  push    rdi
0x180014439  push    r14
0x18001443b  sub     rsp, 20h
0x18001443f  mov     rsi, r8
0x180014442  mov     rbp, rdx
0x180014445  mov     rbx, rcx
0x180014448  test    r8, r8
0x18001444b  jnz     short loc_180014472
0x18001444d  mov     rax, [rcx+20h]
0x180014451  mov     rcx, [rax+38h]
0x180014455  add     rcx, 8
0x180014459  call    findElementWithHash
0x18001445e  mov     rax, [rax+10h]
0x180014462  test    rax, rax
0x180014465  jz      short loc_1800144D0
0x180014467  add     rsp, 20h
0x18001446b  pop     r14
0x18001446d  pop     rdi
0x18001446e  pop     rsi
0x18001446f  pop     rbp
0x180014470  pop     rbx
0x180014471  retn
0x180014472  mov     r11d, [rcx+28h]
0x180014476  xor     edi, edi
0x180014478  test    r11d, r11d
0x18001447b  jle     loc_180014594
0x180014481  mov     r14, [rcx+20h]
0x180014485  mov     edx, edi
0x180014487  mov     rcx, rsi
0x18001448a  shl     rdx, 5
0x18001448e  mov     rdx, [rdx+r14]
0x180014492  call    sqlite3StrICmp
0x180014497  test    eax, eax
0x180014499  jnz     loc_18001464C
0x18001449f  mov     rax, [rbx+20h]
0x1800144a3  xor     r8d, r8d
0x1800144a6  movsxd  r14, edi
0x1800144a9  mov     rdx, rbp
0x1800144ac  shl     r14, 5
0x1800144b0  mov     rcx, [r14+rax+18h]
0x1800144b5  add     rcx, 8
0x1800144b9  call    findElementWithHash
0x1800144be  mov     rsi, [rax+10h]
0x1800144c2  test    rsi, rsi
0x1800144c5  jz      loc_1800145BB
0x1800144cb  mov     rax, rsi
0x1800144ce  jmp     short loc_180014467
0x1800144d0  mov     rax, [rbx+20h]
0x1800144d4  xor     r8d, r8d
0x1800144d7  mov     rdx, rbp
0x1800144da  mov     rcx, [rax+18h]
0x1800144de  add     rcx, 8
0x1800144e2  call    findElementWithHash
0x1800144e7  mov     rsi, [rax+10h]
0x1800144eb  test    rsi, rsi
0x1800144ee  jnz     short loc_1800144CB
0x1800144f0  lea     edi, [rsi+2]
0x1800144f3  cmp     [rbx+28h], edi
0x1800144f6  jle     short loc_180014527
0x1800144f8  mov     rax, [rbx+20h]
0x1800144fc  xor     r8d, r8d
0x1800144ff  movsxd  rcx, edi
0x180014502  mov     rdx, rbp
0x180014505  shl     rcx, 5
0x180014509  mov     rcx, [rcx+rax+18h]
0x18001450e  add     rcx, 8
0x180014512  call    findElementWithHash
0x180014517  mov     rsi, [rax+10h]
0x18001451b  test    rsi, rsi
0x18001451e  jnz     short loc_1800144CB
0x180014520  inc     edi
0x180014522  cmp     edi, [rbx+28h]
0x180014525  jl      short loc_1800144F8
0x180014527  mov     r8d, 7
0x18001452d  lea     rdx, aSqlite_0; "sqlite_"
0x180014534  mov     rcx, rbp
0x180014537  call    sqlite3_strnicmp
0x18001453c  test    eax, eax
0x18001453e  jnz     short loc_1800144CB
0x180014540  lea     rdx, aSqliteSchema+7; "schema"
0x180014547  lea     rcx, [rbp+7]
0x18001454b  call    sqlite3StrICmp
0x180014550  test    eax, eax
0x180014552  jz      loc_18001469D
0x180014558  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x18001455f  lea     rcx, [rbp+7]
0x180014563  call    sqlite3StrICmp
0x180014568  test    eax, eax
0x18001456a  jnz     loc_1800144CB
0x180014570  mov     rax, [rbx+20h]
0x180014574  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x18001457b  mov     rcx, [rax+38h]
0x18001457f  xor     r8d, r8d
0x180014582  add     rcx, 8
0x180014586  call    findElementWithHash
0x18001458b  mov     rsi, [rax+10h]
0x18001458f  jmp     loc_1800144CB
0x180014594  cmp     edi, r11d
0x180014597  jl      loc_18001449F
0x18001459d  lea     rdx, aMain; "main"
0x1800145a4  mov     rcx, rsi
0x1800145a7  call    sqlite3StrICmp
0x1800145ac  test    eax, eax
0x1800145ae  jz      loc_18001465C
0x1800145b4  xor     eax, eax
0x1800145b6  jmp     loc_180014467
0x1800145bb  test    rbp, rbp
0x1800145be  jz      loc_1800144CB
0x1800145c4  mov     r8d, 7
0x1800145ca  lea     rdx, aSqlite_0; "sqlite_"
0x1800145d1  mov     r9, rbp
0x1800145d4  lea     r10, qword_18009E760
0x1800145db  dec     r8d
0x1800145de  cmp     byte ptr [r9], 0
0x1800145e2  jz      short loc_180014603
0x1800145e4  movzx   eax, byte ptr [rdx]
0x1800145e7  movzx   ecx, byte ptr [r9]
0x1800145eb  mov     al, [rax+r10]
0x1800145ef  cmp     [rcx+r10], al
0x1800145f3  jnz     short loc_180014603
0x1800145f5  inc     r9
0x1800145f8  inc     rdx
0x1800145fb  test    r8d, r8d
0x1800145fe  jg      short loc_1800145DB
0x180014600  dec     r8d
0x180014603  test    r8d, r8d
0x180014606  js      short loc_180014621
0x180014608  movzx   eax, byte ptr [rdx]
0x18001460b  movzx   ecx, byte ptr [rax+r10]
0x180014610  movzx   eax, byte ptr [r9]
0x180014614  movzx   eax, byte ptr [rax+r10]
0x180014619  cmp     eax, ecx
0x18001461b  jnz     loc_1800144CB
0x180014621  add     rbp, 7
0x180014625  mov     rcx, rbp
0x180014628  cmp     edi, 1
0x18001462b  jz      short loc_180014663
0x18001462d  lea     rdx, aSqliteSchema+7; "schema"
0x180014634  call    sqlite3StrICmp
0x180014639  test    eax, eax
0x18001463b  jnz     loc_1800144CB
0x180014641  mov     rax, [rbx+20h]
0x180014645  mov     rcx, [rax+r14+18h]
0x18001464a  jmp     short loc_1800146A5
0x18001464c  inc     edi
0x18001464e  cmp     edi, r11d
0x180014651  jl      loc_180014485
0x180014657  jmp     loc_180014594
0x18001465c  xor     edi, edi
0x18001465e  jmp     loc_18001449F
0x180014663  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x18001466a  call    sqlite3StrICmp
0x18001466f  test    eax, eax
0x180014671  jz      loc_180014570
0x180014677  lea     rdx, aSqliteSchema+7; "schema"
0x18001467e  mov     rcx, rbp
0x180014681  call    sqlite3StrICmp
0x180014686  test    eax, eax
0x180014688  jz      loc_180014570
0x18001468e  lea     rdx, aSqliteMaster+7; "master"
0x180014695  mov     rcx, rbp
0x180014698  jmp     loc_180014563
0x18001469d  mov     rax, [rbx+20h]
0x1800146a1  mov     rcx, [rax+18h]
0x1800146a5  lea     rdx, aSqliteMaster; "sqlite_master"
0x1800146ac  jmp     loc_18001457F
```
