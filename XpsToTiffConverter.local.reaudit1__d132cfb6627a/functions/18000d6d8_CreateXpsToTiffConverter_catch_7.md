# CreateXpsToTiffConverter$catch$7

- ea: `0x18000d6d8`
- end: `0x18000d70e`
- name: `CreateXpsToTiffConverter$catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a848`

## pseudocode

```c
__int64 __fastcall CreateXpsToTiffConverter_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x8C,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpsto"
                                         "tiffconverter.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d6d8  mov     [rsp+arg_8], rdx
0x18000d6dd  push    rbp
0x18000d6de  sub     rsp, 20h
0x18000d6e2  mov     rbp, rdx
0x18000d6e5  mov     rcx, [rbp+28h]; this
0x18000d6e9  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000d6f0  mov     edx, 8Ch; void *
0x18000d6f5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d6fa  mov     [rbp+30h], eax
0x18000d6fd  mov     rax, 0
0x18000d707  add     rsp, 20h
0x18000d70b  pop     rbp
0x18000d70c  retn
```
