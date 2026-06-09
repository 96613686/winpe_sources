# _Windows::UI::Composition::EffectInstance::GetBounds_::_1_::catch$4

- ea: `0x18002c5f0`
- end: `0x18002c629`
- name: `_Windows::UI::Composition::EffectInstance::GetBounds_::_1_::catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800266dc`

## string_xrefs

- `0x18002c604`: `onecoreuap\windows\dwm\effects\compiler\effectinstance.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectInstance::GetBounds_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x18E,
                           (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectinstance.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002c5f0  mov     [rsp+arg_8], rdx
0x18002c5f5  push    rbp
0x18002c5f6  sub     rsp, 30h
0x18002c5fa  mov     rbp, rdx
0x18002c5fd  mov     rcx, [rbp+0C8h]; this
0x18002c604  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18002c60b  mov     edx, 18Eh; void *
0x18002c610  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c615  mov     [rbp+50h], eax
0x18002c618  mov     rax, 0
0x18002c622  add     rsp, 30h
0x18002c626  pop     rbp
0x18002c627  retn
```
