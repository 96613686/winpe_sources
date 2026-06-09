# UlpOpenCoupling

- ea: `0x14003deb0`
- end: `0x14003e638`
- name: `UlpOpenCoupling`
- size: `1928`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003cdc0`
- `0x140071234`

## callees

- `0x14000a350`
- `0x14003deb0`
- `0x140049d08`
- `0x1400513f0`
- `0x1400705d0`
- `0x140087a50`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c5c10`
- `0x1401d9f54`
- `0x1401da2b4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003e063`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003e063`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003dfb9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e3e0`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e498`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003dfb9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e3e0`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003e498`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e135`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e5e9`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e135`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x14003e5e9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003e4c2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003e4c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003dfc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e2a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e314`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003dfc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e2a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e314`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e3ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4a4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003df10`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003df10`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14003e308`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14003e308`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e296`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e3be`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e296`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003e3be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e18b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e331`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e18b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003e331`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e104`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003e104`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003def8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e17a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e320`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003def8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e17a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e320`

## pseudocode

```c
__int64 __fastcall UlpOpenCoupling(__int64 a1, ULONG_PTR a2, char **a3)
{
  volatile signed __int32 *v3; // r15
  __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int Coupling; // esi
  _QWORD *v11; // r8
  _QWORD *v12; // r14
  _QWORD *v13; // rdi
  volatile signed __int32 *v14; // rdx
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  char *v17; // r9
  volatile signed __int32 LockArray_high; // esi
  unsigned __int64 v20; // rdi
  volatile signed __int32 *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rcx
  _QWORD *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  char *v30; // rdx
  int v31; // eax
  __int64 v32; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v34; // rax
  _QWORD *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  char v38; // [rsp+80h] [rbp+8h] BYREF
  char **v39; // [rsp+90h] [rbp+18h]
  PVOID Entry; // [rsp+98h] [rbp+20h] BYREF

  v39 = a3;
  v3 = 0;
  Entry = 0;
  v38 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v28 = *(_QWORD *)(a1 + 48);
    else
      v28 = 0;
    WPP_SF_qqqi(1032, 27, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, v28, a2, a3);
  }
  KeEnterCriticalRegion();
  v6 = a1 + 944;
  ExAcquirePushLockSharedEx(a1 + 944, 0);
  if ( *(_BYTE *)(a1 + 968) )
    goto LABEL_62;
  Coupling = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qiqqq(v8, v7, v9, a1, *(_QWORD *)(a1 + 48), a2, &v38, &Entry);
  v11 = 0;
  v12 = (_QWORD *)(a1 + 952);
  v13 = *(_QWORD **)(a1 + 952);
  Entry = 0;
  while ( v13 != v12 )
  {
    if ( v13[5] == a2 )
    {
      v14 = (volatile signed __int32 *)v13 - 1;
      do
      {
        v15 = *v14;
        if ( !*v14 )
        {
          v11 = Entry;
          Coupling = -1073741436;
          goto LABEL_14;
        }
        v16 = v15 + 1;
        if ( UxDebugCheckRefcount && v16 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v14, 0xAu, v16);
      }
      while ( v15 != _InterlockedCompareExchange(v14, v16, v15) );
      if ( v13 != (_QWORD *)*v12 && (v38 || (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(a1 + 944, 0)) )
      {
        v38 = 1;
        v34 = *v13;
        if ( *(_QWORD **)(*v13 + 8LL) == v13 )
        {
          v35 = (_QWORD *)v13[1];
          if ( (_QWORD *)*v35 == v13 )
          {
            *v35 = v34;
            *(_QWORD *)(v34 + 8) = v35;
            *v13 = 0;
            v13[1] = 0;
            v36 = *v12;
            if ( *(_QWORD **)(*v12 + 8LL) == v12 )
            {
              *v13 = v36;
              v13[1] = v12;
              *(_QWORD *)(v36 + 8) = v13;
              *v12 = v13;
              goto LABEL_13;
            }
          }
        }
LABEL_37:
        __fastfail(3u);
      }
LABEL_13:
      v11 = v13 - 3;
      Entry = v13 - 3;
      break;
    }
    v13 = (_QWORD *)*v13;
  }
LABEL_14:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_qD(1032, 26, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v11, Coupling);
    v11 = Entry;
  }
  if ( Coupling >= 0 && !v11 )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v21 = (volatile signed __int32 *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0930)(
                                         (unsigned int)dword_1401A0918,
                                         qword_1401A0920,
                                         (unsigned int)dword_1401A0928,
                                         0);
    }
    else if ( UxCompactMode )
    {
      v32 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v21 = (volatile signed __int32 *)PplAllocateFromLookasideListProcessor(v32, CurrentNodeNumber);
    }
    else
    {
      v20 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v20 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v20 + 64);
      v21 = (volatile signed __int32 *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v20 + 64));
    }
    v3 = v21;
    if ( v21 )
    {
      memset((void *)v21, 0, 0xA0u);
      *v3 = LockArray_high;
      *((_DWORD *)v3 + 4) = 1430482005;
      *((_DWORD *)v3 + 5) = 1;
      *((_BYTE *)v3 + 81) = 1;
      *((_QWORD *)v3 + 7) = a1;
      *((_QWORD *)v3 + 8) = a2;
      v22 = _InterlockedIncrement((volatile signed __int32 *)a2);
      if ( UxDebugCheckRefcount && v22 <= -1 )
        UlBugCheckEx(3u, a2, 0xEu, v22);
      v23 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
      if ( UxDebugCheckRefcount && v23 <= -1 )
        UlBugCheckEx(3u, a1 + 40, 0xEu, v23);
      Coupling = 0;
      *((_QWORD *)v3 + 9) = 0;
      *((_QWORD *)v3 + 13) = v3 + 24;
      *((_QWORD *)v3 + 12) = v3 + 24;
      *((_QWORD *)v3 + 15) = v3 + 28;
      *((_QWORD *)v3 + 14) = v3 + 28;
      KeInitializeSpinLock((PKSPIN_LOCK)v3 + 16);
      *((_QWORD *)v3 + 18) = v3 + 34;
      *((_QWORD *)v3 + 17) = v3 + 34;
      *((_DWORD *)v3 + 38) = 0;
      *((_DWORD *)v3 + 39) = -1;
      if ( (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(a1 + 944, 0) )
      {
LABEL_33:
        v38 = 1;
        v24 = _InterlockedIncrement(v3 + 5);
        if ( UxDebugCheckRefcount && v24 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0xAu, v24);
        v25 = *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8LL * *(unsigned __int16 *)(a1 + 56));
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v25, 0);
        if ( !*(_BYTE *)(v25 + 24) )
        {
          v26 = *v12;
          if ( *(_QWORD **)(*v12 + 8LL) != v12 )
            goto LABEL_37;
          *((_QWORD *)v3 + 3) = v26;
          *((_QWORD *)v3 + 4) = v12;
          *(_QWORD *)(v26 + 8) = v3 + 6;
          *v12 = v3 + 6;
          v27 = *(_QWORD **)(v25 + 16);
          if ( *v27 != v25 + 8 )
            goto LABEL_37;
          *((_QWORD *)v3 + 5) = v25 + 8;
          *((_QWORD *)v3 + 6) = v27;
          *v27 = v3 + 10;
          *(_QWORD *)(v25 + 16) = v3 + 10;
          ExReleasePushLockExclusiveEx(v25, 0);
          KeLeaveCriticalRegion();
          Entry = (PVOID)v3;
          v3 = 0;
          goto LABEL_18;
        }
        v29 = _InterlockedDecrement(v3 + 5);
        if ( UxDebugCheckRefcount && v29 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0xAu, v29);
        if ( !v29 )
          UlpFreeCoupling((char *)v3, 0);
        ExReleasePushLockExclusiveEx(v25, 0);
        KeLeaveCriticalRegion();
LABEL_62:
        Coupling = -1073741436;
        ExReleasePushLockEx(v6, 0);
        KeLeaveCriticalRegion();
        goto LABEL_63;
      }
      ExReleasePushLockSharedEx(a1 + 944, 0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 944, 0);
      v38 = 1;
      if ( !*(_BYTE *)(a1 + 968) )
      {
        Coupling = UlpFindCoupling(a1, a2, &v38, &Entry);
        if ( Coupling < 0 || Entry )
          goto LABEL_18;
        goto LABEL_33;
      }
      Coupling = -1073741436;
    }
    else
    {
      Coupling = -1073741670;
    }
    ExReleasePushLockEx(a1 + 944, 0);
    KeLeaveCriticalRegion();
    goto LABEL_63;
  }
