# _CProvisioningSingleton::SetProvisioningProvider_::_1_::catch$3

- ea: `0x18002af5a`
- end: `0x18002af90`
- name: `_CProvisioningSingleton::SetProvisioningProvider_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002af6b`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::SetProvisioningProvider_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xA9,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002af5a  mov     [rsp+arg_8], rdx
0x18002af5f  push    rbp
0x18002af60  sub     rsp, 20h
0x18002af64  mov     rbp, rdx
0x18002af67  mov     rcx, [rbp+28h]; this
0x18002af6b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002af72  mov     edx, 0A9h; void *
0x18002af77  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002af7c  mov     [rbp+30h], eax
0x18002af7f  mov     rax, 0
0x18002af89  add     rsp, 20h
0x18002af8d  pop     rbp
0x18002af8e  retn
```
