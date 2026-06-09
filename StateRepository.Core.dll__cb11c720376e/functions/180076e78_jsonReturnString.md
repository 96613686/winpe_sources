# jsonReturnString

- ea: `0x180076e78`
- end: `0x180076f6f`
- name: `jsonReturnString`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180073178`
- `0x180073280`
- `0x180074920`
- `0x180075ef0`
- `0x180076000`
- `0x1800765e0`
- `0x1800767b0`
- `0x180076d64`
- `0x180077008`

## callees

- `0x180048740`
- `0x180067570`
- `0x180068190`
- `0x180073a54`
- `0x180076e78`
- `0x180076f78`
- `0x1800772d4`
- `0x180077320`
- `0x18008f3f0`

## string_xrefs

- `0x180076f48`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonReturnString(_QWORD *a1, __int64 a2, __int64 a3)
{
  char v3; // al
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(_QWORD); // r9
  __int64 v9; // rax
  __int64 v10; // rcx

  v3 = *((_BYTE *)a1 + 33);
  if ( !v3 )
  {
    if ( (sqlite3_user_data(*a1) & 8) != 0 )
    {
      jsonReturnStringAsBlob(a1);
      return jsonStringReset(a1);
    }
    if ( *((_BYTE *)a1 + 32) )
    {
      v7 = a1[1];
      LODWORD(v8) = -1;
LABEL_13:
      sqlite3_result_text64(*a1, v7, a1[3], (_DWORD)v8, 1);
      return jsonStringReset(a1);
    }
    if ( (unsigned int)jsonStringTerminate(a1) )
    {
      if ( !a2
        || *(_BYTE *)(a2 + 48)
        || !*(_DWORD *)(a2 + 12)
        || (v9 = a1[1],
            ++*(_QWORD *)(v9 - 8),
            *(_QWORD *)(a2 + 16) = v9,
            *(_DWORD *)(a2 + 32) = *((_DWORD *)a1 + 6),
            *(_BYTE *)(a2 + 48) = 1,
            (unsigned int)jsonCacheInsert(a3, a2) != 7) )
      {
        v7 = a1[1];
        v8 = sqlite3RCStrUnref;
        ++*(_QWORD *)(v7 - 8);
        goto LABEL_13;
      }
      v10 = a3;
    }
    else
    {
      v10 = *a1;
    }
LABEL_17:
    sqlite3_result_error_nomem(v10);
    return jsonStringReset(a1);
  }
  if ( (v3 & 1) != 0 )
  {
    v10 = *a1;
    goto LABEL_17;
  }
  if ( (v3 & 2) != 0 )
    sqlite3_result_error(*a1, "malformed JSON", 0xFFFFFFFFLL);
  return jsonStringReset(a1);
}

```

## disassembly

```asm
0x180076e78  mov     [rsp+arg_0], rbx
0x180076e7d  mov     [rsp+arg_8], rsi
0x180076e82  push    rdi
0x180076e83  sub     rsp, 30h
0x180076e87  mov     al, [rcx+21h]
0x180076e8a  mov     rsi, r8
0x180076e8d  mov     rdi, rdx
0x180076e90  mov     rbx, rcx
0x180076e93  test    al, al
0x180076e95  jnz     loc_180076F33
0x180076e9b  mov     rcx, [rcx]
0x180076e9e  call    sqlite3_user_data
0x180076ea3  test    al, 8
0x180076ea5  jz      short loc_180076EB4
0x180076ea7  mov     rcx, rbx
0x180076eaa  call    jsonReturnStringAsBlob
0x180076eaf  jmp     loc_180076F58
0x180076eb4  cmp     byte ptr [rbx+20h], 0
0x180076eb8  jz      short loc_180076EC4
0x180076eba  mov     rdx, [rbx+8]
0x180076ebe  or      r9, 0FFFFFFFFFFFFFFFFh
0x180076ec2  jmp     short loc_180076F1B
0x180076ec4  mov     rcx, rbx
0x180076ec7  call    jsonStringTerminate
0x180076ecc  test    eax, eax
0x180076ece  jz      short loc_180076F2E
0x180076ed0  test    rdi, rdi
0x180076ed3  jz      short loc_180076F0C
0x180076ed5  cmp     byte ptr [rdi+30h], 0
0x180076ed9  jnz     short loc_180076F0C
0x180076edb  cmp     dword ptr [rdi+0Ch], 0
0x180076edf  jbe     short loc_180076F0C
0x180076ee1  mov     rax, [rbx+8]
0x180076ee5  mov     rdx, rdi
0x180076ee8  mov     rcx, rsi
0x180076eeb  inc     qword ptr [rax-8]
0x180076eef  mov     [rdi+10h], rax
0x180076ef3  mov     eax, [rbx+18h]
0x180076ef6  mov     [rdi+20h], eax
0x180076ef9  mov     byte ptr [rdi+30h], 1
0x180076efd  call    jsonCacheInsert
0x180076f02  cmp     eax, 7
0x180076f05  jnz     short loc_180076F0C
0x180076f07  mov     rcx, rsi
0x180076f0a  jmp     short loc_180076F3A
0x180076f0c  mov     rdx, [rbx+8]
0x180076f10  lea     r9, sqlite3RCStrUnref
0x180076f17  inc     qword ptr [rdx-8]
0x180076f1b  mov     r8, [rbx+18h]
0x180076f1f  mov     rcx, [rbx]
0x180076f22  mov     [rsp+38h+var_18], 1
0x180076f27  call    sqlite3_result_text64
0x180076f2c  jmp     short loc_180076F58
0x180076f2e  mov     rcx, [rbx]
0x180076f31  jmp     short loc_180076F3A
0x180076f33  test    al, 1
0x180076f35  jz      short loc_180076F41
0x180076f37  mov     rcx, [rcx]
0x180076f3a  call    sqlite3_result_error_nomem
0x180076f3f  jmp     short loc_180076F58
0x180076f41  test    al, 2
0x180076f43  jz      short loc_180076F58
0x180076f45  mov     rcx, [rcx]
0x180076f48  lea     rdx, aMalformedJson; "malformed JSON"
0x180076f4f  or      r8d, 0FFFFFFFFh
0x180076f53  call    sqlite3_result_error
0x180076f58  mov     rcx, rbx
0x180076f5b  mov     rbx, [rsp+38h+arg_0]
0x180076f60  mov     rsi, [rsp+38h+arg_8]
0x180076f65  add     rsp, 30h
0x180076f69  pop     rdi
0x180076f6a  jmp     jsonStringReset
```
