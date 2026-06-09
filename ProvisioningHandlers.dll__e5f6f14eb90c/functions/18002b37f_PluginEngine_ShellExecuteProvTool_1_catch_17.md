# _PluginEngine::ShellExecuteProvTool_::_1_::catch$17

- ea: `0x18002b37f`
- end: `0x18002b3b8`
- name: `_PluginEngine::ShellExecuteProvTool_::_1_::catch$17`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b393`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::ShellExecuteProvTool_::_1_::catch_17(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 392),
                           (void *)0xF0,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b37f  mov     [rsp+arg_8], rdx
0x18002b384  push    rbp
0x18002b385  sub     rsp, 20h
0x18002b389  mov     rbp, rdx
0x18002b38c  mov     rcx, [rbp+188h]; this
0x18002b393  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b39a  mov     edx, 0F0h; void *
0x18002b39f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b3a4  mov     [rbp+20h], eax
0x18002b3a7  mov     rax, 0
0x18002b3b1  add     rsp, 20h
0x18002b3b5  pop     rbp
0x18002b3b6  retn
```
