# __lambda_ff9fab94e839700dcda8ee6d193e4200_::operator()_::_1_::catch$2

- ea: `0x180023b7d`
- end: `0x180023bb1`
- name: `__lambda_ff9fab94e839700dcda8ee6d193e4200_::operator()_::_1_::catch$2`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180016114`

## string_xrefs

- `0x180023b8e`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_ff9fab94e839700dcda8ee6d193e4200_::operator()_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x507,
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180023b7d  mov     [rsp+arg_8], rdx
0x180023b82  push    rbp
0x180023b83  sub     rsp, 20h
0x180023b87  mov     rbp, rdx
0x180023b8a  mov     rcx, [rbp+48h]; this
0x180023b8e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180023b95  mov     edx, 507h; void *
0x180023b9a  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180023b9f  nop
0x180023ba0  mov     rax, 0
0x180023baa  add     rsp, 20h
0x180023bae  pop     rbp
0x180023baf  retn
```
