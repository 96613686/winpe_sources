# jsonAppendSqlValue

- ea: `0x18008200c`
- end: `0x18008216f`
- name: `jsonAppendSqlValue`
- size: `355`
- prototype: `void *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800824f0`
- `0x1800826c0`
- `0x180085210`
- `0x180085390`
- `0x1800859c0`

## callees

- `0x180024b60`
- `0x18004c5f0`
- `0x180054e70`
- `0x180054ef4`
- `0x180078968`
- `0x180081f40`
- `0x180081f90`
- `0x18008200c`
- `0x180082178`
- `0x180083f44`
- `0x18008593c`
- `0x1800864e4`
- `0x18008671c`
- `0x18009d650`
- `0x18009ee40`

## string_xrefs

- `0x1800820aa`: `JSON cannot hold BLOB values`

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
  switch ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a2 + 20) & 0x3F)) )
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
0x18008200c  push    rbx
0x18008200e  push    rbp
0x18008200f  push    rsi
0x180082010  push    rdi
0x180082011  sub     rsp, 78h
0x180082015  movzx   eax, word ptr [rdx+14h]
0x180082019  mov     rdi, rcx
0x18008201c  and     eax, 3Fh
0x18008201f  lea     rcx, qword_1800B5270
0x180082026  mov     rsi, rdx
0x180082029  movzx   r8d, byte ptr [rax+rcx]
0x18008202e  sub     r8d, 1
0x180082032  jz      loc_180082141
0x180082038  sub     r8d, 1
0x18008203c  jz      loc_18008211B
0x180082042  sub     r8d, 1
0x180082046  jz      loc_1800820E5
0x18008204c  cmp     r8d, 2
0x180082050  jz      short loc_1800820CB
0x180082052  mov     rcx, rdx
0x180082055  call    jsonFuncArgMightBeBinary
0x18008205a  test    eax, eax
0x18008205c  jz      short loc_18008209D
0x18008205e  xor     edx, edx; Val
0x180082060  lea     rcx, [rsp+98h+var_78]; void *
0x180082065  lea     r8d, [rdx+48h]; Size
0x180082069  call    memset_0
0x18008206e  mov     rcx, rsi
0x180082071  call    sqlite3_value_blob
0x180082076  mov     dl, 1
0x180082078  mov     [rsp+98h+var_78], rax
0x18008207d  mov     rcx, rsi
0x180082080  call    sqlite3ValueBytes
0x180082085  mov     r8, rdi
0x180082088  mov     [rsp+98h+var_70], eax
0x18008208c  xor     edx, edx
0x18008208e  lea     rcx, [rsp+98h+var_78]
0x180082093  call    jsonTranslateBlobToText
0x180082098  jmp     loc_180082166
0x18008209d  cmp     byte ptr [rdi+21h], 0
0x1800820a1  jnz     loc_180082166
0x1800820a7  mov     rcx, [rdi]
0x1800820aa  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x1800820b1  or      r8d, 0FFFFFFFFh
0x1800820b5  call    sqlite3_result_error
0x1800820ba  mov     rcx, rdi
0x1800820bd  mov     byte ptr [rdi+21h], 4
0x1800820c1  call    jsonStringReset
0x1800820c6  jmp     loc_180082166
0x1800820cb  mov     r8d, 4
0x1800820d1  lea     rdx, aNull_2; "null"
0x1800820d8  mov     rcx, rdi
0x1800820db  call    jsonAppendRawNZ
0x1800820e0  jmp     loc_180082166
0x1800820e5  mov     dl, 1
0x1800820e7  mov     rcx, rsi
0x1800820ea  call    sqlite3ValueText
0x1800820ef  mov     dl, 1
0x1800820f1  mov     rcx, rsi
0x1800820f4  mov     rbx, rax
0x1800820f7  call    sqlite3ValueBytes
0x1800820fc  mov     rcx, rsi
0x1800820ff  mov     ebp, eax
0x180082101  call    sqlite3_value_subtype
0x180082106  mov     r8d, ebp
0x180082109  mov     rdx, rbx
0x18008210c  mov     rcx, rdi
0x18008210f  cmp     eax, 4Ah ; 'J'
0x180082112  jz      short loc_180082161
0x180082114  call    jsonAppendString
0x180082119  jmp     short loc_180082166
0x18008211b  mov     rcx, rsi
0x18008211e  call    sqlite3VdbeRealValue
0x180082123  movaps  xmm3, xmm0
0x180082126  lea     r8, a015g; "%!0.15g"
0x18008212d  movq    r9, xmm0
0x180082132  mov     rdx, rdi
0x180082135  mov     ecx, 64h ; 'd'
0x18008213a  call    jsonPrintf
0x18008213f  jmp     short loc_180082166
0x180082141  mov     dl, 1
0x180082143  mov     rcx, rsi
0x180082146  call    sqlite3ValueText
0x18008214b  mov     dl, 1
0x18008214d  mov     rcx, rsi
0x180082150  mov     rbx, rax
0x180082153  call    sqlite3ValueBytes
0x180082158  mov     r8d, eax
0x18008215b  mov     rdx, rbx
0x18008215e  mov     rcx, rdi
0x180082161  call    jsonAppendRaw
0x180082166  add     rsp, 78h
0x18008216a  pop     rdi
0x18008216b  pop     rsi
0x18008216c  pop     rbp
0x18008216d  pop     rbx
0x18008216e  retn
```
