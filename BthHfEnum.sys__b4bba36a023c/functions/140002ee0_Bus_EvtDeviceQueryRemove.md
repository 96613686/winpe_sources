# Bus_EvtDeviceQueryRemove

- ea: `0x140002ee0`
- end: `0x140002f66`
- name: `Bus_EvtDeviceQueryRemove`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140002ee0`
- `0x1400041d0`
- `0x14000b960`

## pseudocode

```c
__int64 __fastcall Bus_EvtDeviceQueryRemove(__int64 a1)
{
  bool v2; // dl

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      51,
      (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids);
  return BthHwUnInitialize(a1);
}

```

## disassembly

```asm
0x140002ee0  push    rbx
0x140002ee2  sub     rsp, 40h
0x140002ee6  mov     rbx, rcx
0x140002ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ef0  lea     rax, WPP_GLOBAL_Control
0x140002ef7  cmp     rcx, rax
0x140002efa  jz      short loc_140002F0D
0x140002efc  mov     eax, [rcx+2Ch]
0x140002eff  test    al, 8
0x140002f01  jz      short loc_140002F0D
0x140002f03  cmp     byte ptr [rcx+29h], 4
0x140002f07  jb      short loc_140002F0D
0x140002f09  mov     dl, 1
0x140002f0b  jmp     short loc_140002F0F
0x140002f0d  xor     dl, dl
0x140002f0f  lea     rax, WPP_RECORDER_INITIALIZED
0x140002f16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002f1d  setnz   r8b
0x140002f21  test    dl, dl
0x140002f23  jnz     short loc_140002F2A
0x140002f25  test    r8b, r8b
0x140002f28  jz      short loc_140002F57
0x140002f2a  mov     r9, [rcx+40h]
0x140002f2e  lea     rax, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x140002f35  mov     rcx, [rcx+18h]
0x140002f39  mov     [rsp+48h+var_10], rax
0x140002f3e  mov     [rsp+48h+var_18], 33h ; '3'
0x140002f45  mov     [rsp+48h+var_20], 4
0x140002f4d  mov     [rsp+48h+var_28], 4
0x140002f52  call    WPP_RECORDER_AND_TRACE_SF_
0x140002f57  mov     rcx, rbx
0x140002f5a  call    BthHwUnInitialize
0x140002f5f  add     rsp, 40h
0x140002f63  pop     rbx
0x140002f64  retn
```
