# SpatialDecParseSpecificConfig(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE)

- ea: `0x18007d4f4`
- end: `0x18007d755`
- name: `?SpatialDecParseSpecificConfig@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@@Z`
- size: `609`
- prototype: `enum SACDEC_ERROR __high(struct CDK_BITSTREAM *, struct T_SPATIAL_SPECIFIC_CONFIG *, int, enum AUDIO_OBJECT_TYPE)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800723b4`
- `0x18007d75c`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x18002ce0c`
- `0x18004dd14`
- `0x18007c55c`
- `0x18007ca70`
- `0x18007cb98`
- `0x18007d4f4`

## pseudocode

```c
__int64 __fastcall SpatialDecParseSpecificConfig(int *a1, _DWORD *a2, int a3, int a4)
{
  __int64 v8; // r8
  unsigned int v9; // ebp
  int v10; // r14d
  int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  unsigned int v18; // ebx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // r8
  int i; // ecx
  __int64 v27; // rax
  int j; // r15d
  int v29; // ebx
  __int64 v30; // r8
  int v31; // r8d
  int v32; // r9d

  memset_0(a2, 0, 0xC0u);
  CDKsyncCache_0(a1);
  v9 = a1[2];
  if ( a3 )
  {
    v10 = 8 * a3;
    if ( 8 * a3 > (int)v9 )
      goto LABEL_23;
  }
  else
  {
    v10 = a1[2];
  }
  v11 = CDKreadBits(a1, 4, v8);
  if ( v11 == 15 )
  {
    a2[1] = CDKreadBits(a1, 24, v12);
  }
  else
  {
    v13 = *((_DWORD *)&samplingFreqTable + v11);
    a2[1] = v13;
    if ( !v13 )
      goto LABEL_23;
  }
  v14 = CDKreadBits(a1, 5, v12) + 1;
  a2[2] = v14;
  if ( (unsigned int)(v14 - 1) > 0x3F )
    goto LABEL_23;
  a2[3] = *((unsigned __int8 *)&freqResTable_LD + (int)CDKreadBits(a1, 3, v15));
  if ( (unsigned int)CDKreadBits(a1, 4, v16) == 7 )
  {
    a2[4] = 7;
    a2[13] = 1;
    a2[19] = 0;
    a2[11] = 1;
    a2[12] = 2;
    a2[5] = CDKreadBits(a1, 2, v17);
    a2[6] = CDKreadBits(a1, 1, v19);
    a2[8] = CDKreadBits(a1, 3, v20);
    v22 = CDKreadBits(a1, 2, v21);
    a2[9] = v22;
    if ( v22 > 2 )
      return 4294966314LL;
    v24 = CDKreadBits(a1, 2, v23);
    a2[10] = v24;
    if ( v24 > 2 )
      return 4294966314LL;
    for ( i = 0; i < a2[13]; a2[v27 + 14] = 0 )
      v27 = i++;
    for ( j = 0; j < a2[19]; ++j )
    {
      v29 = CDKreadBits(a1, 1, v25);
      CDKreadBits(a1, 3, v30);
      if ( v29 )
        CDKreadBits(a1, 8, v25);
    }
    if ( a2[9] == 2 )
      a2[39] = CDKreadBits(a1, 1, v25);
    CDKbyteAlign_0(a1, v9);
    CDKsyncCache_0(a1);
    if ( (int)(v10 - v9 + a1[2]) >= 0 )
    {
      a2[30] = 0;
      a2[7] = 0;
      v18 = SpatialDecParseExtensionConfig((_DWORD)a1, (_DWORD)a2, v31, v32);
      CDKbyteAlign_0(a1, v9);
      a2[40] = a4;
      SpatialDecDecodeHelperInfo(a2);
      goto LABEL_24;
    }
LABEL_23:
    v18 = -982;
    goto LABEL_24;
  }
  v18 = -983;
LABEL_24:
  if ( a3 > 0 )
  {
    CDKsyncCache_0(a1);
    CDKpushBiDirectional_0(a1, a1[2] + 8 * a3 - v9);
  }
  return v18;
}

