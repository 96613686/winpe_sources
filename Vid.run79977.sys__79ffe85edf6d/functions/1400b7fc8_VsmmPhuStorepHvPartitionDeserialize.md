# VsmmPhuStorepHvPartitionDeserialize

- ea: `0x1400b7fc8`
- end: `0x1400b829a`
- name: `VsmmPhuStorepHvPartitionDeserialize`
- size: `722`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400baf2c`

## callees

- `0x140021c60`
- `0x140021e00`
- `0x14002f724`
- `0x1400b7fc8`
- `0x1400b82a0`
- `0x1400ba804`
- `0x1400bab24`

## import_xrefs

- `winhvr!WinHvGetPartitionProperty` at `0x1400b81f4`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b81f4`

## string_xrefs

- `0x1400b806c`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b80ba`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b8108`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b8134`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b81c3`: `VsmmPhuStorepHvPartitionDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepHvPartitionDeserialize(int a1, __int64 *a2, int a3, __int64 a4, _OWORD *a5)
{
  int Structure; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  char v14; // bl
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rax
  bool v18; // sf
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v24; // [rsp+30h] [rbp-71h] BYREF
  int v25[4]; // [rsp+38h] [rbp-69h] BYREF
  int v26; // [rsp+48h] [rbp-59h] BYREF
  _OWORD v27[4]; // [rsp+50h] [rbp-51h] BYREF
  __int128 v28; // [rsp+90h] [rbp-11h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-1h]
  __int128 v30; // [rsp+B0h] [rbp+Fh]

  v24 = 0;
  v26 = 0;
  *(_OWORD *)v25 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  memset(v27, 0, sizeof(v27));
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, a3, (int)v25, 20, v25, 0);
  v10 = Structure;
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7048,
      (unsigned int)Structure);
    return v10;
  }
  v11 = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v25[1], (int)&v25[2], 48, &v28, 0);
  v10 = v11;
  if ( v11 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7061,
      (unsigned int)v11);
    return v10;
  }
  v12 = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v25[3], (int)&v26, 64, v27, 0);
  v10 = v12;
  if ( v12 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7082,
      (unsigned int)v12);
    return v10;
  }
  if ( !LOBYTE(v27[0]) )
  {
    v10 = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7089,
      3221227787LL);
    return v10;
  }
  v13 = *a2;
  v14 = 0;
  v15 = *a2 & 1;
  if ( (*a2 & 2) != 0 )
  {
    if ( v15 )
    {
      v16 = *((_QWORD *)&v27[3] + 1);
      if ( *((_QWORD *)&v27[3] + 1) )
      {
        if ( (v13 & 4) != 0 )
        {
          BYTE1(v27[0]) &= 0xFCu;
          *((_QWORD *)&v27[0] + 1) = *((_QWORD *)&v27[3] + 1);
          memset(&v27[1], 0, 48);
          LODWORD(v27[1]) = 1;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    if ( (v13 & 4) != 0 )
    {
      v16 = *((_QWORD *)&v27[0] + 1);
      v14 = 1;
      if ( v15 )
        v16 = 0;
      *((_QWORD *)&v27[0] + 1) = v16;
      goto LABEL_21;
    }
    if ( v15 )
    {
      v10 = -1073741713;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepHvPartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        7151,
        3221225583LL);
      return v10;
    }
  }
  v16 = *((_QWORD *)&v27[0] + 1);
LABEL_21:
  v17 = *((_QWORD *)&v30 + 1);
  if ( (*((_QWORD *)&v30 + 1) & 0x10000LL) == 0 )
  {
    if ( v16 )
    {
      v18 = (int)WinHvGetPartitionProperty(v16, 524289, &v24) < 0;
      v17 = *((_QWORD *)&v30 + 1);
      if ( !v18 )
        v17 = *((_QWORD *)&v30 + 1) & 0xFFFFFFFFFFFF3FFFuLL | 0x4000;
    }
  }
  *((_QWORD *)&v30 + 1) = v17 | 0x10000;
  VsmmPhuStorepSerializationChargeIncrease(a4, 144, 1);
  v19 = v29;
  *a5 = v28;
  v20 = v30;
  a5[1] = v19;
  a5[3] = v27[0];
  v21 = v27[2];
  a5[2] = v20;
  a5[4] = v27[1];
  v22 = v27[3];
  a5[5] = v21;
  a5[6] = v22;
  if ( v14 )
    VsmmPhuStorepHvPartitionFree(a4, (__int64)a5);
  return 0;
}

```

## disassembly

