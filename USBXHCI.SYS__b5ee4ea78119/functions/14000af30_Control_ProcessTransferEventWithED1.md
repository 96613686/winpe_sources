# Control_ProcessTransferEventWithED1

- ea: `0x14000af30`
- end: `0x14000ba74`
- name: `Control_ProcessTransferEventWithED1`
- size: `2884`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400029b0`
- `0x14000af00`

## callees

- `0x140002568`
- `0x14000ac60`
- `0x14000af30`
- `0x14000c264`
- `0x14000c7c0`
- `0x14000d6a0`
- `0x140026550`
- `0x140028524`
- `0x14002b300`
- `0x140034218`
- `0x140037214`
- `0x14004c704`
- `0x140057db0`
- `0x1400599b0`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14000b3c5`
- `ntoskrnl!DbgPrint` at `0x14000b8d5`
- `ntoskrnl!DbgPrint` at `0x14000b3c5`
- `ntoskrnl!DbgPrint` at `0x14000b8d5`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000b3d1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000b8e1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000b3d1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000b8e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5af`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b851`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5af`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b851`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b43f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b546`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b5f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b7fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b944`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b43f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b546`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b5f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b7fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b944`

## string_xrefs

- `0x14000b38e`: `Received duplicate Transfer Event TRB with Halted Completion Code`

## pseudocode

