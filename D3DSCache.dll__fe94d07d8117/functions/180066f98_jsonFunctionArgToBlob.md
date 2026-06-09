# jsonFunctionArgToBlob

- ea: `0x180066f98`
- end: `0x1800671ac`
- name: `jsonFunctionArgToBlob`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180067314`

## callees

- `0x180042bb0`
- `0x180042dc4`
- `0x180045374`
- `0x1800657a8`
- `0x180065e14`
- `0x180066ed4`
- `0x180066f98`
- `0x18008c97c`
- `0x18008eb70`
- `0x180094470`
- `0x180096df0`
- `0x180096e70`
- `0x180098a80`
- `0x180098ce0`

## string_xrefs

- `0x18006703f`: `JSON cannot hold BLOB values`
- `0x1800670a0`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonFunctionArgToBlob(__int64 a1, __int64 a2, __int64 *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // edi
  int v10; // edi
  int v11; // edi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdi
  unsigned int v18; // r14d
  int v19; // eax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  const char *v22; // r9
  __int64 v23; // r8
  double v24; // xmm0_8
  unsigned int v25; // edi
  const char *v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rdx

  v6 = *((unsigned __int8 *)qword_1800B9DC0 + (*(_WORD *)(a2 + 20) & 0x3F));
  memset_0(a3, 0, 0x48u);
  a3[3] = sqlite3_context_db_handle(a1);
  v9 = v6 - 1;
  if ( !v9 )
  {
    LOBYTE(v7) = 1;
    v29 = sqlite3ValueBytes(a2, v7);
    LOBYTE(v30) = 1;
    v25 = v29;
    v26 = (const char *)sqlite3ValueText(a2, v30);
    if ( !v26 )
      return 1;
    LOBYTE(v20) = 3;
LABEL_27:
    v21 = a3;
    v23 = v25;
    v22 = v26;
LABEL_28:
    jsonBlobAppendNode(v21, v20, v23, v22);
    goto LABEL_29;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v24 = sqlite3VdbeRealValue(a2, v7, v8);
    v20 = 0x7FF0000000000000LL;
    if ( (*(_QWORD *)&v24 & 0xFFFFFFFFFFFFFLL) != 0 && (*(_QWORD *)&v24 & 0x7FF0000000000000LL) == 0x7FF0000000000000LL )
    {
      LOBYTE(v20) = 0;
      v25 = 0;
      v26 = 0;
    }
    else
    {
      LOBYTE(v20) = 1;
      v27 = sqlite3ValueBytes(a2, v20);
      LOBYTE(v28) = 1;
      v25 = v27;
      v26 = (const char *)sqlite3ValueText(a2, v28);
      if ( !v26 )
        return 1;
      if ( *v26 == 73 )
      {
        v20 = 5;
        v26 = "9e999";
        v25 = 5;
      }
      else
      {
        if ( *v26 == 45 && v26[1] == 73 )
        {
          v25 = 6;
          v26 = "-9e999";
        }
        v20 = 5;
      }
    }
    goto LABEL_27;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    LOBYTE(v7) = 1;
    v15 = sqlite3ValueText(a2, v7);
    LOBYTE(v16) = 1;
    v17 = v15;
    v18 = sqlite3ValueBytes(a2, v16);
    if ( !v17 )
      return 1;
    v19 = sqlite3_value_subtype(a2);
    v21 = a3;
    if ( v19 == 74 )
    {
      a3[2] = v17;
      *((_DWORD *)a3 + 8) = v18;
      if ( (unsigned int)jsonConvertTextToBlob(a3, a1) )
      {
        sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
        sqlite3DbFree(a3[3], *a3);
        memset_0(a3, 0, 0x48u);
        return 1;
      }
      goto LABEL_29;
    }
    v22 = (const char *)v17;
    v23 = v18;
    LOBYTE(v20) = 10;
    goto LABEL_28;
  }
  if ( v11 != 1 )
  {
    *((_DWORD *)a3 + 2) = 1;
    *a3 = (__int64)&qword_1800C7908;
    return 0;
  }
  if ( !(unsigned int)jsonFuncArgMightBeBinary(a2) )
  {
    sqlite3_result_error(a1, "JSON cannot hold BLOB values", 0xFFFFFFFFLL);
    return 1;
  }
  v13 = sqlite3_value_blob(a2);
  LOBYTE(v14) = 1;
  *a3 = v13;
  *((_DWORD *)a3 + 2) = sqlite3ValueBytes(a2, v14);
LABEL_29:
  if ( !*((_BYTE *)a3 + 47) )
    return 0;
  sqlite3_result_error_nomem(a1);
  return 1;
}

```

