# _CProvisioningSingleton::GetProvisioningProvider_::_1_::catch$4

- ea: `0x18002addc`
- end: `0x18002ae12`
- name: `_CProvisioningSingleton::GetProvisioningProvider_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002aded`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::GetProvisioningProvider_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xB8,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002addc  mov     [rsp+arg_8], rdx
0x18002ade1  push    rbp
0x18002ade2  sub     rsp, 20h
0x18002ade6  mov     rbp, rdx
0x18002ade9  mov     rcx, [rbp+48h]; this
0x18002aded  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002adf4  mov     edx, 0B8h; void *
0x18002adf9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002adfe  mov     [rbp+50h], eax
0x18002ae01  mov     rax, 0
0x18002ae0b  add     rsp, 20h
0x18002ae0f  pop     rbp
0x18002ae10  retn
```
