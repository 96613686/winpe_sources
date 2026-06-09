# McTemplateK0hzr0q_EtwWriteTransfer

- ea: `0x140001090`
- end: `0x140001110`
- name: `McTemplateK0hzr0q_EtwWriteTransfer`
- size: `128`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, unsigned __int16, __int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aca0`

## callees

- `0x140001030`
- `0x140001a30`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0q_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  __int16 *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  __int64 v10; // [rsp+50h] [rbp-30h]
  int v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+5Ch] [rbp-24h]
  char *v13; // [rsp+60h] [rbp-20h]
  __int64 v14; // [rsp+68h] [rbp-18h]
  unsigned __int16 v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v9 = 2;
  v12 = 0;
  v8 = (__int16 *)&v15;
  v10 = a5;
  v14 = 4;
  v11 = 2 * a4;
  v13 = &a6;
  return McGenEventWrite_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)ProcessStart2, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140001090  mov     [rsp-8+arg_18], r9w
0x140001096  push    rbp
0x140001097  mov     rbp, rsp
0x14000109a  sub     rsp, 80h
0x1400010a1  mov     rax, cs:__security_cookie
0x1400010a8  xor     rax, rsp
0x1400010ab  mov     [rbp+var_10], rax
0x1400010af  xor     ecx, ecx
0x1400010b1  mov     [rbp+var_38], 2
0x1400010b9  lea     rax, [rbp+arg_18]
0x1400010bd  mov     [rbp+var_24], ecx
0x1400010c0  mov     [rbp+var_40], rax
0x1400010c4  lea     rdx, ProcessStart2
0x1400010cb  mov     rax, [rbp+arg_20]
0x1400010cf  mov     [rbp+var_30], rax
0x1400010d3  movzx   eax, r9w
0x1400010d7  lea     r9d, [rcx+4]
0x1400010db  add     eax, eax
0x1400010dd  mov     [rbp+var_18], r9
0x1400010e1  mov     [rbp+var_28], eax
0x1400010e4  lea     rax, [rbp+arg_28]
0x1400010e8  mov     [rbp+var_20], rax
0x1400010ec  lea     rax, [rbp+var_50]
0x1400010f0  mov     [rsp+80h+var_60], rax
0x1400010f5  call    McGenEventWrite_EtwWriteTransfer
0x1400010fa  mov     rcx, [rbp+var_10]
0x1400010fe  xor     rcx, rsp; StackCookie
0x140001101  call    __security_check_cookie
0x140001106  add     rsp, 80h
0x14000110d  pop     rbp
0x14000110e  retn
```
