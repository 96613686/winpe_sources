# sqlite3FindTable

- ea: `0x180078c74`
- end: `0x180078e8f`
- name: `sqlite3FindTable`
- size: `539`
- prototype: ``
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x180036570`
- `0x180059064`
- `0x1800600a0`
- `0x1800610a8`
- `0x180061400`
- `0x180067ef8`
- `0x180068554`
- `0x1800688dc`
- `0x18006dde4`
- `0x180070678`
- `0x1800797bc`
- `0x180080620`
- `0x1800847e0`
- `0x180089be4`
- `0x18008dd8c`
- `0x18008e690`
- `0x18009db14`
- `0x18009dc0c`
- `0x1800adac0`

## callees

- `0x180047054`
- `0x180078c74`
- `0x18008ed60`
- `0x1800ada30`

## string_xrefs

- `0x180078e66`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // r11d
  int v7; // edi
  __int64 v8; // r14
  __int64 v9; // r14
  __int64 v10; // rsi
  __int64 v11; // rbp
  char *v12; // rdx
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // rcx
  const char *v16; // rdx
  int v17; // edi

  if ( !a3 )
  {
    result = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL) + 8LL, a2, 0) + 16);
    if ( result )
      return result;
    v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL, a2, 0) + 16);
    if ( v10 )
      return v10;
    v17 = 2;
    if ( *(int *)(a1 + 40) > 2 )
    {
      do
      {
        v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v17 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
        if ( v10 )
          return v10;
      }
      while ( ++v17 < *(_DWORD *)(a1 + 40) );
    }
    if ( (unsigned int)sqlite3_strnicmp(a2, "sqlite_", 7) )
      return v10;
    if ( (unsigned int)sqlite3StrICmp(a2 + 7, "schema") )
    {
      v12 = "temp_schema";
      v13 = a2 + 7;
      goto LABEL_28;
    }
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
LABEL_18:
    v16 = "sqlite_master";
    return *(_QWORD *)(findElementWithHash(v15 + 8, v16, 0) + 16);
  }
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
  if ( v7 != 1 )
  {
    if ( (unsigned int)sqlite3StrICmp(v11, "schema") )
      return v10;
    v15 = *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 24);
    goto LABEL_18;
  }
  if ( !(unsigned int)sqlite3StrICmp(v11, "temp_schema") || !(unsigned int)sqlite3StrICmp(v11, "schema") )
    goto LABEL_29;
  v12 = "master";
  v13 = v11;
LABEL_28:
  if ( !(unsigned int)sqlite3StrICmp(v13, v12) )
  {
LABEL_29:
    v16 = "sqlite_temp_master";
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
    return *(_QWORD *)(findElementWithHash(v15 + 8, v16, 0) + 16);
  }
  return v10;
}

```

## disassembly

