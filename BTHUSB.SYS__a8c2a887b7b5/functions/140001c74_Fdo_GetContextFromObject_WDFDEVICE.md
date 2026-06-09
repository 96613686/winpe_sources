# Fdo::GetContextFromObject(WDFDEVICE__ *)

- ea: `0x140001c74`
- end: `0x140001ca2`
- name: `?GetContextFromObject@Fdo@@CAPEAV1@PEAUWDFDEVICE__@@@Z`
- size: `46`
- prototype: `struct Fdo *__fastcall(struct WDFDEVICE__ *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001c50`
- `0x140018910`
- `0x140018a70`
- `0x140018b00`
- `0x140018ef0`
- `0x140018f10`
- `0x140019008`

## callees

- `0x14000de00`

## pseudocode

```c
struct Fdo *__fastcall Fdo::GetContextFromObject(struct WDFDEVICE__ *a1)
{
  return (struct Fdo *)((__int64 (__fastcall *)(_LIST_ENTRY *, struct WDFDEVICE__ *, __int64 *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[101].Flink)(
                         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
                         a1,
                         off_140013060);
}

```

## disassembly

```asm
0x140001c74  sub     rsp, 28h
0x140001c78  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140001c7f  mov     rdx, rcx
0x140001c82  mov     r8, cs:off_140013060
0x140001c89  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140001c90  mov     rax, [rax+650h]
0x140001c97  call    _guard_dispatch_icall
0x140001c9c  add     rsp, 28h
0x140001ca0  retn
```
