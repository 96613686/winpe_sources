# McTemplateU0d_EventWriteTransfer

- ea: `0x140012058`
- end: `0x1400120af`
- name: `McTemplateU0d_EventWriteTransfer`
- size: `87`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f9a4`
- `0x1400185c8`
- `0x1400186d4`
- `0x140018768`
- `0x1400187fc`
- `0x140018920`
- `0x1400189b4`
- `0x140018aec`
- `0x140018b80`

## callees

- `0x1400029c0`
- `0x140011ffc`

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
0x140012058  mov     r11, rsp
0x14001205b  mov     [r11+18h], r8d
0x14001205f  sub     rsp, 68h
0x140012063  mov     rax, cs:__security_cookie
0x14001206a  xor     rax, rsp
0x14001206d  mov     [rsp+68h+var_18], rax
0x140012072  lea     rax, [r11+18h]
0x140012076  mov     qword ptr [r11-20h], 4
0x14001207e  mov     [r11-28h], rax
0x140012082  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140012089  lea     rax, [r11-38h]
0x14001208d  mov     r9d, 2
0x140012093  mov     [r11-48h], rax
0x140012097  call    McGenEventWrite_EventWriteTransfer
0x14001209c  mov     rcx, [rsp+68h+var_18]
0x1400120a1  xor     rcx, rsp; StackCookie
0x1400120a4  call    __security_check_cookie
0x1400120a9  add     rsp, 68h
0x1400120ad  retn
```
