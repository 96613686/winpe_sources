# _PluginEngine::StartListeningPluginEvent_::_1_::catch$2

- ea: `0x18002b3d0`
- end: `0x18002b406`
- name: `_PluginEngine::StartListeningPluginEvent_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b3e1`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::StartListeningPluginEvent_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x1C0,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b3d0  mov     [rsp+arg_8], rdx
0x18002b3d5  push    rbp
0x18002b3d6  sub     rsp, 20h
0x18002b3da  mov     rbp, rdx
0x18002b3dd  mov     rcx, [rbp+78h]; this
0x18002b3e1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b3e8  mov     edx, 1C0h; void *
0x18002b3ed  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b3f2  mov     [rbp+20h], eax
0x18002b3f5  mov     rax, 0
0x18002b3ff  add     rsp, 20h
0x18002b403  pop     rbp
0x18002b404  retn
```
