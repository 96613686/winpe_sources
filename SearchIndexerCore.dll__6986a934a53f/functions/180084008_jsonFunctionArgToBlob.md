# jsonFunctionArgToBlob

- ea: `0x180084008`
- end: `0x18008421c`
- name: `jsonFunctionArgToBlob`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180084384`

## callees

- `0x180024b60`
- `0x180041d10`
- `0x18004c5f0`
- `0x180054e70`
- `0x180054ef4`
- `0x180070500`
- `0x180078968`
- `0x1800827b8`
- `0x180082ea4`
- `0x180083f44`
- `0x180084008`
- `0x18009d650`
- `0x18009d6d0`
- `0x18009ee40`

## string_xrefs

- `0x1800840af`: `JSON cannot hold BLOB values`
- `0x180084110`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonFunctionArgToBlob(__int64 a1, __int64 a2, __int64 *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  int v8; // edi
  int v9; // edi
  int v10; // edi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  const char *v16; // rdi
  unsigned int v17; // r14d
  int v18; // eax
  __int64 *v19; // rcx
  const char *v20; // r9
  unsigned int v21; // r8d
  char v22; // dl
  double v23; // xmm0_8
  __int64 v24; // rdx
  int v25; // edi
  const char *v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx

  v6 = *((unsigned __int8 *)qword_1800B5270 + (*(_WORD *)(a2 + 20) & 0x3F));
  memset_0(a3, 0, 0x48u);
  a3[3] = sqlite3_context_db_handle(a1);
  v8 = v6 - 1;
  if ( !v8 )
  {
    LOBYTE(v7) = 1;
    v29 = sqlite3ValueBytes(a2, v7);
    LOBYTE(v30) = 1;
    v25 = v29;
    v26 = (const char *)sqlite3ValueText(a2, v30);
    if ( !v26 )
      return 1;
    v22 = 3;
LABEL_27:
    v19 = a3;
    v21 = v25;
    v20 = v26;
LABEL_28:
    jsonBlobAppendNode(v19, v22, v21, v20);
    goto LABEL_29;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v23 = sqlite3VdbeRealValue(a2);
    v24 = 0x7FF0000000000000LL;
    if ( (*(_QWORD *)&v23 & 0xFFFFFFFFFFFFFLL) != 0 && (*(_QWORD *)&v23 & 0x7FF0000000000000LL) == 0x7FF0000000000000LL )
    {
      v22 = 0;
      v25 = 0;
      v26 = 0;
    }
    else
    {
      LOBYTE(v24) = 1;
      v27 = sqlite3ValueBytes(a2, v24);
      LOBYTE(v28) = 1;
      v25 = v27;
      v26 = (const char *)sqlite3ValueText(a2, v28);
      if ( !v26 )
        return 1;
      if ( *v26 == 73 )
      {
        v22 = 5;
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
        v22 = 5;
      }
    }
    goto LABEL_27;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    LOBYTE(v7) = 1;
    v14 = sqlite3ValueText(a2, v7);
    LOBYTE(v15) = 1;
    v16 = (const char *)v14;
    v17 = sqlite3ValueBytes(a2, v15);
    if ( !v16 )
      return 1;
    v18 = sqlite3_value_subtype(a2);
    v19 = a3;
    if ( v18 == 74 )
    {
      a3[2] = (__int64)v16;
      *((_DWORD *)a3 + 8) = v17;
      if ( (unsigned int)jsonConvertTextToBlob((__int64)a3, a1) )
      {
        sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
        sqlite3DbFree(a3[3], *a3);
        memset_0(a3, 0, 0x48u);
        return 1;
      }
      goto LABEL_29;
    }
    v20 = v16;
    v21 = v17;
    v22 = 10;
    goto LABEL_28;
  }
  if ( v10 != 1 )
  {
    *((_DWORD *)a3 + 2) = 1;
    *a3 = (__int64)qword_1800D0DE0;
    return 0;
  }
  if ( !(unsigned int)jsonFuncArgMightBeBinary(a2) )
  {
    sqlite3_result_error(a1, "JSON cannot hold BLOB values", 0xFFFFFFFFLL);
    return 1;
  }
  v12 = sqlite3_value_blob(a2);
  LOBYTE(v13) = 1;
  *a3 = v12;
  *((_DWORD *)a3 + 2) = sqlite3ValueBytes(a2, v13);
LABEL_29:
  if ( !*((_BYTE *)a3 + 47) )
    return 0;
  sqlite3_result_error_nomem(a1);
  return 1;
}

```

