# MSCryptECDHSP800135IkeKDFTest

- ea: `0x1800632e4`
- end: `0x18006342e`
- name: `MSCryptECDHSP800135IkeKDFTest`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800631b4`

## callees

- `0x18000ecb0`
- `0x180058a04`
- `0x1800631a8`
- `0x1800632e4`
- `0x18007f790`

## string_xrefs

- `0x1800633fb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\algself.c`

## pseudocode

```c
__int64 MSCryptECDHSP800135IkeKDFTest()
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // r9
  __int64 v3; // rcx
  unsigned int v5; // [rsp+50h] [rbp-29h] BYREF
  _DWORD v6[2]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v7; // [rsp+60h] [rbp-19h]
  _QWORD v8[2]; // [rsp+70h] [rbp-9h] BYREF
  int v9; // [rsp+80h] [rbp+7h]
  int v10; // [rsp+84h] [rbp+Bh]
  __int64 *v11; // [rsp+88h] [rbp+Fh]
  int v12; // [rsp+90h] [rbp+17h]
  int v13; // [rsp+94h] [rbp+1Bh]
  __int64 *v14; // [rsp+98h] [rbp+1Fh]
  int v15; // [rsp+A0h] [rbp+27h]
  int v16; // [rsp+A4h] [rbp+2Bh]
  __int64 *v17; // [rsp+A8h] [rbp+2Fh]
  __int128 Buf1; // [rsp+B0h] [rbp+37h] BYREF
  int v19; // [rsp+C0h] [rbp+47h]

  v19 = 0;
  v5 = 0;
  v9 = 16;
  v8[1] = L"SHA1";
  v12 = 16;
  v11 = g_kdfTestKey;
  v14 = g_kdfTestKey;
  v17 = g_kdfTestKey;
  v15 = 16;
  v7 = v8;
  v8[0] = 10;
  Buf1 = 0;
  v10 = 3;
  v13 = 1;
  v16 = 2;
  v6[1] = 4;
  v6[0] = 0;
  v0 = KDF_HASH(1, g_IkeAgreedSecret, 0x20u, 196610, (__int64)v6, &Buf1, 0x14u, &v5, 0);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 247;
    v3 = (unsigned int)v0;
LABEL_7:
    DebugTraceError(v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\algself.c", v2);
    return v1;
  }
  if ( v5 != 20 || memcmp_0(&Buf1, g_IkeTestResult, 0x14u) )
  {
    v1 = -1073741823;
    v2 = 256;
    v3 = 3221225473LL;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800632e4  mov     [rsp-8+arg_0], rbx
0x1800632e9  push    rbp
0x1800632ea  lea     rbp, [rsp-57h]
0x1800632ef  sub     rsp, 0D0h
0x1800632f6  mov     rax, cs:__security_cookie
0x1800632fd  xor     rax, rsp
0x180063300  mov     [rbp+57h+var_8], rax
0x180063304  xor     eax, eax
0x180063306  mov     [rsp+0D0h+var_90], 0
0x18006330e  mov     [rbp+57h+var_10], eax
0x180063311  lea     rdx, g_IkeAgreedSecret
0x180063318  mov     [rbp+57h+var_80], eax
0x18006331b  mov     ecx, 10h
0x180063320  lea     rax, aSha1; "SHA1"
0x180063327  mov     [rbp+57h+var_50], ecx
0x18006332a  mov     [rbp+57h+var_58], rax
0x18006332e  xorps   xmm0, xmm0
0x180063331  lea     rax, g_kdfTestKey
0x180063338  mov     [rbp+57h+var_40], ecx
0x18006333b  mov     [rbp+57h+var_48], rax
0x18006333f  lea     r10d, [rcx-0Fh]
0x180063343  mov     [rbp+57h+var_38], rax
0x180063347  lea     r8d, [rcx+10h]
0x18006334b  mov     [rbp+57h+var_28], rax
0x18006334f  mov     r9d, 30002h
0x180063355  lea     rax, [rbp+57h+var_60]
0x180063359  mov     [rbp+57h+var_30], ecx
0x18006335c  mov     [rbp+57h+var_70], rax
0x180063360  mov     ecx, r10d
0x180063363  lea     rax, [rbp+57h+var_80]
0x180063367  mov     [rbp+57h+var_60], 0Ah
0x18006336f  mov     [rsp+0D0h+var_98], rax
0x180063374  lea     rax, [rbp+57h+Buf1]
0x180063378  mov     [rsp+0D0h+var_A0], 14h
0x180063380  mov     [rsp+0D0h+var_A8], rax
0x180063385  lea     rax, [rbp+57h+var_78]
0x180063389  mov     [rsp+0D0h+var_B0], rax
0x18006338e  movups  [rbp+57h+Buf1], xmm0
0x180063392  mov     [rbp+57h+var_4C], 3
0x180063399  mov     [rbp+57h+var_3C], r10d
0x18006339d  mov     [rbp+57h+var_2C], 2
0x1800633a4  mov     [rbp+57h+var_74], 4
0x1800633ab  mov     [rbp+57h+var_78], 0
0x1800633b2  call    _KDF_HASH
0x1800633b7  mov     ebx, eax
0x1800633b9  test    eax, eax
0x1800633bb  jns     short loc_1800633C7
0x1800633bd  mov     r9d, 0F7h
0x1800633c3  mov     ecx, eax
0x1800633c5  jmp     short loc_1800633FB
0x1800633c7  cmp     [rbp+57h+var_80], 14h
0x1800633cb  jnz     short loc_1800633EB
0x1800633cd  mov     r8d, 14h; Size
0x1800633d3  lea     rdx, g_IkeTestResult; Buf2
0x1800633da  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800633de  call    memcmp_0
0x1800633e3  test    eax, eax
0x1800633e5  jnz     short loc_1800633EB
0x1800633e7  xor     ebx, ebx
0x1800633e9  jmp     short loc_18006340E
0x1800633eb  mov     ebx, 0C0000001h
0x1800633f0  mov     r9d, 100h
0x1800633f6  mov     ecx, 0C0000001h
0x1800633fb  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063402  lea     rdx, aStatus; "Status"
0x180063409  call    DebugTraceError
0x18006340e  mov     eax, ebx
0x180063410  mov     rcx, [rbp+57h+var_8]
0x180063414  xor     rcx, rsp; StackCookie
0x180063417  call    __security_check_cookie
0x18006341c  mov     rbx, [rsp+0D0h+arg_0]
0x180063424  add     rsp, 0D0h
0x18006342b  pop     rbp
0x18006342c  retn
```
