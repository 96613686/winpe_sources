# Endpoint_TransferEventHandler

- ea: `0x1400029b0`
- end: `0x1400033c2`
- name: `Endpoint_TransferEventHandler`
- size: `2578`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400028a0`

## callees

- `0x140002568`
- `0x1400029b0`
- `0x1400038c0`
- `0x140009ea4`
- `0x14000a43c`
- `0x14000a7b0`
- `0x14000af30`
- `0x14000ba7c`
- `0x14000c264`
- `0x140028524`
- `0x14002b300`
- `0x140032a48`
- `0x140033204`
- `0x140034218`
- `0x140037214`
- `0x140057db0`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140003159`
- `ntoskrnl!DbgPrint` at `0x140003159`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140003165`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140003165`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003093`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003093`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031f2`

## string_xrefs

- `0x14000306a`: `Received duplicate Transfer Event TRB with Halted Completion Code`
- `0x140003377`: `Unrecognized completion code in Transfer Event TRB`

## pseudocode

```c
void __fastcall Endpoint_TransferEventHandler(_QWORD *a1, __int64 a2, int a3, int a4)
{
  __int64 v5; // rcx
  __int64 v7; // rdx
  int v8; // r8d
  unsigned __int8 *v9; // rbp
  __int64 v10; // rdx
  signed __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rax
  signed __int64 v14; // rdx
  int v15; // ebp
  int v16; // r14d
  char v17; // al
  __int64 v18; // rcx
  unsigned int v19; // edi
  int v20; // edx
  __int64 v21; // rsi
  __int64 v22; // rcx
  int v23; // r9d
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // ecx
  __int64 v27; // rdi
  __int64 v28; // rbp
  __int64 v29; // rbx
  bool v30; // zf
  const char *v31; // r14
  __int64 v32; // rbx
  KIRQL v33; // al
  bool v34; // zf
  __int64 v35; // rdx
  __int64 v36; // r8
  char v37; // al
  __int64 v38; // rax
  int v39; // edx
  int v40; // [rsp+20h] [rbp-68h]
  int v41; // [rsp+28h] [rbp-60h]
  int v42; // [rsp+30h] [rbp-58h]
  _QWORD *v43; // [rsp+38h] [rbp-50h]
  int v44; // [rsp+40h] [rbp-48h]
  __int128 v45; // [rsp+50h] [rbp-38h] BYREF
  char v46; // [rsp+98h] [rbp+10h] BYREF
  KIRQL v47; // [rsp+A0h] [rbp+18h]

  v46 = 0;
  v5 = *(_QWORD *)a2;
  v7 = *(_QWORD *)(*(_QWORD *)a2 + 744LL);
  if ( (v7 & 4) != 0 && *((_BYTE *)a1 + 11) == 2 && (*((_DWORD *)a1 + 3) & 4) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_ddqL(*(_QWORD *)(a2 + 80), v7, a3, 94);
    return;
  }
  v8 = *((unsigned __int8 *)a1 + 11);
  v9 = (unsigned __int8 *)a1 + 11;
  if ( _bittest64((const signed __int64 *)(v5 + 736), 0x3Eu) && (_BYTE)v8 == 0xC7 )
    goto LABEL_14;
  if ( (v7 & 0x20) != 0 )
  {
    if ( (_BYTE)v8 == 0xC6 )
    {
LABEL_14:
      if ( !*(_BYTE *)(a2 + 37) )
      {
        v10 = *(_QWORD *)(a2 + 88);
        if ( v10 )
        {
          (*(void (__fastcall **)(_QWORD *))(*(_QWORD *)(v10 + 32) + 88LL))(a1);
        }
        else if ( (*(_DWORD *)a1 & 3) != 0 )
        {
          if ( (*(_DWORD *)a1 & 3) != 1 && (unsigned __int64)(*(_DWORD *)a1 & 3) - 2 <= 1 )
          {
            if ( (*((_DWORD *)a1 + 3) & 4) != 0 )
              Bulk_ProcessTransferEventWithED1(a1, 0);
            else
              Bulk_ProcessTransferEventWithED0(a1, 0);
          }
        }
        else if ( (*((_DWORD *)a1 + 3) & 4) != 0 )
        {
          Control_ProcessTransferEventWithED1(a1, 0);
        }
        else
        {
          Control_ProcessTransferEventWithED0(a1, 0);
        }
        return;
      }
      v11 = *a1;
      if ( !*a1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v44 = *((unsigned __int8 *)a1 + 11);
          v43 = a1;
          v42 = *(_DWORD *)(a2 + 152);
          v41 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + 143LL);
          WPP_RECORDER_SF_ddqL(*(_QWORD *)(a2 + 80), v7, v8, 96);
        }
        goto LABEL_82;
      }
      v12 = *(_QWORD *)(a2 + 144);
      v13 = *(_QWORD *)(v12 + 32);
      v14 = *(_QWORD *)(v13 + 24);
      if ( v11 >= v14 && v11 < v14 + *(unsigned int *)(v13 + 44) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v44 = *((unsigned __int8 *)a1 + 11);
          v43 = a1;
          v42 = *(_DWORD *)(a2 + 152);
          v41 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + 143LL);
          WPP_RECORDER_SF_ddqL(*(_QWORD *)(a2 + 80), v14, v8, 97);
        }
        goto LABEL_82;
      }
      v15 = 1;
      v16 = 1;
      if ( !*(_DWORD *)(v12 + 8) )
      {
LABEL_48:
        if ( (*((_DWORD *)a1 + 3) & 4) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_ddi(*(_QWORD *)(a2 + 80), v14, v8, 99);
          }
          v18 = *(_QWORD *)a2;
          if ( *(_BYTE *)(*(_QWORD *)a2 + 1048LL) && _bittest64((const signed __int64 *)(v18 + 736), 0x25u) )
          {
            if ( *(_DWORD *)(v18 + 644) == 1 )
              v19 = *(unsigned __int16 *)(v18 + 652) | (*(unsigned __int16 *)(v18 + 648) << 16);
            else
              v19 = 0;
            MicrosoftTelemetryAssertTriggeredArgsMsgKM(
              "USBXHCI.SYS",
              v19,
              1,
              "Feature_DropStaleEventsWithEventDataSet was effective");
          }
          else
          {
            Controller_ReportFatalErrorEx(v18, 2, 4126, 0, 0, *(_QWORD *)(a2 + 16), a2, 0);
          }
          return;
        }
        if ( (unsigned __int8)(*((_BYTE *)a1 + 11) - 26) > 2u )
        {
          v21 = *(_QWORD *)(a2 + 144);
          v46 = 0;
          if ( !*(_DWORD *)(v21 + 8) )
          {
LABEL_65:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v14) = 2;
              WPP_RECORDER_SF_ddi(*(_QWORD *)(a2 + 80), v14, v8, 104);
            }
            Controller_ReportFatalErrorEx(*(_QWORD *)a2, 2, 4127, 0, 0, *(_QWORD *)(a2 + 16), a2, 0);
            return;
          }
          while ( 1 )
          {
            v22 = *(_QWORD *)(104LL * (unsigned int)(v15 - 1) + *(_QWORD *)(a2 + 144) + 48);
            if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)(v22 + 32) + 80LL))(
                   v22,
                   *a1,
                   &v46) )
            {
              break;
            }
            if ( (unsigned int)++v15 > *(_DWORD *)(v21 + 8) )
              goto LABEL_65;
          }
          if ( _bittest64((const signed __int64 *)(*(_QWORD *)a2 + 736LL), 0x26u) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return;
            v23 = 101;
          }
          else
          {
            if ( !v46 || !(unsigned __int8)Endpoint_StoppedCompletionCode(*((unsigned __int8 *)a1 + 11)) )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v14) = 2;
                WPP_RECORDER_SF_ddi(*(_QWORD *)(a2 + 80), v14, v8, 103);
              }
              Controller_ReportFatalErrorEx(*(_QWORD *)a2, 2, 4128, 0, 0, *(_QWORD *)(a2 + 16), a2, 0);
              return;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return;
            v23 = 102;
          }
          LOBYTE(v14) = 3;
          WPP_RECORDER_SF_ddi(*(_QWORD *)(a2 + 80), v14, v8, v23);
          return;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_DD(
            *(_QWORD *)(a2 + 80),
            v14,
            13,
            100,
            (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
            *(_BYTE *)(*(_QWORD *)(a2 + 16) + 143LL),
            *(_DWORD *)(a2 + 152));
        }
