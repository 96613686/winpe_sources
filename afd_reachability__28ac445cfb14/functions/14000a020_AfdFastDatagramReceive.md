# AfdFastDatagramReceive

- ea: `0x14000a020`
- end: `0x14000a85b`
- name: `AfdFastDatagramReceive`
- size: `2107`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14000a870`
- `0x140049700`

## callees

- `0x140009920`
- `0x14000a020`
- `0x140012610`
- `0x1400137a0`
- `0x140013dc0`
- `0x14001b0d0`
- `0x140026170`
- `0x14002ce20`
- `0x14002fd5c`
- `0x140030390`
- `0x140037804`
- `0x1400445b8`
- `0x14004968c`
- `0x140050be4`
- `0x1400726d0`
- `0x140092008`
- `0x14009214c`
- `0x140092254`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14000a15e`
- `ntoskrnl!ExGetPreviousMode` at `0x14000a15e`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a3e5`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a3f5`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a430`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a3e5`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a3f5`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a430`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000a7cd`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000a817`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000a7cd`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000a817`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a7ff`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a84a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a7ff`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000a84a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a103`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a151`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a58b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a603`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a73f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a103`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a151`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a58b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a603`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a73f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a06f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a538`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a5a7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a06f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a538`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a5a7`
- `ntoskrnl!IoIs32bitProcess` at `0x14000a308`
- `ntoskrnl!IoIs32bitProcess` at `0x14000a308`

## pseudocode

```c
char __fastcall AfdFastDatagramReceive(__int64 a1, __int64 a2, unsigned int a3, char a4, __int64 a5)
{
  __int64 v9; // rsi
  __int64 *v10; // rax
  __int64 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  void *v15; // rdx
  __int64 v16; // rcx
  _DWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  unsigned __int16 *v21; // rdx
  unsigned int v22; // r13d
  KPROCESSOR_MODE v23; // cl
  unsigned int ULongFromUser; // eax
  bool v25; // zf
  void *v26; // rcx
  size_t v27; // r13
  unsigned int *v28; // rax
  KPROCESSOR_MODE v29; // dl
  unsigned int v30; // eax
  void *v31; // rcx
  void *v32; // rdx
  unsigned int *v33; // rcx
  unsigned int v34; // ecx
  __int64 v35; // r15
  char v36; // si
  char v37; // bl
  __int64 v38; // [rsp+20h] [rbp-C8h]
  SIZE_T Length; // [rsp+28h] [rbp-C0h]
  int v40; // [rsp+30h] [rbp-B8h]
  int v41; // [rsp+30h] [rbp-B8h]
  int v42; // [rsp+58h] [rbp-90h]
  int v43; // [rsp+58h] [rbp-90h]
  KPROCESSOR_MODE PreviousMode; // [rsp+60h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-78h] BYREF
  __int128 v46; // [rsp+88h] [rbp-60h] BYREF
  __int64 v47; // [rsp+98h] [rbp-50h]
  __int64 v48; // [rsp+A0h] [rbp-48h]
  unsigned __int16 *v49; // [rsp+A8h] [rbp-40h]
  __int64 *v50; // [rsp+B0h] [rbp-38h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( SBYTE1(xmmword_1400875E0) < 0 )
    WPP_SF_q(1039, 17, WPP_a21e66b129c637a1ed598ef54f085a19_Traceguids, a1);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  if ( (*(_BYTE *)(a1 + 7) & 0x10) != 0 )
    goto LABEL_12;
  v9 = 0;
  v48 = 0;
  if ( g_AfdEtwTraceEnable )
  {
    v9 = MEMORY[0xFFFFF78000000008];
    v48 = MEMORY[0xFFFFF78000000008];
  }
  if ( *(_DWORD *)(a1 + 148) )
  {
    v10 = (__int64 *)(a1 + 128);
    v11 = *(__int64 **)(a1 + 128);
    if ( v11[1] != a1 + 128 )
      goto LABEL_82;
    v12 = *v11;
    if ( *(__int64 **)(*v11 + 8) != v11 )
      goto LABEL_82;
    *v10 = v12;
    *(_QWORD *)(v12 + 8) = v10;
    if ( *((_DWORD *)v11 + 16) <= a3 && *((int *)v11 + 12) >= 0 )
    {
      v50 = v11;
      --*(_DWORD *)(a1 + 148);
      *(_DWORD *)(a1 + 144) -= *((_DWORD *)v11 + 16);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      PreviousMode = ExGetPreviousMode();
      AFDETW_START_ACTIVITY_FASTIO(a1, v9);
      DWORD2(v46) = 0;
      *(_QWORD *)&v46 = 0;
      v15 = *(void **)a2;
      if ( a4 )
        RtlCopyFromUser(&v46, v15, 0x10u);
      else
        RtlCopyVolatileMemory(&v46, v15, 0x10u);
      *(_QWORD *)&v46 = *((_QWORD *)&v46 + 1);
      if ( *((_DWORD *)v11 + 16) )
      {
        AFDETW_TRACEBUFFER(v16, v9, v11[7], 0);
        LOBYTE(v40) = a4;
        LODWORD(Length) = *((_DWORD *)v11 + 16);
        LODWORD(v38) = 0;
        AfdCopyMdlChainToBufferArray(*(void **)a2, v38, Length, v40);
      }
      if ( *(_QWORD *)(a2 + 24) )
      {
        v20 = *(_DWORD *)(a1 + 8);
        v21 = (unsigned __int16 *)v11[5];
        v49 = v21;
        if ( (v20 & 0x100) != 0 )
          v22 = *((_DWORD *)v11 + 8);
        else
          v22 = v21[2] + 2;
        v23 = PreviousMode;
        if ( PreviousMode )
        {
          ULongFromUser = RtlReadULongFromUser(*(_QWORD *)(a2 + 32));
          v23 = PreviousMode;
          v21 = v49;
        }
        else
        {
          ULongFromUser = **(_DWORD **)(a2 + 32);
        }
        if ( ULongFromUser < v22 )
          ExRaiseAccessViolation();
        if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
          v21 += 3;
        v25 = v23 == 0;
        v26 = *(void **)(a2 + 24);
        if ( v25 )
          RtlCopyVolatileMemory(v26, v21, v22);
        else
          RtlCopyToUser(v26, v21, v22);
        if ( PreviousMode )
          RtlWriteULongToUser(*(_QWORD *)(a2 + 32), v22);
        else
          **(_DWORD **)(a2 + 32) = v22;
      }
      if ( *(_QWORD *)(a2 + 48) )
      {
        if ( (v11[2] & 0x1000) != 0 && (v27 = *((unsigned int *)v11 + 17), (_DWORD)v27) )
        {
          if ( IoIs32bitProcess(0) )
          {
            LODWORD(v27) = AfdComputeCMSGLength32(v11[14] + *((unsigned int *)v11 + 16), (unsigned int)v27);
            v33 = *(unsigned int **)(a2 + 48);
            if ( PreviousMode )
              v34 = RtlReadULongFromUser(v33);
            else
              v34 = *v33;
            if ( (unsigned int)v27 > v34 )
              ExRaiseAccessViolation();
            AfdCopyCMSGBuffer32(*(void **)(a2 + 40));
          }
          else
          {
            v28 = *(unsigned int **)(a2 + 48);
            v29 = PreviousMode;
            if ( PreviousMode )
            {
              v30 = RtlReadULongFromUser(v28);
              v29 = PreviousMode;
            }
            else
            {
              v30 = *v28;
            }
            if ( (unsigned int)v27 > v30 )
              ExRaiseAccessViolation();
            v31 = *(void **)(a2 + 40);
            v25 = v29 == 0;
            v32 = (void *)(*((unsigned int *)v11 + 16) + v11[14]);
            if ( v25 )
              RtlCopyVolatileMemory(v31, v32, v27);
            else
              RtlCopyToUser(v31, v32, v27);
          }
        }
        else
        {
          LODWORD(v27) = 0;
        }
        if ( PreviousMode )
          RtlWriteULongToUser(*(_QWORD *)(a2 + 48), (unsigned int)v27);
        else
          **(_DWORD **)(a2 + 48) = v27;
      }
      v17 = *(_DWORD **)(a2 + 56);
      if ( v17 )
      {
        v18 = 0;
        v19 = *((_DWORD *)v11 + 4);
        if ( (v19 & 4) != 0 )
          v18 = 1024;
        if ( (v19 & 8) != 0 )
          LODWORD(v18) = v18 | 0x800;
        if ( PreviousMode )
          RtlWriteULongToUser(v17, v18);
        else
          *v17 = v18;
      }
      *(_QWORD *)(a5 + 8) = *((unsigned int *)v11 + 16);
      *(_DWORD *)a5 = 0;
      v41 = a3;
      v35 = v46;
      AFDETW_TRACERECVDATAGRAM(0, 4200, a1, 1, *(_DWORD *)(a2 + 8), v46, v41, 0, 0, v9, *(_DWORD *)(a2 + 12), 0);
      LOBYTE(v42) = 1;
      AFDETW_TRACERECVDATAGRAM(
        1,
        4201,
        a1,
        1,
        *(_DWORD *)(a2 + 8),
        v35,
        *((_DWORD *)v11 + 16),
        0,
        v11[5],
        v9,
        *(_DWORD *)(a2 + 12),
        v42);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
      *(_DWORD *)(a1 + 72) &= ~1u;
      if ( *(_DWORD *)(a1 + 148) )
      {
        AfdIndicateEventSelectEvent(a1, 1, 0);
      }
      else
      {
        AfdNotifySockEventsChangedUnderLock(a1, 0, 1);
        if ( (*(_DWORD *)(a1 + 8) & 0x10) == 0 )
          *(_BYTE *)(a1 + 33) = 1;
      }
      v36 = 0;
      v46 = 0;
      v47 = 0;
      if ( *(_QWORD *)(a1 + 384) && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 392)) )
      {
        v36 = 1;
        AfdNotifyPostEvents(a1, &LockHandle, 0);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v36 )
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 392));
      AfdReturnBuffer((unsigned __int16 *)v11, *(PEPROCESS *)(a1 + 48));
      return 1;
    }
    v13 = *v10;
    if ( *(__int64 **)(*v10 + 8) != v10 )
