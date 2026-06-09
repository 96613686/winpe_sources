# Em_AmrNB_Dec_LspToLpc

- ea: `0x180007eb4`
- end: `0x18000803f`
- name: `Em_AmrNB_Dec_LspToLpc`
- size: `395`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800051e0`
- `0x180008078`
- `0x180008e48`

## callees

- `0x180001400`
- `0x180007d60`
- `0x180007eb4`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_LspToLpc(_WORD *a1)
{
  int v2; // esi
  __int64 v3; // r10
  int v4; // r8d
  __int64 v5; // rdi
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // ecx
  bool v10; // sf
  int v11; // r8d
  int v12; // r9d
  __int16 v13; // ax
  int v14; // r8d
  int v15; // eax
  __int16 v16; // cx
  __int64 v17; // rax
  _DWORD v19[6]; // [rsp+28h] [rbp-50h] BYREF
  _DWORD v20[6]; // [rsp+40h] [rbp-38h] BYREF

  Em_AmrNB_Dec_GetLspPolynomial(a1 + 1, v20);
  Em_AmrNB_Dec_GetLspPolynomial(a1 + 2, v19);
  v2 = 6;
  *a1 = 4096;
  v3 = 5;
  do
  {
    v4 = v20[v3];
    v5 = v3 - 1;
    v6 = v20[v3 - 1];
    v7 = v4 + v6;
    if ( (v6 ^ v4) >= 0 && (v7 ^ v4) < 0 )
    {
      v7 = 0x7FFFFFFF;
      if ( v4 < 0 )
        v7 = 0x80000000;
    }
    v8 = v19[v3];
    v9 = v8 - v19[v5];
    v10 = (v19[v5] ^ v8) < 0;
    v20[v3] = v7;
    if ( v10 && ((v9 ^ v8) & 0x80000000) != 0 )
    {
      v9 = 0x7FFFFFFF;
      if ( v8 < 0 )
        v9 = 0x80000000;
    }
    v19[v3] = v9;
    v11 = v9 + v7;
    if ( ((v7 ^ v9) & 0x80000000) != 0 || (v7 ^ v11) >= 0 )
    {
      v12 = v11 >> 13;
    }
    else if ( v7 >= 0 )
    {
      LOWORD(v11) = -1;
      LOWORD(v12) = -1;
    }
    else
    {
      LOWORD(v11) = 0;
      LOWORD(v12) = 0;
    }
    v13 = v12 + 1;
    if ( (v11 & 0x1000) == 0 )
      v13 = v12;
    v14 = v7 - v9;
    a1[v3] = v13;
    if ( ((v7 ^ v9) & 0x80000000) == 0 || (v7 ^ v14) >= 0 )
    {
      v15 = v14 >> 13;
    }
    else if ( v7 >= 0 )
    {
      LOWORD(v15) = -1;
      LOWORD(v14) = -1;
    }
    else
    {
      LOWORD(v14) = 0;
      LOWORD(v15) = 0;
    }
    --v3;
    v16 = v15 + 1;
    if ( (v14 & 0x1000) == 0 )
      v16 = v15;
    v17 = v2++;
    a1[v17] = v16;
  }
  while ( v5 );
  return 0;
}

```

## disassembly

