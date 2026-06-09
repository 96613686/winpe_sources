# _PluginEngine::GetPluginIndexFromId_::_1_::catch$8

- ea: `0x18002b17b`
- end: `0x18002b1b1`
- name: `_PluginEngine::GetPluginIndexFromId_::_1_::catch$8`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b18c`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::GetPluginIndexFromId_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x9F,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b17b  mov     [rsp+arg_8], rdx
0x18002b180  push    rbp
0x18002b181  sub     rsp, 20h
0x18002b185  mov     rbp, rdx
0x18002b188  mov     rcx, [rbp+78h]; this
0x18002b18c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b193  mov     edx, 9Fh; void *
0x18002b198  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b19d  mov     [rbp+20h], eax
0x18002b1a0  mov     rax, 0
0x18002b1aa  add     rsp, 20h
0x18002b1ae  pop     rbp
0x18002b1af  retn
```
