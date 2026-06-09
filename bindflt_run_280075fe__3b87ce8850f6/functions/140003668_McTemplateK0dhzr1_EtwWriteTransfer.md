# McTemplateK0dhzr1_EtwWriteTransfer

- ea: `0x140003668`
- end: `0x1400036e9`
- name: `McTemplateK0dhzr1_EtwWriteTransfer`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022a40`

## callees

- `0x140003608`
- `0x140004b90`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dhzr1_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v11 = 2;
  v8 = &v15;
  v10 = &a5;
  v12 = a6;
  v9 = 4;
  v13 = 2 * a5;
  v14 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)BindFltInstanceAttachFailure, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140003668  mov     [rsp-8+arg_18], r9d
0x14000366d  push    rbp
0x14000366e  mov     rbp, rsp
0x140003671  sub     rsp, 80h
0x140003678  mov     rax, cs:__security_cookie
0x14000367f  xor     rax, rsp
0x140003682  mov     [rbp+var_10], rax
0x140003686  lea     rax, [rbp+arg_18]
0x14000368a  mov     [rbp+var_28], 2
0x140003692  mov     [rbp+var_40], rax
0x140003696  lea     rdx, BindFltInstanceAttachFailure
0x14000369d  lea     rax, [rbp+arg_20]
0x1400036a1  mov     r9d, 4
0x1400036a7  mov     [rbp+var_30], rax
0x1400036ab  xor     ecx, ecx
0x1400036ad  mov     rax, [rbp+arg_28]
0x1400036b1  mov     [rbp+var_20], rax
0x1400036b5  movzx   eax, [rbp+arg_20]
0x1400036b9  add     eax, eax
0x1400036bb  mov     [rbp+var_38], r9
0x1400036bf  mov     [rbp+var_18], eax
0x1400036c2  lea     rax, [rbp+var_50]
0x1400036c6  mov     [rsp+80h+var_60], rax
0x1400036cb  mov     [rbp+var_14], ecx
0x1400036ce  call    McGenEventWrite_EtwWriteTransfer
0x1400036d3  mov     rcx, [rbp+var_10]
0x1400036d7  xor     rcx, rsp; StackCookie
0x1400036da  call    __security_check_cookie
0x1400036df  add     rsp, 80h
0x1400036e6  pop     rbp
0x1400036e7  retn
```
