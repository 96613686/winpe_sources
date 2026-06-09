# AiLogEvent

- ea: `0x140024f88`
- end: `0x140024fe4`
- name: `AiLogEvent`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140023c04`

## callees

- `0x1400016d8`
- `0x140024f88`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140024f9b`
- `ntoskrnl!EtwWrite` at `0x140024f9b`

## pseudocode

```c
NTSTATUS __fastcall AiLogEvent(REGHANDLE a1, const EVENT_DESCRIPTOR *a2)
{
  NTSTATUS result; // eax

  result = EtwWrite(a1, a2, 0, 0, 0);
  if ( result < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    return WPP_SF_D(
             WPP_GLOBAL_Control->AttachedDevice,
             10,
             WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids,
             (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x140024f88  sub     rsp, 38h
0x140024f8c  xor     r9d, r9d; UserDataCount
0x140024f8f  mov     [rsp+38h+UserData], 0; UserData
0x140024f98  xor     r8d, r8d; ActivityId
0x140024f9b  call    cs:__imp_EtwWrite
0x140024fa2  nop     dword ptr [rax+rax+00h]
0x140024fa7  test    eax, eax
0x140024fa9  jns     short loc_140024FDE
0x140024fab  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fb2  lea     rdx, WPP_GLOBAL_Control
0x140024fb9  cmp     rcx, rdx
0x140024fbc  jz      short loc_140024FDE
0x140024fbe  mov     edx, [rcx+2Ch]
0x140024fc1  test    dl, 4
0x140024fc4  jz      short loc_140024FDE
0x140024fc6  mov     rcx, [rcx+18h]
0x140024fca  lea     r8, WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids
0x140024fd1  mov     edx, 0Ah
0x140024fd6  mov     r9d, eax
0x140024fd9  call    WPP_SF_D
0x140024fde  add     rsp, 38h
0x140024fe2  retn
```