## disassembly

```asm
0x180066f98  push    rbx
0x180066f9a  push    rbp
0x180066f9b  push    rsi
0x180066f9c  push    rdi
0x180066f9d  push    r14
0x180066f9f  sub     rsp, 20h
0x180066fa3  movzx   eax, word ptr [rdx+14h]
0x180066fa7  mov     rbp, rcx
0x180066faa  mov     rbx, r8
0x180066fad  lea     rcx, qword_1800B9DC0
0x180066fb4  and     eax, 3Fh
0x180066fb7  mov     rsi, rdx
0x180066fba  xor     edx, edx; Val
0x180066fbc  movzx   edi, byte ptr [rax+rcx]
0x180066fc0  mov     rcx, rbx; void *
0x180066fc3  lea     r8d, [rdx+48h]; Size
0x180066fc7  call    memset_0
0x180066fcc  mov     rcx, rbp
0x180066fcf  call    sqlite3_context_db_handle
0x180066fd4  mov     [rbx+18h], rax
0x180066fd8  sub     edi, 1
0x180066fdb  jz      loc_180067166
0x180066fe1  sub     edi, 1
0x180066fe4  jz      loc_1800670D8
0x180066fea  sub     edi, 1
0x180066fed  jz      short loc_180067055
0x180066fef  cmp     edi, 1
0x180066ff2  jz      short loc_180067012
0x180066ff4  lea     rax, qword_1800C7908
0x180066ffb  mov     dword ptr [rbx+8], 1
0x180067002  mov     [rbx], rax
0x180067005  xor     eax, eax
0x180067007  add     rsp, 20h
0x18006700b  pop     r14
0x18006700d  pop     rdi
0x18006700e  pop     rsi
0x18006700f  pop     rbp
0x180067010  pop     rbx
0x180067011  retn
0x180067012  mov     rcx, rsi
0x180067015  call    jsonFuncArgMightBeBinary
0x18006701a  test    eax, eax
0x18006701c  jz      short loc_18006703B
0x18006701e  mov     rcx, rsi
0x180067021  call    sqlite3_value_blob
0x180067026  mov     dl, 1
0x180067028  mov     [rbx], rax
0x18006702b  mov     rcx, rsi
0x18006702e  call    sqlite3ValueBytes
0x180067033  mov     [rbx+8], eax
0x180067036  jmp     loc_180067195
0x18006703b  or      r8d, 0FFFFFFFFh
0x18006703f  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x180067046  mov     rcx, rbp
0x180067049  call    sqlite3_result_error
0x18006704e  mov     eax, 1
0x180067053  jmp     short loc_180067007
0x180067055  mov     dl, 1
0x180067057  mov     rcx, rsi
0x18006705a  call    sqlite3ValueText
0x18006705f  mov     dl, 1
0x180067061  mov     rcx, rsi
0x180067064  mov     rdi, rax
0x180067067  call    sqlite3ValueBytes
0x18006706c  mov     r14d, eax
0x18006706f  test    rdi, rdi
0x180067072  jz      short loc_18006704E
0x180067074  mov     rcx, rsi
0x180067077  call    sqlite3_value_subtype
0x18006707c  mov     rcx, rbx
0x18006707f  cmp     eax, 4Ah ; 'J'
0x180067082  jnz     short loc_1800670CB
0x180067084  mov     rdx, rbp
0x180067087  mov     [rbx+10h], rdi
0x18006708b  mov     [rbx+20h], r14d
0x18006708f  call    jsonConvertTextToBlob
0x180067094  test    eax, eax
0x180067096  jz      loc_180067195
0x18006709c  or      r8d, 0FFFFFFFFh
0x1800670a0  lea     rdx, aMalformedJson; "malformed JSON"
0x1800670a7  mov     rcx, rbp
0x1800670aa  call    sqlite3_result_error
0x1800670af  mov     rdx, [rbx]
0x1800670b2  mov     rcx, [rbx+18h]
0x1800670b6  call    sqlite3DbFree
0x1800670bb  xor     edx, edx; Val
0x1800670bd  mov     rcx, rbx; void *
0x1800670c0  lea     r8d, [rdx+48h]; Size
0x1800670c4  call    memset_0
0x1800670c9  jmp     short loc_18006704E
0x1800670cb  mov     r9, rdi
0x1800670ce  mov     r8d, r14d
0x1800670d1  mov     dl, 0Ah
0x1800670d3  jmp     loc_180067190
0x1800670d8  mov     rcx, rsi
0x1800670db  call    sqlite3VdbeRealValue
0x1800670e0  movq    rax, xmm0
0x1800670e5  mov     rcx, 0FFFFFFFFFFFFFh
0x1800670ef  test    rcx, rax
0x1800670f2  mov     rdx, 7FF0000000000000h
0x1800670fc  setnz   cl
0x1800670ff  and     rax, rdx
0x180067102  cmp     rax, rdx
0x180067105  setz    al
0x180067108  test    al, cl
0x18006710a  jz      short loc_180067114
0x18006710c  xor     dl, dl
0x18006710e  xor     edi, edi
0x180067110  xor     eax, eax
0x180067112  jmp     short loc_180067187
0x180067114  mov     dl, 1
0x180067116  mov     rcx, rsi
0x180067119  call    sqlite3ValueBytes
0x18006711e  mov     dl, 1
0x180067120  mov     rcx, rsi
0x180067123  mov     edi, eax
0x180067125  call    sqlite3ValueText
0x18006712a  test    rax, rax
0x18006712d  jz      loc_18006704E
0x180067133  cmp     byte ptr [rax], 49h ; 'I'
0x180067136  jnz     short loc_180067148
0x180067138  mov     edx, 5
0x18006713d  lea     rax, a9e999_0; "9e999"
0x180067144  mov     edi, edx
0x180067146  jmp     short loc_180067187
0x180067148  cmp     byte ptr [rax], 2Dh ; '-'
0x18006714b  jnz     short loc_18006715F
0x18006714d  cmp     byte ptr [rax+1], 49h ; 'I'
0x180067151  jnz     short loc_18006715F
0x180067153  mov     edi, 6
0x180067158  lea     rax, a9e999; "-9e999"
0x18006715f  mov     edx, 5
0x180067164  jmp     short loc_180067187
0x180067166  mov     dl, 1
0x180067168  mov     rcx, rsi
0x18006716b  call    sqlite3ValueBytes
0x180067170  mov     dl, 1
0x180067172  mov     rcx, rsi
0x180067175  mov     edi, eax
0x180067177  call    sqlite3ValueText
0x18006717c  test    rax, rax
0x18006717f  jz      loc_18006704E
0x180067185  mov     dl, 3
0x180067187  mov     rcx, rbx
0x18006718a  mov     r8d, edi
0x18006718d  mov     r9, rax
0x180067190  call    jsonBlobAppendNode
0x180067195  cmp     byte ptr [rbx+2Fh], 0
0x180067199  jz      loc_180067005
0x18006719f  mov     rcx, rbp
0x1800671a2  call    sqlite3_result_error_nomem
0x1800671a7  jmp     loc_18006704E
```
