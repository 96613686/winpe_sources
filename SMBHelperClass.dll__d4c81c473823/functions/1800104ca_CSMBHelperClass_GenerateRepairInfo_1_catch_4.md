# _CSMBHelperClass::GenerateRepairInfo_::_1_::catch$4

- ea: `0x1800104ca`
- end: `0x1800104fd`
- name: `_CSMBHelperClass::GenerateRepairInfo_::_1_::catch$4`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800104e5`
- `msvcrt!??1exception@@UEAA@XZ` at `0x1800104e5`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GenerateRepairInfo_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 152) = -2147467259;
  exception::~exception((exception *)(a2 + 56));
  return 0;
}

```

## disassembly

```asm
0x1800104ca  mov     [rsp+arg_8], rdx
0x1800104cf  push    rbp
0x1800104d0  sub     rsp, 20h
0x1800104d4  mov     rbp, rdx
0x1800104d7  mov     dword ptr [rbp+98h], 80004005h
0x1800104e1  lea     rcx, [rbp+38h]
0x1800104e5  call    cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
0x1800104eb  nop
0x1800104ec  mov     rax, 0
0x1800104f6  add     rsp, 20h
0x1800104fa  pop     rbp
0x1800104fb  retn
```
