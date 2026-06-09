# jsonReturnString

- ea: `0x180086088`
- end: `0x18008617f`
- name: `jsonReturnString`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800823e0`
- `0x1800824f0`
- `0x180083b70`
- `0x18008510c`
- `0x180085210`
- `0x1800857f0`
- `0x1800859c0`
- `0x180085f74`
- `0x180086218`

## callees

- `0x180082cc4`
- `0x180086088`
- `0x180086188`
- `0x1800864e4`
- `0x180086530`
- `0x18009d650`
- `0x18009d6d0`
- `0x18009d830`
- `0x18009ed10`

## string_xrefs

- `0x180086158`: `malformed JSON`

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
0x180086088  mov     [rsp+arg_0], rbx
0x18008608d  mov     [rsp+arg_8], rsi
0x180086092  push    rdi
0x180086093  sub     rsp, 30h
0x180086097  mov     al, [rcx+21h]
0x18008609a  mov     rsi, r8
0x18008609d  mov     rdi, rdx
0x1800860a0  mov     rbx, rcx
0x1800860a3  test    al, al
0x1800860a5  jnz     loc_180086143
0x1800860ab  mov     rcx, [rcx]
0x1800860ae  call    sqlite3_user_data
0x1800860b3  test    al, 8
0x1800860b5  jz      short loc_1800860C4
0x1800860b7  mov     rcx, rbx
0x1800860ba  call    jsonReturnStringAsBlob
0x1800860bf  jmp     loc_180086168
0x1800860c4  cmp     byte ptr [rbx+20h], 0
0x1800860c8  jz      short loc_1800860D4
0x1800860ca  mov     rdx, [rbx+8]
0x1800860ce  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800860d2  jmp     short loc_18008612B
0x1800860d4  mov     rcx, rbx
0x1800860d7  call    jsonStringTerminate
0x1800860dc  test    eax, eax
0x1800860de  jz      short loc_18008613E
0x1800860e0  test    rdi, rdi
0x1800860e3  jz      short loc_18008611C
0x1800860e5  cmp     byte ptr [rdi+30h], 0
0x1800860e9  jnz     short loc_18008611C
0x1800860eb  cmp     dword ptr [rdi+0Ch], 0
0x1800860ef  jbe     short loc_18008611C
0x1800860f1  mov     rax, [rbx+8]
0x1800860f5  mov     rdx, rdi
0x1800860f8  mov     rcx, rsi
0x1800860fb  inc     qword ptr [rax-8]
0x1800860ff  mov     [rdi+10h], rax
0x180086103  mov     eax, [rbx+18h]
0x180086106  mov     [rdi+20h], eax
0x180086109  mov     byte ptr [rdi+30h], 1
0x18008610d  call    jsonCacheInsert
0x180086112  cmp     eax, 7
0x180086115  jnz     short loc_18008611C
0x180086117  mov     rcx, rsi
0x18008611a  jmp     short loc_18008614A
0x18008611c  mov     rdx, [rbx+8]
0x180086120  lea     r9, sqlite3RCStrUnref
0x180086127  inc     qword ptr [rdx-8]
0x18008612b  mov     r8, [rbx+18h]
0x18008612f  mov     rcx, [rbx]
0x180086132  mov     [rsp+38h+var_18], 1
0x180086137  call    sqlite3_result_text64
0x18008613c  jmp     short loc_180086168
0x18008613e  mov     rcx, [rbx]
0x180086141  jmp     short loc_18008614A
0x180086143  test    al, 1
0x180086145  jz      short loc_180086151
0x180086147  mov     rcx, [rcx]
0x18008614a  call    sqlite3_result_error_nomem
0x18008614f  jmp     short loc_180086168
0x180086151  test    al, 2
0x180086153  jz      short loc_180086168
0x180086155  mov     rcx, [rcx]
0x180086158  lea     rdx, aMalformedJson; "malformed JSON"
0x18008615f  or      r8d, 0FFFFFFFFh
0x180086163  call    sqlite3_result_error
0x180086168  mov     rcx, rbx
0x18008616b  mov     rbx, [rsp+38h+arg_0]
0x180086170  mov     rsi, [rsp+38h+arg_8]
0x180086175  add     rsp, 30h
0x180086179  pop     rdi
0x18008617a  jmp     jsonStringReset
```
