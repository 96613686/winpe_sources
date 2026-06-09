# jsonAppendSqlValue

- ea: `0x18004d5bc`
- end: `0x18004d743`
- name: `jsonAppendSqlValue`
- size: `391`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18004da80`
- `0x18004dca0`
- `0x180050850`
- `0x180050a20`
- `0x180051180`

## callees

- `0x180002cf8`
- `0x18004d4e8`
- `0x18004d538`
- `0x18004d5bc`
- `0x18004d74c`
- `0x18004f598`
- `0x1800510fc`
- `0x180051dfc`
- `0x180052118`
- `0x180092290`
- `0x18009b4ec`
- `0x18009c204`
- `0x1800ae6c0`
- `0x1800ae720`

## string_xrefs

- `0x18004d665`: `JSON cannot hold BLOB values`

## pseudocode

```c
__int64 __fastcall jsonAppendSqlValue(__int64 *a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 result; // rax
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // eax
  double v9; // xmm0_8
  __int64 v10; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+38h] [rbp-50h]

  v3 = a2;
  switch ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(a2 + 20) & 0x3F)) )
  {
    case 1:
      LOBYTE(a2) = 1;
      v7 = sqlite3ValueText(v3, a2);
      v8 = sqlite3_value_bytes(v3);
      return jsonAppendRaw(a1, v7, v8);
    case 2:
      v9 = sqlite3VdbeRealValue(a2);
      return jsonPrintf(100, a1, "%!0.15g", v9);
    case 3:
      LOBYTE(a2) = 1;
      v7 = sqlite3ValueText(v3, a2);
      v8 = sqlite3_value_bytes(v3);
      if ( (*(_WORD *)(v3 + 20) & 0x800) == 0 || *(_BYTE *)(v3 + 23) != 74 )
        return jsonAppendString(a1, v7, v8);
      return jsonAppendRaw(a1, v7, v8);
    case 5:
      return jsonAppendRawNZ(a1, "null", 4);
  }
  result = jsonFuncArgMightBeBinary(a2);
  if ( (_DWORD)result )
  {
    memset_0(&v10, 0, 0x48u);
    v10 = sqlite3_value_blob(v3);
    v11 = sqlite3_value_bytes(v3);
    return jsonTranslateBlobToText(&v10, 0, a1);
  }
  else if ( !*((_BYTE *)a1 + 33) )
  {
    v6 = *a1;
    LOBYTE(v5) = 1;
    *(_DWORD *)(v6 + 36) = 1;
    sqlite3VdbeMemSetStr(*(_QWORD *)v6, "JSON cannot hold BLOB values", -1, v5, -1);
    *((_BYTE *)a1 + 33) = 4;
    return jsonStringReset(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18004d5bc  mov     [rsp+arg_0], rbx
0x18004d5c1  mov     [rsp+arg_8], rsi
0x18004d5c6  push    rdi
0x18004d5c7  sub     rsp, 80h
0x18004d5ce  movzx   eax, word ptr [rdx+14h]
0x18004d5d2  mov     rdi, rcx
0x18004d5d5  and     eax, 3Fh
0x18004d5d8  lea     rcx, qword_1800FE430
0x18004d5df  mov     rsi, rdx
0x18004d5e2  movzx   r8d, byte ptr [rax+rcx]
0x18004d5e7  sub     r8d, 1
0x18004d5eb  jz      loc_18004D70B
0x18004d5f1  sub     r8d, 1
0x18004d5f5  jz      loc_18004D6E5
0x18004d5fb  sub     r8d, 1
0x18004d5ff  jz      loc_18004D6AF
0x18004d605  cmp     r8d, 2
0x18004d609  jz      loc_18004D698
0x18004d60f  mov     rcx, rdx
0x18004d612  call    jsonFuncArgMightBeBinary
0x18004d617  test    eax, eax
0x18004d619  jz      short loc_18004D658
0x18004d61b  xor     edx, edx; Val
0x18004d61d  lea     rcx, [rsp+88h+var_58]; void *
0x18004d622  lea     r8d, [rdx+48h]; Size
0x18004d626  call    memset_0
0x18004d62b  mov     rcx, rsi
0x18004d62e  call    sqlite3_value_blob
0x18004d633  mov     rcx, rsi
0x18004d636  mov     [rsp+88h+var_58], rax
0x18004d63b  call    sqlite3_value_bytes
0x18004d640  mov     r8, rdi
0x18004d643  mov     [rsp+88h+var_50], eax
0x18004d647  xor     edx, edx
0x18004d649  lea     rcx, [rsp+88h+var_58]
0x18004d64e  call    jsonTranslateBlobToText
0x18004d653  jmp     loc_18004D72E
0x18004d658  cmp     byte ptr [rdi+21h], 0
0x18004d65c  jnz     loc_18004D72E
0x18004d662  mov     rcx, [rdi]
0x18004d665  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x18004d66c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d670  mov     r9b, 1
0x18004d673  mov     [rsp+88h+var_68], r8
0x18004d678  mov     dword ptr [rcx+24h], 1
0x18004d67f  mov     rcx, [rcx]
0x18004d682  call    sqlite3VdbeMemSetStr
0x18004d687  mov     rcx, rdi
0x18004d68a  mov     byte ptr [rdi+21h], 4
0x18004d68e  call    jsonStringReset
0x18004d693  jmp     loc_18004D72E
0x18004d698  mov     r8d, 4
0x18004d69e  lea     rdx, aNull_2; "null"
0x18004d6a5  mov     rcx, rdi
0x18004d6a8  call    jsonAppendRawNZ
0x18004d6ad  jmp     short loc_18004D72E
0x18004d6af  mov     dl, 1
0x18004d6b1  mov     rcx, rsi
0x18004d6b4  call    sqlite3ValueText
0x18004d6b9  mov     rcx, rsi
0x18004d6bc  mov     rbx, rax
0x18004d6bf  call    sqlite3_value_bytes
0x18004d6c4  mov     ecx, 800h
0x18004d6c9  test    [rsi+14h], cx
0x18004d6cd  jz      short loc_18004D6D5
0x18004d6cf  cmp     byte ptr [rsi+17h], 4Ah ; 'J'
0x18004d6d3  jz      short loc_18004D720
0x18004d6d5  mov     r8d, eax
0x18004d6d8  mov     rdx, rbx
0x18004d6db  mov     rcx, rdi
0x18004d6de  call    jsonAppendString
0x18004d6e3  jmp     short loc_18004D72E
0x18004d6e5  mov     rcx, rsi
0x18004d6e8  call    sqlite3VdbeRealValue
0x18004d6ed  movaps  xmm3, xmm0
0x18004d6f0  lea     r8, a015g; "%!0.15g"
0x18004d6f7  movq    r9, xmm0
0x18004d6fc  mov     rdx, rdi
0x18004d6ff  mov     ecx, 64h ; 'd'
0x18004d704  call    jsonPrintf
0x18004d709  jmp     short loc_18004D72E
0x18004d70b  mov     dl, 1
0x18004d70d  mov     rcx, rsi
0x18004d710  call    sqlite3ValueText
0x18004d715  mov     rcx, rsi
0x18004d718  mov     rbx, rax
0x18004d71b  call    sqlite3_value_bytes
0x18004d720  mov     r8d, eax
0x18004d723  mov     rdx, rbx
0x18004d726  mov     rcx, rdi
0x18004d729  call    jsonAppendRaw
0x18004d72e  lea     r11, [rsp+88h+var_8]
0x18004d736  mov     rbx, [r11+10h]
0x18004d73a  mov     rsi, [r11+18h]
0x18004d73e  mov     rsp, r11
0x18004d741  pop     rdi
0x18004d742  retn
```
