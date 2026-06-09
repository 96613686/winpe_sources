# BthUsb_SyncCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000b0c0`
- end: `0x14000b143`
- name: `?BthUsb_SyncCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `131`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002dcc`
- `0x14000b0c0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b12b`
- `ntoskrnl!KeSetEvent` at `0x14000b12b`

## pseudocode

```c
__int64 __fastcall BthUsb_SyncCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct _KEVENT *a3)
{
  bool v4; // dl

  v4 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, v4, (_DWORD)a1, WPP_GLOBAL_Control->DeviceExtension);
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000b0c0  push    rbx
0x14000b0c2  sub     rsp, 60h
0x14000b0c6  mov     rbx, r8
0x14000b0c9  mov     r9, rdx
0x14000b0cc  mov     r8, rcx
0x14000b0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0d6  mov     eax, [rcx+2Ch]
0x14000b0d9  test    al, 2
0x14000b0db  jz      short loc_14000B0E7
0x14000b0dd  cmp     byte ptr [rcx+29h], 4
0x14000b0e1  jb      short loc_14000B0E7
0x14000b0e3  mov     dl, 1
0x14000b0e5  jmp     short loc_14000B0E9
0x14000b0e7  xor     dl, dl
0x14000b0e9  mov     eax, [r9+30h]
0x14000b0ed  mov     [rsp+68h+var_18], eax
0x14000b0f1  lea     rax, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000b0f8  mov     [rsp+68h+var_20], r9
0x14000b0fd  mov     r9, [rcx+40h]
0x14000b101  mov     rcx, [rcx+18h]
0x14000b105  mov     [rsp+68h+var_28], r8
0x14000b10a  mov     [rsp+68h+var_30], rax
0x14000b10f  mov     [rsp+68h+var_38], 0Bh
0x14000b116  mov     [rsp+68h+var_40], 2
0x14000b11e  call    WPP_RECORDER_AND_TRACE_SF_qqD
0x14000b123  xor     r8d, r8d; Wait
0x14000b126  xor     edx, edx; Increment
0x14000b128  mov     rcx, rbx; Event
0x14000b12b  call    cs:__imp_KeSetEvent
0x14000b132  nop     dword ptr [rax+rax+00h]
0x14000b137  mov     eax, 0C0000016h
0x14000b13c  add     rsp, 60h
0x14000b140  pop     rbx
0x14000b141  retn
```
