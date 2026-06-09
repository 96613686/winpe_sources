# _CProvisioningSingleton::GetInstalledPackageList_::_1_::catch$5

- ea: `0x18002ad7c`
- end: `0x18002adb2`
- name: `_CProvisioningSingleton::GetInstalledPackageList_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002ad8d`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::GetInstalledPackageList_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x123,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002ad7c  mov     [rsp+arg_8], rdx
0x18002ad81  push    rbp
0x18002ad82  sub     rsp, 20h
0x18002ad86  mov     rbp, rdx
0x18002ad89  mov     rcx, [rbp+38h]; this
0x18002ad8d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002ad94  mov     edx, 123h; void *
0x18002ad99  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002ad9e  mov     [rbp+40h], eax
0x18002ada1  mov     rax, 0
0x18002adab  add     rsp, 20h
0x18002adaf  pop     rbp
0x18002adb0  retn
```
