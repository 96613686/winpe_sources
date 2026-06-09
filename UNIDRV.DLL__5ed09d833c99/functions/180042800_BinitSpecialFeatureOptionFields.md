# BinitSpecialFeatureOptionFields

- ea: `0x180042800`
- end: `0x18004308a`
- name: `BinitSpecialFeatureOptionFields`
- size: `2186`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180049418`

## callees

- `0x180007150`
- `0x18000a0b0`
- `0x18000af00`
- `0x18000cdd0`
- `0x180040318`
- `0x180042700`
- `0x180042800`
- `0x180076630`

## string_xrefs

- `0x18004288a`: `RESDLL`
- `0x180043052`: `RESDLL`
- `0x180043059`: `References to ResourceDLLs must be placed in the feature with symbolname: %s.`
- `0x18004303d`: `ResourceDLL names must be declared explicitly using *Name not *rcNameID.`

## pseudocode

```c
__int64 __fastcall BinitSpecialFeatureOptionFields(__int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // r12
  unsigned int *v4; // rax
  unsigned int v5; // ecx
  __int64 v6; // r13
  __int64 v7; // r14
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rsi
  unsigned int *v11; // r15
  unsigned int v12; // r11d
  int v13; // edx
  char *v14; // rcx
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rax
  _DWORD *v18; // r13
  unsigned int v19; // esi
  unsigned int v20; // r8d
  unsigned __int64 v21; // rdx
  int v22; // r12d
  char *v23; // rcx
  int v24; // edx
  char *v25; // rcx
  void *v26; // r11
  unsigned int v27; // esi
  int v28; // ebx
  unsigned int v29; // esi
  __int64 v30; // rbx
  __int64 v31; // rbx
  __int64 v32; // r11
  __int64 v33; // rbx
  __int64 v34; // r8
  int v35; // r8d
  __int64 v36; // r11
  __int64 v37; // r8
  float v38; // xmm0_4
  int v39; // eax
  bool v40; // zf
  int v41; // eax
  int v42; // r11d
  unsigned __int64 v44; // [rsp+50h] [rbp-29h] BYREF
  int v45; // [rsp+58h] [rbp-21h] BYREF
  int v46; // [rsp+5Ch] [rbp-1Dh]
  int v47; // [rsp+60h] [rbp-19h]
  int v48; // [rsp+64h] [rbp-15h]
  int v49; // [rsp+68h] [rbp-11h] BYREF
  int v50; // [rsp+6Ch] [rbp-Dh]
  __int64 v51; // [rsp+70h] [rbp-9h]
  __int64 v52; // [rsp+78h] [rbp-1h]
  __int64 v53; // [rsp+80h] [rbp+7h]
  __int64 v54; // [rsp+88h] [rbp+Fh]
  int v55; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v56; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v57; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v58; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_QWORD *)(a1 + 780) = 0;
  *(_DWORD *)(a1 + 732) = 0;
  v2 = *(_QWORD *)(a1 + 264);
  v3 = *(_QWORD *)(a1 + 408);
  v4 = *(unsigned int **)(a1 + 384);
  v57 = 0;
  v55 = 0;
  v54 = v2;
  v5 = *v4;
  v51 = v3;
  if ( v5 == -1 )
    return 1;
  while ( 2 )
  {
    v6 = 5LL * v5;
    v7 = *(unsigned int *)(v3 + 20LL * v5 + 8);
    v8 = *(_QWORD *)(v3 + 20LL * v5);
    v53 = v6;
    v44 = v8;
    if ( (_DWORD)v7 && (_DWORD)v7 == *(_DWORD *)(a1 + 2556) )
    {
      if ( (_DWORD)v8 != 6 || strncmp_0((const char *)(*(_QWORD *)a1 + HIDWORD(v8)), "RESDLL", 6u) )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BinitSpecialFeatureOptionFields",
          "References to ResourceDLLs must be placed in the feature with symbolname: %s.",
          "RESDLL");
        return 0;
      }
      if ( *(_DWORD *)(396 * v7 + v2 + 108) != 0x7FFFFFFF )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BinitSpecialFeatureOptionFields",
          "ResourceDLL names must be declared explicitly using *Name not *rcNameID.");
        return 0;
      }
    }
    v9 = ComputeCrc32Checksum(" NewFeature ", 12, *(_DWORD *)(a1 + 732));
    *(_DWORD *)(a1 + 732) = v9;
    v10 = *(_QWORD *)a1;
    *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum((char *)(*(_QWORD *)a1 + HIDWORD(v8)), v8, v9);
    v11 = (unsigned int *)(396 * v7 + v2);
    if ( (unsigned int)BReadDataInGlobalNode(v11 + 4, &v57, a1) && *(_DWORD *)(v57 + v10) == 1 )
    {
      v13 = 6;
      v14 = " TRUE ";
    }
    else
    {
      v13 = 7;
      v14 = " FALSE ";
    }
    *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(v14, v13, v12);
    v15 = *(unsigned int *)(v3 + 4 * v6 + 16);
    v11[98] = *(_DWORD *)(v3 + 20 * v15 + 8) + 1;
    if ( !(unsigned int)BwriteToHeap(v11 + 7, &v44, 8u, 4u, a1) )
      return 0;
    v16 = v44;
    v11[7] |= 0x80000000;
    v56 = 0;
    v46 = v16 + 2;
    if ( !(unsigned int)BReadDataInGlobalNode(v11 + 1, &v56, a1)
      || (v17 = *(_QWORD *)a1, v47 = 1, *(_DWORD *)(v56 + v17) != 1) )
    {
      v47 = 0;
    }
    v18 = v11 + 97;
    if ( !(unsigned int)BIdentifyConstantString(&v44, v11 + 97, 0x22u, 1, a1) )
      *v18 = 0xFFFF;
    if ( *v18 != 6 && *v18 != 9 || (unsigned int)BReadDataInGlobalNode(v11, &v56, a1) )
      goto LABEL_22;
    v56 = 2;
    if ( !(unsigned int)BwriteToHeap(v11, &v56, 4u, 4u, a1) )
      return 0;
    *v11 |= 0x80000000;
