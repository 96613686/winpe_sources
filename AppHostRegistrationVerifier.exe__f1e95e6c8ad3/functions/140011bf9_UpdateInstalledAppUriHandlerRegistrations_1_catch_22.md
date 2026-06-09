# _UpdateInstalledAppUriHandlerRegistrations_::_1_::catch$22

- ea: `0x140011bf9`
- end: `0x140011c23`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::catch$22`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000f2a4`
- `0x140011bf9`

## pseudocode

```c
__int64 __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::catch_22(__int64 a1, __int64 a2)
{
  UpdatePackageForFailedValidation(*(HKEY *)(a2 + 56));
  return 0;
}

```

## disassembly

```asm
0x140011bf9  mov     [rsp+arg_8], rdx
0x140011bfe  push    rbp
0x140011bff  sub     rsp, 30h
0x140011c03  mov     rbp, rdx
0x140011c06  mov     rcx, [rbp+38h]; hKey
0x140011c0a  call    ?UpdatePackageForFailedValidation@@YAXPEAUHKEY__@@@Z; UpdatePackageForFailedValidation(HKEY__ *)
0x140011c0f  nop
0x140011c10  jmp     short $+2
0x140011c12  mov     rax, 0
0x140011c1c  add     rsp, 30h
0x140011c20  pop     rbp
0x140011c21  retn
```
