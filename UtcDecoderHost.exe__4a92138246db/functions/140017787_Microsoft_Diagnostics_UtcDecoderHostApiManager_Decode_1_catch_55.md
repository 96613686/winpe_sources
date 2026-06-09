# _Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_1_::catch$55

- ea: `0x140017787`
- end: `0x1400177c0`
- name: `_Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_1_::catch$55`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140011084`

## string_xrefs

- `0x14001779b`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode_::_1_::catch_55(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 632),
                           (void *)0x98,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140017787  mov     [rsp+arg_8], rdx
0x14001778c  push    rbp
0x14001778d  sub     rsp, 30h
0x140017791  mov     rbp, rdx
0x140017794  mov     rcx, [rbp+278h]; this
0x14001779b  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x1400177a2  mov     edx, 98h; void *
0x1400177a7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1400177ac  mov     [rbp+38h], eax
0x1400177af  mov     rax, 0
0x1400177b9  add     rsp, 30h
0x1400177bd  pop     rbp
0x1400177be  retn
```
