# jsonObjectFunc

- ea: `0x140034930`
- end: `0x140034aef`
- name: `jsonObjectFunc`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140032314`
- `0x1400327f8`
- `0x140032830`
- `0x1400329e4`
- `0x140034930`
- `0x1400367dc`
- `0x140036834`
- `0x140073758`
- `0x14007c6ac`
- `0x14008f900`

## string_xrefs

- `0x14003497d`: `json_object() requires an even number of arguments`
- `0x140034ac5`: `json_object() labels must be TEXT`

## pseudocode

```c
__int64 __fastcall jsonObjectFunc(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 result; // rax
  int v9; // esi
  char *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-69h] BYREF
  char *v19; // [rsp+38h] [rbp-61h]
  unsigned __int64 v20; // [rsp+40h] [rbp-59h]
  unsigned __int64 v21; // [rsp+48h] [rbp-51h]
  __int16 v22; // [rsp+50h] [rbp-49h]
  char v23; // [rsp+52h] [rbp-47h] BYREF
  char v24[109]; // [rsp+53h] [rbp-46h] BYREF

  memset_0(v24, 0, 0x65u);
  if ( (a2 & 1) != 0 )
  {
    v7 = *(_QWORD *)a1;
    *(_DWORD *)(a1 + 36) = 1;
    LOBYTE(v6) = 1;
    return sqlite3VdbeMemSetStr(v7, "json_object() requires an even number of arguments", -1, v6, -1);
  }
  else
  {
    v9 = 0;
    v18 = a1;
    v22 = 1;
    v10 = &v23;
    v19 = &v23;
    v11 = 1;
    v20 = 100;
    v23 = 123;
    v21 = 1;
    if ( a2 > 0 )
    {
      do
      {
        if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(*(_QWORD *)(a3 + 8LL * v9) + 20LL) & 0x3F)) != 3 )
        {
          v17 = *(_QWORD *)a1;
          *(_DWORD *)(a1 + 36) = 1;
          LOBYTE(v6) = 1;
          sqlite3VdbeMemSetStr(v17, "json_object() labels must be TEXT", -1, v6, -1);
          return jsonReset(&v18);
        }
        jsonAppendSeparator(&v18);
        LOBYTE(v12) = 1;
        v13 = sqlite3ValueText(*(_QWORD *)(a3 + 8LL * v9), v12);
        v14 = sqlite3_value_bytes(*(_QWORD *)(a3 + 8LL * v9));
        jsonAppendString(&v18, v13, v14);
        if ( v21 < v20 )
        {
          v19[v21++] = 58;
        }
        else
        {
          LOBYTE(v15) = 58;
          jsonAppendCharExpand(&v18, v15);
        }
        jsonAppendValue(&v18, *(_QWORD *)(a3 + 8LL * v9 + 8));
        v9 += 2;
      }
      while ( v9 < a2 );
      v11 = v21;
      if ( v21 >= v20 )
      {
        LOBYTE(v16) = 125;
        jsonAppendCharExpand(&v18, v16);
        goto LABEL_13;
      }
      v10 = v19;
    }
    v10[v11] = 125;
    ++v21;
LABEL_13:
    jsonResult(&v18);
    result = *(_QWORD *)a1;
    *(_WORD *)(result + 20) |= 0x800u;
    *(_BYTE *)(result + 23) = 74;
  }
  return result;
}

