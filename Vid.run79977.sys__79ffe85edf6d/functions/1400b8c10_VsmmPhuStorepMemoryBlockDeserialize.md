# VsmmPhuStorepMemoryBlockDeserialize

- ea: `0x1400b8c10`
- end: `0x1400b92db`
- name: `VsmmPhuStorepMemoryBlockDeserialize`
- size: `1739`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400b9670`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021e00`
- `0x14002f724`
- `0x1400b462c`
- `0x1400b8c10`
- `0x1400b92e4`
- `0x1400bab24`
- `0x1400e8ed4`
- `0x1400f4f7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b91b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b91b8`

## string_xrefs

- `0x1400b8cbb`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b8d05`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b8d4f`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b8d82`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b8df4`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b8f15`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b9033`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b90ea`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b9211`: `VsmmPhuStorepMemoryBlockDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepMemoryBlockDeserialize(int a1, __int64 *a2, int a3, __int64 a4, __int64 a5)
{
  int Structure; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  __int16 v13; // r15d^2
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // r11
  char v18; // r14
  char v19; // r12
  char v20; // bl
  __int128 v21; // xmm3
  __int128 v22; // xmm2
  __int128 v23; // xmm6
  int v24; // r9d
  __int128 v25; // xmm4
  __int128 v26; // xmm5
  __int64 v27; // rax
  int v28; // r8d
  void *v29; // rdx
  int v30; // r9d
  __int128 v31; // xmm1
  __int64 v32; // rbx
  __int64 v33; // rsi
  int v34; // edx
  int v36; // [rsp+38h] [rbp-D0h] BYREF
  int v37; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v41[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v42; // [rsp+98h] [rbp-70h]
  __int128 v43; // [rsp+A8h] [rbp-60h]
  _OWORD v44[6]; // [rsp+B8h] [rbp-50h] BYREF
  int v45[4]; // [rsp+118h] [rbp+10h] BYREF
  int v46; // [rsp+128h] [rbp+20h] BYREF
  __int128 v47; // [rsp+130h] [rbp+28h] BYREF
  __int128 v48; // [rsp+140h] [rbp+38h]
  _BYTE v49[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v50[16]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v51[16]; // [rsp+188h] [rbp+80h] BYREF
  int *v52; // [rsp+198h] [rbp+90h]
  __int64 v53; // [rsp+1A0h] [rbp+98h]
  int *v54; // [rsp+1A8h] [rbp+A0h]
  __int64 v55; // [rsp+1B0h] [rbp+A8h]
  __int64 *v56; // [rsp+1B8h] [rbp+B0h]
  __int64 v57; // [rsp+1C0h] [rbp+B8h]
  __int64 *v58; // [rsp+1C8h] [rbp+C0h]
  __int64 v59; // [rsp+1D0h] [rbp+C8h]
  int *v60; // [rsp+1D8h] [rbp+D0h]
  __int64 v61; // [rsp+1E0h] [rbp+D8h]

  v46 = 0;
  *(_OWORD *)v45 = 0;
  v47 = 0;
  v48 = 0;
  memset(v44, 0, sizeof(v44));
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, a3, (int)v45, 20, v45, 0);
  v10 = Structure;
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7944,
      (unsigned int)Structure);
    return v10;
  }
  v11 = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v45[1], (int)&v45[2], 32, &v47, 0);
  v10 = v11;
  if ( v11 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7957,
      (unsigned int)v11);
    return v10;
  }
  v12 = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v45[3], (int)&v46, 96, v44, 0);
  v10 = v12;
  if ( v12 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7975,
      (unsigned int)v12);
    return v10;
  }
  v13 = WORD1(v44[0]);
  if ( !LOBYTE(v44[0]) )
  {
    v10 = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7982,
      3221227787LL);
    return v10;
  }
  v14 = *a2;
  v15 = *a2 & 1;
  if ( v15 && ((BYTE8(v48) & 1) == 0 && !*((_QWORD *)&v44[2] + 1) || (BYTE1(v44[0]) & 1) == 0) )
  {
    v10 = -1073741713;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v50, "VsmmPhuStorepMemoryBlockDeserialize");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v37 = 8017;
      v52 = &v37;
      v53 = 4;
      v54 = (int *)&v38;
      LODWORD(v38) = v16;
      v39 = v17 & *((_QWORD *)&v48 + 1);
      v56 = &v39;
      v40 = *((_QWORD *)&v44[2] + 1);
      v58 = &v40;
      v55 = 4;
      LOBYTE(v36) = v17 & BYTE1(v44[0]);
      v60 = &v36;
      v57 = 8;
      v59 = 8;
      v61 = v17;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004F6AC, 0, 0, 9, v49);
    }
    return v10;
  }
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( ((*((_QWORD *)&v48 + 1) >> 4) & 1LL) != 0 || (BYTE1(v44[0]) & 2) == 0 )
  {
    if ( (v14 & 4) == 0 )
    {
      if ( !v15 )
        goto LABEL_31;
      if ( (v14 & 2) == 0 )
      {
        v10 = -1073741713;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorepMemoryBlockDeserialize",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          8074,
          3221225583LL);
        return v10;
      }
    }
    if ( (BYTE1(v44[0]) & 2) == 0 )
    {
      if ( v15 )
      {
        *((_QWORD *)&v44[1] + 1) = 0;
        *(_QWORD *)&v44[2] = 0;
      }
      else if ( *((_QWORD *)&v44[1] + 1) )
      {
        v18 = 1;
      }
    }
    v20 = v15;
    if ( ((*((_QWORD *)&v48 + 1) >> 4) & 1LL) != 0 )
    {
      if ( (BYTE1(v44[0]) & 1) != 0 )
        v20 = 1;
      else
        v19 = 1;
    }
  }
LABEL_31:
  v21 = v44[3];
  v22 = v44[5];
  v23 = v44[2];
  v41[0] = v44[0];
  v41[3] = v44[3];
  v42 = v44[4];
  v43 = v44[5];
  v24 = VsmmPhuStoreMemoryBlockDeterminePageOwnership(a4, *((_QWORD *)&v48 + 1));
  if ( !v13 )
  {
    *((_QWORD *)&v41[3] + 1) = *(_QWORD *)&v44[3];
    v21 = v41[3];
    *((_QWORD *)&v42 + 1) = *((_QWORD *)&v44[3] + 1);
    *(_QWORD *)&v42 = 0;
    v25 = v42;
    *(_QWORD *)&v43 = *(_QWORD *)&v44[4];
    goto LABEL_38;
  }
  if ( v13 == 1 )
  {
LABEL_38:
    v27 = 0;
    goto LABEL_39;
  }
  if ( v13 != 2 )
  {
    if ( v13 != 3 )
      goto LABEL_48;
    goto LABEL_42;
  }
  v27 = *((_QWORD *)&v43 + 1);
LABEL_39:
  if ( v27 )
    v27 = -1;
  *((_QWORD *)&v43 + 1) = v27;
  v22 = v43;
LABEL_42:
  if ( (BYTE1(v41[0]) & 4) != 0 )
  {
    v10 = -1073739509;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      return v10;
    tlgCreate1Sz_char(v50, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v38) = 8176;
    v52 = (int *)&v38;
    v29 = &unk_14004F4FA;
    v57 = 2;
    v54 = &v37;
    LOWORD(v36) = WORD1(v41[0]);
LABEL_68:
    v56 = (__int64 *)&v36;
    v53 = 4;
    v37 = v28;
    v55 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v29, 0, 0, 7, v49);
    return v10;
  }
  if ( v24 == 1 )
    BYTE1(v41[0]) |= 4u;
LABEL_48:
  WORD1(v41[0]) = 4;
  if ( (BYTE1(v41[0]) & 4) != 0 && v24 != 1 )
  {
    v10 = -1073739509;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      return v10;
    tlgCreate1Sz_char(v50, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v38) = 8215;
    v29 = &unk_14004F54F;
LABEL_67:
    v57 = 4;
    v52 = (int *)&v38;
    v54 = &v37;
    v36 = v30;
    goto LABEL_68;
  }
  if ( (unsigned int)(DWORD1(v41[0]) - 1) > 1 )
  {
    v10 = -1073739509;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      return v10;
    tlgCreate1Sz_char(v50, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v38) = 8227;
    v29 = &unk_14004F5A0;
    goto LABEL_67;
  }
  v31 = v48;
  *(_OWORD *)a5 = v47;
  *(_OWORD *)(a5 + 32) = v41[0];
  *(_OWORD *)(a5 + 48) = v26;
  *(_OWORD *)(a5 + 64) = v23;
  *(_OWORD *)(a5 + 80) = v21;
  *(_OWORD *)(a5 + 96) = v25;
  *(_OWORD *)(a5 + 112) = v22;
  *(_OWORD *)(a5 + 16) = v31;
  if ( v20 )
    *(_QWORD *)(a5 + 112) = 0;
  if ( v18 )
  {
    v32 = *(_QWORD *)(a5 + 64);
    v33 = *(_QWORD *)(a5 + 56);
    if ( v32 )
    {
      memset(v41, 0, sizeof(v41));
      VsmmPhysicalBufferAssign(0, v34, v33, v32, v41);
      VsmmPhysicalBufferTeardown(v41);
      *(_QWORD *)(a5 + 64) = 0;
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(a5 + 56), 0x6D4D6456u);
    }
    *(_QWORD *)(a5 + 56) = 0;
  }
  if ( v19 )
    VsmmPhuStorepMemoryBlockFree(a4, a5);
  return 0;
}

```