## disassembly

```asm
0x180084008  push    rbx
0x18008400a  push    rbp
0x18008400b  push    rsi
0x18008400c  push    rdi
0x18008400d  push    r14
0x18008400f  sub     rsp, 20h
0x180084013  movzx   eax, word ptr [rdx+14h]
0x180084017  mov     rbp, rcx
0x18008401a  mov     rbx, r8
0x18008401d  lea     rcx, qword_1800B5270
0x180084024  and     eax, 3Fh
0x180084027  mov     rsi, rdx
0x18008402a  xor     edx, edx; Val
0x18008402c  movzx   edi, byte ptr [rax+rcx]
0x180084030  mov     rcx, rbx; void *
0x180084033  lea     r8d, [rdx+48h]; Size
0x180084037  call    memset_0
0x18008403c  mov     rcx, rbp
0x18008403f  call    sqlite3_context_db_handle
0x180084044  mov     [rbx+18h], rax
0x180084048  sub     edi, 1
0x18008404b  jz      loc_1800841D6
0x180084051  sub     edi, 1
0x180084054  jz      loc_180084148
0x18008405a  sub     edi, 1
0x18008405d  jz      short loc_1800840C5
0x18008405f  cmp     edi, 1
0x180084062  jz      short loc_180084082
0x180084064  lea     rax, qword_1800D0DE0
0x18008406b  mov     dword ptr [rbx+8], 1
0x180084072  mov     [rbx], rax
0x180084075  xor     eax, eax
0x180084077  add     rsp, 20h
0x18008407b  pop     r14
0x18008407d  pop     rdi
0x18008407e  pop     rsi
0x18008407f  pop     rbp
0x180084080  pop     rbx
0x180084081  retn
0x180084082  mov     rcx, rsi
0x180084085  call    jsonFuncArgMightBeBinary
0x18008408a  test    eax, eax
0x18008408c  jz      short loc_1800840AB
0x18008408e  mov     rcx, rsi
0x180084091  call    sqlite3_value_blob
0x180084096  mov     dl, 1
0x180084098  mov     [rbx], rax
0x18008409b  mov     rcx, rsi
0x18008409e  call    sqlite3ValueBytes
0x1800840a3  mov     [rbx+8], eax
0x1800840a6  jmp     loc_180084205
0x1800840ab  or      r8d, 0FFFFFFFFh
0x1800840af  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x1800840b6  mov     rcx, rbp
0x1800840b9  call    sqlite3_result_error
0x1800840be  mov     eax, 1
0x1800840c3  jmp     short loc_180084077
0x1800840c5  mov     dl, 1
0x1800840c7  mov     rcx, rsi
0x1800840ca  call    sqlite3ValueText
0x1800840cf  mov     dl, 1
0x1800840d1  mov     rcx, rsi
0x1800840d4  mov     rdi, rax
0x1800840d7  call    sqlite3ValueBytes
0x1800840dc  mov     r14d, eax
0x1800840df  test    rdi, rdi
0x1800840e2  jz      short loc_1800840BE
0x1800840e4  mov     rcx, rsi
0x1800840e7  call    sqlite3_value_subtype
0x1800840ec  mov     rcx, rbx
0x1800840ef  cmp     eax, 4Ah ; 'J'
0x1800840f2  jnz     short loc_18008413B
0x1800840f4  mov     rdx, rbp
0x1800840f7  mov     [rbx+10h], rdi
0x1800840fb  mov     [rbx+20h], r14d
0x1800840ff  call    jsonConvertTextToBlob
0x180084104  test    eax, eax
0x180084106  jz      loc_180084205
0x18008410c  or      r8d, 0FFFFFFFFh
0x180084110  lea     rdx, aMalformedJson; "malformed JSON"
0x180084117  mov     rcx, rbp
0x18008411a  call    sqlite3_result_error
0x18008411f  mov     rdx, [rbx]
0x180084122  mov     rcx, [rbx+18h]
0x180084126  call    sqlite3DbFree
0x18008412b  xor     edx, edx; Val
0x18008412d  mov     rcx, rbx; void *
0x180084130  lea     r8d, [rdx+48h]; Size
0x180084134  call    memset_0
0x180084139  jmp     short loc_1800840BE
0x18008413b  mov     r9, rdi
0x18008413e  mov     r8d, r14d
0x180084141  mov     dl, 0Ah
0x180084143  jmp     loc_180084200
0x180084148  mov     rcx, rsi
0x18008414b  call    sqlite3VdbeRealValue
0x180084150  movq    rax, xmm0
0x180084155  mov     rcx, 0FFFFFFFFFFFFFh
0x18008415f  test    rcx, rax
0x180084162  mov     rdx, 7FF0000000000000h
0x18008416c  setnz   cl
0x18008416f  and     rax, rdx
0x180084172  cmp     rax, rdx
0x180084175  setz    al
0x180084178  test    al, cl
0x18008417a  jz      short loc_180084184
0x18008417c  xor     dl, dl
0x18008417e  xor     edi, edi
0x180084180  xor     eax, eax
0x180084182  jmp     short loc_1800841F7
0x180084184  mov     dl, 1
0x180084186  mov     rcx, rsi
0x180084189  call    sqlite3ValueBytes
0x18008418e  mov     dl, 1
0x180084190  mov     rcx, rsi
0x180084193  mov     edi, eax
0x180084195  call    sqlite3ValueText
0x18008419a  test    rax, rax
0x18008419d  jz      loc_1800840BE
0x1800841a3  cmp     byte ptr [rax], 49h ; 'I'
0x1800841a6  jnz     short loc_1800841B8
0x1800841a8  mov     edx, 5
0x1800841ad  lea     rax, a9e999_0; "9e999"
0x1800841b4  mov     edi, edx
0x1800841b6  jmp     short loc_1800841F7
0x1800841b8  cmp     byte ptr [rax], 2Dh ; '-'
0x1800841bb  jnz     short loc_1800841CF
0x1800841bd  cmp     byte ptr [rax+1], 49h ; 'I'
0x1800841c1  jnz     short loc_1800841CF
0x1800841c3  mov     edi, 6
0x1800841c8  lea     rax, a9e999; "-9e999"
0x1800841cf  mov     edx, 5
0x1800841d4  jmp     short loc_1800841F7
0x1800841d6  mov     dl, 1
0x1800841d8  mov     rcx, rsi
0x1800841db  call    sqlite3ValueBytes
0x1800841e0  mov     dl, 1
0x1800841e2  mov     rcx, rsi
0x1800841e5  mov     edi, eax
0x1800841e7  call    sqlite3ValueText
0x1800841ec  test    rax, rax
0x1800841ef  jz      loc_1800840BE
0x1800841f5  mov     dl, 3
0x1800841f7  mov     rcx, rbx
0x1800841fa  mov     r8d, edi
0x1800841fd  mov     r9, rax
0x180084200  call    jsonBlobAppendNode
0x180084205  cmp     byte ptr [rbx+2Fh], 0
0x180084209  jz      loc_180084075
0x18008420f  mov     rcx, rbp
0x180084212  call    sqlite3_result_error_nomem
0x180084217  jmp     loc_1800840BE
```
