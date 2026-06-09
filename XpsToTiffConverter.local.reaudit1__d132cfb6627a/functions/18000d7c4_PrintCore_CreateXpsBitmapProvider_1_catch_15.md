# _PrintCore::CreateXpsBitmapProvider_::_1_::catch$15

- ea: `0x18000d7c4`
- end: `0x18000d7fd`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::catch$15`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a848`

## pseudocode

```c
__int64 __fastcall PrintCore::CreateXpsBitmapProvider_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x89,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpsbitmapprovider\\xpspag"
                                         "ebitmapprovider.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d7c4  mov     [rsp+arg_8], rdx
0x18000d7c9  push    rbp
0x18000d7ca  sub     rsp, 50h
0x18000d7ce  mov     rbp, rdx
0x18000d7d1  mov     rcx, [rbp+0C8h]; this
0x18000d7d8  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000d7df  mov     edx, 89h; void *
0x18000d7e4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d7e9  mov     [rbp+50h], eax
0x18000d7ec  mov     rax, 0
0x18000d7f6  add     rsp, 50h
0x18000d7fa  pop     rbp
0x18000d7fb  retn
```
