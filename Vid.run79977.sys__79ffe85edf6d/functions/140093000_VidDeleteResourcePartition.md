# VidDeleteResourcePartition

- ea: `0x140093000`
- end: `0x140093379`
- name: `VidDeleteResourcePartition`
- size: `889`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x1400071a4`
- `0x140007dbc`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400309d0`
- `0x140033b00`
- `0x1400778d4`
- `0x140093000`
- `0x1400959e8`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140093293`
- `ntoskrnl!RtlRbRemoveNode` at `0x140093293`

## string_xrefs

- `0x14009304c`: `VidDeleteResourcePartition`
- `0x1400930bf`: `VidDeleteResourcePartition`
- `0x140093184`: `VidDeleteResourcePartition`
- `0x1400931ff`: `VidDeleteResourcePartition`
- `0x1400932c5`: `VidDeleteResourcePartition`

## pseudocode

```c
__int64 __fastcall VidDeleteResourcePartition(int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  _DWORD *v6; // rbx
  char *v7; // r15
  char *v8; // rsi
  char *v9; // rbx
  void *v10; // rdx
  int *v11; // rax
  char *v12; // rax
  __int64 v13; // r8
  int v15; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v16[3]; // [rsp+34h] [rbp-55h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v19[16]; // [rsp+70h] [rbp-19h] BYREF
  int *v20; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  int *v22; // [rsp+90h] [rbp+7h]
  __int64 v23; // [rsp+98h] [rbp+Fh]
  char *v24; // [rsp+A0h] [rbp+17h]
  __int64 v25; // [rsp+A8h] [rbp+1Fh]

  if ( a2 )
  {
    v5 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidDeleteResourcePartition",
      "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
      1959,
      3221225485LL);
    return v5;
  }
  v6 = VidDeviceExtension;
  v7 = (char *)VidDeviceExtension + 1640;
  v8 = (char *)VidDeviceExtension + 2200;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640, 0, a3, a4);
  VidPushLockAcquireExclusive(v8);
  if ( v6[409] )
  {
    v9 = 0;
    v5 = -1073741436;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v18, "VidDeleteResourcePartition");
      tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v16[0] = 1977;
      v20 = v16;
      v10 = &unk_140048460;
      v11 = &v15;
      v15 = -1073741436;
LABEL_7:
      v22 = v11;
      v25 = 16;
      v24 = (char *)a1;
      v23 = 4;
      v21 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v10, 0, 0, 7, v17);
    }
  }
  else
  {
    v12 = (char *)VidResourcePartitionFindById(v8, a1);
    v9 = v12;
    if ( v12 )
    {
      if ( *(_QWORD *)v12 )
      {
        v5 = -1073740024;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v18, "VidDeleteResourcePartition");
          tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          v15 = 2008;
          v20 = &v15;
          v21 = 4;
          v22 = v16;
          v16[0] = -1073740024;
          v24 = v9 + 8;
          v23 = 4;
          v25 = 16;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400483C1, 0, 0, 7, v17);
        }
        v9 = 0;
      }
      else
      {
        RtlRbRemoveNode(v8 + 8, v12 + 32);
        if ( (unsigned int)dword_140065110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v18, "VidDeleteResourcePartition");
          tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          v21 = v13;
          v20 = &v15;
          v15 = 2020;
          v22 = a1;
          v23 = 16;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140048416, 0, 0, 6, v17);
        }
        v5 = 0;
      }
      goto LABEL_21;
    }
    v5 = -1073741275;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v18, "VidDeleteResourcePartition");
      tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v15 = 1993;
      v20 = &v15;
      v10 = &unk_1400484B4;
      v11 = v16;
      v16[0] = -1073741275;
      goto LABEL_7;
    }
  }
LABEL_21:
  VidPushLockRelease(v8);
  VidLockRelease(v7);
  if ( v9 )
    VidResourcePartitionpFree(v9);
  return v5;
}

