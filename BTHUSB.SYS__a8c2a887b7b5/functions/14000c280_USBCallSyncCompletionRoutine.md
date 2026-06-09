# USBCallSyncCompletionRoutine

- ea: `0x14000c280`
- end: `0x14000c30d`
- name: `USBCallSyncCompletionRoutine`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c280`
- `0x14000c60c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c2c6`
- `ntoskrnl!KeSetEvent` at `0x14000c2c6`

## pseudocode

```c
__int64 __fastcall USBCallSyncCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  __int64 v4; // rdx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, a2, 7, 15);
  KeSetEvent(a3, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, v4, 7, 16);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000c280  mov     [rsp+arg_0], rbx
0x14000c285  push    rsi
0x14000c286  sub     rsp, 30h
0x14000c28a  mov     rbx, r8
0x14000c28d  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000c294  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000c29b  jz      short loc_14000C2BE
0x14000c29d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c2a4  cmp     word ptr [rcx+48h], 0
0x14000c2a9  jz      short loc_14000C2BE
0x14000c2ab  mov     rcx, [rcx+40h]
0x14000c2af  mov     r9d, 0Fh
0x14000c2b5  lea     r8d, [r9-8]
0x14000c2b9  call    WPP_RECORDER_SF_
0x14000c2be  xor     r8d, r8d; Wait
0x14000c2c1  xor     edx, edx; Increment
0x14000c2c3  mov     rcx, rbx; Event
0x14000c2c6  call    cs:__imp_KeSetEvent
0x14000c2cd  nop     dword ptr [rax+rax+00h]
0x14000c2d2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000c2d9  jz      short loc_14000C2FC
0x14000c2db  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c2e2  cmp     word ptr [rcx+48h], 0
0x14000c2e7  jz      short loc_14000C2FC
0x14000c2e9  mov     rcx, [rcx+40h]
0x14000c2ed  mov     r9d, 10h
0x14000c2f3  lea     r8d, [r9-9]
0x14000c2f7  call    WPP_RECORDER_SF_
0x14000c2fc  mov     rbx, [rsp+38h+arg_0]
0x14000c301  mov     eax, 0C0000016h
0x14000c306  add     rsp, 30h
0x14000c30a  pop     rsi
0x14000c30b  retn
```
