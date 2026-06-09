# _BingFilterDS::UpdateCandidateCache_::_1_::catch$7

- ea: `0x18000cf6e`
- end: `0x18000cf96`
- name: `_BingFilterDS::UpdateCandidateCache_::_1_::catch$7`
- size: `40`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009e10`

## pseudocode

```c
__int64 __fastcall BingFilterDS::UpdateCandidateCache_::_1_::catch_7(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[11], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x18000cf6e  mov     [rsp+arg_8], rdx
0x18000cf73  push    rbp
0x18000cf74  sub     rsp, 20h
0x18000cf78  mov     rbp, rdx
0x18000cf7b  mov     rcx, [rbp+58h]; this
0x18000cf7f  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18000cf84  nop
0x18000cf85  mov     rax, 0
0x18000cf8f  add     rsp, 20h
0x18000cf93  pop     rbp
0x18000cf94  retn
```
