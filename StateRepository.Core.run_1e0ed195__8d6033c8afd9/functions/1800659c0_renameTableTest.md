# renameTableTest

- ea: `0x1800659c0`
- end: `0x180065bed`
- name: `renameTableTest`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180014928`
- `0x180028540`
- `0x180039850`
- `0x18003f6dc`
- `0x180047fb0`
- `0x180048d20`
- `0x18005ede0`
- `0x1800659c0`
- `0x180065bf4`
- `0x180065c94`
- `0x180068880`
- `0x18006910e`
- `0x18007e074`
- `0x18007e240`

## pseudocode

```c
__int64 __fastcall renameTableTest(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r14d
  __int64 v15; // r13
  __int64 result; // rax
  int v17; // esi
  __int64 v18; // rdx
  int v19; // edi
  int v20; // r14d
  __int64 v21; // rsi
  int v22; // eax
  int v23; // r9d
  __int64 v24; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h]
  int v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  _OWORD v28[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[24]; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+C4h] [rbp-3Ch]
  __int64 v33; // [rsp+1F0h] [rbp+F0h]
  __int64 v34; // [rsp+200h] [rbp+100h]

  v5 = sqlite3_context_db_handle(a1);
  LOBYTE(v6) = 1;
  v7 = v5;
  v8 = sqlite3ValueText(*a3, v6);
  LOBYTE(v9) = 1;
  v10 = v8;
  v24 = v8;
  v11 = sqlite3ValueText(a3[1], v9);
  v12 = sqlite3_value_int64(a3[4]);
  LOBYTE(v13) = 1;
  v14 = *(_DWORD *)(v7 + 48);
  v26 = v12;
  v15 = sqlite3ValueText(a3[5], v13);
  v25 = sqlite3_value_int64(a3[6]);
  result = *(_QWORD *)(v7 + 512);
  v27 = result;
  *(_QWORD *)(v7 + 512) = 0;
  if ( v10 && v11 )
  {
    memset_0(v30, 0, 0x1A8u);
    v17 = *(_DWORD *)(v7 + 48);
    if ( v25 )
      *(_QWORD *)(v7 + 48) &= 0xFFFFFFFF9FFFFFFFuLL;
    v19 = renameParseSql((__int64)v30, v24, v7, v11, v26);
    *(_QWORD *)(v7 + 48) |= v17 & 0x60000000;
    if ( v19 )
      goto LABEL_18;
    v20 = v14 & 0x4000000;
    if ( !v20 && (v18 = v33) != 0 && *(_BYTE *)(v33 + 63) == 2 )
    {
      v29 = 0;
      v28[0] = (unsigned __int64)v30;
      memset(&v28[1], 0, 32);
      sqlite3SelectPrep(v30, *(_QWORD *)(v33 + 64), v28);
      if ( !v32 )
        goto LABEL_21;
      v19 = v31;
    }
    else
    {
      v21 = v34;
      if ( !v34 )
        goto LABEL_21;
      if ( !v20 )
      {
        v19 = renameResolveTrigger((unsigned __int64)v30);
        if ( v19 )
        {
LABEL_18:
          if ( v15 && (*(_DWORD *)(v7 + 48) & 0x10000001) != 1 )
            renameColumnParseError(a1, v15, a3[2], a3[3], (__int64)v30);
          goto LABEL_21;
        }
        v21 = v34;
      }
      sqlite3FindDbName(v7, v24);
      v22 = sqlite3SchemaToIndex(v7, *(_QWORD *)(v21 + 48));
      if ( v22 != v23 )
      {
LABEL_21:
        renameParseCleanup(v30, v18);
        result = v27;
        goto LABEL_22;
      }
      sqlite3_result_int(a1, 1);
    }
    if ( v19 )
      goto LABEL_18;
    goto LABEL_21;
  }
LABEL_22:
  *(_QWORD *)(v7 + 512) = result;
  return result;
}

