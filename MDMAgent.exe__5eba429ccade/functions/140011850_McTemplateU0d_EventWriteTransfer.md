# McTemplateU0d_EventWriteTransfer

- ea: `0x140011850`
- end: `0x1400118a6`
- name: `McTemplateU0d_EventWriteTransfer`
- size: `86`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f1f8`
- `0x1400178e8`
- `0x1400179f0`
- `0x140017a80`
- `0x140017b10`
- `0x140017c2c`
- `0x140017cbc`
- `0x140017dec`
- `0x140017e7c`

## callees

- `0x140002930`
- `0x1400117fc`

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
0x140011850  mov     r11, rsp
0x140011853  mov     [r11+18h], r8d
0x140011857  sub     rsp, 68h
0x14001185b  mov     rax, cs:__security_cookie
0x140011862  xor     rax, rsp
0x140011865  mov     [rsp+68h+var_18], rax
0x14001186a  lea     rax, [r11+18h]
0x14001186e  mov     qword ptr [r11-20h], 4
0x140011876  mov     [r11-28h], rax
0x14001187a  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140011881  lea     rax, [r11-38h]
0x140011885  mov     r9d, 2
0x14001188b  mov     [r11-48h], rax
0x14001188f  call    McGenEventWrite_EventWriteTransfer
0x140011894  mov     rcx, [rsp+68h+var_18]
0x140011899  xor     rcx, rsp; StackCookie
0x14001189c  call    __security_check_cookie
0x1400118a1  add     rsp, 68h
0x1400118a5  retn
```
