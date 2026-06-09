# McTemplateU0q_EventWriteTransfer

- ea: `0x18000e970`
- end: `0x18000e9bf`
- name: `McTemplateU0q_EventWriteTransfer`
- size: `79`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bd0`
- `0x180001dd0`
- `0x180002c80`
- `0x180003100`
- `0x180003c10`
- `0x180003fa0`
- `0x180006410`
- `0x1800068b0`
- `0x180006db0`
- `0x180008020`
- `0x1800098a0`
- `0x180009aa0`
- `0x18000a160`
- `0x18000c770`
- `0x18000d840`
- `0x18000e4e0`
- `0x180015544`
- `0x1800159c4`
- `0x180018dac`
- `0x18001910c`
- `0x18001939c`
- `0x18001a090`
- `0x18001a170`
- `0x18001a250`
- `0x18001a510`
- `0x18001a670`
- `0x18001af50`
- `0x18001db90`

## callees

- `0x18000ea40`
- `0x180020c30`

## pseudocode

```c
ULONG __fastcall McTemplateU0q_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x18000e970  mov     r11, rsp
0x18000e973  mov     [r11+18h], r8d
0x18000e977  sub     rsp, 68h
0x18000e97b  mov     rax, cs:__security_cookie
0x18000e982  xor     rax, rsp
0x18000e985  mov     [rsp+68h+var_18], rax
0x18000e98a  lea     rax, [r11+18h]
0x18000e98e  mov     qword ptr [r11-20h], 4
0x18000e996  mov     [r11-28h], rax
0x18000e99a  mov     r9d, 2
0x18000e9a0  lea     rax, [r11-38h]
0x18000e9a4  mov     [r11-48h], rax
0x18000e9a8  call    McGenEventWrite_EventWriteTransfer
0x18000e9ad  mov     rcx, [rsp+68h+var_18]
0x18000e9b2  xor     rcx, rsp; StackCookie
0x18000e9b5  call    __security_check_cookie
0x18000e9ba  add     rsp, 68h
0x18000e9be  retn
```
