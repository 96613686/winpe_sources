# EldSpecificConfig_Parse

- ea: `0x1800793b8`
- end: `0x18007977c`
- name: `EldSpecificConfig_Parse`
- size: `964`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180011da8`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x180012580`
- `0x180012768`
- `0x1800793b8`
- `0x18007a300`
- `0x18007a444`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall EldSpecificConfig_Parse(__int64 a1, int *a2, __int64 a3)
{
  int v4; // r14d
  int v7; // ebp
  char v8; // al
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // r8
  _DWORD *v15; // r15
  __int64 v16; // r8
  char v17; // al
  char v18; // cl
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int i; // esi
  int v27; // r12d
  __int64 v28; // r8
  int v29; // r13d
  int v30; // r14d
  __int64 v31; // r8
  int v32; // esi
  int v33; // eax
  int v34; // r14d
  int SampleRate; // eax
  __int64 v36; // r8
  __int64 v37; // r11
  unsigned int (__fastcall *v38)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, int, int, __int64); // rax
  int j; // r14d
  int v40; // esi
  int v41; // eax
  unsigned int v43; // r13d
  int v44; // [rsp+48h] [rbp-50h]
  int v45; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v46; // [rsp+B0h] [rbp+18h]
  int v47; // [rsp+B8h] [rbp+20h]

  v46 = a3;
  *(_QWORD *)a1 = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  v47 = 0;
  v7 = 0;
  v8 = CDKreadBits(a2, 1, a3);
  *(_BYTE *)a1 = v8;
  *(_DWORD *)(a1 + 1208) = v8 != 0 ? 480 : 512;
  *(_BYTE *)(a1 + 1226) = CDKreadBits(a2, 1, v9);
  *(_BYTE *)(a1 + 1227) = CDKreadBits(a2, 1, v10);
  *(_BYTE *)(a1 + 1228) = CDKreadBits(a2, 1, v11);
  v13 = CDKreadBits(a2, 1, v12);
  *(_BYTE *)(a1 + 1) = v13;
  v15 = (_DWORD *)(a1 + 1204);
  if ( v13 != 1 )
    goto LABEL_20;
  *(_BYTE *)(a1 + 3) = CDKreadBits(a2, 1, v14);
  v17 = CDKreadBits(a2, 1, v16);
  v18 = *(_BYTE *)(a1 + 3);
  *(_BYTE *)(a1 + 4) = v17;
  *(_DWORD *)(a1 + 1220) = *v15 << v18;
  if ( !*(_QWORD *)(a3 + 80) )
    return 1026;
  v19 = *(char *)(a1 + 1224);
  if ( v19 > 6 )
  {
    v23 = v19 - 7;
    if ( v23 )
    {
      v24 = v23 - 4;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          if ( v25 != 2 )
            goto LABEL_20;
        }
      }
    }
    v7 = 4;
    goto LABEL_17;
  }
  if ( v19 == 6 )
    goto LABEL_9;
  v20 = v19 - 1;
  if ( !v20 || (v21 = v20 - 1) == 0 )
  {
    v7 = 1;
LABEL_17:
    for ( i = 0; i < v7; ++i )
      v4 += skipSbrHeader(a2, 0);
    v47 = v4;
    goto LABEL_20;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v7 = 2;
    goto LABEL_17;
  }
  if ( (unsigned int)(v22 - 1) <= 1 )
  {
LABEL_9:
    v7 = 3;
    goto LABEL_17;
  }
