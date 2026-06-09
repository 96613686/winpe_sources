# jsonValidFunc

- ea: `0x18006aa50`
- end: `0x18006ab8e`
- name: `jsonValidFunc`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x18003f71c`
- `0x180045374`
- `0x180066ed4`
- `0x1800683e0`
- `0x18006841c`
- `0x18006aa50`
- `0x18006ad94`
- `0x18008c97c`
- `0x180096df0`
- `0x180096e70`
- `0x180096ef0`
- `0x180098a80`

## string_xrefs

- `0x18006aa81`: `FLAGS parameter to json_valid() must be between 1 and 15`

## pseudocode

```c
__int64 __fastcall jsonValidFunc(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rdi
  __int64 result; // rax
  unsigned int v7; // ebx
  _BYTE *v8; // rax
  _BYTE *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v14; // [rsp+28h] [rbp-70h]

  LOBYTE(v5) = 1;
  if ( (_DWORD)a2 == 2 )
  {
    v5 = sqlite3VdbeIntValue(a3[1], a2, a3);
    if ( (unsigned __int64)(v5 - 1) > 0xE )
      return sqlite3_result_error(a1, "FLAGS parameter to json_valid() must be between 1 and 15", 0xFFFFFFFFLL);
  }
  result = *(_WORD *)(*a3 + 20) & 0x3F;
  if ( *((_BYTE *)qword_1800B9DC0 + result) == 4 )
  {
    if ( (unsigned int)jsonFuncArgMightBeBinary(*a3) )
    {
      if ( (v5 & 4) != 0 )
      {
        v7 = 1;
      }
      else
      {
        v7 = 0;
        if ( (v5 & 8) != 0 )
        {
          memset_0(&v13, 0, 0x48u);
          v10 = sqlite3_value_blob(*a3);
          v11 = *a3;
          LOBYTE(v12) = 1;
          v13 = v10;
          v14 = sqlite3ValueBytes(v11, v12);
          LOBYTE(v7) = (unsigned int)jsonbValidityCheck(&v13, 0, v14, 1) == 0;
        }
      }
      return sqlite3_result_int(a1, v7);
    }
  }
  else if ( *((_BYTE *)qword_1800B9DC0 + result) == 5 )
  {
    return result;
  }
  v7 = 0;
  if ( (v5 & 3) != 0 )
  {
    v8 = (_BYTE *)jsonParseFuncArg(a1, *a3, 2);
    v9 = v8;
    if ( v8 )
    {
      if ( v8[47] )
      {
        sqlite3_result_error_nomem(a1);
      }
      else if ( !v8[46] && ((v5 & 2) != 0 || !v8[49]) )
      {
        v7 = 1;
      }
      jsonParseFree(v9);
    }
    else
    {
      sqlite3_result_error_nomem(a1);
    }
  }
  return sqlite3_result_int(a1, v7);
}

