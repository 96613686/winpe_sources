# _PluginEngine::RemoveProvisioning_::_1_::catch$32

- ea: `0x18002b295`
- end: `0x18002b2ce`
- name: `_PluginEngine::RemoveProvisioning_::_1_::catch$32`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b2a9`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::RemoveProvisioning_::_1_::catch_32(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 296),
                           (void *)0x1AF,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b295  mov     [rsp+arg_8], rdx
0x18002b29a  push    rbp
0x18002b29b  sub     rsp, 20h
0x18002b29f  mov     rbp, rdx
0x18002b2a2  mov     rcx, [rbp+128h]; this
0x18002b2a9  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b2b0  mov     edx, 1AFh; void *
0x18002b2b5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b2ba  mov     [rbp+40h], eax
0x18002b2bd  mov     rax, 0
0x18002b2c7  add     rsp, 20h
0x18002b2cb  pop     rbp
0x18002b2cc  retn
```