```asm
0x1400b7fc8  mov     [rsp-8+arg_8], rbx
0x1400b7fcd  push    rbp
0x1400b7fce  push    rsi
0x1400b7fcf  push    rdi
0x1400b7fd0  push    r14
0x1400b7fd2  push    r15
0x1400b7fd4  lea     rbp, [rsp-2Fh]
0x1400b7fd9  sub     rsp, 0D0h
0x1400b7fe0  mov     rax, cs:__security_cookie
0x1400b7fe7  xor     rax, rsp
0x1400b7fea  mov     [rbp+4Fh+var_30], rax
0x1400b7fee  mov     rdi, [rbp+4Fh+arg_20]
0x1400b7ff2  xorps   xmm1, xmm1
0x1400b7ff5  xor     eax, eax
0x1400b7ff7  mov     [rbp+4Fh+var_C0], 0
0x1400b7fff  mov     ebx, r8d
0x1400b8002  mov     [rbp+4Fh+var_A8], eax
0x1400b8005  mov     r15, rdx
0x1400b8008  mov     rsi, rcx
0x1400b800b  xorps   xmm0, xmm0
0x1400b800e  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1400b8012  lea     r8d, [rax+40h]; Size
0x1400b8016  xor     edx, edx; Val
0x1400b8018  mov     r14, r9
0x1400b801b  movups  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x1400b801f  movups  [rbp+4Fh+var_60], xmm1
0x1400b8023  movups  [rbp+4Fh+var_50], xmm1
0x1400b8027  movups  [rbp+4Fh+var_40], xmm1
0x1400b802b  call    memset
0x1400b8030  lea     rax, [rbp+4Fh+var_B8]
0x1400b8034  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b803d  mov     r9d, 14h; int
0x1400b8043  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b8048  lea     r8, [rbp+4Fh+var_B8]; int
0x1400b804c  mov     edx, ebx; int
0x1400b804e  mov     rcx, rsi; int
0x1400b8051  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b8056  mov     ebx, eax
0x1400b8058  test    eax, eax
0x1400b805a  jns     short loc_1400B807D
0x1400b805c  mov     r9d, eax
0x1400b805f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8066  mov     r8d, 1B88h
0x1400b806c  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b8073  call    VidTraceErrorStatusInternal0
0x1400b8078  jmp     loc_1400B8274
0x1400b807d  mov     edx, [rbp+4Fh+var_B8+4]; int
0x1400b8080  lea     rax, [rbp+4Fh+var_60]
0x1400b8084  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b808d  lea     r8, [rbp+4Fh+var_B8+8]; int
0x1400b8091  mov     r9d, 30h ; '0'; int
0x1400b8097  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b809c  mov     rcx, rsi; int
0x1400b809f  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b80a4  mov     ebx, eax
0x1400b80a6  test    eax, eax
0x1400b80a8  jns     short loc_1400B80CB
0x1400b80aa  mov     r9d, eax
0x1400b80ad  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b80b4  mov     r8d, 1B95h
0x1400b80ba  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b80c1  call    VidTraceErrorStatusInternal0
0x1400b80c6  jmp     loc_1400B8274
0x1400b80cb  mov     edx, [rbp+4Fh+var_B8+0Ch]; int
0x1400b80ce  lea     rax, [rbp+4Fh+var_A0]
0x1400b80d2  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b80db  lea     r8, [rbp+4Fh+var_A8]; int
0x1400b80df  mov     r9d, 40h ; '@'; int
0x1400b80e5  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b80ea  mov     rcx, rsi; int
0x1400b80ed  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b80f2  mov     ebx, eax
0x1400b80f4  test    eax, eax
0x1400b80f6  jns     short loc_1400B8119
0x1400b80f8  mov     r9d, eax
0x1400b80fb  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8102  mov     r8d, 1BAAh
0x1400b8108  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b810f  call    VidTraceErrorStatusInternal0
0x1400b8114  jmp     loc_1400B8274
0x1400b8119  cmp     byte ptr [rbp+4Fh+var_A0], 0
0x1400b811d  jnz     short loc_1400B8145
0x1400b811f  mov     ebx, 0C000090Bh
0x1400b8124  mov     r9d, ebx
0x1400b8127  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b812e  mov     r8d, 1BB1h
0x1400b8134  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b813b  call    VidTraceErrorStatusInternal0
0x1400b8140  jmp     loc_1400B8274
0x1400b8145  mov     rax, [r15]
0x1400b8148  xor     bl, bl
0x1400b814a  mov     rdx, rax
0x1400b814d  and     edx, 1
0x1400b8150  test    al, 2
0x1400b8152  jz      short loc_1400B8190
0x1400b8154  test    rdx, rdx
0x1400b8157  jz      short loc_1400B81D4
0x1400b8159  mov     rcx, qword ptr [rbp+4Fh+var_70+8]
0x1400b815d  test    rcx, rcx
0x1400b8160  jz      short loc_1400B81D4
0x1400b8162  test    al, 4
0x1400b8164  jz      short loc_1400B81D4
0x1400b8166  and     byte ptr [rbp+4Fh+var_A0+1], 0FCh
0x1400b816a  xorps   xmm0, xmm0
0x1400b816d  xor     eax, eax
0x1400b816f  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1400b8173  movups  [rbp+4Fh+var_90], xmm0
0x1400b8177  mov     qword ptr [rbp+4Fh+var_70], rax
0x1400b817b  mov     qword ptr [rbp+4Fh+var_70+8], 0
0x1400b8183  movups  [rbp+4Fh+var_80], xmm0
0x1400b8187  mov     dword ptr [rbp+4Fh+var_90], 1
0x1400b818e  jmp     short loc_1400B81D8
0x1400b8190  test    al, 4
0x1400b8192  jz      short loc_1400B81A9
0x1400b8194  mov     rcx, qword ptr [rbp+4Fh+var_A0+8]
0x1400b8198  xor     eax, eax
0x1400b819a  test    rdx, rdx
0x1400b819d  mov     bl, 1
0x1400b819f  cmovnz  rcx, rax
0x1400b81a3  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1400b81a7  jmp     short loc_1400B81D8
0x1400b81a9  test    rdx, rdx
0x1400b81ac  jz      short loc_1400B81D4
0x1400b81ae  mov     ebx, 0C000006Fh
0x1400b81b3  mov     r9d, ebx
0x1400b81b6  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b81bd  mov     r8d, 1BEFh
0x1400b81c3  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b81ca  call    VidTraceErrorStatusInternal0
0x1400b81cf  jmp     loc_1400B8274
0x1400b81d4  mov     rcx, qword ptr [rbp+4Fh+var_A0+8]
0x1400b81d8  mov     rax, qword ptr [rbp+4Fh+var_40+8]
0x1400b81dc  mov     esi, 10000h
0x1400b81e1  test    rsi, rax
0x1400b81e4  jnz     short loc_1400B8212
0x1400b81e6  test    rcx, rcx
0x1400b81e9  jz      short loc_1400B8212
0x1400b81eb  lea     r8, [rbp+4Fh+var_C0]
0x1400b81ef  mov     edx, 80001h
0x1400b81f4  call    cs:__imp_WinHvGetPartitionProperty
0x1400b81fb  nop     dword ptr [rax+rax+00h]
0x1400b8200  test    eax, eax
0x1400b8202  mov     rax, qword ptr [rbp+4Fh+var_40+8]
0x1400b8206  js      short loc_1400B8212
0x1400b8208  btr     rax, 0Fh
0x1400b820d  bts     rax, 0Eh
0x1400b8212  or      rax, rsi
0x1400b8215  mov     edx, 90h
0x1400b821a  mov     r8d, 1
0x1400b8220  mov     qword ptr [rbp+4Fh+var_40+8], rax
0x1400b8224  mov     rcx, r14
0x1400b8227  call    VsmmPhuStorepSerializationChargeIncrease
0x1400b822c  movups  xmm0, [rbp+4Fh+var_60]
0x1400b8230  movups  xmm1, [rbp+4Fh+var_50]
0x1400b8234  movups  xmmword ptr [rdi], xmm0
0x1400b8237  movups  xmm0, [rbp+4Fh+var_40]
0x1400b823b  movups  xmmword ptr [rdi+10h], xmm1
0x1400b823f  movaps  xmm1, [rbp+4Fh+var_A0]
0x1400b8243  movups  xmmword ptr [rdi+30h], xmm1
0x1400b8247  movaps  xmm1, [rbp+4Fh+var_80]
0x1400b824b  movups  xmmword ptr [rdi+20h], xmm0
0x1400b824f  movaps  xmm0, [rbp+4Fh+var_90]
0x1400b8253  movups  xmmword ptr [rdi+40h], xmm0
0x1400b8257  movaps  xmm0, [rbp+4Fh+var_70]
0x1400b825b  movups  xmmword ptr [rdi+50h], xmm1
0x1400b825f  movups  xmmword ptr [rdi+60h], xmm0
0x1400b8263  test    bl, bl
0x1400b8265  jz      short loc_1400B8272
0x1400b8267  mov     rdx, rdi
0x1400b826a  mov     rcx, r14
0x1400b826d  call    VsmmPhuStorepHvPartitionFree
0x1400b8272  xor     ebx, ebx
0x1400b8274  mov     eax, ebx
0x1400b8276  mov     rcx, [rbp+4Fh+var_30]
0x1400b827a  xor     rcx, rsp; StackCookie
0x1400b827d  call    __security_check_cookie
0x1400b8282  mov     rbx, [rsp+0F0h+arg_8]
0x1400b828a  add     rsp, 0D0h
0x1400b8291  pop     r15
0x1400b8293  pop     r14
0x1400b8295  pop     rdi
0x1400b8296  pop     rsi
0x1400b8297  pop     rbp
0x1400b8298  retn
```