## disassembly

```asm
0x1400b8c10  mov     rax, rsp
0x1400b8c13  mov     [rax+10h], rbx
0x1400b8c17  push    rbp
0x1400b8c18  push    rsi
0x1400b8c19  push    rdi
0x1400b8c1a  push    r12
0x1400b8c1c  push    r13
0x1400b8c1e  push    r14
0x1400b8c20  push    r15
0x1400b8c22  lea     rbp, [rax-138h]
0x1400b8c29  sub     rsp, 200h
0x1400b8c30  movaps  xmmword ptr [rax-48h], xmm6
0x1400b8c34  mov     rax, cs:__security_cookie
0x1400b8c3b  xor     rax, rsp
0x1400b8c3e  mov     [rbp+130h+var_50], rax
0x1400b8c45  mov     rdi, [rbp+130h+arg_20]
0x1400b8c4c  xor     eax, eax
0x1400b8c4e  xorps   xmm1, xmm1
0x1400b8c51  mov     [rbp+130h+var_110], eax
0x1400b8c54  mov     ebx, r8d
0x1400b8c57  mov     r14, rdx
0x1400b8c5a  mov     rsi, rcx
0x1400b8c5d  xorps   xmm0, xmm0
0x1400b8c60  lea     r12d, [rax+60h]
0x1400b8c64  xor     edx, edx; Val
0x1400b8c66  mov     r8d, r12d; Size
0x1400b8c69  lea     rcx, [rbp+130h+var_180]; void *
0x1400b8c6d  mov     r13, r9
0x1400b8c70  movups  xmmword ptr [rbp+130h+var_120], xmm0
0x1400b8c74  movups  [rbp+130h+var_108], xmm1
0x1400b8c78  movups  [rbp+130h+var_F8], xmm1
0x1400b8c7c  call    memset
0x1400b8c81  lea     rax, [rbp+130h+var_120]
0x1400b8c85  xor     r15d, r15d
0x1400b8c88  mov     [rsp+230h+var_208], r15; __int64
0x1400b8c8d  lea     r9d, [r12-4Ch]; int
0x1400b8c92  lea     r8, [rbp+130h+var_120]; int
0x1400b8c96  mov     [rsp+230h+var_210], rax; void *
0x1400b8c9b  mov     edx, ebx; int
0x1400b8c9d  mov     rcx, rsi; int
0x1400b8ca0  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b8ca5  mov     ebx, eax
0x1400b8ca7  test    eax, eax
0x1400b8ca9  jns     short loc_1400B8CCC
0x1400b8cab  mov     r9d, eax
0x1400b8cae  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8cb5  mov     r8d, 1F08h
0x1400b8cbb  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8cc2  call    VidTraceErrorStatusInternal0
0x1400b8cc7  jmp     loc_1400B92A9
0x1400b8ccc  mov     edx, [rbp+130h+var_120+4]; int
0x1400b8ccf  lea     rax, [rbp+130h+var_108]
0x1400b8cd3  mov     [rsp+230h+var_208], r15; __int64
0x1400b8cd8  lea     r8, [rbp+130h+var_120+8]; int
0x1400b8cdc  mov     r9d, 20h ; ' '; int
0x1400b8ce2  mov     [rsp+230h+var_210], rax; void *
0x1400b8ce7  mov     rcx, rsi; int
0x1400b8cea  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b8cef  mov     ebx, eax
0x1400b8cf1  test    eax, eax
0x1400b8cf3  jns     short loc_1400B8D16
0x1400b8cf5  mov     r9d, eax
0x1400b8cf8  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8cff  mov     r8d, 1F15h
0x1400b8d05  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8d0c  call    VidTraceErrorStatusInternal0
0x1400b8d11  jmp     loc_1400B92A9
0x1400b8d16  mov     edx, [rbp+130h+var_120+0Ch]; int
0x1400b8d19  lea     rax, [rbp+130h+var_180]
0x1400b8d1d  mov     [rsp+230h+var_208], r15; __int64
0x1400b8d22  lea     r8, [rbp+130h+var_110]; int
0x1400b8d26  mov     r9d, r12d; int
0x1400b8d29  mov     [rsp+230h+var_210], rax; void *
0x1400b8d2e  mov     rcx, rsi; int
0x1400b8d31  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b8d36  xor     r10d, r10d
0x1400b8d39  mov     ebx, eax
0x1400b8d3b  test    eax, eax
0x1400b8d3d  jns     short loc_1400B8D60
0x1400b8d3f  mov     r9d, eax
0x1400b8d42  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8d49  mov     r8d, 1F27h
0x1400b8d4f  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8d56  call    VidTraceErrorStatusInternal0
0x1400b8d5b  jmp     loc_1400B92A9
0x1400b8d60  mov     r15, qword ptr [rbp+130h+var_180]
0x1400b8d64  test    r15b, r15b
0x1400b8d67  jnz     short loc_1400B8D93
0x1400b8d69  mov     r8d, 0C000090Bh
0x1400b8d6f  mov     ebx, r8d
0x1400b8d72  mov     r9d, r8d
0x1400b8d75  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8d7c  mov     r8d, 1F2Eh
0x1400b8d82  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8d89  call    VidTraceErrorStatusInternal0
0x1400b8d8e  jmp     loc_1400B92A9
0x1400b8d93  mov     r8, [r14]
0x1400b8d96  mov     r11d, 1
0x1400b8d9c  mov     r9, qword ptr [rbp+130h+var_F8+8]
0x1400b8da0  mov     rax, r8
0x1400b8da3  mov     dl, byte ptr [rbp+130h+var_180+1]
0x1400b8da6  and     rax, r11
0x1400b8da9  jz      loc_1400B8ECF
0x1400b8daf  test    r11b, r9b
0x1400b8db2  jnz     short loc_1400B8DBA
0x1400b8db4  cmp     qword ptr [rbp+130h+var_160+8], r10
0x1400b8db8  jz      short loc_1400B8DC3
0x1400b8dba  test    r11b, dl
0x1400b8dbd  jnz     loc_1400B8ECF
0x1400b8dc3  mov     eax, cs:dword_140065110
0x1400b8dc9  mov     r9d, 0C000006Fh
0x1400b8dcf  mov     ebx, r9d
0x1400b8dd2  cmp     eax, 2
0x1400b8dd5  jbe     loc_1400B92A9
0x1400b8ddb  mov     edx, 100h
0x1400b8de0  lea     rcx, dword_140065110
0x1400b8de7  call    _tlgKeywordOn
0x1400b8dec  test    al, al
0x1400b8dee  jz      loc_1400B92A9
0x1400b8df4  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8dfb  lea     rcx, [rbp+130h+var_C0]
0x1400b8dff  call    _tlgCreate1Sz_char
0x1400b8e04  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8e0b  lea     rcx, [rbp+130h+var_B0]
0x1400b8e12  call    _tlgCreate1Sz_char
0x1400b8e17  lea     rax, [rsp+230h+var_1FC]
0x1400b8e1c  mov     [rsp+230h+var_1FC], 1F51h
0x1400b8e24  mov     [rbp+130h+var_A0], rax
0x1400b8e2b  lea     rdx, unk_14004F6AC
0x1400b8e32  lea     rax, [rsp+230h+var_1F8]
0x1400b8e37  mov     [rbp+130h+var_98], 4
0x1400b8e42  mov     [rbp+130h+var_90], rax
0x1400b8e49  mov     rax, qword ptr [rbp+130h+var_F8+8]
0x1400b8e4d  and     rax, r11
0x1400b8e50  mov     dword ptr [rsp+230h+var_1F8], r9d
0x1400b8e55  mov     [rsp+230h+var_1F0], rax
0x1400b8e5a  lea     rax, [rsp+230h+var_1F0]
0x1400b8e5f  mov     [rbp+130h+var_80], rax
0x1400b8e66  mov     rax, qword ptr [rbp+130h+var_160+8]
0x1400b8e6a  mov     qword ptr [rsp+230h+var_1E8], rax
0x1400b8e6f  lea     rax, [rsp+230h+var_1E8]
0x1400b8e74  mov     [rbp+130h+var_70], rax
0x1400b8e7b  mov     al, byte ptr [rbp+130h+var_180+1]
0x1400b8e7e  and     al, r11b
0x1400b8e81  mov     [rbp+130h+var_88], 4
0x1400b8e8c  mov     byte ptr [rsp+230h+var_200], al
0x1400b8e90  lea     rax, [rsp+230h+var_200]
0x1400b8e95  mov     [rbp+130h+var_60], rax
0x1400b8e9c  lea     rax, [rbp+130h+var_E0]
0x1400b8ea0  mov     [rsp+230h+var_208], rax
0x1400b8ea5  mov     dword ptr [rsp+230h+var_210], 9
0x1400b8ead  mov     [rbp+130h+var_78], 8
0x1400b8eb8  mov     [rbp+130h+var_68], 8
0x1400b8ec3  mov     [rbp+130h+var_58], r11
0x1400b8eca  jmp     loc_1400B9297
0x1400b8ecf  mov     rcx, r9
0x1400b8ed2  movzx   r14d, r10b
0x1400b8ed6  shr     rcx, 4
0x1400b8eda  mov     r12b, r10b
0x1400b8edd  mov     bl, r10b
0x1400b8ee0  mov     esi, 4
0x1400b8ee5  and     rcx, r11
0x1400b8ee8  jnz     short loc_1400B8EEF
0x1400b8eea  test    dl, 2
0x1400b8eed  jnz     short loc_1400B8F56
0x1400b8eef  test    sil, r8b
0x1400b8ef2  jnz     short loc_1400B8F26
0x1400b8ef4  test    rax, rax
0x1400b8ef7  jz      short loc_1400B8F56
0x1400b8ef9  test    r8b, 2
0x1400b8efd  jnz     short loc_1400B8F26
0x1400b8eff  mov     r9d, 0C000006Fh
0x1400b8f05  mov     ebx, r9d
0x1400b8f08  mov     r8d, 1F8Ah
0x1400b8f0e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8f15  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b8f1c  call    VidTraceErrorStatusInternal0
0x1400b8f21  jmp     loc_1400B92A9
0x1400b8f26  test    dl, 2
0x1400b8f29  jnz     short loc_1400B8F42
0x1400b8f2b  test    rax, rax
0x1400b8f2e  jz      short loc_1400B8F3A
0x1400b8f30  mov     [rbp+130h+var_168], r10
0x1400b8f34  mov     qword ptr [rbp+130h+var_160], r10
0x1400b8f38  jmp     short loc_1400B8F42
0x1400b8f3a  cmp     [rbp+130h+var_168], r10
0x1400b8f3e  cmovnz  r14d, r11d
0x1400b8f42  mov     bl, al
0x1400b8f44  test    rcx, rcx
0x1400b8f47  jz      short loc_1400B8F56
0x1400b8f49  test    r11b, dl
0x1400b8f4c  jz      short loc_1400B8F53
0x1400b8f4e  mov     bl, r11b
0x1400b8f51  jmp     short loc_1400B8F56
0x1400b8f53  mov     r12b, r11b
0x1400b8f56  movaps  xmm0, [rbp+130h+var_180]
0x1400b8f5a  mov     rdx, r9
0x1400b8f5d  movaps  xmm3, [rbp+130h+var_150]
0x1400b8f61  mov     rcx, r13
0x1400b8f64  movaps  xmm4, [rbp+130h+var_140]
0x1400b8f68  movaps  xmm2, [rbp+130h+var_130]
0x1400b8f6c  movaps  xmm5, xmmword ptr [rbp-40h]
0x1400b8f70  movaps  xmm6, [rbp+130h+var_160]
0x1400b8f74  movaps  [rsp+230h+var_1E8+8], xmm0
0x1400b8f79  movaps  [rbp+130h+var_1B0], xmm3
0x1400b8f7d  movaps  [rbp+130h+var_1A0], xmm4
0x1400b8f81  movaps  [rbp+130h+var_190], xmm2
0x1400b8f85  call    VsmmPhuStoreMemoryBlockDeterminePageOwnership
0x1400b8f8a  shr     r15, 10h
0x1400b8f8e  mov     r9d, eax
0x1400b8f91  movzx   edx, r15w
0x1400b8f95  xor     r15d, r15d
0x1400b8f98  test    edx, edx
0x1400b8f9a  jz      short loc_1400B8FB6
0x1400b8f9c  sub     edx, 1
0x1400b8f9f  jz      short loc_1400B8FDA
0x1400b8fa1  sub     edx, 1
0x1400b8fa4  jz      short loc_1400B8FB0
0x1400b8fa6  cmp     edx, 1
0x1400b8fa9  jz      short loc_1400B8FF0
0x1400b8fab  jmp     loc_1400B90A7
0x1400b8fb0  mov     rax, qword ptr [rbp+130h+var_190+8]
0x1400b8fb4  jmp     short loc_1400B8FDD
0x1400b8fb6  mov     rax, qword ptr [rbp+130h+var_150]
0x1400b8fba  mov     qword ptr [rbp+130h+var_1B0+8], rax
0x1400b8fbe  mov     rax, qword ptr [rbp+130h+var_150+8]
0x1400b8fc2  movaps  xmm3, [rbp+130h+var_1B0]
0x1400b8fc6  mov     qword ptr [rbp+130h+var_1A0+8], rax
0x1400b8fca  mov     rax, qword ptr [rbp+130h+var_140]
0x1400b8fce  mov     qword ptr [rbp+130h+var_1A0], r15
0x1400b8fd2  movaps  xmm4, [rbp+130h+var_1A0]
0x1400b8fd6  mov     qword ptr [rbp+130h+var_190], rax
0x1400b8fda  mov     rax, r15
0x1400b8fdd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b8fe1  test    rax, rax
0x1400b8fe4  cmovnz  rax, rcx
0x1400b8fe8  mov     qword ptr [rbp+130h+var_190+8], rax
0x1400b8fec  movaps  xmm2, [rbp+130h+var_190]
0x1400b8ff0  mov     rax, qword ptr [rsp+230h+var_1E8+8]
0x1400b8ff5  shr     rax, 8
0x1400b8ff9  test    sil, al
0x1400b8ffc  jz      loc_1400B909C
0x1400b9002  mov     eax, cs:dword_140065110
0x1400b9008  mov     r8d, 0C000090Bh
0x1400b900e  mov     ebx, r8d
0x1400b9011  cmp     eax, 2
0x1400b9014  jbe     loc_1400B92A9
0x1400b901a  mov     edx, 100h
0x1400b901f  lea     rcx, dword_140065110
0x1400b9026  call    _tlgKeywordOn
0x1400b902b  test    al, al
0x1400b902d  jz      loc_1400B92A9
0x1400b9033  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b903a  lea     rcx, [rbp+130h+var_C0]
0x1400b903e  call    _tlgCreate1Sz_char
0x1400b9043  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b904a  lea     rcx, [rbp+130h+var_B0]
0x1400b9051  call    _tlgCreate1Sz_char
0x1400b9056  lea     rax, [rsp+230h+var_1F8]
0x1400b905b  mov     dword ptr [rsp+230h+var_1F8], 1FF0h
0x1400b9063  mov     [rbp+130h+var_A0], rax
0x1400b906a  lea     rdx, unk_14004F4FA
0x1400b9071  lea     rax, [rsp+230h+var_1FC]
0x1400b9076  mov     [rbp+130h+var_78], 2
0x1400b9081  mov     [rbp+130h+var_90], rax
0x1400b9088  movzx   eax, word ptr [rsp+230h+var_1E8+0Ah]
0x1400b908d  mov     word ptr [rsp+230h+var_200], ax
0x1400b9092  lea     rax, [rsp+230h+var_200]
0x1400b9097  jmp     loc_1400B926C
0x1400b909c  cmp     r9d, 1
0x1400b90a0  jnz     short loc_1400B90A7
0x1400b90a2  or      byte ptr [rsp+230h+var_1E8+9], sil
0x1400b90a7  mov     word ptr [rsp+230h+var_1E8+0Ah], si
0x1400b90ac  test    byte ptr [rsp+230h+var_1E8+9], sil
0x1400b90b1  jz      short loc_1400B9121
0x1400b90b3  cmp     r9d, 1
0x1400b90b7  jz      short loc_1400B9121
0x1400b90b9  mov     eax, cs:dword_140065110
0x1400b90bf  mov     r8d, 0C000090Bh
0x1400b90c5  mov     ebx, r8d
0x1400b90c8  cmp     eax, 2
0x1400b90cb  jbe     loc_1400B92A9
0x1400b90d1  mov     edx, 100h
0x1400b90d6  lea     rcx, dword_140065110
0x1400b90dd  call    _tlgKeywordOn
0x1400b90e2  test    al, al
0x1400b90e4  jz      loc_1400B92A9
0x1400b90ea  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b90f1  lea     rcx, [rbp+130h+var_C0]
0x1400b90f5  call    _tlgCreate1Sz_char
0x1400b90fa  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b9101  lea     rcx, [rbp+130h+var_B0]
0x1400b9108  call    _tlgCreate1Sz_char
0x1400b910d  mov     dword ptr [rsp+230h+var_1F8], 2017h
0x1400b9115  lea     rdx, unk_14004F54F
0x1400b911c  jmp     loc_1400B9243
0x1400b9121  mov     r9d, dword ptr [rsp+230h+var_1E8+0Ch]
0x1400b9126  lea     eax, [r9-1]
0x1400b912a  cmp     eax, 1
0x1400b912d  ja      loc_1400B91E0
  ... truncated ...
```
