# McTemplateU0q_EventWriteTransfer

- ea: `0x18001d52c`
- end: `0x18001d57b`
- name: `McTemplateU0q_EventWriteTransfer`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048e0`
- `0x180005030`

## callees

- `0x1800106c0`
- `0x18001d4d4`

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
0x18001d52c  mov     r11, rsp
0x18001d52f  mov     [r11+18h], r8d
0x18001d533  sub     rsp, 68h
0x18001d537  mov     rax, cs:__security_cookie
0x18001d53e  xor     rax, rsp
0x18001d541  mov     [rsp+68h+var_18], rax
0x18001d546  lea     rax, [r11+18h]
0x18001d54a  mov     qword ptr [r11-20h], 4
0x18001d552  mov     [r11-28h], rax
0x18001d556  mov     r9d, 2
0x18001d55c  lea     rax, [r11-38h]
0x18001d560  mov     [r11-48h], rax
0x18001d564  call    McGenEventWrite_EventWriteTransfer
0x18001d569  mov     rcx, [rsp+68h+var_18]
0x18001d56e  xor     rcx, rsp; StackCookie
0x18001d571  call    __security_check_cookie
0x18001d576  add     rsp, 68h
0x18001d57a  retn
```
