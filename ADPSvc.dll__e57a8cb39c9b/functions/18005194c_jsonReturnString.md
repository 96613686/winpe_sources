# jsonReturnString

- ea: `0x18005194c`
- end: `0x180051a56`
- name: `jsonReturnString`
- size: `266`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004d90c`
- `0x18004da80`
- `0x18004f190`
- `0x1800506d8`
- `0x180050850`
- `0x180050fb0`
- `0x180051180`
- `0x180051828`
- `0x180051b04`

## callees

- `0x18004e224`
- `0x18005194c`
- `0x180051a5c`
- `0x180051dfc`
- `0x180051e54`
- `0x18009b4ec`
- `0x1800ab280`
- `0x1800ab480`

## string_xrefs

- `0x180051a1d`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonReturnString(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // al
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(); // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx

  v4 = *((_BYTE *)a1 + 33);
  if ( !v4 )
  {
    v8 = *a1;
    if ( (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8LL) & 8) != 0 )
    {
      jsonReturnStringAsBlob(a1);
      return jsonStringReset(a1);
    }
    if ( *((_BYTE *)a1 + 32) )
    {
      v9 = a1[1];
      LODWORD(v10) = -1;
LABEL_13:
      sqlite3_result_text64(v8, v9, a1[3], (_DWORD)v10, 1);
      return jsonStringReset(a1);
    }
    if ( (unsigned int)jsonStringTerminate(a1) )
    {
      if ( !a2
        || *(_BYTE *)(a2 + 48)
        || !*(_DWORD *)(a2 + 12)
        || (v11 = a1[1],
            ++*(_QWORD *)(v11 - 8),
            *(_QWORD *)(a2 + 16) = v11,
            *(_DWORD *)(a2 + 32) = *((_DWORD *)a1 + 6),
            *(_BYTE *)(a2 + 48) = 1,
            (unsigned int)jsonCacheInsert(a3, a2) != 7) )
      {
        v9 = a1[1];
        v10 = sqlite3RCStrUnref;
        ++*(_QWORD *)(v9 - 8);
        v8 = *a1;
        goto LABEL_13;
      }
      v12 = a3;
    }
    else
    {
      v12 = *a1;
    }
LABEL_17:
    sqlite3_result_error_nomem(v12);
    return jsonStringReset(a1);
  }
  if ( (v4 & 1) != 0 )
  {
    v12 = *a1;
    goto LABEL_17;
  }
  if ( (v4 & 2) != 0 )
  {
    v13 = *a1;
    LOBYTE(a4) = 1;
    *(_DWORD *)(v13 + 36) = 1;
    sqlite3VdbeMemSetStr(*(_QWORD *)v13, "malformed JSON", -1, a4, -1);
  }
  return jsonStringReset(a1);
}

```

## disassembly

```asm
0x18005194c  mov     [rsp+arg_0], rbx
0x180051951  mov     [rsp+arg_8], rsi
0x180051956  push    rdi
0x180051957  sub     rsp, 30h
0x18005195b  mov     al, [rcx+21h]
0x18005195e  mov     rsi, r8
0x180051961  mov     rdi, rdx
0x180051964  mov     rbx, rcx
0x180051967  test    al, al
0x180051969  jnz     loc_180051A08
0x18005196f  mov     rcx, [rcx]
0x180051972  mov     rax, [rcx+8]
0x180051976  test    byte ptr [rax+8], 8
0x18005197a  jz      short loc_180051989
0x18005197c  mov     rcx, rbx
0x18005197f  call    jsonReturnStringAsBlob
0x180051984  jmp     loc_180051A3F
0x180051989  cmp     byte ptr [rbx+20h], 0
0x18005198d  jz      short loc_180051999
0x18005198f  mov     rdx, [rbx+8]
0x180051993  or      r9, 0FFFFFFFFFFFFFFFFh
0x180051997  jmp     short loc_1800519F3
0x180051999  mov     rcx, rbx
0x18005199c  call    jsonStringTerminate
0x1800519a1  test    eax, eax
0x1800519a3  jz      short loc_180051A03
0x1800519a5  test    rdi, rdi
0x1800519a8  jz      short loc_1800519E1
0x1800519aa  cmp     byte ptr [rdi+30h], 0
0x1800519ae  jnz     short loc_1800519E1
0x1800519b0  cmp     dword ptr [rdi+0Ch], 0
0x1800519b4  jbe     short loc_1800519E1
0x1800519b6  mov     rax, [rbx+8]
0x1800519ba  mov     rdx, rdi
0x1800519bd  mov     rcx, rsi
0x1800519c0  inc     qword ptr [rax-8]
0x1800519c4  mov     [rdi+10h], rax
0x1800519c8  mov     eax, [rbx+18h]
0x1800519cb  mov     [rdi+20h], eax
0x1800519ce  mov     byte ptr [rdi+30h], 1
0x1800519d2  call    jsonCacheInsert
0x1800519d7  cmp     eax, 7
0x1800519da  jnz     short loc_1800519E1
0x1800519dc  mov     rcx, rsi
0x1800519df  jmp     short loc_180051A0F
0x1800519e1  mov     rdx, [rbx+8]
0x1800519e5  lea     r9, sqlite3RCStrUnref
0x1800519ec  inc     qword ptr [rdx-8]
0x1800519f0  mov     rcx, [rbx]
0x1800519f3  mov     r8, [rbx+18h]
0x1800519f7  mov     byte ptr [rsp+38h+var_18], 1
0x1800519fc  call    sqlite3_result_text64
0x180051a01  jmp     short loc_180051A3F
0x180051a03  mov     rcx, [rbx]
0x180051a06  jmp     short loc_180051A0F
0x180051a08  test    al, 1
0x180051a0a  jz      short loc_180051A16
0x180051a0c  mov     rcx, [rcx]
0x180051a0f  call    sqlite3_result_error_nomem
0x180051a14  jmp     short loc_180051A3F
0x180051a16  test    al, 2
0x180051a18  jz      short loc_180051A3F
0x180051a1a  mov     rcx, [rcx]
0x180051a1d  lea     rdx, aMalformedJson; "malformed JSON"
0x180051a24  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051a28  mov     r9b, 1
0x180051a2b  mov     [rsp+38h+var_18], r8
0x180051a30  mov     dword ptr [rcx+24h], 1
0x180051a37  mov     rcx, [rcx]
0x180051a3a  call    sqlite3VdbeMemSetStr
0x180051a3f  mov     rcx, rbx
0x180051a42  mov     rbx, [rsp+38h+arg_0]
0x180051a47  mov     rsi, [rsp+38h+arg_8]
0x180051a4c  add     rsp, 30h
0x180051a50  pop     rdi
0x180051a51  jmp     jsonStringReset
```
