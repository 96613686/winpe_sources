# jsonPatchFunc

- ea: `0x180085740`
- end: `0x1800857df`
- name: `jsonPatchFunc`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180084cb8`
- `0x180085450`
- `0x18008548c`
- `0x180085740`
- `0x180085f74`
- `0x18009d650`
- `0x18009d6d0`

## string_xrefs

- `0x1800857b3`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonPatchFunc(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  int v9; // eax

  result = jsonParseFuncArg(a1, *a3, 1);
  v6 = result;
  if ( result )
  {
    v7 = jsonParseFuncArg(a1, a3[1], 0);
    v8 = v7;
    if ( v7 )
    {
      v9 = jsonMergePatch(v6, 0, v7, 0);
      if ( v9 )
      {
        if ( v9 == 3 )
          sqlite3_result_error_nomem(a1);
        else
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
      }
      else
      {
        jsonReturnParse(a1, v6);
      }
      jsonParseFree(v8);
    }
    return jsonParseFree(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180085740  mov     [rsp+arg_0], rbx
0x180085745  mov     [rsp+arg_8], rsi
0x18008574a  push    rdi
0x18008574b  sub     rsp, 20h
0x18008574f  mov     rsi, r8
0x180085752  mov     rbx, rcx
0x180085755  mov     r8d, 1
0x18008575b  mov     rdx, [rsi]
0x18008575e  call    jsonParseFuncArg
0x180085763  mov     rdi, rax
0x180085766  test    rax, rax
0x180085769  jz      short loc_1800857CF
0x18008576b  mov     rdx, [rsi+8]
0x18008576f  xor     r8d, r8d
0x180085772  mov     rcx, rbx
0x180085775  call    jsonParseFuncArg
0x18008577a  mov     rsi, rax
0x18008577d  test    rax, rax
0x180085780  jz      short loc_1800857C7
0x180085782  xor     r9d, r9d
0x180085785  mov     r8, rax
0x180085788  xor     edx, edx
0x18008578a  mov     rcx, rdi
0x18008578d  call    jsonMergePatch
0x180085792  mov     rcx, rbx
0x180085795  test    eax, eax
0x180085797  jnz     short loc_1800857A3
0x180085799  mov     rdx, rdi
0x18008579c  call    jsonReturnParse
0x1800857a1  jmp     short loc_1800857BF
0x1800857a3  cmp     eax, 3
0x1800857a6  jnz     short loc_1800857AF
0x1800857a8  call    sqlite3_result_error_nomem
0x1800857ad  jmp     short loc_1800857BF
0x1800857af  or      r8d, 0FFFFFFFFh
0x1800857b3  lea     rdx, aMalformedJson; "malformed JSON"
0x1800857ba  call    sqlite3_result_error
0x1800857bf  mov     rcx, rsi
0x1800857c2  call    jsonParseFree
0x1800857c7  mov     rcx, rdi
0x1800857ca  call    jsonParseFree
0x1800857cf  mov     rbx, [rsp+28h+arg_0]
0x1800857d4  mov     rsi, [rsp+28h+arg_8]
0x1800857d9  add     rsp, 20h
0x1800857dd  pop     rdi
0x1800857de  retn
```
