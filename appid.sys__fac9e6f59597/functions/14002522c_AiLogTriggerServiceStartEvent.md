# AiLogTriggerServiceStartEvent

- ea: `0x14002522c`
- end: `0x1400252d5`
- name: `AiLogTriggerServiceStartEvent`
- size: `169`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14001f9f0`
- `0x140021924`

## callees

- `0x1400016d8`
- `0x14002522c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140025279`
- `ntoskrnl!EtwWrite` at `0x140025279`
- `ntoskrnl!EtwUnregister` at `0x14002528c`
- `ntoskrnl!EtwUnregister` at `0x14002528c`
- `ntoskrnl!EtwRegister` at `0x14002524c`
- `ntoskrnl!EtwRegister` at `0x14002524c`

## pseudocode

```c
int AiLogTriggerServiceStartEvent()
{
  NTSTATUS v0; // ebx
  PDEVICE_OBJECT *v1; // rax
  ULONGLONG RegHandle; // [rsp+40h] [rbp+8h] BYREF

  RegHandle = 0;
  if ( EtwRegister(&AppIdServiceTriggerEventProviderId, 0, 0, &RegHandle) < 0
    || (v0 = EtwWrite(RegHandle, &AppIdStartServiceEvent, 0, 0, 0), LODWORD(v1) = EtwUnregister(RegHandle), v0 < 0) )
  {
    v1 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v1) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)v1 & 1) != 0 )
        LODWORD(v1) = WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids);
    }
  }
  return (int)v1;
}

```

## disassembly

```asm
0x14002522c  push    rbx
0x14002522e  sub     rsp, 30h
0x140025232  lea     r9, [rsp+38h+RegHandle]; RegHandle
0x140025237  mov     [rsp+38h+RegHandle], 0
0x140025240  xor     r8d, r8d; CallbackContext
0x140025243  lea     rcx, AppIdServiceTriggerEventProviderId; ProviderId
0x14002524a  xor     edx, edx; EnableCallback
0x14002524c  call    cs:__imp_EtwRegister
0x140025253  nop     dword ptr [rax+rax+00h]
0x140025258  mov     ebx, eax
0x14002525a  test    eax, eax
0x14002525c  js      short loc_14002529C
0x14002525e  mov     rcx, [rsp+38h+RegHandle]; RegHandle
0x140025263  lea     rdx, AppIdStartServiceEvent; EventDescriptor
0x14002526a  xor     r9d, r9d; UserDataCount
0x14002526d  mov     [rsp+38h+UserData], 0; UserData
0x140025276  xor     r8d, r8d; ActivityId
0x140025279  call    cs:__imp_EtwWrite
0x140025280  nop     dword ptr [rax+rax+00h]
0x140025285  mov     rcx, [rsp+38h+RegHandle]; RegHandle
0x14002528a  mov     ebx, eax
0x14002528c  call    cs:__imp_EtwUnregister
0x140025293  nop     dword ptr [rax+rax+00h]
0x140025298  test    ebx, ebx
0x14002529a  jns     short loc_1400252CE
0x14002529c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252a3  lea     rax, WPP_GLOBAL_Control
0x1400252aa  cmp     rcx, rax
0x1400252ad  jz      short loc_1400252CE
0x1400252af  mov     eax, [rcx+2Ch]
0x1400252b2  test    al, 1
0x1400252b4  jz      short loc_1400252CE
0x1400252b6  mov     rcx, [rcx+18h]
0x1400252ba  lea     r8, WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids
0x1400252c1  mov     edx, 0Fh
0x1400252c6  mov     r9d, ebx
0x1400252c9  call    WPP_SF_D
0x1400252ce  add     rsp, 30h
0x1400252d2  pop     rbx
0x1400252d3  retn
```
