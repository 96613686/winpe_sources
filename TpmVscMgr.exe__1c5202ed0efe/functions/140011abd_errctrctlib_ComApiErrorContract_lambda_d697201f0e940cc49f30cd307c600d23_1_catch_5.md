# _errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$5

- ea: `0x140011abd`
- end: `0x140011ae2`
- name: `_errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch$5`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23____::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 80) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x140011abd  mov     [rsp+arg_8], rdx
0x140011ac2  push    rbp
0x140011ac3  sub     rsp, 20h
0x140011ac7  mov     rbp, rdx
0x140011aca  mov     dword ptr [rbp+50h], 8007000Eh
0x140011ad1  mov     rax, 0
0x140011adb  add     rsp, 20h
0x140011adf  pop     rbp
0x140011ae0  retn
```