LABEL_82:
        v24 = *((unsigned __int8 *)a1 + 11);
        if ( _bittest64((const signed __int64 *)(*(_QWORD *)a2 + 736LL), 0x3Eu) && (_BYTE)v24 == 0xC7
          || (*(_BYTE *)(*(_QWORD *)a2 + 744LL) & 0x20) != 0 && (_BYTE)v24 == 0xC6
          || (unsigned __int8)v24 <= 0x24u && (v25 = 0x150000045CLL, _bittest64(&v25, v24)) )
        {
          _m_prefetchw((const void *)(a2 + 32));
          if ( (_InterlockedOr((volatile signed __int32 *)(a2 + 32), 0x20u) & 0x20) != 0 )
          {
            v27 = *(_QWORD *)(a2 + 24);
            v28 = *(_QWORD *)(a2 + 8);
            v29 = *(_QWORD *)a2;
            v45 = 0;
            v30 = WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            v31 = "Received duplicate Transfer Event TRB with Halted Completion Code";
LABEL_94:
            if ( !v30 )
              WPP_RECORDER_SF_s(*(_QWORD *)(v29 + 72), v24, v8, a4, v40, (__int64)v31);
            if ( (*(_DWORD *)(v29 + 848) & 0x2000000) != 0 && !*(_BYTE *)(v29 + 797) )
            {
              DbgPrint("xHCI Hardware Verifier Break: %s\n", v31);
              if ( !KdRefreshDebuggerNotPresent() )
                __debugbreak();
            }
            v45 = 0;
            if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 0x10) != 0 )
              McTemplateK0pppxsb16b16_EtwWriteTransfer(
                v26,
                v24,
                v8,
                *(_QWORD *)(v29 + 8),
                v28,
                v27,
                0,
                (__int64)v31,
                (__int64)&v45,
                (__int64)&v45);
            return;
          }
          *(_DWORD *)(*(_QWORD *)(a2 + 144) + 24LL) = v24;
          _InterlockedOr((volatile signed __int32 *)(a2 + 32), 4u);
          v32 = a2 + 312;
          v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v32 + 840));
          *(_DWORD *)(v32 + 4LL * *(unsigned __int8 *)(v32 + 833) + 768) = 154;
          *(_BYTE *)(v32 + 833) = (*(_BYTE *)(v32 + 833) + 1) & 0xF;
          v34 = *(_BYTE *)(v32 + 1016) == 0;
          v35 = v32 + 884;
          *(_DWORD *)(v32 + 884 + 4LL * *(unsigned __int8 *)(v32 + 949)) = 154;
        }
        else
        {
          LOBYTE(v24) = v24 - 26;
          if ( (unsigned __int8)v24 > 2u )
            return;
          _m_prefetchw((const void *)(a2 + 32));
          if ( (_InterlockedOr((volatile signed __int32 *)(a2 + 32), 0x10u) & 0x10) != 0 )
          {
            v27 = *(_QWORD *)(a2 + 24);
            v28 = *(_QWORD *)(a2 + 8);
            v29 = *(_QWORD *)a2;
            v45 = 0;
            v30 = WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            v31 = "Received duplicate Stopped Transfer Events";
            goto LABEL_94;
          }
          _m_prefetchw((const void *)(a2 + 32));
          if ( (_InterlockedXor((volatile signed __int32 *)(a2 + 32), 8u) & 8) == 0 )
            return;
          v32 = a2 + 312;
          v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v32 + 840));
          *(_DWORD *)(v32 + 4LL * *(unsigned __int8 *)(v32 + 833) + 768) = 118;
          *(_BYTE *)(v32 + 833) = (*(_BYTE *)(v32 + 833) + 1) & 0xF;
          v34 = *(_BYTE *)(v32 + 1016) == 0;
          v35 = v32 + 884;
          *(_DWORD *)(v32 + 884 + 4LL * *(unsigned __int8 *)(v32 + 949)) = 118;
        }
        v36 = v33;
        v47 = v33;
        v37 = *(_BYTE *)(v35 + 65);
        if ( v34 )
        {
          *(_BYTE *)(v35 + 65) = (v37 + 1) & 0xF;
          if ( !*(_BYTE *)(v32 + 848) )
          {
            *(_BYTE *)(v32 + 848) = 1;
            v38 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 1632))(
                    WdfDriverGlobals,
                    *(_QWORD *)(v32 + 960),
                    v36);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *, int, int, _QWORD *, int))(WdfFunctions_01033 + 1640))(
              WdfDriverGlobals,
              v38,
              "State Machine Tag",
              1021,
              "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\smengine.c",
              v41,
              v42,
              v43,
              v44);
            ESM_RunStateMachine((PVOID)v32);
            LOBYTE(v36) = v47;
          }
        }
        else
        {
          *(_BYTE *)(v35 + 65) = (v37 + 1) & 0xF;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v32 + 840), v36);
        return;
      }
      while ( 1 )
      {
        v14 = *(_QWORD *)(104LL * (unsigned int)(v16 - 1) + *(_QWORD *)(a2 + 144) + 48);
        if ( v14 )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v14 + 32) + 88LL))(a1);
        }
        else if ( (*(_DWORD *)a1 & 3) != 0 )
        {
          if ( (*(_DWORD *)a1 & 3) == 1 || (unsigned __int64)(*(_DWORD *)a1 & 3) - 2 > 1 )
            goto LABEL_47;
          if ( (*((_DWORD *)a1 + 3) & 4) != 0 )
            v17 = Bulk_ProcessTransferEventWithED1(a1, 0);
          else
            v17 = Bulk_ProcessTransferEventWithED0(a1, 0);
        }
        else if ( (*((_DWORD *)a1 + 3) & 4) != 0 )
        {
          v17 = Control_ProcessTransferEventWithED1(a1, 0);
        }
        else
        {
          v17 = Control_ProcessTransferEventWithED0(a1, 0);
        }
        if ( v17 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            v20 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + 143LL);
            LOBYTE(v20) = 5;
            WPP_RECORDER_SF_ddd(
              *(_QWORD *)(a2 + 80),
              v20,
              13,
              98,
              (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
              *(_BYTE *)(*(_QWORD *)(a2 + 16) + 143LL),
              *(_DWORD *)(a2 + 152),
              v16 + 1);
          }
          return;
        }
