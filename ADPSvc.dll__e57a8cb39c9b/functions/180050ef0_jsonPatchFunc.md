# jsonPatchFunc

- ea: `0x180050ef0`
- end: `0x180050fa4`
- name: `jsonPatchFunc`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180050268`
- `0x180050b30`
- `0x180050b6c`
- `0x180050ef0`
- `0x180051828`
- `0x18009b4ec`
- `0x1800ab280`

## string_xrefs

- `0x180050f65`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonPatchFunc(_DWORD *a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rcx

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
        {
          sqlite3_result_error_nomem(a1);
        }
        else
        {
          v11 = *(_QWORD *)a1;
          a1[9] = 1;
          LOBYTE(v10) = 1;
          sqlite3VdbeMemSetStr(v11, "malformed JSON", -1, v10, -1);
        }
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
0x180050ef0  mov     [rsp+arg_0], rbx
0x180050ef5  mov     [rsp+arg_8], rsi
0x180050efa  push    rdi
0x180050efb  sub     rsp, 30h
0x180050eff  mov     rsi, r8
0x180050f02  mov     rbx, rcx
0x180050f05  mov     r8d, 1
0x180050f0b  mov     rdx, [rsi]
0x180050f0e  call    jsonParseFuncArg
0x180050f13  mov     rdi, rax
0x180050f16  test    rax, rax
0x180050f19  jz      short loc_180050F94
0x180050f1b  mov     rdx, [rsi+8]
0x180050f1f  xor     r8d, r8d
0x180050f22  mov     rcx, rbx
0x180050f25  call    jsonParseFuncArg
0x180050f2a  mov     rsi, rax
0x180050f2d  test    rax, rax
0x180050f30  jz      short loc_180050F8C
0x180050f32  xor     r9d, r9d
0x180050f35  mov     r8, rax
0x180050f38  xor     edx, edx
0x180050f3a  mov     rcx, rdi
0x180050f3d  call    jsonMergePatch
0x180050f42  test    eax, eax
0x180050f44  jnz     short loc_180050F53
0x180050f46  mov     rdx, rdi
0x180050f49  mov     rcx, rbx
0x180050f4c  call    jsonReturnParse
0x180050f51  jmp     short loc_180050F84
0x180050f53  cmp     eax, 3
0x180050f56  jnz     short loc_180050F62
0x180050f58  mov     rcx, rbx
0x180050f5b  call    sqlite3_result_error_nomem
0x180050f60  jmp     short loc_180050F84
0x180050f62  mov     rcx, [rbx]
0x180050f65  lea     rdx, aMalformedJson; "malformed JSON"
0x180050f6c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180050f70  mov     dword ptr [rbx+24h], 1
0x180050f77  mov     r9b, 1
0x180050f7a  mov     [rsp+38h+var_18], r8
0x180050f7f  call    sqlite3VdbeMemSetStr
0x180050f84  mov     rcx, rsi
0x180050f87  call    jsonParseFree
0x180050f8c  mov     rcx, rdi
0x180050f8f  call    jsonParseFree
0x180050f94  mov     rbx, [rsp+38h+arg_0]
0x180050f99  mov     rsi, [rsp+38h+arg_8]
0x180050f9e  add     rsp, 30h
0x180050fa2  pop     rdi
0x180050fa3  retn
```
