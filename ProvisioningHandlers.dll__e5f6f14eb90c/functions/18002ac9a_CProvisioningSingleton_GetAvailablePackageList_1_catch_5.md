# _CProvisioningSingleton::GetAvailablePackageList_::_1_::catch$5

- ea: `0x18002ac9a`
- end: `0x18002acd0`
- name: `_CProvisioningSingleton::GetAvailablePackageList_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002acab`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::GetAvailablePackageList_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xDF,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002ac9a  mov     [rsp+arg_8], rdx
0x18002ac9f  push    rbp
0x18002aca0  sub     rsp, 20h
0x18002aca4  mov     rbp, rdx
0x18002aca7  mov     rcx, [rbp+38h]; this
0x18002acab  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002acb2  mov     edx, 0DFh; void *
0x18002acb7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002acbc  mov     [rbp+40h], eax
0x18002acbf  mov     rax, 0
0x18002acc9  add     rsp, 20h
0x18002accd  pop     rbp
0x18002acce  retn
```
