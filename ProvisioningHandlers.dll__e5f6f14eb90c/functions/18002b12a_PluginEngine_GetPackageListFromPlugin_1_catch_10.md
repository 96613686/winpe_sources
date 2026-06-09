# _PluginEngine::GetPackageListFromPlugin_::_1_::catch$10

- ea: `0x18002b12a`
- end: `0x18002b163`
- name: `_PluginEngine::GetPackageListFromPlugin_::_1_::catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b13e`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::GetPackageListFromPlugin_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x85,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b12a  mov     [rsp+arg_8], rdx
0x18002b12f  push    rbp
0x18002b130  sub     rsp, 20h
0x18002b134  mov     rbp, rdx
0x18002b137  mov     rcx, [rbp+0F8h]; this
0x18002b13e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b145  mov     edx, 85h; void *
0x18002b14a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b14f  mov     [rbp+20h], eax
0x18002b152  mov     rax, 0
0x18002b15c  add     rsp, 20h
0x18002b160  pop     rbp
0x18002b161  retn
```
