# av_aes_init

- ea: `0x180029f30`
- end: `0x18002a1e4`
- name: `av_aes_init`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a610`

## callees

- `0x180029da0`
- `0x180029f30`
- `0x18002a280`
- `0x18002a368`
- `0x180077a60`
- `0x180078e90`
- `0x18007a960`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029fb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029fb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029fd5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029fd5`

## pseudocode

```c
__int64 __fastcall av_aes_init(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  __int128 *v4; // rbx
  __int64 (__fastcall *v5)(int, int, int, int, __int64, int); // rax
  int v6; // r13d
  int v9; // r14d
  int v10; // edi
  __int64 v11; // r8
  int v12; // r15d
  __int64 v13; // r14
  __int64 v14; // r9
  __int64 *v15; // rsi
  int v16; // edx
  __int64 i; // rcx
  int v18; // r9d
  char *v19; // rdx
  __int64 v20; // r10
  char *v21; // rcx
  __int64 v22; // r8
  char *v23; // rcx
  __int64 v24; // r8
  __int128 *v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rdx
  __int128 *v28; // rcx
  __int128 v29; // xmm1
  BOOL fPending[2]; // [rsp+20h] [rbp-59h] BYREF
  int v32; // [rsp+28h] [rbp-51h]
  unsigned int v33; // [rsp+2Ch] [rbp-4Dh]
  __int128 v34; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v35[16]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v36; // [rsp+50h] [rbp-29h]
  _BYTE v37[4]; // [rsp+60h] [rbp-19h] BYREF
  char v38; // [rsp+64h] [rbp-15h] BYREF

  v4 = (__int128 *)a1;
  v33 = a4;
  v5 = sub_180029CB0;
  v6 = a3 >> 5;
  v9 = (a3 >> 5) + 6;
  *(_DWORD *)(a1 + 272) = v9;
  if ( a4 )
    v5 = sub_180029BC0;
  v32 = v6 + 6;
  *(_QWORD *)(a1 + 280) = v5;
  sub_180077A60(a1, a4);
  fPending[0] = 0;
  InitOnceBeginInitialize(&InitOnce, 0, fPending, 0);
  if ( fPending[0] )
    sub_180029DA0();
  InitOnceComplete(&InitOnce, 0, 0);
  if ( ((a3 - 128) & 0xFFFFFF3F) != 0 || a3 == 320 )
    return 4294967274LL;
  v10 = 4 * v6;
  *(_QWORD *)fPending = 4 * v6;
  sub_18007A960(v37, a2, *(_QWORD *)fPending);
  sub_18007A960(v4, a2, 4 * v6);
  v11 = v6;
  v12 = 16 * (v9 + 1);
  if ( 4 * v6 < v12 )
  {
    _mm_lfence();
    v13 = *(_QWORD *)fPending;
    v14 = 4 * (v6 - 1LL);
    v15 = &qword_18007DB20;
    do
    {
      v16 = 0;
      for ( i = 0; i < 4; ++i )
        v37[i] ^= *((_BYTE *)qword_1800A9170 + (unsigned __int8)v37[v14 + (++v16 & 3)]);
      v18 = 1;
      v37[0] ^= *(_BYTE *)v15;
      v15 = (__int64 *)((char *)v15 + 1);
      if ( v11 > 1 )
      {
        v19 = &v38;
        v20 = v6 - 1LL;
        do
        {
          if ( v6 == 8 && v18 == 4 )
          {
            v21 = v19;
            v22 = 4;
            do
            {
              *v21 ^= *((_BYTE *)qword_1800A9170 + (unsigned __int8)*(v21 - 4));
              ++v21;
              --v22;
            }
            while ( v22 );
          }
          else
          {
            v23 = v19;
            v24 = 4;
            do
            {
              *v23 ^= *(v23 - 4);
              ++v23;
              --v24;
            }
            while ( v24 );
          }
          ++v18;
          v19 += 4;
          --v20;
        }
        while ( v20 );
      }
      sub_18007A960((char *)v4 + v10, v37, v13);
      v11 = v6;
      v10 += 4 * v6;
      v14 = 4 * (v6 - 1LL);
    }
    while ( v10 < v12 );
    v9 = v32;
  }
  if ( v33 )
  {
    if ( v9 > 1LL )
    {
      v25 = v4 + 1;
      v26 = v9 - 1LL;
      do
      {
        v36 = *v25;
        sub_18002A368(v35, 0, qword_1800A9170);
        sub_18002A280(&v34, qword_1800A9770, 1);
        *v25++ = v34;
        --v26;
      }
      while ( v26 );
    }
  }
  else
  {
    v27 = (__int64)(v9 + 1) >> 1;
    if ( v27 > 0 )
    {
      v28 = &v4[v9];
      do
      {
        v29 = *v28;
        *v28-- = *v4;
        *v4++ = v29;
        --v27;
      }
      while ( v27 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029f30  push    rbp
0x180029f32  push    rbx
0x180029f33  push    rsi
0x180029f34  push    rdi
0x180029f35  push    r12
0x180029f37  push    r13
0x180029f39  push    r14
0x180029f3b  push    r15
0x180029f3d  lea     rbp, [rsp-1Fh]
0x180029f42  sub     rsp, 98h
0x180029f49  mov     rax, cs:__security_cookie
0x180029f50  xor     rax, rsp
0x180029f53  mov     [rbp+57h+var_50], rax
0x180029f57  mov     rbx, rcx
0x180029f5a  mov     [rbp+57h+var_A4], r9d
0x180029f5e  mov     r13d, r8d
0x180029f61  lea     rax, sub_180029CB0
0x180029f68  sar     r13d, 5
0x180029f6c  mov     rsi, rdx
0x180029f6f  test    r9d, r9d
0x180029f72  mov     edx, r9d
0x180029f75  mov     edi, r8d
0x180029f78  lea     r14d, [r13+6]
0x180029f7c  mov     [rcx+110h], r14d
0x180029f83  lea     rcx, sub_180029BC0
0x180029f8a  cmovnz  rax, rcx
0x180029f8e  mov     [rbp+57h+var_A8], r14d
0x180029f92  mov     rcx, rbx
0x180029f95  mov     [rbx+118h], rax
0x180029f9c  call    sub_180077A60
0x180029fa1  xor     r9d, r9d; lpContext
0x180029fa4  mov     [rbp+57h+fPending], 0
0x180029fab  lea     r8, [rbp+57h+fPending]; fPending
0x180029faf  xor     edx, edx; dwFlags
0x180029fb1  lea     rcx, InitOnce; lpInitOnce
0x180029fb8  call    cs:InitOnceBeginInitialize
0x180029fbe  cmp     [rbp+57h+fPending], 0
0x180029fc2  jz      short loc_180029FC9
0x180029fc4  call    sub_180029DA0
0x180029fc9  xor     r8d, r8d; lpContext
0x180029fcc  lea     rcx, InitOnce; lpInitOnce
0x180029fd3  xor     edx, edx; dwFlags
0x180029fd5  call    cs:InitOnceComplete
0x180029fdb  lea     eax, [rdi-80h]
0x180029fde  test    eax, 0FFFFFF3Fh
0x180029fe3  jnz     loc_18002A1BF
0x180029fe9  cmp     edi, 140h
0x180029fef  jz      loc_18002A1BF
0x180029ff5  lea     edi, ds:0[r13*4]
0x180029ffd  mov     rdx, rsi
0x18002a000  movsxd  r15, edi
0x18002a003  lea     rcx, [rbp+57h+var_70]
0x18002a007  mov     r8, r15
0x18002a00a  mov     qword ptr [rbp+57h+fPending], r15
0x18002a00e  call    sub_18007A960
0x18002a013  mov     r8, r15
0x18002a016  mov     rdx, rsi
0x18002a019  mov     rcx, rbx
0x18002a01c  call    sub_18007A960
0x18002a021  lea     r15d, [r14+1]
0x18002a025  movsxd  r8, r13d
0x18002a028  shl     r15d, 4
0x18002a02c  lea     r11, qword_1800A9170
0x18002a033  cmp     edi, r15d
0x18002a036  jge     loc_18002A123
0x18002a03c  lfence
0x18002a03f  mov     r14, qword ptr [rbp+57h+fPending]
0x18002a043  lea     r12, [r8-1]
0x18002a047  lea     r9, ds:0[r12*4]
0x18002a04f  lea     rsi, qword_18007DB20
0x18002a056  xor     edx, edx
0x18002a058  xor     ecx, ecx
0x18002a05a  lea     rax, [rdx+1]
0x18002a05e  inc     edx
0x18002a060  and     eax, 3
0x18002a063  add     rax, r9
0x18002a066  movzx   eax, [rbp+rax+57h+var_70]
0x18002a06b  mov     al, [rax+r11]
0x18002a06f  xor     [rbp+rcx+57h+var_70], al
0x18002a073  inc     rcx
0x18002a076  cmp     rcx, 4
0x18002a07a  jl      short loc_18002A05A
0x18002a07c  mov     al, [rsi]
0x18002a07e  mov     r9d, 1
0x18002a084  xor     [rbp+57h+var_70], al
0x18002a087  inc     rsi
0x18002a08a  cmp     r8, r9
0x18002a08d  jle     short loc_18002A0E1
0x18002a08f  lea     rdx, [rbp+57h+var_6C]
0x18002a093  mov     r10, r12
0x18002a096  cmp     r13d, 8
0x18002a09a  jnz     short loc_18002A0BD
0x18002a09c  cmp     r9d, 4
0x18002a0a0  jnz     short loc_18002A0BD
0x18002a0a2  mov     rcx, rdx
0x18002a0a5  mov     r8d, r9d
0x18002a0a8  movzx   eax, byte ptr [rcx-4]
0x18002a0ac  mov     al, [rax+r11]
0x18002a0b0  xor     [rcx], al
0x18002a0b2  inc     rcx
0x18002a0b5  sub     r8, 1
0x18002a0b9  jnz     short loc_18002A0A8
0x18002a0bb  jmp     short loc_18002A0D4
0x18002a0bd  mov     rcx, rdx
0x18002a0c0  mov     r8d, 4
0x18002a0c6  mov     al, [rcx-4]
0x18002a0c9  xor     [rcx], al
0x18002a0cb  inc     rcx
0x18002a0ce  sub     r8, 1
0x18002a0d2  jnz     short loc_18002A0C6
0x18002a0d4  inc     r9d
0x18002a0d7  add     rdx, 4
0x18002a0db  sub     r10, 1
0x18002a0df  jnz     short loc_18002A096
0x18002a0e1  movsxd  rcx, edi
0x18002a0e4  lea     rdx, [rbp+57h+var_70]
0x18002a0e8  add     rcx, rbx
0x18002a0eb  mov     r8, r14
0x18002a0ee  call    sub_18007A960
0x18002a0f3  lea     eax, ds:0[r13*4]
0x18002a0fb  movsxd  r8, r13d
0x18002a0fe  add     edi, eax
0x18002a100  lea     r9, ds:0[r12*4]
0x18002a108  lea     r11, qword_1800A9170
0x18002a10f  cmp     edi, r15d
0x18002a112  jl      loc_18002A056
0x18002a118  mov     r14d, [rbp+57h+var_A8]
0x18002a11c  lea     r11, qword_1800A9170
0x18002a123  cmp     [rbp+57h+var_A4], 0
0x18002a127  movsxd  rcx, r14d
0x18002a12a  jz      short loc_18002A189
0x18002a12c  cmp     rcx, 1
0x18002a130  jle     loc_18002A1BB
0x18002a136  add     rbx, 10h
0x18002a13a  lea     rdi, [rcx-1]
0x18002a13e  movups  xmm0, xmmword ptr [rbx]
0x18002a141  mov     r8, r11
0x18002a144  lea     rcx, [rbp+57h+var_90]
0x18002a148  xor     edx, edx
0x18002a14a  movdqu  [rbp+57h+var_80], xmm0
0x18002a14f  call    sub_18002A368
0x18002a154  mov     r9d, 3
0x18002a15a  lea     rdx, qword_1800A9770
0x18002a161  lea     rcx, [rbp+57h+var_A0]
0x18002a165  lea     r8d, [r9-2]
0x18002a169  call    sub_18002A280
0x18002a16e  lea     r11, qword_1800A9170
0x18002a175  movups  xmm0, [rbp+57h+var_A0]
0x18002a179  movdqu  xmmword ptr [rbx], xmm0
0x18002a17d  lea     rbx, [rbx+10h]
0x18002a181  sub     rdi, 1
0x18002a185  jnz     short loc_18002A13E
0x18002a187  jmp     short loc_18002A1BB
0x18002a189  lea     eax, [r14+1]
0x18002a18d  movsxd  rdx, eax
0x18002a190  sar     rdx, 1
0x18002a193  test    rdx, rdx
0x18002a196  jle     short loc_18002A1BB
0x18002a198  shl     rcx, 4
0x18002a19c  add     rcx, rbx
0x18002a19f  movups  xmm0, xmmword ptr [rbx]
0x18002a1a2  movups  xmm1, xmmword ptr [rcx]
0x18002a1a5  movdqu  xmmword ptr [rcx], xmm0
0x18002a1a9  lea     rcx, [rcx-10h]
0x18002a1ad  movdqu  xmmword ptr [rbx], xmm1
0x18002a1b1  lea     rbx, [rbx+10h]
0x18002a1b5  sub     rdx, 1
0x18002a1b9  jnz     short loc_18002A19F
0x18002a1bb  xor     eax, eax
0x18002a1bd  jmp     short loc_18002A1C4
0x18002a1bf  mov     eax, 0FFFFFFEAh
0x18002a1c4  mov     rcx, [rbp+57h+var_50]
0x18002a1c8  xor     rcx, rsp; StackCookie
0x18002a1cb  call    __security_check_cookie
0x18002a1d0  add     rsp, 98h
0x18002a1d7  pop     r15
0x18002a1d9  pop     r14
0x18002a1db  pop     r13
0x18002a1dd  pop     r12
0x18002a1df  pop     rdi
0x18002a1e0  pop     rsi
0x18002a1e1  pop     rbx
0x18002a1e2  pop     rbp
0x18002a1e3  retn
```
