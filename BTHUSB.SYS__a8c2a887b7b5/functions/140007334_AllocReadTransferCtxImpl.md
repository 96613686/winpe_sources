# AllocReadTransferCtxImpl

- ea: `0x140007334`
- end: `0x1400073cf`
- name: `AllocReadTransferCtxImpl`
- size: `155`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400073e0`
- `0x1400076c0`

## callees

- `0x1400045e4`
- `0x140006700`
- `0x140007334`

## pseudocode

```c
__int64 __fastcall AllocReadTransferCtxImpl(struct _DEVICE_EXTENSION *a1, unsigned int a2, struct _LIST_ENTRY *a3)
{
  unsigned int v4; // edi
  unsigned int READ_FRAMES_X_REQ; // esi

  v4 = a2;
  READ_FRAMES_X_REQ = a1->Sco.UsbAltSetting->READ_FRAMES_X_REQ;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLL(WPP_GLOBAL_Control->AttachedDevice, a2, (_DWORD)a3, WPP_GLOBAL_Control->DeviceExtension);
  return BthUsb_ScoAllocTransferContextsImpl(a1, v4, READ_FRAMES_X_REQ, 0x102u, &a1->Sco.ReadCtxQueue, a3);
}

```

## disassembly

```asm
0x140007334  push    rbx
0x140007336  push    rbp
0x140007337  push    rsi
0x140007338  push    rdi
0x140007339  sub     rsp, 68h
0x14000733d  mov     rax, [rcx+478h]
0x140007344  mov     rbp, r8
0x140007347  mov     edi, edx
0x140007349  mov     rbx, rcx
0x14000734c  mov     esi, [rax+48h]
0x14000734f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007356  mov     eax, [rcx+2Ch]
0x140007359  test    al, 8
0x14000735b  jz      short loc_140007367
0x14000735d  cmp     byte ptr [rcx+29h], 4
0x140007361  jb      short loc_140007367
0x140007363  mov     dl, 1
0x140007365  jmp     short loc_140007369
0x140007367  xor     dl, dl
0x140007369  mov     r9, [rcx+40h]
0x14000736d  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007374  mov     rcx, [rcx+18h]
0x140007378  mov     [rsp+88h+var_38], 102h
0x140007380  mov     [rsp+88h+var_40], esi
0x140007384  mov     [rsp+88h+var_48], edi
0x140007388  mov     [rsp+88h+var_50], rax
0x14000738d  mov     [rsp+88h+var_58], 0Bh
0x140007394  mov     dword ptr [rsp+88h+var_60], 4
0x14000739c  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x1400073a1  lea     rax, [rbx+198h]
0x1400073a8  mov     [rsp+88h+var_60], rbp; struct _LIST_ENTRY *
0x1400073ad  mov     r9d, 102h; unsigned int
0x1400073b3  mov     [rsp+88h+var_68], rax; struct _RESOURCE_QUEUE *
0x1400073b8  mov     r8d, esi; unsigned int
0x1400073bb  mov     edx, edi; unsigned int
0x1400073bd  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400073c0  call    ?BthUsb_ScoAllocTransferContextsImpl@@YAJPEAU_DEVICE_EXTENSION@@KKKPEAU_RESOURCE_QUEUE@@PEAU_LIST_ENTRY@@@Z; BthUsb_ScoAllocTransferContextsImpl(_DEVICE_EXTENSION *,ulong,ulong,ulong,_RESOURCE_QUEUE *,_LIST_ENTRY *)
0x1400073c5  add     rsp, 68h
0x1400073c9  pop     rdi
0x1400073ca  pop     rsi
0x1400073cb  pop     rbp
0x1400073cc  pop     rbx
0x1400073cd  retn
```
