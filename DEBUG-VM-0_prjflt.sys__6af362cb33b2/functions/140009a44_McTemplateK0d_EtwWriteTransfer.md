# McTemplateK0d_EtwWriteTransfer

- ea: `0x140009a44`
- end: `0x140009a9b`
- name: `McTemplateK0d_EtwWriteTransfer`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400484e0`

## callees

- `0x140004100`
- `0x14000ba20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0d_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ProjFsDriverEntryFailure, a3, 2u, &v5);
}

```

## disassembly

```asm
0x140009a44  mov     r11, rsp
0x140009a47  mov     [r11+20h], r9d
0x140009a4b  sub     rsp, 68h
0x140009a4f  mov     rax, cs:__security_cookie
0x140009a56  xor     rax, rsp
0x140009a59  mov     [rsp+68h+var_18], rax
0x140009a5e  lea     rax, [r11+20h]
0x140009a62  mov     qword ptr [r11-20h], 4
0x140009a6a  mov     [r11-28h], rax
0x140009a6e  lea     rdx, ProjFsDriverEntryFailure
0x140009a75  lea     rax, [r11-38h]
0x140009a79  mov     r9d, 2
0x140009a7f  mov     [r11-48h], rax
0x140009a83  call    McGenEventWrite_EtwWriteTransfer
0x140009a88  mov     rcx, [rsp+68h+var_18]
0x140009a8d  xor     rcx, rsp; StackCookie
0x140009a90  call    __security_check_cookie
0x140009a95  add     rsp, 68h
0x140009a99  retn
```
