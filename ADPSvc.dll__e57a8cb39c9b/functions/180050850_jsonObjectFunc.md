# jsonObjectFunc

- ea: `0x180050850`
- end: `0x180050a14`
- name: `jsonObjectFunc`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18004d338`
- `0x18004d584`
- `0x18004d5bc`
- `0x18004d74c`
- `0x180050850`
- `0x18005194c`
- `0x180051dfc`
- `0x180092290`
- `0x18009b4ec`
- `0x1800ae720`

## string_xrefs

- `0x18005089d`: `json_object() requires an even number of arguments`
- `0x1800509ea`: `json_object() labels must be TEXT`

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
        if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(*(_QWORD *)(a3 + 8LL * v9) + 20LL) & 0x3F)) != 3 )
        {
          v17 = *(_QWORD *)a1;
          *(_DWORD *)(a1 + 36) = 1;
          LOBYTE(v6) = 1;
          sqlite3VdbeMemSetStr(v17, "json_object() labels must be TEXT", -1, v6, -1);
          return jsonStringReset(&v18);
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
        jsonAppendSqlValue(&v18, *(_QWORD *)(a3 + 8LL * v9 + 8));
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
    jsonReturnString(&v18, 0, 0);
    result = *(_QWORD *)a1;
    *(_WORD *)(result + 20) |= 0x800u;
    *(_BYTE *)(result + 23) = 74;
  }
  return result;
}

```

## disassembly

