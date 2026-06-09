# jsonArrayCompute

- ea: `0x180073178`
- end: `0x180073266`
- name: `jsonArrayCompute`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073270`
- `0x1800734e0`

## callees

- `0x180048740`
- `0x180048c00`
- `0x180072b08`
- `0x180073178`
- `0x180076e78`
- `0x180076f78`
- `0x18007734c`
- `0x180086490`
- `0x18008f4f0`
- `0x18008f510`

## pseudocode

```c
__int64 __fastcall jsonArrayCompute(__int64 a1, int a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rbx
  __int64 v7; // rdx
  char v8; // al
  __int64 result; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx

  v4 = (_QWORD *)sqlite3_aggregate_context(a1, 0);
  v6 = v4;
  if ( !v4 )
  {
    sqlite3_result_text(a1, "[]", 2, 0);
    return sqlite3_result_subtype(a1, 74);
  }
  LOBYTE(v5) = 93;
  *v4 = a1;
  jsonAppendChar(v4, v5);
  v8 = sqlite3_user_data(a1, v7);
  if ( *((_BYTE *)v6 + 33) )
    return jsonReturnString(v6, 0, 0);
  if ( (v8 & 8) == 0 )
  {
    v11 = *((unsigned int *)v6 + 6);
    v12 = -1;
    v13 = v6[1];
    if ( a2 )
    {
      if ( !*((_BYTE *)v6 + 32) )
        v12 = (__int64)sqlite3RCStrUnref;
      sqlite3_result_text(a1, v13, v11, v12);
      *((_BYTE *)v6 + 32) = 1;
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
  if ( !*((_BYTE *)v6 + 32) )
    return sqlite3RCStrUnref(v6[1], v10);
  return result;
}

```

## disassembly

```asm
0x180073178  mov     [rsp+arg_0], rbx
0x18007317d  mov     [rsp+arg_8], rsi
0x180073182  push    rdi
0x180073183  sub     rsp, 20h
0x180073187  mov     esi, edx
0x180073189  mov     rdi, rcx
0x18007318c  xor     edx, edx
0x18007318e  call    sqlite3_aggregate_context
0x180073193  mov     rbx, rax
0x180073196  test    rax, rax
0x180073199  jz      loc_180073233
0x18007319f  mov     dl, 5Dh ; ']'
0x1800731a1  mov     [rax], rdi
0x1800731a4  mov     rcx, rax
0x1800731a7  call    jsonAppendChar
0x1800731ac  mov     rcx, rdi
0x1800731af  call    sqlite3_user_data
0x1800731b4  cmp     byte ptr [rbx+21h], 0
0x1800731b8  jz      short loc_1800731CC
0x1800731ba  xor     r8d, r8d
0x1800731bd  xor     edx, edx
0x1800731bf  mov     rcx, rbx
0x1800731c2  call    jsonReturnString
0x1800731c7  jmp     loc_180073256
0x1800731cc  test    al, 8
0x1800731ce  jz      short loc_1800731F7
0x1800731d0  mov     rcx, rbx
0x1800731d3  call    jsonReturnStringAsBlob
0x1800731d8  test    esi, esi
0x1800731da  jz      short loc_1800731ED
0x1800731dc  cmp     byte ptr [rbx+20h], 0
0x1800731e0  jnz     short loc_180073256
0x1800731e2  mov     rcx, [rbx+8]
0x1800731e6  call    sqlite3RCStrUnref
0x1800731eb  jmp     short loc_180073256
0x1800731ed  mov     rcx, rbx
0x1800731f0  call    jsonStringTrimOneChar
0x1800731f5  jmp     short loc_180073256
0x1800731f7  mov     r8d, [rbx+18h]
0x1800731fb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800731ff  mov     rdx, [rbx+8]
0x180073203  mov     rcx, rdi
0x180073206  test    esi, esi
0x180073208  jz      short loc_180073224
0x18007320a  cmp     byte ptr [rbx+20h], 0
0x18007320e  lea     rax, sqlite3RCStrUnref
0x180073215  cmovz   r9, rax
0x180073219  call    sqlite3_result_text
0x18007321e  mov     byte ptr [rbx+20h], 1
0x180073222  jmp     short loc_180073249
0x180073224  call    sqlite3_result_text
0x180073229  mov     rcx, rbx
0x18007322c  call    jsonStringTrimOneChar
0x180073231  jmp     short loc_180073249
0x180073233  xor     r9d, r9d
0x180073236  lea     rdx, asc_1800A62DC; "[]"
0x18007323d  mov     rcx, rdi
0x180073240  lea     r8d, [r9+2]
0x180073244  call    sqlite3_result_text
0x180073249  mov     edx, 4Ah ; 'J'
0x18007324e  mov     rcx, rdi
0x180073251  call    sqlite3_result_subtype
0x180073256  mov     rbx, [rsp+28h+arg_0]
0x18007325b  mov     rsi, [rsp+28h+arg_8]
0x180073260  add     rsp, 20h
0x180073264  pop     rdi
0x180073265  retn
```
