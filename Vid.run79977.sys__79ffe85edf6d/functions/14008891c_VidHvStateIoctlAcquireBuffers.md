# VidHvStateIoctlAcquireBuffers

- ea: `0x14008891c`
- end: `0x140088e96`
- name: `VidHvStateIoctlAcquireBuffers`
- size: `1402`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400321a4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140024e18`
- `0x1400305c0`
- `0x140030960`
- `0x140030990`
- `0x1400309d0`
- `0x14008891c`
- `0x14008a704`
- `0x14008ad14`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140088bf0`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140088bf0`
- `ntoskrnl!RtlRbRemoveNode` at `0x140088b52`
- `ntoskrnl!RtlRbRemoveNode` at `0x140088b52`
- `ntoskrnl!ProbeForWrite` at `0x14008898e`
- `ntoskrnl!ProbeForWrite` at `0x14008898e`

## pseudocode

```c
__int64 __fastcall VidHvStateIoctlAcquireBuffers(
        __int64 a1,
        volatile void *a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6)
{
  char v9; // r12
  __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // r14d
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // r13d
  __int64 **v18; // r10
  __int64 **v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rax
  __int64 *v23; // rcx
  __int64 v24; // r8
  unsigned __int64 v25; // r14
  __int64 *v26; // rax
  unsigned __int64 v27; // rax
  __int64 *v28; // rdx
  int v29; // ecx
  __int64 v30; // r8
  __int64 *v32; // [rsp+48h] [rbp-140h] BYREF
  __int64 v33; // [rsp+50h] [rbp-138h] BYREF
  __int64 v34; // [rsp+58h] [rbp-130h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-128h] BYREF
  unsigned int *v36; // [rsp+70h] [rbp-118h] BYREF
  _DWORD *v37; // [rsp+78h] [rbp-110h]
  char v38[32]; // [rsp+80h] [rbp-108h] BYREF
  char v39[16]; // [rsp+A0h] [rbp-E8h] BYREF
  char v40[16]; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 *v41; // [rsp+C0h] [rbp-C8h]
  __int64 v42; // [rsp+C8h] [rbp-C0h]
  __int64 *v43; // [rsp+D0h] [rbp-B8h]
  __int64 v44; // [rsp+D8h] [rbp-B0h]
  __int64 v45; // [rsp+E0h] [rbp-A8h]
  __int64 v46; // [rsp+E8h] [rbp-A0h]
  _DWORD *v47; // [rsp+F0h] [rbp-98h]
  __int64 v48; // [rsp+F8h] [rbp-90h]
  __int64 v49; // [rsp+100h] [rbp-88h]
  _DWORD v50[2]; // [rsp+108h] [rbp-80h] BYREF
  unsigned int **v51; // [rsp+110h] [rbp-78h]
  __int64 v52; // [rsp+118h] [rbp-70h]
  _QWORD *v53; // [rsp+120h] [rbp-68h]
  __int64 v54; // [rsp+128h] [rbp-60h]
  __int64 *v55; // [rsp+130h] [rbp-58h]
  __int64 v56; // [rsp+138h] [rbp-50h]

  v35[1] = a4;
  v36 = a3;
  v35[0] = a2;
  v37 = a6;
  v34 = a1;
  v33 = a4;
  v9 = 0;
  v10 = 0;
  v32 = 0;
  *a6 = 0;
  ProbeForWrite(a2, 8LL * *a3, 8u);
  if ( (unsigned __int8)VidOpCtrlStart(a1 + 12624, v11, v12, v13) )
  {
    v10 = *(_QWORD *)(a1 + 12720);
    v32 = (__int64 *)v10;
    VidLockAcquireExclusive(v10);
    v9 = 1;
    v15 = a5;
    v16 = VidHvStatepAcquireBuffers(a1, a4, a5, a6);
    v14 = v16;
    if ( v16 >= 0 )
    {
      v17 = *a3;
      if ( v17 >= *(_DWORD *)(v10 + 56) )
        v17 = *(_DWORD *)(v10 + 56);
      v18 = (__int64 **)(v10 + 40);
      v19 = *(__int64 ***)(v10 + 40);
      v20 = 0;
      v21 = v35[0];
      while ( v19 != v18 && (unsigned int)v20 < v17 )
      {
        *(_QWORD *)(v21 + 8 * v20) = v19[3];
        v19 = (__int64 **)*v19;
        v20 = (unsigned int)(v20 + 1);
      }
      LODWORD(v34) = 0;
      if ( v17 )
      {
        do
        {
          v22 = *v18;
          if ( (__int64 **)(*v18)[1] != v18 || (v23 = (__int64 *)*v22, *(__int64 **)(*v22 + 8) != v22) )
            __fastfail(3u);
          *v18 = v23;
          v23[1] = (__int64)v18;
          --*(_DWORD *)(v10 + 56);
          v32 = v22 - 3;
          RtlRbRemoveNode(v10 + 16, v22 - 3);
          v25 = *(_QWORD *)(v10 + 64);
          if ( (*(_BYTE *)(v10 + 72) & 1) != 0 && v25 )
            v25 ^= v10 + 64;
          LODWORD(v33) = *(_BYTE *)(v10 + 72) & 1;
          LOBYTE(v24) = 0;
          if ( v25 )
          {
            v26 = v32 + 6;
            for ( v35[0] = v32 + 6; ; v26 = (__int64 *)v35[0] )
            {
              if ( (int)VidHvStatepCompareBuffersByMappedAddress(v26, v25) < 0 )
              {
                v27 = *(_QWORD *)v25;
                if ( (_DWORD)v33 )
                {
                  if ( !v27 )
                    goto LABEL_31;
                  v27 ^= v25;
                }
                if ( !v27 )
                {
LABEL_31:
                  LOBYTE(v24) = 0;
                  break;
                }
              }
              else
              {
                v27 = *(_QWORD *)(v25 + 8);
                if ( (_DWORD)v33 )
                {
                  if ( !v27 )
                    goto LABEL_25;
                  v27 ^= v25;
                }
                if ( !v27 )
                {
LABEL_25:
                  LOBYTE(v24) = 1;
                  break;
                }
              }
              v25 = v27;
            }
          }
          RtlRbInsertNodeEx(v10 + 64, v25, v24, v32);
          v28 = v32;
          *((_DWORD *)v32 + 32) = v32[16] & 0xFFFFFFFC | 2;
          v29 = a5 & 1;
          if ( (a5 & 1) != 0 && (*v37 & 2) == 0 && *(__int64 **)(v10 + 80) == v28 )
            *(_QWORD *)(v10 + 80) = 0;
          LODWORD(v34) = v34 + 1;
          v18 = (__int64 **)(v10 + 40);
        }
        while ( (unsigned int)v34 < v17 );
      }
      else
      {
        v29 = a5 & 1;
      }
      v14 = 0;
      if ( v29 && *(_QWORD *)(v10 + 80) )
        *v37 |= 2u;
      *v36 = v17;
    }
    else
    {
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidHvStateIoctlAcquireBuffers",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
        362,
        a1 + 656,
        a1 + 120,
        *(_QWORD *)(a1 + 648),
        v16);
    }
  }
  else
  {
    v14 = -1073741436;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlAcquireBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      349,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      -1073741436);
    v15 = a5;
  }
  if ( v14 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v39, "VidHvStateIoctlAcquireBuffers");
    tlgCreate1Sz_char(v40, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
    LODWORD(v34) = 443;
    v41 = &v34;
    v42 = 4;
    LODWORD(v33) = v14;
    v43 = &v33;
    v44 = 4;
    v45 = a1 + 656;
    v46 = 16;
    v47 = v50;
    v48 = 2;
    v49 = *(_QWORD *)(a1 + 128);
    v50[0] = *(unsigned __int16 *)(a1 + 120);
    v50[1] = 0;
    v36 = *(unsigned int **)(a1 + 648);
    v51 = &v36;
    v52 = 8;
    v35[0] = v30;
    v53 = v35;
    v54 = 8;
    LODWORD(v32) = v15;
    v55 = (__int64 *)&v32;
    v56 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140047441, 0, 0, 12, v38);
  }
  if ( v9 )
  {
    VidLockRelease(v10);
    VidOpCtrlFinish(a1 + 12624);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14008891c  push    rbx
0x14008891e  push    rsi
0x14008891f  push    r12
0x140088921  push    r13
0x140088923  push    r14
0x140088925  push    r15
0x140088927  sub     rsp, 158h
0x14008892e  mov     rax, cs:__security_cookie
0x140088935  xor     rax, rsp
0x140088938  mov     [rsp+188h+var_48], rax
0x140088940  mov     r14, r9
0x140088943  mov     [rsp+188h+var_120], r9
0x140088948  mov     r13, r8
0x14008894b  mov     [rsp+188h+var_118], r8
0x140088950  mov     rax, rdx
0x140088953  mov     [rsp+188h+var_128], rdx
0x140088958  mov     rsi, rcx
0x14008895b  mov     rbx, [rsp+188h+arg_28]
0x140088963  mov     [rsp+188h+var_110], rbx
0x140088968  mov     [rsp+188h+var_130], rcx
0x14008896d  mov     [rsp+188h+var_138], r9
0x140088972  xor     r12b, r12b
0x140088975  xor     r15d, r15d
0x140088978  mov     [rsp+188h+var_140], r15
0x14008897d  mov     [rbx], r15d
0x140088980  mov     edx, [r8]
0x140088983  shl     rdx, 3; Length
0x140088987  lea     r8d, [r15+8]; Alignment
0x14008898b  mov     rcx, rax; Address
0x14008898e  call    cs:__imp_ProbeForWrite
0x140088995  nop     dword ptr [rax+rax+00h]
0x14008899a  nop
0x14008899b  lea     rcx, [rsi+3150h]
0x1400889a2  call    VidOpCtrlStart
0x1400889a7  test    al, al
0x1400889a9  jnz     short loc_1400889FC
0x1400889ab  mov     r14d, 0C0000184h
0x1400889b1  lea     rcx, [rsi+78h]
0x1400889b5  lea     r9, [rsi+290h]
0x1400889bc  mov     [rsp+188h+var_158], r14d
0x1400889c1  mov     rax, [rsi+288h]
0x1400889c8  mov     [rsp+188h+var_160], rax
0x1400889cd  mov     [rsp+188h+var_168], rcx
0x1400889d2  mov     r8d, 15Dh
0x1400889d8  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x1400889df  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x1400889e6  call    VidTracePartitionErrorInternal0
0x1400889eb  mov     ebx, [rsp+188h+arg_20]
0x1400889f2  mov     r8, [rsp+188h+var_120]
0x1400889f7  jmp     loc_140088CD0
0x1400889fc  mov     r15, [rsi+31B0h]
0x140088a03  mov     [rsp+188h+var_140], r15
0x140088a08  mov     rcx, r15
0x140088a0b  call    VidLockAcquireExclusive
0x140088a10  mov     r12d, 1
0x140088a16  mov     [rsp+188h+var_148], r12b
0x140088a1b  mov     r9, rbx
0x140088a1e  mov     ebx, [rsp+188h+arg_20]
0x140088a25  mov     r8d, ebx
0x140088a28  mov     rdx, r14
0x140088a2b  mov     rcx, rsi
0x140088a2e  call    VidHvStatepAcquireBuffers
0x140088a33  mov     r14d, eax
0x140088a36  test    eax, eax
0x140088a38  jns     short loc_140088A78
0x140088a3a  lea     rdx, [rsi+78h]
0x140088a3e  lea     r9, [rsi+290h]
0x140088a45  mov     [rsp+188h+var_158], eax
0x140088a49  mov     rcx, [rsi+288h]
0x140088a50  mov     [rsp+188h+var_160], rcx
0x140088a55  mov     [rsp+188h+var_168], rdx
0x140088a5a  mov     r8d, 16Ah
0x140088a60  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140088a67  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140088a6e  call    VidTracePartitionErrorInternal0
0x140088a73  jmp     loc_1400889F2
0x140088a78  mov     eax, [r15+38h]
0x140088a7c  mov     r13d, [r13+0]
0x140088a80  cmp     r13d, eax
0x140088a83  cmovnb  r13d, eax
0x140088a87  lea     r10, [r15+28h]
0x140088a8b  mov     rdx, [r10]
0x140088a8e  xor     r8d, r8d
0x140088a91  mov     r9, [rsp+188h+var_128]
0x140088a96  cmp     rdx, r10
0x140088a99  jz      short loc_140088B0C
0x140088a9b  cmp     r8d, r13d
0x140088a9e  jnb     short loc_140088B0C
0x140088aa0  mov     rax, [rdx+18h]
0x140088aa4  mov     [r9+r8*8], rax
0x140088aa8  mov     rdx, [rdx]
0x140088aab  add     r8d, r12d
0x140088aae  jmp     short loc_140088A96
0x140088ab0  mov     r14d, eax
0x140088ab3  mov     rsi, [rsp+188h+var_130]
0x140088ab8  lea     rcx, [rsi+78h]
0x140088abc  lea     r9, [rsi+290h]
0x140088ac3  mov     [rsp+188h+var_158], eax
0x140088ac7  mov     rax, [rsi+288h]
0x140088ace  mov     [rsp+188h+var_160], rax
0x140088ad3  mov     [rsp+188h+var_168], rcx
0x140088ad8  mov     r8d, 184h
0x140088ade  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140088ae5  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140088aec  call    VidTracePartitionErrorInternal0
0x140088af1  mov     ebx, [rsp+188h+arg_20]
0x140088af8  mov     r15, [rsp+188h+var_140]
0x140088afd  mov     r12b, [rsp+188h+var_148]
0x140088b02  mov     r8, [rsp+188h+var_138]
0x140088b07  jmp     loc_140088CD0
0x140088b0c  mov     dword ptr [rsp+188h+var_130], 0
0x140088b14  test    r13d, r13d
0x140088b17  jz      loc_140088C54
0x140088b1d  mov     rax, [r10]
0x140088b20  cmp     [rax+8], r10
0x140088b24  jnz     loc_140088C4D
0x140088b2a  mov     rcx, [rax]
0x140088b2d  cmp     [rcx+8], rax
0x140088b31  jnz     loc_140088C4D
0x140088b37  mov     [r10], rcx
0x140088b3a  mov     [rcx+8], r10
0x140088b3e  dec     dword ptr [r15+38h]
0x140088b42  add     rax, 0FFFFFFFFFFFFFFE8h
0x140088b46  mov     [rsp+188h+var_140], rax
0x140088b4b  lea     rcx, [r15+10h]
0x140088b4f  mov     rdx, rax
0x140088b52  call    cs:__imp_RtlRbRemoveNode
0x140088b59  nop     dword ptr [rax+rax+00h]
0x140088b5e  lea     rdx, [r15+40h]
0x140088b62  mov     r14, [rdx]
0x140088b65  test    [r15+48h], r12b
0x140088b69  jz      short loc_140088B73
0x140088b6b  test    r14, r14
0x140088b6e  jz      short loc_140088B73
0x140088b70  xor     r14, rdx
0x140088b73  movzx   eax, byte ptr [rdx+8]
0x140088b77  and     eax, r12d
0x140088b7a  mov     dword ptr [rsp+188h+var_138], eax
0x140088b7e  xor     r8b, r8b
0x140088b81  test    r14, r14
0x140088b84  jz      short loc_140088BE4
0x140088b86  mov     rax, [rsp+188h+var_140]
0x140088b8b  add     rax, 30h ; '0'
0x140088b8f  mov     [rsp+188h+var_128], rax
0x140088b94  mov     rdx, r14
0x140088b97  mov     rcx, rax
0x140088b9a  call    VidHvStatepCompareBuffersByMappedAddress
0x140088b9f  test    eax, eax
0x140088ba1  js      short loc_140088BC0
0x140088ba3  mov     rax, [r14+8]
0x140088ba7  cmp     dword ptr [rsp+188h+var_138], 0
0x140088bac  jz      short loc_140088BB6
0x140088bae  test    rax, rax
0x140088bb1  jz      short loc_140088BBB
0x140088bb3  xor     rax, r14
0x140088bb6  test    rax, rax
0x140088bb9  jnz     short loc_140088BD7
0x140088bbb  mov     r8b, r12b
0x140088bbe  jmp     short loc_140088BE4
0x140088bc0  mov     rax, [r14]
0x140088bc3  cmp     dword ptr [rsp+188h+var_138], 0
0x140088bc8  jz      short loc_140088BD2
0x140088bca  test    rax, rax
0x140088bcd  jz      short loc_140088BE1
0x140088bcf  xor     rax, r14
0x140088bd2  test    rax, rax
0x140088bd5  jz      short loc_140088BE1
0x140088bd7  mov     r14, rax
0x140088bda  mov     rax, [rsp+188h+var_128]
0x140088bdf  jmp     short loc_140088B94
0x140088be1  xor     r8b, r8b
0x140088be4  mov     r9, [rsp+188h+var_140]
0x140088be9  mov     rdx, r14
0x140088bec  lea     rcx, [r15+40h]
0x140088bf0  call    cs:__imp_RtlRbInsertNodeEx
0x140088bf7  nop     dword ptr [rax+rax+00h]
0x140088bfc  mov     rdx, [rsp+188h+var_140]
0x140088c01  mov     eax, [rdx+80h]
0x140088c07  and     eax, 0FFFFFFFEh
0x140088c0a  or      eax, 2
0x140088c0d  mov     [rdx+80h], eax
0x140088c13  mov     ecx, ebx
0x140088c15  and     ecx, r12d
0x140088c18  jz      short loc_140088C33
0x140088c1a  mov     rax, [rsp+188h+var_110]
0x140088c1f  mov     eax, [rax]
0x140088c21  test    al, 2
0x140088c23  jnz     short loc_140088C33
0x140088c25  cmp     [r15+50h], rdx
0x140088c29  jnz     short loc_140088C33
0x140088c2b  mov     qword ptr [r15+50h], 0
0x140088c33  mov     edx, dword ptr [rsp+188h+var_130]
0x140088c37  add     edx, r12d
0x140088c3a  mov     dword ptr [rsp+188h+var_130], edx
0x140088c3e  cmp     edx, r13d
0x140088c41  lea     r10, [r15+28h]
0x140088c45  jb      loc_140088B1D
0x140088c4b  jmp     short loc_140088C59
0x140088c4d  mov     ecx, 3
0x140088c52  int     29h; Win8: RtlFailFast(ecx)
0x140088c54  mov     ecx, ebx
0x140088c56  and     ecx, r12d
0x140088c59  xor     r14d, r14d
0x140088c5c  test    ecx, ecx
0x140088c5e  jz      short loc_140088C6E
0x140088c60  cmp     [r15+50h], r14
0x140088c64  jz      short loc_140088C6E
0x140088c66  mov     rax, [rsp+188h+var_110]
0x140088c6b  or      dword ptr [rax], 2
0x140088c6e  mov     rax, [rsp+188h+var_118]
0x140088c73  mov     [rax], r13d
0x140088c76  jmp     loc_1400889F2
0x140088c7b  mov     r14d, eax
0x140088c7e  mov     rsi, [rsp+188h+var_130]
0x140088c83  lea     rcx, [rsi+78h]
0x140088c87  lea     r9, [rsi+290h]
0x140088c8e  mov     [rsp+188h+var_158], eax
0x140088c92  mov     rax, [rsi+288h]
0x140088c99  mov     [rsp+188h+var_160], rax
0x140088c9e  mov     [rsp+188h+var_168], rcx
0x140088ca3  mov     r8d, 156h
0x140088ca9  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140088cb0  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140088cb7  call    VidTracePartitionErrorInternal0
0x140088cbc  mov     ebx, [rsp+188h+arg_20]
0x140088cc3  mov     r15, [rsp+188h+var_140]
0x140088cc8  mov     r12b, r15b
0x140088ccb  mov     r8, [rsp+188h+var_138]
0x140088cd0  test    r14d, r14d
0x140088cd3  jns     loc_140088E52
0x140088cd9  mov     eax, cs:dword_140065110
0x140088cdf  cmp     eax, 2
0x140088ce2  jbe     loc_140088E52
0x140088ce8  mov     edx, 100h
0x140088ced  lea     rcx, dword_140065110
0x140088cf4  call    _tlgKeywordOn
0x140088cf9  test    al, al
0x140088cfb  jz      loc_140088E52
0x140088d01  lea     rdx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140088d08  lea     rcx, [rsp+188h+var_E8]
0x140088d10  call    _tlgCreate1Sz_char
0x140088d15  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140088d1c  lea     rcx, [rsp+188h+var_D8]
0x140088d24  call    _tlgCreate1Sz_char
0x140088d29  mov     dword ptr [rsp+188h+var_130], 1BBh
0x140088d31  lea     rax, [rsp+188h+var_130]
0x140088d36  mov     [rsp+188h+var_C8], rax
0x140088d3e  mov     [rsp+188h+var_C0], 4
0x140088d4a  mov     dword ptr [rsp+188h+var_138], r14d
0x140088d4f  lea     rax, [rsp+188h+var_138]
0x140088d54  mov     [rsp+188h+var_B8], rax
0x140088d5c  mov     [rsp+188h+var_B0], 4
0x140088d68  lea     rax, [rsi+290h]
0x140088d6f  mov     [rsp+188h+var_A8], rax
0x140088d77  mov     [rsp+188h+var_A0], 10h
0x140088d83  lea     rax, [rsp+188h+var_80]
0x140088d8b  mov     [rsp+188h+var_98], rax
0x140088d93  mov     [rsp+188h+var_90], 2
0x140088d9f  mov     rax, [rsi+80h]
0x140088da6  mov     [rsp+188h+var_88], rax
0x140088dae  movzx   eax, word ptr [rsi+78h]
0x140088db2  mov     [rsp+188h+var_80], eax
0x140088db9  mov     [rsp+188h+var_7C], 0
0x140088dc4  mov     rax, [rsi+288h]
0x140088dcb  mov     [rsp+188h+var_118], rax
0x140088dd0  lea     rax, [rsp+188h+var_118]
0x140088dd5  mov     [rsp+188h+var_78], rax
0x140088ddd  mov     [rsp+188h+var_70], 8
0x140088de9  mov     [rsp+188h+var_128], r8
0x140088dee  lea     rax, [rsp+188h+var_128]
0x140088df3  mov     [rsp+188h+var_68], rax
0x140088dfb  mov     [rsp+188h+var_60], 8
0x140088e07  mov     dword ptr [rsp+188h+var_140], ebx
0x140088e0b  lea     rax, [rsp+188h+var_140]
0x140088e10  mov     [rsp+188h+var_58], rax
0x140088e18  mov     [rsp+188h+var_50], 4
0x140088e24  lea     rax, [rsp+188h+var_108]
0x140088e2c  mov     [rsp+188h+var_160], rax
0x140088e31  mov     dword ptr [rsp+188h+var_168], 0Ch
0x140088e39  xor     r9d, r9d
0x140088e3c  xor     r8d, r8d
0x140088e3f  lea     rdx, unk_140047441
0x140088e46  lea     rcx, dword_140065110
0x140088e4d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140088e52  test    r12b, r12b
0x140088e55  jz      short loc_140088E70
0x140088e57  mov     rcx, r15
0x140088e5a  call    VidLockRelease
0x140088e5f  test    r12b, r12b
0x140088e62  jz      short loc_140088E70
0x140088e64  lea     rcx, [rsi+3150h]
0x140088e6b  call    VidOpCtrlFinish
0x140088e70  mov     eax, r14d
0x140088e73  mov     rcx, [rsp+188h+var_48]
0x140088e7b  xor     rcx, rsp; StackCookie
0x140088e7e  call    __security_check_cookie
0x140088e83  add     rsp, 158h
0x140088e8a  pop     r15
0x140088e8c  pop     r14
0x140088e8e  pop     r13
  ... truncated ...
```
