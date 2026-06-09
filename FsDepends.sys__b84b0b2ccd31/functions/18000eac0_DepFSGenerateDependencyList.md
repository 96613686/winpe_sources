# DepFSGenerateDependencyList

- ea: `0x18000eac0`
- end: `0x18000f2df`
- name: `DepFSGenerateDependencyList`
- size: `2079`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x180008010`
- `0x1800084f4`
- `0x180009840`
- `0x18000a874`
- `0x18000b450`
- `0x18000b5f0`
- `0x18000ce60`
- `0x18000fa10`

## callees

- `0x180001150`
- `0x180001544`
- `0x18000eac0`
- `0x18000f73c`
- `0x18000f91c`
- `0x18000f970`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x18000f237`
- `ntoskrnl!KeBugCheck` at `0x18000f237`
- `ntoskrnl!ExAllocatePool2` at `0x18000eb3a`
- `ntoskrnl!ExAllocatePool2` at `0x18000eb3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eb65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eba9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f2b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eb65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eba9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f2b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f27e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f27e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000eb59`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000eb9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000f2aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000eb59`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000eb9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000f2aa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000eb0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000eb0f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000eafe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000eafe`

## pseudocode

```c
__int64 __fastcall DepFSGenerateDependencyList(__int64 a1, __int64 *a2, int a3, __int64 *a4, char a5, __int16 a6)
{
  unsigned int v10; // esi
  __int64 Pool2; // rax
  _DWORD *v12; // rbx
  bool v14; // zf
  int v15; // edx
  int v16; // r10d
  unsigned int v17; // r15d
  _QWORD *v18; // rsi
  _DWORD *v19; // rdi
  int v20; // eax
  unsigned int i; // edi
  __int16 v22; // ax
  __int64 v23; // rcx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 *v27; // r8
  int v28; // ebp
  bool v29; // dl
  __int64 *v30; // rcx
  __int64 v31; // rdx
  __int64 *v32; // rsi
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // r12
  __int64 v36; // r13
  _QWORD *v37; // r14
  _QWORD *v38; // rdi
  unsigned int v39; // edx
  char v40; // r9
  unsigned __int16 v41; // ax
  __int64 v42; // rsi
  _QWORD *v43; // rsi
  _DWORD *v44; // rdi
  unsigned int v45; // edx
  char v46; // r9
  unsigned int v47; // eax
  __int64 v48; // rcx
  int v49; // eax
  bool v50; // sf
  int v51; // [rsp+30h] [rbp-48h]
  unsigned int v52; // [rsp+34h] [rbp-44h]

  if ( !a5 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
  }
  v10 = 16 * (dword_180005180 + dword_180005190) + 8;
  Pool2 = ExAllocatePool2(256, v10, 1816424516);
  *a4 = Pool2;
  v12 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( !a5 )
    {
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
    }
    return 3221225626LL;
  }
  *(_WORD *)Pool2 = 12352;
  *(_WORD *)(Pool2 + 2) = v10;
  v14 = dword_180005180 + dword_180005190 == 0;
  v15 = dword_180005180 + dword_180005190;
  *(_DWORD *)(Pool2 + 4) = dword_180005180 + dword_180005190;
  if ( v14 )
  {
    if ( !a5 )
    {
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
    }
    return 0;
  }
  v16 = 0;
  v17 = v15 - 1;
  v51 = 0;
  if ( a1 )
  {
    v18 = *(_QWORD **)(a1 + 24);
    while ( v18 != (_QWORD *)(a1 + 24) )
    {
      v19 = (_DWORD *)*(v18 - 3);
      v18 = (_QWORD *)*v18;
      v20 = ReferenceVolumeContext(v19);
      v51 = v20;
      v16 = v20;
      if ( v20 >= 0 )
      {
        v23 = 2LL * v17;
        *(_QWORD *)&v12[2 * v23 + 4] = v19;
        v12[2 * v23 + 2] = 1;
        if ( (v19[14] & 2) != 0 )
          LOWORD(v12[4 * v17 + 2]) = 17;
        if ( (*(_DWORD *)(a1 + 92) & 0x20) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids, a1, v19);
            v16 = v51;
          }
          v19[14] |= 0x20u;
          if ( (v19[14] & 2) != 0 )
LABEL_125:
            KeBugCheck(0x22u);
        }
        --v17;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dqq(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
            (unsigned int)v20,
            a1,
            v19);
          v16 = v51;
        }
        if ( (a6 & 0x8000) == 0 )
          goto LABEL_19;
      }
    }
LABEL_72:
    v34 = v12[1] - 1;
    v52 = v34;
    if ( (v34 & 0x80000000) == 0 )
    {
      do
      {
        v35 = 2LL * v34;
        v36 = *(_QWORD *)&v12[4 * v34 + 4];
        if ( !v36 )
          break;
        if ( (v12[4 * v34 + 2] & 1) != 0 )
        {
          v37 = *(_QWORD **)(v36 + 8);
          while ( v37 != (_QWORD *)(v36 + 8) )
          {
            v38 = v37 - 1;
            v37 = (_QWORD *)*v37;
            if ( (*((_DWORD *)v38 + 23) & 0x10) == 0 )
            {
              v39 = v17 + 1;
              v40 = 1;
              if ( v17 + 1 >= v12[1] )
                goto LABEL_84;
              do
              {
                if ( *(_QWORD **)&v12[4 * v39 + 4] == v38 )
                {
                  v40 = 0;
                  v41 = HIWORD(v12[4 * v39 + 2]);
                  if ( v41 <= HIWORD(v12[2 * v35 + 2]) )
                    v41 = HIWORD(v12[2 * v35 + 2]);
                  HIWORD(v12[4 * v39 + 2]) = v41;
                }
                ++v39;
              }
              while ( v39 < v12[1] );
              if ( v40 )
              {
LABEL_84:
                v42 = 4LL * v17;
                *(_QWORD *)&v12[v42 + 4] = v38;
                LOWORD(v12[v42 + 2]) = 2;
                if ( (*((_DWORD *)v38 + 15) & 0x30) != 0 )
                  LOWORD(v12[v42 + 2]) = 18;
                if ( (*(_DWORD *)(v36 + 56) & 0x20) != 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_qq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      18,
                      WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
                      v38,
                      v36);
                  }
                  *((_DWORD *)v38 + 23) |= 0x20u;
                }
                HIWORD(v12[v42 + 2]) = HIWORD(v12[2 * v35 + 2]);
                if ( (a6 & 0x100) != 0 )
                {
                  _InterlockedAdd((volatile signed __int32 *)v38 + 24, 1u);
                  LOWORD(v12[v42 + 2]) |= 0x100u;
                }
                ++*((_DWORD *)v38 + 14);
                --v17;
              }
            }
          }
        }
        else
        {
          v43 = *(_QWORD **)(v36 + 24);
          while ( v43 != (_QWORD *)(v36 + 24) )
          {
            v44 = (_DWORD *)*(v43 - 3);
            v45 = v17 + 1;
            v46 = 1;
            v43 = (_QWORD *)*v43;
            if ( v17 + 1 < v12[1] )
            {
              do
              {
                if ( *(_DWORD **)&v12[4 * v45 + 4] == v44 )
                {
                  v47 = HIWORD(v12[4 * v45 + 2]);
                  v46 = 0;
                  if ( v47 <= (unsigned int)HIWORD(v12[2 * v35 + 2]) + 1 )
                    LOWORD(v47) = HIWORD(v12[2 * v35 + 2]) + 1;
                  HIWORD(v12[4 * v45 + 2]) = v47;
                }
                ++v45;
              }
              while ( v45 < v12[1] );
              if ( !v46 )
                continue;
            }
            v51 = ReferenceVolumeContext(v44);
            if ( v51 >= 0 )
            {
              v48 = 2LL * v17;
              *(_QWORD *)&v12[2 * v48 + 4] = v44;
              LOWORD(v12[2 * v48 + 2]) = 1;
              HIWORD(v12[2 * v48 + 2]) = HIWORD(v12[2 * v35 + 2]) + 1;
              if ( (v44[14] & 2) != 0 )
                LOWORD(v12[4 * v17 + 2]) = 17;
              if ( (*(_DWORD *)(v36 + 92) & 0x20) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    20,
                    WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
                    v36,
                    v44);
                }
                v49 = v44[14] | 0x20;
                v44[14] = v49;
                if ( (v49 & 2) != 0 )
                  goto LABEL_125;
              }
              --v17;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_Dqq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
                  (unsigned int)v51,
                  a1,
                  v44);
              }
              if ( (a6 & 0x8000) == 0 )
                goto LABEL_19;
            }
          }
        }
        v50 = (int)(v52 - 1) < 0;
        v34 = v52 - 1;
        v16 = v51;
        --v52;
      }
      while ( !v50 );
    }
    if ( v16 < 0 )
      goto LABEL_40;
    goto LABEL_132;
  }
  if ( a2 )
  {
    v51 = ReferenceVolumeContext(a2);
    v16 = v51;
    if ( v51 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = 16;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    v26 = 2LL * v17;
    *(_QWORD *)&v12[2 * v26 + 4] = a2;
    v12[2 * v26 + 2] = 1;
    if ( (a2[7] & 2) != 0 )
      LOWORD(v12[4 * v17 + 2]) = 17;
    --v17;
    goto LABEL_72;
  }
  if ( a3 )
  {
    v27 = (__int64 *)qword_1800051B0;
    if ( (__int64 *)qword_1800051B0 != &qword_1800051B0 )
    {
      v28 = a3 & 0x11;
      do
      {
        v29 = 0;
        v30 = v27 - 5;
        v27 = (__int64 *)*v27;
        if ( v28 )
          v29 = (*((_BYTE *)v30 + 60) & 8) != 0;
        if ( (*((_DWORD *)v30 + 23) & 0x10) == 0 && v29 )
        {
          v31 = 16LL * v17;
          *(_QWORD *)(v31 + Pool2 + 16) = v30;
          *(_WORD *)(v31 + Pool2 + 8) = 2;
          if ( (*((_DWORD *)v30 + 15) & 0x30) != 0 )
            *(_WORD *)(v31 + Pool2 + 8) = 18;
          *(_WORD *)(v31 + Pool2 + 10) = 0;
          if ( (a6 & 0x100) != 0 )
          {
            _InterlockedAdd((volatile signed __int32 *)v30 + 24, 1u);
            *(_WORD *)(v31 + Pool2 + 8) |= 0x100u;
          }
          ++*((_DWORD *)v30 + 14);
          --v17;
        }
      }
      while ( v27 != &qword_1800051B0 );
      v16 = 0;
    }
    goto LABEL_72;
  }
  v32 = (__int64 *)qword_1800051A0;
  if ( (__int64 *)qword_1800051A0 == &qword_1800051A0 )
    goto LABEL_72;
  while ( 1 )
  {
    a2 = v32 - 5;
    v32 = (__int64 *)*v32;
    if ( (__int64 *)a2[3] == a2 + 3 )
      break;
LABEL_66:
    if ( v32 == &qword_1800051A0 )
      goto LABEL_72;
  }
  v51 = ReferenceVolumeContext(a2);
  v16 = v51;
  if ( v51 >= 0 )
  {
    v33 = 2LL * v17;
    *(_QWORD *)&v12[2 * v33 + 4] = a2;
    v12[2 * v33 + 2] = 1;
    if ( (a2[7] & 2) != 0 )
      LOWORD(v12[4 * v17 + 2]) = 17;
    --v17;
    goto LABEL_66;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v25 = 17;
LABEL_39:
    WPP_SF_Dqq(v24->AttachedDevice, v25, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids, (unsigned int)v16, 0, a2);
  }
LABEL_40:
  if ( (a6 & 0x8000) == 0 )
  {
LABEL_19:
    for ( i = 0; i < v12[1]; ++i )
    {
      v22 = v12[4 * i + 2];
      if ( (v22 & 1) != 0 )
      {
        DereferenceVolumeContext(*(_QWORD *)&v12[4 * i + 4]);
      }
      else if ( (v22 & 2) != 0 )
      {
        if ( (a6 & 0x100) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v12[4 * i + 4] + 96LL));
        DereferenceDependencyContext(*(PVOID *)&v12[4 * i + 4]);
      }
    }
    ExFreePoolWithTag(v12, 0x6C447044u);
    *a4 = 0;
  }
LABEL_132:
  if ( !a5 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v51;
}

```

