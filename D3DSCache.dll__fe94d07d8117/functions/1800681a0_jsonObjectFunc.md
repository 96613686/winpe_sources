# jsonObjectFunc

- ea: `0x1800681a0`
- end: `0x18006830c`
- name: `jsonObjectFunc`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180042dc4`
- `0x1800449f0`
- `0x180045374`
- `0x180064d60`
- `0x180064fcc`
- `0x180064ffc`
- `0x180065168`
- `0x1800681a0`
- `0x180069018`
- `0x180069474`
- `0x18008c97c`
- `0x180096df0`
- `0x180096fb0`

## string_xrefs

- `0x1800681ee`: `json_object() requires an even number of arguments`
- `0x1800682a4`: `json_object() labels must be TEXT`

## pseudocode

```c
__int64 __fastcall jsonObjectFunc(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // rdx
  int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rdx
  _QWORD v16[4]; // [rsp+20h] [rbp-69h] BYREF
  __int16 v17; // [rsp+40h] [rbp-49h]
  _BYTE v18[110]; // [rsp+42h] [rbp-47h] BYREF

  memset_0(v18, 0, 0x66u);
  if ( (a2 & 1) != 0 )
    return sqlite3_result_error(a1, "json_object() requires an even number of arguments", 0xFFFFFFFFLL);
  v8 = 0;
  v16[0] = a1;
  v16[3] = 0;
  LOBYTE(v6) = 123;
  v16[1] = v18;
  v17 = 1;
  v16[2] = 100;
  jsonAppendChar(v16, v6);
  while ( v8 < a2 )
  {
    if ( *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(*(_QWORD *)(a3 + 8LL * v8) + 20LL) & 0x3F)) != 3 )
    {
      sqlite3_result_error(a1, "json_object() labels must be TEXT", 0xFFFFFFFFLL);
      return jsonStringReset(v16);
    }
    jsonAppendSeparator(v16);
    LOBYTE(v10) = 1;
    v11 = sqlite3ValueText(*(_QWORD *)(a3 + 8LL * v8), v10);
    LOBYTE(v12) = 1;
    v13 = v11;
    v14 = sqlite3ValueBytes(*(_QWORD *)(a3 + 8LL * v8), v12);
    jsonAppendString(v16, v13, v14);
    LOBYTE(v15) = 58;
    jsonAppendChar(v16, v15);
    jsonAppendSqlValue(v16, *(_QWORD *)(a3 + 8LL * v8 + 8));
    v8 += 2;
  }
  LOBYTE(v9) = 125;
  jsonAppendChar(v16, v9);
  jsonReturnString(v16, 0, 0);
  return sqlite3_result_subtype(a1, 74);
}

