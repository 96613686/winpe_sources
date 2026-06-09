# McTemplateK0d_EtwWriteTransfer

- ea: `0x1400049ac`
- end: `0x140004a03`
- name: `McTemplateK0d_EtwWriteTransfer`
- size: `87`
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
NTSTATUS __fastcall McTemplateK0d_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)BindFltDriverEntryFailure, a3, 2u, &v5);
}

```

## disassembly

```asm
0x1400049ac  mov     r11, rsp
0x1400049af  mov     [r11+20h], r9d
0x1400049b3  sub     rsp, 68h
0x1400049b7  mov     rax, cs:__security_cookie
0x1400049be  xor     rax, rsp
0x1400049c1  mov     [rsp+68h+var_18], rax
0x1400049c6  lea     rax, [r11+20h]
0x1400049ca  mov     qword ptr [r11-20h], 4
0x1400049d2  mov     [r11-28h], rax
0x1400049d6  lea     rdx, BindFltDriverEntryFailure
0x1400049dd  lea     rax, [r11-38h]
0x1400049e1  mov     r9d, 2
0x1400049e7  mov     [r11-48h], rax
0x1400049eb  call    McGenEventWrite_EtwWriteTransfer
0x1400049f0  mov     rcx, [rsp+68h+var_18]
0x1400049f5  xor     rcx, rsp; StackCookie
0x1400049f8  call    __security_check_cookie
0x1400049fd  add     rsp, 68h
0x140004a01  retn
```