LABEL_18:
  ExReleasePushLockEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( Coupling >= 0 )
  {
    v17 = (char *)Entry;
    goto LABEL_20;
  }
LABEL_63:
  v17 = (char *)Entry;
  if ( Entry )
  {
    v30 = (char *)Entry + 20;
    v31 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
    if ( UxDebugCheckRefcount && v31 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v30, 0xAu, v31);
    if ( !v31 )
      UlpFreeCoupling(v17, 0);
    v17 = 0;
    Entry = 0;
  }
LABEL_20:
  if ( v3 )
  {
    v37 = _InterlockedDecrement(v3 + 5);
    if ( UxDebugCheckRefcount && v37 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 1u, v37);
    UlpFreeCoupling((char *)v3, 1u);
    v17 = (char *)Entry;
  }
  *v39 = v17;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 28, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v17, Coupling);
  return (unsigned int)Coupling;
}

```

## disassembly

```asm
0x14003deb0  mov     rax, rsp
0x14003deb3  mov     [rax+18h], r8
0x14003deb7  push    rbx
0x14003deb8  push    rbp
0x14003deb9  push    rdi
0x14003deba  push    r12
0x14003debc  push    r13
0x14003debe  push    r14
0x14003dec0  push    r15
0x14003dec2  sub     rsp, 40h
0x14003dec6  xor     r15d, r15d
0x14003dec9  mov     qword ptr [rax+20h], 0
0x14003ded1  mov     [rax+8], r15b
0x14003ded5  mov     r13, rdx
0x14003ded8  mov     rbx, rcx
0x14003dedb  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003dee2  jnz     loc_14003E1D5
0x14003dee8  mov     edi, 30h ; '0'
0x14003deed  mov     [rsp+78h+arg_8], rsi
0x14003def5  mov     rbp, rbx
0x14003def8  call    cs:__imp_KeEnterCriticalRegion
0x14003deff  nop     dword ptr [rax+rax+00h]
0x14003df04  lea     r12, [rbx+3B0h]
0x14003df0b  xor     edx, edx
0x14003df0d  mov     rcx, r12
0x14003df10  call    cs:__imp_ExAcquirePushLockSharedEx
0x14003df17  nop     dword ptr [rax+rax+00h]
0x14003df1c  mov     r14d, 0FFFFFFFFh
0x14003df22  cmp     [rbx+3C8h], r15b
0x14003df29  jnz     loc_14003E3D6
0x14003df2f  xor     esi, esi
0x14003df31  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003df38  jnz     loc_14003E5A1
0x14003df3e  xor     r8d, r8d
0x14003df41  lea     r14, [rbx+3B8h]
0x14003df48  mov     rdi, [r14]
0x14003df4b  mov     [rsp+78h+Entry], r8
0x14003df53  cmp     rdi, r14
0x14003df56  jz      short loc_14003DF9E
0x14003df58  cmp     [rdi+28h], r13
0x14003df5c  lea     rbp, [rdi-18h]
0x14003df60  jnz     loc_14003E38B
0x14003df66  lea     rdx, [rbp+14h]; BugCheckParameter2
0x14003df6a  mov     eax, [rdx]
0x14003df6c  test    eax, eax
0x14003df6e  jz      loc_14003E20B
0x14003df74  cmp     cs:UxDebugCheckRefcount, sil
0x14003df7b  lea     ecx, [rax+1]
0x14003df7e  jnz     loc_14003E2E6
0x14003df84  lock cmpxchg [rdx], ecx
0x14003df88  jnz     short loc_14003DF6A
0x14003df8a  cmp     rdi, [r14]
0x14003df8d  jnz     loc_14003E5D6
0x14003df93  mov     r8, rbp
0x14003df96  mov     [rsp+78h+Entry], rbp
0x14003df9e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003dfa5  jnz     loc_14003E602
0x14003dfab  test    esi, esi
0x14003dfad  js      short loc_14003DFB4
0x14003dfaf  test    r8, r8
0x14003dfb2  jz      short loc_14003E01D
0x14003dfb4  xor     edx, edx
0x14003dfb6  mov     rcx, r12
0x14003dfb9  call    cs:__imp_ExReleasePushLockEx
0x14003dfc0  nop     dword ptr [rax+rax+00h]
0x14003dfc5  call    cs:__imp_KeLeaveCriticalRegion
0x14003dfcc  nop     dword ptr [rax+rax+00h]
0x14003dfd1  test    esi, esi
0x14003dfd3  js      loc_14003E4B0
0x14003dfd9  mov     r9, [rsp+78h+Entry]
0x14003dfe1  test    r15, r15
0x14003dfe4  jnz     loc_14003E559
0x14003dfea  mov     rax, [rsp+78h+arg_10]
0x14003dff2  mov     [rax], r9
0x14003dff5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003dffc  jnz     loc_14003E450
0x14003e002  mov     eax, esi
0x14003e004  mov     rsi, [rsp+78h+arg_8]
0x14003e00c  add     rsp, 40h
0x14003e010  pop     r15
0x14003e012  pop     r14
0x14003e014  pop     r13
0x14003e016  pop     r12
0x14003e018  pop     rdi
0x14003e019  pop     rbp
0x14003e01a  pop     rbx
0x14003e01b  retn
0x14003e01d  mov     esi, gs:1A4h
0x14003e025  cmp     cs:UxDebugDisableLookaside, r15b
0x14003e02c  jnz     loc_14003E2BE
0x14003e032  cmp     cs:UxCompactMode, r15b
0x14003e039  jnz     loc_14003E4BB
0x14003e03f  mov     rcx, cs:qword_1401A0910
0x14003e046  lea     edi, [rsi+1]
0x14003e049  shl     rdi, 7
0x14003e04d  add     rdi, rcx
0x14003e050  movzx   eax, byte ptr [rdi+0B0h]
0x14003e057  test    al, al
0x14003e059  jz      loc_14003E4DE
0x14003e05f  lea     rcx, [rdi+40h]; Lookaside
0x14003e063  call    cs:__imp_ExAllocateFromLookasideListEx
0x14003e06a  nop     dword ptr [rax+rax+00h]
0x14003e06f  xor     edx, edx; Val
0x14003e071  mov     r15, rax
0x14003e074  test    rax, rax
0x14003e077  jz      loc_14003E490
0x14003e07d  mov     r8d, 0A0h; Size
0x14003e083  mov     rcx, rax; void *
0x14003e086  call    memset
0x14003e08b  mov     [r15], esi
0x14003e08e  mov     eax, 1
0x14003e093  mov     dword ptr [r15+10h], 55436C55h
0x14003e09b  mov     dword ptr [r15+14h], 1
0x14003e0a3  mov     byte ptr [r15+51h], 1
0x14003e0a8  mov     [r15+38h], rbx
0x14003e0ac  mov     [r15+40h], r13
0x14003e0b0  lock xadd [r13+0], eax
0x14003e0b6  inc     eax
0x14003e0b8  cmp     cs:UxDebugCheckRefcount, 0
0x14003e0bf  jnz     loc_14003E221
0x14003e0c5  lea     rdx, [rbx+28h]; BugCheckParameter2
0x14003e0c9  mov     eax, 1
0x14003e0ce  lock xadd [rdx], eax
0x14003e0d2  inc     eax
0x14003e0d4  cmp     cs:UxDebugCheckRefcount, 0
0x14003e0db  jnz     loc_14003E241
0x14003e0e1  lea     rax, [r15+60h]
0x14003e0e5  xor     esi, esi
0x14003e0e7  mov     [r15+48h], rsi
0x14003e0eb  lea     rcx, [r15+80h]; SpinLock
0x14003e0f2  mov     [rax+8], rax
0x14003e0f6  mov     [rax], rax
0x14003e0f9  lea     rax, [r15+70h]
0x14003e0fd  mov     [rax+8], rax
0x14003e101  mov     [rax], rax
0x14003e104  call    cs:__imp_KeInitializeSpinLock
0x14003e10b  nop     dword ptr [rax+rax+00h]
0x14003e110  lea     rax, [r15+88h]
0x14003e117  xor     edx, edx
0x14003e119  mov     [rax+8], rax
0x14003e11d  mov     rcx, r12
0x14003e120  mov     [rax], rax
0x14003e123  mov     [r15+98h], esi
0x14003e12a  mov     dword ptr [r15+9Ch], 0FFFFFFFFh
0x14003e135  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x14003e13c  nop     dword ptr [rax+rax+00h]
0x14003e141  test    al, al
0x14003e143  jz      loc_14003E303
0x14003e149  mov     [rsp+78h+arg_0], 1
0x14003e151  mov     eax, 1
0x14003e156  lock xadd [r15+14h], eax
0x14003e15c  inc     eax
0x14003e15e  cmp     cs:UxDebugCheckRefcount, 0
0x14003e165  jnz     loc_14003E25E
0x14003e16b  movzx   ecx, word ptr [rbx+38h]
0x14003e16f  mov     rax, [r13+108h]
0x14003e176  mov     rbx, [rax+rcx*8]
0x14003e17a  call    cs:__imp_KeEnterCriticalRegion
0x14003e181  nop     dword ptr [rax+rax+00h]
0x14003e186  xor     edx, edx
0x14003e188  mov     rcx, rbx
0x14003e18b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003e192  nop     dword ptr [rax+rax+00h]
0x14003e197  cmp     byte ptr [rbx+18h], 0
0x14003e19b  jnz     loc_14003E393
0x14003e1a1  mov     rcx, [r14]
0x14003e1a4  cmp     [rcx+8], r14
0x14003e1a8  jnz     short loc_14003E1CE
0x14003e1aa  mov     [r15+18h], rcx
0x14003e1ae  lea     rax, [r15+18h]
0x14003e1b2  mov     [rax+8], r14
0x14003e1b6  mov     [rcx+8], rax
0x14003e1ba  lea     rcx, [rbx+8]
0x14003e1be  mov     [r14], rax
0x14003e1c1  mov     rdx, [rcx+8]
0x14003e1c5  cmp     [rdx], rcx
0x14003e1c8  jz      loc_14003E27F
0x14003e1ce  mov     ecx, 3
0x14003e1d3  int     29h; Win8: RtlFailFast(ecx)
0x14003e1d5  test    rbx, rbx
0x14003e1d8  jz      short loc_14003E21D
0x14003e1da  mov     rax, [rcx+30h]
0x14003e1de  mov     [rsp+78h+var_48], r8
0x14003e1e3  mov     edx, 1Bh
0x14003e1e8  mov     [rsp+78h+var_50], r13
0x14003e1ed  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x14003e1f4  mov     ecx, 408h
0x14003e1f9  mov     [rsp+78h+var_58], rax
0x14003e1fe  mov     r9, rbx
0x14003e201  call    WPP_SF_qqqi
0x14003e206  jmp     loc_14003DEE8
0x14003e20b  mov     r8, [rsp+78h+Entry]
0x14003e213  mov     esi, 0C0000184h
0x14003e218  jmp     loc_14003DF9E
0x14003e21d  xor     eax, eax
0x14003e21f  jmp     short loc_14003E1DE
0x14003e221  cmp     eax, 0FFFFFFFFh
0x14003e224  jg      loc_14003E0C5
0x14003e22a  movsxd  r9, eax; BugCheckParameter4
0x14003e22d  mov     r8d, 0Eh; BugCheckParameter3
0x14003e233  mov     rdx, r13; BugCheckParameter2
0x14003e236  mov     ecx, 3; BugCheckParameter1
0x14003e23b  call    UlBugCheckEx
0x14003e241  cmp     eax, 0FFFFFFFFh
0x14003e244  jg      loc_14003E0E1
0x14003e24a  movsxd  r9, eax; BugCheckParameter4
0x14003e24d  mov     ecx, 3; BugCheckParameter1
0x14003e252  mov     r8d, 0Eh; BugCheckParameter3
0x14003e258  call    UlBugCheckEx
0x14003e25e  cmp     eax, 0FFFFFFFFh
0x14003e261  jg      loc_14003E16B
0x14003e267  movsxd  r9, eax; BugCheckParameter4
0x14003e26a  lea     rdx, [r15+14h]; BugCheckParameter2
0x14003e26e  mov     r8d, 0Ah; BugCheckParameter3
0x14003e274  mov     ecx, 3; BugCheckParameter1
0x14003e279  call    UlBugCheckEx
0x14003e27f  lea     rax, [r15+28h]
0x14003e283  mov     [rax], rcx
0x14003e286  mov     [rax+8], rdx
0x14003e28a  mov     [rdx], rax
0x14003e28d  xor     edx, edx
0x14003e28f  mov     [rcx+8], rax
0x14003e293  mov     rcx, rbx
0x14003e296  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003e29d  nop     dword ptr [rax+rax+00h]
0x14003e2a2  call    cs:__imp_KeLeaveCriticalRegion
0x14003e2a9  nop     dword ptr [rax+rax+00h]
0x14003e2ae  mov     [rsp+78h+Entry], r15
0x14003e2b6  xor     r15d, r15d
0x14003e2b9  jmp     loc_14003DFB4
0x14003e2be  mov     rax, cs:off_1401A0930
0x14003e2c5  xor     r9d, r9d
0x14003e2c8  mov     r8d, cs:dword_1401A0928
0x14003e2cf  mov     rdx, cs:qword_1401A0920
0x14003e2d6  mov     ecx, cs:dword_1401A0918
0x14003e2dc  call    _guard_dispatch_icall
0x14003e2e1  jmp     loc_14003E06F
0x14003e2e6  cmp     ecx, 0FFFFFFFFh
0x14003e2e9  jg      loc_14003DF84
0x14003e2ef  movsxd  r9, ecx; BugCheckParameter4
0x14003e2f2  mov     r8d, 0Ah; BugCheckParameter3
0x14003e2f8  mov     ecx, 3; BugCheckParameter1
0x14003e2fd  call    UlBugCheckEx
0x14003e303  xor     edx, edx
0x14003e305  mov     rcx, r12
0x14003e308  call    cs:__imp_ExReleasePushLockSharedEx
0x14003e30f  nop     dword ptr [rax+rax+00h]
0x14003e314  call    cs:__imp_KeLeaveCriticalRegion
0x14003e31b  nop     dword ptr [rax+rax+00h]
0x14003e320  call    cs:__imp_KeEnterCriticalRegion
0x14003e327  nop     dword ptr [rax+rax+00h]
0x14003e32c  xor     edx, edx
0x14003e32e  mov     rcx, r12
0x14003e331  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003e338  nop     dword ptr [rax+rax+00h]
0x14003e33d  mov     [rsp+78h+arg_0], 1
0x14003e345  cmp     [rbx+3C8h], sil
0x14003e34c  jnz     loc_14003E62C
0x14003e352  lea     r9, [rsp+78h+Entry]
0x14003e35a  mov     rdx, r13
0x14003e35d  lea     r8, [rsp+78h+arg_0]
0x14003e365  mov     rcx, rbx
0x14003e368  call    UlpFindCoupling
0x14003e36d  mov     esi, eax
0x14003e36f  test    eax, eax
0x14003e371  js      loc_14003DFB4
0x14003e377  cmp     [rsp+78h+Entry], 0
0x14003e380  jz      loc_14003E149
0x14003e386  jmp     loc_14003DFB4
0x14003e38b  mov     rdi, [rdi]
0x14003e38e  jmp     loc_14003DF53
0x14003e393  mov     r14d, 0FFFFFFFFh
0x14003e399  mov     eax, r14d
0x14003e39c  lock xadd [r15+14h], eax
0x14003e3a2  dec     eax
0x14003e3a4  cmp     cs:UxDebugCheckRefcount, 0
0x14003e3ab  jnz     loc_14003E46F
0x14003e3b1  test    eax, eax
0x14003e3b3  jz      loc_14003E441
0x14003e3b9  xor     edx, edx
0x14003e3bb  mov     rcx, rbx
0x14003e3be  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003e3c5  nop     dword ptr [rax+rax+00h]
0x14003e3ca  call    cs:__imp_KeLeaveCriticalRegion
0x14003e3d1  nop     dword ptr [rax+rax+00h]
0x14003e3d6  xor     edx, edx
0x14003e3d8  mov     rcx, r12
0x14003e3db  mov     esi, 0C0000184h
0x14003e3e0  call    cs:__imp_ExReleasePushLockEx
0x14003e3e7  nop     dword ptr [rax+rax+00h]
0x14003e3ec  call    cs:__imp_KeLeaveCriticalRegion
0x14003e3f3  nop     dword ptr [rax+rax+00h]
0x14003e3f8  mov     r9, [rsp+78h+Entry]
0x14003e400  test    r9, r9
0x14003e403  jz      loc_14003DFE1
0x14003e409  lea     rdx, [r9+14h]; BugCheckParameter2
0x14003e40d  mov     eax, r14d
0x14003e410  lock xadd [rdx], eax
0x14003e414  dec     eax
0x14003e416  cmp     cs:UxDebugCheckRefcount, 0
  ... truncated ...
```