```

## disassembly

```asm
0x140093000  mov     [rsp-8+arg_8], rbx
0x140093005  mov     [rsp-8+arg_10], rsi
0x14009300a  push    rbp
0x14009300b  push    rdi
0x14009300c  push    r12
0x14009300e  push    r14
0x140093010  push    r15
0x140093012  lea     rbp, [rsp-37h]
0x140093017  sub     rsp, 0C0h
0x14009301e  mov     rax, cs:__security_cookie
0x140093025  xor     rax, rsp
0x140093028  mov     [rbp+57h+var_30], rax
0x14009302c  xor     r12d, r12d
0x14009302f  mov     r14, rcx
0x140093032  test    rdx, rdx
0x140093035  jz      short loc_14009305D
0x140093037  mov     edi, 0C000000Dh
0x14009303c  mov     r9d, edi
0x14009303f  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093046  mov     r8d, 7A7h
0x14009304c  lea     rcx, aViddeleteresou; "VidDeleteResourcePartition"
0x140093053  call    VidTraceErrorStatusInternal0
0x140093058  jmp     loc_14009334E
0x14009305d  mov     rbx, cs:VidDeviceExtension
0x140093064  lea     r15, [rbx+668h]
0x14009306b  mov     rcx, r15
0x14009306e  lea     rsi, [rbx+898h]
0x140093075  call    VidLockAcquireShared
0x14009307a  mov     rcx, rsi
0x14009307d  call    VidPushLockAcquireExclusive
0x140093082  cmp     [rbx+664h], r12d
0x140093089  jz      loc_140093144
0x14009308f  mov     eax, cs:dword_140065110
0x140093095  mov     rbx, r12
0x140093098  mov     edi, 0C0000184h
0x14009309d  cmp     eax, 2
0x1400930a0  jbe     loc_140093331
0x1400930a6  mov     edx, 100h
0x1400930ab  lea     rcx, dword_140065110
0x1400930b2  call    _tlgKeywordOn
0x1400930b7  test    al, al
0x1400930b9  jz      loc_140093331
0x1400930bf  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x1400930c6  lea     rcx, [rbp+57h+var_80]
0x1400930ca  call    _tlgCreate1Sz_char
0x1400930cf  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400930d6  lea     rcx, [rbp+57h+var_70]
0x1400930da  call    _tlgCreate1Sz_char
0x1400930df  lea     rax, [rbp+57h+var_AC]
0x1400930e3  mov     [rbp+57h+var_AC], 7B9h
0x1400930ea  mov     [rbp+57h+var_60], rax
0x1400930ee  lea     rdx, unk_140048460
0x1400930f5  lea     rax, [rbp+57h+var_B0]
0x1400930f9  mov     [rbp+57h+var_B0], edi
0x1400930fc  mov     [rbp+57h+var_50], rax
0x140093100  lea     rcx, dword_140065110
0x140093107  lea     rax, [rbp+57h+var_A0]
0x14009310b  mov     [rbp+57h+var_38], 10h
0x140093113  mov     [rsp+0E0h+var_B8], rax
0x140093118  xor     r9d, r9d
0x14009311b  xor     r8d, r8d
0x14009311e  mov     [rsp+0E0h+var_C0], 7
0x140093126  mov     [rbp+57h+var_40], r14
0x14009312a  mov     [rbp+57h+var_48], 4
0x140093132  mov     [rbp+57h+var_58], 4
0x14009313a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009313f  jmp     loc_140093331
0x140093144  mov     rdx, r14
0x140093147  mov     rcx, rsi
0x14009314a  call    VidResourcePartitionFindById
0x14009314f  mov     rbx, rax
0x140093152  test    rax, rax
0x140093155  jnz     short loc_1400931C6
0x140093157  mov     eax, cs:dword_140065110
0x14009315d  mov     edi, 0C0000225h
0x140093162  cmp     eax, 2
0x140093165  jbe     loc_140093331
0x14009316b  mov     edx, 100h
0x140093170  lea     rcx, dword_140065110
0x140093177  call    _tlgKeywordOn
0x14009317c  test    al, al
0x14009317e  jz      loc_140093331
0x140093184  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x14009318b  lea     rcx, [rbp+57h+var_80]
0x14009318f  call    _tlgCreate1Sz_char
0x140093194  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009319b  lea     rcx, [rbp+57h+var_70]
0x14009319f  call    _tlgCreate1Sz_char
0x1400931a4  lea     rax, [rbp+57h+var_B0]
0x1400931a8  mov     [rbp+57h+var_B0], 7C9h
0x1400931af  mov     [rbp+57h+var_60], rax
0x1400931b3  lea     rdx, unk_1400484B4
0x1400931ba  lea     rax, [rbp+57h+var_AC]
0x1400931be  mov     [rbp+57h+var_AC], edi
0x1400931c1  jmp     loc_1400930FC
0x1400931c6  mov     rax, [rax]
0x1400931c9  test    rax, rax
0x1400931cc  jz      loc_14009328B
0x1400931d2  mov     eax, cs:dword_140065110
0x1400931d8  mov     edi, 0C0000708h
0x1400931dd  cmp     eax, 2
0x1400931e0  jbe     loc_140093283
0x1400931e6  mov     edx, 100h
0x1400931eb  lea     rcx, dword_140065110
0x1400931f2  call    _tlgKeywordOn
0x1400931f7  test    al, al
0x1400931f9  jz      loc_140093283
0x1400931ff  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x140093206  lea     rcx, [rbp+57h+var_80]
0x14009320a  call    _tlgCreate1Sz_char
0x14009320f  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093216  lea     rcx, [rbp+57h+var_70]
0x14009321a  call    _tlgCreate1Sz_char
0x14009321f  lea     rax, [rbp+57h+var_B0]
0x140093223  mov     [rbp+57h+var_B0], 7D8h
0x14009322a  mov     [rbp+57h+var_60], rax
0x14009322e  lea     rdx, unk_1400483C1
0x140093235  lea     rax, [rbp+57h+var_AC]
0x140093239  mov     [rbp+57h+var_58], 4
0x140093241  mov     [rbp+57h+var_50], rax
0x140093245  lea     rcx, dword_140065110
0x14009324c  lea     rax, [rbx+8]
0x140093250  mov     [rbp+57h+var_AC], edi
0x140093253  mov     [rbp+57h+var_40], rax
0x140093257  xor     r9d, r9d
0x14009325a  lea     rax, [rbp+57h+var_A0]
0x14009325e  mov     [rbp+57h+var_48], 4
0x140093266  mov     [rsp+0E0h+var_B8], rax
0x14009326b  xor     r8d, r8d
0x14009326e  mov     [rsp+0E0h+var_C0], 7
0x140093276  mov     [rbp+57h+var_38], 10h
0x14009327e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140093283  mov     rbx, r12
0x140093286  jmp     loc_140093331
0x14009328b  lea     rdx, [rbx+20h]
0x14009328f  lea     rcx, [rsi+8]
0x140093293  call    cs:__imp_RtlRbRemoveNode
0x14009329a  nop     dword ptr [rax+rax+00h]
0x14009329f  mov     eax, cs:dword_140065110
0x1400932a5  mov     r8d, 4
0x1400932ab  cmp     eax, r8d
0x1400932ae  jbe     short loc_14009332E
0x1400932b0  mov     edx, 100h
0x1400932b5  lea     rcx, dword_140065110
0x1400932bc  call    _tlgKeywordOn
0x1400932c1  test    al, al
0x1400932c3  jz      short loc_14009332E
0x1400932c5  lea     rdx, aViddeleteresou; "VidDeleteResourcePartition"
0x1400932cc  lea     rcx, [rbp+57h+var_80]
0x1400932d0  call    _tlgCreate1Sz_char
0x1400932d5  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400932dc  lea     rcx, [rbp+57h+var_70]
0x1400932e0  call    _tlgCreate1Sz_char
0x1400932e5  lea     rax, [rbp+57h+var_B0]
0x1400932e9  mov     [rbp+57h+var_58], r8
0x1400932ed  mov     [rbp+57h+var_60], rax
0x1400932f1  lea     rdx, unk_140048416
0x1400932f8  lea     rax, [rbp+57h+var_A0]
0x1400932fc  mov     [rbp+57h+var_B0], 7E4h
0x140093303  mov     [rsp+0E0h+var_B8], rax
0x140093308  lea     rcx, dword_140065110
0x14009330f  xor     r9d, r9d
0x140093312  mov     [rsp+0E0h+var_C0], 6
0x14009331a  xor     r8d, r8d
0x14009331d  mov     [rbp+57h+var_50], r14
0x140093321  mov     [rbp+57h+var_48], 10h
0x140093329  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009332e  mov     edi, r12d
0x140093331  mov     rcx, rsi
0x140093334  call    VidPushLockRelease
0x140093339  mov     rcx, r15
0x14009333c  call    VidLockRelease
0x140093341  test    rbx, rbx
0x140093344  jz      short loc_14009334E
0x140093346  mov     rcx, rbx; P
0x140093349  call    VidResourcePartitionpFree
0x14009334e  mov     eax, edi
0x140093350  mov     rcx, [rbp+57h+var_30]
0x140093354  xor     rcx, rsp; StackCookie
0x140093357  call    __security_check_cookie
0x14009335c  lea     r11, [rsp+0E0h+var_20]
0x140093364  mov     rbx, [r11+38h]
0x140093368  mov     rsi, [r11+40h]
0x14009336c  mov     rsp, r11
0x14009336f  pop     r15
0x140093371  pop     r14
0x140093373  pop     r12
0x140093375  pop     rdi
0x140093376  pop     rbp
0x140093377  retn
```
