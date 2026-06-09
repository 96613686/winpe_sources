# jsonAppendSqlValue

- ea: `0x180072da4`
- end: `0x180072f07`
- name: `jsonAppendSqlValue`
- size: `355`
- prototype: `void *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180073280`
- `0x180073450`
- `0x180076000`
- `0x180076180`
- `0x1800767b0`

## callees

- `0x180027a20`
- `0x180028540`
- `0x180048d38`
- `0x18006910e`
- `0x180072cd8`
- `0x180072d28`
- `0x180072da4`
- `0x180072f10`
- `0x180074d08`
- `0x18007672c`
- `0x1800772d4`
- `0x18007750c`
- `0x18008924c`
- `0x18008f3f0`
- `0x180090e20`

## string_xrefs

- `0x180072e42`: `JSON cannot hold BLOB values`

## pseudocode

```c
void *__fastcall jsonAppendSqlValue(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rsi
  void *result; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  const void *v9; // rbx
  unsigned int v10; // ebp
  int v11; // eax
  unsigned int v12; // r8d
  const void *v13; // rdx
  _QWORD *v14; // rcx
  double v15; // xmm0_8
  __int64 v16; // rax
  __int64 v17; // rdx
  const void *v18; // rbx
  __int64 v19; // [rsp+20h] [rbp-78h] BYREF
  int v20; // [rsp+28h] [rbp-70h]

  v3 = a2;
  switch ( *((_BYTE *)qword_18009EC50 + (*(_WORD *)(a2 + 20) & 0x3F)) )
  {
    case 1:
      LOBYTE(a2) = 1;
      v16 = sqlite3ValueText(v3, a2);
      LOBYTE(v17) = 1;
      v18 = (const void *)v16;
      v12 = sqlite3ValueBytes(v3, v17);
      v13 = v18;
      v14 = a1;
      return jsonAppendRaw(v14, v13, v12);
    case 2:
      v15 = sqlite3VdbeRealValue(a2);
      return (void *)jsonPrintf(100, a1, "%!0.15g", v15);
    case 3:
      LOBYTE(a2) = 1;
      v7 = sqlite3ValueText(v3, a2);
      LOBYTE(v8) = 1;
      v9 = (const void *)v7;
      v10 = sqlite3ValueBytes(v3, v8);
      v11 = sqlite3_value_subtype(v3);
      v12 = v10;
      v13 = v9;
      v14 = a1;
      if ( v11 != 74 )
        return (void *)jsonAppendString(a1, v9, v10);
      return jsonAppendRaw(v14, v13, v12);
    case 5:
      return jsonAppendRawNZ(a1, "null", 4u);
  }
  result = (void *)jsonFuncArgMightBeBinary(a2);
  if ( (_DWORD)result )
  {
    memset_0(&v19, 0, 0x48u);
    v5 = sqlite3_value_blob(v3);
    LOBYTE(v6) = 1;
    v19 = v5;
    v20 = sqlite3ValueBytes(v3, v6);
    return (void *)jsonTranslateBlobToText(&v19, 0, a1);
  }
  else if ( !*((_BYTE *)a1 + 33) )
  {
    sqlite3_result_error(*a1, "JSON cannot hold BLOB values", 0xFFFFFFFFLL);
    *((_BYTE *)a1 + 33) = 4;
    return (void *)jsonStringReset(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180072da4  push    rbx
0x180072da6  push    rbp
0x180072da7  push    rsi
0x180072da8  push    rdi
0x180072da9  sub     rsp, 78h
0x180072dad  movzx   eax, word ptr [rdx+14h]
0x180072db1  mov     rdi, rcx
0x180072db4  and     eax, 3Fh
0x180072db7  lea     rcx, qword_18009EC50
0x180072dbe  mov     rsi, rdx
0x180072dc1  movzx   r8d, byte ptr [rax+rcx]
0x180072dc6  sub     r8d, 1
0x180072dca  jz      loc_180072ED9
0x180072dd0  sub     r8d, 1
0x180072dd4  jz      loc_180072EB3
0x180072dda  sub     r8d, 1
0x180072dde  jz      loc_180072E7D
0x180072de4  cmp     r8d, 2
0x180072de8  jz      short loc_180072E63
0x180072dea  mov     rcx, rdx
0x180072ded  call    jsonFuncArgMightBeBinary
0x180072df2  test    eax, eax
0x180072df4  jz      short loc_180072E35
0x180072df6  xor     edx, edx; Val
0x180072df8  lea     rcx, [rsp+98h+var_78]; void *
0x180072dfd  lea     r8d, [rdx+48h]; Size
0x180072e01  call    memset_0
0x180072e06  mov     rcx, rsi
0x180072e09  call    sqlite3_value_blob
0x180072e0e  mov     dl, 1
0x180072e10  mov     [rsp+98h+var_78], rax
0x180072e15  mov     rcx, rsi
0x180072e18  call    sqlite3ValueBytes
0x180072e1d  mov     r8, rdi
0x180072e20  mov     [rsp+98h+var_70], eax
0x180072e24  xor     edx, edx
0x180072e26  lea     rcx, [rsp+98h+var_78]
0x180072e2b  call    jsonTranslateBlobToText
0x180072e30  jmp     loc_180072EFE
0x180072e35  cmp     byte ptr [rdi+21h], 0
0x180072e39  jnz     loc_180072EFE
0x180072e3f  mov     rcx, [rdi]
0x180072e42  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x180072e49  or      r8d, 0FFFFFFFFh
0x180072e4d  call    sqlite3_result_error
0x180072e52  mov     rcx, rdi
0x180072e55  mov     byte ptr [rdi+21h], 4
0x180072e59  call    jsonStringReset
0x180072e5e  jmp     loc_180072EFE
0x180072e63  mov     r8d, 4
0x180072e69  lea     rdx, aNull_2; "null"
0x180072e70  mov     rcx, rdi
0x180072e73  call    jsonAppendRawNZ
0x180072e78  jmp     loc_180072EFE
0x180072e7d  mov     dl, 1
0x180072e7f  mov     rcx, rsi
0x180072e82  call    sqlite3ValueText
0x180072e87  mov     dl, 1
0x180072e89  mov     rcx, rsi
0x180072e8c  mov     rbx, rax
0x180072e8f  call    sqlite3ValueBytes
0x180072e94  mov     rcx, rsi
0x180072e97  mov     ebp, eax
0x180072e99  call    sqlite3_value_subtype
0x180072e9e  mov     r8d, ebp
0x180072ea1  mov     rdx, rbx
0x180072ea4  mov     rcx, rdi
0x180072ea7  cmp     eax, 4Ah ; 'J'
0x180072eaa  jz      short loc_180072EF9
0x180072eac  call    jsonAppendString
0x180072eb1  jmp     short loc_180072EFE
0x180072eb3  mov     rcx, rsi
0x180072eb6  call    sqlite3VdbeRealValue
0x180072ebb  movaps  xmm3, xmm0
0x180072ebe  lea     r8, a015g; "%!0.15g"
0x180072ec5  movq    r9, xmm0
0x180072eca  mov     rdx, rdi
0x180072ecd  mov     ecx, 64h ; 'd'
0x180072ed2  call    jsonPrintf
0x180072ed7  jmp     short loc_180072EFE
0x180072ed9  mov     dl, 1
0x180072edb  mov     rcx, rsi
0x180072ede  call    sqlite3ValueText
0x180072ee3  mov     dl, 1
0x180072ee5  mov     rcx, rsi
0x180072ee8  mov     rbx, rax
0x180072eeb  call    sqlite3ValueBytes
0x180072ef0  mov     r8d, eax
0x180072ef3  mov     rdx, rbx
0x180072ef6  mov     rcx, rdi
0x180072ef9  call    jsonAppendRaw
0x180072efe  add     rsp, 78h
0x180072f02  pop     rdi
0x180072f03  pop     rsi
0x180072f04  pop     rbp
0x180072f05  pop     rbx
0x180072f06  retn
```
