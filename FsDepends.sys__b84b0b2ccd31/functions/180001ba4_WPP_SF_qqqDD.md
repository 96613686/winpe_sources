# WPP_SF_qqqDD

- ea: `0x180001ba4`
- end: `0x180001c2c`
- name: `WPP_SF_qqqDD`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001610`

## callees

- `0x180001fb0`

## pseudocode

```c
__int64 __fastcall WPP_SF_qqqDD(__int64 a1)
{
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *))pfnWppTraceMessage)(
           a1,
           43,
           WPP_bc64936b77293105c4440102cf4189d6_Traceguids);
}

```

## disassembly

```asm
0x180001ba4  mov     r11, rsp
0x180001ba7  mov     [r11+20h], r9
0x180001bab  sub     rsp, 98h
0x180001bb2  mov     rax, cs:pfnWppTraceMessage
0x180001bb9  lea     rdx, [r11-18h]
0x180001bbd  mov     qword ptr [r11-28h], 0
0x180001bc5  mov     r9d, 32h ; '2'
0x180001bcb  mov     dword ptr [r11-18h], 0
0x180001bd3  lea     r8d, [r9-2Eh]
0x180001bd7  mov     [r11-30h], r8
0x180001bdb  mov     [r11-38h], rdx
0x180001bdf  lea     rdx, [r11+38h]
0x180001be3  mov     [r11-40h], r8
0x180001be7  lea     r8d, [r9-2Ah]
0x180001beb  mov     [r11-48h], rdx
0x180001bef  lea     rdx, [r11+30h]
0x180001bf3  mov     [r11-50h], r8
0x180001bf7  mov     [r11-58h], rdx
0x180001bfb  lea     rdx, [r11+28h]
0x180001bff  mov     [r11-60h], r8
0x180001c03  mov     [r11-68h], rdx
0x180001c07  lea     rdx, [r11+20h]
0x180001c0b  mov     [r11-70h], r8
0x180001c0f  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x180001c16  mov     [r11-78h], rdx
0x180001c1a  lea     edx, [r9-7]
0x180001c1e  call    _guard_dispatch_icall
0x180001c23  add     rsp, 98h
0x180001c2a  retn
```
