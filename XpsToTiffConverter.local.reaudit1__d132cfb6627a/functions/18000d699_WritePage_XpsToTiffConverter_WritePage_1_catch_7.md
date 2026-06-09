# _WritePage::XpsToTiffConverter::WritePage_::_1_::catch$7

- ea: `0x18000d699`
- end: `0x18000d6d2`
- name: `_WritePage::XpsToTiffConverter::WritePage_::_1_::catch$7`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a848`

## pseudocode

```c
__int64 __fastcall WritePage::XpsToTiffConverter::WritePage_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 312),
                           (void *)0x54,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpsto"
                                         "tiffconverter.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d699  mov     [rsp+arg_8], rdx
0x18000d69e  push    rbp
0x18000d69f  sub     rsp, 50h
0x18000d6a3  mov     rbp, rdx
0x18000d6a6  mov     rcx, [rbp+138h]; this
0x18000d6ad  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000d6b4  mov     edx, 54h ; 'T'; void *
0x18000d6b9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d6be  mov     [rbp+50h], eax
0x18000d6c1  mov     rax, 0
0x18000d6cb  add     rsp, 50h
0x18000d6cf  pop     rbp
0x18000d6d0  retn
```
