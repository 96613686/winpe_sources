# McTemplateU0q_EtwEventWriteTransfer

- ea: `0x180016ec0`
- end: `0x180016f0f`
- name: `McTemplateU0q_EtwEventWriteTransfer`
- size: `79`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043d0`
- `0x18000caa0`
- `0x180014c2c`
- `0x1800167c8`

## callees

- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0q_EtwEventWriteTransfer(int a1, int a2, int a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF
  int v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = a3;
  v4[3] = 4;
  v4[2] = &v5;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180016ec0  mov     r11, rsp
0x180016ec3  mov     [r11+18h], r8d
0x180016ec7  sub     rsp, 68h
0x180016ecb  mov     rax, cs:__security_cookie
0x180016ed2  xor     rax, rsp
0x180016ed5  mov     [rsp+68h+var_18], rax
0x180016eda  lea     rax, [r11+18h]
0x180016ede  mov     qword ptr [r11-20h], 4
0x180016ee6  mov     [r11-28h], rax
0x180016eea  mov     r9d, 2
0x180016ef0  lea     rax, [r11-38h]
0x180016ef4  mov     [r11-48h], rax
0x180016ef8  call    McGenEventWrite_EtwEventWriteTransfer
0x180016efd  mov     rcx, [rsp+68h+var_18]
0x180016f02  xor     rcx, rsp; StackCookie
0x180016f05  call    __security_check_cookie
0x180016f0a  add     rsp, 68h
0x180016f0e  retn
```
