# likeFunc

- ea: `0x18006b650`
- end: `0x18006b781`
- name: `likeFunc`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180042dc4`
- `0x18006b650`
- `0x18006fcc8`
- `0x18008c5fc`
- `0x18008c658`
- `0x18008c97c`
- `0x180094470`
- `0x180096df0`
- `0x180096ef0`
- `0x180098a60`

## string_xrefs

- `0x18006b697`: `LIKE or GLOB pattern too complex`

## pseudocode

```c
__int64 __fastcall likeFunc(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned __int8 *v11; // rdi
  __int64 v12; // rdx
  const char *v13; // rdx
  __int64 result; // rax
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rbp
  int v21; // eax
  int v22; // [rsp+50h] [rbp+18h] BYREF
  __int64 v23; // [rsp+58h] [rbp+20h] BYREF

  v6 = sqlite3_context_db_handle(a1);
  v8 = sqlite3_user_data(a1, v7);
  v9 = *a3;
  LOBYTE(v10) = 1;
  v11 = (unsigned __int8 *)v8;
  v22 = 0;
  if ( (int)sqlite3ValueBytes(v9, v10) > *(_DWORD *)(v6 + 168) )
  {
    v13 = "LIKE or GLOB pattern too complex";
    return sqlite3_result_error(a1, v13, 0xFFFFFFFFLL);
  }
  if ( a2 == 3 )
  {
    LOBYTE(v12) = 1;
    result = sqlite3ValueText(a3[2], v12);
    v23 = result;
    if ( !result )
      return result;
    if ( (unsigned int)sqlite3Utf8CharLen(result, 0xFFFFFFFFLL) != 1 )
    {
      v13 = "ESCAPE expression must be a single character";
      return sqlite3_result_error(a1, v13, 0xFFFFFFFFLL);
    }
    v15 = sqlite3Utf8Read(&v23);
    v16 = v15;
    if ( v15 == *v11 || v15 == v11[1] )
    {
      v17 = *(_DWORD *)v11;
      v11 = (unsigned __int8 *)&v22;
      v22 = v17;
      if ( v15 == (unsigned __int8)v17 )
        LOBYTE(v22) = 0;
      if ( v15 == BYTE1(v22) )
        BYTE1(v22) = 0;
    }
  }
  else
  {
    v16 = v11[2];
  }
  LOBYTE(v12) = 1;
  v18 = sqlite3ValueText(*a3, v12);
  LOBYTE(v19) = 1;
  v20 = v18;
  result = sqlite3ValueText(a3[1], v19);
  if ( result )
  {
    if ( v20 )
    {
      v21 = patternCompare(v20, result, v11, v16);
      return sqlite3_result_int(a1, v21 == 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006b650  mov     [rsp+arg_0], rbx
0x18006b655  mov     [rsp+arg_8], rbp
0x18006b65a  push    rsi
0x18006b65b  push    rdi
0x18006b65c  push    r14
0x18006b65e  sub     rsp, 20h
0x18006b662  mov     r14, r8
0x18006b665  mov     ebp, edx
0x18006b667  mov     rsi, rcx
0x18006b66a  call    sqlite3_context_db_handle
0x18006b66f  mov     rcx, rsi
0x18006b672  mov     rbx, rax
0x18006b675  call    sqlite3_user_data
0x18006b67a  mov     rcx, [r14]
0x18006b67d  mov     dl, 1
0x18006b67f  mov     rdi, rax
0x18006b682  mov     [rsp+38h+arg_10], 0
0x18006b68a  call    sqlite3ValueBytes
0x18006b68f  cmp     eax, [rbx+0A8h]
0x18006b695  jle     short loc_18006B6AF
0x18006b697  lea     rdx, aLikeOrGlobPatt; "LIKE or GLOB pattern too complex"
0x18006b69e  or      r8d, 0FFFFFFFFh
0x18006b6a2  mov     rcx, rsi
0x18006b6a5  call    sqlite3_result_error
0x18006b6aa  jmp     loc_18006B76E
0x18006b6af  cmp     ebp, 3
0x18006b6b2  jnz     short loc_18006B728
0x18006b6b4  mov     rcx, [r14+10h]
0x18006b6b8  mov     dl, 1
0x18006b6ba  call    sqlite3ValueText
0x18006b6bf  mov     [rsp+38h+arg_18], rax
0x18006b6c4  test    rax, rax
0x18006b6c7  jz      loc_18006B76E
0x18006b6cd  or      edx, 0FFFFFFFFh
0x18006b6d0  mov     rcx, rax
0x18006b6d3  call    sqlite3Utf8CharLen
0x18006b6d8  cmp     eax, 1
0x18006b6db  jz      short loc_18006B6E6
0x18006b6dd  lea     rdx, aEscapeExpressi; "ESCAPE expression must be a single char"...
0x18006b6e4  jmp     short loc_18006B69E
0x18006b6e6  lea     rcx, [rsp+38h+arg_18]
0x18006b6eb  call    sqlite3Utf8Read
0x18006b6f0  movzx   ecx, byte ptr [rdi]
0x18006b6f3  mov     ebx, eax
0x18006b6f5  cmp     eax, ecx
0x18006b6f7  jz      short loc_18006B701
0x18006b6f9  movzx   ecx, byte ptr [rdi+1]
0x18006b6fd  cmp     eax, ecx
0x18006b6ff  jnz     short loc_18006B72C
0x18006b701  mov     ecx, [rdi]
0x18006b703  lea     rdi, [rsp+38h+arg_10]
0x18006b708  mov     [rsp+38h+arg_10], ecx
0x18006b70c  movzx   ecx, cl
0x18006b70f  cmp     ebx, ecx
0x18006b711  jnz     short loc_18006B718
0x18006b713  mov     byte ptr [rsp+38h+arg_10], 0
0x18006b718  movzx   eax, byte ptr [rsp+38h+arg_10+1]
0x18006b71d  cmp     ebx, eax
0x18006b71f  jnz     short loc_18006B72C
0x18006b721  mov     byte ptr [rsp+38h+arg_10+1], 0
0x18006b726  jmp     short loc_18006B72C
0x18006b728  movzx   ebx, byte ptr [rdi+2]
0x18006b72c  mov     rcx, [r14]
0x18006b72f  mov     dl, 1
0x18006b731  call    sqlite3ValueText
0x18006b736  mov     rcx, [r14+8]
0x18006b73a  mov     dl, 1
0x18006b73c  mov     rbp, rax
0x18006b73f  call    sqlite3ValueText
0x18006b744  test    rax, rax
0x18006b747  jz      short loc_18006B76E
0x18006b749  test    rbp, rbp
0x18006b74c  jz      short loc_18006B76E
0x18006b74e  mov     r9d, ebx
0x18006b751  mov     r8, rdi
0x18006b754  mov     rdx, rax
0x18006b757  mov     rcx, rbp
0x18006b75a  call    patternCompare
0x18006b75f  xor     edx, edx
0x18006b761  mov     rcx, rsi
0x18006b764  test    eax, eax
0x18006b766  setz    dl
0x18006b769  call    sqlite3_result_int
0x18006b76e  mov     rbx, [rsp+38h+arg_0]
0x18006b773  mov     rbp, [rsp+38h+arg_8]
0x18006b778  add     rsp, 20h
0x18006b77c  pop     r14
0x18006b77e  pop     rdi
0x18006b77f  pop     rsi
0x18006b780  retn
```
