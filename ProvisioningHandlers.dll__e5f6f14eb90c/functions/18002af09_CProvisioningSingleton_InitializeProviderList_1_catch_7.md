# _CProvisioningSingleton::InitializeProviderList_::_1_::catch$7

- ea: `0x18002af09`
- end: `0x18002af42`
- name: `_CProvisioningSingleton::InitializeProviderList_::_1_::catch$7`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002af1d`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::InitializeProviderList_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x9B,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002af09  mov     [rsp+arg_8], rdx
0x18002af0e  push    rbp
0x18002af0f  sub     rsp, 20h
0x18002af13  mov     rbp, rdx
0x18002af16  mov     rcx, [rbp+98h]; this
0x18002af1d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002af24  mov     edx, 9Bh; void *
0x18002af29  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002af2e  mov     [rbp+20h], eax
0x18002af31  mov     rax, 0
0x18002af3b  add     rsp, 20h
0x18002af3f  pop     rbp
0x18002af40  retn
```
