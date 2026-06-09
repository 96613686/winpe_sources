# jsonAppendSqlValue

- ea: `0x180064ffc`
- end: `0x18006515f`
- name: `jsonAppendSqlValue`
- size: `355`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800654e0`
- `0x1800656b0`
- `0x1800681a0`
- `0x180068320`
- `0x180068950`

## callees

- `0x180042dc4`
- `0x180045374`
- `0x180064f30`
- `0x180064f80`
- `0x180064ffc`
- `0x180065168`
- `0x180066ed4`
- `0x1800688cc`
- `0x180069474`
- `0x1800696ac`
- `0x18008c97c`
- `0x18008eb70`
- `0x180096df0`
- `0x180098a80`
- `0x180098ce0`

## string_xrefs

- `0x18006509a`: `JSON cannot hold BLOB values`

## pseudocode

```c
__int64 __fastcall jsonAppendSqlValue(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned int v10; // ebp
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  double v15; // xmm0_8
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // [rsp+20h] [rbp-78h] BYREF
  int v20; // [rsp+28h] [rbp-70h]

  v3 = a2;
  switch ( *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(a2 + 20) & 0x3F)) )
  {
    case 1:
      LOBYTE(a2) = 1;
      v16 = sqlite3ValueText(v3, a2);
      LOBYTE(v17) = 1;
      v18 = v16;
      v12 = (unsigned int)sqlite3ValueBytes(v3, v17);
      v13 = v18;
      v14 = a1;
      return jsonAppendRaw(v14, v13, v12);
    case 2:
      v15 = sqlite3VdbeRealValue(
              a2,
              a2,
              (unsigned int)*((unsigned __int8 *)qword_1800B9DC0 + (*(_WORD *)(a2 + 20) & 0x3F)) - 2);
      return jsonPrintf(100, a1, "%!0.15g", v15);
    case 3:
      LOBYTE(a2) = 1;
      v7 = sqlite3ValueText(v3, a2);
      LOBYTE(v8) = 1;
      v9 = v7;
      v10 = sqlite3ValueBytes(v3, v8);
      v11 = sqlite3_value_subtype(v3);
      v12 = v10;
      v13 = v9;
      v14 = a1;
      if ( v11 != 74 )
        return jsonAppendString(a1, v9, v10);
      return jsonAppendRaw(v14, v13, v12);
    case 5:
      return jsonAppendRawNZ(a1, "null", 4);
  }
  result = jsonFuncArgMightBeBinary(a2);
  if ( (_DWORD)result )
  {
    memset_0(&v19, 0, 0x48u);
    v5 = sqlite3_value_blob(v3);
    LOBYTE(v6) = 1;
    v19 = v5;
    v20 = sqlite3ValueBytes(v3, v6);
    return jsonTranslateBlobToText(&v19, 0, a1);
  }
  else if ( !*(_BYTE *)(a1 + 33) )
  {
    sqlite3_result_error(*(_QWORD *)a1, "JSON cannot hold BLOB values", 0xFFFFFFFFLL);
    *(_BYTE *)(a1 + 33) = 4;
    return jsonStringReset(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180064ffc  push    rbx
0x180064ffe  push    rbp
0x180064fff  push    rsi
0x180065000  push    rdi
0x180065001  sub     rsp, 78h
0x180065005  movzx   eax, word ptr [rdx+14h]
0x180065009  mov     rdi, rcx
0x18006500c  and     eax, 3Fh
0x18006500f  lea     rcx, qword_1800B9DC0
0x180065016  mov     rsi, rdx
0x180065019  movzx   r8d, byte ptr [rax+rcx]
0x18006501e  sub     r8d, 1
0x180065022  jz      loc_180065131
0x180065028  sub     r8d, 1
0x18006502c  jz      loc_18006510B
0x180065032  sub     r8d, 1
0x180065036  jz      loc_1800650D5
0x18006503c  cmp     r8d, 2
0x180065040  jz      short loc_1800650BB
0x180065042  mov     rcx, rdx
0x180065045  call    jsonFuncArgMightBeBinary
0x18006504a  test    eax, eax
0x18006504c  jz      short loc_18006508D
0x18006504e  xor     edx, edx; Val
0x180065050  lea     rcx, [rsp+98h+var_78]; void *
0x180065055  lea     r8d, [rdx+48h]; Size
0x180065059  call    memset_0
0x18006505e  mov     rcx, rsi
0x180065061  call    sqlite3_value_blob
0x180065066  mov     dl, 1
0x180065068  mov     [rsp+98h+var_78], rax
0x18006506d  mov     rcx, rsi
0x180065070  call    sqlite3ValueBytes
0x180065075  mov     r8, rdi
0x180065078  mov     [rsp+98h+var_70], eax
0x18006507c  xor     edx, edx
0x18006507e  lea     rcx, [rsp+98h+var_78]
0x180065083  call    jsonTranslateBlobToText
0x180065088  jmp     loc_180065156
0x18006508d  cmp     byte ptr [rdi+21h], 0
0x180065091  jnz     loc_180065156
0x180065097  mov     rcx, [rdi]
0x18006509a  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x1800650a1  or      r8d, 0FFFFFFFFh
0x1800650a5  call    sqlite3_result_error
0x1800650aa  mov     rcx, rdi
0x1800650ad  mov     byte ptr [rdi+21h], 4
0x1800650b1  call    jsonStringReset
0x1800650b6  jmp     loc_180065156
0x1800650bb  mov     r8d, 4
0x1800650c1  lea     rdx, aNull_3; "null"
0x1800650c8  mov     rcx, rdi
0x1800650cb  call    jsonAppendRawNZ
0x1800650d0  jmp     loc_180065156
0x1800650d5  mov     dl, 1
0x1800650d7  mov     rcx, rsi
0x1800650da  call    sqlite3ValueText
0x1800650df  mov     dl, 1
0x1800650e1  mov     rcx, rsi
0x1800650e4  mov     rbx, rax
0x1800650e7  call    sqlite3ValueBytes
0x1800650ec  mov     rcx, rsi
0x1800650ef  mov     ebp, eax
0x1800650f1  call    sqlite3_value_subtype
0x1800650f6  mov     r8d, ebp
0x1800650f9  mov     rdx, rbx
0x1800650fc  mov     rcx, rdi
0x1800650ff  cmp     eax, 4Ah ; 'J'
0x180065102  jz      short loc_180065151
0x180065104  call    jsonAppendString
0x180065109  jmp     short loc_180065156
0x18006510b  mov     rcx, rsi
0x18006510e  call    sqlite3VdbeRealValue
0x180065113  movaps  xmm3, xmm0
0x180065116  lea     r8, a015g; "%!0.15g"
0x18006511d  movq    r9, xmm0
0x180065122  mov     rdx, rdi
0x180065125  mov     ecx, 64h ; 'd'
0x18006512a  call    jsonPrintf
0x18006512f  jmp     short loc_180065156
0x180065131  mov     dl, 1
0x180065133  mov     rcx, rsi
0x180065136  call    sqlite3ValueText
0x18006513b  mov     dl, 1
0x18006513d  mov     rcx, rsi
0x180065140  mov     rbx, rax
0x180065143  call    sqlite3ValueBytes
0x180065148  mov     r8d, eax
0x18006514b  mov     rdx, rbx
0x18006514e  mov     rcx, rdi
0x180065151  call    jsonAppendRaw
0x180065156  add     rsp, 78h
0x18006515a  pop     rdi
0x18006515b  pop     rsi
0x18006515c  pop     rbp
0x18006515d  pop     rbx
0x18006515e  retn
```