```

## disassembly

```asm
0x18007d4f4  push    rbx
0x18007d4f6  push    rbp
0x18007d4f7  push    rsi
0x18007d4f8  push    rdi
0x18007d4f9  push    r12
0x18007d4fb  push    r13
0x18007d4fd  push    r14
0x18007d4ff  push    r15
0x18007d501  sub     rsp, 38h
0x18007d505  mov     rsi, rdx
0x18007d508  mov     r12d, r8d
0x18007d50b  mov     rdi, rcx
0x18007d50e  xor     edx, edx; Val
0x18007d510  mov     rcx, rsi; void *
0x18007d513  mov     r8d, 0C0h; Size
0x18007d519  mov     r13d, r9d
0x18007d51c  call    memset_0
0x18007d521  mov     rcx, rdi
0x18007d524  call    CDKsyncCache_0
0x18007d529  mov     ebp, [rdi+8]
0x18007d52c  xor     ebx, ebx
0x18007d52e  test    r12d, r12d
0x18007d531  jnz     short loc_18007D538
0x18007d533  mov     r14d, ebp
0x18007d536  jmp     short loc_18007D549
0x18007d538  lea     r14d, ds:0[r12*8]
0x18007d540  cmp     r14d, ebp
0x18007d543  jg      loc_18007D71A
0x18007d549  mov     edx, 4
0x18007d54e  mov     rcx, rdi
0x18007d551  call    CDKreadBits
0x18007d556  lea     r15, __ImageBase
0x18007d55d  cmp     eax, 0Fh
0x18007d560  jnz     short loc_18007D572
0x18007d562  lea     edx, [rax+9]
0x18007d565  mov     rcx, rdi
0x18007d568  call    CDKreadBits
0x18007d56d  mov     [rsi+4], eax
0x18007d570  jmp     short loc_18007D587
0x18007d572  cdqe
0x18007d574  mov     eax, ds:rva ?samplingFreqTable@@3QBHB[r15+rax*4]; int const near * const samplingFreqTable ...
0x18007d57c  mov     [rsi+4], eax
0x18007d57f  test    eax, eax
0x18007d581  jz      loc_18007D71A
0x18007d587  mov     edx, 5
0x18007d58c  mov     rcx, rdi
0x18007d58f  call    CDKreadBits
0x18007d594  inc     eax
0x18007d596  mov     [rsi+8], eax
0x18007d599  dec     eax
0x18007d59b  cmp     eax, 3Fh ; '?'
0x18007d59e  ja      loc_18007D71A
0x18007d5a4  mov     edx, 3
0x18007d5a9  mov     rcx, rdi
0x18007d5ac  call    CDKreadBits
0x18007d5b1  movsxd  rcx, eax
0x18007d5b4  mov     edx, 4
0x18007d5b9  movzx   eax, byte ptr [rcx+r15+0D0D28h]
0x18007d5c2  mov     rcx, rdi
0x18007d5c5  mov     [rsi+0Ch], eax
0x18007d5c8  call    CDKreadBits
0x18007d5cd  cmp     eax, 7
0x18007d5d0  jz      short loc_18007D5DC
0x18007d5d2  mov     ebx, 0FFFFFC29h
0x18007d5d7  jmp     loc_18007D71F
0x18007d5dc  mov     r15d, 1
0x18007d5e2  mov     dword ptr [rsi+10h], 7
0x18007d5e9  mov     rcx, rdi
0x18007d5ec  mov     [rsi+34h], r15d
0x18007d5f0  mov     [rsi+4Ch], ebx
0x18007d5f3  mov     [rsi+2Ch], r15d
0x18007d5f7  lea     eax, [r15+1]
0x18007d5fb  mov     edx, eax
0x18007d5fd  mov     [rsi+30h], eax
0x18007d600  call    CDKreadBits
0x18007d605  mov     edx, r15d
0x18007d608  mov     [rsi+14h], eax
0x18007d60b  mov     rcx, rdi
0x18007d60e  call    CDKreadBits
0x18007d613  lea     edx, [r15+2]
0x18007d617  mov     [rsi+18h], eax
0x18007d61a  mov     rcx, rdi
0x18007d61d  call    CDKreadBits
0x18007d622  lea     edx, [r15+1]
0x18007d626  mov     [rsi+20h], eax
0x18007d629  mov     rcx, rdi
0x18007d62c  call    CDKreadBits
0x18007d631  mov     [rsi+24h], eax
0x18007d634  cmp     eax, 2
0x18007d637  jg      loc_18007D713
0x18007d63d  lea     edx, [r15+1]
0x18007d641  mov     rcx, rdi
0x18007d644  call    CDKreadBits
0x18007d649  mov     [rsi+28h], eax
0x18007d64c  cmp     eax, 2
0x18007d64f  jg      loc_18007D713
0x18007d655  mov     ecx, ebx
0x18007d657  cmp     [rsi+34h], ebx
0x18007d65a  jle     short loc_18007D66B
0x18007d65c  movsxd  rax, ecx
0x18007d65f  add     ecx, r15d
0x18007d662  mov     [rsi+rax*4+38h], ebx
0x18007d666  cmp     ecx, [rsi+34h]
0x18007d669  jl      short loc_18007D65C
0x18007d66b  mov     r15d, ebx
0x18007d66e  cmp     [rsi+4Ch], ebx
0x18007d671  jle     short loc_18007D6AB
0x18007d673  mov     edx, 1
0x18007d678  mov     rcx, rdi
0x18007d67b  call    CDKreadBits
0x18007d680  mov     edx, 3
0x18007d685  mov     rcx, rdi
0x18007d688  mov     ebx, eax
0x18007d68a  call    CDKreadBits
0x18007d68f  test    ebx, ebx
0x18007d691  jz      short loc_18007D6A0
0x18007d693  mov     edx, 8
0x18007d698  mov     rcx, rdi
0x18007d69b  call    CDKreadBits
0x18007d6a0  inc     r15d
0x18007d6a3  cmp     r15d, [rsi+4Ch]
0x18007d6a7  jl      short loc_18007D673
0x18007d6a9  xor     ebx, ebx
0x18007d6ab  cmp     dword ptr [rsi+24h], 2
0x18007d6af  jnz     short loc_18007D6C4
0x18007d6b1  mov     edx, 1
0x18007d6b6  mov     rcx, rdi
0x18007d6b9  call    CDKreadBits
0x18007d6be  mov     [rsi+9Ch], eax
0x18007d6c4  mov     edx, ebp
0x18007d6c6  mov     rcx, rdi
0x18007d6c9  call    CDKbyteAlign_0
0x18007d6ce  mov     rcx, rdi
0x18007d6d1  call    CDKsyncCache_0
0x18007d6d6  mov     ecx, [rdi+8]
0x18007d6d9  sub     r14d, ebp
0x18007d6dc  add     ecx, r14d
0x18007d6df  js      short loc_18007D71A
0x18007d6e1  mov     [rsp+78h+var_50], ecx
0x18007d6e5  mov     rdx, rsi
0x18007d6e8  mov     rcx, rdi
0x18007d6eb  mov     [rsi+78h], ebx
0x18007d6ee  mov     [rsi+1Ch], ebx
0x18007d6f1  call    SpatialDecParseExtensionConfig
0x18007d6f6  mov     edx, ebp
0x18007d6f8  mov     rcx, rdi
0x18007d6fb  mov     ebx, eax
0x18007d6fd  call    CDKbyteAlign_0
0x18007d702  mov     rcx, rsi
0x18007d705  mov     [rsi+0A0h], r13d
0x18007d70c  call    SpatialDecDecodeHelperInfo
0x18007d711  jmp     short loc_18007D71F
0x18007d713  mov     eax, 0FFFFFC2Ah
0x18007d718  jmp     short loc_18007D743
0x18007d71a  mov     ebx, 0FFFFFC2Ah
0x18007d71f  test    r12d, r12d
0x18007d722  jle     short loc_18007D741
0x18007d724  mov     rcx, rdi
0x18007d727  call    CDKsyncCache_0
0x18007d72c  lea     edx, ds:0[r12*8]
0x18007d734  mov     rcx, rdi
0x18007d737  sub     edx, ebp
0x18007d739  add     edx, [rdi+8]
0x18007d73c  call    CDKpushBiDirectional_0
0x18007d741  mov     eax, ebx
0x18007d743  add     rsp, 38h
0x18007d747  pop     r15
0x18007d749  pop     r14
0x18007d74b  pop     r13
0x18007d74d  pop     r12
0x18007d74f  pop     rdi
0x18007d750  pop     rsi
0x18007d751  pop     rbp
0x18007d752  pop     rbx
0x18007d753  retn
```