LABEL_22:
    v19 = 0;
    v48 = 257;
    v56 = 0;
    while ( (_DWORD)v15 != -1 )
    {
      v20 = *(_DWORD *)(a1 + 732);
      v58 = 0;
      v45 = 0;
      v21 = *(_QWORD *)(v51 + 20LL * (unsigned int)v15);
      v22 = *(_DWORD *)(v3 + 20LL * (unsigned int)v15 + 8);
      v23 = (char *)(*(_QWORD *)a1 + HIDWORD(v21));
      v52 = 5LL * (unsigned int)v15;
      v44 = v21;
      *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(v23, v21, v20);
      if ( (unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x58u, 4u, &v45, 0, &v55, 0, a1) && v55 && v45 == 1 )
      {
        v24 = 6;
        v25 = " TRUE ";
      }
      else
      {
        v24 = 7;
        v25 = " FALSE ";
      }
      *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(v25, v24, *(_DWORD *)(a1 + 732));
      if ( !(unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x64u, 8u, v26, &v44, &v55, (unsigned int)v26, a1) )
        return 0;
      if ( v47 )
      {
        v46 += v44 + 1;
      }
      else
      {
        if ( v19 < (int)v44 + 1 )
          v19 = v44 + 1;
        v56 = v19;
      }
      switch ( *v18 )
      {
        case 1:
          v27 = 35;
          break;
        case 3:
          v27 = 38;
          goto LABEL_44;
        case 4:
          v27 = 37;
          break;
        case 5:
          v27 = 36;
          break;
        case 8:
          v27 = 39;
          goto LABEL_44;
        case 9:
          v27 = 40;
          goto LABEL_44;
        case 0xA:
          v27 = 41;
LABEL_44:
          v28 = 0;
          goto LABEL_52;
        case 0xC:
          v27 = 42;
          break;
        default:
          goto LABEL_86;
      }
      v28 = 1;
LABEL_52:
      if ( !(unsigned int)BIdentifyConstantString(&v44, &v58, v27, v28, a1) )
      {
        if ( !v28 )
          goto LABEL_85;
        v40 = *v18 == 12;
        v45 = 0;
        v58 = 0;
        v44 = 0;
        if ( v40
          && (unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x150u, 4u, &v58, 0, &v55, 0, a1)
          && v55
          && v58
          && (unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x154u, 8u, &v44, 0, &v55, 0, a1)
          && v55
          && (unsigned int)(v44 - 4) <= 0xFC
          && (unsigned int)(HIDWORD(v44) - 4) <= 0xFC )
        {
          v41 = 18;
        }
        else
        {
          v41 = v48++;
        }
        v58 = v41;
        if ( !(unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x168u, 4u, &v45, 0, &v55, 0, a1) )
          return 0;
        if ( v55 )
          goto LABEL_85;
        v39 = BexchangeArbDataInFOATNode(v7, v22, 0x168u, 4u, 0, &v58, &v55, 0, a1);
        goto LABEL_84;
      }
      if ( !(unsigned int)BexchangeArbDataInFOATNode(v7, v22, 0x168u, 4u, 0, &v58, &v55, 0, a1) )
        return 0;
      if ( v27 == 35 )
      {
        v29 = v58;
        if ( v58 < 0x100 )
        {
          v58 = 1;
          if ( v29 == 1 )
          {
            v30 = *(_QWORD *)(a1 + 24);
            BwriteToHeap((_DWORD *)(v30 + 456), &v58, 4u, 4u, a1);
            *(_DWORD *)(v30 + 456) |= 0x80000000;
          }
          else if ( v29 == 9 )
          {
            v31 = *(_QWORD *)(a1 + 24);
            BwriteToHeap((_DWORD *)(v31 + 460), &v58, 4u, 4u, a1);
            *(_DWORD *)(v31 + 460) |= 0x80000000;
          }
          v32 = 0;
          do
          {
            if ( *((_DWORD *)aPaperDimensions + 3 * v32) == v29 )
              break;
            v32 = (unsigned int)(v32 + 1);
          }
          while ( *((_DWORD *)aPaperDimensions + 3 * v32 + 1) );
          v33 = *(_QWORD *)(a1 + 24);
          if ( !(unsigned int)BReadDataInGlobalNode((unsigned int *)(v33 + 4), &v57, a1) )
            return 0;
          v58 = 0;
          v35 = BReadDataInGlobalNode((unsigned int *)(v33 + 476), &v58, v34);
          if ( v35 )
            v35 = *(_DWORD *)(v58 + *(_QWORD *)a1);
          if ( v35 )
          {
            v38 = (float)*(int *)(v57 + *(_QWORD *)a1 + 4LL);
            v49 = (int)((double)*((int *)aPaperDimensions + 3 * v36 + 1)
                      / 100.0
                      * (float)*(int *)(v57 + *(_QWORD *)a1)
                      / 254.0);
            v50 = (int)((double)*((int *)&aPaperDimensions[1] + 3 * v36) / 100.0 * v38 / 254.0);
          }
          else
          {
            v37 = *(_QWORD *)a1;
            v49 = *(_DWORD *)(v57 + *(_QWORD *)a1) * (*((_DWORD *)aPaperDimensions + 3 * v36 + 1) / 100) / 254;
            v50 = *(_DWORD *)(v57 + v37 + 4) * (*((_DWORD *)&aPaperDimensions[1] + 3 * v36) / 100) / 254;
          }
          v39 = BexchangeArbDataInFOATNode(v7, v22, 0xC8u, 8u, 0, &v49, &v55, 0, a1);
LABEL_84:
          if ( !v39 )
            return 0;
        }
      }
LABEL_85:
      v19 = v56;
LABEL_86:
      v3 = v51;
      LODWORD(v15) = *(_DWORD *)(v51 + 4 * v52 + 12);
    }
    v56 = 0;
    if ( (unsigned int)BReadDataInGlobalNode(v11, &v56, a1) && *(_DWORD *)(v56 + *(_QWORD *)a1) == 2 )
      *(_DWORD *)(a1 + 784) += v42;
    else
      *(_DWORD *)(a1 + 780) += v42;
    v5 = *(_DWORD *)(v3 + 4 * v53 + 12);
    if ( v5 != -1 )
    {
      v2 = v54;
      continue;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180042800  push    rbp
0x180042802  push    rbx
0x180042803  push    rsi
0x180042804  push    rdi
0x180042805  push    r12
0x180042807  push    r13
0x180042809  push    r14
0x18004280b  push    r15
0x18004280d  lea     rbp, [rsp-1Fh]
0x180042812  sub     rsp, 98h
0x180042819  xor     esi, esi
0x18004281b  mov     rdi, rcx
0x18004281e  mov     [rcx+30Ch], rsi
0x180042825  mov     [rcx+2DCh], esi
0x18004282b  mov     r15, [rcx+108h]
0x180042832  mov     r12, [rcx+198h]
0x180042839  mov     rax, [rcx+180h]
0x180042840  mov     [rbp+57h+arg_10], esi
0x180042843  mov     [rbp+57h+arg_0], esi
0x180042846  mov     [rbp+57h+var_48], r15
0x18004284a  mov     ecx, [rax]
0x18004284c  mov     [rbp+57h+var_60], r12
0x180042850  cmp     ecx, 0FFFFFFFFh
0x180042853  jz      loc_180043070
0x180042859  mov     eax, ecx
0x18004285b  lea     r13, [rax+rax*4]
0x18004285f  mov     r14d, [r12+r13*4+8]
0x180042864  mov     rbx, [r12+r13*4]
0x180042868  mov     [rbp+57h+var_50], r13
0x18004286c  mov     [rbp+57h+var_80], rbx
0x180042870  test    r14d, r14d
0x180042873  jz      short loc_1800428BE
0x180042875  cmp     r14d, [rdi+9FCh]
0x18004287c  jnz     short loc_1800428BE
0x18004287e  cmp     ebx, 6
0x180042881  jnz     loc_180043052
0x180042887  mov     rcx, rbx
0x18004288a  lea     rdx, aResdll; "RESDLL"
0x180042891  shr     rcx, 20h
0x180042895  mov     r8d, ebx; MaxCount
0x180042898  add     rcx, [rdi]; Str1
0x18004289b  call    strncmp_0
0x1800428a0  test    eax, eax
0x1800428a2  jnz     loc_180043052
0x1800428a8  imul    rcx, r14, 18Ch
0x1800428af  cmp     dword ptr [rcx+r15+6Ch], 7FFFFFFFh
0x1800428b8  jnz     loc_18004303D
0x1800428be  mov     r8d, [rdi+2DCh]
0x1800428c5  lea     rcx, aNewfeature; " NewFeature "
0x1800428cc  mov     edx, 0Ch
0x1800428d1  call    ComputeCrc32Checksum
0x1800428d6  mov     [rdi+2DCh], eax
0x1800428dc  mov     rcx, rbx
0x1800428df  mov     rsi, [rdi]
0x1800428e2  mov     r8d, eax
0x1800428e5  shr     rcx, 20h
0x1800428e9  mov     edx, ebx
0x1800428eb  add     rcx, rsi
0x1800428ee  call    ComputeCrc32Checksum
0x1800428f3  imul    rdx, r14, 18Ch
0x1800428fa  mov     r8, rdi
0x1800428fd  mov     [rdi+2DCh], eax
0x180042903  add     r15, rdx
0x180042906  mov     r11d, eax
0x180042909  lea     rdx, [rbp+57h+arg_10]
0x18004290d  lea     rcx, [r15+10h]
0x180042911  call    BReadDataInGlobalNode
0x180042916  test    eax, eax
0x180042918  jz      short loc_180042931
0x18004291a  mov     ecx, [rbp+57h+arg_10]
0x18004291d  cmp     dword ptr [rcx+rsi], 1
0x180042921  jnz     short loc_180042931
0x180042923  mov     edx, 6
0x180042928  lea     rcx, aTrue_0; " TRUE "
0x18004292f  jmp     short loc_18004293D
0x180042931  mov     edx, 7
0x180042936  lea     rcx, aFalse_0; " FALSE "
0x18004293d  mov     r8d, r11d
0x180042940  call    ComputeCrc32Checksum
0x180042945  mov     [rdi+2DCh], eax
0x18004294b  lea     rdx, [rbp+57h+var_80]
0x18004294f  mov     ebx, [r12+r13*4+10h]
0x180042954  mov     r9d, 4
0x18004295a  mov     [rsp+0D0h+var_B0], rdi
0x18004295f  lea     rax, [rbx+rbx*4]
0x180042963  mov     ecx, [r12+rax*4+8]
0x180042968  lea     r8d, [r9+4]
0x18004296c  inc     ecx
0x18004296e  mov     [r15+188h], ecx
0x180042975  lea     rcx, [r15+1Ch]
0x180042979  call    BwriteToHeap
0x18004297e  test    eax, eax
0x180042980  jz      loc_18004306C
0x180042986  mov     eax, dword ptr [rbp+57h+var_80]
0x180042989  lea     rcx, [r15+4]
0x18004298d  bts     dword ptr [r15+1Ch], 1Fh
0x180042993  lea     rdx, [rbp+57h+arg_8]
0x180042997  add     eax, 2
0x18004299a  mov     [rbp+57h+arg_8], 0
0x1800429a1  mov     r8, rdi
0x1800429a4  mov     [rbp+57h+var_74], eax
0x1800429a7  call    BReadDataInGlobalNode
0x1800429ac  test    eax, eax
0x1800429ae  jz      short loc_1800429C3
0x1800429b0  mov     ecx, [rbp+57h+arg_8]
0x1800429b3  mov     rax, [rdi]
0x1800429b6  mov     [rbp+57h+var_70], 1
0x1800429bd  cmp     dword ptr [rcx+rax], 1
0x1800429c1  jz      short loc_1800429CA
0x1800429c3  mov     [rbp+57h+var_70], 0
0x1800429ca  mov     r9d, 1
0x1800429d0  mov     [rsp+0D0h+var_B0], rdi
0x1800429d5  lea     r13, [r15+184h]
0x1800429dc  mov     rdx, r13
0x1800429df  lea     rcx, [rbp+57h+var_80]
0x1800429e3  lea     r8d, [r9+21h]
0x1800429e7  call    BIdentifyConstantString
0x1800429ec  test    eax, eax
0x1800429ee  jnz     short loc_1800429F8
0x1800429f0  mov     dword ptr [r13+0], 0FFFFh
0x1800429f8  cmp     dword ptr [r13+0], 6
0x1800429fd  jz      short loc_180042A06
0x1800429ff  cmp     dword ptr [r13+0], 9
0x180042a04  jnz     short loc_180042A49
0x180042a06  mov     r8, rdi
0x180042a09  lea     rdx, [rbp+57h+arg_8]
0x180042a0d  mov     rcx, r15
0x180042a10  call    BReadDataInGlobalNode
0x180042a15  test    eax, eax
0x180042a17  jnz     short loc_180042A49
0x180042a19  mov     eax, 4
0x180042a1e  mov     [rbp+57h+arg_8], 2
0x180042a25  mov     r9d, eax
0x180042a28  mov     [rsp+0D0h+var_B0], rdi
0x180042a2d  mov     r8d, eax
0x180042a30  lea     rdx, [rbp+57h+arg_8]
0x180042a34  mov     rcx, r15
0x180042a37  call    BwriteToHeap
0x180042a3c  test    eax, eax
0x180042a3e  jz      loc_18004306C
0x180042a44  bts     dword ptr [r15], 1Fh
0x180042a49  xor     esi, esi
0x180042a4b  mov     [rbp+57h+var_6C], 101h
0x180042a52  mov     [rbp+57h+arg_8], esi
0x180042a55  jmp     loc_180042FE0
0x180042a5a  mov     rdx, [rbp+57h+var_60]
0x180042a5e  mov     r8d, [rdi+2DCh]
0x180042a65  mov     eax, ebx
0x180042a67  mov     [rbp+57h+arg_18], 0
0x180042a6e  mov     [rbp+57h+var_78], 0
0x180042a75  lea     rax, [rax+rax*4]
0x180042a79  mov     rdx, [rdx+rax*4]
0x180042a7d  mov     r12d, [r12+rax*4+8]
0x180042a82  mov     rcx, rdx
0x180042a85  shr     rcx, 20h
0x180042a89  add     rcx, [rdi]
0x180042a8c  mov     [rbp+57h+var_58], rax
0x180042a90  mov     [rbp+57h+var_80], rdx
0x180042a94  call    ComputeCrc32Checksum
0x180042a99  mov     [rsp+0D0h+var_90], rdi
0x180042a9e  mov     r9d, 4
0x180042aa4  mov     [rdi+2DCh], eax
0x180042aaa  mov     edx, r12d
0x180042aad  mov     [rsp+0D0h+var_98], 0
0x180042ab5  lea     rax, [rbp+57h+arg_0]
0x180042ab9  mov     [rsp+0D0h+var_A0], rax
0x180042abe  mov     ecx, r14d
0x180042ac1  lea     rax, [rbp+57h+var_78]
0x180042ac5  mov     [rsp+0D0h+var_A8], 0
0x180042ace  lea     r8d, [r9+54h]
0x180042ad2  mov     [rsp+0D0h+var_B0], rax
0x180042ad7  call    BexchangeArbDataInFOATNode
0x180042adc  xor     r11d, r11d
0x180042adf  test    eax, eax
0x180042ae1  jz      short loc_180042AFC
0x180042ae3  cmp     [rbp+57h+arg_0], r11d
0x180042ae7  jz      short loc_180042AFC
0x180042ae9  cmp     [rbp+57h+var_78], 1
0x180042aed  jnz     short loc_180042AFC
0x180042aef  lea     edx, [r11+6]
0x180042af3  lea     rcx, aTrue_0; " TRUE "
0x180042afa  jmp     short loc_180042B08
0x180042afc  mov     edx, 7
0x180042b01  lea     rcx, aFalse_0; " FALSE "
0x180042b08  mov     r8d, [rdi+2DCh]
0x180042b0f  call    ComputeCrc32Checksum
0x180042b14  mov     [rsp+0D0h+var_90], rdi
0x180042b19  mov     r9d, 8
0x180042b1f  mov     [rsp+0D0h+var_98], r11d
0x180042b24  mov     edx, r12d
0x180042b27  mov     [rdi+2DCh], eax
0x180042b2d  mov     ecx, r14d
0x180042b30  lea     rax, [rbp+57h+arg_0]
0x180042b34  mov     [rsp+0D0h+var_A0], rax
0x180042b39  lea     r8d, [r9+5Ch]
0x180042b3d  lea     rax, [rbp+57h+var_80]
0x180042b41  mov     [rsp+0D0h+var_A8], rax
0x180042b46  mov     [rsp+0D0h+var_B0], r11
0x180042b4b  call    BexchangeArbDataInFOATNode
0x180042b50  test    eax, eax
0x180042b52  jz      loc_18004306C
0x180042b58  cmp     [rbp+57h+var_70], 0
0x180042b5c  jz      short loc_180042B6B
0x180042b5e  mov     ecx, [rbp+57h+var_74]
0x180042b61  inc     ecx
0x180042b63  add     ecx, dword ptr [rbp+57h+var_80]
0x180042b66  mov     [rbp+57h+var_74], ecx
0x180042b69  jmp     short loc_180042B78
0x180042b6b  mov     eax, dword ptr [rbp+57h+var_80]
0x180042b6e  inc     eax
0x180042b70  cmp     esi, eax
0x180042b72  cmovb   esi, eax
0x180042b75  mov     [rbp+57h+arg_8], esi
0x180042b78  mov     ecx, [r13+0]
0x180042b7c  sub     ecx, 1
0x180042b7f  jz      short loc_180042BD9
0x180042b81  sub     ecx, 2
0x180042b84  jz      short loc_180042BD2
0x180042b86  sub     ecx, 1
0x180042b89  jz      short loc_180042BCB
0x180042b8b  sub     ecx, 1
0x180042b8e  jz      short loc_180042BC4
0x180042b90  sub     ecx, 3
0x180042b93  jz      short loc_180042BBD
0x180042b95  sub     ecx, 1
0x180042b98  jz      short loc_180042BB6
0x180042b9a  sub     ecx, 1
0x180042b9d  jz      short loc_180042BAD
0x180042b9f  cmp     ecx, 2
0x180042ba2  jnz     loc_180042FD3
0x180042ba8  lea     esi, [rcx+28h]
0x180042bab  jmp     short loc_180042BDE
0x180042bad  mov     esi, 29h ; ')'
0x180042bb2  xor     ebx, ebx
0x180042bb4  jmp     short loc_180042BE3
0x180042bb6  mov     esi, 28h ; '('
0x180042bbb  jmp     short loc_180042BB2
0x180042bbd  mov     esi, 27h ; '''
0x180042bc2  jmp     short loc_180042BB2
0x180042bc4  mov     esi, 24h ; '$'
0x180042bc9  jmp     short loc_180042BDE
0x180042bcb  mov     esi, 25h ; '%'
0x180042bd0  jmp     short loc_180042BDE
0x180042bd2  mov     esi, 26h ; '&'
0x180042bd7  jmp     short loc_180042BB2
0x180042bd9  mov     esi, 23h ; '#'
0x180042bde  mov     ebx, 1
0x180042be3  mov     r9d, ebx
0x180042be6  mov     [rsp+0D0h+var_B0], rdi
0x180042beb  mov     r8d, esi
0x180042bee  lea     rdx, [rbp+57h+arg_18]
0x180042bf2  lea     rcx, [rbp+57h+var_80]
0x180042bf6  call    BIdentifyConstantString
0x180042bfb  test    eax, eax
0x180042bfd  jz      loc_180042E4F
0x180042c03  mov     [rsp+0D0h+var_90], rdi
0x180042c08  lea     rax, [rbp+57h+arg_0]
0x180042c0c  mov     [rsp+0D0h+var_98], 0
0x180042c14  mov     r9d, 4
0x180042c1a  mov     [rsp+0D0h+var_A0], rax
0x180042c1f  mov     r8d, 168h
0x180042c25  lea     rax, [rbp+57h+arg_18]
0x180042c29  mov     edx, r12d
0x180042c2c  mov     [rsp+0D0h+var_A8], rax
0x180042c31  mov     ecx, r14d
0x180042c34  mov     [rsp+0D0h+var_B0], 0
0x180042c3d  call    BexchangeArbDataInFOATNode
0x180042c42  test    eax, eax
0x180042c44  jz      loc_18004306C
0x180042c4a  cmp     esi, 23h ; '#'
0x180042c4d  jnz     loc_180042FD0
0x180042c53  mov     esi, [rbp+57h+arg_18]
0x180042c56  cmp     esi, 100h
0x180042c5c  jnb     loc_180042FD0
0x180042c62  mov     [rbp+57h+arg_18], 1
0x180042c69  cmp     esi, 1
0x180042c6c  jnz     short loc_180042C9A
0x180042c6e  mov     rbx, [rdi+18h]
0x180042c72  lea     eax, [rsi+3]
0x180042c75  mov     r9d, eax
0x180042c78  mov     [rsp+0D0h+var_B0], rdi
0x180042c7d  mov     r8d, eax
0x180042c80  lea     rdx, [rbp+57h+arg_18]
0x180042c84  lea     rcx, [rbx+1C8h]
0x180042c8b  call    BwriteToHeap
0x180042c90  bts     dword ptr [rbx+1C8h], 1Fh
0x180042c98  jmp     short loc_180042CC9
0x180042c9a  cmp     esi, 9
0x180042c9d  jnz     short loc_180042CC9
0x180042c9f  mov     rbx, [rdi+18h]
0x180042ca3  lea     eax, [rsi-5]
0x180042ca6  mov     r9d, eax
0x180042ca9  mov     [rsp+0D0h+var_B0], rdi
0x180042cae  mov     r8d, eax
0x180042cb1  lea     rdx, [rbp+57h+arg_18]
0x180042cb5  lea     rcx, [rbx+1CCh]
0x180042cbc  call    BwriteToHeap
0x180042cc1  bts     dword ptr [rbx+1CCh], 1Fh
0x180042cc9  xor     r11d, r11d
0x180042ccc  lea     rdx, aPaperDimensions
  ... truncated ...
```