```

## disassembly

```asm
0x140034930  mov     [rsp-8+arg_8], rbx
0x140034935  mov     [rsp-8+arg_18], rsi
0x14003493a  push    rbp
0x14003493b  push    rdi
0x14003493c  push    r12
0x14003493e  push    r14
0x140034940  push    r15
0x140034942  lea     rbp, [rsp-37h]
0x140034947  sub     rsp, 0D0h
0x14003494e  mov     rax, cs:__security_cookie
0x140034955  xor     rax, rsp
0x140034958  mov     [rbp+57h+var_30], rax
0x14003495c  mov     r15d, edx
0x14003495f  mov     r12, r8
0x140034962  xor     edx, edx; Val
0x140034964  mov     rdi, rcx
0x140034967  lea     rcx, [rbp+57h+var_9D]; void *
0x14003496b  lea     r8d, [rdx+65h]; Size
0x14003496f  call    memset_0
0x140034974  test    r15b, 1
0x140034978  jz      short loc_1400349A1
0x14003497a  mov     rcx, [rdi]
0x14003497d  lea     rdx, aJsonObjectRequ; "json_object() requires an even number o"...
0x140034984  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034988  mov     dword ptr [rdi+24h], 1
0x14003498f  mov     r9b, 1
0x140034992  mov     [rsp+0F0h+var_D0], r8
0x140034997  call    sqlite3VdbeMemSetStr
0x14003499c  jmp     loc_140034A9A
0x1400349a1  xor     esi, esi
0x1400349a3  mov     [rbp+57h+var_C0], rdi
0x1400349a7  mov     [rbp+57h+var_A0], 1
0x1400349ad  lea     rcx, [rbp+57h+var_9E]
0x1400349b1  mov     [rbp+57h+var_B8], rcx
0x1400349b5  mov     eax, 1
0x1400349ba  mov     [rbp+57h+var_B0], 64h ; 'd'
0x1400349c2  mov     [rbp+57h+var_9E], 7Bh ; '{'
0x1400349c6  mov     [rbp+57h+var_A8], rax
0x1400349ca  test    r15d, r15d
0x1400349cd  jle     loc_140034A79
0x1400349d3  movsxd  r14, esi
0x1400349d6  mov     rax, [r12+r14*8]
0x1400349da  movzx   ecx, word ptr [rax+14h]
0x1400349de  lea     rax, qword_1400B5170
0x1400349e5  and     ecx, 3Fh
0x1400349e8  cmp     byte ptr [rcx+rax], 3
0x1400349ec  jnz     loc_140034AC2
0x1400349f2  lea     rcx, [rbp+57h+var_C0]
0x1400349f6  call    jsonAppendSeparator
0x1400349fb  mov     rcx, [r12+r14*8]
0x1400349ff  mov     dl, 1
0x140034a01  call    sqlite3ValueText
0x140034a06  mov     rcx, [r12+r14*8]
0x140034a0a  mov     rbx, rax
0x140034a0d  call    sqlite3_value_bytes
0x140034a12  mov     r8d, eax
0x140034a15  lea     rcx, [rbp+57h+var_C0]
0x140034a19  mov     rdx, rbx
0x140034a1c  call    jsonAppendString
0x140034a21  mov     rcx, [rbp+57h+var_A8]
0x140034a25  cmp     rcx, [rbp+57h+var_B0]
0x140034a29  jb      short loc_140034A38
0x140034a2b  mov     dl, 3Ah ; ':'
0x140034a2d  lea     rcx, [rbp+57h+var_C0]
0x140034a31  call    jsonAppendCharExpand
0x140034a36  jmp     short loc_140034A44
0x140034a38  mov     rax, [rbp+57h+var_B8]
0x140034a3c  mov     byte ptr [rcx+rax], 3Ah ; ':'
0x140034a40  inc     [rbp+57h+var_A8]
0x140034a44  mov     rdx, [r12+r14*8+8]
0x140034a49  lea     rcx, [rbp+57h+var_C0]
0x140034a4d  call    jsonAppendValue
0x140034a52  add     esi, 2
0x140034a55  cmp     esi, r15d
0x140034a58  jl      loc_1400349D3
0x140034a5e  mov     rax, [rbp+57h+var_A8]
0x140034a62  cmp     rax, [rbp+57h+var_B0]
0x140034a66  jb      short loc_140034A75
0x140034a68  mov     dl, 7Dh ; '}'
0x140034a6a  lea     rcx, [rbp+57h+var_C0]
0x140034a6e  call    jsonAppendCharExpand
0x140034a73  jmp     short loc_140034A81
0x140034a75  mov     rcx, [rbp+57h+var_B8]
0x140034a79  mov     byte ptr [rax+rcx], 7Dh ; '}'
0x140034a7d  inc     [rbp+57h+var_A8]
0x140034a81  lea     rcx, [rbp+57h+var_C0]
0x140034a85  call    jsonResult
0x140034a8a  mov     rax, [rdi]
0x140034a8d  mov     ecx, 800h
0x140034a92  or      [rax+14h], cx
0x140034a96  mov     byte ptr [rax+17h], 4Ah ; 'J'
0x140034a9a  mov     rcx, [rbp+57h+var_30]
0x140034a9e  xor     rcx, rsp; StackCookie
0x140034aa1  call    __security_check_cookie
0x140034aa6  lea     r11, [rsp+0F0h+var_20]
0x140034aae  mov     rbx, [r11+38h]
0x140034ab2  mov     rsi, [r11+48h]
0x140034ab6  mov     rsp, r11
0x140034ab9  pop     r15
0x140034abb  pop     r14
0x140034abd  pop     r12
0x140034abf  pop     rdi
0x140034ac0  pop     rbp
0x140034ac1  retn
0x140034ac2  mov     rcx, [rdi]
0x140034ac5  lea     rdx, aJsonObjectLabe; "json_object() labels must be TEXT"
0x140034acc  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034ad0  mov     dword ptr [rdi+24h], 1
0x140034ad7  mov     r9b, 1
0x140034ada  mov     [rsp+0F0h+var_D0], r8
0x140034adf  call    sqlite3VdbeMemSetStr
0x140034ae4  lea     rcx, [rbp+57h+var_C0]
0x140034ae8  call    jsonReset
0x140034aed  jmp     short loc_140034A9A
```
