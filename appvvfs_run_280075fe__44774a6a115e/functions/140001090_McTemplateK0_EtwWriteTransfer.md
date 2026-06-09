# McTemplateK0_EtwWriteTransfer

- ea: `0x140001090`
- end: `0x1400010d2`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `66`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010e0`
- `0x1400011c0`
- `0x140001380`
- `0x140001530`
- `0x140001690`
- `0x1400017e0`

## callees

- `0x140001030`
- `0x140013b00`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(
           (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
           a2,
           a3,
           1u,
           &v4);
}

```

## disassembly

```asm
0x140001090  sub     rsp, 58h
0x140001094  mov     rax, cs:__security_cookie
0x14000109b  xor     rax, rsp
0x14000109e  mov     [rsp+58h+var_18], rax
0x1400010a3  lea     rax, [rsp+58h+var_28]
0x1400010a8  mov     r9d, 1
0x1400010ae  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400010b5  mov     [rsp+58h+var_38], rax
0x1400010ba  call    McGenEventWrite_EtwWriteTransfer
0x1400010bf  mov     rcx, [rsp+58h+var_18]
0x1400010c4  xor     rcx, rsp; StackCookie
0x1400010c7  call    __security_check_cookie
0x1400010cc  add     rsp, 58h
0x1400010d0  retn
```
