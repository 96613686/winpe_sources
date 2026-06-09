# jsonReturnString

- ea: `0x180069018`
- end: `0x18006910f`
- name: `jsonReturnString`
- size: `247`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800653d0`
- `0x1800654e0`
- `0x180066b00`
- `0x18006809c`
- `0x1800681a0`
- `0x180068780`
- `0x180068950`
- `0x180068f04`
- `0x1800691a8`

## callees

- `0x180065c34`
- `0x180069018`
- `0x180069118`
- `0x180069474`
- `0x1800694c0`
- `0x180096df0`
- `0x180096e70`
- `0x180097050`
- `0x180098a60`

## string_xrefs

- `0x1800690e8`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonReturnString(_QWORD *a1, __int64 a2, __int64 a3)
{
  char v3; // al
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(); // r9
  __int64 v9; // rax
  __int64 v10; // rcx

  v3 = *((_BYTE *)a1 + 33);
  if ( !v3 )
  {
    if ( (sqlite3_user_data(*a1, a2) & 8) != 0 )
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
0x180069018  mov     [rsp+arg_0], rbx
0x18006901d  mov     [rsp+arg_8], rsi
0x180069022  push    rdi
0x180069023  sub     rsp, 30h
0x180069027  mov     al, [rcx+21h]
0x18006902a  mov     rsi, r8
0x18006902d  mov     rdi, rdx
0x180069030  mov     rbx, rcx
0x180069033  test    al, al
0x180069035  jnz     loc_1800690D3
0x18006903b  mov     rcx, [rcx]
0x18006903e  call    sqlite3_user_data
0x180069043  test    al, 8
0x180069045  jz      short loc_180069054
0x180069047  mov     rcx, rbx
0x18006904a  call    jsonReturnStringAsBlob
0x18006904f  jmp     loc_1800690F8
0x180069054  cmp     byte ptr [rbx+20h], 0
0x180069058  jz      short loc_180069064
0x18006905a  mov     rdx, [rbx+8]
0x18006905e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069062  jmp     short loc_1800690BB
0x180069064  mov     rcx, rbx
0x180069067  call    jsonStringTerminate
0x18006906c  test    eax, eax
0x18006906e  jz      short loc_1800690CE
0x180069070  test    rdi, rdi
0x180069073  jz      short loc_1800690AC
0x180069075  cmp     byte ptr [rdi+30h], 0
0x180069079  jnz     short loc_1800690AC
0x18006907b  cmp     dword ptr [rdi+0Ch], 0
0x18006907f  jbe     short loc_1800690AC
0x180069081  mov     rax, [rbx+8]
0x180069085  mov     rdx, rdi
0x180069088  mov     rcx, rsi
0x18006908b  inc     qword ptr [rax-8]
0x18006908f  mov     [rdi+10h], rax
0x180069093  mov     eax, [rbx+18h]
0x180069096  mov     [rdi+20h], eax
0x180069099  mov     byte ptr [rdi+30h], 1
0x18006909d  call    jsonCacheInsert
0x1800690a2  cmp     eax, 7
0x1800690a5  jnz     short loc_1800690AC
0x1800690a7  mov     rcx, rsi
0x1800690aa  jmp     short loc_1800690DA
0x1800690ac  mov     rdx, [rbx+8]
0x1800690b0  lea     r9, sqlite3RCStrUnref
0x1800690b7  inc     qword ptr [rdx-8]
0x1800690bb  mov     r8, [rbx+18h]
0x1800690bf  mov     rcx, [rbx]
0x1800690c2  mov     [rsp+38h+var_18], 1
0x1800690c7  call    sqlite3_result_text64
0x1800690cc  jmp     short loc_1800690F8
0x1800690ce  mov     rcx, [rbx]
0x1800690d1  jmp     short loc_1800690DA
0x1800690d3  test    al, 1
0x1800690d5  jz      short loc_1800690E1
0x1800690d7  mov     rcx, [rcx]
0x1800690da  call    sqlite3_result_error_nomem
0x1800690df  jmp     short loc_1800690F8
0x1800690e1  test    al, 2
0x1800690e3  jz      short loc_1800690F8
0x1800690e5  mov     rcx, [rcx]
0x1800690e8  lea     rdx, aMalformedJson; "malformed JSON"
0x1800690ef  or      r8d, 0FFFFFFFFh
0x1800690f3  call    sqlite3_result_error
0x1800690f8  mov     rcx, rbx
0x1800690fb  mov     rbx, [rsp+38h+arg_0]
0x180069100  mov     rsi, [rsp+38h+arg_8]
0x180069105  add     rsp, 30h
0x180069109  pop     rdi
0x18006910a  jmp     jsonStringReset
```