## disassembly

```asm
0x18000eac0  mov     [rsp+arg_8], rbx
0x18000eac5  mov     [rsp+arg_18], r9
0x18000eaca  mov     [rsp+arg_0], rcx
0x18000eacf  push    rbp
0x18000ead0  push    rsi
0x18000ead1  push    rdi
0x18000ead2  push    r12
0x18000ead4  push    r13
0x18000ead6  push    r14
0x18000ead8  push    r15
0x18000eada  sub     rsp, 40h
0x18000eade  mov     r14b, [rsp+78h+arg_20]
0x18000eae6  lea     r12, Resource
0x18000eaed  mov     r15, r9
0x18000eaf0  mov     ebp, r8d
0x18000eaf3  mov     rdi, rdx
0x18000eaf6  mov     r13, rcx
0x18000eaf9  test    r14b, r14b
0x18000eafc  jnz     short loc_18000EB1B
0x18000eafe  call    cs:__imp_KeEnterCriticalRegion
0x18000eb05  nop     dword ptr [rax+rax+00h]
0x18000eb0a  mov     dl, 1; Wait
0x18000eb0c  mov     rcx, r12; Resource
0x18000eb0f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000eb16  nop     dword ptr [rax+rax+00h]
0x18000eb1b  mov     esi, cs:dword_180005190
0x18000eb21  mov     ecx, 100h
0x18000eb26  add     esi, cs:dword_180005180
0x18000eb2c  mov     r8d, 6C447044h
0x18000eb32  shl     esi, 4
0x18000eb35  add     esi, 8
0x18000eb38  mov     edx, esi
0x18000eb3a  call    cs:__imp_ExAllocatePool2
0x18000eb41  nop     dword ptr [rax+rax+00h]
0x18000eb46  mov     [r15], rax
0x18000eb49  mov     rbx, rax
0x18000eb4c  test    rax, rax
0x18000eb4f  jnz     short loc_18000EB7B
0x18000eb51  test    r14b, r14b
0x18000eb54  jnz     short loc_18000EB71
0x18000eb56  mov     rcx, r12; Resource
0x18000eb59  call    cs:__imp_ExReleaseResourceLite
0x18000eb60  nop     dword ptr [rax+rax+00h]
0x18000eb65  call    cs:__imp_KeLeaveCriticalRegion
0x18000eb6c  nop     dword ptr [rax+rax+00h]
0x18000eb71  mov     eax, 0C000009Ah
0x18000eb76  jmp     loc_18000F2C6
0x18000eb7b  mov     word ptr [rax], 3040h
0x18000eb80  mov     [rax+2], si
0x18000eb84  mov     edx, cs:dword_180005190
0x18000eb8a  add     edx, cs:dword_180005180
0x18000eb90  mov     [rax+4], edx
0x18000eb93  jnz     short loc_18000EBBC
0x18000eb95  test    r14b, r14b
0x18000eb98  jnz     short loc_18000EBB5
0x18000eb9a  mov     rcx, r12; Resource
0x18000eb9d  call    cs:__imp_ExReleaseResourceLite
0x18000eba4  nop     dword ptr [rax+rax+00h]
0x18000eba9  call    cs:__imp_KeLeaveCriticalRegion
0x18000ebb0  nop     dword ptr [rax+rax+00h]
0x18000ebb5  xor     eax, eax
0x18000ebb7  jmp     loc_18000F2C6
0x18000ebbc  xor     r10d, r10d
0x18000ebbf  lea     r15d, [rdx-1]
0x18000ebc3  or      r14d, 0FFFFFFFFh
0x18000ebc7  mov     [rsp+78h+var_48], r10d
0x18000ebcc  lea     r12, WPP_GLOBAL_Control
0x18000ebd3  lea     esi, [r10+2]
0x18000ebd7  test    r13, r13
0x18000ebda  jz      loc_18000ED32
0x18000ebe0  lea     r14, [r13+18h]
0x18000ebe4  mov     rsi, [r14]
0x18000ebe7  lea     ebp, [r10+1]
0x18000ebeb  cmp     rsi, r14
0x18000ebee  jz      loc_18000EF36
0x18000ebf4  mov     rdi, [rsi-18h]
0x18000ebf8  xor     edx, edx
0x18000ebfa  mov     rsi, [rsi]
0x18000ebfd  mov     rcx, rdi; Context
0x18000ec00  call    ReferenceVolumeContext
0x18000ec05  mov     [rsp+78h+var_48], eax
0x18000ec09  mov     r10d, eax
0x18000ec0c  test    eax, eax
0x18000ec0e  jns     loc_18000ECA4
0x18000ec14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1b  mov     r11d, 2
0x18000ec21  cmp     rcx, r12
0x18000ec24  jz      short loc_18000EC60
0x18000ec26  mov     edx, [rcx+2Ch]
0x18000ec29  test    bpl, dl
0x18000ec2c  jz      short loc_18000EC60
0x18000ec2e  cmp     [rcx+29h], r11b
0x18000ec32  jb      short loc_18000EC60
0x18000ec34  mov     rcx, [rcx+18h]
0x18000ec38  lea     edx, [r11+0Ch]
0x18000ec3c  mov     [rsp+78h+var_50], rdi
0x18000ec41  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000ec48  mov     r9d, eax
0x18000ec4b  mov     [rsp+78h+var_58], r13
0x18000ec50  call    WPP_SF_Dqq
0x18000ec55  mov     r10d, [rsp+78h+var_48]
0x18000ec5a  mov     r11d, 2
0x18000ec60  test    [rsp+78h+arg_28], 8000h
0x18000ec6b  jnz     loc_18000ED24
0x18000ec71  mov     r12d, 100h
0x18000ec77  xor     edi, edi
0x18000ec79  cmp     [rbx+4], edi
0x18000ec7c  jbe     loc_18000F276
0x18000ec82  mov     ecx, edi
0x18000ec84  add     rcx, rcx
0x18000ec87  movzx   eax, word ptr [rbx+rcx*8+8]
0x18000ec8c  test    bpl, al
0x18000ec8f  jz      loc_18000F244
0x18000ec95  mov     rcx, [rbx+rcx*8+10h]
0x18000ec9a  call    DereferenceVolumeContext
0x18000ec9f  jmp     loc_18000F26B
0x18000eca4  mov     ecx, r15d
0x18000eca7  mov     r11d, 2
0x18000ecad  add     rcx, rcx
0x18000ecb0  mov     [rbx+rcx*8+10h], rdi
0x18000ecb5  mov     [rbx+rcx*8+8], ebp
0x18000ecb9  mov     eax, [rdi+38h]
0x18000ecbc  test    r11b, al
0x18000ecbf  jz      short loc_18000ECC8
0x18000ecc1  mov     word ptr [rbx+rcx*8+8], 11h
0x18000ecc8  mov     eax, [r13+5Ch]
0x18000eccc  test    al, 20h
0x18000ecce  jz      short loc_18000ED21
0x18000ecd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecd7  cmp     rcx, r12
0x18000ecda  jz      short loc_18000ED11
0x18000ecdc  mov     eax, [rcx+2Ch]
0x18000ecdf  test    al, 20h
0x18000ece1  jz      short loc_18000ED11
0x18000ece3  cmp     byte ptr [rcx+29h], 4
0x18000ece7  jb      short loc_18000ED11
0x18000ece9  mov     rcx, [rcx+18h]
0x18000eced  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000ecf4  mov     edx, 0Fh
0x18000ecf9  mov     [rsp+78h+var_58], rdi
0x18000ecfe  mov     r9, r13
0x18000ed01  call    WPP_SF_qq
0x18000ed06  mov     r10d, [rsp+78h+var_48]
0x18000ed0b  mov     r11d, 2
0x18000ed11  or      dword ptr [rdi+38h], 20h
0x18000ed15  mov     eax, [rdi+38h]
0x18000ed18  test    r11b, al
0x18000ed1b  jnz     loc_18000F232
0x18000ed21  dec     r15d
0x18000ed24  cmp     rsi, r14
0x18000ed27  jnz     loc_18000EBF4
0x18000ed2d  jmp     loc_18000EF3C
0x18000ed32  test    rdi, rdi
0x18000ed35  jz      loc_18000EDE4
0x18000ed3b  xor     edx, edx
0x18000ed3d  mov     rcx, rdi; Context
0x18000ed40  call    ReferenceVolumeContext
0x18000ed45  mov     [rsp+78h+var_48], eax
0x18000ed49  mov     r10d, eax
0x18000ed4c  test    eax, eax
0x18000ed4e  jns     short loc_18000EDB6
0x18000ed50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed57  lea     rax, WPP_GLOBAL_Control
0x18000ed5e  mov     ebp, 1
0x18000ed63  cmp     rcx, rax
0x18000ed66  jz      short loc_18000ED9A
0x18000ed68  mov     eax, [rcx+2Ch]
0x18000ed6b  test    bpl, al
0x18000ed6e  jz      short loc_18000ED9A
0x18000ed70  cmp     [rcx+29h], sil
0x18000ed74  jb      short loc_18000ED9A
0x18000ed76  lea     edx, [rbp+0Fh]
0x18000ed79  mov     rcx, [rcx+18h]
0x18000ed7d  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000ed84  mov     [rsp+78h+var_50], rdi
0x18000ed89  mov     r9d, r10d
0x18000ed8c  mov     [rsp+78h+var_58], 0
0x18000ed95  call    WPP_SF_Dqq
0x18000ed9a  mov     r12d, 100h
0x18000eda0  test    [rsp+78h+arg_28], 8000h
0x18000edab  jnz     loc_18000F299
0x18000edb1  jmp     loc_18000EC77
0x18000edb6  mov     ecx, r15d
0x18000edb9  mov     ebp, 1
0x18000edbe  add     rcx, rcx
0x18000edc1  mov     [rbx+rcx*8+10h], rdi
0x18000edc6  mov     [rbx+rcx*8+8], ebp
0x18000edca  mov     eax, [rdi+38h]
0x18000edcd  test    sil, al
0x18000edd0  jz      short loc_18000EDD9
0x18000edd2  mov     word ptr [rbx+rcx*8+8], 11h
0x18000edd9  add     r15d, r14d
0x18000eddc  mov     r11d, esi
0x18000eddf  jmp     loc_18000EF3C
0x18000ede4  test    ebp, ebp
0x18000ede6  jz      loc_18000EE88
0x18000edec  mov     r8, cs:qword_1800051B0
0x18000edf3  lea     r9, qword_1800051B0
0x18000edfa  mov     r12d, 100h
0x18000ee00  cmp     r8, r9
0x18000ee03  jz      short loc_18000EE7B
0x18000ee05  and     ebp, 11h
0x18000ee08  mov     r10d, 1
0x18000ee0e  xor     dl, dl
0x18000ee10  lea     rcx, [r8-28h]
0x18000ee14  mov     r8, [r8]
0x18000ee17  test    ebp, ebp
0x18000ee19  jz      short loc_18000EE26
0x18000ee1b  test    byte ptr [rcx+3Ch], 8
0x18000ee1f  movzx   edx, dl
0x18000ee22  cmovnz  edx, r10d
0x18000ee26  mov     eax, [rcx+5Ch]
0x18000ee29  test    al, 10h
0x18000ee2b  jnz     short loc_18000EE73
0x18000ee2d  test    dl, dl
0x18000ee2f  jz      short loc_18000EE73
0x18000ee31  mov     edx, r15d
0x18000ee34  shl     rdx, 4
0x18000ee38  mov     [rdx+rbx+10h], rcx
0x18000ee3d  mov     [rdx+rbx+8], si
0x18000ee42  mov     eax, [rcx+3Ch]
0x18000ee45  test    al, 30h
0x18000ee47  jz      short loc_18000EE50
0x18000ee49  mov     word ptr [rdx+rbx+8], 12h
0x18000ee50  xor     eax, eax
0x18000ee52  mov     [rdx+rbx+0Ah], ax
0x18000ee57  test    [rsp+78h+arg_28], r12d
0x18000ee5f  jz      short loc_18000EE6C
0x18000ee61  lock add [rcx+60h], r10d
0x18000ee66  or      [rdx+rbx+8], r12w
0x18000ee6c  add     [rcx+38h], r10d
0x18000ee70  add     r15d, r14d
0x18000ee73  cmp     r8, r9
0x18000ee76  jnz     short loc_18000EE0E
0x18000ee78  xor     r10d, r10d
0x18000ee7b  mov     ebp, 1
0x18000ee80  mov     r11d, esi
0x18000ee83  jmp     loc_18000EF42
0x18000ee88  mov     rsi, cs:qword_1800051A0
0x18000ee8f  lea     r14, qword_1800051A0
0x18000ee96  mov     ebp, 1
0x18000ee9b  cmp     rsi, r14
0x18000ee9e  jz      loc_18000EF36
0x18000eea4  lea     rdi, [rsi-28h]
0x18000eea8  mov     rsi, [rsi]
0x18000eeab  lea     rax, [rdi+18h]
0x18000eeaf  cmp     [rax], rax
0x18000eeb2  jnz     short loc_18000EEF2
0x18000eeb4  xor     edx, edx
0x18000eeb6  mov     rcx, rdi; Context
0x18000eeb9  call    ReferenceVolumeContext
0x18000eebe  mov     [rsp+78h+var_48], eax
0x18000eec2  mov     r10d, eax
0x18000eec5  test    eax, eax
0x18000eec7  js      short loc_18000EEFF
0x18000eec9  mov     ecx, r15d
0x18000eecc  mov     r11d, 2
0x18000eed2  add     rcx, rcx
0x18000eed5  mov     [rbx+rcx*8+10h], rdi
0x18000eeda  mov     [rbx+rcx*8+8], ebp
0x18000eede  mov     eax, [rdi+38h]
0x18000eee1  test    r11b, al
0x18000eee4  jz      short loc_18000EEED
0x18000eee6  mov     word ptr [rbx+rcx*8+8], 11h
0x18000eeed  dec     r15d
0x18000eef0  jmp     short loc_18000EEF8
0x18000eef2  mov     r11d, 2
0x18000eef8  cmp     rsi, r14
0x18000eefb  jnz     short loc_18000EEA4
0x18000eefd  jmp     short loc_18000EF3C
0x18000eeff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef06  lea     rax, WPP_GLOBAL_Control
0x18000ef0d  cmp     rcx, rax
0x18000ef10  jz      loc_18000ED9A
0x18000ef16  mov     eax, [rcx+2Ch]
0x18000ef19  test    bpl, al
0x18000ef1c  jz      loc_18000ED9A
0x18000ef22  cmp     byte ptr [rcx+29h], 2
0x18000ef26  jb      loc_18000ED9A
0x18000ef2c  mov     edx, 11h
0x18000ef31  jmp     loc_18000ED79
0x18000ef36  mov     r11d, 2
0x18000ef3c  mov     r12d, 100h
0x18000ef42  mov     eax, [rbx+4]
0x18000ef45  sub     eax, ebp
0x18000ef47  mov     [rsp+78h+var_44], eax
0x18000ef4b  js      loc_18000F228
0x18000ef51  mov     r12d, eax
0x18000ef54  add     r12, r12
0x18000ef57  mov     r13, [rbx+r12*8+10h]
0x18000ef5c  test    r13, r13
0x18000ef5f  jz      loc_18000F222
0x18000ef65  mov     r10d, 1
0x18000ef6b  test    [rbx+r12*8+8], r10b
0x18000ef70  jz      loc_18000F084
0x18000ef76  lea     rbp, [r13+8]
0x18000ef7a  mov     r14, [rbp+0]
0x18000ef7e  jmp     loc_18000F076
0x18000ef83  lea     rdi, [r14-8]
0x18000ef87  mov     r14, [r14]
  ... truncated ...
```