LABEL_20:
  v27 = 0;
  v45 = 0;
  *(_BYTE *)(a1 + 2) = 0;
  CDKsyncCache_0(a2);
  v29 = a2[2];
  *(_DWORD *)(a1 + 8) = *v15;
  while ( 1 )
  {
    v30 = CDKreadBits(a2, 4, v28);
    if ( !v30 )
      break;
    CDKsyncCache_0(a2);
    if ( a2[2] < 0 || v27 >= 15 )
      return 1025;
    v32 = CDKreadBits(a2, 4, v31);
    if ( v32 == 15 )
    {
      v33 = CDKreadBits(a2, 8, v28);
      if ( v33 == 255 )
        v32 = CDKreadBits(a2, (unsigned int)(v32 + 1), v28) + 270;
      else
        v32 = v33 + 15;
      v27 = v45;
    }
    v34 = v30 - 2;
    if ( v34 )
    {
      if ( v34 != 1 )
        goto LABEL_39;
      SampleRate = getSampleRate(a2, &v45, 4);
      *(_DWORD *)(a1 + 8) = SampleRate;
      if ( (unsigned int)(SampleRate - 1) > 0x176FF || (unsigned __int8)CDKreadBits(a2, 4, v36) )
        return 1025;
      if ( *(_BYTE *)(a1 + 2) == 1 )
        return 1026;
    }
    else
    {
      v37 = v46;
      *(_BYTE *)(a1 + 2) = 1;
      v38 = *(unsigned int (__fastcall **)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, int, int, __int64))(v37 + 64);
      if ( !v38 )
      {
LABEL_39:
        for ( j = 0; j < v32; ++j )
          CDKreadBits(a2, 8, v28);
        goto LABEL_41;
      }
      LOBYTE(v44) = *(_BYTE *)(a1 + 1234);
      if ( v38(
             *(_QWORD *)(v37 + 72),
             a2,
             *(unsigned int *)(a1 + 1200),
             (unsigned int)(*v15 << *(_BYTE *)(a1 + 3)),
             *(_DWORD *)(a1 + 1208) << *(_BYTE *)(a1 + 3),
             *(char *)(a1 + 1224),
             1,
             -1,
             v32,
             v44,
             a1 + 1237) )
      {
        return 1025;
      }
      if ( *(_DWORD *)(a1 + 8) != *v15 )
        return 1026;
    }
LABEL_41:
    v45 = ++v27;
  }
  CDKsyncCache_0(a2);
  if ( a2[2] >= 0 )
  {
    if ( *(_BYTE *)(a1 + 1) != 1 || !v7 )
      return 0;
    v40 = 1;
    if ( *(_DWORD *)(a1 + 8) )
    {
      v41 = *v15 / *(_DWORD *)(a1 + 8);
      v40 = v41;
      if ( *v15 % *(_DWORD *)(a1 + 8) )
        return 1026;
      if ( v41 != 1 )
      {
        if ( (v41 & 1) != 0 )
          return 1026;
        if ( ((v41 - 2) & 0xFFFFFFFD) != 0 )
          v40 = 1;
      }
      if ( *(_DWORD *)(a1 + 1208) % v40 )
        return 1026;
    }
    CDKsyncCache_0(a2);
    v43 = v29 - a2[2];
    CDKpushBack_0(a2, v43 + v47);
    if ( !(unsigned int)ld_sbr_header(a1, (unsigned int)v40, a2, v46) )
    {
      CDKpushFor(a2, v43);
      return 0;
    }
  }
  return 1025;
}

