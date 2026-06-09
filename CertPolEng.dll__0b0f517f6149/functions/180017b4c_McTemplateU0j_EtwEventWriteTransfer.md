# McTemplateU0j_EtwEventWriteTransfer

- ea: `0x180017b4c`
- end: `0x180017b9a`
- name: `McTemplateU0j_EtwEventWriteTransfer`
- size: `78`
- prototype: `__int64 __fastcall(int, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004da0`

## callees

- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0j_EtwEventWriteTransfer(int a1, __int64 a2, __int64 a3)
{
  _QWORD v4[4]; // [rsp+30h] [rbp-38h] BYREF

  v4[2] = a3;
  v4[3] = 16;
  return McGenEventWrite_EtwEventWriteTransfer(a1, (unsigned int)ProviderNotEnabled, a3, 2, (__int64)v4);
}

```

## disassembly

```asm
0x180017b4c  mov     r11, rsp
0x180017b4f  sub     rsp, 68h
0x180017b53  mov     rax, cs:__security_cookie
0x180017b5a  xor     rax, rsp
0x180017b5d  mov     [rsp+68h+var_18], rax
0x180017b62  lea     rax, [r11-38h]
0x180017b66  mov     [r11-28h], r8
0x180017b6a  mov     r9d, 2
0x180017b70  mov     [r11-48h], rax
0x180017b74  lea     rdx, ProviderNotEnabled
0x180017b7b  mov     qword ptr [r11-20h], 10h
0x180017b83  call    McGenEventWrite_EtwEventWriteTransfer
0x180017b88  mov     rcx, [rsp+68h+var_18]
0x180017b8d  xor     rcx, rsp; StackCookie
0x180017b90  call    __security_check_cookie
0x180017b95  add     rsp, 68h
0x180017b99  retn
```
