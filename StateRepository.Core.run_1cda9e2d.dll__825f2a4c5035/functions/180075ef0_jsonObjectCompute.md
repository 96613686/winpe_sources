# jsonObjectCompute

- ea: `0x180075ef0`
- end: `0x180075fde`
- name: `jsonObjectCompute`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075ff0`
- `0x180076230`

## callees

- `0x180048740`
- `0x180048c00`
- `0x180072b08`
- `0x180075ef0`
- `0x180076e78`
- `0x180076f78`
- `0x18007734c`
- `0x180086490`
- `0x18008f4f0`
- `0x18008f510`

## pseudocode

```c
__int64 __fastcall jsonObjectCompute(__int64 a1, int a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rdx
  char v8; // al
  __int64 result; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx

  v4 = sqlite3_aggregate_context(a1, 0);
  v6 = v4;
  if ( !v4 )
  {
    sqlite3_result_text(a1, "{}", 2, 0);
    return sqlite3_result_subtype(a1, 74);
  }
  LOBYTE(v5) = 125;
  jsonAppendChar(v4, v5);
  *(_QWORD *)v6 = a1;
  v8 = sqlite3_user_data(a1, v7);
  if ( *(_BYTE *)(v6 + 33) )
    return jsonReturnString((_QWORD *)v6, 0, 0);
  if ( (v8 & 8) == 0 )
  {
    v11 = *(unsigned int *)(v6 + 24);
    v12 = -1;
    v13 = *(_QWORD *)(v6 + 8);
    if ( a2 )
    {
      if ( !*(_BYTE *)(v6 + 32) )
        v12 = (__int64)sqlite3RCStrUnref;
      sqlite3_result_text(a1, v13, v11, v12);
      *(_BYTE *)(v6 + 32) = 1;
    }
    else
    {
      sqlite3_result_text(a1, v13, v11, -1);
      jsonStringTrimOneChar(v6);
    }
    return sqlite3_result_subtype(a1, 74);
  }
  result = jsonReturnStringAsBlob(v6);
  if ( !a2 )
    return jsonStringTrimOneChar(v6);
  if ( !*(_BYTE *)(v6 + 32) )
    return sqlite3RCStrUnref(*(_QWORD *)(v6 + 8), v10);
  return result;
}

```

## disassembly

```asm
0x180075ef0  mov     [rsp+arg_0], rbx
0x180075ef5  mov     [rsp+arg_8], rsi
0x180075efa  push    rdi
0x180075efb  sub     rsp, 20h
0x180075eff  mov     esi, edx
0x180075f01  mov     rdi, rcx
0x180075f04  xor     edx, edx
0x180075f06  call    sqlite3_aggregate_context
0x180075f0b  mov     rbx, rax
0x180075f0e  test    rax, rax
0x180075f11  jz      loc_180075FAB
0x180075f17  mov     dl, 7Dh ; '}'
0x180075f19  mov     rcx, rax
0x180075f1c  call    jsonAppendChar
0x180075f21  mov     rcx, rdi
0x180075f24  mov     [rbx], rdi
0x180075f27  call    sqlite3_user_data
0x180075f2c  cmp     byte ptr [rbx+21h], 0
0x180075f30  jz      short loc_180075F44
0x180075f32  xor     r8d, r8d
0x180075f35  xor     edx, edx
0x180075f37  mov     rcx, rbx
0x180075f3a  call    jsonReturnString
0x180075f3f  jmp     loc_180075FCE
0x180075f44  test    al, 8
0x180075f46  jz      short loc_180075F6F
0x180075f48  mov     rcx, rbx
0x180075f4b  call    jsonReturnStringAsBlob
0x180075f50  test    esi, esi
0x180075f52  jz      short loc_180075F65
0x180075f54  cmp     byte ptr [rbx+20h], 0
0x180075f58  jnz     short loc_180075FCE
0x180075f5a  mov     rcx, [rbx+8]
0x180075f5e  call    sqlite3RCStrUnref
0x180075f63  jmp     short loc_180075FCE
0x180075f65  mov     rcx, rbx
0x180075f68  call    jsonStringTrimOneChar
0x180075f6d  jmp     short loc_180075FCE
0x180075f6f  mov     r8d, [rbx+18h]
0x180075f73  or      r9, 0FFFFFFFFFFFFFFFFh
0x180075f77  mov     rdx, [rbx+8]
0x180075f7b  mov     rcx, rdi
0x180075f7e  test    esi, esi
0x180075f80  jz      short loc_180075F9C
0x180075f82  cmp     byte ptr [rbx+20h], 0
0x180075f86  lea     rax, sqlite3RCStrUnref
0x180075f8d  cmovz   r9, rax
0x180075f91  call    sqlite3_result_text
0x180075f96  mov     byte ptr [rbx+20h], 1
0x180075f9a  jmp     short loc_180075FC1
0x180075f9c  call    sqlite3_result_text
0x180075fa1  mov     rcx, rbx
0x180075fa4  call    jsonStringTrimOneChar
0x180075fa9  jmp     short loc_180075FC1
0x180075fab  xor     r9d, r9d
0x180075fae  lea     rdx, asc_1800A62E0; "{}"
0x180075fb5  mov     rcx, rdi
0x180075fb8  lea     r8d, [r9+2]
0x180075fbc  call    sqlite3_result_text
0x180075fc1  mov     edx, 4Ah ; 'J'
0x180075fc6  mov     rcx, rdi
0x180075fc9  call    sqlite3_result_subtype
0x180075fce  mov     rbx, [rsp+28h+arg_0]
0x180075fd3  mov     rsi, [rsp+28h+arg_8]
0x180075fd8  add     rsp, 20h
0x180075fdc  pop     rdi
0x180075fdd  retn
```
