# jsonObjectFunc

- ea: `0x180076000`
- end: `0x18007616c`
- name: `jsonObjectFunc`
- size: `364`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180028540`
- `0x180048d38`
- `0x180068880`
- `0x18006910e`
- `0x180072b08`
- `0x180072d74`
- `0x180072da4`
- `0x180072f10`
- `0x180076000`
- `0x180076e78`
- `0x1800772d4`
- `0x18008f3f0`
- `0x18008f4f0`

## string_xrefs

- `0x18007604e`: `json_object() requires an even number of arguments`
- `0x180076104`: `json_object() labels must be TEXT`

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
    if ( *((_BYTE *)qword_18009EC50 + (*(_WORD *)(*(_QWORD *)(a3 + 8LL * v7) + 20LL) & 0x3F)) != 3 )
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
0x180076000  mov     [rsp-8+arg_8], rbx
0x180076005  mov     [rsp-8+arg_18], rsi
0x18007600a  push    rbp
0x18007600b  push    rdi
0x18007600c  push    r12
0x18007600e  push    r14
0x180076010  push    r15
0x180076012  lea     rbp, [rsp-37h]
0x180076017  sub     rsp, 0C0h
0x18007601e  mov     rax, cs:__security_cookie
0x180076025  xor     rax, rsp
0x180076028  mov     [rbp+57h+var_30], rax
0x18007602c  mov     r15d, edx
0x18007602f  mov     r12, r8
0x180076032  xor     edx, edx; Val
0x180076034  mov     rdi, rcx
0x180076037  lea     rcx, [rbp+57h+var_9E]; void *
0x18007603b  lea     r8d, [rdx+66h]; Size
0x18007603f  call    memset_0
0x180076044  test    r15b, 1
0x180076048  jz      short loc_180076062
0x18007604a  or      r8d, 0FFFFFFFFh
0x18007604e  lea     rdx, aJsonObjectRequ; "json_object() requires an even number o"...
0x180076055  mov     rcx, rdi
0x180076058  call    sqlite3_result_error
0x18007605d  jmp     loc_180076144
0x180076062  xor     esi, esi
0x180076064  mov     [rbp+57h+var_C0], rdi
0x180076068  lea     rax, [rbp+57h+var_9E]
0x18007606c  mov     [rbp+57h+var_A8], rsi
0x180076070  mov     dl, 7Bh ; '{'
0x180076072  mov     [rbp+57h+var_B8], rax
0x180076076  lea     rcx, [rbp+57h+var_C0]
0x18007607a  mov     [rbp+57h+var_A0], 1
0x180076080  mov     [rbp+57h+var_B0], 64h ; 'd'
0x180076088  call    jsonAppendChar
0x18007608d  cmp     esi, r15d
0x180076090  jge     loc_18007611E
0x180076096  movsxd  r14, esi
0x180076099  mov     rax, [r12+r14*8]
0x18007609d  movzx   ecx, word ptr [rax+14h]
0x1800760a1  lea     rax, qword_18009EC50
0x1800760a8  and     ecx, 3Fh
0x1800760ab  cmp     byte ptr [rcx+rax], 3
0x1800760af  jnz     short loc_180076100
0x1800760b1  lea     rcx, [rbp+57h+var_C0]
0x1800760b5  call    jsonAppendSeparator
0x1800760ba  mov     rcx, [r12+r14*8]
0x1800760be  mov     dl, 1
0x1800760c0  call    sqlite3ValueText
0x1800760c5  mov     rcx, [r12+r14*8]
0x1800760c9  mov     dl, 1
0x1800760cb  mov     rbx, rax
0x1800760ce  call    sqlite3ValueBytes
0x1800760d3  mov     r8d, eax
0x1800760d6  lea     rcx, [rbp+57h+var_C0]
0x1800760da  mov     rdx, rbx
0x1800760dd  call    jsonAppendString
0x1800760e2  mov     dl, 3Ah ; ':'
0x1800760e4  lea     rcx, [rbp+57h+var_C0]
0x1800760e8  call    jsonAppendChar
0x1800760ed  mov     rdx, [r12+r14*8+8]
0x1800760f2  lea     rcx, [rbp+57h+var_C0]
0x1800760f6  call    jsonAppendSqlValue
0x1800760fb  add     esi, 2
0x1800760fe  jmp     short loc_18007608D
0x180076100  or      r8d, 0FFFFFFFFh
0x180076104  lea     rdx, aJsonObjectLabe; "json_object() labels must be TEXT"
0x18007610b  mov     rcx, rdi
0x18007610e  call    sqlite3_result_error
0x180076113  lea     rcx, [rbp+57h+var_C0]
0x180076117  call    jsonStringReset
0x18007611c  jmp     short loc_180076144
0x18007611e  mov     dl, 7Dh ; '}'
0x180076120  lea     rcx, [rbp+57h+var_C0]
0x180076124  call    jsonAppendChar
0x180076129  xor     r8d, r8d
0x18007612c  lea     rcx, [rbp+57h+var_C0]
0x180076130  xor     edx, edx
0x180076132  call    jsonReturnString
0x180076137  mov     edx, 4Ah ; 'J'
0x18007613c  mov     rcx, rdi
0x18007613f  call    sqlite3_result_subtype
0x180076144  mov     rcx, [rbp+57h+var_30]
0x180076148  xor     rcx, rsp; StackCookie
0x18007614b  call    __security_check_cookie
0x180076150  lea     r11, [rsp+0E0h+var_20]
0x180076158  mov     rbx, [r11+38h]
0x18007615c  mov     rsi, [r11+48h]
0x180076160  mov     rsp, r11
0x180076163  pop     r15
0x180076165  pop     r14
0x180076167  pop     r12
0x180076169  pop     rdi
0x18007616a  pop     rbp
0x18007616b  retn
```
