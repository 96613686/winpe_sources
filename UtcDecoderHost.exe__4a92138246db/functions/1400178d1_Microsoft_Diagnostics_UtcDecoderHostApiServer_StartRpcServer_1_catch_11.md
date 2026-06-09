# _Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer_::_1_::catch$11

- ea: `0x1400178d1`
- end: `0x140017907`
- name: `_Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer_::_1_::catch$11`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140011084`

## string_xrefs

- `0x1400178e2`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer_::_1_::catch_11(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x26,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1400178d1  mov     [rsp+arg_8], rdx
0x1400178d6  push    rbp
0x1400178d7  sub     rsp, 20h
0x1400178db  mov     rbp, rdx
0x1400178de  mov     rcx, [rbp+58h]; this
0x1400178e2  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x1400178e9  mov     edx, 26h ; '&'; void *
0x1400178ee  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1400178f3  mov     [rbp+20h], eax
0x1400178f6  mov     rax, 0
0x140017900  add     rsp, 20h
0x140017904  pop     rbp
0x140017905  retn
```
