# WPP_SF_d

- ea: `0x18000d18c`
- end: `0x18000d1df`
- name: `WPP_SF_d`
- size: `83`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `61`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b78`
- `0x180001c48`
- `0x18000266c`
- `0x180003894`
- `0x180003b90`
- `0x180004b20`
- `0x180004dbc`
- `0x180005b24`
- `0x18000617c`
- `0x180006474`
- `0x1800067e8`
- `0x1800079b4`
- `0x18000cc94`
- `0x18000cd38`
- `0x18000cdc4`
- `0x18000ce50`
- `0x18000cefc`
- `0x18000d800`
- `0x18000fd78`
- `0x18001044c`
- `0x1800112c8`
- `0x18001167c`
- `0x1800117e8`
- `0x180011b03`
- `0x180011b65`
- `0x180011cb0`
- `0x180011d12`
- `0x180011e60`
- `0x180011ec2`
- `0x180012083`
- `0x1800120e5`
- `0x180012340`
- `0x1800123a2`
- `0x1800125d6`
- `0x180012638`
- `0x180012779`
- `0x1800127db`
- `0x180012d92`
- `0x180012df4`
- `0x180012f35`
- `0x180012f97`
- `0x1800130d8`
- `0x18001313a`
- `0x18001327b`
- `0x1800132dd`
- `0x18001341e`
- `0x180013480`
- `0x1800135c1`
- `0x180013623`
- `0x180013764`

## callees

- `0x1800119f0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000d1c7`
- `ntdll!EtwTraceMessage` at `0x18000d1c7`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+40h] [rbp-18h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000d18c  mov     r11, rsp
0x18000d18f  sub     rsp, 58h
0x18000d193  mov     rax, cs:__security_cookie
0x18000d19a  xor     rax, rsp
0x18000d19d  mov     [rsp+58h+var_10], rax
0x18000d1a2  mov     qword ptr [r11-28h], 0
0x18000d1aa  lea     rax, [r11-18h]
0x18000d1ae  mov     [r11-18h], r9d
0x18000d1b2  movzx   r9d, dx
0x18000d1b6  mov     edx, 2Bh ; '+'
0x18000d1bb  mov     qword ptr [r11-30h], 4
0x18000d1c3  mov     [r11-38h], rax
0x18000d1c7  call    cs:__imp_EtwTraceMessage
0x18000d1cd  mov     rcx, [rsp+58h+var_10]
0x18000d1d2  xor     rcx, rsp; StackCookie
0x18000d1d5  call    __security_check_cookie
0x18000d1da  add     rsp, 58h
0x18000d1de  retn
```
