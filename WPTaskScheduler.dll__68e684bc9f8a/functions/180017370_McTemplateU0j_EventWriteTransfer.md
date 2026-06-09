# McTemplateU0j_EventWriteTransfer

- ea: `0x180017370`
- end: `0x1800173b7`
- name: `McTemplateU0j_EventWriteTransfer`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bd0`
- `0x180001dd0`
- `0x1800025b0`
- `0x180002c80`
- `0x180002d90`
- `0x180002f00`
- `0x180003fa0`
- `0x180005440`
- `0x180006410`
- `0x1800074e0`
- `0x180009360`
- `0x18000d7f0`
- `0x180017470`
- `0x1800174c0`
- `0x180017530`
- `0x180017590`
- `0x1800177a0`
- `0x180017850`

## callees

- `0x18000ea40`
- `0x180020c30`

## pseudocode

```c
ULONG __fastcall McTemplateU0j_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  __int64 v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]

  v5 = a3;
  v6 = 16;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x180017370  mov     r11, rsp
0x180017373  sub     rsp, 68h
0x180017377  mov     rax, cs:__security_cookie
0x18001737e  xor     rax, rsp
0x180017381  mov     [rsp+68h+var_18], rax
0x180017386  lea     rax, [r11-38h]
0x18001738a  mov     [r11-28h], r8
0x18001738e  mov     r9d, 2
0x180017394  mov     [r11-48h], rax
0x180017398  mov     qword ptr [r11-20h], 10h
0x1800173a0  call    McGenEventWrite_EventWriteTransfer
0x1800173a5  mov     rcx, [rsp+68h+var_18]
0x1800173aa  xor     rcx, rsp; StackCookie
0x1800173ad  call    __security_check_cookie
0x1800173b2  add     rsp, 68h
0x1800173b6  retn
```
