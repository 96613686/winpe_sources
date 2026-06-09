# _RemovePackage_::_1_::catch$0

- ea: `0x14000e4df`
- end: `0x14000e515`
- name: `_RemovePackage_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400076f4`

## pseudocode

```c
__int64 __fastcall RemovePackage_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xB0,
                           (int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000e4df  mov     [rsp+arg_8], rdx
0x14000e4e4  push    rbp
0x14000e4e5  sub     rsp, 20h
0x14000e4e9  mov     rbp, rdx
0x14000e4ec  mov     rcx, [rbp+28h]; this
0x14000e4f0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000e4f7  mov     edx, 0B0h; void *
0x14000e4fc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000e501  mov     [rbp+30h], eax
0x14000e504  mov     rax, 0
0x14000e50e  add     rsp, 20h
0x14000e512  pop     rbp
0x14000e513  retn
```