```

## disassembly

```asm
0x1800681a0  mov     [rsp-8+arg_8], rbx
0x1800681a5  mov     [rsp-8+arg_18], rsi
0x1800681aa  push    rbp
0x1800681ab  push    rdi
0x1800681ac  push    r12
0x1800681ae  push    r14
0x1800681b0  push    r15
0x1800681b2  lea     rbp, [rsp-37h]
0x1800681b7  sub     rsp, 0C0h
0x1800681be  mov     rax, cs:__security_cookie
0x1800681c5  xor     rax, rsp
0x1800681c8  mov     [rbp+57h+var_30], rax
0x1800681cc  mov     r15d, edx
0x1800681cf  mov     r12, r8
0x1800681d2  xor     edx, edx; Val
0x1800681d4  mov     rdi, rcx
0x1800681d7  lea     rcx, [rbp+57h+var_9E]; void *
0x1800681db  lea     r8d, [rdx+66h]; Size
0x1800681df  call    memset_0
0x1800681e4  test    r15b, 1
0x1800681e8  jz      short loc_180068202
0x1800681ea  or      r8d, 0FFFFFFFFh
0x1800681ee  lea     rdx, aJsonObjectRequ; "json_object() requires an even number o"...
0x1800681f5  mov     rcx, rdi
0x1800681f8  call    sqlite3_result_error
0x1800681fd  jmp     loc_1800682E4
0x180068202  xor     esi, esi
0x180068204  mov     [rbp+57h+var_C0], rdi
0x180068208  lea     rax, [rbp+57h+var_9E]
0x18006820c  mov     [rbp+57h+var_A8], rsi
0x180068210  mov     dl, 7Bh ; '{'
0x180068212  mov     [rbp+57h+var_B8], rax
0x180068216  lea     rcx, [rbp+57h+var_C0]
0x18006821a  mov     [rbp+57h+var_A0], 1
0x180068220  mov     [rbp+57h+var_B0], 64h ; 'd'
0x180068228  call    jsonAppendChar
0x18006822d  cmp     esi, r15d
0x180068230  jge     loc_1800682BE
0x180068236  movsxd  r14, esi
0x180068239  mov     rax, [r12+r14*8]
0x18006823d  movzx   ecx, word ptr [rax+14h]
0x180068241  lea     rax, qword_1800B9DC0
0x180068248  and     ecx, 3Fh
0x18006824b  cmp     byte ptr [rcx+rax], 3
0x18006824f  jnz     short loc_1800682A0
0x180068251  lea     rcx, [rbp+57h+var_C0]
0x180068255  call    jsonAppendSeparator
0x18006825a  mov     rcx, [r12+r14*8]
0x18006825e  mov     dl, 1
0x180068260  call    sqlite3ValueText
0x180068265  mov     rcx, [r12+r14*8]
0x180068269  mov     dl, 1
0x18006826b  mov     rbx, rax
0x18006826e  call    sqlite3ValueBytes
0x180068273  mov     r8d, eax
0x180068276  lea     rcx, [rbp+57h+var_C0]
0x18006827a  mov     rdx, rbx
0x18006827d  call    jsonAppendString
0x180068282  mov     dl, 3Ah ; ':'
0x180068284  lea     rcx, [rbp+57h+var_C0]
0x180068288  call    jsonAppendChar
0x18006828d  mov     rdx, [r12+r14*8+8]
0x180068292  lea     rcx, [rbp+57h+var_C0]
0x180068296  call    jsonAppendSqlValue
0x18006829b  add     esi, 2
0x18006829e  jmp     short loc_18006822D
0x1800682a0  or      r8d, 0FFFFFFFFh
0x1800682a4  lea     rdx, aJsonObjectLabe; "json_object() labels must be TEXT"
0x1800682ab  mov     rcx, rdi
0x1800682ae  call    sqlite3_result_error
0x1800682b3  lea     rcx, [rbp+57h+var_C0]
0x1800682b7  call    jsonStringReset
0x1800682bc  jmp     short loc_1800682E4
0x1800682be  mov     dl, 7Dh ; '}'
0x1800682c0  lea     rcx, [rbp+57h+var_C0]
0x1800682c4  call    jsonAppendChar
0x1800682c9  xor     r8d, r8d
0x1800682cc  lea     rcx, [rbp+57h+var_C0]
0x1800682d0  xor     edx, edx
0x1800682d2  call    jsonReturnString
0x1800682d7  mov     edx, 4Ah ; 'J'
0x1800682dc  mov     rcx, rdi
0x1800682df  call    sqlite3_result_subtype
0x1800682e4  mov     rcx, [rbp+57h+var_30]
0x1800682e8  xor     rcx, rsp; StackCookie
0x1800682eb  call    __security_check_cookie
0x1800682f0  lea     r11, [rsp+0E0h+var_20]
0x1800682f8  mov     rbx, [r11+38h]
0x1800682fc  mov     rsi, [r11+48h]
0x180068300  mov     rsp, r11
0x180068303  pop     r15
0x180068305  pop     r14
0x180068307  pop     r12
0x180068309  pop     rdi
0x18006830a  pop     rbp
0x18006830b  retn
```
