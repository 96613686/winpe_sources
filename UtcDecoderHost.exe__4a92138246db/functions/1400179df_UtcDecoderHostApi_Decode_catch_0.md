# UtcDecoderHostApi_Decode$catch$0

- ea: `0x1400179df`
- end: `0x140017a15`
- name: `UtcDecoderHostApi_Decode$catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140011084`

## string_xrefs

- `0x1400179f0`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiforwarders.cpp`

## pseudocode

```c
__int64 __fastcall UtcDecoderHostApi_Decode_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x1C,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiforwarders.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1400179df  mov     [rsp+arg_8], rdx
0x1400179e4  push    rbp
0x1400179e5  sub     rsp, 30h
0x1400179e9  mov     rbp, rdx
0x1400179ec  mov     rcx, [rbp+48h]; this
0x1400179f0  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\service"...
0x1400179f7  mov     edx, 1Ch; void *
0x1400179fc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140017a01  mov     [rbp+30h], eax
0x140017a04  mov     rax, 0
0x140017a0e  add     rsp, 30h
0x140017a12  pop     rbp
0x140017a13  retn
```
