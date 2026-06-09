# likeFunc

- ea: `0x1800886c0`
- end: `0x1800887f1`
- name: `likeFunc`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180024b60`
- `0x180054ef4`
- `0x180070500`
- `0x180070520`
- `0x1800886c0`
- `0x18008b340`
- `0x180098e14`
- `0x180098e70`
- `0x18009d650`
- `0x18009ed10`

## string_xrefs

- `0x180088707`: `LIKE or GLOB pattern too complex`

## pseudocode

```c
__int64 __fastcall likeFunc(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int8 *v10; // rdi
  __int64 v11; // rdx
  const char *v12; // rdx
  __int64 result; // rax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rbp
  int v20; // eax
  int v21; // [rsp+50h] [rbp+18h] BYREF
  __int64 v22; // [rsp+58h] [rbp+20h] BYREF

  v6 = sqlite3_context_db_handle(a1);
  v7 = sqlite3_user_data(a1);
  v8 = *a3;
  LOBYTE(v9) = 1;
  v10 = (unsigned __int8 *)v7;
  v21 = 0;
  if ( (int)sqlite3ValueBytes(v8, v9) > *(_DWORD *)(v6 + 168) )
  {
    v12 = "LIKE or GLOB pattern too complex";
    return sqlite3_result_error(a1, v12, 0xFFFFFFFFLL);
  }
  if ( a2 == 3 )
  {
    LOBYTE(v11) = 1;
    result = sqlite3ValueText(a3[2], v11);
    v22 = result;
    if ( !result )
      return result;
    if ( (unsigned int)sqlite3Utf8CharLen(result, 0xFFFFFFFFLL) != 1 )
    {
      v12 = "ESCAPE expression must be a single character";
      return sqlite3_result_error(a1, v12, 0xFFFFFFFFLL);
    }
    v14 = sqlite3Utf8Read(&v22);
    v15 = v14;
    if ( v14 == *v10 || v14 == v10[1] )
    {
      v16 = *(_DWORD *)v10;
      v10 = (unsigned __int8 *)&v21;
      v21 = v16;
      if ( v14 == (unsigned __int8)v16 )
        LOBYTE(v21) = 0;
      if ( v14 == BYTE1(v21) )
        BYTE1(v21) = 0;
    }
  }
  else
  {
    v15 = v10[2];
  }
  LOBYTE(v11) = 1;
  v17 = sqlite3ValueText(*a3, v11);
  LOBYTE(v18) = 1;
  v19 = v17;
  result = sqlite3ValueText(a3[1], v18);
  if ( result )
  {
    if ( v19 )
    {
      v20 = patternCompare(v19, result, v10, v15);
      return sqlite3_result_int(a1, v20 == 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800886c0  mov     [rsp+arg_0], rbx
0x1800886c5  mov     [rsp+arg_8], rbp
0x1800886ca  push    rsi
0x1800886cb  push    rdi
0x1800886cc  push    r14
0x1800886ce  sub     rsp, 20h
0x1800886d2  mov     r14, r8
0x1800886d5  mov     ebp, edx
0x1800886d7  mov     rsi, rcx
0x1800886da  call    sqlite3_context_db_handle
0x1800886df  mov     rcx, rsi
0x1800886e2  mov     rbx, rax
0x1800886e5  call    sqlite3_user_data
0x1800886ea  mov     rcx, [r14]
0x1800886ed  mov     dl, 1
0x1800886ef  mov     rdi, rax
0x1800886f2  mov     [rsp+38h+arg_10], 0
0x1800886fa  call    sqlite3ValueBytes
0x1800886ff  cmp     eax, [rbx+0A8h]
0x180088705  jle     short loc_18008871F
0x180088707  lea     rdx, aLikeOrGlobPatt; "LIKE or GLOB pattern too complex"
0x18008870e  or      r8d, 0FFFFFFFFh
0x180088712  mov     rcx, rsi
0x180088715  call    sqlite3_result_error
0x18008871a  jmp     loc_1800887DE
0x18008871f  cmp     ebp, 3
0x180088722  jnz     short loc_180088798
0x180088724  mov     rcx, [r14+10h]
0x180088728  mov     dl, 1
0x18008872a  call    sqlite3ValueText
0x18008872f  mov     [rsp+38h+arg_18], rax
0x180088734  test    rax, rax
0x180088737  jz      loc_1800887DE
0x18008873d  or      edx, 0FFFFFFFFh
0x180088740  mov     rcx, rax
0x180088743  call    sqlite3Utf8CharLen
0x180088748  cmp     eax, 1
0x18008874b  jz      short loc_180088756
0x18008874d  lea     rdx, aEscapeExpressi; "ESCAPE expression must be a single char"...
0x180088754  jmp     short loc_18008870E
0x180088756  lea     rcx, [rsp+38h+arg_18]
0x18008875b  call    sqlite3Utf8Read
0x180088760  movzx   ecx, byte ptr [rdi]
0x180088763  mov     ebx, eax
0x180088765  cmp     eax, ecx
0x180088767  jz      short loc_180088771
0x180088769  movzx   ecx, byte ptr [rdi+1]
0x18008876d  cmp     eax, ecx
0x18008876f  jnz     short loc_18008879C
0x180088771  mov     ecx, [rdi]
0x180088773  lea     rdi, [rsp+38h+arg_10]
0x180088778  mov     [rsp+38h+arg_10], ecx
0x18008877c  movzx   ecx, cl
0x18008877f  cmp     ebx, ecx
0x180088781  jnz     short loc_180088788
0x180088783  mov     byte ptr [rsp+38h+arg_10], 0
0x180088788  movzx   eax, byte ptr [rsp+38h+arg_10+1]
0x18008878d  cmp     ebx, eax
0x18008878f  jnz     short loc_18008879C
0x180088791  mov     byte ptr [rsp+38h+arg_10+1], 0
0x180088796  jmp     short loc_18008879C
0x180088798  movzx   ebx, byte ptr [rdi+2]
0x18008879c  mov     rcx, [r14]
0x18008879f  mov     dl, 1
0x1800887a1  call    sqlite3ValueText
0x1800887a6  mov     rcx, [r14+8]
0x1800887aa  mov     dl, 1
0x1800887ac  mov     rbp, rax
0x1800887af  call    sqlite3ValueText
0x1800887b4  test    rax, rax
0x1800887b7  jz      short loc_1800887DE
0x1800887b9  test    rbp, rbp
0x1800887bc  jz      short loc_1800887DE
0x1800887be  mov     r9d, ebx
0x1800887c1  mov     r8, rdi
0x1800887c4  mov     rdx, rax
0x1800887c7  mov     rcx, rbp
0x1800887ca  call    patternCompare
0x1800887cf  xor     edx, edx
0x1800887d1  mov     rcx, rsi
0x1800887d4  test    eax, eax
0x1800887d6  setz    dl
0x1800887d9  call    sqlite3_result_int
0x1800887de  mov     rbx, [rsp+38h+arg_0]
0x1800887e3  mov     rbp, [rsp+38h+arg_8]
0x1800887e8  add     rsp, 20h
0x1800887ec  pop     r14
0x1800887ee  pop     rdi
0x1800887ef  pop     rsi
0x1800887f0  retn
```