```c
char __fastcall Control_ProcessTransferEventWithED1(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // r12
  __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  __int64 v8; // r8
  __int64 v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // rdx
  __int64 v13; // r8
  int v14; // r12d
  __int64 *v15; // r8
  __int64 v16; // rcx
  int v17; // edx
  char v18; // cl
  int v19; // edx
  int v20; // ebx
  unsigned int v21; // r13d
  int v22; // edx
  int v23; // edx
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  _QWORD *v28; // rdx
  int v29; // ecx
  __int64 v30; // rdi
  __int64 v31; // rsi
  __int64 v32; // rbx
  _QWORD *v33; // rbx
  KIRQL v34; // al
  __int64 v35; // r8
  bool v36; // zf
  char *v37; // rcx
  char v38; // al
  __int64 v39; // rdx
  __int64 v40; // rax
  bool v41; // cc
  KSPIN_LOCK *v42; // rcx
  int v43; // eax
  int v44; // eax
  __int64 v45; // rbx
  __int64 v46; // rax
  KIRQL v47; // al
  __int64 v48; // rdx
  __int64 v49; // rax
  KIRQL v50; // al
  __int64 v51; // rdx
  __int64 v52; // rax
  KIRQL v53; // dl
  KSPIN_LOCK *v54; // rcx
  int v55; // edx
  int v56; // r8d
  int v57; // r9d
  _QWORD *v58; // rdx
  int v59; // ecx
  __int64 v60; // rdi
  __int64 v61; // rsi
  __int64 v62; // rbx
  KIRQL v63; // al
  __int64 v64; // rdx
  __int64 v65; // rax
  int v66; // [rsp+20h] [rbp-A8h]
  int v67; // [rsp+28h] [rbp-A0h]
  __int128 v68; // [rsp+60h] [rbp-68h] BYREF
  __int128 v69; // [rsp+70h] [rbp-58h] BYREF
  KIRQL v70; // [rsp+D0h] [rbp+8h]
  KIRQL v71; // [rsp+D8h] [rbp+10h]
  KIRQL v72; // [rsp+E0h] [rbp+18h]
  KIRQL v73; // [rsp+E8h] [rbp+20h]

  v4 = *(_QWORD *)a1;
  v5 = a2;
  v6 = *(_QWORD *)a1 & 0xFFFFFFFFFFFFFFF8uLL;
  if ( !a2 )
  {
    v5 = *(_QWORD *)(v6 + 56);
    v13 = *(_QWORD *)(v5 + 360);
    if ( v6 != v13 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v67 = HIBYTE(*(_DWORD *)(a1 + 12));
      WPP_RECORDER_SF_DDiqq(*(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL), v67, v13, 21);
    }
LABEL_17:
    v14 = v4 & 4;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v67 = HIBYTE(*(_DWORD *)(a1 + 12));
      WPP_RECORDER_SF_DDqLDDi(
        *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
        HIWORD(*(_DWORD *)(a1 + 12)) & 0x1F,
        *(_DWORD *)(a1 + 8) & 0xFFFFFF,
        22);
    }
    v15 = WPP_033405c12d5f32917339b215e0870938_Traceguids;
    v16 = *(_QWORD *)(v5 + 56);
    if ( (HIWORD(*(_DWORD *)(a1 + 12)) & 0x1F) != *(_DWORD *)(v16 + 152)
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = HIBYTE(*(_DWORD *)(a1 + 12));
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(v16 + 80),
        v17,
        14,
        23,
        (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
        HIBYTE(*(_DWORD *)(a1 + 12)),
        HIWORD(*(_DWORD *)(a1 + 12)) & 0x1F);
      v15 = WPP_033405c12d5f32917339b215e0870938_Traceguids;
    }
    v18 = *(_BYTE *)(a1 + 15);
    if ( v18 != *(_BYTE *)(*(_QWORD *)(v5 + 48) + 143LL)
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = *(_WORD *)(a1 + 14) & 0x1F;
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
        v19,
        14,
        24,
        (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
        v18,
        *(_BYTE *)(a1 + 14) & 0x1F);
    }
    v20 = 0;
    v21 = *(_DWORD *)(a1 + 8) & 0xFFFFFF;
    if ( v21 > *(_DWORD *)(v6 + 104) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = *(unsigned __int8 *)(*(_QWORD *)(v5 + 48) + 143LL);
        LOBYTE(v22) = 3;
        WPP_RECORDER_SF_DDDD(
          *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
          v22,
          14,
          25,
          (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
          *(_BYTE *)(*(_QWORD *)(v5 + 48) + 143LL),
          *(_DWORD *)(*(_QWORD *)(v5 + 56) + 152LL),
          *(_BYTE *)(a1 + 8),
          *(_DWORD *)(v6 + 104));
      }
      v21 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = *(unsigned __int8 *)(*(_QWORD *)(v5 + 48) + 143LL);
      LOBYTE(v23) = 4;
      WPP_RECORDER_SF_DDqq(
        *(_QWORD *)(*(_QWORD *)(v5 + 56) + 80LL),
        v23,
        (_DWORD)v15,
        26,
        (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v5 + 48) + 143LL),
        *(_DWORD *)(*(_QWORD *)(v5 + 56) + 152LL),
        *(_QWORD *)(v6 + 24),
        v6);
    }
    if ( !v14 )
    {
      v24 = *(_QWORD *)(v6 + 48);
      *(_DWORD *)(v6 + 108) = v21;
      if ( (*(_DWORD *)(v24 + 32) & 1) != 0 && *(_DWORD *)(v6 + 64) == 2 )
        memmove(*(void **)(v6 + 80), *(const void **)(*(_QWORD *)(v6 + 88) + 16LL), v21);
    }
    v25 = *(unsigned __int8 *)(a1 + 11);
    v26 = **(_QWORD **)(v5 + 56);
    if ( _bittest64((const signed __int64 *)(v26 + 736), 0x3Eu) && (_BYTE)v25 == 0xC7
      || (*(_BYTE *)(v26 + 744) & 0x20) != 0 && (_BYTE)v25 == 0xC6
      || (unsigned __int8)v25 <= 0x24u && (v27 = 0x150000045CLL, _bittest64(&v27, v25)) )
    {
      *(_DWORD *)(v6 + 124) = v25;
      v28 = *(_QWORD **)(v5 + 56);
      _m_prefetchw(v28 + 4);
      if ( (_InterlockedOr((volatile signed __int32 *)v28 + 8, 0x20u) & 0x20) != 0 )
      {
        v30 = v28[3];
        v31 = v28[1];
        v32 = *v28;
        v68 = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_s(
            *(_QWORD *)(v32 + 72),
            (_DWORD)v28,
            (_DWORD)v15,
            a4,
            v66,
            (__int64)"Received duplicate Transfer Event TRB with Halted Completion Code");
        if ( (*(_DWORD *)(v32 + 848) & 0x2000000) != 0 && !*(_BYTE *)(v32 + 797) )
        {
          DbgPrint(
            "xHCI Hardware Verifier Break: %s\n",
            "Received duplicate Transfer Event TRB with Halted Completion Code");
          if ( !KdRefreshDebuggerNotPresent() )
            __debugbreak();
        }
        v68 = 0;
        if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 0x10) != 0 )
          McTemplateK0pppxsb16b16_EtwWriteTransfer(
            v29,
            (_DWORD)v28,
            (_DWORD)v15,
            *(_QWORD *)(v32 + 8),
            v31,
            v30,
            0,
            (__int64)"Received duplicate Transfer Event TRB with Halted Completion Code",
            (__int64)&v68,
            (__int64)&v68);
        return 1;
      }
      v33 = v28 + 39;
      v34 = KeAcquireSpinLockRaiseToDpc(v28 + 144);
      v35 = v34;
      v70 = v34;
      *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 833) + 192) = 154;
      *((_BYTE *)v33 + 833) = (*((_BYTE *)v33 + 833) + 1) & 0xF;
      v36 = *((_BYTE *)v33 + 1016) == 0;
      v37 = (char *)v33 + 884;
      *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 949) + 221) = 154;
      v38 = *((_BYTE *)v33 + 949);
      if ( v36 )
      {
        *((_BYTE *)v33 + 949) = (v38 + 1) & 0xF;
        if ( !*((_BYTE *)v33 + 848) )
        {
          v39 = v33[120];
          *((_BYTE *)v33 + 848) = 1;
          v40 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 1632))(
                  WdfDriverGlobals,
                  v39,
                  v35);
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *, int))(WdfFunctions_01033 + 1640))(
            WdfDriverGlobals,
            v40,
            "State Machine Tag",
            1021,
            "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\smengine.c",
            v67);
          ESM_RunStateMachine(v33);
          LOBYTE(v35) = v70;
        }
        goto LABEL_91;
      }
LABEL_88:
      v37[65] = (v38 + 1) & 0xF;
LABEL_91:
      v54 = v33 + 105;
      v53 = v35;
      goto LABEL_92;
    }
    v41 = (unsigned __int8)(v25 - 26) <= 2u;
    v42 = (KSPIN_LOCK *)(v5 + 96);
    if ( v41 )
    {
      *(_BYTE *)(v5 + 104) = KeAcquireSpinLockRaiseToDpc(v42);
      v55 = ++*(_DWORD *)(v6 + 132);
      if ( v14 )
      {
        if ( *(_DWORD *)(v6 + 108) == *(_DWORD *)(v6 + 104) )
        {
          *(_DWORD *)(v6 + 124) = 1;
        }
        else if ( *(_BYTE *)(a1 + 11) == 28 )
        {
          *(_DWORD *)(v6 + 124) = 28;
        }
        v20 = *(_DWORD *)(v6 + 128) - v55;
      }
      *(_DWORD *)(v5 + 372) = v20;
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 96), *(_BYTE *)(v5 + 104));
      v58 = *(_QWORD **)(v5 + 56);
      _m_prefetchw(v58 + 4);
      if ( (_InterlockedOr((volatile signed __int32 *)v58 + 8, 0x10u) & 0x10) != 0 )
      {
        v60 = v58[3];
        v61 = v58[1];
        v62 = *v58;
        v69 = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_s(
            *(_QWORD *)(v62 + 72),
            (_DWORD)v58,
            v56,
            v57,
            v66,
            (__int64)"Received duplicate Stopped Transfer Events");
        if ( (*(_DWORD *)(v62 + 848) & 0x2000000) != 0 && !*(_BYTE *)(v62 + 797) )
        {
          DbgPrint("xHCI Hardware Verifier Break: %s\n", "Received duplicate Stopped Transfer Events");
          if ( !KdRefreshDebuggerNotPresent() )
            __debugbreak();
        }
        v69 = 0;
        if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 0x10) != 0 )
          McTemplateK0pppxsb16b16_EtwWriteTransfer(
            v59,
            (_DWORD)v58,
            v56,
            *(_QWORD *)(v62 + 8),
            v61,
            v60,
            0,
            (__int64)"Received duplicate Stopped Transfer Events",
            (__int64)&v69,
            (__int64)&v69);
        return 1;
      }
      _m_prefetchw(v58 + 4);
      if ( (_InterlockedXor((volatile signed __int32 *)v58 + 8, 8u) & 8) != 0 )
      {
        v33 = v58 + 39;
        v63 = KeAcquireSpinLockRaiseToDpc(v58 + 144);
        v35 = v63;
        v73 = v63;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 833) + 192) = 118;
        *((_BYTE *)v33 + 833) = (*((_BYTE *)v33 + 833) + 1) & 0xF;
        v36 = *((_BYTE *)v33 + 1016) == 0;
        v37 = (char *)v33 + 884;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 949) + 221) = 118;
        v38 = *((_BYTE *)v33 + 949);
        if ( v36 )
        {
          *((_BYTE *)v33 + 949) = (v38 + 1) & 0xF;
          if ( !*((_BYTE *)v33 + 848) )
          {
            v64 = v33[120];
            *((_BYTE *)v33 + 848) = 1;
            v65 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 1632))(
                    WdfDriverGlobals,
                    v64,
                    v35);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *, int))(WdfFunctions_01033 + 1640))(
              WdfDriverGlobals,
              v65,
              "State Machine Tag",
              1021,
              "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\smengine.c",
              v67);
            ESM_RunStateMachine(v33);
            LOBYTE(v35) = v73;
          }
          goto LABEL_91;
        }
        goto LABEL_88;
      }
    }
    else
    {
      *(_BYTE *)(v5 + 104) = KeAcquireSpinLockRaiseToDpc(v42);
      ++*(_DWORD *)(v6 + 132);
      if ( v14 )
      {
        v36 = *(_DWORD *)(v6 + 112) == 3;
        *(_DWORD *)(v6 + 124) = *(unsigned __int8 *)(a1 + 11);
        if ( !v36 && *(_DWORD *)(v6 + 116) != 3 )
          Control_Transfer_CompleteCancelable(v5);
      }
      v43 = *(_DWORD *)(v5 + 372);
      if ( !v43 || (v44 = v43 - 1, (*(_DWORD *)(v5 + 372) = v44) != 0) || (*(_DWORD *)(v5 + 368) & 4) == 0 )
      {
        v53 = *(_BYTE *)(v5 + 104);
        v54 = (KSPIN_LOCK *)(v5 + 96);
LABEL_92:
        KeReleaseSpinLock(v54, v53);
        return 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 96), *(_BYTE *)(v5 + 104));
      v45 = *(_QWORD *)(v5 + 56);
      if ( !*(_BYTE *)(v45 + 37) )
      {
        v33 = (_QWORD *)(v45 + 312);
        v50 = KeAcquireSpinLockRaiseToDpc(v33 + 105);
        v35 = v50;
        v72 = v50;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 833) + 192) = 150;
        *((_BYTE *)v33 + 833) = (*((_BYTE *)v33 + 833) + 1) & 0xF;
        v36 = *((_BYTE *)v33 + 1016) == 0;
        v37 = (char *)v33 + 884;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 949) + 221) = 150;
        v38 = *((_BYTE *)v33 + 949);
        if ( v36 )
        {
          *((_BYTE *)v33 + 949) = (v38 + 1) & 0xF;
          if ( !*((_BYTE *)v33 + 848) )
          {
            v51 = v33[120];
            *((_BYTE *)v33 + 848) = 1;
            v52 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 1632))(
                    WdfDriverGlobals,
                    v51,
                    v35);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *, int))(WdfFunctions_01033 + 1640))(
              WdfDriverGlobals,
              v52,
              "State Machine Tag",
              1021,
              "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\smengine.c",
              v67);
            ESM_RunStateMachine(v33);
            LOBYTE(v35) = v72;
          }
          goto LABEL_91;
        }
        goto LABEL_88;
      }
      v46 = *(_QWORD *)(v45 + 144);
      if ( _InterlockedIncrement((volatile signed __int32 *)(v46 + 20)) == *(_DWORD *)(v46 + 8) )
      {
        v33 = (_QWORD *)(v45 + 312);
        v47 = KeAcquireSpinLockRaiseToDpc(v33 + 105);
        v35 = v47;
        v71 = v47;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 833) + 192) = 150;
        *((_BYTE *)v33 + 833) = (*((_BYTE *)v33 + 833) + 1) & 0xF;
        v36 = *((_BYTE *)v33 + 1016) == 0;
        v37 = (char *)v33 + 884;
        *((_DWORD *)v33 + *((unsigned __int8 *)v33 + 949) + 221) = 150;
        v38 = *((_BYTE *)v33 + 949);
        if ( v36 )
        {
          *((_BYTE *)v33 + 949) = (v38 + 1) & 0xF;
          if ( !*((_BYTE *)v33 + 848) )
          {
            v48 = v33[120];
            *((_BYTE *)v33 + 848) = 1;
            v49 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 1632))(
                    WdfDriverGlobals,
                    v48,
                    v35);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *, int))(WdfFunctions_01033 + 1640))(
              WdfDriverGlobals,
              v49,
              "State Machine Tag",
              1021,
              "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\smengine.c",
              v67);
            ESM_RunStateMachine(v33);
            LOBYTE(v35) = v71;
          }
          goto LABEL_91;
        }
        goto LABEL_88;
      }
    }
    return 1;
  }
  v8 = *(_QWORD *)(a2 + 360);
  if ( v6 == v8 )
    goto LABEL_17;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDiqq(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 80LL), HIBYTE(*(_DWORD *)(a1 + 12)), v8, 20);
  v9 = *(_QWORD *)(v5 + 40);
  if ( *(_BYTE *)(v9 + 1048) && _bittest64((const signed __int64 *)(v9 + 736), 0x25u) )
  {
    v10 = *(_DWORD *)(*(_QWORD *)(v9 + 128) + 20LL);
    if ( *(_DWORD *)(v9 + 644) == 1 )
      v11 = *(unsigned __int16 *)(v9 + 652) | (*(unsigned __int16 *)(v9 + 648) << 16);
    else
      v11 = 0;
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      "USBXHCI.SYS",
      v11,
      v10,
      "Feature_DropStaleEventsWithEventDataSet was effective (CONTROL)");
    if ( !v10 )
      Controller_HwVerifierBreakIfEnabled(
        *(_QWORD *)(v5 + 40),
        *(_QWORD *)(v5 + 48),
        *(_QWORD *)(v5 + 56),
        0x10000000,
        (__int64)"Event TRB received with invalid Event Data Pointer value (CONTROL)",
        0,
        a1);
    return 0;
  }
  else
  {
    Controller_ReportFatalErrorEx(v9, 2, 4126, 0, 0, *(_QWORD *)(v5 + 48), *(_QWORD *)(v5 + 56), v5);
    return 0;
  }
}

```