LABEL_47:
        if ( (unsigned int)++v16 > *(_DWORD *)(v12 + 8) )
          goto LABEL_48;
      }
    }
    v9 = (unsigned __int8 *)a1 + 11;
  }
  if ( (_BYTE)v8 != 5 && (_BYTE)v8 != 33 && (unsigned __int8)(v8 + 64) > 0x1Fu )
    goto LABEL_14;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v39 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + 143LL);
    LOBYTE(v39) = 2;
    WPP_RECORDER_SF_ddd(
      *(_QWORD *)(v5 + 72),
      v39,
      13,
      95,
      (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
      *(_BYTE *)(*(_QWORD *)(a2 + 16) + 143LL),
      *(_DWORD *)(a2 + 152),
      v8);
    v9 = (unsigned __int8 *)a1 + 11;
  }
  Controller_HwVerifierBreakIfEnabled(
    *(_QWORD *)a2,
    *(_QWORD *)(a2 + 8),
    *(_QWORD *)(a2 + 24),
    2048,
    (__int64)"Unrecognized completion code in Transfer Event TRB",
    0,
    a2 + 200);
  Controller_ReportFatalErrorEx(*(_QWORD *)a2, 2, 4112, *v9, 0, *(_QWORD *)(a2 + 16), a2, 0);
}

