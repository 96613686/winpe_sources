# _PluginEngine::StopListeningPluginEvent_::_1_::catch$2

- ea: `0x18002b40c`
- end: `0x18002b442`
- name: `_PluginEngine::StopListeningPluginEvent_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b41d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::StopListeningPluginEvent_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x1D0,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b40c  mov     [rsp+arg_8], rdx
0x18002b411  push    rbp
0x18002b412  sub     rsp, 20h
0x18002b416  mov     rbp, rdx
0x18002b419  mov     rcx, [rbp+68h]; this
0x18002b41d  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b424  mov     edx, 1D0h; void *
0x18002b429  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b42e  mov     [rbp+20h], eax
0x18002b431  mov     rax, 0
0x18002b43b  add     rsp, 20h
0x18002b43f  pop     rbp
0x18002b440  retn
```