```asm
0x180078c74  push    rbx
0x180078c76  push    rbp
0x180078c77  push    rsi
0x180078c78  push    rdi
0x180078c79  push    r14
0x180078c7b  sub     rsp, 20h
0x180078c7f  mov     rsi, r8
0x180078c82  mov     rbp, rdx
0x180078c85  mov     rbx, rcx
0x180078c88  test    r8, r8
0x180078c8b  jz      loc_180078D98
0x180078c91  mov     r11d, [rcx+28h]
0x180078c95  xor     edi, edi
0x180078c97  test    r11d, r11d
0x180078c9a  jle     short loc_180078CBD
0x180078c9c  mov     r14, [rcx+20h]
0x180078ca0  mov     edx, edi
0x180078ca2  mov     rcx, rsi
0x180078ca5  shl     rdx, 5
0x180078ca9  mov     rdx, [rdx+r14]
0x180078cad  call    sqlite3StrICmp
0x180078cb2  test    eax, eax
0x180078cb4  jz      short loc_180078CDB
0x180078cb6  inc     edi
0x180078cb8  cmp     edi, r11d
0x180078cbb  jl      short loc_180078CA0
0x180078cbd  cmp     edi, r11d
0x180078cc0  jl      short loc_180078CDB
0x180078cc2  lea     rdx, aMain; "main"
0x180078cc9  mov     rcx, rsi
0x180078ccc  call    sqlite3StrICmp
0x180078cd1  test    eax, eax
0x180078cd3  jnz     loc_180078D68
0x180078cd9  xor     edi, edi
0x180078cdb  mov     rax, [rbx+20h]
0x180078cdf  xor     r8d, r8d
0x180078ce2  movsxd  r14, edi
0x180078ce5  mov     rdx, rbp
0x180078ce8  shl     r14, 5
0x180078cec  mov     rcx, [r14+rax+18h]
0x180078cf1  add     rcx, 8
0x180078cf5  call    findElementWithHash
0x180078cfa  mov     rsi, [rax+10h]
0x180078cfe  test    rsi, rsi
0x180078d01  jnz     loc_180078E81
0x180078d07  lea     r8d, [rsi+7]
0x180078d0b  mov     rcx, rbp
0x180078d0e  lea     rdx, aSqlite_0; "sqlite_"
0x180078d15  call    sqlite3_strnicmp
0x180078d1a  test    eax, eax
0x180078d1c  jnz     loc_180078E81
0x180078d22  add     rbp, 7
0x180078d26  mov     rcx, rbp
0x180078d29  cmp     edi, 1
0x180078d2c  jnz     short loc_180078D6F
0x180078d2e  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x180078d35  call    sqlite3StrICmp
0x180078d3a  test    eax, eax
0x180078d3c  jz      loc_180078E62
0x180078d42  lea     rdx, aSqliteSchema+7; "schema"
0x180078d49  mov     rcx, rbp
0x180078d4c  call    sqlite3StrICmp
0x180078d51  test    eax, eax
0x180078d53  jz      loc_180078E62
0x180078d59  lea     rdx, aSqliteMaster+7; "master"
0x180078d60  mov     rcx, rbp
0x180078d63  jmp     loc_180078E59
0x180078d68  xor     eax, eax
0x180078d6a  jmp     loc_180078E84
0x180078d6f  lea     rdx, aSqliteSchema+7; "schema"
0x180078d76  call    sqlite3StrICmp
0x180078d7b  test    eax, eax
0x180078d7d  jnz     loc_180078E81
0x180078d83  mov     rax, [rbx+20h]
0x180078d87  mov     rcx, [r14+rax+18h]
0x180078d8c  lea     rdx, aSqliteMaster; "sqlite_master"
0x180078d93  jmp     loc_180078E71
0x180078d98  mov     rax, [rcx+20h]
0x180078d9c  xor     r8d, r8d
0x180078d9f  mov     rcx, [rax+38h]
0x180078da3  add     rcx, 8
0x180078da7  call    findElementWithHash
0x180078dac  mov     rax, [rax+10h]
0x180078db0  test    rax, rax
0x180078db3  jnz     loc_180078E84
0x180078db9  mov     rax, [rbx+20h]
0x180078dbd  xor     r8d, r8d
0x180078dc0  mov     rdx, rbp
0x180078dc3  mov     rcx, [rax+18h]
0x180078dc7  add     rcx, 8
0x180078dcb  call    findElementWithHash
0x180078dd0  mov     rsi, [rax+10h]
0x180078dd4  test    rsi, rsi
0x180078dd7  jnz     loc_180078E81
0x180078ddd  lea     edi, [rsi+2]
0x180078de0  cmp     [rbx+28h], edi
0x180078de3  jle     short loc_180078E14
0x180078de5  mov     rax, [rbx+20h]
0x180078de9  xor     r8d, r8d
0x180078dec  movsxd  rcx, edi
0x180078def  mov     rdx, rbp
0x180078df2  shl     rcx, 5
0x180078df6  mov     rcx, [rcx+rax+18h]
0x180078dfb  add     rcx, 8
0x180078dff  call    findElementWithHash
0x180078e04  mov     rsi, [rax+10h]
0x180078e08  test    rsi, rsi
0x180078e0b  jnz     short loc_180078E81
0x180078e0d  inc     edi
0x180078e0f  cmp     edi, [rbx+28h]
0x180078e12  jl      short loc_180078DE5
0x180078e14  mov     r8d, 7
0x180078e1a  lea     rdx, aSqlite_0; "sqlite_"
0x180078e21  mov     rcx, rbp
0x180078e24  call    sqlite3_strnicmp
0x180078e29  test    eax, eax
0x180078e2b  jnz     short loc_180078E81
0x180078e2d  lea     rdx, aSqliteSchema+7; "schema"
0x180078e34  lea     rcx, [rbp+7]
0x180078e38  call    sqlite3StrICmp
0x180078e3d  test    eax, eax
0x180078e3f  jnz     short loc_180078E4E
0x180078e41  mov     rax, [rbx+20h]
0x180078e45  mov     rcx, [rax+18h]
0x180078e49  jmp     loc_180078D8C
0x180078e4e  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x180078e55  lea     rcx, [rbp+7]
0x180078e59  call    sqlite3StrICmp
0x180078e5e  test    eax, eax
0x180078e60  jnz     short loc_180078E81
0x180078e62  mov     rax, [rbx+20h]
0x180078e66  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x180078e6d  mov     rcx, [rax+38h]
0x180078e71  xor     r8d, r8d
0x180078e74  add     rcx, 8
0x180078e78  call    findElementWithHash
0x180078e7d  mov     rsi, [rax+10h]
0x180078e81  mov     rax, rsi
0x180078e84  add     rsp, 20h
0x180078e88  pop     r14
0x180078e8a  pop     rdi
0x180078e8b  pop     rsi
0x180078e8c  pop     rbp
0x180078e8d  pop     rbx
0x180078e8e  retn
```
