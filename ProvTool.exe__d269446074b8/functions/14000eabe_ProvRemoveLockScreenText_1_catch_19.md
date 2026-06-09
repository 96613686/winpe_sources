# _ProvRemoveLockScreenText_::_1_::catch$19

- ea: `0x14000eabe`
- end: `0x14000eaf7`
- name: `_ProvRemoveLockScreenText_::_1_::catch$19`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400076f4`

## pseudocode

```c
__int64 __fastcall ProvRemoveLockScreenText_::_1_::catch_19(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x70,
                           (int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000eabe  mov     [rsp+arg_8], rdx
0x14000eac3  push    rbp
0x14000eac4  sub     rsp, 40h
0x14000eac8  mov     rbp, rdx
0x14000eacb  mov     rcx, [rbp+0D8h]; this
0x14000ead2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x14000ead9  mov     edx, 70h ; 'p'; void *
0x14000eade  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000eae3  mov     [rbp+40h], eax
0x14000eae6  mov     rax, 0
0x14000eaf0  add     rsp, 40h
0x14000eaf4  pop     rbp
0x14000eaf5  retn
```