## disassembly

```asm
0x14000af30  push    rbx
0x14000af32  push    rbp
0x14000af33  push    rsi
0x14000af34  push    rdi
0x14000af35  push    r12
0x14000af37  push    r14
0x14000af39  sub     rsp, 98h
0x14000af40  mov     r12, [rcx]
0x14000af43  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000af4a  mov     rsi, r12
0x14000af4d  mov     rdi, rdx
0x14000af50  and     rsi, 0FFFFFFFFFFFFFFF8h
0x14000af54  mov     r14, rcx
0x14000af57  test    rdx, rdx
0x14000af5a  jz      loc_14000B0A2
0x14000af60  mov     r8, [rdx+168h]
0x14000af67  cmp     rsi, r8
0x14000af6a  jz      loc_14000B0F3
0x14000af70  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000af77  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000af7e  jz      short loc_14000AFB8
0x14000af80  mov     edx, [rcx+0Ch]
0x14000af83  mov     r9d, 14h
0x14000af89  mov     rcx, [rdi+38h]
0x14000af8d  mov     eax, edx
0x14000af8f  mov     [rsp+0C8h+var_80], r8
0x14000af94  mov     [rsp+0C8h+var_88], rsi
0x14000af99  shr     eax, 10h
0x14000af9c  mov     rcx, [rcx+50h]
0x14000afa0  and     eax, 1Fh
0x14000afa3  shr     edx, 18h
0x14000afa6  mov     [rsp+0C8h+var_90], r12
0x14000afab  mov     dword ptr [rsp+0C8h+var_98], eax
0x14000afaf  mov     dword ptr [rsp+0C8h+var_A0], edx
0x14000afb3  call    WPP_RECORDER_SF_DDiqq
0x14000afb8  mov     rcx, [rdi+28h]
0x14000afbc  cmp     byte ptr [rcx+418h], 0
0x14000afc3  jz      loc_14000B05E
0x14000afc9  bt      qword ptr [rcx+2E0h], 25h ; '%'
0x14000afd2  jnb     loc_14000B05E
0x14000afd8  mov     rax, [rcx+80h]
0x14000afdf  mov     esi, [rax+14h]
0x14000afe2  xor     ebx, ebx; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_DropStaleEventsWithEventDataSet was effective (CONTROL)")
0x14000afe4  cmp     dword ptr [rcx+284h], 1
0x14000afeb  jnz     short loc_14000B002
0x14000afed  movzx   edx, word ptr [rcx+288h]
0x14000aff4  movzx   eax, word ptr [rcx+28Ch]
0x14000affb  shl     edx, 10h
0x14000affe  or      edx, eax
0x14000b000  jmp     short loc_14000B004
0x14000b002  mov     edx, ebx
0x14000b004  lea     r9, aFeatureDropsta; "Feature_DropStaleEventsWithEventDataSet"...
0x14000b00b  mov     r8d, esi
0x14000b00e  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x14000b015  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14000b01a  test    esi, esi
0x14000b01c  jnz     short loc_14000B04B
0x14000b01e  mov     r8, [rdi+38h]
0x14000b022  lea     rax, aEventTrbReceiv_1; "Event TRB received with invalid Event D"...
0x14000b029  mov     rdx, [rdi+30h]
0x14000b02d  mov     r9d, 10000000h
0x14000b033  mov     rcx, [rdi+28h]
0x14000b037  mov     [rsp+0C8h+var_98], r14
0x14000b03c  mov     [rsp+0C8h+var_A0], rbx
0x14000b041  mov     [rsp+0C8h+var_A8], rax
0x14000b046  call    Controller_HwVerifierBreakIfEnabled
0x14000b04b  xor     al, al
0x14000b04d  add     rsp, 98h
0x14000b054  pop     r14
0x14000b056  pop     r12
0x14000b058  pop     rdi
0x14000b059  pop     rsi
0x14000b05a  pop     rbp
0x14000b05b  pop     rbx
0x14000b05c  retn
0x14000b05e  mov     rax, [rdi+38h]
0x14000b062  xor     ebx, ebx
0x14000b064  mov     [rsp+0C8h+var_90], rdi
0x14000b069  xor     r9d, r9d
0x14000b06c  mov     [rsp+0C8h+var_98], rax
0x14000b071  mov     edx, 2
0x14000b076  mov     rax, [rdi+30h]
0x14000b07a  mov     r8d, 101Eh
0x14000b080  mov     [rsp+0C8h+var_A0], rax
0x14000b085  mov     [rsp+0C8h+var_A8], rbx
0x14000b08a  call    Controller_ReportFatalErrorEx
0x14000b08f  xor     al, al
0x14000b091  add     rsp, 98h
0x14000b098  pop     r14
0x14000b09a  pop     r12
0x14000b09c  pop     rdi
0x14000b09d  pop     rsi
0x14000b09e  pop     rbp
0x14000b09f  pop     rbx
0x14000b0a0  retn
0x14000b0a2  mov     rdi, [rsi+38h]
0x14000b0a6  mov     r8, [rdi+168h]
0x14000b0ad  cmp     rsi, r8
0x14000b0b0  jz      short loc_14000B0F3
0x14000b0b2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b0b9  jz      short loc_14000B0F3
0x14000b0bb  mov     edx, [rcx+0Ch]
0x14000b0be  mov     r9d, 15h
0x14000b0c4  mov     rcx, [rdi+38h]
0x14000b0c8  mov     eax, edx
0x14000b0ca  mov     [rsp+0C8h+var_80], r8
0x14000b0cf  mov     [rsp+0C8h+var_88], rsi
0x14000b0d4  shr     eax, 10h
0x14000b0d7  mov     rcx, [rcx+50h]
0x14000b0db  and     eax, 1Fh
0x14000b0de  shr     edx, 18h
0x14000b0e1  mov     [rsp+0C8h+var_90], r12
0x14000b0e6  mov     dword ptr [rsp+0C8h+var_98], eax
0x14000b0ea  mov     dword ptr [rsp+0C8h+var_A0], edx
0x14000b0ee  call    WPP_RECORDER_SF_DDiqq
0x14000b0f3  and     r12d, 4; __annotation("TMF:",
0x14000b0f7  mov     [rsp+0C8h+var_38], r13
0x14000b0ff  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000b106  mov     [rsp+0C8h+var_40], r15
0x14000b10e  jz      short loc_14000B173
0x14000b110  mov     ebx, [r14+0Ch]
0x14000b114  mov     r9d, 16h
0x14000b11a  mov     r11d, [r14+8]
0x14000b11e  mov     r10d, ebx
0x14000b121  mov     rax, [r14]
0x14000b124  mov     r8d, r11d
0x14000b127  mov     rcx, [rdi+38h]
0x14000b12b  mov     edx, ebx
0x14000b12d  mov     [rsp+0C8h+var_70], rax
0x14000b132  and     r8d, 0FFFFFFh
0x14000b139  shr     r10d, 2
0x14000b13d  and     r10d, 1
0x14000b141  shr     r11d, 18h
0x14000b145  mov     rcx, [rcx+50h]
0x14000b149  mov     [rsp+0C8h+var_78], r10d
0x14000b14e  mov     dword ptr [rsp+0C8h+var_80], r8d
0x14000b153  mov     dword ptr [rsp+0C8h+var_88], r11d
0x14000b158  shr     edx, 10h
0x14000b15b  and     edx, 1Fh
0x14000b15e  mov     [rsp+0C8h+var_90], r14
0x14000b163  shr     ebx, 18h
0x14000b166  mov     dword ptr [rsp+0C8h+var_98], edx
0x14000b16a  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x14000b16e  call    WPP_RECORDER_SF_DDqLDDi
0x14000b173  mov     edx, [r14+0Ch]
0x14000b177  lea     r8, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14000b17e  mov     rcx, [rdi+38h]
0x14000b182  mov     eax, edx
0x14000b184  shr     eax, 10h
0x14000b187  and     eax, 1Fh
0x14000b18a  cmp     eax, [rcx+98h]
0x14000b190  jz      short loc_14000B1C9
0x14000b192  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b199  jz      short loc_14000B1C9
0x14000b19b  mov     rcx, [rcx+50h]
0x14000b19f  mov     r9d, 17h
0x14000b1a5  shr     edx, 18h
0x14000b1a8  mov     dword ptr [rsp+0C8h+var_98], eax
0x14000b1ac  mov     dword ptr [rsp+0C8h+var_A0], edx
0x14000b1b0  mov     dl, 2
0x14000b1b2  mov     [rsp+0C8h+var_A8], r8
0x14000b1b7  mov     r8d, 0Eh
0x14000b1bd  call    WPP_RECORDER_SF_DD
0x14000b1c2  lea     r8, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14000b1c9  mov     rax, [rdi+30h]
0x14000b1cd  movzx   ecx, byte ptr [r14+0Fh]
0x14000b1d2  cmp     cl, [rax+8Fh]
0x14000b1d8  jz      short loc_14000B215
0x14000b1da  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b1e1  jz      short loc_14000B215
0x14000b1e3  movzx   edx, word ptr [r14+0Eh]
0x14000b1e8  mov     eax, ecx
0x14000b1ea  mov     rcx, [rdi+38h]
0x14000b1ee  and     edx, 1Fh
0x14000b1f1  mov     dword ptr [rsp+0C8h+var_98], edx
0x14000b1f5  mov     r9d, 18h
0x14000b1fb  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14000b1ff  mov     dl, 2
0x14000b201  mov     [rsp+0C8h+var_A8], r8
0x14000b206  mov     r8d, 0Eh
0x14000b20c  mov     rcx, [rcx+50h]
0x14000b210  call    WPP_RECORDER_SF_DD
0x14000b215  mov     r13d, [r14+8]
0x14000b219  xor     ebx, ebx
0x14000b21b  mov     r10d, [rsi+68h]
0x14000b21f  and     r13d, 0FFFFFFh
0x14000b226  cmp     r13d, r10d
0x14000b229  jbe     short loc_14000B281
0x14000b22b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b232  jz      short loc_14000B27E
0x14000b234  mov     rax, [rdi+30h]
0x14000b238  mov     r9d, 19h
0x14000b23e  mov     rcx, [rdi+38h]
0x14000b242  mov     r8d, 0Eh
0x14000b248  mov     dword ptr [rsp+0C8h+var_88], r10d
0x14000b24d  mov     dword ptr [rsp+0C8h+var_90], r13d
0x14000b252  movzx   edx, byte ptr [rax+8Fh]
0x14000b259  mov     eax, [rcx+98h]
0x14000b25f  mov     rcx, [rcx+50h]
0x14000b263  mov     dword ptr [rsp+0C8h+var_98], eax
0x14000b267  lea     rax, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14000b26e  mov     dword ptr [rsp+0C8h+var_A0], edx
0x14000b272  mov     dl, 3
0x14000b274  mov     [rsp+0C8h+var_A8], rax
0x14000b279  call    WPP_RECORDER_SF_DDDD
0x14000b27e  mov     r13d, ebx
0x14000b281  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b288  jz      short loc_14000B2D2
0x14000b28a  mov     rax, [rdi+30h]
0x14000b28e  mov     r9d, 1Ah
0x14000b294  mov     rcx, [rdi+38h]
0x14000b298  mov     [rsp+0C8h+var_88], rsi
0x14000b29d  movzx   edx, byte ptr [rax+8Fh]
0x14000b2a4  mov     rax, [rsi+18h]
0x14000b2a8  mov     [rsp+0C8h+var_90], rax
0x14000b2ad  mov     eax, [rcx+98h]
0x14000b2b3  mov     rcx, [rcx+50h]
0x14000b2b7  mov     dword ptr [rsp+0C8h+var_98], eax
0x14000b2bb  lea     rax, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14000b2c2  mov     dword ptr [rsp+0C8h+var_A0], edx
0x14000b2c6  mov     dl, 4
0x14000b2c8  mov     [rsp+0C8h+var_A8], rax
0x14000b2cd  call    WPP_RECORDER_SF_DDqq
0x14000b2d2  test    r12, r12
0x14000b2d5  jnz     short loc_14000B301
0x14000b2d7  mov     rax, [rsi+30h]
0x14000b2db  mov     [rsi+6Ch], r13d
0x14000b2df  mov     ecx, [rax+20h]
0x14000b2e2  test    cl, 1
0x14000b2e5  jz      short loc_14000B301
0x14000b2e7  cmp     dword ptr [rsi+40h], 2
0x14000b2eb  jnz     short loc_14000B301
0x14000b2ed  mov     rdx, [rsi+58h]
0x14000b2f1  mov     rcx, [rsi+50h]; void *
0x14000b2f5  mov     r8d, r13d; Size
0x14000b2f8  mov     rdx, [rdx+10h]; Src
0x14000b2fc  call    memmove
0x14000b301  mov     rax, [rdi+38h]
0x14000b305  movzx   ecx, byte ptr [r14+0Bh]
0x14000b30a  mov     rdx, [rax]
0x14000b30d  bt      qword ptr [rdx+2E0h], 3Eh ; '>'
0x14000b316  jnb     short loc_14000B31D
0x14000b318  cmp     cl, 0C7h
0x14000b31b  jz      short loc_14000B348
0x14000b31d  test    byte ptr [rdx+2E8h], 20h
0x14000b324  jz      short loc_14000B32B
0x14000b326  cmp     cl, 0C6h
0x14000b329  jz      short loc_14000B348
0x14000b32b  cmp     cl, 24h ; '$'
0x14000b32e  ja      loc_14000B536
0x14000b334  mov     rdx, 150000045Ch
0x14000b33e  bt      rdx, rcx
0x14000b342  jnb     loc_14000B536
0x14000b348  mov     [rsi+7Ch], ecx
0x14000b34b  mov     rdx, [rdi+38h]
0x14000b34f  prefetchw byte ptr [rdx+20h]
0x14000b353  mov     eax, [rdx+20h]
0x14000b356  nop     word ptr [rax+rax+00000000h]
0x14000b360  mov     ecx, eax
0x14000b362  or      ecx, 20h
0x14000b365  lock cmpxchg [rdx+20h], ecx
0x14000b36a  jnz     short loc_14000B360
0x14000b36c  test    al, 20h
0x14000b36e  jz      loc_14000B431
0x14000b374  mov     rdi, [rdx+18h]
0x14000b378  xorps   xmm0, xmm0
0x14000b37b  mov     rsi, [rdx+8]
0x14000b37f  mov     rbx, [rdx]
0x14000b382  movups  [rsp+0C8h+var_68], xmm0
0x14000b387  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000b38e  lea     r14, aReceivedDuplic; "Received duplicate Transfer Event TRB w"...
0x14000b395  jz      short loc_14000B3A5
0x14000b397  mov     rcx, [rbx+48h]
0x14000b39b  mov     [rsp+0C8h+var_A0], r14
0x14000b3a0  call    WPP_RECORDER_SF_s
0x14000b3a5  mov     eax, [rbx+350h]
0x14000b3ab  bt      rax, 19h
0x14000b3b0  jnb     short loc_14000B3E2
0x14000b3b2  cmp     byte ptr [rbx+31Dh], 0
0x14000b3b9  jnz     short loc_14000B3E2
0x14000b3bb  mov     rdx, r14
0x14000b3be  lea     rcx, Format; "xHCI Hardware Verifier Break: %s\n"
0x14000b3c5  call    cs:__imp_DbgPrint
0x14000b3cc  nop     dword ptr [rax+rax+00h]
0x14000b3d1  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14000b3d8  nop     dword ptr [rax+rax+00h]
0x14000b3dd  test    al, al
0x14000b3df  jnz     short loc_14000B3E2
0x14000b3e1  int     3; Trap to Debugger
0x14000b3e2  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 10h
0x14000b3e9  xorps   xmm0, xmm0
0x14000b3ec  movups  [rsp+0C8h+var_68], xmm0
0x14000b3f1  jz      loc_14000BA51
0x14000b3f7  lea     rax, [rsp+0C8h+var_68]
0x14000b3fc  mov     [rsp+0C8h+var_80], rax
0x14000b401  lea     rax, [rsp+0C8h+var_68]
0x14000b406  mov     r9, [rbx+8]
0x14000b40a  mov     [rsp+0C8h+var_88], rax
0x14000b40f  mov     [rsp+0C8h+var_90], r14
0x14000b414  mov     [rsp+0C8h+var_98], 2000000h
  ... truncated ...
```