```

## disassembly

```asm
0x1800659c0  mov     [rsp-8+arg_8], rbx
0x1800659c5  push    rbp
0x1800659c6  push    rsi
0x1800659c7  push    rdi
0x1800659c8  push    r12
0x1800659ca  push    r13
0x1800659cc  push    r14
0x1800659ce  push    r15
0x1800659d0  lea     rbp, [rsp-150h]
0x1800659d8  sub     rsp, 250h
0x1800659df  mov     rax, cs:__security_cookie
0x1800659e6  xor     rax, rsp
0x1800659e9  mov     [rbp+180h+var_40], rax
0x1800659f0  mov     r15, r8
0x1800659f3  mov     r12, rcx
0x1800659f6  call    sqlite3_context_db_handle
0x1800659fb  mov     rcx, [r15]
0x1800659fe  mov     dl, 1
0x180065a00  mov     rbx, rax
0x180065a03  call    sqlite3ValueText
0x180065a08  mov     rcx, [r15+8]
0x180065a0c  mov     dl, 1
0x180065a0e  mov     rsi, rax
0x180065a11  mov     [rsp+280h+var_250], rax
0x180065a16  call    sqlite3ValueText
0x180065a1b  mov     rcx, [r15+20h]
0x180065a1f  mov     rdi, rax
0x180065a22  call    sqlite3_value_int64
0x180065a27  mov     rcx, [r15+28h]
0x180065a2b  mov     dl, 1
0x180065a2d  mov     r14d, [rbx+30h]
0x180065a31  mov     [rsp+280h+var_240], rax
0x180065a36  call    sqlite3ValueText
0x180065a3b  mov     rcx, [r15+30h]
0x180065a3f  mov     r13, rax
0x180065a42  call    sqlite3_value_int64
0x180065a47  mov     [rsp+280h+var_248], rax
0x180065a4c  mov     rax, [rbx+200h]
0x180065a53  mov     [rsp+280h+var_238], rax
0x180065a58  mov     qword ptr [rbx+200h], 0
0x180065a63  test    rsi, rsi
0x180065a66  jz      loc_180065BBC
0x180065a6c  test    rdi, rdi
0x180065a6f  jz      loc_180065BBC
0x180065a75  xor     edx, edx; Val
0x180065a77  lea     rcx, [rbp+180h+var_1F0]; void *
0x180065a7b  mov     r8d, 1A8h; Size
0x180065a81  call    memset_0
0x180065a86  cmp     dword ptr [rsp+280h+var_248], 0
0x180065a8b  mov     esi, [rbx+30h]
0x180065a8e  jz      short loc_180065A98
0x180065a90  and     qword ptr [rbx+30h], 0FFFFFFFF9FFFFFFFh
0x180065a98  mov     rax, [rsp+280h+var_240]
0x180065a9d  lea     rcx, [rbp+180h+var_1F0]
0x180065aa1  mov     rdx, [rsp+280h+var_250]
0x180065aa6  mov     r9, rdi
0x180065aa9  mov     r8, rbx
0x180065aac  mov     dword ptr [rsp+280h+var_260], eax
0x180065ab0  call    renameParseSql
0x180065ab5  and     esi, 60000000h
0x180065abb  mov     edi, eax
0x180065abd  or      [rbx+30h], rsi
0x180065ac1  test    eax, eax
0x180065ac3  jnz     loc_180065B7F
0x180065ac9  and     r14d, 4000000h
0x180065ad0  jnz     short loc_180065B26
0x180065ad2  mov     rdx, [rbp+180h+var_90]
0x180065ad9  test    rdx, rdx
0x180065adc  jz      short loc_180065B26
0x180065ade  cmp     byte ptr [rdx+3Fh], 2
0x180065ae2  jnz     short loc_180065B26
0x180065ae4  xorps   xmm0, xmm0
0x180065ae7  lea     r8, [rsp+280h+var_230]
0x180065aec  xor     eax, eax
0x180065aee  lea     rcx, [rbp+180h+var_1F0]
0x180065af2  mov     [rbp+180h+var_200], rax
0x180065af6  lea     rax, [rbp+180h+var_1F0]
0x180065afa  movups  [rsp+280h+var_230], xmm0
0x180065aff  mov     qword ptr [rsp+280h+var_230], rax
0x180065b04  movups  [rsp+280h+var_220], xmm0
0x180065b09  movups  [rsp+280h+var_210], xmm0
0x180065b0e  mov     rdx, [rdx+40h]
0x180065b12  call    sqlite3SelectPrep
0x180065b17  cmp     [rbp+180h+var_1BC], r14d
0x180065b1b  jz      loc_180065BAE
0x180065b21  mov     edi, [rbp+180h+var_1D8]
0x180065b24  jmp     short loc_180065B7B
0x180065b26  mov     rsi, [rbp+180h+var_80]
0x180065b2d  test    rsi, rsi
0x180065b30  jz      short loc_180065BAE
0x180065b32  test    r14d, r14d
0x180065b35  jnz     short loc_180065B4D
0x180065b37  lea     rcx, [rbp+180h+var_1F0]
0x180065b3b  call    renameResolveTrigger
0x180065b40  mov     edi, eax
0x180065b42  test    eax, eax
0x180065b44  jnz     short loc_180065B7F
0x180065b46  mov     rsi, [rbp+180h+var_80]
0x180065b4d  mov     rdx, [rsp+280h+var_250]
0x180065b52  mov     rcx, rbx
0x180065b55  call    sqlite3FindDbName
0x180065b5a  mov     rdx, [rsi+30h]
0x180065b5e  mov     rcx, rbx
0x180065b61  mov     r9d, eax
0x180065b64  call    sqlite3SchemaToIndex
0x180065b69  cmp     eax, r9d
0x180065b6c  jnz     short loc_180065BAE
0x180065b6e  mov     edx, 1
0x180065b73  mov     rcx, r12
0x180065b76  call    sqlite3_result_int
0x180065b7b  test    edi, edi
0x180065b7d  jz      short loc_180065BAE
0x180065b7f  test    r13, r13
0x180065b82  jz      short loc_180065BAE
0x180065b84  mov     eax, [rbx+30h]
0x180065b87  and     eax, 10000001h
0x180065b8c  cmp     rax, 1
0x180065b90  jz      short loc_180065BAE
0x180065b92  mov     r9, [r15+18h]
0x180065b96  lea     rax, [rbp+180h+var_1F0]
0x180065b9a  mov     r8, [r15+10h]
0x180065b9e  mov     rdx, r13
0x180065ba1  mov     rcx, r12
0x180065ba4  mov     [rsp+280h+var_260], rax
0x180065ba9  call    renameColumnParseError
0x180065bae  lea     rcx, [rbp+180h+var_1F0]
0x180065bb2  call    renameParseCleanup
0x180065bb7  mov     rax, [rsp+280h+var_238]
0x180065bbc  mov     [rbx+200h], rax
0x180065bc3  mov     rcx, [rbp+180h+var_40]
0x180065bca  xor     rcx, rsp; StackCookie
0x180065bcd  call    __security_check_cookie
0x180065bd2  mov     rbx, [rsp+280h+arg_8]
0x180065bda  add     rsp, 250h
0x180065be1  pop     r15
0x180065be3  pop     r14
0x180065be5  pop     r13
0x180065be7  pop     r12
0x180065be9  pop     rdi
0x180065bea  pop     rsi
0x180065beb  pop     rbp
0x180065bec  retn
```
