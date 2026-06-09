# likeFunc

- ea: `0x1800794b0`
- end: `0x1800795e1`
- name: `likeFunc`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180028540`
- `0x180048740`
- `0x180048d20`
- `0x180048d38`
- `0x18004b520`
- `0x18005b544`
- `0x18005b910`
- `0x18005ede0`
- `0x1800794b0`
- `0x18008f3f0`

## string_xrefs

- `0x1800794f7`: `LIKE or GLOB pattern too complex`

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
0x1800794b0  mov     [rsp+arg_0], rbx
0x1800794b5  mov     [rsp+arg_8], rbp
0x1800794ba  push    rsi
0x1800794bb  push    rdi
0x1800794bc  push    r14
0x1800794be  sub     rsp, 20h
0x1800794c2  mov     r14, r8
0x1800794c5  mov     ebp, edx
0x1800794c7  mov     rsi, rcx
0x1800794ca  call    sqlite3_context_db_handle
0x1800794cf  mov     rcx, rsi
0x1800794d2  mov     rbx, rax
0x1800794d5  call    sqlite3_user_data
0x1800794da  mov     rcx, [r14]
0x1800794dd  mov     dl, 1
0x1800794df  mov     rdi, rax
0x1800794e2  mov     [rsp+38h+arg_10], 0
0x1800794ea  call    sqlite3ValueBytes
0x1800794ef  cmp     eax, [rbx+0A8h]
0x1800794f5  jle     short loc_18007950F
0x1800794f7  lea     rdx, aLikeOrGlobPatt; "LIKE or GLOB pattern too complex"
0x1800794fe  or      r8d, 0FFFFFFFFh
0x180079502  mov     rcx, rsi
0x180079505  call    sqlite3_result_error
0x18007950a  jmp     loc_1800795CE
0x18007950f  cmp     ebp, 3
0x180079512  jnz     short loc_180079588
0x180079514  mov     rcx, [r14+10h]
0x180079518  mov     dl, 1
0x18007951a  call    sqlite3ValueText
0x18007951f  mov     [rsp+38h+arg_18], rax
0x180079524  test    rax, rax
0x180079527  jz      loc_1800795CE
0x18007952d  or      edx, 0FFFFFFFFh
0x180079530  mov     rcx, rax
0x180079533  call    sqlite3Utf8CharLen
0x180079538  cmp     eax, 1
0x18007953b  jz      short loc_180079546
0x18007953d  lea     rdx, aEscapeExpressi; "ESCAPE expression must be a single char"...
0x180079544  jmp     short loc_1800794FE
0x180079546  lea     rcx, [rsp+38h+arg_18]
0x18007954b  call    sqlite3Utf8Read
0x180079550  movzx   ecx, byte ptr [rdi]
0x180079553  mov     ebx, eax
0x180079555  cmp     eax, ecx
0x180079557  jz      short loc_180079561
0x180079559  movzx   ecx, byte ptr [rdi+1]
0x18007955d  cmp     eax, ecx
0x18007955f  jnz     short loc_18007958C
0x180079561  mov     ecx, [rdi]
0x180079563  lea     rdi, [rsp+38h+arg_10]
0x180079568  mov     [rsp+38h+arg_10], ecx
0x18007956c  movzx   ecx, cl
0x18007956f  cmp     ebx, ecx
0x180079571  jnz     short loc_180079578
0x180079573  mov     byte ptr [rsp+38h+arg_10], 0
0x180079578  movzx   eax, byte ptr [rsp+38h+arg_10+1]
0x18007957d  cmp     ebx, eax
0x18007957f  jnz     short loc_18007958C
0x180079581  mov     byte ptr [rsp+38h+arg_10+1], 0
0x180079586  jmp     short loc_18007958C
0x180079588  movzx   ebx, byte ptr [rdi+2]
0x18007958c  mov     rcx, [r14]
0x18007958f  mov     dl, 1
0x180079591  call    sqlite3ValueText
0x180079596  mov     rcx, [r14+8]
0x18007959a  mov     dl, 1
0x18007959c  mov     rbp, rax
0x18007959f  call    sqlite3ValueText
0x1800795a4  test    rax, rax
0x1800795a7  jz      short loc_1800795CE
0x1800795a9  test    rbp, rbp
0x1800795ac  jz      short loc_1800795CE
0x1800795ae  mov     r9d, ebx
0x1800795b1  mov     r8, rdi
0x1800795b4  mov     rdx, rax
0x1800795b7  mov     rcx, rbp
0x1800795ba  call    patternCompare
0x1800795bf  xor     edx, edx
0x1800795c1  mov     rcx, rsi
0x1800795c4  test    eax, eax
0x1800795c6  setz    dl
0x1800795c9  call    sqlite3_result_int
0x1800795ce  mov     rbx, [rsp+38h+arg_0]
0x1800795d3  mov     rbp, [rsp+38h+arg_8]
0x1800795d8  add     rsp, 20h
0x1800795dc  pop     r14
0x1800795de  pop     rdi
0x1800795df  pop     rsi
0x1800795e0  retn
```
