# _PluginEngine::PopulatePluginList_::_1_::catch$8

- ea: `0x18002b1db`
- end: `0x18002b211`
- name: `_PluginEngine::PopulatePluginList_::_1_::catch$8`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b1ec`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::PopulatePluginList_::_1_::catch_8(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0xBF,
                            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002b1db  mov     [rsp+arg_8], rdx
0x18002b1e0  push    rbp
0x18002b1e1  sub     rsp, 20h
0x18002b1e5  mov     rbp, rdx
0x18002b1e8  mov     rcx, [rbp+68h]; this
0x18002b1ec  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b1f3  mov     edx, 0BFh; void *
0x18002b1f8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b1fd  mov     [rbp+78h], eax
0x18002b200  mov     rax, 0
0x18002b20a  add     rsp, 20h
0x18002b20e  pop     rbp
0x18002b20f  retn
```
