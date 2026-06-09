# _CSMBHelperClass::GetRepairInfo_::_1_::catch$1

- ea: `0x180010531`
- end: `0x180010561`
- name: `_CSMBHelperClass::GetRepairInfo_::_1_::catch$1`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180010531`

## pseudocode

```c
_BOOL8 __fastcall CSMBHelperClass::GetRepairInfo_::_1_::catch_1(__int64 a1, __int64 a2)
{
  return *(_DWORD *)(a2 + 32) != 0;
}

```

## disassembly

```asm
0x180010531  mov     [rsp+arg_8], rdx
0x180010536  push    rbp
0x180010537  sub     rsp, 20h
0x18001053b  mov     rbp, rdx
0x18001053e  cmp     dword ptr [rbp+20h], 0
0x180010542  jnz     short loc_180010550
0x180010544  mov     rax, 0
0x18001054e  jmp     short loc_18001055A
0x180010550  mov     rax, 1
0x18001055a  add     rsp, 20h
0x18001055e  pop     rbp
0x18001055f  retn
```
