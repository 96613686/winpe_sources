# __ctrlfp

- ea: `0x4143be`
- end: `0x4143e8`
- name: `__ctrlfp`
- size: `42`
- prototype: `int()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x415977`
- `0x415bbf`
- `0x415d11`
- `0x416312`

## pseudocode

```c
int _ctrlfp()
{
  __int16 v1; // [esp+4h] [ebp-4h]

  return v1;
}

```

## disassembly

```asm
0x4143be  mov     edi, edi
0x4143c0  push    ebp
0x4143c1  mov     ebp, esp
0x4143c3  push    ecx
0x4143c4  push    ecx
0x4143c5  fstcw   [ebp+var_4]
0x4143c9  mov     ecx, [ebp+arg_4]
0x4143cc  mov     eax, [ebp+arg_0]
0x4143cf  not     ecx
0x4143d1  and     cx, [ebp+var_4]
0x4143d5  and     eax, [ebp+arg_4]
0x4143d8  or      cx, ax
0x4143db  mov     [ebp+var_8], cx
0x4143df  fldcw   [ebp+var_8]
0x4143e2  movsx   eax, [ebp+var_4]
0x4143e6  leave
0x4143e7  retn
```