```

## disassembly

```asm
0x18006aa50  push    rbx
0x18006aa52  push    rbp
0x18006aa53  push    rsi
0x18006aa54  push    rdi
0x18006aa55  sub     rsp, 78h
0x18006aa59  mov     rsi, r8
0x18006aa5c  mov     rbp, rcx
0x18006aa5f  mov     dil, 1
0x18006aa62  cmp     edx, 2
0x18006aa65  jnz     short loc_18006AA95
0x18006aa67  mov     rcx, [r8+8]
0x18006aa6b  call    sqlite3VdbeIntValue
0x18006aa70  mov     rdi, rax
0x18006aa73  lea     rdx, [rax-1]
0x18006aa77  cmp     rdx, 0Eh
0x18006aa7b  jbe     short loc_18006AA95
0x18006aa7d  or      r8d, 0FFFFFFFFh
0x18006aa81  lea     rdx, aFlagsParameter; "FLAGS parameter to json_valid() must be"...
0x18006aa88  mov     rcx, rbp
0x18006aa8b  call    sqlite3_result_error
0x18006aa90  jmp     loc_18006AB85
0x18006aa95  mov     rdx, [rsi]
0x18006aa98  lea     rcx, qword_1800B9DC0
0x18006aa9f  movzx   eax, word ptr [rdx+14h]
0x18006aaa3  and     eax, 3Fh
0x18006aaa6  movzx   ecx, byte ptr [rax+rcx]
0x18006aaaa  sub     ecx, 4
0x18006aaad  jz      short loc_18006AAEE
0x18006aaaf  cmp     ecx, 1
0x18006aab2  jz      loc_18006AB85
0x18006aab8  xor     ebx, ebx
0x18006aaba  test    dil, 3
0x18006aabe  jz      loc_18006AB7B
0x18006aac4  mov     rdx, [rsi]
0x18006aac7  lea     r8d, [rbx+2]
0x18006aacb  mov     rcx, rbp
0x18006aace  call    jsonParseFuncArg
0x18006aad3  mov     rsi, rax
0x18006aad6  test    rax, rax
0x18006aad9  jz      loc_18006AB73
0x18006aadf  cmp     [rax+2Fh], bl
0x18006aae2  jz      short loc_18006AB54
0x18006aae4  mov     rcx, rbp
0x18006aae7  call    sqlite3_result_error_nomem
0x18006aaec  jmp     short loc_18006AB69
0x18006aaee  mov     rcx, rdx
0x18006aaf1  call    jsonFuncArgMightBeBinary
0x18006aaf6  test    eax, eax
0x18006aaf8  jz      short loc_18006AAB8
0x18006aafa  test    dil, 4
0x18006aafe  jz      short loc_18006AB07
0x18006ab00  mov     ebx, 1
0x18006ab05  jmp     short loc_18006AB7B
0x18006ab07  xor     ebx, ebx
0x18006ab09  test    dil, 8
0x18006ab0d  jz      short loc_18006AB7B
0x18006ab0f  xor     edx, edx; Val
0x18006ab11  lea     r8d, [rbx+48h]; Size
0x18006ab15  lea     rcx, [rsp+98h+var_78]; void *
0x18006ab1a  call    memset_0
0x18006ab1f  mov     rcx, [rsi]
0x18006ab22  call    sqlite3_value_blob
0x18006ab27  mov     rcx, [rsi]
0x18006ab2a  mov     dl, 1
0x18006ab2c  mov     [rsp+98h+var_78], rax
0x18006ab31  call    sqlite3ValueBytes
0x18006ab36  lea     r9d, [rbx+1]
0x18006ab3a  mov     [rsp+98h+var_70], eax
0x18006ab3e  mov     r8d, eax
0x18006ab41  lea     rcx, [rsp+98h+var_78]
0x18006ab46  xor     edx, edx
0x18006ab48  call    jsonbValidityCheck
0x18006ab4d  test    eax, eax
0x18006ab4f  setz    bl
0x18006ab52  jmp     short loc_18006AB7B
0x18006ab54  cmp     [rax+2Eh], bl
0x18006ab57  jnz     short loc_18006AB69
0x18006ab59  test    dil, 2
0x18006ab5d  jnz     short loc_18006AB64
0x18006ab5f  cmp     [rax+31h], bl
0x18006ab62  jnz     short loc_18006AB69
0x18006ab64  mov     ebx, 1
0x18006ab69  mov     rcx, rsi
0x18006ab6c  call    jsonParseFree
0x18006ab71  jmp     short loc_18006AB7B
0x18006ab73  mov     rcx, rbp
0x18006ab76  call    sqlite3_result_error_nomem
0x18006ab7b  mov     edx, ebx
0x18006ab7d  mov     rcx, rbp
0x18006ab80  call    sqlite3_result_int
0x18006ab85  add     rsp, 78h
0x18006ab89  pop     rdi
0x18006ab8a  pop     rsi
0x18006ab8b  pop     rbp
0x18006ab8c  pop     rbx
0x18006ab8d  retn
```
