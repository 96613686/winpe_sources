# Controller_RaiseAndTrackIrql

- ea: `0x140010d40`
- end: `0x140010f46`
- name: `Controller_RaiseAndTrackIrql`
- size: `518`
- prototype: ``
- caller_count: `31`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006e40`
- `0x14000cce0`
- `0x14000d02c`
- `0x14000d2e4`
- `0x14000ea20`
- `0x14000f9f0`
- `0x140010b50`
- `0x140011330`
- `0x140018ba0`
- `0x14001c178`
- `0x14001c620`
- `0x14001c790`
- `0x1400216b8`
- `0x140021964`
- `0x140021f3c`
- `0x1400224d0`
- `0x140022850`
- `0x140022b1c`
- `0x140023490`
- `0x14002390c`
- `0x14002dd50`
- `0x14002ece0`
- `0x140032f80`
- `0x140034c10`
- `0x140038220`
- `0x14003b408`
- `0x14003b570`
- `0x14004c570`
- `0x14004c650`
- `0x14004cf70`
- `0x140056390`

## callees

- `0x140010d40`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14002b2c0`
- `0x140046070`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140010dfd`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140010e84`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140010dfd`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140010e84`
- `ntoskrnl!KfRaiseIrql` at `0x140010d64`
- `ntoskrnl!KfRaiseIrql` at `0x140010d64`
- `ntoskrnl!KeLowerIrql` at `0x140010ebd`
- `ntoskrnl!KeLowerIrql` at `0x140010ebd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010d75`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010d75`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010d4d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010d4d`

## pseudocode

