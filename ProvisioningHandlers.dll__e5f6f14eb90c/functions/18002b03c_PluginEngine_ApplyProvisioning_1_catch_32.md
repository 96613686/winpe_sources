# _PluginEngine::ApplyProvisioning_::_1_::catch$32

- ea: `0x18002b03c`
- end: `0x18002b075`
- name: `_PluginEngine::ApplyProvisioning_::_1_::catch$32`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c798`

## string_xrefs

- `0x18002b050`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::ApplyProvisioning_::_1_::catch_32(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 376),
                           (void *)0x177,
                           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002b03c  mov     [rsp+arg_8], rdx
0x18002b041  push    rbp
0x18002b042  sub     rsp, 40h
0x18002b046  mov     rbp, rdx
0x18002b049  mov     rcx, [rbp+178h]; this
0x18002b050  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002b057  mov     edx, 177h; void *
0x18002b05c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002b061  mov     [rbp+58h], eax
0x18002b064  mov     rax, 0
0x18002b06e  add     rsp, 40h
0x18002b072  pop     rbp
0x18002b073  retn
```
