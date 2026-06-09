# McTemplateK0_EtwWriteTransfer

- ea: `0x140004964`
- end: `0x1400049a6`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140027078`

## callees

- `0x140003608`
- `0x140004b90`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)BindFltDriverEntrySuccess, a3, 1u, &v4);
}

```

## disassembly

```asm
0x140004964  sub     rsp, 58h
0x140004968  mov     rax, cs:__security_cookie
0x14000496f  xor     rax, rsp
0x140004972  mov     [rsp+58h+var_18], rax
0x140004977  lea     rax, [rsp+58h+var_28]
0x14000497c  mov     r9d, 1
0x140004982  lea     rdx, BindFltDriverEntrySuccess
0x140004989  mov     [rsp+58h+var_38], rax
0x14000498e  call    McGenEventWrite_EtwWriteTransfer
0x140004993  mov     rcx, [rsp+58h+var_18]
0x140004998  xor     rcx, rsp; StackCookie
0x14000499b  call    __security_check_cookie
0x1400049a0  add     rsp, 58h
0x1400049a4  retn
```
