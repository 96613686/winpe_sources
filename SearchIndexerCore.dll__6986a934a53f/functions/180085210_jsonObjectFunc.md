# jsonObjectFunc

- ea: `0x180085210`
- end: `0x18008537c`
- name: `jsonObjectFunc`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180024b60`
- `0x180054ef4`
- `0x180078968`
- `0x1800789c0`
- `0x180081d70`
- `0x180081fdc`
- `0x18008200c`
- `0x180082178`
- `0x180085210`
- `0x180086088`
- `0x1800864e4`
- `0x18009d650`
- `0x18009d790`

## string_xrefs

- `0x18008525e`: `json_object() requires an even number of arguments`
- `0x180085314`: `json_object() labels must be TEXT`

## pseudocode

```c
__int64 __fastcall jsonObjectFunc(__int64 a1, int a2, __int64 a3)
{
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int8 *v11; // rbx
  unsigned int v12; // eax
  _QWORD v13[4]; // [rsp+20h] [rbp-69h] BYREF
  __int16 v14; // [rsp+40h] [rbp-49h]
  _BYTE v15[110]; // [rsp+42h] [rbp-47h] BYREF

  memset_0(v15, 0, 0x66u);
  if ( (a2 & 1) != 0 )
    return sqlite3_result_error(a1, "json_object() requires an even number of arguments", 0xFFFFFFFFLL);
  v7 = 0;
  v13[0] = a1;
  v13[3] = 0;
  v13[1] = v15;
  v14 = 1;
  v13[2] = 100;
  jsonAppendChar(v13, 123);
  while ( v7 < a2 )
  {
    if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(*(_QWORD *)(a3 + 8LL * v7) + 20LL) & 0x3F)) != 3 )
    {
      sqlite3_result_error(a1, "json_object() labels must be TEXT", 0xFFFFFFFFLL);
      return jsonStringReset(v13);
    }
    jsonAppendSeparator(v13);
    LOBYTE(v8) = 1;
    v9 = sqlite3ValueText(*(_QWORD *)(a3 + 8LL * v7), v8);
    LOBYTE(v10) = 1;
    v11 = (unsigned __int8 *)v9;
    v12 = sqlite3ValueBytes(*(_QWORD *)(a3 + 8LL * v7), v10);
    jsonAppendString(v13, v11, v12);
    jsonAppendChar(v13, 58);
    jsonAppendSqlValue(v13, *(_QWORD *)(a3 + 8LL * v7 + 8));
    v7 += 2;
  }
  jsonAppendChar(v13, 125);
  jsonReturnString(v13, 0, 0);
  return sqlite3_result_subtype(a1, 74);
}

```

## disassembly

```asm
0x180085210  mov     [rsp-8+arg_8], rbx
0x180085215  mov     [rsp-8+arg_18], rsi
0x18008521a  push    rbp
0x18008521b  push    rdi
0x18008521c  push    r12
0x18008521e  push    r14
0x180085220  push    r15
0x180085222  lea     rbp, [rsp-37h]
0x180085227  sub     rsp, 0C0h
0x18008522e  mov     rax, cs:__security_cookie
0x180085235  xor     rax, rsp
0x180085238  mov     [rbp+57h+var_30], rax
0x18008523c  mov     r15d, edx
0x18008523f  mov     r12, r8
0x180085242  xor     edx, edx; Val
0x180085244  mov     rdi, rcx
0x180085247  lea     rcx, [rbp+57h+var_9E]; void *
0x18008524b  lea     r8d, [rdx+66h]; Size
0x18008524f  call    memset_0
0x180085254  test    r15b, 1
0x180085258  jz      short loc_180085272
0x18008525a  or      r8d, 0FFFFFFFFh
0x18008525e  lea     rdx, aJsonObjectRequ; "json_object() requires an even number o"...
0x180085265  mov     rcx, rdi
0x180085268  call    sqlite3_result_error
0x18008526d  jmp     loc_180085354
0x180085272  xor     esi, esi
0x180085274  mov     [rbp+57h+var_C0], rdi
0x180085278  lea     rax, [rbp+57h+var_9E]
0x18008527c  mov     [rbp+57h+var_A8], rsi
0x180085280  mov     dl, 7Bh ; '{'
0x180085282  mov     [rbp+57h+var_B8], rax
0x180085286  lea     rcx, [rbp+57h+var_C0]
0x18008528a  mov     [rbp+57h+var_A0], 1
0x180085290  mov     [rbp+57h+var_B0], 64h ; 'd'
0x180085298  call    jsonAppendChar
0x18008529d  cmp     esi, r15d
0x1800852a0  jge     loc_18008532E
0x1800852a6  movsxd  r14, esi
0x1800852a9  mov     rax, [r12+r14*8]
0x1800852ad  movzx   ecx, word ptr [rax+14h]
0x1800852b1  lea     rax, qword_1800B5270
0x1800852b8  and     ecx, 3Fh
0x1800852bb  cmp     byte ptr [rcx+rax], 3
0x1800852bf  jnz     short loc_180085310
0x1800852c1  lea     rcx, [rbp+57h+var_C0]
0x1800852c5  call    jsonAppendSeparator
0x1800852ca  mov     rcx, [r12+r14*8]
0x1800852ce  mov     dl, 1
0x1800852d0  call    sqlite3ValueText
0x1800852d5  mov     rcx, [r12+r14*8]
0x1800852d9  mov     dl, 1
0x1800852db  mov     rbx, rax
0x1800852de  call    sqlite3ValueBytes
0x1800852e3  mov     r8d, eax
0x1800852e6  lea     rcx, [rbp+57h+var_C0]
0x1800852ea  mov     rdx, rbx
0x1800852ed  call    jsonAppendString
0x1800852f2  mov     dl, 3Ah ; ':'
0x1800852f4  lea     rcx, [rbp+57h+var_C0]
0x1800852f8  call    jsonAppendChar
0x1800852fd  mov     rdx, [r12+r14*8+8]
0x180085302  lea     rcx, [rbp+57h+var_C0]
0x180085306  call    jsonAppendSqlValue
0x18008530b  add     esi, 2
0x18008530e  jmp     short loc_18008529D
0x180085310  or      r8d, 0FFFFFFFFh
0x180085314  lea     rdx, aJsonObjectLabe; "json_object() labels must be TEXT"
0x18008531b  mov     rcx, rdi
0x18008531e  call    sqlite3_result_error
0x180085323  lea     rcx, [rbp+57h+var_C0]
0x180085327  call    jsonStringReset
0x18008532c  jmp     short loc_180085354
0x18008532e  mov     dl, 7Dh ; '}'
0x180085330  lea     rcx, [rbp+57h+var_C0]
0x180085334  call    jsonAppendChar
0x180085339  xor     r8d, r8d
0x18008533c  lea     rcx, [rbp+57h+var_C0]
0x180085340  xor     edx, edx
0x180085342  call    jsonReturnString
0x180085347  mov     edx, 4Ah ; 'J'
0x18008534c  mov     rcx, rdi
0x18008534f  call    sqlite3_result_subtype
0x180085354  mov     rcx, [rbp+57h+var_30]
0x180085358  xor     rcx, rsp; StackCookie
0x18008535b  call    __security_check_cookie
0x180085360  lea     r11, [rsp+0E0h+var_20]
0x180085368  mov     rbx, [r11+38h]
0x18008536c  mov     rsi, [r11+48h]
0x180085370  mov     rsp, r11
0x180085373  pop     r15
0x180085375  pop     r14
0x180085377  pop     r12
0x180085379  pop     rdi
0x18008537a  pop     rbp
0x18008537b  retn
```
