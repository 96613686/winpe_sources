# Controller_LowerAndTrackIrql

- ea: `0x1400110e0`
- end: `0x140011322`
- name: `Controller_LowerAndTrackIrql`
- size: `578`
- prototype: ``
- caller_count: `30`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006e40`
- `0x14000cce0`
- `0x14000d02c`
- `0x14000d2e4`
- `0x14000ea20`
- `0x140010b50`
- `0x140011330`
- `0x140018c80`
- `0x14001c178`
- `0x14001c620`
- `0x14001c790`
- `0x1400216b8`
- `0x140021830`
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

- `0x1400110e0`
- `0x14001ad0c`
- `0x14002b2c0`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140011179`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140011179`
- `ntoskrnl!KeBugCheckEx` at `0x140011220`
- `ntoskrnl!KeBugCheckEx` at `0x14001129d`
- `ntoskrnl!KeBugCheckEx` at `0x140011220`
- `ntoskrnl!KeBugCheckEx` at `0x14001129d`
- `ntoskrnl!KeLowerIrql` at `0x140011148`
- `ntoskrnl!KeLowerIrql` at `0x140011148`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400110f4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400110f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011102`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400112aa`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011102`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400112aa`

## pseudocode

```c
void __fastcall Controller_LowerAndTrackIrql(_QWORD *a1)
{
  __int64 CurrentProcessorNumber; // rdi
  int v3; // edx
  __int64 v4; // rax
  __int64 v5; // rdx
  KIRQL v6; // cl
  ULONG_PTR v7; // rax
  ULONG_PTR v8; // rax
  KIRQL CurrentIrql; // al
  int v10; // edx
  int v11; // edx
  int v12; // r8d
  int v13; // r9d

  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  if ( KeGetCurrentIrql() == 2 )
  {
    if ( (unsigned int)CurrentProcessorNumber >= *((_DWORD *)a1 + 330) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_d(
          a1[9],
          v3,
          4,
          344,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          CurrentProcessorNumber);
      }
      v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 264))(WdfDriverGlobals, *a1);
      KeBugCheckEx(0x144u, 4u, v7, 2u, 1u);
    }
    v4 = a1[164];
    v5 = 2 * CurrentProcessorNumber;
    if ( !*(_BYTE *)(v4 + 2 * CurrentProcessorNumber) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_d(
          a1[9],
          v5,
          4,
          345,
          (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
          CurrentProcessorNumber);
      }
      v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 264))(WdfDriverGlobals, *a1);
      KeBugCheckEx(0x144u, 4u, v8, 2u, 2u);
    }
    v6 = *(_BYTE *)(v4 + v5 + 1);
    *(_BYTE *)(v4 + 2 * CurrentProcessorNumber) = 0;
    *(_BYTE *)(a1[164] + v5 + 1) = -1;
    KeLowerIrql(v6);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CurrentIrql = KeGetCurrentIrql();
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(a1[9], v10, 4, 346, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, CurrentIrql);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v11, v12, v13);
    }
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
    Controller_ReportFatalError((_DWORD)a1, 0, 4136, 0, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x1400110e0  mov     [rsp+arg_0], rbx
0x1400110e5  mov     [rsp+arg_8], rsi
0x1400110ea  push    rdi
0x1400110eb  sub     rsp, 40h
0x1400110ef  mov     rbx, rcx
0x1400110f2  xor     ecx, ecx; ProcNumber
0x1400110f4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400110fb  nop     dword ptr [rax+rax+00h]
0x140011100  mov     edi, eax
0x140011102  call    cs:__imp_KeGetCurrentIrql
0x140011109  nop     dword ptr [rax+rax+00h]
0x14001110e  cmp     al, 2
0x140011110  jnz     short loc_140011165
0x140011112  cmp     edi, [rbx+528h]
0x140011118  jnb     loc_1400111B0
0x14001111e  mov     rax, [rbx+520h]
0x140011125  lea     rdx, [rdi+rdi]
0x140011129  cmp     byte ptr [rax+rdx], 0
0x14001112d  jz      loc_14001122D
0x140011133  movzx   ecx, byte ptr [rax+rdx+1]; NewIrql
0x140011138  mov     byte ptr [rax+rdx], 0
0x14001113c  mov     rax, [rbx+520h]
0x140011143  mov     byte ptr [rax+rdx+1], 0FFh
0x140011148  call    cs:__imp_KeLowerIrql
0x14001114f  nop     dword ptr [rax+rax+00h]
0x140011154  mov     rbx, [rsp+48h+arg_0]
0x140011159  mov     rsi, [rsp+48h+arg_8]
0x14001115e  add     rsp, 40h
0x140011162  pop     rdi
0x140011163  retn
0x140011165  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001116c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140011173  jnz     loc_1400112AA
0x140011179  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140011180  nop     dword ptr [rax+rax+00h]
0x140011185  test    al, al
0x140011187  jnz     short loc_14001118A
0x140011189  int     3; Trap to Debugger
0x14001118a  xor     eax, eax
0x14001118c  xor     r9d, r9d
0x14001118f  mov     [rsp+48h+var_18], rax
0x140011194  xor     edx, edx
0x140011196  mov     [rsp+48h+var_20], rax
0x14001119b  mov     r8d, 1028h
0x1400111a1  mov     rcx, rbx
0x1400111a4  mov     [rsp+48h+BugCheckParameter4], rax
0x1400111a9  call    Controller_ReportFatalError
0x1400111ae  jmp     short loc_140011154
0x1400111b0  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400111b7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400111be  jz      short loc_1400111E7
0x1400111c0  mov     rcx, [rbx+48h]
0x1400111c4  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400111cb  mov     r9d, 158h
0x1400111d1  mov     dword ptr [rsp+48h+var_20], edi
0x1400111d5  mov     r8d, 4
0x1400111db  mov     [rsp+48h+BugCheckParameter4], rax
0x1400111e0  mov     dl, 2
0x1400111e2  call    WPP_RECORDER_SF_d
0x1400111e7  mov     rax, cs:WdfFunctions_01033
0x1400111ee  mov     rdx, [rbx]
0x1400111f1  mov     rcx, cs:WdfDriverGlobals
0x1400111f8  mov     rax, [rax+108h]
0x1400111ff  call    _guard_dispatch_icall
0x140011204  mov     r9d, 2; BugCheckParameter3
0x14001120a  mov     [rsp+48h+BugCheckParameter4], 1; BugCheckParameter4
0x140011213  mov     r8, rax; BugCheckParameter2
0x140011216  mov     edx, 4; BugCheckParameter1
0x14001121b  mov     ecx, 144h; BugCheckCode
0x140011220  call    cs:__imp_KeBugCheckEx
0x14001122d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140011234  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001123b  jz      short loc_140011264
0x14001123d  mov     rcx, [rbx+48h]
0x140011241  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140011248  mov     r9d, 159h
0x14001124e  mov     dword ptr [rsp+48h+var_20], edi
0x140011252  mov     r8d, 4
0x140011258  mov     [rsp+48h+BugCheckParameter4], rax
0x14001125d  mov     dl, 2
0x14001125f  call    WPP_RECORDER_SF_d
0x140011264  mov     rax, cs:WdfFunctions_01033
0x14001126b  mov     rdx, [rbx]
0x14001126e  mov     rcx, cs:WdfDriverGlobals
0x140011275  mov     rax, [rax+108h]
0x14001127c  call    _guard_dispatch_icall
0x140011281  mov     r9d, 2; BugCheckParameter3
0x140011287  mov     [rsp+48h+BugCheckParameter4], 2; BugCheckParameter4
0x140011290  mov     r8, rax; BugCheckParameter2
0x140011293  mov     edx, 4; BugCheckParameter1
0x140011298  mov     ecx, 144h; BugCheckCode
0x14001129d  call    cs:__imp_KeBugCheckEx
0x1400112aa  call    cs:__imp_KeGetCurrentIrql
0x1400112b1  nop     dword ptr [rax+rax+00h]
0x1400112b6  mov     rcx, [rbx+48h]
0x1400112ba  mov     r9d, 15Ah
0x1400112c0  movzx   eax, al
0x1400112c3  mov     r8d, 4
0x1400112c9  mov     dword ptr [rsp+48h+var_20], eax
0x1400112cd  mov     dl, 2
0x1400112cf  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400112d6  mov     [rsp+48h+BugCheckParameter4], rax
0x1400112db  call    WPP_RECORDER_SF_d
0x1400112e0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400112e7  jz      loc_140011179
0x1400112ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112f4  lea     rax, aExpectedToBeCa; "Expected to be called at DISPATCH_LEVEL"...
0x1400112fb  mov     [rsp+48h+var_10], rax
0x140011300  lea     rax, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140011307  mov     dword ptr [rsp+48h+var_18], 3801h
0x14001130f  mov     [rsp+48h+var_20], rax
0x140011314  mov     rcx, [rcx+40h]
0x140011318  call    WPP_RECORDER_SF_sds
0x14001131d  jmp     loc_140011179
```
