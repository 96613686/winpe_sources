# McTemplateU0d_EventWriteTransfer

- ea: `0x180011bb0`
- end: `0x180011c07`
- name: `McTemplateU0d_EventWriteTransfer`
- size: `87`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb90`
- `0x18001bb18`
- `0x18001bc24`
- `0x18001bcb8`
- `0x18001bd4c`
- `0x18001be70`
- `0x18001bf04`
- `0x18001bf98`
- `0x18001c02c`

## callees

- `0x180001c60`
- `0x180011b54`

## pseudocode

```c
ULONG __fastcall McTemplateU0d_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x180011bb0  mov     r11, rsp
0x180011bb3  mov     [r11+18h], r8d
0x180011bb7  sub     rsp, 68h
0x180011bbb  mov     rax, cs:__security_cookie
0x180011bc2  xor     rax, rsp
0x180011bc5  mov     [rsp+68h+var_18], rax
0x180011bca  lea     rax, [r11+18h]
0x180011bce  mov     qword ptr [r11-20h], 4
0x180011bd6  mov     [r11-28h], rax
0x180011bda  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180011be1  lea     rax, [r11-38h]
0x180011be5  mov     r9d, 2
0x180011beb  mov     [r11-48h], rax
0x180011bef  call    McGenEventWrite_EventWriteTransfer
0x180011bf4  mov     rcx, [rsp+68h+var_18]
0x180011bf9  xor     rcx, rsp; StackCookie
0x180011bfc  call    __security_check_cookie
0x180011c01  add     rsp, 68h
0x180011c05  retn
```