```c
char __fastcall Controller_RaiseAndTrackIrql(__int64 a1)
{
  int v2; // edx
  KIRQL v3; // di
  ULONG CurrentProcessorNumber; // eax
  int v5; // edx
  __int64 v6; // rcx
  char result; // al
  __int64 v8; // rdx
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  int v14; // r9d

  if ( KeGetCurrentIrql() == 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), v2, 4, 342, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v9, v10, v11);
    }
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
    Controller_ReportFatalError(a1, 0, 4134, 0, 0, 0, 0);
    return 0;
  }
  else
  {
    v3 = KfRaiseIrql(2u);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( CurrentProcessorNumber >= *(_DWORD *)(a1 + 1320) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 72),
          v5,
          4,
          343,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          CurrentProcessorNumber);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14);
      }
      if ( !KdRefreshDebuggerNotPresent() )
        __debugbreak();
      Controller_ReportFatalError(a1, 0, 4135, 0, 0, 0, 0);
      KeLowerIrql(v3);
      return 0;
    }
    else
    {
      v6 = CurrentProcessorNumber;
      result = 1;
      v8 = 2 * v6;
      *(_BYTE *)(v8 + *(_QWORD *)(a1 + 1312)) = 1;
      *(_BYTE *)(*(_QWORD *)(a1 + 1312) + v8 + 1) = v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010d40  mov     [rsp+arg_8], rbx
0x140010d45  push    rsi
0x140010d46  sub     rsp, 40h
0x140010d4a  mov     rbx, rcx
0x140010d4d  call    cs:__imp_KeGetCurrentIrql
0x140010d54  nop     dword ptr [rax+rax+00h]
0x140010d59  cmp     al, 2
0x140010d5b  jz      short loc_140010DBD
0x140010d5d  mov     cl, 2; NewIrql
0x140010d5f  mov     [rsp+48h+arg_0], rdi
0x140010d64  call    cs:__imp_KfRaiseIrql
0x140010d6b  nop     dword ptr [rax+rax+00h]
0x140010d70  xor     ecx, ecx; ProcNumber
0x140010d72  movzx   edi, al
0x140010d75  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140010d7c  nop     dword ptr [rax+rax+00h]
0x140010d81  cmp     eax, [rbx+528h]
0x140010d87  jnb     loc_140010E40
0x140010d8d  mov     ecx, eax
0x140010d8f  mov     al, 1
0x140010d91  lea     rdx, [rcx+rcx]
0x140010d95  mov     rcx, [rbx+520h]
0x140010d9c  mov     byte ptr [rdx+rcx], 1
0x140010da0  mov     rcx, [rbx+520h]
0x140010da7  mov     [rcx+rdx+1], dil
0x140010dac  mov     rdi, [rsp+48h+arg_0]
0x140010db1  mov     rbx, [rsp+48h+arg_8]
0x140010db6  add     rsp, 40h
0x140010dba  pop     rsi
0x140010dbb  retn
0x140010dbd  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010dc4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010dcb  jz      short loc_140010DFD
0x140010dcd  mov     rcx, [rbx+48h]
0x140010dd1  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140010dd8  mov     r9d, 156h
0x140010dde  mov     [rsp+48h+var_28], rax
0x140010de3  mov     r8d, 4
0x140010de9  mov     dl, 2
0x140010deb  call    WPP_RECORDER_SF_
0x140010df0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010df7  jnz     loc_140010EDC
0x140010dfd  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140010e04  nop     dword ptr [rax+rax+00h]
0x140010e09  test    al, al
0x140010e0b  jnz     short loc_140010E0E
0x140010e0d  int     3; Trap to Debugger
0x140010e0e  xor     ecx, ecx
0x140010e10  xor     r9d, r9d
0x140010e13  mov     [rsp+48h+var_18], rcx
0x140010e18  xor     edx, edx
0x140010e1a  mov     [rsp+48h+var_20], rcx
0x140010e1f  mov     r8d, 1026h
0x140010e25  mov     [rsp+48h+var_28], rcx
0x140010e2a  mov     rcx, rbx
0x140010e2d  call    Controller_ReportFatalError
0x140010e32  xor     al, al
0x140010e34  mov     rbx, [rsp+48h+arg_8]
0x140010e39  add     rsp, 40h
0x140010e3d  pop     rsi
0x140010e3e  retn
0x140010e40  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010e47  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010e4e  jz      short loc_140010E84
0x140010e50  mov     rcx, [rbx+48h]
0x140010e54  mov     r9d, 157h
0x140010e5a  mov     dword ptr [rsp+48h+var_20], eax
0x140010e5e  mov     r8d, 4
0x140010e64  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140010e6b  mov     dl, 2
0x140010e6d  mov     [rsp+48h+var_28], rax
0x140010e72  call    WPP_RECORDER_SF_d
0x140010e77  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010e7e  jnz     loc_140010F11
0x140010e84  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140010e8b  nop     dword ptr [rax+rax+00h]
0x140010e90  test    al, al
0x140010e92  jnz     short loc_140010E95
0x140010e94  int     3; Trap to Debugger
0x140010e95  xor     ecx, ecx
0x140010e97  xor     r9d, r9d
0x140010e9a  mov     [rsp+48h+var_18], rcx
0x140010e9f  xor     edx, edx
0x140010ea1  mov     [rsp+48h+var_20], rcx
0x140010ea6  mov     r8d, 1027h
0x140010eac  mov     [rsp+48h+var_28], rcx
0x140010eb1  mov     rcx, rbx
0x140010eb4  call    Controller_ReportFatalError
0x140010eb9  movzx   ecx, dil; NewIrql
0x140010ebd  call    cs:__imp_KeLowerIrql
0x140010ec4  nop     dword ptr [rax+rax+00h]
0x140010ec9  mov     rdi, [rsp+48h+arg_0]
0x140010ece  xor     al, al
0x140010ed0  mov     rbx, [rsp+48h+arg_8]
0x140010ed5  add     rsp, 40h
0x140010ed9  pop     rsi
0x140010eda  retn
0x140010edc  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ee3  lea     rax, aNotExpectedToB; "Not expected to be called at DISPATCH_L"...
0x140010eea  mov     [rsp+48h+var_10], rax
0x140010eef  lea     rax, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140010ef6  mov     dword ptr [rsp+48h+var_18], 378Bh
0x140010efe  mov     [rsp+48h+var_20], rax
0x140010f03  mov     rcx, [rcx+40h]
0x140010f07  call    WPP_RECORDER_SF_sds
0x140010f0c  jmp     loc_140010DFD
0x140010f11  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f18  lea     rax, aProcessorIndex; "Processor index out of range."
0x140010f1f  mov     [rsp+48h+var_10], rax
0x140010f24  lea     rax, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140010f2b  mov     dword ptr [rsp+48h+var_18], 37A7h
0x140010f33  mov     [rsp+48h+var_20], rax
0x140010f38  mov     rcx, [rcx+40h]
0x140010f3c  call    WPP_RECORDER_SF_sds
0x140010f41  jmp     loc_140010E84
```
