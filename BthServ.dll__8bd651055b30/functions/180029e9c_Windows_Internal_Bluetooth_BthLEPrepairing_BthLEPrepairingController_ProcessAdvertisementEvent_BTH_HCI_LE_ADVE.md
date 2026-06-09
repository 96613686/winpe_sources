# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessAdvertisementEvent(_BTH_HCI_LE_ADVERTISEMENT_DATA const *)

- ea: `0x180029e9c`
- end: `0x18002a02d`
- name: `?ProcessAdvertisementEvent@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJPEBU_BTH_HCI_LE_ADVERTISEMENT_DATA@@@Z`
- size: `401`
- prototype: `int(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, const struct _BTH_HCI_LE_ADVERTISEMENT_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000be8c`

## callees

- `0x1800110fc`
- `0x18001140c`
- `0x180029e9c`
- `0x18002a034`
- `0x18002aec0`
- `0x18002bde8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f84`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessAdvertisementEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        const struct _BTH_HCI_LE_ADVERTISEMENT_DATA *a2)
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
      v10 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromAdvertisement(
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
      31,
      (__int64)WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180029e9c  push    rbx
0x180029e9e  push    rbp
0x180029e9f  push    rsi
0x180029ea0  push    rdi
0x180029ea1  push    r12
0x180029ea3  push    r13
0x180029ea5  push    r14
0x180029ea7  push    r15
0x180029ea9  sub     rsp, 68h
0x180029ead  mov     r14, rdx
0x180029eb0  mov     rsi, rcx
0x180029eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029eba  lea     r15, WPP_GLOBAL_Control
0x180029ec1  mov     dil, 1
0x180029ec4  cmp     rcx, r15
0x180029ec7  jz      short loc_180029ED4
0x180029ec9  cmp     byte ptr [rcx+19h], 5
0x180029ecd  jb      short loc_180029ED4
0x180029ecf  mov     dl, dil
0x180029ed2  jmp     short loc_180029ED6
0x180029ed4  xor     dl, dl
0x180029ed6  lea     r12, WPP_RECORDER_INITIALIZED
0x180029edd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180029ee4  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x180029eeb  setnz   r8b
0x180029eef  test    dl, dl
0x180029ef1  jnz     short loc_180029EF8
0x180029ef3  test    r8b, r8b
0x180029ef6  jz      short loc_180029F16
0x180029ef8  mov     r9, [rcx+28h]
0x180029efc  mov     rcx, [rcx+10h]
0x180029f00  mov     [rsp+0A8h+var_60], rsi
0x180029f05  mov     [rsp+0A8h+var_70], r13
0x180029f0a  mov     [rsp+0A8h+var_78], 1Dh
0x180029f11  call    WPP_RECORDER_AND_TRACE_SF_si
0x180029f16  lea     rbp, [rsi+30h]
0x180029f1a  xor     ebx, ebx
0x180029f1c  mov     rcx, rbp; lpCriticalSection
0x180029f1f  call    cs:__imp_EnterCriticalSection
0x180029f25  cmp     [rsi+8], ebx
0x180029f28  jnz     short loc_180029F75
0x180029f2a  mov     ebx, 8000000Eh
0x180029f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f36  cmp     rcx, r15
0x180029f39  jz      short loc_180029F46
0x180029f3b  cmp     byte ptr [rcx+19h], 2
0x180029f3f  jb      short loc_180029F46
0x180029f41  mov     dl, dil
0x180029f44  jmp     short loc_180029F48
0x180029f46  xor     dl, dl
0x180029f48  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180029f4f  setnz   r8b
0x180029f53  test    dl, dl
0x180029f55  jnz     short loc_180029F5C
0x180029f57  test    r8b, r8b
0x180029f5a  jz      short loc_180029F7C
0x180029f5c  mov     r9, [rcx+28h]
0x180029f60  mov     rcx, [rcx+10h]
0x180029f64  mov     [rsp+0A8h+var_70], r13
0x180029f69  mov     [rsp+0A8h+var_78], 1Eh
0x180029f70  call    WPP_RECORDER_AND_TRACE_SF_s
0x180029f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f7c  test    rbp, rbp
0x180029f7f  jz      short loc_180029F91
0x180029f81  mov     rcx, rbp; lpCriticalSection
0x180029f84  call    cs:__imp_LeaveCriticalSection
0x180029f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f91  test    ebx, ebx
0x180029f93  js      short loc_180029FC1
0x180029f95  cmp     qword ptr [rsi+28h], 0
0x180029f9a  jz      short loc_180029FBF
0x180029f9c  mov     rcx, [rsi+28h]; this
0x180029fa0  mov     rdx, r14; struct _BTH_HCI_LE_ADVERTISEMENT_DATA *
0x180029fa3  call    ?ShouldPairDeviceFromAdvertisement@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_HCI_LE_ADVERTISEMENT_DATA@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromAdvertisement(_BTH_HCI_LE_ADVERTISEMENT_DATA const *)
0x180029fa8  test    rax, rax
0x180029fab  jz      short loc_180029FB8
0x180029fad  mov     rdx, rax; struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *
0x180029fb0  mov     rcx, rsi; this
0x180029fb3  call    ?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)
0x180029fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fbf  test    ebx, ebx
0x180029fc1  jnz     short loc_180029FCB
0x180029fc3  xor     eax, eax
0x180029fc5  cmp     byte ptr [rcx+19h], 5
0x180029fc9  jmp     short loc_180029FD1
0x180029fcb  xor     eax, eax
0x180029fcd  cmp     byte ptr [rcx+19h], 2
0x180029fd1  setnb   al
0x180029fd4  cmp     rcx, r15
0x180029fd7  jz      short loc_180029FDD
0x180029fd9  test    eax, eax
0x180029fdb  jnz     short loc_180029FE0
0x180029fdd  xor     dil, dil
0x180029fe0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180029fe7  setnz   r8b
0x180029feb  test    dil, dil
0x180029fee  jnz     short loc_180029FF5
0x180029ff0  test    r8b, r8b
0x180029ff3  jz      short loc_18002A01A
0x180029ff5  mov     r9, [rcx+28h]
0x180029ff9  mov     dl, dil
0x180029ffc  mov     rcx, [rcx+10h]
0x18002a000  mov     [rsp+0A8h+var_58], ebx
0x18002a004  mov     [rsp+0A8h+var_60], rsi
0x18002a009  mov     [rsp+0A8h+var_70], r13
0x18002a00e  mov     [rsp+0A8h+var_78], 1Fh
0x18002a015  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002a01a  mov     eax, ebx
0x18002a01c  add     rsp, 68h
0x18002a020  pop     r15
0x18002a022  pop     r14
0x18002a024  pop     r13
0x18002a026  pop     r12
0x18002a028  pop     rdi
0x18002a029  pop     rsi
0x18002a02a  pop     rbp
0x18002a02b  pop     rbx
0x18002a02c  retn
```
