# BinitSpecialFeatureOptionFields

- ea: `0x18004165c`
- end: `0x180041ee5`
- name: `BinitSpecialFeatureOptionFields`
- size: `2185`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047f54`

## callees

- `0x180007220`
- `0x18000a0b8`
- `0x18000aef4`
- `0x18000cd90`
- `0x18003f288`
- `0x18004155c`
- `0x18004165c`
- `0x180074550`

## string_xrefs

- `0x1800416e6`: `RESDLL`
- `0x180041eae`: `RESDLL`
- `0x180041eb5`: `References to ResourceDLLs must be placed in the feature with symbolname: %s.`
- `0x180041e99`: `ResourceDLL names must be declared explicitly using *Name not *rcNameID.`

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
  _DWORD *v11; // r15
  unsigned int v12; // r11d
  __int64 v13; // rdx
  const char *v14; // rcx
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rax
  _DWORD *v18; // r13
  unsigned int v19; // esi
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  unsigned int v22; // r12d
  unsigned __int64 v23; // rcx
  int v24; // esi
  int v25; // ebx
  unsigned int v26; // esi
  __int64 v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // r11
  __int64 v30; // rbx
  __int64 v31; // r8
  int v32; // r8d
  __int64 v33; // r11
  __int64 v34; // r8
  float v35; // xmm0_4
  __int64 v36; // r8
  bool v37; // zf
  unsigned int v38; // eax
  int v39; // r11d
  unsigned __int64 v41; // [rsp+50h] [rbp-29h] BYREF
  int v42; // [rsp+58h] [rbp-21h]
  int v43; // [rsp+5Ch] [rbp-1Dh]
  int v44; // [rsp+60h] [rbp-19h]
  int v45; // [rsp+64h] [rbp-15h]
  int v46; // [rsp+68h] [rbp-11h]
  int v47; // [rsp+6Ch] [rbp-Dh]
  __int64 v48; // [rsp+70h] [rbp-9h]
  __int64 v49; // [rsp+78h] [rbp-1h]
  __int64 v50; // [rsp+80h] [rbp+7h]
  __int64 v51; // [rsp+88h] [rbp+Fh]
  unsigned int v52; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v53; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v54; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_QWORD *)(a1 + 780) = 0;
  *(_DWORD *)(a1 + 732) = 0;
  v2 = *(_QWORD *)(a1 + 264);
  v3 = *(_QWORD *)(a1 + 408);
  v4 = *(unsigned int **)(a1 + 384);
  v53 = 0;
  v51 = v2;
  v5 = *v4;
  v48 = v3;
  if ( v5 == -1 )
    return 1;
  while ( 2 )
  {
    v6 = 5LL * v5;
    v7 = *(unsigned int *)(v3 + 20LL * v5 + 8);
    v8 = *(_QWORD *)(v3 + 20LL * v5);
    v50 = v6;
    v41 = v8;
    if ( (_DWORD)v7 && (_DWORD)v7 == *(_DWORD *)(a1 + 2556) )
    {
      if ( (_DWORD)v8 != 6 || strncmp_0((const char *)(*(_QWORD *)a1 + HIDWORD(v8)), "RESDLL", 6u) )
      {
        WriteDbgTraceErrorGpd(
          "BinitSpecialFeatureOptionFields",
          "References to ResourceDLLs must be placed in the feature with symbolname: %s.",
          "RESDLL");
        return 0;
      }
      if ( *(_DWORD *)(396 * v7 + v2 + 108) != 0x7FFFFFFF )
      {
        WriteDbgTraceErrorGpd(
          "BinitSpecialFeatureOptionFields",
          "ResourceDLL names must be declared explicitly using *Name not *rcNameID.");
        return 0;
      }
    }
    v9 = ComputeCrc32Checksum(" NewFeature ", 12, *(unsigned int *)(a1 + 732));
    *(_DWORD *)(a1 + 732) = v9;
    v10 = *(_QWORD *)a1;
    *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(*(_QWORD *)a1 + HIDWORD(v8), (unsigned int)v8, v9);
    v11 = (_DWORD *)(396 * v7 + v2);
    if ( (unsigned int)BReadDataInGlobalNode(v11 + 4, &v53, a1) && *(_DWORD *)(v53 + v10) == 1 )
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
    if ( !(unsigned int)BwriteToHeap(v11 + 7, &v41, 8, 4, a1) )
      return 0;
    v16 = v41;
    v11[7] |= 0x80000000;
    v52 = 0;
    v43 = v16 + 2;
    if ( !(unsigned int)BReadDataInGlobalNode(v11 + 1, &v52, a1)
      || (v17 = *(_QWORD *)a1, v44 = 1, *(_DWORD *)(v52 + v17) != 1) )
    {
      v44 = 0;
    }
    v18 = v11 + 97;
    if ( !(unsigned int)BIdentifyConstantString((unsigned int)&v41, (int)v11 + 388, 34, 1, a1) )
      *v18 = 0xFFFF;
    if ( *v18 != 6 && *v18 != 9 || (unsigned int)BReadDataInGlobalNode(v11, &v52, a1) )
      goto LABEL_22;
    v52 = 2;
    if ( !(unsigned int)BwriteToHeap(v11, &v52, 4, 4, a1) )
      return 0;
    *v11 |= 0x80000000;
LABEL_22:
    v19 = 0;
    v45 = 257;
    v52 = 0;
    while ( (_DWORD)v15 != -1 )
    {
      v20 = *(unsigned int *)(a1 + 732);
      v54 = 0;
      v42 = 0;
      v21 = *(_QWORD *)(v48 + 20LL * (unsigned int)v15);
      v22 = *(_DWORD *)(v3 + 20LL * (unsigned int)v15 + 8);
      v23 = *(_QWORD *)a1 + HIDWORD(v21);
      v49 = 5LL * (unsigned int)v15;
      v41 = v21;
      *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(v23, v21, v20);
      BexchangeArbDataInFOATNode((unsigned int)v7, v22, 88);
      *(_DWORD *)(a1 + 732) = ComputeCrc32Checksum(" FALSE ", 7, *(unsigned int *)(a1 + 732));
      if ( !(unsigned int)BexchangeArbDataInFOATNode((unsigned int)v7, v22, 100) )
        return 0;
      if ( v44 )
      {
        v43 += v41 + 1;
      }
      else
      {
        if ( v19 < (int)v41 + 1 )
          v19 = v41 + 1;
        v52 = v19;
      }
      switch ( *v18 )
      {
        case 1:
          v24 = 35;
          break;
        case 3:
          v24 = 38;
          goto LABEL_39;
        case 4:
          v24 = 37;
          break;
        case 5:
          v24 = 36;
          break;
        case 8:
          v24 = 39;
          goto LABEL_39;
        case 9:
          v24 = 40;
          goto LABEL_39;
        case 0xA:
          v24 = 41;
LABEL_39:
          v25 = 0;
          goto LABEL_47;
        case 0xC:
          v24 = 42;
          break;
        default:
          goto LABEL_72;
      }
      v25 = 1;
LABEL_47:
      if ( (unsigned int)BIdentifyConstantString((unsigned int)&v41, (unsigned int)&v54, v24, v25, a1) )
      {
        if ( !(unsigned int)BexchangeArbDataInFOATNode((unsigned int)v7, v22, 360) )
          return 0;
        if ( v24 == 35 )
        {
          v26 = v54;
          if ( v54 < 0x100 )
          {
            v54 = 1;
            if ( v26 == 1 )
            {
              v27 = *(_QWORD *)(a1 + 24);
              BwriteToHeap(v27 + 456, &v54, 4, 4, a1);
              *(_DWORD *)(v27 + 456) |= 0x80000000;
            }
            else if ( v26 == 9 )
            {
              v28 = *(_QWORD *)(a1 + 24);
              BwriteToHeap(v28 + 460, &v54, 4, 4, a1);
              *(_DWORD *)(v28 + 460) |= 0x80000000;
            }
            v29 = 0;
            do
            {
              if ( *((_DWORD *)aPaperDimensions + 3 * v29) == v26 )
                break;
              v29 = (unsigned int)(v29 + 1);
            }
            while ( *((_DWORD *)aPaperDimensions + 3 * v29 + 1) );
            v30 = *(_QWORD *)(a1 + 24);
            if ( !(unsigned int)BReadDataInGlobalNode(v30 + 4, &v53, a1) )
              return 0;
            v54 = 0;
            v32 = BReadDataInGlobalNode(v30 + 476, &v54, v31);
            if ( v32 )
              v32 = *(_DWORD *)(v54 + *(_QWORD *)a1);
            if ( v32 )
            {
              v35 = (float)*(int *)(v53 + *(_QWORD *)a1 + 4LL);
              v46 = (int)((double)*((int *)aPaperDimensions + 3 * v33 + 1)
                        / 100.0
                        * (float)*(int *)(v53 + *(_QWORD *)a1)
                        / 254.0);
              v47 = (int)((double)*((int *)&aPaperDimensions[1] + 3 * v33) / 100.0 * v35 / 254.0);
            }
            else
            {
              v34 = *(_QWORD *)a1;
              v46 = *(_DWORD *)(v53 + *(_QWORD *)a1) * (*((_DWORD *)aPaperDimensions + 3 * v33 + 1) / 100) / 254;
              v47 = *(_DWORD *)(v53 + v34 + 4) * (*((_DWORD *)&aPaperDimensions[1] + 3 * v33) / 100) / 254;
            }
            v36 = 200;
LABEL_70:
            if ( !(unsigned int)BexchangeArbDataInFOATNode((unsigned int)v7, v22, v36) )
              return 0;
          }
        }
      }
      else if ( v25 )
      {
        v37 = *v18 == 12;
        v42 = 0;
        v54 = 0;
        v41 = 0;
        if ( v37 )
          BexchangeArbDataInFOATNode((unsigned int)v7, v22, 336);
        v38 = v45++;
        v54 = v38;
        if ( !(unsigned int)BexchangeArbDataInFOATNode((unsigned int)v7, v22, 360) )
          return 0;
        v36 = 360;
        goto LABEL_70;
      }
      v19 = v52;
LABEL_72:
      v3 = v48;
      LODWORD(v15) = *(_DWORD *)(v48 + 4 * v49 + 12);
    }
    v52 = 0;
    if ( (unsigned int)BReadDataInGlobalNode(v11, &v52, a1) && *(_DWORD *)(v52 + *(_QWORD *)a1) == 2 )
      *(_DWORD *)(a1 + 784) += v39;
    else
      *(_DWORD *)(a1 + 780) += v39;
    v5 = *(_DWORD *)(v3 + 4 * v50 + 12);
    if ( v5 != -1 )
    {
      v2 = v51;
      continue;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18004165c  push    rbp
0x18004165e  push    rbx
0x18004165f  push    rsi
0x180041660  push    rdi
0x180041661  push    r12
0x180041663  push    r13
0x180041665  push    r14
0x180041667  push    r15
0x180041669  lea     rbp, [rsp-1Fh]
0x18004166e  sub     rsp, 98h
0x180041675  xor     esi, esi
0x180041677  mov     rdi, rcx
0x18004167a  mov     [rcx+30Ch], rsi
0x180041681  mov     [rcx+2DCh], esi
0x180041687  mov     r15, [rcx+108h]
0x18004168e  mov     r12, [rcx+198h]
0x180041695  mov     rax, [rcx+180h]
0x18004169c  mov     [rbp+57h+arg_10], esi
0x18004169f  mov     [rbp+57h+arg_0], esi
0x1800416a2  mov     [rbp+57h+var_48], r15
0x1800416a6  mov     ecx, [rax]
0x1800416a8  mov     [rbp+57h+var_60], r12
0x1800416ac  cmp     ecx, 0FFFFFFFFh
0x1800416af  jz      loc_180041ECC
0x1800416b5  mov     eax, ecx
0x1800416b7  lea     r13, [rax+rax*4]
0x1800416bb  mov     r14d, [r12+r13*4+8]
0x1800416c0  mov     rbx, [r12+r13*4]
0x1800416c4  mov     [rbp+57h+var_50], r13
0x1800416c8  mov     [rbp+57h+var_80], rbx
0x1800416cc  test    r14d, r14d
0x1800416cf  jz      short loc_18004171A
0x1800416d1  cmp     r14d, [rdi+9FCh]
0x1800416d8  jnz     short loc_18004171A
0x1800416da  cmp     ebx, 6
0x1800416dd  jnz     loc_180041EAE
0x1800416e3  mov     rcx, rbx
0x1800416e6  lea     rdx, aResdll; "RESDLL"
0x1800416ed  shr     rcx, 20h
0x1800416f1  mov     r8d, ebx; MaxCount
0x1800416f4  add     rcx, [rdi]; Str1
0x1800416f7  call    strncmp_0
0x1800416fc  test    eax, eax
0x1800416fe  jnz     loc_180041EAE
0x180041704  imul    rcx, r14, 18Ch
0x18004170b  cmp     dword ptr [rcx+r15+6Ch], 7FFFFFFFh
0x180041714  jnz     loc_180041E99
0x18004171a  mov     r8d, [rdi+2DCh]
0x180041721  lea     rcx, aNewfeature; " NewFeature "
0x180041728  mov     edx, 0Ch
0x18004172d  call    ComputeCrc32Checksum
0x180041732  mov     [rdi+2DCh], eax
0x180041738  mov     rcx, rbx
0x18004173b  mov     rsi, [rdi]
0x18004173e  mov     r8d, eax
0x180041741  shr     rcx, 20h
0x180041745  mov     edx, ebx
0x180041747  add     rcx, rsi
0x18004174a  call    ComputeCrc32Checksum
0x18004174f  imul    rdx, r14, 18Ch
0x180041756  mov     r8, rdi
0x180041759  mov     [rdi+2DCh], eax
0x18004175f  add     r15, rdx
0x180041762  mov     r11d, eax
0x180041765  lea     rdx, [rbp+57h+arg_10]
0x180041769  lea     rcx, [r15+10h]
0x18004176d  call    BReadDataInGlobalNode
0x180041772  test    eax, eax
0x180041774  jz      short loc_18004178D
0x180041776  mov     ecx, [rbp+57h+arg_10]
0x180041779  cmp     dword ptr [rcx+rsi], 1
0x18004177d  jnz     short loc_18004178D
0x18004177f  mov     edx, 6
0x180041784  lea     rcx, aTrue_0; " TRUE "
0x18004178b  jmp     short loc_180041799
0x18004178d  mov     edx, 7
0x180041792  lea     rcx, aFalse_0; " FALSE "
0x180041799  mov     r8d, r11d
0x18004179c  call    ComputeCrc32Checksum
0x1800417a1  mov     [rdi+2DCh], eax
0x1800417a7  lea     rdx, [rbp+57h+var_80]
0x1800417ab  mov     ebx, [r12+r13*4+10h]
0x1800417b0  mov     r9d, 4
0x1800417b6  mov     [rsp+0D0h+var_B0], rdi
0x1800417bb  lea     rax, [rbx+rbx*4]
0x1800417bf  mov     ecx, [r12+rax*4+8]
0x1800417c4  lea     r8d, [r9+4]
0x1800417c8  inc     ecx
0x1800417ca  mov     [r15+188h], ecx
0x1800417d1  lea     rcx, [r15+1Ch]
0x1800417d5  call    BwriteToHeap
0x1800417da  test    eax, eax
0x1800417dc  jz      loc_180041EC8
0x1800417e2  mov     eax, dword ptr [rbp+57h+var_80]
0x1800417e5  lea     rcx, [r15+4]
0x1800417e9  bts     dword ptr [r15+1Ch], 1Fh
0x1800417ef  lea     rdx, [rbp+57h+arg_8]
0x1800417f3  add     eax, 2
0x1800417f6  mov     [rbp+57h+arg_8], 0
0x1800417fd  mov     r8, rdi
0x180041800  mov     [rbp+57h+var_74], eax
0x180041803  call    BReadDataInGlobalNode
0x180041808  test    eax, eax
0x18004180a  jz      short loc_18004181F
0x18004180c  mov     ecx, [rbp+57h+arg_8]
0x18004180f  mov     rax, [rdi]
0x180041812  mov     [rbp+57h+var_70], 1
0x180041819  cmp     dword ptr [rcx+rax], 1
0x18004181d  jz      short loc_180041826
0x18004181f  mov     [rbp+57h+var_70], 0
0x180041826  mov     r9d, 1
0x18004182c  mov     [rsp+0D0h+var_B0], rdi
0x180041831  lea     r13, [r15+184h]
0x180041838  mov     rdx, r13
0x18004183b  lea     rcx, [rbp+57h+var_80]
0x18004183f  lea     r8d, [r9+21h]
0x180041843  call    BIdentifyConstantString
0x180041848  test    eax, eax
0x18004184a  jnz     short loc_180041854
0x18004184c  mov     dword ptr [r13+0], 0FFFFh
0x180041854  cmp     dword ptr [r13+0], 6
0x180041859  jz      short loc_180041862
0x18004185b  cmp     dword ptr [r13+0], 9
0x180041860  jnz     short loc_1800418A5
0x180041862  mov     r8, rdi
0x180041865  lea     rdx, [rbp+57h+arg_8]
0x180041869  mov     rcx, r15
0x18004186c  call    BReadDataInGlobalNode
0x180041871  test    eax, eax
0x180041873  jnz     short loc_1800418A5
0x180041875  mov     eax, 4
0x18004187a  mov     [rbp+57h+arg_8], 2
0x180041881  mov     r9d, eax
0x180041884  mov     [rsp+0D0h+var_B0], rdi
0x180041889  mov     r8d, eax
0x18004188c  lea     rdx, [rbp+57h+arg_8]
0x180041890  mov     rcx, r15
0x180041893  call    BwriteToHeap
0x180041898  test    eax, eax
0x18004189a  jz      loc_180041EC8
0x1800418a0  bts     dword ptr [r15], 1Fh
0x1800418a5  xor     esi, esi
0x1800418a7  mov     [rbp+57h+var_6C], 101h
0x1800418ae  mov     [rbp+57h+arg_8], esi
0x1800418b1  jmp     loc_180041E3C
0x1800418b6  mov     rdx, [rbp+57h+var_60]
0x1800418ba  mov     r8d, [rdi+2DCh]
0x1800418c1  mov     eax, ebx
0x1800418c3  mov     [rbp+57h+arg_18], 0
0x1800418ca  mov     [rbp+57h+var_78], 0
0x1800418d1  lea     rax, [rax+rax*4]
0x1800418d5  mov     rdx, [rdx+rax*4]
0x1800418d9  mov     r12d, [r12+rax*4+8]
0x1800418de  mov     rcx, rdx
0x1800418e1  shr     rcx, 20h
0x1800418e5  add     rcx, [rdi]
0x1800418e8  mov     [rbp+57h+var_58], rax
0x1800418ec  mov     [rbp+57h+var_80], rdx
0x1800418f0  call    ComputeCrc32Checksum
0x1800418f5  mov     [rsp+0D0h+var_90], rdi
0x1800418fa  mov     r9d, 4
0x180041900  mov     [rdi+2DCh], eax
0x180041906  mov     edx, r12d
0x180041909  mov     [rsp+0D0h+var_98], 0
0x180041911  lea     rax, [rbp+57h+arg_0]
0x180041915  mov     [rsp+0D0h+var_A0], rax
0x18004191a  mov     ecx, r14d
0x18004191d  lea     rax, [rbp+57h+var_78]
0x180041921  mov     [rsp+0D0h+var_A8], 0
0x18004192a  lea     r8d, [r9+54h]
0x18004192e  mov     [rsp+0D0h+var_B0], rax
0x180041933  call    BexchangeArbDataInFOATNode
0x180041938  xor     r11d, r11d
0x18004193b  test    eax, eax
0x18004193d  jz      short loc_180041958
0x18004193f  cmp     [rbp+57h+arg_0], r11d
0x180041943  jz      short loc_180041958
0x180041945  cmp     [rbp+57h+var_78], 1
0x180041949  jnz     short loc_180041958
0x18004194b  lea     edx, [r11+6]
0x18004194f  lea     rcx, aTrue_0; " TRUE "
0x180041956  jmp     short loc_180041964
0x180041958  mov     edx, 7
0x18004195d  lea     rcx, aFalse_0; " FALSE "
0x180041964  mov     r8d, [rdi+2DCh]
0x18004196b  call    ComputeCrc32Checksum
0x180041970  mov     [rsp+0D0h+var_90], rdi
0x180041975  mov     r9d, 8
0x18004197b  mov     [rsp+0D0h+var_98], r11d
0x180041980  mov     edx, r12d
0x180041983  mov     [rdi+2DCh], eax
0x180041989  mov     ecx, r14d
0x18004198c  lea     rax, [rbp+57h+arg_0]
0x180041990  mov     [rsp+0D0h+var_A0], rax
0x180041995  lea     r8d, [r9+5Ch]
0x180041999  lea     rax, [rbp+57h+var_80]
0x18004199d  mov     [rsp+0D0h+var_A8], rax
0x1800419a2  mov     [rsp+0D0h+var_B0], r11
0x1800419a7  call    BexchangeArbDataInFOATNode
0x1800419ac  test    eax, eax
0x1800419ae  jz      loc_180041EC8
0x1800419b4  cmp     [rbp+57h+var_70], 0
0x1800419b8  jz      short loc_1800419C7
0x1800419ba  mov     ecx, [rbp+57h+var_74]
0x1800419bd  inc     ecx
0x1800419bf  add     ecx, dword ptr [rbp+57h+var_80]
0x1800419c2  mov     [rbp+57h+var_74], ecx
0x1800419c5  jmp     short loc_1800419D4
0x1800419c7  mov     eax, dword ptr [rbp+57h+var_80]
0x1800419ca  inc     eax
0x1800419cc  cmp     esi, eax
0x1800419ce  cmovb   esi, eax
0x1800419d1  mov     [rbp+57h+arg_8], esi
0x1800419d4  mov     ecx, [r13+0]
0x1800419d8  sub     ecx, 1
0x1800419db  jz      short loc_180041A35
0x1800419dd  sub     ecx, 2
0x1800419e0  jz      short loc_180041A2E
0x1800419e2  sub     ecx, 1
0x1800419e5  jz      short loc_180041A27
0x1800419e7  sub     ecx, 1
0x1800419ea  jz      short loc_180041A20
0x1800419ec  sub     ecx, 3
0x1800419ef  jz      short loc_180041A19
0x1800419f1  sub     ecx, 1
0x1800419f4  jz      short loc_180041A12
0x1800419f6  sub     ecx, 1
0x1800419f9  jz      short loc_180041A09
0x1800419fb  cmp     ecx, 2
0x1800419fe  jnz     loc_180041E2F
0x180041a04  lea     esi, [rcx+28h]
0x180041a07  jmp     short loc_180041A3A
0x180041a09  mov     esi, 29h ; ')'
0x180041a0e  xor     ebx, ebx
0x180041a10  jmp     short loc_180041A3F
0x180041a12  mov     esi, 28h ; '('
0x180041a17  jmp     short loc_180041A0E
0x180041a19  mov     esi, 27h ; '''
0x180041a1e  jmp     short loc_180041A0E
0x180041a20  mov     esi, 24h ; '$'
0x180041a25  jmp     short loc_180041A3A
0x180041a27  mov     esi, 25h ; '%'
0x180041a2c  jmp     short loc_180041A3A
0x180041a2e  mov     esi, 26h ; '&'
0x180041a33  jmp     short loc_180041A0E
0x180041a35  mov     esi, 23h ; '#'
0x180041a3a  mov     ebx, 1
0x180041a3f  mov     r9d, ebx
0x180041a42  mov     [rsp+0D0h+var_B0], rdi
0x180041a47  mov     r8d, esi
0x180041a4a  lea     rdx, [rbp+57h+arg_18]
0x180041a4e  lea     rcx, [rbp+57h+var_80]
0x180041a52  call    BIdentifyConstantString
0x180041a57  test    eax, eax
0x180041a59  jz      loc_180041CAB
0x180041a5f  mov     [rsp+0D0h+var_90], rdi
0x180041a64  lea     rax, [rbp+57h+arg_0]
0x180041a68  mov     [rsp+0D0h+var_98], 0
0x180041a70  mov     r9d, 4
0x180041a76  mov     [rsp+0D0h+var_A0], rax
0x180041a7b  mov     r8d, 168h
0x180041a81  lea     rax, [rbp+57h+arg_18]
0x180041a85  mov     edx, r12d
0x180041a88  mov     [rsp+0D0h+var_A8], rax
0x180041a8d  mov     ecx, r14d
0x180041a90  mov     [rsp+0D0h+var_B0], 0
0x180041a99  call    BexchangeArbDataInFOATNode
0x180041a9e  test    eax, eax
0x180041aa0  jz      loc_180041EC8
0x180041aa6  cmp     esi, 23h ; '#'
0x180041aa9  jnz     loc_180041E2C
0x180041aaf  mov     esi, [rbp+57h+arg_18]
0x180041ab2  cmp     esi, 100h
0x180041ab8  jnb     loc_180041E2C
0x180041abe  mov     [rbp+57h+arg_18], 1
0x180041ac5  cmp     esi, 1
0x180041ac8  jnz     short loc_180041AF6
0x180041aca  mov     rbx, [rdi+18h]
0x180041ace  lea     eax, [rsi+3]
0x180041ad1  mov     r9d, eax
0x180041ad4  mov     [rsp+0D0h+var_B0], rdi
0x180041ad9  mov     r8d, eax
0x180041adc  lea     rdx, [rbp+57h+arg_18]
0x180041ae0  lea     rcx, [rbx+1C8h]
0x180041ae7  call    BwriteToHeap
0x180041aec  bts     dword ptr [rbx+1C8h], 1Fh
0x180041af4  jmp     short loc_180041B25
0x180041af6  cmp     esi, 9
0x180041af9  jnz     short loc_180041B25
0x180041afb  mov     rbx, [rdi+18h]
0x180041aff  lea     eax, [rsi-5]
0x180041b02  mov     r9d, eax
0x180041b05  mov     [rsp+0D0h+var_B0], rdi
0x180041b0a  mov     r8d, eax
0x180041b0d  lea     rdx, [rbp+57h+arg_18]
0x180041b11  lea     rcx, [rbx+1CCh]
0x180041b18  call    BwriteToHeap
0x180041b1d  bts     dword ptr [rbx+1CCh], 1Fh
0x180041b25  xor     r11d, r11d
0x180041b28  lea     rdx, aPaperDimensions
  ... truncated ...
```
