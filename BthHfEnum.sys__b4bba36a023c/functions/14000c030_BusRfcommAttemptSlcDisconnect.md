# BusRfcommAttemptSlcDisconnect

- ea: `0x14000c030`
- end: `0x14000c0d8`
- name: `BusRfcommAttemptSlcDisconnect`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400041d0`
- `0x14000c030`
- `0x14000c438`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BusRfcommAttemptSlcDisconnect(__int64 a1)
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
      11,
      (__int64)WPP_7c449b44c0323832605238337e7a72e5_Traceguids);
  }
  RfcommDisconnect(v2);
  return 0;
}

```

## disassembly

```asm
0x14000c030  push    rbx
0x14000c032  sub     rsp, 40h
0x14000c036  mov     rax, cs:WdfFunctions_01015
0x14000c03d  mov     rdx, rcx
0x14000c040  mov     rcx, cs:WdfDriverGlobals
0x14000c047  mov     rax, [rax+6E8h]
0x14000c04e  call    _guard_dispatch_icall
0x14000c053  mov     rbx, rax
0x14000c056  mov     r10, cs:WPP_GLOBAL_Control
0x14000c05d  lea     rax, WPP_GLOBAL_Control
0x14000c064  cmp     r10, rax
0x14000c067  jz      short loc_14000C07D
0x14000c069  mov     ecx, [r10+2Ch]
0x14000c06d  test    cl, 4
0x14000c070  jz      short loc_14000C07D
0x14000c072  cmp     byte ptr [r10+29h], 4
0x14000c077  jb      short loc_14000C07D
0x14000c079  mov     dl, 1
0x14000c07b  jmp     short loc_14000C07F
0x14000c07d  xor     dl, dl
0x14000c07f  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c086  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c08d  setnz   r8b
0x14000c091  test    dl, dl
0x14000c093  jnz     short loc_14000C09A
0x14000c095  test    r8b, r8b
0x14000c098  jz      short loc_14000C0C7
0x14000c09a  mov     r9, [r10+40h]
0x14000c09e  lea     rax, WPP_7c449b44c0323832605238337e7a72e5_Traceguids
0x14000c0a5  mov     rcx, [r10+18h]
0x14000c0a9  mov     [rsp+48h+var_10], rax
0x14000c0ae  mov     [rsp+48h+var_18], 0Bh
0x14000c0b5  mov     [rsp+48h+var_20], 3
0x14000c0bd  mov     [rsp+48h+var_28], 4
0x14000c0c2  call    WPP_RECORDER_AND_TRACE_SF_
0x14000c0c7  mov     rcx, rbx
0x14000c0ca  call    RfcommDisconnect
0x14000c0cf  xor     eax, eax
0x14000c0d1  add     rsp, 40h
0x14000c0d5  pop     rbx
0x14000c0d6  retn
```
