# jsonValidFunc

- ea: `0x180087a80`
- end: `0x180087bbe`
- name: `jsonValidFunc`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x1800543d0`
- `0x180054e70`
- `0x180054ef4`
- `0x180070520`
- `0x180078968`
- `0x180083f44`
- `0x180085450`
- `0x18008548c`
- `0x180087a80`
- `0x180087dc4`
- `0x18009d650`
- `0x18009d6d0`

## string_xrefs

- `0x180087ab1`: `FLAGS parameter to json_valid() must be between 1 and 15`

## pseudocode

```c
__int64 __fastcall jsonValidFunc(__int64 a1, int a2, __int64 *a3)
{
  char v5; // di
  __int64 v6; // rax
  __int64 result; // rax
  unsigned int v8; // ebx
  _BYTE *v9; // rax
  _BYTE *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // [rsp+20h] [rbp-78h] BYREF
  int v15; // [rsp+28h] [rbp-70h]

  v5 = 1;
  if ( a2 == 2 )
  {
    v6 = sqlite3VdbeIntValue(a3[1]);
    v5 = v6;
    if ( (unsigned __int64)(v6 - 1) > 0xE )
      return sqlite3_result_error(a1, "FLAGS parameter to json_valid() must be between 1 and 15", 0xFFFFFFFFLL);
  }
  result = *(_WORD *)(*a3 + 20) & 0x3F;
  if ( *((_BYTE *)qword_1800B5270 + result) == 4 )
  {
    if ( (unsigned int)jsonFuncArgMightBeBinary(*a3) )
    {
      if ( (v5 & 4) != 0 )
      {
        v8 = 1;
      }
      else
      {
        v8 = 0;
        if ( (v5 & 8) != 0 )
        {
          memset_0(&v14, 0, 0x48u);
          v11 = sqlite3_value_blob(*a3);
          v12 = *a3;
          LOBYTE(v13) = 1;
          v14 = v11;
          v15 = sqlite3ValueBytes(v12, v13);
          LOBYTE(v8) = (unsigned int)jsonbValidityCheck(&v14, 0, v15, 1u) == 0;
        }
      }
      return sqlite3_result_int(a1, v8);
    }
  }
  else if ( *((_BYTE *)qword_1800B5270 + result) == 5 )
  {
    return result;
  }
  v8 = 0;
  if ( (v5 & 3) != 0 )
  {
    v9 = (_BYTE *)jsonParseFuncArg(a1, *a3, 2);
    v10 = v9;
    if ( v9 )
    {
      if ( v9[47] )
      {
        sqlite3_result_error_nomem(a1);
      }
      else if ( !v9[46] && ((v5 & 2) != 0 || !v9[49]) )
      {
        v8 = 1;
      }
      jsonParseFree(v10);
    }
    else
    {
      sqlite3_result_error_nomem(a1);
    }
  }
  return sqlite3_result_int(a1, v8);
}

```

## disassembly

```asm
0x180087a80  push    rbx
0x180087a82  push    rbp
0x180087a83  push    rsi
0x180087a84  push    rdi
0x180087a85  sub     rsp, 78h
0x180087a89  mov     rsi, r8
0x180087a8c  mov     rbp, rcx
0x180087a8f  mov     dil, 1
0x180087a92  cmp     edx, 2
0x180087a95  jnz     short loc_180087AC5
0x180087a97  mov     rcx, [r8+8]
0x180087a9b  call    sqlite3VdbeIntValue
0x180087aa0  mov     rdi, rax
0x180087aa3  lea     rdx, [rax-1]
0x180087aa7  cmp     rdx, 0Eh
0x180087aab  jbe     short loc_180087AC5
0x180087aad  or      r8d, 0FFFFFFFFh
0x180087ab1  lea     rdx, aFlagsParameter; "FLAGS parameter to json_valid() must be"...
0x180087ab8  mov     rcx, rbp
0x180087abb  call    sqlite3_result_error
0x180087ac0  jmp     loc_180087BB5
0x180087ac5  mov     rdx, [rsi]
0x180087ac8  lea     rcx, qword_1800B5270
0x180087acf  movzx   eax, word ptr [rdx+14h]
0x180087ad3  and     eax, 3Fh
0x180087ad6  movzx   ecx, byte ptr [rax+rcx]
0x180087ada  sub     ecx, 4
0x180087add  jz      short loc_180087B1E
0x180087adf  cmp     ecx, 1
0x180087ae2  jz      loc_180087BB5
0x180087ae8  xor     ebx, ebx
0x180087aea  test    dil, 3
0x180087aee  jz      loc_180087BAB
0x180087af4  mov     rdx, [rsi]
0x180087af7  lea     r8d, [rbx+2]
0x180087afb  mov     rcx, rbp
0x180087afe  call    jsonParseFuncArg
0x180087b03  mov     rsi, rax
0x180087b06  test    rax, rax
0x180087b09  jz      loc_180087BA3
0x180087b0f  cmp     [rax+2Fh], bl
0x180087b12  jz      short loc_180087B84
0x180087b14  mov     rcx, rbp
0x180087b17  call    sqlite3_result_error_nomem
0x180087b1c  jmp     short loc_180087B99
0x180087b1e  mov     rcx, rdx
0x180087b21  call    jsonFuncArgMightBeBinary
0x180087b26  test    eax, eax
0x180087b28  jz      short loc_180087AE8
0x180087b2a  test    dil, 4
0x180087b2e  jz      short loc_180087B37
0x180087b30  mov     ebx, 1
0x180087b35  jmp     short loc_180087BAB
0x180087b37  xor     ebx, ebx
0x180087b39  test    dil, 8
0x180087b3d  jz      short loc_180087BAB
0x180087b3f  xor     edx, edx; Val
0x180087b41  lea     r8d, [rbx+48h]; Size
0x180087b45  lea     rcx, [rsp+98h+var_78]; void *
0x180087b4a  call    memset_0
0x180087b4f  mov     rcx, [rsi]
0x180087b52  call    sqlite3_value_blob
0x180087b57  mov     rcx, [rsi]
0x180087b5a  mov     dl, 1
0x180087b5c  mov     [rsp+98h+var_78], rax
0x180087b61  call    sqlite3ValueBytes
0x180087b66  lea     r9d, [rbx+1]
0x180087b6a  mov     [rsp+98h+var_70], eax
0x180087b6e  mov     r8d, eax
0x180087b71  lea     rcx, [rsp+98h+var_78]
0x180087b76  xor     edx, edx
0x180087b78  call    jsonbValidityCheck
0x180087b7d  test    eax, eax
0x180087b7f  setz    bl
0x180087b82  jmp     short loc_180087BAB
0x180087b84  cmp     [rax+2Eh], bl
0x180087b87  jnz     short loc_180087B99
0x180087b89  test    dil, 2
0x180087b8d  jnz     short loc_180087B94
0x180087b8f  cmp     [rax+31h], bl
0x180087b92  jnz     short loc_180087B99
0x180087b94  mov     ebx, 1
0x180087b99  mov     rcx, rsi
0x180087b9c  call    jsonParseFree
0x180087ba1  jmp     short loc_180087BAB
0x180087ba3  mov     rcx, rbp
0x180087ba6  call    sqlite3_result_error_nomem
0x180087bab  mov     edx, ebx
0x180087bad  mov     rcx, rbp
0x180087bb0  call    sqlite3_result_int
0x180087bb5  add     rsp, 78h
0x180087bb9  pop     rdi
0x180087bba  pop     rsi
0x180087bbb  pop     rbp
0x180087bbc  pop     rbx
0x180087bbd  retn
```
