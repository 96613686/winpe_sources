# _PrintCore::CreateXpsBitmapProvider_::_1_::catch$15

- ea: `0x180010705`
- end: `0x180010737`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::catch$15`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f028`

## pseudocode

```c
__int64 __fastcall PrintCore::CreateXpsBitmapProvider_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x89,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180010705  mov     [rsp+arg_8], rdx
0x18001070a  push    rbp
0x18001070b  sub     rsp, 50h
0x18001070f  mov     rbp, rdx
0x180010712  mov     rcx, [rbp+0C8h]; this
0x180010719  mov     edx, 89h; void *
0x18001071e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180010723  mov     [rbp+50h], eax
0x180010726  mov     rax, 0
0x180010730  add     rsp, 50h
0x180010734  pop     rbp
0x180010735  retn
```
