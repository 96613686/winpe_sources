# jsonReturnParse

- ea: `0x180076d64`
- end: `0x180076e71`
- name: `jsonReturnParse`
- size: `269`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180075144`
- `0x180076530`
- `0x180076860`

## callees

- `0x180048740`
- `0x180068190`
- `0x180068880`
- `0x18006910e`
- `0x180076d64`
- `0x180076e78`
- `0x18007750c`
- `0x18008f340`
- `0x18008f4f0`

## pseudocode

```c
__int64 __fastcall jsonReturnParse(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD v5[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int16 v6; // [rsp+40h] [rbp-88h]
  _BYTE v7[110]; // [rsp+42h] [rbp-86h] BYREF

  if ( *((_BYTE *)a2 + 47) )
    return sqlite3_result_error_nomem(a1);
  if ( (sqlite3_user_data(a1) & 8) != 0 )
  {
    if ( !*((_DWORD *)a2 + 3) || *((_BYTE *)a2 + 50) )
    {
      return sqlite3_result_blob(a1, *a2, *((unsigned int *)a2 + 2), -1);
    }
    else
    {
      result = sqlite3_result_blob(a1, *a2, *((unsigned int *)a2 + 2), sqlite3OomClear);
      *((_DWORD *)a2 + 3) = 0;
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
    *((_DWORD *)a2 + 13) = 0;
    jsonTranslateBlobToText(a2, 0, v5);
    jsonReturnString(v5, a2, a1);
    return sqlite3_result_subtype(a1, 74);
  }
  return result;
}

```

## disassembly

```asm
0x180076d64  mov     [rsp+arg_10], rbx
0x180076d69  push    rdi
0x180076d6a  sub     rsp, 0C0h
0x180076d71  mov     rax, cs:__security_cookie
0x180076d78  xor     rax, rsp
0x180076d7b  mov     [rsp+0C8h+var_18], rax
0x180076d83  cmp     byte ptr [rdx+2Fh], 0
0x180076d87  mov     rbx, rdx
0x180076d8a  mov     rdi, rcx
0x180076d8d  jz      short loc_180076D99
0x180076d8f  call    sqlite3_result_error_nomem
0x180076d94  jmp     loc_180076E50
0x180076d99  call    sqlite3_user_data
0x180076d9e  test    al, 8
0x180076da0  jz      short loc_180076DE5
0x180076da2  cmp     dword ptr [rbx+0Ch], 0
0x180076da6  jbe     short loc_180076DD0
0x180076da8  cmp     byte ptr [rbx+32h], 0
0x180076dac  jnz     short loc_180076DD0
0x180076dae  mov     r8d, [rbx+8]
0x180076db2  lea     r9, sqlite3OomClear
0x180076db9  mov     rdx, [rbx]
0x180076dbc  mov     rcx, rdi
0x180076dbf  call    sqlite3_result_blob
0x180076dc4  mov     dword ptr [rbx+0Ch], 0
0x180076dcb  jmp     loc_180076E50
0x180076dd0  mov     r8d, [rbx+8]
0x180076dd4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180076dd8  mov     rdx, [rbx]
0x180076ddb  mov     rcx, rdi
0x180076dde  call    sqlite3_result_blob
0x180076de3  jmp     short loc_180076E50
0x180076de5  xor     edx, edx; Val
0x180076de7  lea     rcx, [rsp+0C8h+var_86]; void *
0x180076dec  lea     r8d, [rdx+66h]; Size
0x180076df0  call    memset_0
0x180076df5  lea     rax, [rsp+0C8h+var_86]
0x180076dfa  mov     [rsp+0C8h+var_A8], rdi
0x180076dff  lea     r8, [rsp+0C8h+var_A8]
0x180076e04  mov     [rsp+0C8h+var_A0], rax
0x180076e09  xor     edx, edx
0x180076e0b  mov     [rsp+0C8h+var_88], 1
0x180076e12  mov     rcx, rbx
0x180076e15  mov     [rsp+0C8h+var_98], 64h ; 'd'
0x180076e1e  mov     [rsp+0C8h+var_90], 0
0x180076e27  mov     dword ptr [rbx+34h], 0
0x180076e2e  call    jsonTranslateBlobToText
0x180076e33  mov     r8, rdi
0x180076e36  lea     rcx, [rsp+0C8h+var_A8]
0x180076e3b  mov     rdx, rbx
0x180076e3e  call    jsonReturnString
0x180076e43  mov     edx, 4Ah ; 'J'
0x180076e48  mov     rcx, rdi
0x180076e4b  call    sqlite3_result_subtype
0x180076e50  mov     rcx, [rsp+0C8h+var_18]
0x180076e58  xor     rcx, rsp; StackCookie
0x180076e5b  call    __security_check_cookie
0x180076e60  mov     rbx, [rsp+0C8h+arg_10]
0x180076e68  add     rsp, 0C0h
0x180076e6f  pop     rdi
0x180076e70  retn
```
