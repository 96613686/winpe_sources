# _CProvisioningSingleton::GetInstalledPackageDetails_::_1_::catch$5

- ea: `0x18002ad24`
- end: `0x18002ad5d`
- name: `_CProvisioningSingleton::GetInstalledPackageDetails_::_1_::catch$5`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002ad38`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::GetInstalledPackageDetails_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x137,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002ad24  mov     [rsp+arg_8], rdx
0x18002ad29  push    rbp
0x18002ad2a  sub     rsp, 20h
0x18002ad2e  mov     rbp, rdx
0x18002ad31  mov     rcx, [rbp+0A8h]; this
0x18002ad38  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002ad3f  mov     edx, 137h; void *
0x18002ad44  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002ad49  mov     [rbp+20h], eax
0x18002ad4c  mov     rax, 0
0x18002ad56  add     rsp, 20h
0x18002ad5a  pop     rbp
0x18002ad5b  retn
```
