# McTemplateK0_EtwWriteTransfer

- ea: `0x14000a1ac`
- end: `0x14000a1e7`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: `NTSTATUS __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const GUID *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140009d98`
- `0x14000a310`
- `0x14000be10`
- `0x14000c1d4`
- `0x14000da20`
- `0x14000db20`
- `0x140012b18`
- `0x140013f68`
- `0x140014364`

## callees

- `0x14000a14c`
- `0x140015af0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const GUID *a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 1u, &v4);
}

```

## disassembly

```asm
0x14000a1ac  sub     rsp, 58h
0x14000a1b0  mov     rax, cs:__security_cookie
0x14000a1b7  xor     rax, rsp
0x14000a1ba  mov     [rsp+58h+var_18], rax
0x14000a1bf  lea     rax, [rsp+58h+var_28]
0x14000a1c4  mov     r9d, 1
0x14000a1ca  mov     [rsp+58h+var_38], rax
0x14000a1cf  call    McGenEventWrite_EtwWriteTransfer
0x14000a1d4  mov     rcx, [rsp+58h+var_18]
0x14000a1d9  xor     rcx, rsp; StackCookie
0x14000a1dc  call    __security_check_cookie
0x14000a1e1  add     rsp, 58h
0x14000a1e5  retn
```
