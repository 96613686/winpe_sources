# LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x140003ab4`
- end: `0x140003c24`
- name: `?LOGASSERT@@YAXPEBGK000@Z`
- size: `368`
- prototype: `void __fastcall(const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140002300`
- `0x140003150`
- `0x14000445c`
- `0x1400063e0`
- `0x140006544`
- `0x14000660c`
- `0x1400068bc`
- `0x1400076e0`
- `0x140007bf8`

## callees

- `0x14000108c`
- `0x140003ab4`
- `0x14000ae60`

## pseudocode

```c
void __fastcall LOGASSERT(
        const unsigned __int16 *a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // r9
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // [rsp+30h] [rbp-51h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-41h] BYREF
  const unsigned __int16 *v15; // [rsp+60h] [rbp-21h]
  int v16; // [rsp+68h] [rbp-19h]
  int v17; // [rsp+6Ch] [rbp-15h]
  int *v18; // [rsp+70h] [rbp-11h]
  __int64 v19; // [rsp+78h] [rbp-9h]
  const unsigned __int16 *v20; // [rsp+80h] [rbp-1h]
  int v21; // [rsp+88h] [rbp+7h]
  int v22; // [rsp+8Ch] [rbp+Bh]
  const wchar_t *v23; // [rsp+90h] [rbp+Fh]
  __int64 v24; // [rsp+98h] [rbp+17h]
  const WCHAR *v25; // [rsp+A0h] [rbp+1Fh]
  int v26; // [rsp+A8h] [rbp+27h]
  int v27; // [rsp+ACh] [rbp+2Bh]
  const char *v28; // [rsp+B0h] [rbp+2Fh]
  __int64 v29; // [rsp+B8h] [rbp+37h]

  if ( (unsigned int)dword_140013000 > 5
    && (qword_140013010 & 0x400000000000LL) != 0
    && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
  {
    v6 = a5;
    v28 = "10.0.10011.16384";
    v7 = -1;
    v13 = a2;
    v29 = 17;
    v8 = 2;
    if ( a5 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a5[v9] );
      v10 = 2 * v9 + 2;
    }
    else
    {
      v6 = &LocaleName;
      v10 = 2;
    }
    v25 = v6;
    v23 = L"ASSERT";
    v26 = v10;
    v27 = 0;
    v24 = 14;
    if ( a3 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a3[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      a3 = &LocaleName;
      v12 = 2;
    }
    v21 = v12;
    v18 = &v13;
    v20 = a3;
    v22 = 0;
    v19 = 4;
    if ( a1 )
    {
      do
        ++v7;
      while ( a1[v7] );
      v8 = 2 * v7 + 2;
    }
    else
    {
      a1 = &LocaleName;
    }
    v16 = v8;
    v15 = a1;
    v17 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_140013000, byte_140011549, 0, 0, 8, v14, v13);
  }
}

```

## disassembly

```asm
0x140003ab4  push    rbp
0x140003ab6  lea     rbp, [rsp-4Fh]
0x140003abb  sub     rsp, 0D0h
0x140003ac2  mov     rax, cs:__security_cookie
0x140003ac9  xor     rax, rsp
0x140003acc  mov     [rbp+4Fh+var_10], rax
0x140003ad0  mov     eax, cs:dword_140013000
0x140003ad6  mov     r10, rcx
0x140003ad9  cmp     eax, 5
0x140003adc  jbe     loc_140003C0F
0x140003ae2  mov     r9, cs:qword_140013018
0x140003ae9  mov     rcx, 400000000000h
0x140003af3  mov     rax, cs:qword_140013010
0x140003afa  test    rcx, rax
0x140003afd  jz      loc_140003C0F
0x140003b03  mov     rax, r9
0x140003b06  and     rax, rcx
0x140003b09  cmp     rax, r9
0x140003b0c  jnz     loc_140003C0F
0x140003b12  mov     rcx, [rbp+4Fh+arg_20]
0x140003b16  lea     rax, a1001001116384; "10.0.10011.16384"
0x140003b1d  xor     r11d, r11d
0x140003b20  mov     [rbp+4Fh+var_20], rax
0x140003b24  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b28  mov     [rbp+4Fh+var_A0], edx
0x140003b2b  mov     [rbp+4Fh+var_18], 11h
0x140003b33  lea     edx, [r11+2]
0x140003b37  test    rcx, rcx
0x140003b3a  jz      short loc_140003B53
0x140003b3c  mov     r9, rax
0x140003b3f  inc     r9
0x140003b42  cmp     [rcx+r9*2], r11w
0x140003b47  jnz     short loc_140003B3F
0x140003b49  lea     r9d, ds:2[r9*2]
0x140003b51  jmp     short loc_140003B5D
0x140003b53  lea     rcx, LocaleName
0x140003b5a  mov     r9d, edx
0x140003b5d  mov     [rbp+4Fh+var_30], rcx
0x140003b61  lea     rcx, aAssert; "ASSERT"
0x140003b68  mov     [rbp+4Fh+var_40], rcx
0x140003b6c  mov     [rbp+4Fh+var_28], r9d
0x140003b70  mov     [rbp+4Fh+var_24], r11d
0x140003b74  mov     [rbp+4Fh+var_38], 0Eh
0x140003b7c  test    r8, r8
0x140003b7f  jz      short loc_140003B97
0x140003b81  mov     rcx, rax
0x140003b84  inc     rcx
0x140003b87  cmp     [r8+rcx*2], r11w
0x140003b8c  jnz     short loc_140003B84
0x140003b8e  lea     ecx, ds:2[rcx*2]
0x140003b95  jmp     short loc_140003BA0
0x140003b97  lea     r8, LocaleName
0x140003b9e  mov     ecx, edx
0x140003ba0  mov     [rbp+4Fh+var_48], ecx
0x140003ba3  lea     rcx, [rbp+4Fh+var_A0]
0x140003ba7  mov     [rbp+4Fh+var_60], rcx
0x140003bab  mov     [rbp+4Fh+var_50], r8
0x140003baf  mov     [rbp+4Fh+var_44], r11d
0x140003bb3  mov     [rbp+4Fh+var_58], 4
0x140003bbb  test    r10, r10
0x140003bbe  jz      short loc_140003BD3
0x140003bc0  inc     rax
0x140003bc3  cmp     [r10+rax*2], r11w
0x140003bc8  jnz     short loc_140003BC0
0x140003bca  lea     edx, ds:2[rax*2]
0x140003bd1  jmp     short loc_140003BDA
0x140003bd3  lea     r10, LocaleName
0x140003bda  lea     rax, [rbp+4Fh+var_90]
0x140003bde  mov     [rbp+4Fh+var_68], edx
0x140003be1  mov     [rsp+0D0h+var_A8], rax
0x140003be6  lea     rdx, byte_140011549
0x140003bed  xor     r9d, r9d
0x140003bf0  mov     [rsp+0D0h+var_B0], 8
0x140003bf8  xor     r8d, r8d
0x140003bfb  mov     [rbp+4Fh+var_70], r10
0x140003bff  lea     rcx, dword_140013000
0x140003c06  mov     [rbp+4Fh+var_64], r11d
0x140003c0a  call    _tlgWriteTransfer_EventWriteTransfer
0x140003c0f  mov     rcx, [rbp+4Fh+var_10]
0x140003c13  xor     rcx, rsp; StackCookie
0x140003c16  call    __security_check_cookie
0x140003c1b  add     rsp, 0D0h
0x140003c22  pop     rbp
0x140003c23  retn
```
