# jsonValidFunc

- ea: `0x180078870`
- end: `0x1800789ae`
- name: `jsonValidFunc`
- size: `318`
- prototype: `__int64 __fastcall(__int64, int, __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180027a20`
- `0x180047fb0`
- `0x180048d38`
- `0x18005ede0`
- `0x180068190`
- `0x18006910e`
- `0x180074d08`
- `0x180076240`
- `0x18007627c`
- `0x180078870`
- `0x180078bb4`
- `0x18008f3f0`

## string_xrefs

- `0x1800788a1`: `FLAGS parameter to json_valid() must be between 1 and 15`

## pseudocode

```c
__int64 __fastcall jsonValidFunc(__int64 a1, int a2, __int64 *a3)
{
  char v5; // di
  __int64 v6; // rax
  __int64 result; // rax
  unsigned int v8; // ebx
  _BYTE *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // [rsp+20h] [rbp-78h] BYREF
  int v15; // [rsp+28h] [rbp-70h]

  v5 = 1;
  if ( a2 == 2 )
  {
    v6 = sqlite3_value_int64(a3[1]);
    v5 = v6;
    if ( (unsigned __int64)(v6 - 1) > 0xE )
      return sqlite3_result_error(a1, "FLAGS parameter to json_valid() must be between 1 and 15", 0xFFFFFFFFLL);
  }
  result = *(_WORD *)(*a3 + 20) & 0x3F;
  if ( *((_BYTE *)qword_18009EC50 + result) == 4 )
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
  else if ( *((_BYTE *)qword_18009EC50 + result) == 5 )
  {
    return result;
  }
  v8 = 0;
  if ( (v5 & 3) != 0 )
  {
    v9 = (_BYTE *)jsonParseFuncArg(a1, *a3, 2);
    v10 = (__int64)v9;
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
0x180078870  push    rbx
0x180078872  push    rbp
0x180078873  push    rsi
0x180078874  push    rdi
0x180078875  sub     rsp, 78h
0x180078879  mov     rsi, r8
0x18007887c  mov     rbp, rcx
0x18007887f  mov     dil, 1
0x180078882  cmp     edx, 2
0x180078885  jnz     short loc_1800788B5
0x180078887  mov     rcx, [r8+8]
0x18007888b  call    sqlite3_value_int64
0x180078890  mov     rdi, rax
0x180078893  lea     rdx, [rax-1]
0x180078897  cmp     rdx, 0Eh
0x18007889b  jbe     short loc_1800788B5
0x18007889d  or      r8d, 0FFFFFFFFh
0x1800788a1  lea     rdx, aFlagsParameter; "FLAGS parameter to json_valid() must be"...
0x1800788a8  mov     rcx, rbp
0x1800788ab  call    sqlite3_result_error
0x1800788b0  jmp     loc_1800789A5
0x1800788b5  mov     rdx, [rsi]
0x1800788b8  lea     rcx, qword_18009EC50
0x1800788bf  movzx   eax, word ptr [rdx+14h]
0x1800788c3  and     eax, 3Fh
0x1800788c6  movzx   ecx, byte ptr [rax+rcx]
0x1800788ca  sub     ecx, 4
0x1800788cd  jz      short loc_18007890E
0x1800788cf  cmp     ecx, 1
0x1800788d2  jz      loc_1800789A5
0x1800788d8  xor     ebx, ebx
0x1800788da  test    dil, 3
0x1800788de  jz      loc_18007899B
0x1800788e4  mov     rdx, [rsi]
0x1800788e7  lea     r8d, [rbx+2]
0x1800788eb  mov     rcx, rbp
0x1800788ee  call    jsonParseFuncArg
0x1800788f3  mov     rsi, rax
0x1800788f6  test    rax, rax
0x1800788f9  jz      loc_180078993
0x1800788ff  cmp     [rax+2Fh], bl
0x180078902  jz      short loc_180078974
0x180078904  mov     rcx, rbp
0x180078907  call    sqlite3_result_error_nomem
0x18007890c  jmp     short loc_180078989
0x18007890e  mov     rcx, rdx
0x180078911  call    jsonFuncArgMightBeBinary
0x180078916  test    eax, eax
0x180078918  jz      short loc_1800788D8
0x18007891a  test    dil, 4
0x18007891e  jz      short loc_180078927
0x180078920  mov     ebx, 1
0x180078925  jmp     short loc_18007899B
0x180078927  xor     ebx, ebx
0x180078929  test    dil, 8
0x18007892d  jz      short loc_18007899B
0x18007892f  xor     edx, edx; Val
0x180078931  lea     r8d, [rbx+48h]; Size
0x180078935  lea     rcx, [rsp+98h+var_78]; void *
0x18007893a  call    memset_0
0x18007893f  mov     rcx, [rsi]
0x180078942  call    sqlite3_value_blob
0x180078947  mov     rcx, [rsi]
0x18007894a  mov     dl, 1
0x18007894c  mov     [rsp+98h+var_78], rax
0x180078951  call    sqlite3ValueBytes
0x180078956  lea     r9d, [rbx+1]
0x18007895a  mov     [rsp+98h+var_70], eax
0x18007895e  mov     r8d, eax
0x180078961  lea     rcx, [rsp+98h+var_78]
0x180078966  xor     edx, edx
0x180078968  call    jsonbValidityCheck
0x18007896d  test    eax, eax
0x18007896f  setz    bl
0x180078972  jmp     short loc_18007899B
0x180078974  cmp     [rax+2Eh], bl
0x180078977  jnz     short loc_180078989
0x180078979  test    dil, 2
0x18007897d  jnz     short loc_180078984
0x18007897f  cmp     [rax+31h], bl
0x180078982  jnz     short loc_180078989
0x180078984  mov     ebx, 1
0x180078989  mov     rcx, rsi
0x18007898c  call    jsonParseFree
0x180078991  jmp     short loc_18007899B
0x180078993  mov     rcx, rbp
0x180078996  call    sqlite3_result_error_nomem
0x18007899b  mov     edx, ebx
0x18007899d  mov     rcx, rbp
0x1800789a0  call    sqlite3_result_int
0x1800789a5  add     rsp, 78h
0x1800789a9  pop     rdi
0x1800789aa  pop     rsi
0x1800789ab  pop     rbp
0x1800789ac  pop     rbx
0x1800789ad  retn
```
