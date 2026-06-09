# UsbDevice_QueueTunnelStateDSM

- ea: `0x14003c85c`
- end: `0x14003ca75`
- name: `UsbDevice_QueueTunnelStateDSM`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14004f320`
- `0x14004f7c0`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14003c85c`
- `0x1400599b0`

## string_xrefs

- `0x14003c8cd`: `Attempting to queue Tunnel State DSM on an unsupported machine`
- `0x14003c8a0`: `Attempting to queue Tunnel State DSM without an update to the tunnel state`

## pseudocode

```c
char __fastcall UsbDevice_QueueTunnelStateDSM(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  _QWORD *v5; // rax
  int v6; // edx
  _QWORD *v7; // rax
  __int128 v9; // [rsp+30h] [rbp-50h] BYREF
  __int64 v10; // [rsp+40h] [rbp-40h]
  __int128 v11; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+58h] [rbp-28h]
  __int128 v13; // [rsp+68h] [rbp-18h]
  __int64 *v14; // [rsp+78h] [rbp-8h]
  __int64 v15; // [rsp+90h] [rbp+10h] BYREF

  v15 = 0;
  v3 = *(_DWORD *)(a2 + 24) >> 7;
  LOBYTE(v3) = v3 & 1;
  LODWORD(v10) = 0;
  LODWORD(v14) = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  Debug_FreAssertMsg(
    "Attempting to queue Tunnel State DSM without an update to the tunnel state",
    v3,
    "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\usbdevice.c",
    1737);
  Debug_FreAssertMsg(
    "Attempting to queue Tunnel State DSM on an unsupported machine",
    (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 744LL) & 0x10000000) != 0,
    "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\usbdevice.c",
    1738);
  v10 = 0;
  v9 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x43 )
      LODWORD(v9) = -1;
    else
      LODWORD(v9) = *(_DWORD *)(WdfStructures + 536);
  }
  else
  {
    LODWORD(v9) = 24;
  }
  LOBYTE(v10) = 1;
  *((_QWORD *)&v9 + 1) = UsbDevice_RunUpdateTunnelStateDsm;
  v14 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v11) = -1;
    else
      LODWORD(v11) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v11) = 56;
  }
  v14 = off_14006C0E0;
  v5 = *(_QWORD **)(a1 + 8);
  *((_QWORD *)&v12 + 1) = 0x100000001LL;
  *(_QWORD *)&v13 = *v5;
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64 *))(WdfFunctions_01033 + 3032))(
         WdfDriverGlobals,
         &v9,
         &v11,
         &v15) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v6,
        12,
        33,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_DWORD *)(a1 + 44));
    }
    *(_BYTE *)(a2 + 67) = 4;
    return 0;
  }
  else
  {
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     v15,
                     off_14006C0E0);
    v7[2] = *(_QWORD *)(a1 + 432);
    *v7 = a1;
    v7[1] = a2;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 3040))(WdfDriverGlobals, v15);
    return 1;
  }
}

```

## disassembly

