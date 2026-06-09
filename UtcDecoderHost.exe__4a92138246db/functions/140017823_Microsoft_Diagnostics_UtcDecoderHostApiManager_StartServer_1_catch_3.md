# _Microsoft::Diagnostics::UtcDecoderHostApiManager::StartServer_::_1_::catch$3

- ea: `0x140017823`
- end: `0x140017859`
- name: `_Microsoft::Diagnostics::UtcDecoderHostApiManager::StartServer_::_1_::catch$3`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140011084`

## string_xrefs

- `0x140017834`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::StartServer_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x31,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140017823  mov     [rsp+arg_8], rdx
0x140017828  push    rbp
0x140017829  sub     rsp, 20h
0x14001782d  mov     rbp, rdx
0x140017830  mov     rcx, [rbp+38h]; this
0x140017834  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x14001783b  mov     edx, 31h ; '1'; void *
0x140017840  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140017845  mov     [rbp+40h], eax
0x140017848  mov     rax, 0
0x140017852  add     rsp, 20h
0x140017856  pop     rbp
0x140017857  retn
```
