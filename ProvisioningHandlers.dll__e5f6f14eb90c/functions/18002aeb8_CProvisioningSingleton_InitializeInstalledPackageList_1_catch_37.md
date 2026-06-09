# _CProvisioningSingleton::InitializeInstalledPackageList_::_1_::catch$37

- ea: `0x18002aeb8`
- end: `0x18002aef1`
- name: `_CProvisioningSingleton::InitializeInstalledPackageList_::_1_::catch$37`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002aecc`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::InitializeInstalledPackageList_::_1_::catch_37(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 328),
                           (void *)0x110,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002aeb8  mov     [rsp+arg_8], rdx
0x18002aebd  push    rbp
0x18002aebe  sub     rsp, 20h
0x18002aec2  mov     rbp, rdx
0x18002aec5  mov     rcx, [rbp+148h]; this
0x18002aecc  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002aed3  mov     edx, 110h; void *
0x18002aed8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002aedd  mov     [rbp+50h], eax
0x18002aee0  mov     rax, 0
0x18002aeea  add     rsp, 20h
0x18002aeee  pop     rbp
0x18002aeef  retn
```
