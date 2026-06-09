# LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)

- ea: `0x140003c2c`
- end: `0x140003ddd`
- name: `?LOGASSERTHR@@YAXPEBGK000J@Z`
- size: `433`
- prototype: `void __fastcall(const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `38`
- callee_count: `3`
- tags: ``

## callers

- `0x140001cb8`
- `0x140001e2c`
- `0x140002140`
- `0x140002300`
- `0x1400024d4`
- `0x140002838`
- `0x140002c94`
- `0x14000300c`
- `0x140003218`
- `0x1400036d8`
- `0x140003948`
- `0x140004288`
- `0x140004760`
- `0x140005988`
- `0x140005bc0`
- `0x1400066f4`
- `0x140006a88`
- `0x140006e24`
- `0x140007158`
- `0x1400076e0`
- `0x140007bf8`
- `0x140007d88`
- `0x140007e64`
- `0x140008090`
- `0x140008510`
- `0x140008710`
- `0x140009344`
- `0x140009470`
- `0x14000988c`
- `0x140009cb0`
- `0x140009f88`
- `0x14000a0c8`
- `0x14000a208`
- `0x14000a340`
- `0x14000a4f4`
- `0x14000a61c`
- `0x14000a8dc`
- `0x14000aaa4`

## callees

- `0x14000108c`
- `0x140003c2c`
- `0x14000ae60`

## pseudocode

```c
void __fastcall LOGASSERTHR(
        const unsigned __int16 *a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6)
{
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // r8
  int v12; // r8d
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // [rsp+30h] [rbp-69h] BYREF
  int v18; // [rsp+34h] [rbp-65h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-59h] BYREF
  const unsigned __int16 *v20; // [rsp+60h] [rbp-39h]
  int v21; // [rsp+68h] [rbp-31h]
  int v22; // [rsp+6Ch] [rbp-2Dh]
  int *v23; // [rsp+70h] [rbp-29h]
  __int64 v24; // [rsp+78h] [rbp-21h]
  const unsigned __int16 *v25; // [rsp+80h] [rbp-19h]
  int v26; // [rsp+88h] [rbp-11h]
  int v27; // [rsp+8Ch] [rbp-Dh]
  const unsigned __int16 *v28; // [rsp+90h] [rbp-9h]
  int v29; // [rsp+98h] [rbp-1h]
  int v30; // [rsp+9Ch] [rbp+3h]
  const WCHAR *v31; // [rsp+A0h] [rbp+7h]
  int v32; // [rsp+A8h] [rbp+Fh]
  int v33; // [rsp+ACh] [rbp+13h]
  int *v34; // [rsp+B0h] [rbp+17h]
  __int64 v35; // [rsp+B8h] [rbp+1Fh]
  const char *v36; // [rsp+C0h] [rbp+27h]
  __int64 v37; // [rsp+C8h] [rbp+2Fh]

  if ( (unsigned int)dword_140013000 > 5
    && (qword_140013010 & 0x400000000000LL) != 0
    && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
  {
    v8 = a5;
    v17 = a6;
    v36 = "10.0.10011.16384";
    v34 = &v17;
    v9 = -1;
    v18 = a2;
    v10 = 2;
    v37 = 17;
    v35 = 4;
    if ( a5 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a5[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v8 = &LocaleName;
      v12 = 2;
    }
    v31 = v8;
    v32 = v12;
    v33 = 0;
    if ( a4 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a4[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
      a4 = &LocaleName;
      v14 = 2;
    }
    v28 = a4;
    v29 = v14;
    v30 = 0;
    if ( a3 )
    {
      v15 = -1;
      do
        ++v15;
      while ( a3[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      a3 = &LocaleName;
      v16 = 2;
    }
    v26 = v16;
    v23 = &v18;
    v25 = a3;
    v27 = 0;
    v24 = 4;
    if ( a1 )
    {
      do
        ++v9;
      while ( a1[v9] );
      v10 = 2 * v9 + 2;
    }
    else
    {
      a1 = &LocaleName;
    }
    v21 = v10;
    v20 = a1;
    v22 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_140013000, qword_140011598, 0, 0, 9, v19, v17);
  }
}

```

## disassembly

```asm
0x140003c2c  mov     [rsp-8+arg_0], rbx
0x140003c31  push    rbp
0x140003c32  lea     rbp, [rsp-47h]
0x140003c37  sub     rsp, 0E0h
0x140003c3e  mov     rax, cs:__security_cookie
0x140003c45  xor     rax, rsp
0x140003c48  mov     [rbp+47h+var_10], rax
0x140003c4c  mov     eax, cs:dword_140013000
0x140003c52  mov     rbx, r8
0x140003c55  mov     r11, rcx
0x140003c58  cmp     eax, 5
0x140003c5b  jbe     loc_140003DC0
0x140003c61  mov     r10, cs:qword_140013018
0x140003c68  mov     rcx, 400000000000h
0x140003c72  mov     rax, cs:qword_140013010
0x140003c79  test    rcx, rax
0x140003c7c  jz      loc_140003DC0
0x140003c82  mov     rax, r10
0x140003c85  and     rax, rcx
0x140003c88  cmp     rax, r10
0x140003c8b  jnz     loc_140003DC0
0x140003c91  mov     eax, [rbp+47h+arg_28]
0x140003c94  xor     r10d, r10d
0x140003c97  mov     rcx, [rbp+47h+arg_20]
0x140003c9b  mov     [rbp+47h+var_B0], eax
0x140003c9e  lea     rax, a1001001116384; "10.0.10011.16384"
0x140003ca5  mov     [rbp+47h+var_20], rax
0x140003ca9  lea     rax, [rbp+47h+var_B0]
0x140003cad  mov     [rbp+47h+var_30], rax
0x140003cb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003cb5  mov     [rbp+47h+var_AC], edx
0x140003cb8  lea     edx, [r10+2]
0x140003cbc  mov     [rbp+47h+var_18], 11h
0x140003cc4  mov     [rbp+47h+var_28], 4
0x140003ccc  test    rcx, rcx
0x140003ccf  jz      short loc_140003CE8
0x140003cd1  mov     r8, rax
0x140003cd4  inc     r8
0x140003cd7  cmp     [rcx+r8*2], r10w
0x140003cdc  jnz     short loc_140003CD4
0x140003cde  lea     r8d, ds:2[r8*2]
0x140003ce6  jmp     short loc_140003CF2
0x140003ce8  lea     rcx, LocaleName
0x140003cef  mov     r8d, edx
0x140003cf2  mov     [rbp+47h+var_40], rcx
0x140003cf6  mov     [rbp+47h+var_38], r8d
0x140003cfa  mov     [rbp+47h+var_34], r10d
0x140003cfe  test    r9, r9
0x140003d01  jz      short loc_140003D19
0x140003d03  mov     rcx, rax
0x140003d06  inc     rcx
0x140003d09  cmp     [r9+rcx*2], r10w
0x140003d0e  jnz     short loc_140003D06
0x140003d10  lea     ecx, ds:2[rcx*2]
0x140003d17  jmp     short loc_140003D22
0x140003d19  lea     r9, LocaleName
0x140003d20  mov     ecx, edx
0x140003d22  mov     [rbp+47h+var_50], r9
0x140003d26  mov     [rbp+47h+var_48], ecx
0x140003d29  mov     [rbp+47h+var_44], r10d
0x140003d2d  test    rbx, rbx
0x140003d30  jz      short loc_140003D48
0x140003d32  mov     rcx, rax
0x140003d35  inc     rcx
0x140003d38  cmp     [rbx+rcx*2], r10w
0x140003d3d  jnz     short loc_140003D35
0x140003d3f  lea     ecx, ds:2[rcx*2]
0x140003d46  jmp     short loc_140003D51
0x140003d48  lea     rbx, LocaleName
0x140003d4f  mov     ecx, edx
0x140003d51  mov     [rbp+47h+var_58], ecx
0x140003d54  lea     rcx, [rbp+47h+var_AC]
0x140003d58  mov     [rbp+47h+var_70], rcx
0x140003d5c  mov     [rbp+47h+var_60], rbx
0x140003d60  mov     [rbp+47h+var_54], r10d
0x140003d64  mov     [rbp+47h+var_68], 4
0x140003d6c  test    r11, r11
0x140003d6f  jz      short loc_140003D84
0x140003d71  inc     rax
0x140003d74  cmp     [r11+rax*2], r10w
0x140003d79  jnz     short loc_140003D71
0x140003d7b  lea     edx, ds:2[rax*2]
0x140003d82  jmp     short loc_140003D8B
0x140003d84  lea     r11, LocaleName
0x140003d8b  lea     rax, [rbp+47h+var_A0]
0x140003d8f  mov     [rbp+47h+var_78], edx
0x140003d92  mov     [rsp+0E0h+var_B8], rax
0x140003d97  lea     rdx, qword_140011598
0x140003d9e  xor     r9d, r9d
0x140003da1  mov     [rsp+0E0h+var_C0], 9
0x140003da9  xor     r8d, r8d
0x140003dac  mov     [rbp+47h+var_80], r11
0x140003db0  lea     rcx, dword_140013000
0x140003db7  mov     [rbp+47h+var_74], r10d
0x140003dbb  call    _tlgWriteTransfer_EventWriteTransfer
0x140003dc0  mov     rcx, [rbp+47h+var_10]
0x140003dc4  xor     rcx, rsp; StackCookie
0x140003dc7  call    __security_check_cookie
0x140003dcc  mov     rbx, [rsp+0E0h+arg_0]
0x140003dd4  add     rsp, 0E0h
0x140003ddb  pop     rbp
0x140003ddc  retn
```
