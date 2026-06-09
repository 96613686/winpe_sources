# jsonReturnParse

- ea: `0x180085f74`
- end: `0x180086081`
- name: `jsonReturnParse`
- size: `269`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180084384`
- `0x180085740`
- `0x180085a70`

## callees

- `0x180078968`
- `0x1800789c0`
- `0x180085f74`
- `0x180086088`
- `0x18008671c`
- `0x18009d5a0`
- `0x18009d6d0`
- `0x18009d790`
- `0x18009ed10`

## pseudocode

```c
__int64 __fastcall jsonReturnParse(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _QWORD v5[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int16 v6; // [rsp+40h] [rbp-88h]
  _BYTE v7[110]; // [rsp+42h] [rbp-86h] BYREF

  if ( *(_BYTE *)(a2 + 47) )
    return sqlite3_result_error_nomem(a1);
  if ( (sqlite3_user_data(a1) & 8) != 0 )
  {
    if ( !*(_DWORD *)(a2 + 12) || *(_BYTE *)(a2 + 50) )
    {
      return sqlite3_result_blob(a1, *(_QWORD *)a2, *(unsigned int *)(a2 + 8), -1);
    }
    else
    {
      result = sqlite3_result_blob(a1, *(_QWORD *)a2, *(unsigned int *)(a2 + 8), sqlite3OomClear);
      *(_DWORD *)(a2 + 12) = 0;
    }
  }
  else
  {
    memset_0(v7, 0, 0x66u);
    v5[0] = a1;
    v5[1] = v7;
    v6 = 1;
    v5[2] = 100;
    v5[3] = 0;
    *(_DWORD *)(a2 + 52) = 0;
    jsonTranslateBlobToText(a2, 0, (__int64)v5);
    jsonReturnString(v5, a2, a1);
    return sqlite3_result_subtype(a1, 74);
  }
  return result;
}

```

## disassembly

```asm
0x180085f74  mov     [rsp+arg_10], rbx
0x180085f79  push    rdi
0x180085f7a  sub     rsp, 0C0h
0x180085f81  mov     rax, cs:__security_cookie
0x180085f88  xor     rax, rsp
0x180085f8b  mov     [rsp+0C8h+var_18], rax
0x180085f93  cmp     byte ptr [rdx+2Fh], 0
0x180085f97  mov     rbx, rdx
0x180085f9a  mov     rdi, rcx
0x180085f9d  jz      short loc_180085FA9
0x180085f9f  call    sqlite3_result_error_nomem
0x180085fa4  jmp     loc_180086060
0x180085fa9  call    sqlite3_user_data
0x180085fae  test    al, 8
0x180085fb0  jz      short loc_180085FF5
0x180085fb2  cmp     dword ptr [rbx+0Ch], 0
0x180085fb6  jbe     short loc_180085FE0
0x180085fb8  cmp     byte ptr [rbx+32h], 0
0x180085fbc  jnz     short loc_180085FE0
0x180085fbe  mov     r8d, [rbx+8]
0x180085fc2  lea     r9, sqlite3OomClear
0x180085fc9  mov     rdx, [rbx]
0x180085fcc  mov     rcx, rdi
0x180085fcf  call    sqlite3_result_blob
0x180085fd4  mov     dword ptr [rbx+0Ch], 0
0x180085fdb  jmp     loc_180086060
0x180085fe0  mov     r8d, [rbx+8]
0x180085fe4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085fe8  mov     rdx, [rbx]
0x180085feb  mov     rcx, rdi
0x180085fee  call    sqlite3_result_blob
0x180085ff3  jmp     short loc_180086060
0x180085ff5  xor     edx, edx; Val
0x180085ff7  lea     rcx, [rsp+0C8h+var_86]; void *
0x180085ffc  lea     r8d, [rdx+66h]; Size
0x180086000  call    memset_0
0x180086005  lea     rax, [rsp+0C8h+var_86]
0x18008600a  mov     [rsp+0C8h+var_A8], rdi
0x18008600f  lea     r8, [rsp+0C8h+var_A8]
0x180086014  mov     [rsp+0C8h+var_A0], rax
0x180086019  xor     edx, edx
0x18008601b  mov     [rsp+0C8h+var_88], 1
0x180086022  mov     rcx, rbx
0x180086025  mov     [rsp+0C8h+var_98], 64h ; 'd'
0x18008602e  mov     [rsp+0C8h+var_90], 0
0x180086037  mov     dword ptr [rbx+34h], 0
0x18008603e  call    jsonTranslateBlobToText
0x180086043  mov     r8, rdi
0x180086046  lea     rcx, [rsp+0C8h+var_A8]
0x18008604b  mov     rdx, rbx
0x18008604e  call    jsonReturnString
0x180086053  mov     edx, 4Ah ; 'J'
0x180086058  mov     rcx, rdi
0x18008605b  call    sqlite3_result_subtype
0x180086060  mov     rcx, [rsp+0C8h+var_18]
0x180086068  xor     rcx, rsp; StackCookie
0x18008606b  call    __security_check_cookie
0x180086070  mov     rbx, [rsp+0C8h+arg_10]
0x180086078  add     rsp, 0C0h
0x18008607f  pop     rdi
0x180086080  retn
```
