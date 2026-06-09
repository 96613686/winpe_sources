# jsonPatchFunc

- ea: `0x1800686d0`
- end: `0x18006876f`
- name: `jsonPatchFunc`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180067c48`
- `0x1800683e0`
- `0x18006841c`
- `0x1800686d0`
- `0x180068f04`
- `0x180096df0`
- `0x180096e70`

## string_xrefs

- `0x180068743`: `malformed JSON`

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
0x1800686d0  mov     [rsp+arg_0], rbx
0x1800686d5  mov     [rsp+arg_8], rsi
0x1800686da  push    rdi
0x1800686db  sub     rsp, 20h
0x1800686df  mov     rsi, r8
0x1800686e2  mov     rbx, rcx
0x1800686e5  mov     r8d, 1
0x1800686eb  mov     rdx, [rsi]
0x1800686ee  call    jsonParseFuncArg
0x1800686f3  mov     rdi, rax
0x1800686f6  test    rax, rax
0x1800686f9  jz      short loc_18006875F
0x1800686fb  mov     rdx, [rsi+8]
0x1800686ff  xor     r8d, r8d
0x180068702  mov     rcx, rbx
0x180068705  call    jsonParseFuncArg
0x18006870a  mov     rsi, rax
0x18006870d  test    rax, rax
0x180068710  jz      short loc_180068757
0x180068712  xor     r9d, r9d
0x180068715  mov     r8, rax
0x180068718  xor     edx, edx
0x18006871a  mov     rcx, rdi
0x18006871d  call    jsonMergePatch
0x180068722  mov     rcx, rbx
0x180068725  test    eax, eax
0x180068727  jnz     short loc_180068733
0x180068729  mov     rdx, rdi
0x18006872c  call    jsonReturnParse
0x180068731  jmp     short loc_18006874F
0x180068733  cmp     eax, 3
0x180068736  jnz     short loc_18006873F
0x180068738  call    sqlite3_result_error_nomem
0x18006873d  jmp     short loc_18006874F
0x18006873f  or      r8d, 0FFFFFFFFh
0x180068743  lea     rdx, aMalformedJson; "malformed JSON"
0x18006874a  call    sqlite3_result_error
0x18006874f  mov     rcx, rsi
0x180068752  call    jsonParseFree
0x180068757  mov     rcx, rdi
0x18006875a  call    jsonParseFree
0x18006875f  mov     rbx, [rsp+28h+arg_0]
0x180068764  mov     rsi, [rsp+28h+arg_8]
0x180068769  add     rsp, 20h
0x18006876d  pop     rdi
0x18006876e  retn
```
