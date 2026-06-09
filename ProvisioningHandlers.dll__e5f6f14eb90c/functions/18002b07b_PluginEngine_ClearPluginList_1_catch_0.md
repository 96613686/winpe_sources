# _PluginEngine::ClearPluginList_::_1_::catch$0

- ea: `0x18002b07b`
- end: `0x18002b0b1`
- name: `_PluginEngine::ClearPluginList_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b08c`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::ClearPluginList_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xCB,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b07b  mov     [rsp+arg_8], rdx
0x18002b080  push    rbp
0x18002b081  sub     rsp, 20h
0x18002b085  mov     rbp, rdx
0x18002b088  mov     rcx, [rbp+28h]; this
0x18002b08c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b093  mov     edx, 0CBh; void *
0x18002b098  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b09d  mov     [rbp+30h], eax
0x18002b0a0  mov     rax, 0
0x18002b0aa  add     rsp, 20h
0x18002b0ae  pop     rbp
0x18002b0af  retn
```
