# jsonPatchFunc

- ea: `0x180076530`
- end: `0x1800765cf`
- name: `jsonPatchFunc`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180068190`
- `0x180075a9c`
- `0x180076240`
- `0x18007627c`
- `0x180076530`
- `0x180076d64`
- `0x18008f3f0`

## string_xrefs

- `0x1800765a3`: `malformed JSON`

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
0x180076530  mov     [rsp+arg_0], rbx
0x180076535  mov     [rsp+arg_8], rsi
0x18007653a  push    rdi
0x18007653b  sub     rsp, 20h
0x18007653f  mov     rsi, r8
0x180076542  mov     rbx, rcx
0x180076545  mov     r8d, 1
0x18007654b  mov     rdx, [rsi]
0x18007654e  call    jsonParseFuncArg
0x180076553  mov     rdi, rax
0x180076556  test    rax, rax
0x180076559  jz      short loc_1800765BF
0x18007655b  mov     rdx, [rsi+8]
0x18007655f  xor     r8d, r8d
0x180076562  mov     rcx, rbx
0x180076565  call    jsonParseFuncArg
0x18007656a  mov     rsi, rax
0x18007656d  test    rax, rax
0x180076570  jz      short loc_1800765B7
0x180076572  xor     r9d, r9d
0x180076575  mov     r8, rax
0x180076578  xor     edx, edx
0x18007657a  mov     rcx, rdi
0x18007657d  call    jsonMergePatch
0x180076582  mov     rcx, rbx
0x180076585  test    eax, eax
0x180076587  jnz     short loc_180076593
0x180076589  mov     rdx, rdi
0x18007658c  call    jsonReturnParse
0x180076591  jmp     short loc_1800765AF
0x180076593  cmp     eax, 3
0x180076596  jnz     short loc_18007659F
0x180076598  call    sqlite3_result_error_nomem
0x18007659d  jmp     short loc_1800765AF
0x18007659f  or      r8d, 0FFFFFFFFh
0x1800765a3  lea     rdx, aMalformedJson; "malformed JSON"
0x1800765aa  call    sqlite3_result_error
0x1800765af  mov     rcx, rsi
0x1800765b2  call    jsonParseFree
0x1800765b7  mov     rcx, rdi
0x1800765ba  call    jsonParseFree
0x1800765bf  mov     rbx, [rsp+28h+arg_0]
0x1800765c4  mov     rsi, [rsp+28h+arg_8]
0x1800765c9  add     rsp, 20h
0x1800765cd  pop     rdi
0x1800765ce  retn
```