LABEL_82:
      __fastfail(3u);
    *v11 = v13;
    v11[1] = (__int64)v10;
    *(_QWORD *)(v13 + 8) = v11;
    *v10 = (__int64)v11;
LABEL_12:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 0;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x10) == 0 || (*(_DWORD *)(a2 + 12) & 2) != 0 )
    goto LABEL_12;
  *(_DWORD *)(a1 + 72) &= ~1u;
  AfdNotifySockEventsChangedUnderLock(a1, 0, 1);
  if ( (xmmword_1400875E0 & 0x20) != 0 )
    WPP_SF_qD(1029, 18, WPP_a21e66b129c637a1ed598ef54f085a19_Traceguids, a1, *(_DWORD *)(a1 + 72));
  AFDETW_TRACERECVDATAGRAM(0, 4117, a1, 1, 0, 0, a3, 0, 0, v9, *(_DWORD *)(a2 + 12), 1);
  LOBYTE(v43) = 1;
  AFDETW_TRACERECVDATAGRAM(1, 4118, a1, 1, 0, 0, a3, -1073741661, 0, v9, *(_DWORD *)(a2 + 12), v43);
  *(_DWORD *)a5 = -1073741661;
  v37 = 0;
  v46 = 0;
  v47 = 0;
  if ( *(_QWORD *)(a1 + 384) && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 392)) )
  {
    v37 = 1;
    AfdNotifyPostEvents(a1, &LockHandle, 0);
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v37 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 392));
  return 1;
}

