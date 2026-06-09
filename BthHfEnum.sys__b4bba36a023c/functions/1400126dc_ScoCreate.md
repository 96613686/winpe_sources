# ScoCreate

- ea: `0x1400126dc`
- end: `0x140013141`
- name: `ScoCreate`
- size: `2661`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002b5a0`

## callees

- `0x1400041d0`
- `0x14000affc`
- `0x14000f3d0`
- `0x1400126dc`
- `0x140014b78`
- `0x14001adc0`
- `0x14001ae00`
- `0x14001b2c0`
- `0x14002ea30`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140012d49`
- `ntoskrnl!KeInitializeEvent` at `0x140012d66`
- `ntoskrnl!KeInitializeEvent` at `0x140012d49`
- `ntoskrnl!KeInitializeEvent` at `0x140012d66`

## pseudocode

```c
__int64 __fastcall ScoCreate(unsigned __int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6)
{
  __int64 v6; // r14
  __int64 (__fastcall *v10)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *); // rax
  int v11; // edx
  int v12; // r8d
  int v13; // ebx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // r12
  __int64 v17; // rbx
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r14d
  __int64 v21; // rdi
  char *v22; // rbx
  struct _SCOCONTEXT *v23; // rbx
  struct _SCOCONTEXT *v24; // rax
  struct _SCOCONTEXT *v25; // rax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+38h] [rbp-C8h]
  struct _SCOCONTEXT *v31; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v32[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 *v34; // [rsp+98h] [rbp-68h]
  __int128 v35; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-28h]
  _QWORD v41[12]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v42[24]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v43; // [rsp+1A0h] [rbp+A0h] BYREF

  v38 = a3;
  v6 = a3;
  v34 = 0;
  v37 = 0;
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  v43 = 0;
  v35 = 0;
  v36 = 0;
  memset(v41, 0, sizeof(v41));
  memset(v42, 0, sizeof(v42));
  v31 = 0;
  v10 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616);
  v39 = 0;
  v40 = v10(WdfDriverGlobals, a1, off_1400220B0);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (LOBYTE(v11) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v11) = 0;
  }
  if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v12,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      36,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  v34 = off_140022150;
  *((_QWORD *)&v32[1] + 1) = 0x100000001LL;
  memset(v32, 0, 24);
  LODWORD(v32[0]) = 56;
  v33 = 0;
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _OWORD *, struct _SCOCONTEXT **))(WdfFunctions_01015 + 1624))(
          WdfDriverGlobals,
          a1,
          v32,
          &v31);
  if ( v13 >= 0 )
  {
    *(_QWORD *)v31 = a2;
    *((_QWORD *)v31 + 1) = v6;
    *((_QWORD *)v31 + 2) = a4;
    *((_DWORD *)v31 + 6) = 1179145282;
    *((_DWORD *)v31 + 7) = a5;
    *((_DWORD *)v31 + 8) = a6;
    *((_DWORD *)v31 + 26) = 0;
    memset((char *)&v41[1] + 4, 0, 0x54u);
    LODWORD(v41[0]) = 96;
    *(_QWORD *)((char *)v41 + 4) = 3;
    v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _QWORD *, _QWORD, char *))(WdfFunctions_01015 + 1216))(
            WdfDriverGlobals,
            a1,
            v41,
            0,
            (char *)v31 + 96);
    if ( v13 >= 0 )
    {
      memset(&v42[3], 0, 0x54u);
      v42[0] = 96;
      *(_QWORD *)&v42[1] = 3;
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _DWORD *, _QWORD, char *))(WdfFunctions_01015 + 1216))(
              WdfDriverGlobals,
              a1,
              v42,
              0,
              (char *)v31 + 384);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, char *))(WdfFunctions_01015 + 2520))(
                WdfDriverGlobals,
                v32,
                (char *)v31 + 368);
        if ( v13 >= 0 )
        {
          v37 = 0;
          v36 = 0;
          LODWORD(v36) = 0;
          *((_QWORD *)&v35 + 1) = ScoReopenTimer;
          v34 = 0;
          memset(v32, 0, 24);
          *(_QWORD *)&v35 = 40;
          DWORD2(v36) = 0;
          BYTE4(v36) = 1;
          LODWORD(v32[0]) = 56;
          v33 = a1;
          *((_QWORD *)&v32[1] + 1) = 0x100000002LL;
          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, char *))(WdfFunctions_01015 + 2544))(
                  WdfDriverGlobals,
                  &v35,
                  v32,
                  (char *)v31 + 328);
          if ( v13 >= 0 )
          {
            v37 = 0;
            v36 = 0;
            LODWORD(v36) = 0;
            *((_QWORD *)&v35 + 1) = ScoIdleTimer;
            v34 = 0;
            memset(v32, 0, 24);
            *(_QWORD *)&v35 = 40;
            DWORD2(v36) = 0;
            BYTE4(v36) = 1;
            LODWORD(v32[0]) = 56;
            v33 = a1;
            *((_QWORD *)&v32[1] + 1) = 0x100000002LL;
            v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, char *))(WdfFunctions_01015
                                                                                               + 2544))(
                    WdfDriverGlobals,
                    &v35,
                    v32,
                    (char *)v31 + 360);
            if ( v13 >= 0 )
            {
              v37 = 0;
              v36 = 0;
              LODWORD(v36) = 0;
              *((_QWORD *)&v35 + 1) = ScoAvdtpUnsuspendDelayTimer;
              v34 = 0;
              memset(v32, 0, 24);
              *(_QWORD *)&v35 = 40;
              DWORD2(v36) = 0;
              BYTE4(v36) = 1;
              LODWORD(v32[0]) = 56;
              v33 = a1;
              *((_QWORD *)&v32[1] + 1) = 0x100000002LL;
              v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, char *))(WdfFunctions_01015
                                                                                                 + 2544))(
                      WdfDriverGlobals,
                      &v35,
                      v32,
                      (char *)v31 + 296);
              if ( v13 >= 0 )
              {
                v37 = 0;
                v36 = 0;
                LODWORD(v36) = 0;
                *((_QWORD *)&v35 + 1) = ScoTransitionWatchdogTimer;
                v34 = 0;
                memset(v32, 0, 24);
                *(_QWORD *)&v35 = 40;
                DWORD2(v36) = 0;
                BYTE4(v36) = 1;
                LODWORD(v32[0]) = 56;
                v33 = a1;
                *((_QWORD *)&v32[1] + 1) = 0x100000002LL;
                v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, char *))(WdfFunctions_01015 + 2544))(
                        WdfDriverGlobals,
                        &v35,
                        v32,
                        (char *)v31 + 480);
                if ( v13 >= 0 )
                {
                  v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v6 + 32))(521, 1179145282);
                  if ( v14 )
                  {
                    v15 = WdfIoTargetCreateAndFormatRequestForBrb(0, a2, v6, v14, &v39);
                    v16 = v39;
                    v13 = v15;
                    if ( v15 >= 0 )
                    {
                      v17 = v14;
                      v43 = 0x200000010uLL;
                      v14 = 0;
                      if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2024))(
                             WdfDriverGlobals,
                             v39,
                             a2,
                             &v43) )
                      {
                        *((_DWORD *)v31 + 16) = *(_DWORD *)(v17 + 112);
                        *((_WORD *)v31 + 34) = *(_WORD *)(v17 + 124);
                        *((_WORD *)v31 + 35) = *(_WORD *)(v17 + 126);
                        ScoGetControllerSupportedCodecs(v31);
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                          || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
                        {
                          LOBYTE(v18) = 0;
                        }
                        if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_LHH(
                            WPP_GLOBAL_Control->AttachedDevice,
                            v18,
                            v19,
                            WPP_GLOBAL_Control->DeviceExtension,
                            v27,
                            v28,
                            v29,
                            v30,
                            *(_DWORD *)(v17 + 112),
                            *(_WORD *)(v17 + 124),
                            *(_WORD *)(v17 + 126));
                        }
                        KeInitializeEvent((PRKEVENT)((char *)v31 + 304), NotificationEvent, 0);
                        KeInitializeEvent((PRKEVENT)v31 + 14, NotificationEvent, 1u);
                        v20 = 0;
                        while ( 1 )
                        {
                          v21 = 80LL * (int)v20;
                          *(_DWORD *)((char *)v31 + v21 + 136) = v20;
                          v34 = 0;
                          memset(v32, 0, 24);
                          LODWORD(v32[0]) = 56;
                          *((_QWORD *)&v32[1] + 1) = 0x100000001LL;
                          v33 = a1;
                          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, char *))(WdfFunctions_01015
                                                                                                 + 2520))(
                                  WdfDriverGlobals,
                                  v32,
                                  (char *)v31 + v21 + 176);
                          if ( v13 < 0 )
                            break;
                          v34 = 0;
                          *((_QWORD *)&v32[1] + 1) = 0x100000001LL;
                          memset(v32, 0, 24);
                          LODWORD(v32[0]) = 56;
                          v33 = a1;
                          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, char *))(WdfFunctions_01015
                                                                                                 + 104))(
                                  WdfDriverGlobals,
                                  v32,
                                  (char *)v31 + v21 + 184);
                          if ( v13 < 0 )
                            break;
                          memset(v41, 0, sizeof(v41));
                          v41[7] = ScoDataQueue_EvtIoStop;
                          LODWORD(v41[0]) = 96;
                          *(_QWORD *)((char *)v41 + 4) = 3;
                          *((_QWORD *)&v32[1] + 1) = 0x100000001LL;
                          v34 = off_1400221A0;
                          memset(v32, 0, 24);
                          LODWORD(v32[0]) = 56;
                          v33 = 0;
                          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, _QWORD *, _OWORD *, char *))(WdfFunctions_01015 + 1216))(
                                  WdfDriverGlobals,
                                  a1,
                                  v41,
                                  v32,
                                  (char *)v31 + v21 + 160);
                          if ( v13 < 0 )
                            break;
                          v22 = (char *)v31 + v21 + 136;
                          *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                                       WdfDriverGlobals,
                                       *((_QWORD *)v31 + 10 * (int)v20 + 20),
                                       off_1400221A0) = v22;
                          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, void (__fastcall *)(struct WDFQUEUE__ *, void *), _QWORD))(WdfFunctions_01015 + 1328))(
                                  WdfDriverGlobals,
                                  *((_QWORD *)v31 + 10 * (int)v20 + 20),
                                  ScoAudioDataQueueReady,
                                  0);
                          if ( v13 < 0 )
                            break;
                          v37 = 0;
                          v36 = 0;
                          LODWORD(v36) = 0;
                          *((_QWORD *)&v35 + 1) = ScoDataCompletionTimer;
                          v34 = off_1400221A0;
                          DWORD2(v36) = 0;
                          *(_QWORD *)&v35 = 40;
                          BYTE4(v36) = 1;
                          memset((char *)v32 + 4, 0, 20);
                          LODWORD(v32[0]) = 56;
                          v33 = a1;
                          *((_QWORD *)&v32[1] + 1) = 0x100000002LL;
                          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, char *))(WdfFunctions_01015 + 2544))(
                                  WdfDriverGlobals,
                                  &v35,
                                  v32,
                                  (char *)v31 + v21 + 208);
                          if ( v13 < 0 )
                            break;
                          v13 = AudioQueue_MakeAndInitialize(*((_QWORD *)v31 + 10 * (int)v20 + 20), v20);
                          if ( v13 < 0 )
                            break;
                          v23 = v31;
                          ++v20;
                          *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                                       WdfDriverGlobals,
                                       *(_QWORD *)((char *)v31 + v21 + 208),
                                       off_1400221A0) = (char *)v23 + v21 + 136;
                          if ( v20 >= 2 )
                          {
                            v24 = v31;
                            v13 = 0;
                            *((_DWORD *)v31 + 9) = 0;
                            *((_BYTE *)v24 + 40) = 0;
                            v25 = v31;
                            *((_DWORD *)v31 + 12) = 0;
                            *((_BYTE *)v25 + 52) = 0;
                            if ( *(_QWORD *)(v40 + 288) == *(_QWORD *)&GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data1
                              && *(_QWORD *)(v40 + 296) == *(_QWORD *)GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data4 )
                            {
                              *((_BYTE *)v31 + 58) = 1;
                              *((_BYTE *)v31 + 59) = 16;
                            }
                            else
                            {
                              *((_BYTE *)v31 + 58) = 0;
                              *((_BYTE *)v31 + 59) = 0;
                            }
                            break;
                          }
                        }
                        v6 = v38;
                      }
                      else
                      {
                        v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(
                                WdfDriverGlobals,
                                v16);
                      }
                    }
                    if ( v16 )
                      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(
                        WdfDriverGlobals,
                        v16);
                    if ( v14 )
                      (*(void (__fastcall **)(__int64))(v6 + 40))(v14);
                  }
                  else
                  {
                    return (unsigned int)-1073741670;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400126dc  mov     [rsp-8+arg_18], rbx
0x1400126e1  push    rbp
0x1400126e2  push    rsi
0x1400126e3  push    rdi
0x1400126e4  push    r12
0x1400126e6  push    r13
0x1400126e8  push    r14
0x1400126ea  push    r15
0x1400126ec  lea     rbp, [rsp-0C0h]
0x1400126f4  sub     rsp, 1C0h
0x1400126fb  mov     rax, cs:__security_cookie
0x140012702  xor     rax, rsp
0x140012705  mov     [rbp+0F0h+var_40], rax
0x14001270c  xorps   xmm0, xmm0
0x14001270f  mov     [rbp+0F0h+var_128], r8
0x140012713  xor     eax, eax
0x140012715  xorps   xmm1, xmm1
0x140012718  mov     r14, r8
0x14001271b  mov     [rbp+0F0h+var_158], rax
0x14001271f  mov     rdi, rdx
0x140012722  mov     [rbp+0F0h+var_130], rax
0x140012726  mov     r15, rcx
0x140012729  xor     edx, edx; Val
0x14001272b  lea     ebx, [rax+60h]
0x14001272e  mov     rsi, r9
0x140012731  mov     r8d, ebx; Size
0x140012734  lea     rcx, [rbp+0F0h+var_110]; void *
0x140012738  movups  [rsp+1F0h+var_188], xmm0
0x14001273d  movups  [rsp+1F0h+var_178], xmm0
0x140012742  movups  [rbp+0F0h+var_168], xmm0
0x140012746  movups  [rbp+0F0h+var_50], xmm0
0x14001274d  movups  [rbp+0F0h+var_150], xmm1
0x140012751  movups  [rbp+0F0h+var_140], xmm1
0x140012755  call    memset
0x14001275a  mov     r8d, ebx; Size
0x14001275d  lea     rcx, [rbp+0F0h+var_B0]; void *
0x140012761  xor     edx, edx; Val
0x140012763  call    memset
0x140012768  mov     rax, cs:WdfFunctions_01015
0x14001276f  xor     r13d, r13d
0x140012772  mov     r8, cs:off_1400220B0
0x140012779  mov     rdx, r15
0x14001277c  mov     rcx, cs:WdfDriverGlobals
0x140012783  mov     [rsp+1F0h+var_190], r13
0x140012788  mov     rax, [rax+650h]
0x14001278f  mov     [rbp+0F0h+var_120], r13
0x140012793  call    _guard_dispatch_icall
0x140012798  mov     [rbp+0F0h+var_118], rax
0x14001279c  mov     r10, cs:WPP_GLOBAL_Control
0x1400127a3  lea     rax, WPP_GLOBAL_Control
0x1400127aa  lea     r12d, [rbx-5Fh]
0x1400127ae  cmp     r10, rax
0x1400127b1  jz      short loc_1400127C6
0x1400127b3  mov     ecx, [r10+2Ch]
0x1400127b7  test    cl, 10h
0x1400127ba  jz      short loc_1400127C6
0x1400127bc  cmp     byte ptr [r10+29h], 4
0x1400127c1  mov     dl, r12b
0x1400127c4  jnb     short loc_1400127C9
0x1400127c6  mov     dl, r13b
0x1400127c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400127d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400127d7  setnz   r8b
0x1400127db  test    dl, dl
0x1400127dd  jnz     short loc_1400127E4
0x1400127df  test    r8b, r8b
0x1400127e2  jz      short loc_140012811
0x1400127e4  mov     r9, [r10+40h]
0x1400127e8  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x1400127ef  mov     rcx, [r10+18h]
0x1400127f3  mov     [rsp+1F0h+var_1B8], rax
0x1400127f8  mov     [rsp+1F0h+var_1C0], 24h ; '$'
0x1400127ff  mov     [rsp+1F0h+var_1C8], 5
0x140012807  mov     byte ptr [rsp+1F0h+var_1D0], 4
0x14001280c  call    WPP_RECORDER_AND_TRACE_SF_
0x140012811  mov     rax, cs:off_140022150
0x140012818  lea     r9, [rsp+1F0h+var_190]
0x14001281d  mov     rcx, cs:WdfDriverGlobals
0x140012824  lea     r8, [rsp+1F0h+var_188]
0x140012829  xorps   xmm0, xmm0
0x14001282c  mov     [rbp+0F0h+var_158], rax
0x140012830  mov     rax, cs:WdfFunctions_01015
0x140012837  mov     rdx, r15
0x14001283a  movups  [rsp+1F0h+var_178], xmm0
0x14001283f  mov     dword ptr [rbp+0F0h+var_178+8], r12d
0x140012843  movups  [rsp+1F0h+var_188], xmm0
0x140012848  mov     dword ptr [rsp+1F0h+var_188], 38h ; '8'
0x140012850  movups  [rbp+0F0h+var_168], xmm0
0x140012854  mov     dword ptr [rbp+0F0h+var_178+0Ch], r12d
0x140012858  mov     rax, [rax+658h]
0x14001285f  call    _guard_dispatch_icall
0x140012864  mov     ebx, eax
0x140012866  test    eax, eax
0x140012868  js      loc_140013114
0x14001286e  mov     rax, [rsp+1F0h+var_190]
0x140012873  xor     edx, edx; Val
0x140012875  mov     ecx, [rbp+0F0h+arg_20]
0x14001287b  mov     [rax], rdi
0x14001287e  mov     rax, [rsp+1F0h+var_190]
0x140012883  mov     [rax+8], r14
0x140012887  mov     rax, [rsp+1F0h+var_190]
0x14001288c  mov     [rax+10h], rsi
0x140012890  mov     esi, 54h ; 'T'
0x140012895  mov     rax, [rsp+1F0h+var_190]
0x14001289a  mov     r8d, esi; Size
0x14001289d  mov     dword ptr [rax+18h], 46485442h
0x1400128a4  mov     rax, [rsp+1F0h+var_190]
0x1400128a9  mov     [rax+1Ch], ecx
0x1400128ac  mov     rax, [rsp+1F0h+var_190]
0x1400128b1  mov     ecx, [rbp+0F0h+arg_28]
0x1400128b7  mov     [rax+20h], ecx
0x1400128ba  lea     rcx, [rbp+0F0h+var_104]; void *
0x1400128be  mov     rax, [rsp+1F0h+var_190]
0x1400128c3  mov     [rax+68h], r13d
0x1400128c7  call    memset
0x1400128cc  mov     rcx, [rsp+1F0h+var_190]
0x1400128d1  lea     r8, [rbp+0F0h+var_110]
0x1400128d5  mov     rax, cs:WdfFunctions_01015
0x1400128dc  add     rcx, 60h ; '`'
0x1400128e0  mov     [rsp+1F0h+var_1D0], rcx
0x1400128e5  xor     r9d, r9d
0x1400128e8  mov     rcx, cs:WdfDriverGlobals
0x1400128ef  mov     rdx, r15
0x1400128f2  mov     [rbp+0F0h+var_110], 60h ; '`'
0x1400128f9  mov     [rbp+0F0h+var_10C], 3
0x140012901  mov     rax, [rax+4C0h]
0x140012908  call    _guard_dispatch_icall
0x14001290d  mov     ebx, eax
0x14001290f  test    eax, eax
0x140012911  js      loc_140013114
0x140012917  mov     r8d, esi; Size
0x14001291a  lea     rcx, [rbp+0F0h+var_A4]; void *
0x14001291e  xor     edx, edx; Val
0x140012920  call    memset
0x140012925  mov     rcx, [rsp+1F0h+var_190]
0x14001292a  lea     r8, [rbp+0F0h+var_B0]
0x14001292e  mov     rax, cs:WdfFunctions_01015
0x140012935  add     rcx, 180h
0x14001293c  mov     [rsp+1F0h+var_1D0], rcx
0x140012941  xor     r9d, r9d
0x140012944  mov     rcx, cs:WdfDriverGlobals
0x14001294b  mov     rdx, r15
0x14001294e  mov     [rbp+0F0h+var_B0], 60h ; '`'
0x140012955  mov     [rbp+0F0h+var_AC], 3
0x14001295d  mov     rax, [rax+4C0h]
0x140012964  call    _guard_dispatch_icall
0x140012969  mov     ebx, eax
0x14001296b  test    eax, eax
0x14001296d  js      loc_140013114
0x140012973  mov     rax, cs:WdfFunctions_01015
0x14001297a  lea     rdx, [rsp+1F0h+var_188]
0x14001297f  mov     r8, [rsp+1F0h+var_190]
0x140012984  mov     rcx, cs:WdfDriverGlobals
0x14001298b  add     r8, 170h
0x140012992  mov     rax, [rax+9D8h]
0x140012999  call    _guard_dispatch_icall
0x14001299e  mov     ebx, eax
0x1400129a0  test    eax, eax
0x1400129a2  js      loc_140013114
0x1400129a8  mov     r9, [rsp+1F0h+var_190]
0x1400129ad  lea     r8, [rsp+1F0h+var_188]
0x1400129b2  mov     rcx, cs:WdfDriverGlobals
0x1400129b9  lea     rdx, [rbp+0F0h+var_150]
0x1400129bd  xor     eax, eax
0x1400129bf  xorps   xmm0, xmm0
0x1400129c2  mov     [rbp+0F0h+var_130], rax
0x1400129c6  add     r9, 148h
0x1400129cd  movups  [rbp+0F0h+var_140], xmm0
0x1400129d1  lea     rax, ?ScoReopenTimer@@YAXPEAUWDFTIMER__@@@Z; ScoReopenTimer(WDFTIMER__ *)
0x1400129d8  mov     dword ptr [rbp+0F0h+var_140], r13d
0x1400129dc  movups  [rbp+0F0h+var_150], xmm0
0x1400129e0  mov     qword ptr [rbp+0F0h+var_150+8], rax
0x1400129e4  xor     eax, eax
0x1400129e6  movups  [rsp+1F0h+var_178], xmm0
0x1400129eb  mov     [rbp+0F0h+var_158], rax
0x1400129ef  movups  [rsp+1F0h+var_188], xmm0
0x1400129f4  lea     esi, [rax+38h]
0x1400129f7  mov     dword ptr [rbp+0F0h+var_150], 28h ; '('
0x1400129fe  mov     rax, cs:WdfFunctions_01015
0x140012a05  movups  [rbp+0F0h+var_168], xmm0
0x140012a09  mov     dword ptr [rbp+0F0h+var_140+8], r13d
0x140012a0d  mov     byte ptr [rbp+0F0h+var_140+4], r12b
0x140012a11  mov     dword ptr [rsp+1F0h+var_188], esi
0x140012a15  mov     dword ptr [rbp+0F0h+var_178+0Ch], r12d
0x140012a19  mov     qword ptr [rbp+0F0h+var_168], r15
0x140012a1d  mov     dword ptr [rbp+0F0h+var_178+8], 2
0x140012a24  mov     rax, [rax+9F0h]
0x140012a2b  call    _guard_dispatch_icall
0x140012a30  mov     ebx, eax
0x140012a32  test    eax, eax
0x140012a34  js      loc_140013114
0x140012a3a  mov     r9, [rsp+1F0h+var_190]
0x140012a3f  lea     r8, [rsp+1F0h+var_188]
0x140012a44  mov     rcx, cs:WdfDriverGlobals
0x140012a4b  lea     rdx, [rbp+0F0h+var_150]
0x140012a4f  xor     eax, eax
0x140012a51  xorps   xmm0, xmm0
0x140012a54  mov     [rbp+0F0h+var_130], rax
0x140012a58  add     r9, 168h
0x140012a5f  movups  [rbp+0F0h+var_140], xmm0
0x140012a63  lea     rax, ?ScoIdleTimer@@YAXPEAUWDFTIMER__@@@Z; ScoIdleTimer(WDFTIMER__ *)
0x140012a6a  mov     dword ptr [rbp+0F0h+var_140], r13d
0x140012a6e  movups  [rbp+0F0h+var_150], xmm0
0x140012a72  mov     qword ptr [rbp+0F0h+var_150+8], rax
0x140012a76  xor     eax, eax
0x140012a78  movups  [rsp+1F0h+var_178], xmm0
0x140012a7d  mov     [rbp+0F0h+var_158], rax
0x140012a81  mov     rax, cs:WdfFunctions_01015
0x140012a88  movups  [rsp+1F0h+var_188], xmm0
0x140012a8d  mov     dword ptr [rbp+0F0h+var_150], 28h ; '('
0x140012a94  movups  [rbp+0F0h+var_168], xmm0
0x140012a98  mov     dword ptr [rbp+0F0h+var_140+8], r13d
0x140012a9c  mov     byte ptr [rbp+0F0h+var_140+4], r12b
0x140012aa0  mov     dword ptr [rsp+1F0h+var_188], esi
0x140012aa4  mov     dword ptr [rbp+0F0h+var_178+0Ch], r12d
0x140012aa8  mov     qword ptr [rbp+0F0h+var_168], r15
0x140012aac  mov     dword ptr [rbp+0F0h+var_178+8], 2
0x140012ab3  mov     rax, [rax+9F0h]
0x140012aba  call    _guard_dispatch_icall
0x140012abf  mov     ebx, eax
0x140012ac1  test    eax, eax
0x140012ac3  js      loc_140013114
0x140012ac9  mov     r9, [rsp+1F0h+var_190]
0x140012ace  lea     r8, [rsp+1F0h+var_188]
0x140012ad3  mov     rcx, cs:WdfDriverGlobals
0x140012ada  lea     rdx, [rbp+0F0h+var_150]
0x140012ade  xor     eax, eax
0x140012ae0  xorps   xmm0, xmm0
0x140012ae3  mov     [rbp+0F0h+var_130], rax
0x140012ae7  add     r9, 128h
0x140012aee  movups  [rbp+0F0h+var_140], xmm0
0x140012af2  lea     rax, ?ScoAvdtpUnsuspendDelayTimer@@YAXPEAUWDFTIMER__@@@Z; ScoAvdtpUnsuspendDelayTimer(WDFTIMER__ *)
0x140012af9  mov     dword ptr [rbp+0F0h+var_140], r13d
0x140012afd  movups  [rbp+0F0h+var_150], xmm0
0x140012b01  mov     qword ptr [rbp+0F0h+var_150+8], rax
0x140012b05  xor     eax, eax
0x140012b07  movups  [rsp+1F0h+var_178], xmm0
0x140012b0c  mov     [rbp+0F0h+var_158], rax
0x140012b10  mov     rax, cs:WdfFunctions_01015
0x140012b17  movups  [rsp+1F0h+var_188], xmm0
0x140012b1c  mov     dword ptr [rbp+0F0h+var_150], 28h ; '('
0x140012b23  movups  [rbp+0F0h+var_168], xmm0
0x140012b27  mov     dword ptr [rbp+0F0h+var_140+8], r13d
0x140012b2b  mov     byte ptr [rbp+0F0h+var_140+4], r12b
0x140012b2f  mov     dword ptr [rsp+1F0h+var_188], esi
0x140012b33  mov     dword ptr [rbp+0F0h+var_178+0Ch], r12d
0x140012b37  mov     qword ptr [rbp+0F0h+var_168], r15
0x140012b3b  mov     dword ptr [rbp+0F0h+var_178+8], 2
0x140012b42  mov     rax, [rax+9F0h]
0x140012b49  call    _guard_dispatch_icall
0x140012b4e  mov     ebx, eax
0x140012b50  test    eax, eax
0x140012b52  js      loc_140013114
0x140012b58  mov     r9, [rsp+1F0h+var_190]
0x140012b5d  lea     r8, [rsp+1F0h+var_188]
0x140012b62  mov     rcx, cs:WdfDriverGlobals
0x140012b69  lea     rdx, [rbp+0F0h+var_150]
0x140012b6d  xor     eax, eax
0x140012b6f  xorps   xmm0, xmm0
0x140012b72  mov     [rbp+0F0h+var_130], rax
0x140012b76  add     r9, 1E0h
0x140012b7d  movups  [rbp+0F0h+var_140], xmm0
0x140012b81  lea     rax, ?ScoTransitionWatchdogTimer@@YAXPEAUWDFTIMER__@@@Z; ScoTransitionWatchdogTimer(WDFTIMER__ *)
0x140012b88  mov     dword ptr [rbp+0F0h+var_140], r13d
0x140012b8c  movups  [rbp+0F0h+var_150], xmm0
0x140012b90  mov     qword ptr [rbp+0F0h+var_150+8], rax
0x140012b94  xor     eax, eax
0x140012b96  movups  [rsp+1F0h+var_178], xmm0
0x140012b9b  mov     [rbp+0F0h+var_158], rax
0x140012b9f  mov     rax, cs:WdfFunctions_01015
0x140012ba6  movups  [rsp+1F0h+var_188], xmm0
0x140012bab  mov     dword ptr [rbp+0F0h+var_150], 28h ; '('
0x140012bb2  movups  [rbp+0F0h+var_168], xmm0
0x140012bb6  mov     dword ptr [rbp+0F0h+var_140+8], r13d
0x140012bba  mov     byte ptr [rbp+0F0h+var_140+4], r12b
0x140012bbe  mov     dword ptr [rsp+1F0h+var_188], esi
0x140012bc2  mov     dword ptr [rbp+0F0h+var_178+0Ch], r12d
0x140012bc6  mov     qword ptr [rbp+0F0h+var_168], r15
0x140012bca  mov     dword ptr [rbp+0F0h+var_178+8], 2
0x140012bd1  mov     rax, [rax+9F0h]
0x140012bd8  call    _guard_dispatch_icall
0x140012bdd  mov     ebx, eax
0x140012bdf  test    eax, eax
0x140012be1  js      loc_140013114
0x140012be7  mov     rax, [r14+20h]
0x140012beb  mov     edx, 46485442h
0x140012bf0  mov     ecx, 209h
0x140012bf5  call    _guard_dispatch_icall
0x140012bfa  mov     rsi, rax
0x140012bfd  test    rax, rax
0x140012c00  jnz     short loc_140012C0C
0x140012c02  mov     ebx, 0C000009Ah
0x140012c07  jmp     loc_140013114
0x140012c0c  lea     rax, [rbp+0F0h+var_120]
0x140012c10  mov     r9, rsi
0x140012c13  mov     r8, r14
0x140012c16  mov     [rsp+1F0h+var_1D0], rax
0x140012c1b  mov     rdx, rdi
0x140012c1e  xor     ecx, ecx
0x140012c20  call    WdfIoTargetCreateAndFormatRequestForBrb
  ... truncated ...
```
