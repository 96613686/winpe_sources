# _CProvisioningSingleton::GetCurrentProviderList_::_1_::catch$3

- ea: `0x18002acd6`
- end: `0x18002ad0c`
- name: `_CProvisioningSingleton::GetCurrentProviderList_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002ace7`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::GetCurrentProviderList_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x84,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002acd6  mov     [rsp+arg_8], rdx
0x18002acdb  push    rbp
0x18002acdc  sub     rsp, 20h
0x18002ace0  mov     rbp, rdx
0x18002ace3  mov     rcx, [rbp+28h]; this
0x18002ace7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002acee  mov     edx, 84h; void *
0x18002acf3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002acf8  mov     [rbp+30h], eax
0x18002acfb  mov     rax, 0
0x18002ad05  add     rsp, 20h
0x18002ad09  pop     rbp
0x18002ad0a  retn
```