```asm
0x180050850  mov     [rsp-8+arg_8], rbx
0x180050855  mov     [rsp-8+arg_18], rsi
0x18005085a  push    rbp
0x18005085b  push    rdi
0x18005085c  push    r12
0x18005085e  push    r14
0x180050860  push    r15
0x180050862  lea     rbp, [rsp-37h]
0x180050867  sub     rsp, 0D0h
0x18005086e  mov     rax, cs:__security_cookie
0x180050875  xor     rax, rsp
0x180050878  mov     [rbp+57h+var_30], rax
0x18005087c  mov     r15d, edx
0x18005087f  mov     r12, r8
0x180050882  xor     edx, edx; Val
0x180050884  mov     rdi, rcx
0x180050887  lea     rcx, [rbp+57h+var_9D]; void *
0x18005088b  lea     r8d, [rdx+65h]; Size
0x18005088f  call    memset_0
0x180050894  test    r15b, 1
0x180050898  jz      short loc_1800508C1
0x18005089a  mov     rcx, [rdi]
0x18005089d  lea     rdx, aJsonObjectRequ; "json_object() requires an even number o"...
0x1800508a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800508a8  mov     dword ptr [rdi+24h], 1
0x1800508af  mov     r9b, 1
0x1800508b2  mov     [rsp+0F0h+var_D0], r8
0x1800508b7  call    sqlite3VdbeMemSetStr
0x1800508bc  jmp     loc_1800509BF
0x1800508c1  xor     esi, esi
0x1800508c3  mov     [rbp+57h+var_C0], rdi
0x1800508c7  mov     [rbp+57h+var_A0], 1
0x1800508cd  lea     rcx, [rbp+57h+var_9E]
0x1800508d1  mov     [rbp+57h+var_B8], rcx
0x1800508d5  mov     eax, 1
0x1800508da  mov     [rbp+57h+var_B0], 64h ; 'd'
0x1800508e2  mov     [rbp+57h+var_9E], 7Bh ; '{'
0x1800508e6  mov     [rbp+57h+var_A8], rax
0x1800508ea  test    r15d, r15d
0x1800508ed  jle     loc_180050999
0x1800508f3  movsxd  r14, esi
0x1800508f6  mov     rax, [r12+r14*8]
0x1800508fa  movzx   ecx, word ptr [rax+14h]
0x1800508fe  lea     rax, qword_1800FE430
0x180050905  and     ecx, 3Fh
0x180050908  cmp     byte ptr [rcx+rax], 3
0x18005090c  jnz     loc_1800509E7
0x180050912  lea     rcx, [rbp+57h+var_C0]
0x180050916  call    jsonAppendSeparator
0x18005091b  mov     rcx, [r12+r14*8]
0x18005091f  mov     dl, 1
0x180050921  call    sqlite3ValueText
0x180050926  mov     rcx, [r12+r14*8]
0x18005092a  mov     rbx, rax
0x18005092d  call    sqlite3_value_bytes
0x180050932  mov     r8d, eax
0x180050935  lea     rcx, [rbp+57h+var_C0]
0x180050939  mov     rdx, rbx
0x18005093c  call    jsonAppendString
0x180050941  mov     rcx, [rbp+57h+var_A8]
0x180050945  cmp     rcx, [rbp+57h+var_B0]
0x180050949  jb      short loc_180050958
0x18005094b  mov     dl, 3Ah ; ':'
0x18005094d  lea     rcx, [rbp+57h+var_C0]
0x180050951  call    jsonAppendCharExpand
0x180050956  jmp     short loc_180050964
0x180050958  mov     rax, [rbp+57h+var_B8]
0x18005095c  mov     byte ptr [rcx+rax], 3Ah ; ':'
0x180050960  inc     [rbp+57h+var_A8]
0x180050964  mov     rdx, [r12+r14*8+8]
0x180050969  lea     rcx, [rbp+57h+var_C0]
0x18005096d  call    jsonAppendSqlValue
0x180050972  add     esi, 2
0x180050975  cmp     esi, r15d
0x180050978  jl      loc_1800508F3
0x18005097e  mov     rax, [rbp+57h+var_A8]
0x180050982  cmp     rax, [rbp+57h+var_B0]
0x180050986  jb      short loc_180050995
0x180050988  mov     dl, 7Dh ; '}'
0x18005098a  lea     rcx, [rbp+57h+var_C0]
0x18005098e  call    jsonAppendCharExpand
0x180050993  jmp     short loc_1800509A1
0x180050995  mov     rcx, [rbp+57h+var_B8]
0x180050999  mov     byte ptr [rax+rcx], 7Dh ; '}'
0x18005099d  inc     [rbp+57h+var_A8]
0x1800509a1  xor     r8d, r8d
0x1800509a4  lea     rcx, [rbp+57h+var_C0]
0x1800509a8  xor     edx, edx
0x1800509aa  call    jsonReturnString
0x1800509af  mov     rax, [rdi]
0x1800509b2  mov     ecx, 800h
0x1800509b7  or      [rax+14h], cx
0x1800509bb  mov     byte ptr [rax+17h], 4Ah ; 'J'
0x1800509bf  mov     rcx, [rbp+57h+var_30]
0x1800509c3  xor     rcx, rsp; StackCookie
0x1800509c6  call    __security_check_cookie
0x1800509cb  lea     r11, [rsp+0F0h+var_20]
0x1800509d3  mov     rbx, [r11+38h]
0x1800509d7  mov     rsi, [r11+48h]
0x1800509db  mov     rsp, r11
0x1800509de  pop     r15
0x1800509e0  pop     r14
0x1800509e2  pop     r12
0x1800509e4  pop     rdi
0x1800509e5  pop     rbp
0x1800509e6  retn
0x1800509e7  mov     rcx, [rdi]
0x1800509ea  lea     rdx, aJsonObjectLabe; "json_object() labels must be TEXT"
0x1800509f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800509f5  mov     dword ptr [rdi+24h], 1
0x1800509fc  mov     r9b, 1
0x1800509ff  mov     [rsp+0F0h+var_D0], r8
0x180050a04  call    sqlite3VdbeMemSetStr
0x180050a09  lea     rcx, [rbp+57h+var_C0]
0x180050a0d  call    jsonStringReset
0x180050a12  jmp     short loc_1800509BF
```