```

## disassembly

```asm
0x14000a020  mov     r11, rsp
0x14000a023  mov     [r11+10h], rbx
0x14000a027  mov     [r11+18h], rsi
0x14000a02b  mov     [r11+8], rcx
0x14000a02f  push    rdi
0x14000a030  push    r12
0x14000a032  push    r13
0x14000a034  push    r14
0x14000a036  push    r15
0x14000a038  sub     rsp, 0C0h
0x14000a03f  movzx   r13d, r9b
0x14000a043  mov     r15d, r8d
0x14000a046  mov     r12, rdx
0x14000a049  mov     rdi, rcx
0x14000a04c  xorps   xmm0, xmm0
0x14000a04f  xor     eax, eax
0x14000a051  movups  xmmword ptr [rsp+0E8h+LockHandle.LockQueue.Next], xmm0
0x14000a056  mov     [r11-68h], rax
0x14000a05a  cmp     byte ptr cs:xmmword_1400875E0+1, al
0x14000a060  jl      loc_14000A783
0x14000a066  lea     rdx, [rsp+0E8h+LockHandle]; LockHandle
0x14000a06b  lea     rcx, [rdi+38h]; SpinLock
0x14000a06f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a076  nop     dword ptr [rax+rax+00h]
0x14000a07b  test    byte ptr [rdi+7], 10h
0x14000a07f  jnz     short loc_14000A0FE
0x14000a081  xor     esi, esi
0x14000a083  mov     [rsp+0E8h+var_48], rsi
0x14000a08b  cmp     cs:g_AfdEtwTraceEnable, esi
0x14000a091  jz      short loc_14000A0A8
0x14000a093  mov     rsi, 0FFFFF78000000008h
0x14000a09d  mov     rsi, [rsi]
0x14000a0a0  mov     [rsp+0E8h+var_48], rsi
0x14000a0a8  cmp     dword ptr [rdi+94h], 0
0x14000a0af  jz      loc_14000A62B
0x14000a0b5  lea     rax, [rdi+80h]
0x14000a0bc  mov     rbx, [rax]
0x14000a0bf  cmp     [rbx+8], rax
0x14000a0c3  jnz     loc_14000A77C
0x14000a0c9  mov     rcx, [rbx]
0x14000a0cc  cmp     [rcx+8], rbx
0x14000a0d0  jnz     loc_14000A77C
0x14000a0d6  mov     [rax], rcx
0x14000a0d9  mov     [rcx+8], rax
0x14000a0dd  cmp     [rbx+40h], r15d
0x14000a0e1  jbe     short loc_14000A12F
0x14000a0e3  mov     rcx, [rax]
0x14000a0e6  cmp     [rcx+8], rax
0x14000a0ea  jnz     loc_14000A77C
0x14000a0f0  mov     [rbx], rcx
0x14000a0f3  mov     [rbx+8], rax
0x14000a0f7  mov     [rcx+8], rbx
0x14000a0fb  mov     [rax], rbx
0x14000a0fe  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14000a103  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a10a  nop     dword ptr [rax+rax+00h]
0x14000a10f  xor     al, al
0x14000a111  lea     r11, [rsp+0E8h+var_28]
0x14000a119  mov     rbx, [r11+38h]
0x14000a11d  mov     rsi, [r11+40h]
0x14000a121  mov     rsp, r11
0x14000a124  pop     r15
0x14000a126  pop     r14
0x14000a128  pop     r13
0x14000a12a  pop     r12
0x14000a12c  pop     rdi
0x14000a12d  retn
0x14000a12f  cmp     dword ptr [rbx+30h], 0
0x14000a133  jl      short loc_14000A0E3
0x14000a135  mov     [rsp+0E8h+var_38], rbx
0x14000a13d  dec     dword ptr [rdi+94h]
0x14000a143  mov     eax, [rbx+40h]
0x14000a146  sub     [rdi+90h], eax
0x14000a14c  lea     rcx, [rsp+0E8h+LockHandle]; LockHandle
0x14000a151  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a158  nop     dword ptr [rax+rax+00h]
0x14000a15d  nop
0x14000a15e  call    cs:__imp_ExGetPreviousMode
0x14000a165  nop     dword ptr [rax+rax+00h]
0x14000a16a  mov     [rsp+0E8h+var_88], al
0x14000a16e  mov     rdx, rsi
0x14000a171  mov     rcx, rdi
0x14000a174  call    AFDETW_START_ACTIVITY_FASTIO
0x14000a179  xor     eax, eax
0x14000a17b  mov     qword ptr [rsp+0E8h+var_60+4], rax
0x14000a183  mov     qword ptr [rsp+0E8h+var_60], rax
0x14000a18b  mov     rdx, [r12]; Src
0x14000a18f  mov     r8d, 10h; Size
0x14000a195  lea     rcx, [rsp+0E8h+var_60]; void *
0x14000a19d  test    r13b, r13b
0x14000a1a0  jz      loc_14000A3A5
0x14000a1a6  call    RtlCopyFromUser
0x14000a1ab  mov     rax, qword ptr [rsp+0E8h+var_60+8]
0x14000a1b3  mov     qword ptr [rsp+0E8h+var_60], rax
0x14000a1bb  cmp     dword ptr [rbx+40h], 0
0x14000a1bf  jbe     short loc_14000A1F8
0x14000a1c1  xor     r9d, r9d
0x14000a1c4  mov     r8, [rbx+38h]
0x14000a1c8  mov     rdx, rsi
0x14000a1cb  call    AFDETW_TRACEBUFFER
0x14000a1d0  mov     byte ptr [rsp+0E8h+var_B8], r13b; int
0x14000a1d5  mov     eax, [rbx+40h]
0x14000a1d8  mov     dword ptr [rsp+0E8h+Length], eax; Length
0x14000a1dc  mov     dword ptr [rsp+0E8h+var_C8], 0; __int64
0x14000a1e4  mov     r9, [rbx+38h]
0x14000a1e8  mov     r8d, [r12+8]
0x14000a1ed  xor     edx, edx
0x14000a1ef  mov     rcx, [r12]; Src
0x14000a1f3  call    AfdCopyMdlChainToBufferArray
0x14000a1f8  cmp     qword ptr [r12+18h], 0
0x14000a1fe  jnz     short loc_14000A250
0x14000a200  cmp     qword ptr [r12+30h], 0
0x14000a206  jnz     loc_14000A2E7
0x14000a20c  mov     rcx, [r12+38h]
0x14000a211  test    rcx, rcx
0x14000a214  jz      loc_14000A45D
0x14000a21a  xor     edx, edx
0x14000a21c  mov     [rsp+0E8h+var_80], edx
0x14000a220  mov     eax, [rbx+10h]
0x14000a223  test    al, 4
0x14000a225  mov     r8d, 400h
0x14000a22b  cmovnz  edx, r8d
0x14000a22f  mov     [rsp+0E8h+var_80], edx
0x14000a233  test    al, 8
0x14000a235  jnz     loc_14000A44E
0x14000a23b  cmp     [rsp+0E8h+var_88], 0
0x14000a240  jz      loc_14000A45B
0x14000a246  call    RtlWriteULongToUser
0x14000a24b  jmp     loc_14000A45D
0x14000a250  mov     eax, [rdi+8]
0x14000a253  mov     rdx, [rbx+28h]
0x14000a257  mov     [rsp+0E8h+var_40], rdx
0x14000a25f  bt      eax, 8
0x14000a263  jnb     loc_14000A382
0x14000a269  mov     r13d, [rbx+20h]
0x14000a26d  mov     [rsp+0E8h+var_84], r13d
0x14000a272  mov     rax, [r12+20h]
0x14000a277  movzx   ecx, [rsp+0E8h+var_88]
0x14000a27c  test    cl, cl
0x14000a27e  jz      loc_14000A39A
0x14000a284  mov     rcx, rax
0x14000a287  call    RtlReadULongFromUser
0x14000a28c  movzx   ecx, [rsp+0E8h+var_88]
0x14000a291  mov     rdx, [rsp+0E8h+var_40]
0x14000a299  cmp     eax, r13d
0x14000a29c  jb      loc_14000A3F5
0x14000a2a2  mov     eax, [rdi+8]
0x14000a2a5  mov     r8d, r13d; Size
0x14000a2a8  mov     r9, [r12+18h]
0x14000a2ad  bt      eax, 8
0x14000a2b1  jb      short loc_14000A2B7
0x14000a2b3  add     rdx, 6; Src
0x14000a2b7  test    cl, cl
0x14000a2b9  mov     rcx, r9; void *
0x14000a2bc  jz      loc_14000A401
0x14000a2c2  call    RtlCopyToUser
0x14000a2c7  mov     rax, [r12+20h]
0x14000a2cc  cmp     [rsp+0E8h+var_88], 0
0x14000a2d1  jz      loc_14000A40B
0x14000a2d7  mov     edx, r13d
0x14000a2da  mov     rcx, rax
0x14000a2dd  call    RtlWriteULongToUser
0x14000a2e2  jmp     loc_14000A200
0x14000a2e7  test    dword ptr [rbx+10h], 1000h
0x14000a2ee  jz      loc_14000A390
0x14000a2f4  mov     r13d, [rbx+44h]
0x14000a2f8  test    r13d, r13d
0x14000a2fb  jz      loc_14000A390
0x14000a301  mov     [rsp+0E8h+var_84], r13d
0x14000a306  xor     ecx, ecx; Irp
0x14000a308  call    cs:__imp_IoIs32bitProcess
0x14000a30f  nop     dword ptr [rax+rax+00h]
0x14000a314  test    al, al
0x14000a316  jnz     loc_14000A3AF
0x14000a31c  mov     rax, [r12+30h]
0x14000a321  movzx   edx, [rsp+0E8h+var_88]
0x14000a326  test    dl, dl
0x14000a328  jz      short loc_14000A3A1
0x14000a32a  mov     rcx, rax
0x14000a32d  call    RtlReadULongFromUser
0x14000a332  movzx   edx, [rsp+0E8h+var_88]
0x14000a337  cmp     r13d, eax
0x14000a33a  ja      loc_14000A430
0x14000a340  mov     r8, r13; Size
0x14000a343  mov     ecx, [rbx+40h]
0x14000a346  mov     r9, [rbx+70h]
0x14000a34a  add     r9, rcx
0x14000a34d  mov     rcx, [r12+28h]; void *
0x14000a352  test    dl, dl
0x14000a354  mov     rdx, r9; Src
0x14000a357  jz      loc_14000A43C
0x14000a35d  call    RtlCopyToUser
0x14000a362  mov     rax, [r12+30h]
0x14000a367  cmp     [rsp+0E8h+var_88], 0
0x14000a36c  jz      loc_14000A446
0x14000a372  mov     edx, r13d
0x14000a375  mov     rcx, rax
0x14000a378  call    RtlWriteULongToUser
0x14000a37d  jmp     loc_14000A20C
0x14000a382  movzx   r13d, word ptr [rdx+4]
0x14000a387  add     r13d, 2
0x14000a38b  jmp     loc_14000A26D
0x14000a390  xor     r13d, r13d
0x14000a393  mov     [rsp+0E8h+var_84], r13d
0x14000a398  jmp     short loc_14000A362
0x14000a39a  mov     eax, [rax]
0x14000a39c  jmp     loc_14000A299
0x14000a3a1  mov     eax, [rax]
0x14000a3a3  jmp     short loc_14000A337
0x14000a3a5  call    RtlCopyVolatileMemory
0x14000a3aa  jmp     loc_14000A1AB
0x14000a3af  mov     ecx, [rbx+40h]
0x14000a3b2  add     rcx, [rbx+70h]
0x14000a3b6  mov     edx, r13d
0x14000a3b9  call    AfdComputeCMSGLength32
0x14000a3be  mov     r13d, eax
0x14000a3c1  mov     [rsp+0E8h+var_84], r13d
0x14000a3c6  mov     rcx, [r12+30h]
0x14000a3cb  movzx   eax, [rsp+0E8h+var_88]
0x14000a3d0  test    al, al
0x14000a3d2  jz      short loc_14000A3F1
0x14000a3d4  call    RtlReadULongFromUser
0x14000a3d9  mov     ecx, eax
0x14000a3db  movzx   eax, [rsp+0E8h+var_88]
0x14000a3e0  cmp     r13d, ecx
0x14000a3e3  jbe     short loc_14000A413
0x14000a3e5  call    cs:__imp_ExRaiseAccessViolation
0x14000a3ec  nop     dword ptr [rax+rax+00h]
0x14000a3f1  mov     ecx, [rcx]
0x14000a3f3  jmp     short loc_14000A3E0
0x14000a3f5  call    cs:__imp_ExRaiseAccessViolation
0x14000a3fc  nop     dword ptr [rax+rax+00h]
0x14000a401  call    RtlCopyVolatileMemory
0x14000a406  jmp     loc_14000A2C7
0x14000a40b  mov     [rax], r13d
0x14000a40e  jmp     loc_14000A200
0x14000a413  mov     r8, r13
0x14000a416  mov     edx, [rbx+40h]
0x14000a419  add     rdx, [rbx+70h]
0x14000a41d  movzx   r9d, al
0x14000a421  mov     rcx, [r12+28h]; void *
0x14000a426  call    AfdCopyCMSGBuffer32
0x14000a42b  jmp     loc_14000A362
0x14000a430  call    cs:__imp_ExRaiseAccessViolation
0x14000a437  nop     dword ptr [rax+rax+00h]
0x14000a43c  call    RtlCopyVolatileMemory
0x14000a441  jmp     loc_14000A362
0x14000a446  mov     [rax], r13d
0x14000a449  jmp     loc_14000A20C
0x14000a44e  bts     edx, 0Bh
0x14000a452  mov     [rsp+0E8h+var_80], edx
0x14000a456  jmp     loc_14000A23B
0x14000a45b  mov     [rcx], edx
0x14000a45d  mov     eax, [rbx+40h]
0x14000a460  mov     rcx, [rsp+0E8h+arg_20]
0x14000a468  mov     [rcx+8], rax
0x14000a46c  mov     dword ptr [rcx], 0
0x14000a472  mov     [rsp+0E8h+var_90], 0
0x14000a477  mov     eax, [r12+0Ch]
0x14000a47c  mov     [rsp+0E8h+var_98], eax
0x14000a480  mov     [rsp+0E8h+var_A0], rsi
0x14000a485  mov     [rsp+0E8h+var_A8], 0
0x14000a48e  mov     [rsp+0E8h+var_B0], 0
0x14000a496  mov     [rsp+0E8h+var_B8], r15d
0x14000a49b  mov     r15, qword ptr [rsp+0E8h+var_60]
0x14000a4a3  mov     [rsp+0E8h+Length], r15
0x14000a4a8  mov     eax, [r12+8]
0x14000a4ad  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14000a4b1  mov     r9d, 1
0x14000a4b7  mov     r8, rdi
0x14000a4ba  mov     edx, 1068h
0x14000a4bf  xor     ecx, ecx
0x14000a4c1  call    AFDETW_TRACERECVDATAGRAM
0x14000a4c6  mov     [rsp+0E8h+var_90], 1
0x14000a4cb  mov     eax, [r12+0Ch]
0x14000a4d0  mov     [rsp+0E8h+var_98], eax
0x14000a4d4  mov     [rsp+0E8h+var_A0], rsi
0x14000a4d9  mov     rax, [rbx+28h]
0x14000a4dd  mov     [rsp+0E8h+var_A8], rax
0x14000a4e2  mov     [rsp+0E8h+var_B0], 0
0x14000a4ea  mov     eax, [rbx+40h]
0x14000a4ed  mov     [rsp+0E8h+var_B8], eax
0x14000a4f1  mov     [rsp+0E8h+Length], r15
0x14000a4f6  mov     eax, [r12+8]
0x14000a4fb  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14000a4ff  mov     r9d, 1
0x14000a505  mov     r8, rdi
0x14000a508  mov     edx, 1069h
0x14000a50d  mov     ecx, r9d
0x14000a510  call    AFDETW_TRACERECVDATAGRAM
0x14000a515  jmp     loc_14000A59E
0x14000a51a  mov     rdx, [rsp+0E8h+var_48]
0x14000a522  call    AFDETW_STOP_ACTIVITY_FASTIO
0x14000a527  mov     rbx, [rsp+0E8h+arg_0]
0x14000a52f  lea     rcx, [rbx+38h]; SpinLock
0x14000a533  lea     rdx, [rsp+0E8h+LockHandle]; LockHandle
0x14000a538  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a53f  nop     dword ptr [rax+rax+00h]
0x14000a544  lea     rax, [rbx+80h]
0x14000a54b  mov     rdx, [rax]
  ... truncated ...
```
