# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::IsReadyToProcessNextRequest(void)

- ea: `0x14002d3a0`
- end: `0x14002d3f7`
- name: `?IsReadyToProcessNextRequest@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEBA_NXZ`
- size: `87`
- prototype: `bool __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140016970`
- `0x14002d3a0`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::IsReadyToProcessNextRequest(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *this)
{
  __int64 v1; // r8
  bool v2; // bl
  __int64 Timer_high; // rdx

  v1 = *((_QWORD *)this + 27);
  v2 = v1 == 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v1, v2, v1, this);
  }
  return v2;
}

```

## disassembly

```asm
0x14002d3a0  push    rbx
0x14002d3a2  sub     rsp, 30h
0x14002d3a6  mov     r8, [rcx+0D8h]
0x14002d3ad  mov     rax, rcx
0x14002d3b0  test    r8, r8
0x14002d3b3  setz    bl
0x14002d3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d3bd  lea     rdx, WPP_GLOBAL_Control
0x14002d3c4  cmp     rcx, rdx
0x14002d3c7  jz      short loc_14002D3EE
0x14002d3c9  mov     edx, [rcx+2Ch]
0x14002d3cc  test    dl, 20h
0x14002d3cf  jz      short loc_14002D3EE
0x14002d3d1  cmp     byte ptr [rcx+29h], 5
0x14002d3d5  jb      short loc_14002D3EE
0x14002d3d7  mov     rcx, [rcx+18h]
0x14002d3db  mov     [rsp+38h+var_10], rax
0x14002d3e0  movzx   r9d, bl
0x14002d3e4  mov     [rsp+38h+var_18], r8
0x14002d3e9  call    WPP_SF_Dqq
0x14002d3ee  mov     al, bl
0x14002d3f0  add     rsp, 30h
0x14002d3f4  pop     rbx
0x14002d3f5  retn
```
