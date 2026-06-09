# McTemplateU0qq_EtwEventWriteTransfer

- ea: `0x180016f18`
- end: `0x180016f7b`
- name: `McTemplateU0qq_EtwEventWriteTransfer`
- size: `99`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043d0`
- `0x180016b9c`

## callees

- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0qq_EtwEventWriteTransfer(int a1, int a2, int a3, int a4)
{
  _QWORD v5[6]; // [rsp+30h] [rbp-48h] BYREF
  int v6; // [rsp+90h] [rbp+18h] BYREF
  int v7; // [rsp+98h] [rbp+20h] BYREF

  v7 = a4;
  v6 = a3;
  v5[3] = 4;
  v5[2] = &v6;
  v5[5] = 4;
  v5[4] = &v7;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 3, (__int64)v5);
}

```

## disassembly

```asm
0x180016f18  mov     r11, rsp
0x180016f1b  mov     [r11+20h], r9d
0x180016f1f  mov     [r11+18h], r8d
0x180016f23  sub     rsp, 78h
0x180016f27  mov     rax, cs:__security_cookie
0x180016f2e  xor     rax, rsp
0x180016f31  mov     [rsp+78h+var_18], rax
0x180016f36  lea     rax, [r11+18h]
0x180016f3a  mov     qword ptr [r11-30h], 4
0x180016f42  mov     [r11-38h], rax
0x180016f46  mov     r9d, 3
0x180016f4c  lea     rax, [r11+20h]
0x180016f50  mov     qword ptr [r11-20h], 4
0x180016f58  mov     [r11-28h], rax
0x180016f5c  lea     rax, [r11-48h]
0x180016f60  mov     [r11-58h], rax
0x180016f64  call    McGenEventWrite_EtwEventWriteTransfer
0x180016f69  mov     rcx, [rsp+78h+var_18]
0x180016f6e  xor     rcx, rsp; StackCookie
0x180016f71  call    __security_check_cookie
0x180016f76  add     rsp, 78h
0x180016f7a  retn
```