```asm
0x180007eb4  mov     [rsp+arg_8], rbx
0x180007eb9  mov     [rsp+arg_10], rsi
0x180007ebe  push    rdi
0x180007ebf  push    r13
0x180007ec1  push    r14
0x180007ec3  sub     rsp, 60h
0x180007ec7  mov     rax, cs:__security_cookie
0x180007ece  xor     rax, rsp
0x180007ed1  mov     [rsp+78h+var_20], rax
0x180007ed6  mov     rbx, rcx
0x180007ed9  lea     rdx, [rsp+78h+var_38]
0x180007ede  add     rcx, 2
0x180007ee2  call    Em_AmrNB_Dec_GetLspPolynomial
0x180007ee7  lea     rcx, [rbx+4]
0x180007eeb  lea     rdx, [rsp+78h+var_50]
0x180007ef0  call    Em_AmrNB_Dec_GetLspPolynomial
0x180007ef5  mov     esi, 6
0x180007efa  mov     [rsp+78h+var_58], 1
0x180007f02  mov     r13d, 1000h
0x180007f08  mov     r14d, 80000000h
0x180007f0e  mov     [rbx], r13w
0x180007f12  lea     r10d, [rsi-1]
0x180007f16  mov     r8d, [rsp+r10*4+78h+var_38]
0x180007f1b  lea     rdi, [r10-1]
0x180007f1f  mov     ecx, [rsp+rdi*4+78h+var_38]
0x180007f23  mov     eax, r8d
0x180007f26  xor     eax, ecx
0x180007f28  lea     edx, [r8+rcx]
0x180007f2c  jl      short loc_180007F41
0x180007f2e  mov     eax, r8d
0x180007f31  xor     eax, edx
0x180007f33  jge     short loc_180007F41
0x180007f35  test    r8d, r8d
0x180007f38  mov     edx, 7FFFFFFFh
0x180007f3d  cmovs   edx, r14d
0x180007f41  mov     r8d, [rsp+r10*4+78h+var_50]
0x180007f46  mov     ecx, r8d
0x180007f49  sub     ecx, [rsp+rdi*4+78h+var_50]
0x180007f4d  mov     eax, r8d
0x180007f50  xor     eax, [rsp+rdi*4+78h+var_50]
0x180007f54  mov     [rsp+r10*4+78h+var_38], edx
0x180007f59  jge     short loc_180007F6E
0x180007f5b  mov     eax, r8d
0x180007f5e  xor     eax, ecx
0x180007f60  jge     short loc_180007F6E
0x180007f62  test    r8d, r8d
0x180007f65  mov     ecx, 7FFFFFFFh
0x180007f6a  cmovs   ecx, r14d
0x180007f6e  mov     r11d, ecx
0x180007f71  mov     [rsp+r10*4+78h+var_50], ecx
0x180007f76  xor     r11d, edx
0x180007f79  lea     r8d, [rcx+rdx]
0x180007f7d  jl      short loc_180007FA3
0x180007f7f  mov     eax, r8d
0x180007f82  xor     eax, edx
0x180007f84  jge     short loc_180007FA3
0x180007f86  test    edx, edx
0x180007f88  jns     short loc_180007F95
0x180007f8a  mov     r8d, r14d
0x180007f8d  mov     r9d, 0FFFC0000h
0x180007f93  jmp     short loc_180007FAA
0x180007f95  mov     r8d, 7FFFFFFFh
0x180007f9b  mov     r9d, 3FFFFh
0x180007fa1  jmp     short loc_180007FAA
0x180007fa3  mov     r9d, r8d
0x180007fa6  sar     r9d, 0Dh
0x180007faa  movzx   eax, r9w
0x180007fae  add     ax, word ptr [rsp+78h+var_58]
0x180007fb3  test    r13d, r8d
0x180007fb6  mov     r8d, edx
0x180007fb9  cmovz   ax, r9w
0x180007fbe  sub     r8d, ecx
0x180007fc1  mov     [rbx+r10*2], ax
0x180007fc6  test    r11d, r11d
0x180007fc9  jns     short loc_180007FED
0x180007fcb  mov     eax, r8d
0x180007fce  xor     eax, edx
0x180007fd0  jge     short loc_180007FED
0x180007fd2  test    edx, edx
0x180007fd4  jns     short loc_180007FE0
0x180007fd6  mov     r8d, r14d
0x180007fd9  mov     eax, 0FFFC0000h
0x180007fde  jmp     short loc_180007FF3
0x180007fe0  mov     eax, 3FFFFh
0x180007fe5  mov     r8d, 7FFFFFFFh
0x180007feb  jmp     short loc_180007FF3
0x180007fed  mov     eax, r8d
0x180007ff0  sar     eax, 0Dh
0x180007ff3  mov     r9d, 1
0x180007ff9  test    r13d, r8d
0x180007ffc  mov     r10, rdi
0x180007fff  lea     ecx, [r9+rax]
0x180008003  cmovz   cx, ax
0x180008007  movsxd  rax, esi
0x18000800a  add     esi, r9d
0x18000800d  mov     [rbx+rax*2], cx
0x180008011  test    rdi, rdi
0x180008014  jnz     loc_180007F16
0x18000801a  xor     eax, eax
0x18000801c  mov     rcx, [rsp+78h+var_20]
0x180008021  xor     rcx, rsp; StackCookie
0x180008024  call    __security_check_cookie
0x180008029  lea     r11, [rsp+78h+var_18]
0x18000802e  mov     rbx, [r11+28h]
0x180008032  mov     rsi, [r11+30h]
0x180008036  mov     rsp, r11
0x180008039  pop     r14
0x18000803b  pop     r13
0x18000803d  pop     rdi
0x18000803e  retn
```
