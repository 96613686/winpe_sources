# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessFilterEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)

- ea: `0x18002a2f0`
- end: `0x18002a481`
- name: `?ProcessFilterEvent@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJPEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000bfb8`

## callees

- `0x1800110fc`
- `0x18001140c`
- `0x18002a034`
- `0x18002a2f0`
- `0x18002aec0`
- `0x18002bea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a373`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a3d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a3d8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessFilterEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *a2)
{
  char v4; // di
  bool v5; // dl
  int v6; // ebx
  _BYTE *v7; // rcx
  bool v8; // dl
  bool v9; // zf
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v10; // rax
  int v11; // eax
  bool v12; // cf
  int v14; // [rsp+20h] [rbp-88h]
  int v15; // [rsp+28h] [rbp-80h]

  v4 = 1;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 2) )
    goto LABEL_16;
  v6 = -2147483634;
  v7 = WPP_GLOBAL_Control;
  v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_16:
    v7 = WPP_GLOBAL_Control;
  }
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v7 = WPP_GLOBAL_Control;
  }
  v9 = v6 == 0;
  if ( v6 >= 0 )
  {
    if ( *((_QWORD *)this + 5) )
    {
      v10 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(
              *((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor **)this + 5),
              a2);
      if ( v10 )
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(this, v10);
      v7 = WPP_GLOBAL_Control;
    }
    v9 = v6 == 0;
  }
  v11 = 0;
  if ( v9 )
    v12 = v7[25] < 5u;
  else
    v12 = v7[25] < 2u;
  if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v11) = !v12, !v11) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v7 + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v7 + 5),
      v14,
      v15,
      28,
      (__int64)WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002a2f0  push    rbx
0x18002a2f2  push    rbp
0x18002a2f3  push    rsi
0x18002a2f4  push    rdi
0x18002a2f5  push    r12
0x18002a2f7  push    r13
0x18002a2f9  push    r14
0x18002a2fb  push    r15
0x18002a2fd  sub     rsp, 68h
0x18002a301  mov     r14, rdx
0x18002a304  mov     rsi, rcx
0x18002a307  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a30e  lea     r15, WPP_GLOBAL_Control
0x18002a315  mov     dil, 1
0x18002a318  cmp     rcx, r15
0x18002a31b  jz      short loc_18002A328
0x18002a31d  cmp     byte ptr [rcx+19h], 5
0x18002a321  jb      short loc_18002A328
0x18002a323  mov     dl, dil
0x18002a326  jmp     short loc_18002A32A
0x18002a328  xor     dl, dl
0x18002a32a  lea     r12, WPP_RECORDER_INITIALIZED
0x18002a331  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002a338  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a33f  setnz   r8b
0x18002a343  test    dl, dl
0x18002a345  jnz     short loc_18002A34C
0x18002a347  test    r8b, r8b
0x18002a34a  jz      short loc_18002A36A
0x18002a34c  mov     r9, [rcx+28h]
0x18002a350  mov     rcx, [rcx+10h]
0x18002a354  mov     [rsp+0A8h+var_60], rsi
0x18002a359  mov     [rsp+0A8h+var_70], r13
0x18002a35e  mov     [rsp+0A8h+var_78], 1Ah
0x18002a365  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002a36a  lea     rbp, [rsi+30h]
0x18002a36e  xor     ebx, ebx
0x18002a370  mov     rcx, rbp; lpCriticalSection
0x18002a373  call    cs:__imp_EnterCriticalSection
0x18002a379  cmp     [rsi+8], ebx
0x18002a37c  jnz     short loc_18002A3C9
0x18002a37e  mov     ebx, 8000000Eh
0x18002a383  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a38a  cmp     rcx, r15
0x18002a38d  jz      short loc_18002A39A
0x18002a38f  cmp     byte ptr [rcx+19h], 2
0x18002a393  jb      short loc_18002A39A
0x18002a395  mov     dl, dil
0x18002a398  jmp     short loc_18002A39C
0x18002a39a  xor     dl, dl
0x18002a39c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002a3a3  setnz   r8b
0x18002a3a7  test    dl, dl
0x18002a3a9  jnz     short loc_18002A3B0
0x18002a3ab  test    r8b, r8b
0x18002a3ae  jz      short loc_18002A3D0
0x18002a3b0  mov     r9, [rcx+28h]
0x18002a3b4  mov     rcx, [rcx+10h]
0x18002a3b8  mov     [rsp+0A8h+var_70], r13
0x18002a3bd  mov     [rsp+0A8h+var_78], 1Bh
0x18002a3c4  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002a3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3d0  test    rbp, rbp
0x18002a3d3  jz      short loc_18002A3E5
0x18002a3d5  mov     rcx, rbp; lpCriticalSection
0x18002a3d8  call    cs:__imp_LeaveCriticalSection
0x18002a3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3e5  test    ebx, ebx
0x18002a3e7  js      short loc_18002A415
0x18002a3e9  cmp     qword ptr [rsi+28h], 0
0x18002a3ee  jz      short loc_18002A413
0x18002a3f0  mov     rcx, [rsi+28h]; this
0x18002a3f4  mov     rdx, r14; struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *
0x18002a3f7  call    ?ShouldPairDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)
0x18002a3fc  test    rax, rax
0x18002a3ff  jz      short loc_18002A40C
0x18002a401  mov     rdx, rax; struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *
0x18002a404  mov     rcx, rsi; this
0x18002a407  call    ?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)
0x18002a40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a413  test    ebx, ebx
0x18002a415  jnz     short loc_18002A41F
0x18002a417  xor     eax, eax
0x18002a419  cmp     byte ptr [rcx+19h], 5
0x18002a41d  jmp     short loc_18002A425
0x18002a41f  xor     eax, eax
0x18002a421  cmp     byte ptr [rcx+19h], 2
0x18002a425  setnb   al
0x18002a428  cmp     rcx, r15
0x18002a42b  jz      short loc_18002A431
0x18002a42d  test    eax, eax
0x18002a42f  jnz     short loc_18002A434
0x18002a431  xor     dil, dil
0x18002a434  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002a43b  setnz   r8b
0x18002a43f  test    dil, dil
0x18002a442  jnz     short loc_18002A449
0x18002a444  test    r8b, r8b
0x18002a447  jz      short loc_18002A46E
0x18002a449  mov     r9, [rcx+28h]
0x18002a44d  mov     dl, dil
0x18002a450  mov     rcx, [rcx+10h]
0x18002a454  mov     [rsp+0A8h+var_58], ebx
0x18002a458  mov     [rsp+0A8h+var_60], rsi
0x18002a45d  mov     [rsp+0A8h+var_70], r13
0x18002a462  mov     [rsp+0A8h+var_78], 1Ch
0x18002a469  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002a46e  mov     eax, ebx
0x18002a470  add     rsp, 68h
0x18002a474  pop     r15
0x18002a476  pop     r14
0x18002a478  pop     r13
0x18002a47a  pop     r12
0x18002a47c  pop     rdi
0x18002a47d  pop     rsi
0x18002a47e  pop     rbp
0x18002a47f  pop     rbx
0x18002a480  retn
```