```asm
0x14003c85c  mov     [rsp-8+arg_8], rbx
0x14003c861  mov     [rsp-8+arg_10], rdi
0x14003c866  push    rbp
0x14003c867  mov     rbp, rsp
0x14003c86a  sub     rsp, 80h
0x14003c871  xorps   xmm0, xmm0
0x14003c874  mov     [rbp+arg_0], 0
0x14003c87c  mov     rdi, rdx
0x14003c87f  lea     r8, aOnecoreDrivers_17; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003c886  mov     edx, [rdx+18h]
0x14003c889  xor     eax, eax
0x14003c88b  shr     edx, 7
0x14003c88e  mov     rbx, rcx
0x14003c891  and     dl, 1
0x14003c894  mov     dword ptr [rbp+var_40], eax
0x14003c897  mov     r9d, 6C9h
0x14003c89d  mov     dword ptr [rbp+var_8], eax
0x14003c8a0  lea     rcx, aAttemptingToQu_0; "Attempting to queue Tunnel State DSM wi"...
0x14003c8a7  movups  [rbp+var_50], xmm0
0x14003c8ab  movups  [rbp+var_38], xmm0
0x14003c8af  movups  [rbp+var_28], xmm0
0x14003c8b3  movups  [rbp+var_18], xmm0
0x14003c8b7  call    Debug_FreAssertMsg
0x14003c8bc  mov     rax, [rbx+8]
0x14003c8c0  lea     r8, aOnecoreDrivers_17; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003c8c7  mov     r9d, 6CAh
0x14003c8cd  lea     rcx, aAttemptingToQu; "Attempting to queue Tunnel State DSM on"...
0x14003c8d4  mov     edx, [rax+2E8h]
0x14003c8da  shr     rdx, 1Ch
0x14003c8de  and     dl, 1
0x14003c8e1  call    Debug_FreAssertMsg
0x14003c8e6  mov     dl, cs:WdfClientVersionHigherThanFramework
0x14003c8ec  xor     eax, eax
0x14003c8ee  or      r8d, 0FFFFFFFFh
0x14003c8f2  mov     [rbp+var_40], rax
0x14003c8f6  xorps   xmm0, xmm0
0x14003c8f9  movups  [rbp+var_50], xmm0
0x14003c8fd  test    dl, dl
0x14003c8ff  jz      short loc_14003C922
0x14003c901  cmp     cs:WdfStructureCount, 43h ; 'C'
0x14003c908  jbe     short loc_14003C91C
0x14003c90a  mov     rax, cs:WdfStructures
0x14003c911  mov     ecx, [rax+218h]
0x14003c917  mov     dword ptr [rbp+var_50], ecx
0x14003c91a  jmp     short loc_14003C929
0x14003c91c  mov     dword ptr [rbp+var_50], r8d
0x14003c920  jmp     short loc_14003C929
0x14003c922  mov     dword ptr [rbp+var_50], 18h
0x14003c929  lea     rax, UsbDevice_RunUpdateTunnelStateDsm
0x14003c930  mov     byte ptr [rbp+var_40], 1
0x14003c934  mov     qword ptr [rbp+var_50+8], rax
0x14003c938  xor     eax, eax
0x14003c93a  mov     [rbp+var_8], rax
0x14003c93e  movups  [rbp+var_38], xmm0
0x14003c942  movups  [rbp+var_28], xmm0
0x14003c946  movups  [rbp+var_18], xmm0
0x14003c94a  test    dl, dl
0x14003c94c  jz      short loc_14003C96F
0x14003c94e  cmp     cs:WdfStructureCount, 26h ; '&'
0x14003c955  jbe     short loc_14003C969
0x14003c957  mov     rax, cs:WdfStructures
0x14003c95e  mov     ecx, [rax+130h]
0x14003c964  mov     dword ptr [rbp+var_38], ecx
0x14003c967  jmp     short loc_14003C976
0x14003c969  mov     dword ptr [rbp+var_38], r8d
0x14003c96d  jmp     short loc_14003C976
0x14003c96f  mov     dword ptr [rbp+var_38], 38h ; '8'
0x14003c976  mov     rax, cs:off_14006C0E0
0x14003c97d  lea     r9, [rbp+arg_0]
0x14003c981  mov     [rbp+var_8], rax
0x14003c985  lea     r8, [rbp+var_38]
0x14003c989  mov     rax, [rbx+8]
0x14003c98d  lea     rdx, [rbp+var_50]
0x14003c991  mov     dword ptr [rbp+var_28+8], 1
0x14003c998  mov     dword ptr [rbp+var_28+0Ch], 1
0x14003c99f  mov     rcx, [rax]
0x14003c9a2  mov     rax, cs:WdfFunctions_01033
0x14003c9a9  mov     qword ptr [rbp+var_18], rcx
0x14003c9ad  mov     rcx, cs:WdfDriverGlobals
0x14003c9b4  mov     rax, [rax+0BD8h]
0x14003c9bb  call    _guard_dispatch_icall
0x14003c9c0  test    eax, eax
0x14003c9c2  js      short loc_14003CA1D
0x14003c9c4  mov     rax, cs:WdfFunctions_01033
0x14003c9cb  mov     r8, cs:off_14006C0E0
0x14003c9d2  mov     rdx, [rbp+arg_0]
0x14003c9d6  mov     rcx, cs:WdfDriverGlobals
0x14003c9dd  mov     rax, [rax+650h]
0x14003c9e4  call    _guard_dispatch_icall
0x14003c9e9  mov     rcx, [rbx+1B0h]
0x14003c9f0  mov     [rax+10h], rcx
0x14003c9f4  mov     [rax], rbx
0x14003c9f7  mov     [rax+8], rdi
0x14003c9fb  mov     rcx, cs:WdfFunctions_01033
0x14003ca02  mov     rdx, [rbp+arg_0]
0x14003ca06  mov     rax, [rcx+0BE0h]
0x14003ca0d  mov     rcx, cs:WdfDriverGlobals
0x14003ca14  call    _guard_dispatch_icall
0x14003ca19  mov     al, 1
0x14003ca1b  jmp     short loc_14003CA5F
0x14003ca1d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ca24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ca2b  jz      short loc_14003CA59
0x14003ca2d  mov     eax, [rbx+2Ch]
0x14003ca30  mov     r9d, 21h ; '!'
0x14003ca36  mov     rcx, [rbx+8]
0x14003ca3a  mov     dl, 2
0x14003ca3c  mov     [rsp+80h+var_58], eax
0x14003ca40  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14003ca47  mov     [rsp+80h+var_60], rax
0x14003ca4c  lea     r8d, [r9-15h]
0x14003ca50  mov     rcx, [rcx+48h]
0x14003ca54  call    WPP_RECORDER_SF_d
0x14003ca59  mov     byte ptr [rdi+43h], 4
0x14003ca5d  xor     al, al
0x14003ca5f  lea     r11, [rsp+80h+var_s0]
0x14003ca67  mov     rbx, [r11+18h]
0x14003ca6b  mov     rdi, [r11+20h]
0x14003ca6f  mov     rsp, r11
0x14003ca72  pop     rbp
0x14003ca73  retn
```