```

## disassembly

```asm
0x1400029b0  push    rbx
0x1400029b2  push    rsi
0x1400029b3  push    rdi
0x1400029b4  sub     rsp, 70h
0x1400029b8  mov     rdi, rcx
0x1400029bb  mov     [rsp+88h+arg_8], 0
0x1400029c3  mov     rcx, [rdx]
0x1400029c6  mov     rbx, rdx
0x1400029c9  mov     rdx, [rcx+2E8h]
0x1400029d0  test    dl, 4
0x1400029d3  jz      short loc_140002A34
0x1400029d5  cmp     byte ptr [rdi+0Bh], 2
0x1400029d9  jnz     short loc_140002A34
0x1400029db  mov     eax, [rdi+0Ch]
0x1400029de  test    al, 4
0x1400029e0  jnz     short loc_140002A34
0x1400029e2  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400029e9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400029f0  jz      loc_140002EAE
0x1400029f6  mov     rax, [rbx+10h]
0x1400029fa  mov     r9d, 5Eh ; '^'
0x140002a00  mov     dword ptr [rsp+88h+var_48], 2
0x140002a08  mov     [rsp+88h+var_50], rdi
0x140002a0d  movzx   ecx, byte ptr [rax+8Fh]
0x140002a14  mov     eax, [rbx+98h]
0x140002a1a  mov     dword ptr [rsp+88h+var_58], eax
0x140002a1e  mov     dword ptr [rsp+88h+var_60], ecx
0x140002a22  mov     rcx, [rbx+50h]
0x140002a26  call    WPP_RECORDER_SF_ddqL
0x140002a2b  add     rsp, 70h
0x140002a2f  pop     rdi
0x140002a30  pop     rsi
0x140002a31  pop     rbx
0x140002a32  retn
0x140002a34  bt      qword ptr [rcx+2E0h], 3Eh ; '>'
0x140002a3d  movzx   r8d, byte ptr [rdi+0Bh]
0x140002a42  mov     [rsp+88h+arg_0], rbp
0x140002a4a  lea     rbp, [rdi+0Bh]
0x140002a4e  mov     [rsp+88h+var_28], r15
0x140002a53  jnb     short loc_140002A5B
0x140002a55  cmp     r8b, 0C7h
0x140002a59  jz      short loc_140002A8A
0x140002a5b  test    dl, 20h
0x140002a5e  jz      short loc_140002A6A
0x140002a60  cmp     r8b, 0C6h
0x140002a64  jz      short loc_140002A8A
0x140002a66  lea     rbp, [rdi+0Bh]
0x140002a6a  cmp     r8b, 5
0x140002a6e  jz      loc_140003303
0x140002a74  cmp     r8b, 21h ; '!'
0x140002a78  jz      loc_140003303
0x140002a7e  lea     eax, [r8+40h]
0x140002a82  cmp     al, 1Fh
0x140002a84  jbe     loc_140003303
0x140002a8a  cmp     byte ptr [rbx+25h], 0
0x140002a8e  jnz     short loc_140002B0F
0x140002a90  mov     rdx, [rbx+58h]
0x140002a94  test    rdx, rdx
0x140002a97  jz      short loc_140002AAE
0x140002a99  mov     rax, [rdx+20h]
0x140002a9d  mov     rcx, rdi
0x140002aa0  mov     rax, [rax+58h]
0x140002aa4  call    _guard_dispatch_icall
0x140002aa9  jmp     loc_140002EA1
0x140002aae  mov     eax, [rdi]
0x140002ab0  and     eax, 3
0x140002ab3  jz      short loc_140002AEF
0x140002ab5  sub     rax, 1
0x140002ab9  jz      loc_140002EA1
0x140002abf  sub     rax, 1
0x140002ac3  jz      short loc_140002ACF
0x140002ac5  cmp     rax, 1
0x140002ac9  jnz     loc_140002EA1
0x140002acf  mov     eax, [rdi+0Ch]
0x140002ad2  xor     edx, edx
0x140002ad4  mov     rcx, rdi
0x140002ad7  test    al, 4
0x140002ad9  jz      short loc_140002AE5
0x140002adb  call    Bulk_ProcessTransferEventWithED1
0x140002ae0  jmp     loc_140002EA1
0x140002ae5  call    Bulk_ProcessTransferEventWithED0
0x140002aea  jmp     loc_140002EA1
0x140002aef  mov     eax, [rdi+0Ch]
0x140002af2  xor     edx, edx
0x140002af4  mov     rcx, rdi
0x140002af7  test    al, 4
0x140002af9  jz      short loc_140002B05
0x140002afb  call    Control_ProcessTransferEventWithED1
0x140002b00  jmp     loc_140002EA1
0x140002b05  call    Control_ProcessTransferEventWithED0
0x140002b0a  jmp     loc_140002EA1
0x140002b0f  mov     rcx, [rdi]
0x140002b12  mov     [rsp+88h+var_20], r14
0x140002b17  test    rcx, rcx
0x140002b1a  jnz     short loc_140002B67
0x140002b1c  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002b23  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002b2a  jz      loc_140002FF6
0x140002b30  mov     rax, [rbx+10h]
0x140002b34  mov     r9d, 60h ; '`'
0x140002b3a  mov     dword ptr [rsp+88h+var_48], r8d
0x140002b3f  mov     [rsp+88h+var_50], rdi
0x140002b44  movzx   ecx, byte ptr [rax+8Fh]
0x140002b4b  mov     eax, [rbx+98h]
0x140002b51  mov     dword ptr [rsp+88h+var_58], eax
0x140002b55  mov     dword ptr [rsp+88h+var_60], ecx
0x140002b59  mov     rcx, [rbx+50h]
0x140002b5d  call    WPP_RECORDER_SF_ddqL
0x140002b62  jmp     loc_140002FF6
0x140002b67  mov     rsi, [rbx+90h]
0x140002b6e  mov     rax, [rsi+20h]
0x140002b72  mov     rdx, [rax+18h]
0x140002b76  cmp     rcx, rdx
0x140002b79  jl      short loc_140002BD1
0x140002b7b  mov     eax, [rax+2Ch]
0x140002b7e  add     rax, rdx
0x140002b81  cmp     rcx, rax
0x140002b84  jge     short loc_140002BD1
0x140002b86  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002b8d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002b94  jz      loc_140002FF6
0x140002b9a  mov     rax, [rbx+10h]
0x140002b9e  mov     r9d, 61h ; 'a'
0x140002ba4  mov     dword ptr [rsp+88h+var_48], r8d
0x140002ba9  mov     [rsp+88h+var_50], rdi
0x140002bae  movzx   ecx, byte ptr [rax+8Fh]
0x140002bb5  mov     eax, [rbx+98h]
0x140002bbb  mov     dword ptr [rsp+88h+var_58], eax
0x140002bbf  mov     dword ptr [rsp+88h+var_60], ecx
0x140002bc3  mov     rcx, [rbx+50h]
0x140002bc7  call    WPP_RECORDER_SF_ddqL
0x140002bcc  jmp     loc_140002FF6
0x140002bd1  mov     ebp, 1
0x140002bd6  mov     r14d, ebp
0x140002bd9  cmp     [rsi+8], ebp
0x140002bdc  jb      loc_140002C84
0x140002be2  nop     dword ptr [rax+00h]
0x140002be6  nop     word ptr [rax+rax+00000000h]
0x140002bf0  mov     rax, [rbx+90h]
0x140002bf7  lea     ecx, [r14-1]
0x140002bfb  imul    rdx, rcx, 68h ; 'h'
0x140002bff  mov     rdx, [rdx+rax+30h]
0x140002c04  test    rdx, rdx
0x140002c07  jz      short loc_140002C1B
0x140002c09  mov     rax, [rdx+20h]
0x140002c0d  mov     rcx, rdi
0x140002c10  mov     rax, [rax+58h]
0x140002c14  call    _guard_dispatch_icall
0x140002c19  jmp     short loc_140002C67
0x140002c1b  mov     eax, [rdi]
0x140002c1d  and     eax, 3
0x140002c20  jz      short loc_140002C4F
0x140002c22  sub     rax, rbp
0x140002c25  jz      short loc_140002C4B
0x140002c27  sub     rax, rbp
0x140002c2a  jz      short loc_140002C31
0x140002c2c  cmp     rax, rbp
0x140002c2f  jnz     short loc_140002C4B
0x140002c31  mov     eax, [rdi+0Ch]
0x140002c34  xor     edx, edx
0x140002c36  mov     rcx, rdi
0x140002c39  test    al, 4
0x140002c3b  jz      short loc_140002C44
0x140002c3d  call    Bulk_ProcessTransferEventWithED1
0x140002c42  jmp     short loc_140002C67
0x140002c44  call    Bulk_ProcessTransferEventWithED0
0x140002c49  jmp     short loc_140002C67
0x140002c4b  xor     al, al
0x140002c4d  jmp     short loc_140002C6F
0x140002c4f  mov     eax, [rdi+0Ch]
0x140002c52  xor     edx, edx
0x140002c54  mov     rcx, rdi
0x140002c57  test    al, 4
0x140002c59  jz      short loc_140002C62
0x140002c5b  call    Control_ProcessTransferEventWithED1
0x140002c60  jmp     short loc_140002C67
0x140002c62  call    Control_ProcessTransferEventWithED0
0x140002c67  test    al, al
0x140002c69  jnz     loc_140002D11
0x140002c6f  inc     r14d
0x140002c72  cmp     r14d, [rsi+8]
0x140002c76  jbe     loc_140002BF0
0x140002c7c  test    al, al
0x140002c7e  jnz     loc_140002E9C
0x140002c84  mov     eax, [rdi+0Ch]
0x140002c87  test    al, 4
0x140002c89  jz      loc_140002DCC
0x140002c8f  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002c96  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002c9d  jz      short loc_140002CD1
0x140002c9f  mov     rax, [rbx+10h]
0x140002ca3  mov     r9d, 63h ; 'c'
0x140002ca9  mov     dl, 2
0x140002cab  movzx   ecx, byte ptr [rax+8Fh]
0x140002cb2  mov     rax, [rdi]
0x140002cb5  mov     [rsp+88h+var_50], rax
0x140002cba  mov     eax, [rbx+98h]
0x140002cc0  mov     dword ptr [rsp+88h+var_58], eax
0x140002cc4  mov     dword ptr [rsp+88h+var_60], ecx
0x140002cc8  mov     rcx, [rbx+50h]
0x140002ccc  call    WPP_RECORDER_SF_ddi
0x140002cd1  mov     rcx, [rbx]
0x140002cd4  cmp     byte ptr [rcx+418h], 0
0x140002cdb  jz      loc_140002D9F
0x140002ce1  bt      qword ptr [rcx+2E0h], 25h ; '%'
0x140002cea  jnb     loc_140002D9F
0x140002cf0  cmp     [rcx+284h], ebp; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_DropStaleEventsWithEventDataSet was effective")
0x140002cf6  jnz     loc_140002D80
0x140002cfc  movzx   edi, word ptr [rcx+288h]
0x140002d03  movzx   eax, word ptr [rcx+28Ch]
0x140002d0a  shl     edi, 10h
0x140002d0d  or      edi, eax
0x140002d0f  jmp     short loc_140002D82
0x140002d11  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002d18  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002d1f  jz      loc_140002E9C
0x140002d25  mov     rax, cs:WPP_GLOBAL_Control
0x140002d2c  cmp     word ptr [rax+48h], 0
0x140002d31  jz      loc_140002E9C
0x140002d37  mov     rax, [rbx+10h]
0x140002d3b  lea     ecx, [r14+1]
0x140002d3f  mov     dword ptr [rsp+88h+var_50], ecx
0x140002d43  mov     r9d, 62h ; 'b'
0x140002d49  mov     rcx, [rbx+50h]
0x140002d4d  mov     r8d, 0Dh
0x140002d53  movzx   edx, byte ptr [rax+8Fh]
0x140002d5a  mov     eax, [rbx+98h]
0x140002d60  mov     dword ptr [rsp+88h+var_58], eax
0x140002d64  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140002d6b  mov     dword ptr [rsp+88h+var_60], edx
0x140002d6f  mov     dl, 5
0x140002d71  mov     [rsp+88h+var_68], rax
0x140002d76  call    WPP_RECORDER_SF_ddd
0x140002d7b  jmp     loc_140002E9C
0x140002d80  xor     edi, edi
0x140002d82  lea     r9, aFeatureDropsta_2; "Feature_DropStaleEventsWithEventDataSet"...
0x140002d89  mov     r8d, ebp
0x140002d8c  mov     edx, edi
0x140002d8e  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x140002d95  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140002d9a  jmp     loc_140002E9C
0x140002d9f  mov     rax, [rbx+10h]
0x140002da3  xor     edi, edi
0x140002da5  mov     [rsp+88h+var_50], rdi
0x140002daa  xor     r9d, r9d
0x140002dad  mov     [rsp+88h+var_58], rbx
0x140002db2  mov     edx, 2
0x140002db7  mov     [rsp+88h+var_60], rax
0x140002dbc  mov     r8d, 101Eh
0x140002dc2  mov     [rsp+88h+var_68], rdi
0x140002dc7  jmp     loc_140002E97
0x140002dcc  movzx   eax, byte ptr [rdi+0Bh]
0x140002dd0  sub     al, 1Ah
0x140002dd2  cmp     al, 2
0x140002dd4  jbe     loc_140002FAA
0x140002dda  mov     rsi, [rbx+90h]
0x140002de1  mov     [rsp+88h+arg_8], 0
0x140002de9  cmp     [rsi+8], ebp
0x140002dec  jb      short loc_140002E2A
0x140002dee  xchg    ax, ax
0x140002df0  mov     rax, [rbx+90h]
0x140002df7  lea     ecx, [rbp-1]
0x140002dfa  mov     rdx, [rdi]
0x140002dfd  imul    r8, rcx, 68h ; 'h'
0x140002e01  mov     rcx, [r8+rax+30h]
0x140002e06  lea     r8, [rsp+88h+arg_8]
0x140002e0e  mov     rax, [rcx+20h]
0x140002e12  mov     rax, [rax+50h]
0x140002e16  call    _guard_dispatch_icall
0x140002e1b  test    al, al
0x140002e1d  jnz     loc_140002EB7
0x140002e23  inc     ebp
0x140002e25  cmp     ebp, [rsi+8]
0x140002e28  jbe     short loc_140002DF0
0x140002e2a  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002e31  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002e38  jz      short loc_140002E6C
0x140002e3a  mov     rax, [rbx+10h]
0x140002e3e  mov     r9d, 68h ; 'h'
0x140002e44  mov     dl, 2
0x140002e46  movzx   ecx, byte ptr [rax+8Fh]
0x140002e4d  mov     rax, [rdi]
0x140002e50  mov     [rsp+88h+var_50], rax
0x140002e55  mov     eax, [rbx+98h]
0x140002e5b  mov     dword ptr [rsp+88h+var_58], eax
0x140002e5f  mov     dword ptr [rsp+88h+var_60], ecx
0x140002e63  mov     rcx, [rbx+50h]
0x140002e67  call    WPP_RECORDER_SF_ddi
0x140002e6c  mov     rax, [rbx+10h]
0x140002e70  xor     edi, edi
0x140002e72  mov     [rsp+88h+var_50], rdi
0x140002e77  xor     r9d, r9d
0x140002e7a  mov     [rsp+88h+var_58], rbx
0x140002e7f  mov     edx, 2
0x140002e84  mov     [rsp+88h+var_60], rax
0x140002e89  mov     r8d, 101Fh
0x140002e8f  mov     [rsp+88h+var_68], rdi
0x140002e94  mov     rcx, [rbx]
0x140002e97  call    Controller_ReportFatalErrorEx
0x140002e9c  mov     r14, [rsp+88h+var_20]
  ... truncated ...
```
