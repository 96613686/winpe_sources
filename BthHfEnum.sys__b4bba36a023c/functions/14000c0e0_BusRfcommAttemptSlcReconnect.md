# BusRfcommAttemptSlcReconnect

- ea: `0x14000c0e0`
- end: `0x14000c188`
- name: `BusRfcommAttemptSlcReconnect`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400041d0`
- `0x14000c0e0`
- `0x14000c4d8`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BusRfcommAttemptSlcReconnect(__int64 a1)
{
  int v1; // edx
  __int64 v2; // rbx
  int v3; // r8d

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1768))(WdfDriverGlobals, a1);
  LOBYTE(v1) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v1,
      v3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      3,
      10,
      (__int64)WPP_7c449b44c0323832605238337e7a72e5_Traceguids);
  }
  RfcommStartConnect(v2);
  return 0;
}

```

## disassembly

```asm
0x14000c0e0  push    rbx
0x14000c0e2  sub     rsp, 40h
0x14000c0e6  mov     rax, cs:WdfFunctions_01015
0x14000c0ed  mov     rdx, rcx
0x14000c0f0  mov     rcx, cs:WdfDriverGlobals
0x14000c0f7  mov     rax, [rax+6E8h]
0x14000c0fe  call    _guard_dispatch_icall
0x14000c103  mov     rbx, rax
0x14000c106  mov     r10, cs:WPP_GLOBAL_Control
0x14000c10d  lea     rax, WPP_GLOBAL_Control
0x14000c114  cmp     r10, rax
0x14000c117  jz      short loc_14000C12D
0x14000c119  mov     ecx, [r10+2Ch]
0x14000c11d  test    cl, 4
0x14000c120  jz      short loc_14000C12D
0x14000c122  cmp     byte ptr [r10+29h], 4
0x14000c127  jb      short loc_14000C12D
0x14000c129  mov     dl, 1
0x14000c12b  jmp     short loc_14000C12F
0x14000c12d  xor     dl, dl
0x14000c12f  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c136  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c13d  setnz   r8b
0x14000c141  test    dl, dl
0x14000c143  jnz     short loc_14000C14A
0x14000c145  test    r8b, r8b
0x14000c148  jz      short loc_14000C177
0x14000c14a  mov     r9, [r10+40h]
0x14000c14e  lea     rax, WPP_7c449b44c0323832605238337e7a72e5_Traceguids
0x14000c155  mov     rcx, [r10+18h]
0x14000c159  mov     [rsp+48h+var_10], rax
0x14000c15e  mov     [rsp+48h+var_18], 0Ah
0x14000c165  mov     [rsp+48h+var_20], 3
0x14000c16d  mov     [rsp+48h+var_28], 4
0x14000c172  call    WPP_RECORDER_AND_TRACE_SF_
0x14000c177  mov     rcx, rbx
0x14000c17a  call    RfcommStartConnect
0x14000c17f  xor     eax, eax
0x14000c181  add     rsp, 40h
0x14000c185  pop     rbx
0x14000c186  retn
```
