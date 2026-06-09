# _Microsoft::Diagnostics::Utils::String::ReplaceAllImpl_wchar_t__::_1_::catch$0

- ea: `0x140017604`
- end: `0x140017640`
- name: `_Microsoft::Diagnostics::Utils::String::ReplaceAllImpl_wchar_t__::_1_::catch$0`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011084`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::String::ReplaceAllImpl_wchar_t__::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 200) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 168),
                            (void *)0x45C,
                            (int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x140017604  mov     [rsp+arg_8], rdx
0x140017609  push    rbp
0x14001760a  sub     rsp, 40h
0x14001760e  mov     rbp, rdx
0x140017611  mov     rcx, [rbp+0A8h]; this
0x140017618  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x14001761f  mov     edx, 45Ch; void *
0x140017624  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140017629  mov     [rbp+0C8h], eax
0x14001762f  mov     rax, 0
0x140017639  add     rsp, 40h
0x14001763d  pop     rbp
0x14001763e  retn
```