```

## disassembly

```asm
0x1800793b8  mov     [rsp+arg_8], rbx
0x1800793bd  mov     [rsp+arg_10], r8
0x1800793c2  push    rbp
0x1800793c3  push    rsi
0x1800793c4  push    rdi
0x1800793c5  push    r12
0x1800793c7  push    r13
0x1800793c9  push    r14
0x1800793cb  push    r15
0x1800793cd  sub     rsp, 60h
0x1800793d1  xor     eax, eax
0x1800793d3  mov     rbx, rdx
0x1800793d6  mov     [rcx], rax
0x1800793d9  xor     r14d, r14d
0x1800793dc  mov     rdi, rcx
0x1800793df  mov     [rcx+8], eax
0x1800793e2  mov     rcx, rbx
0x1800793e5  mov     [rsp+98h+arg_18], r14d
0x1800793ed  mov     rsi, r8
0x1800793f0  xor     ebp, ebp
0x1800793f2  lea     r12d, [r14+1]
0x1800793f6  mov     edx, r12d
0x1800793f9  call    CDKreadBits
0x1800793fe  mov     [rdi], al
0x180079400  mov     edx, r12d
0x180079403  neg     al
0x180079405  mov     rcx, rbx
0x180079408  sbb     eax, eax
0x18007940a  and     eax, 0FFFFFFE0h
0x18007940d  add     eax, 200h
0x180079412  mov     [rdi+4B8h], eax
0x180079418  call    CDKreadBits
0x18007941d  mov     edx, r12d
0x180079420  mov     [rdi+4CAh], al
0x180079426  mov     rcx, rbx
0x180079429  call    CDKreadBits
0x18007942e  mov     edx, r12d
0x180079431  mov     [rdi+4CBh], al
0x180079437  mov     rcx, rbx
0x18007943a  call    CDKreadBits
0x18007943f  mov     edx, r12d
0x180079442  mov     [rdi+4CCh], al
0x180079448  mov     rcx, rbx
0x18007944b  call    CDKreadBits
0x180079450  mov     [rdi+1], al
0x180079453  lea     r15, [rdi+4B4h]
0x18007945a  cmp     al, r12b
0x18007945d  jnz     loc_180079508
0x180079463  mov     edx, r12d
0x180079466  mov     rcx, rbx
0x180079469  call    CDKreadBits
0x18007946e  mov     edx, r12d
0x180079471  mov     [rdi+3], al
0x180079474  mov     rcx, rbx
0x180079477  call    CDKreadBits
0x18007947c  mov     cl, [rdi+3]
0x18007947f  mov     [rdi+4], al
0x180079482  mov     eax, [r15]
0x180079485  shl     eax, cl
0x180079487  mov     [rdi+4C4h], eax
0x18007948d  cmp     [rsi+50h], rbp
0x180079491  jz      loc_180079711
0x180079497  movsx   ecx, byte ptr [rdi+4C8h]
0x18007949e  cmp     ecx, 6
0x1800794a1  jg      short loc_1800794D1
0x1800794a3  jz      short loc_1800794BE
0x1800794a5  sub     ecx, r12d
0x1800794a8  jz      short loc_1800794CC
0x1800794aa  sub     ecx, r12d
0x1800794ad  jz      short loc_1800794CC
0x1800794af  sub     ecx, r12d
0x1800794b2  jz      short loc_1800794C5
0x1800794b4  sub     ecx, r12d
0x1800794b7  jz      short loc_1800794BE
0x1800794b9  cmp     ecx, r12d
0x1800794bc  jnz     short loc_180079508
0x1800794be  mov     ebp, 3
0x1800794c3  jmp     short loc_1800794EA
0x1800794c5  mov     ebp, 2
0x1800794ca  jmp     short loc_1800794EA
0x1800794cc  mov     ebp, r12d
0x1800794cf  jmp     short loc_1800794EA
0x1800794d1  sub     ecx, 7
0x1800794d4  jz      short loc_1800794E5
0x1800794d6  sub     ecx, 4
0x1800794d9  jz      short loc_1800794E5
0x1800794db  sub     ecx, r12d
0x1800794de  jz      short loc_1800794E5
0x1800794e0  cmp     ecx, 2
0x1800794e3  jnz     short loc_180079508
0x1800794e5  mov     ebp, 4
0x1800794ea  xor     esi, esi
0x1800794ec  xor     edx, edx
0x1800794ee  mov     rcx, rbx
0x1800794f1  call    skipSbrHeader
0x1800794f6  add     r14d, eax
0x1800794f9  add     esi, r12d
0x1800794fc  cmp     esi, ebp
0x1800794fe  jl      short loc_1800794EC
0x180079500  mov     [rsp+98h+arg_18], r14d
0x180079508  xor     r12d, r12d
0x18007950b  mov     rcx, rbx
0x18007950e  mov     [rsp+98h+arg_0], r12d
0x180079516  mov     [rdi+2], r12b
0x18007951a  call    CDKsyncCache_0
0x18007951f  mov     eax, [r15]
0x180079522  mov     r13d, [rbx+8]
0x180079526  mov     [rdi+8], eax
0x180079529  mov     edx, 4
0x18007952e  mov     rcx, rbx
0x180079531  call    CDKreadBits
0x180079536  mov     r14d, eax
0x180079539  mov     rcx, rbx
0x18007953c  test    eax, eax
0x18007953e  jz      loc_1800796B5
0x180079544  call    CDKsyncCache_0
0x180079549  cmp     dword ptr [rbx+8], 0
0x18007954d  jl      loc_18007975E
0x180079553  cmp     r12d, 0Fh
0x180079557  jge     loc_18007975E
0x18007955d  mov     edx, 4
0x180079562  mov     rcx, rbx
0x180079565  call    CDKreadBits
0x18007956a  mov     esi, eax
0x18007956c  cmp     eax, 0Fh
0x18007956f  jnz     short loc_1800795A3
0x180079571  lea     edx, [rax-7]
0x180079574  mov     rcx, rbx
0x180079577  call    CDKreadBits
0x18007957c  lea     r12d, [rax+rsi]
0x180079580  cmp     eax, 0FFh
0x180079585  jnz     short loc_180079598
0x180079587  lea     edx, [rsi+1]
0x18007958a  mov     rcx, rbx
0x18007958d  call    CDKreadBits
0x180079592  lea     esi, [r12+rax]
0x180079596  jmp     short loc_18007959B
0x180079598  mov     esi, r12d
0x18007959b  mov     r12d, [rsp+98h+arg_0]
0x1800795a3  sub     r14d, 2
0x1800795a7  jz      short loc_1800795FA
0x1800795a9  cmp     r14d, 1
0x1800795ad  jnz     loc_180079689
0x1800795b3  lea     r8d, [r14+3]
0x1800795b7  mov     rcx, rbx
0x1800795ba  lea     rdx, [rsp+98h+arg_0]
0x1800795c2  call    getSampleRate
0x1800795c7  mov     [rdi+8], eax
0x1800795ca  dec     eax
0x1800795cc  cmp     eax, 176FFh
0x1800795d1  ja      loc_18007975E
0x1800795d7  lea     edx, [r14+3]
0x1800795db  mov     rcx, rbx
0x1800795de  call    CDKreadBits
0x1800795e3  test    al, al
0x1800795e5  jnz     loc_18007975E
0x1800795eb  cmp     [rdi+2], r14b
0x1800795ef  jz      loc_180079711
0x1800795f5  jmp     loc_1800796A5
0x1800795fa  mov     r11, [rsp+98h+arg_10]
0x180079602  mov     byte ptr [rdi+2], 1
0x180079606  mov     rax, [r11+40h]
0x18007960a  test    rax, rax
0x18007960d  jz      short loc_180079689
0x18007960f  movzx   ecx, byte ptr [rdi+3]
0x180079613  lea     rdx, [rdi+4D5h]
0x18007961a  mov     r8d, [rdi+4B8h]
0x180079621  mov     r9d, [r15]
0x180079624  movsx   r10d, byte ptr [rdi+4C8h]
0x18007962c  mov     [rsp+98h+var_48], rdx
0x180079631  mov     rdx, rbx
0x180079634  shl     r8d, cl
0x180079637  shl     r9d, cl
0x18007963a  mov     cl, [rdi+4D2h]
0x180079640  mov     [rsp+98h+var_50], cl
0x180079644  mov     rcx, [r11+48h]
0x180079648  mov     [rsp+98h+var_58], esi
0x18007964c  mov     [rsp+98h+var_60], 0FFFFFFFFh
0x180079654  mov     [rsp+98h+var_68], 1
0x18007965c  mov     [rsp+98h+var_70], r10d
0x180079661  mov     [rsp+98h+var_78], r8d
0x180079666  mov     r8d, [rdi+4B0h]
0x18007966d  call    cs:__guard_dispatch_icall_fptr
0x180079673  test    eax, eax
0x180079675  jnz     loc_18007975E
0x18007967b  mov     eax, [r15]
0x18007967e  cmp     [rdi+8], eax
0x180079681  jnz     loc_180079711
0x180079687  jmp     short loc_1800796A5
0x180079689  xor     r14d, r14d
0x18007968c  test    esi, esi
0x18007968e  jle     short loc_1800796A5
0x180079690  mov     edx, 8
0x180079695  mov     rcx, rbx
0x180079698  call    CDKreadBits
0x18007969d  inc     r14d
0x1800796a0  cmp     r14d, esi
0x1800796a3  jl      short loc_180079690
0x1800796a5  inc     r12d
0x1800796a8  mov     [rsp+98h+arg_0], r12d
0x1800796b0  jmp     loc_180079529
0x1800796b5  call    CDKsyncCache_0
0x1800796ba  cmp     dword ptr [rbx+8], 0
0x1800796be  jl      loc_18007975E
0x1800796c4  mov     ecx, 1
0x1800796c9  cmp     [rdi+1], cl
0x1800796cc  jnz     loc_18007975A
0x1800796d2  test    ebp, ebp
0x1800796d4  jz      loc_18007975A
0x1800796da  cmp     dword ptr [rdi+8], 0
0x1800796de  mov     esi, ecx
0x1800796e0  jz      short loc_180079718
0x1800796e2  mov     eax, [r15]
0x1800796e5  xor     edx, edx
0x1800796e7  div     dword ptr [rdi+8]
0x1800796ea  mov     esi, eax
0x1800796ec  test    edx, edx
0x1800796ee  jnz     short loc_180079711
0x1800796f0  cmp     eax, ecx
0x1800796f2  jz      short loc_180079704
0x1800796f4  test    cl, sil
0x1800796f7  jnz     short loc_180079711
0x1800796f9  add     eax, 0FFFFFFFEh
0x1800796fc  test    eax, 0FFFFFFFDh
0x180079701  cmovnz  esi, ecx
0x180079704  mov     eax, [rdi+4B8h]
0x18007970a  cdq
0x18007970b  idiv    esi
0x18007970d  test    edx, edx
0x18007970f  jz      short loc_180079718
0x180079711  mov     eax, 402h
0x180079716  jmp     short loc_180079763
0x180079718  mov     rcx, rbx
0x18007971b  call    CDKsyncCache_0
0x180079720  mov     edx, [rsp+98h+arg_18]
0x180079727  mov     rcx, rbx
0x18007972a  sub     r13d, [rbx+8]
0x18007972e  add     edx, r13d
0x180079731  call    CDKpushBack_0
0x180079736  mov     r9, [rsp+98h+arg_10]
0x18007973e  mov     r8, rbx
0x180079741  mov     edx, esi
0x180079743  mov     rcx, rdi
0x180079746  call    ld_sbr_header
0x18007974b  test    eax, eax
0x18007974d  jnz     short loc_18007975E
0x18007974f  mov     edx, r13d
0x180079752  mov     rcx, rbx
0x180079755  call    CDKpushFor
0x18007975a  xor     eax, eax
0x18007975c  jmp     short loc_180079763
0x18007975e  mov     eax, 401h
0x180079763  mov     rbx, [rsp+98h+arg_8]
0x18007976b  add     rsp, 60h
0x18007976f  pop     r15
0x180079771  pop     r14
0x180079773  pop     r13
0x180079775  pop     r12
0x180079777  pop     rdi
0x180079778  pop     rsi
0x180079779  pop     rbp
0x18007977a  retn
```
