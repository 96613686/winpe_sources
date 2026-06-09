# AllocWriteTransferCtxImpl

- ea: `0x140008d90`
- end: `0x140008e2e`
- name: `AllocWriteTransferCtxImpl`
- size: `158`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140008e40`
- `0x140008fd0`

## callees

- `0x1400045e4`
- `0x140006700`
- `0x140008d90`

## pseudocode

```c
__int64 __fastcall AllocWriteTransferCtxImpl(struct _DEVICE_EXTENSION *a1, unsigned int a2, struct _LIST_ENTRY *a3)
{
  const ScoUsbAltSetting *UsbAltSetting; // rax
  unsigned int v5; // esi
  unsigned int WRITE_FRAMES_X_REQ; // ebp
  unsigned int v8; // ebx

  UsbAltSetting = a1->Sco.UsbAltSetting;
  v5 = a2;
  WRITE_FRAMES_X_REQ = UsbAltSetting->WRITE_FRAMES_X_REQ;
  v8 = 32 * UsbAltSetting->MAX_WRITE_HCIPKTS_X_REQ;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLL(WPP_GLOBAL_Control->AttachedDevice, a2, (_DWORD)a3, WPP_GLOBAL_Control->DeviceExtension);
  return BthUsb_ScoAllocTransferContextsImpl(a1, v5, WRITE_FRAMES_X_REQ, v8, &a1->Sco.WriteCtxQueue, a3);
}

```

## disassembly

```asm
0x140008d90  push    rbx
0x140008d92  push    rbp
0x140008d93  push    rsi
0x140008d94  push    rdi
0x140008d95  push    r14
0x140008d97  sub     rsp, 60h
0x140008d9b  mov     rax, [rcx+478h]
0x140008da2  mov     r14, r8
0x140008da5  mov     esi, edx
0x140008da7  mov     rdi, rcx
0x140008daa  mov     ebx, [rax+38h]
0x140008dad  mov     ebp, [rax+3Ch]
0x140008db0  shl     ebx, 5
0x140008db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140008dba  mov     eax, [rcx+2Ch]
0x140008dbd  test    al, 8
0x140008dbf  jz      short loc_140008DCB
0x140008dc1  cmp     byte ptr [rcx+29h], 4
0x140008dc5  jb      short loc_140008DCB
0x140008dc7  mov     dl, 1
0x140008dc9  jmp     short loc_140008DCD
0x140008dcb  xor     dl, dl
0x140008dcd  mov     r9, [rcx+40h]
0x140008dd1  lea     rax, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140008dd8  mov     rcx, [rcx+18h]
0x140008ddc  mov     [rsp+88h+var_38], ebx
0x140008de0  mov     [rsp+88h+var_40], ebp
0x140008de4  mov     [rsp+88h+var_48], esi
0x140008de8  mov     [rsp+88h+var_50], rax
0x140008ded  mov     [rsp+88h+var_58], 0Bh
0x140008df4  mov     dword ptr [rsp+88h+var_60], 4
0x140008dfc  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x140008e01  lea     rax, [rdi+138h]
0x140008e08  mov     [rsp+88h+var_60], r14; struct _LIST_ENTRY *
0x140008e0d  mov     r9d, ebx; unsigned int
0x140008e10  mov     [rsp+88h+var_68], rax; struct _RESOURCE_QUEUE *
0x140008e15  mov     r8d, ebp; unsigned int
0x140008e18  mov     edx, esi; unsigned int
0x140008e1a  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140008e1d  call    ?BthUsb_ScoAllocTransferContextsImpl@@YAJPEAU_DEVICE_EXTENSION@@KKKPEAU_RESOURCE_QUEUE@@PEAU_LIST_ENTRY@@@Z; BthUsb_ScoAllocTransferContextsImpl(_DEVICE_EXTENSION *,ulong,ulong,ulong,_RESOURCE_QUEUE *,_LIST_ENTRY *)
0x140008e22  add     rsp, 60h
0x140008e26  pop     r14
0x140008e28  pop     rdi
0x140008e29  pop     rsi
0x140008e2a  pop     rbp
0x140008e2b  pop     rbx
0x140008e2c  retn
```
