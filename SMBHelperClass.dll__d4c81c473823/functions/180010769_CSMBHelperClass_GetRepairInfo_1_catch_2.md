# _CSMBHelperClass::GetRepairInfo_::_1_::catch$2

- ea: `0x180010769`
- end: `0x180010792`
- name: `_CSMBHelperClass::GetRepairInfo_::_1_::catch$2`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18001077a`
- `msvcrt!??1exception@@UEAA@XZ` at `0x18001077a`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GetRepairInfo_::_1_::catch_2(__int64 a1, __int64 a2)
{
  exception::~exception((exception *)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x180010769  mov     [rsp+arg_8], rdx
0x18001076e  push    rbp
0x18001076f  sub     rsp, 20h
0x180010773  mov     rbp, rdx
0x180010776  lea     rcx, [rbp+40h]
0x18001077a  call    cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
0x180010780  nop
0x180010781  mov     rax, 0
0x18001078b  add     rsp, 20h
0x18001078f  pop     rbp
0x180010790  retn
```
