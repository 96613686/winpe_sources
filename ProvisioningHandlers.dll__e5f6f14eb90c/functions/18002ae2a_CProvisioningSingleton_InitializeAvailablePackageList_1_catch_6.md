# _CProvisioningSingleton::InitializeAvailablePackageList_::_1_::catch$6

- ea: `0x18002ae2a`
- end: `0x18002ae63`
- name: `_CProvisioningSingleton::InitializeAvailablePackageList_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002ae3e`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::InitializeAvailablePackageList_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0xCB,
                           (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002ae2a  mov     [rsp+arg_8], rdx
0x18002ae2f  push    rbp
0x18002ae30  sub     rsp, 20h
0x18002ae34  mov     rbp, rdx
0x18002ae37  mov     rcx, [rbp+88h]; this
0x18002ae3e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002ae45  mov     edx, 0CBh; void *
0x18002ae4a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002ae4f  mov     [rbp+20h], eax
0x18002ae52  mov     rax, 0
0x18002ae5c  add     rsp, 20h
0x18002ae60  pop     rbp
0x18002ae61  retn
```
