# _PluginEngine::RunProvisioningTurn_::_1_::catch$30

- ea: `0x18002b2d4`
- end: `0x18002b30d`
- name: `_PluginEngine::RunProvisioningTurn_::_1_::catch$30`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b2e8`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::RunProvisioningTurn_::_1_::catch_30(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 232),
                           (void *)0x131,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b2d4  mov     [rsp+arg_8], rdx
0x18002b2d9  push    rbp
0x18002b2da  sub     rsp, 20h
0x18002b2de  mov     rbp, rdx
0x18002b2e1  mov     rcx, [rbp+0E8h]; this
0x18002b2e8  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b2ef  mov     edx, 131h; void *
0x18002b2f4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b2f9  mov     [rbp+40h], eax
0x18002b2fc  mov     rax, 0
0x18002b306  add     rsp, 20h
0x18002b30a  pop     rbp
0x18002b30b  retn
```
