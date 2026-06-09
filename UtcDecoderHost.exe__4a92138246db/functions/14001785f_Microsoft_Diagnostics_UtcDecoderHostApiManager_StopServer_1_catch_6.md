# _Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer_::_1_::catch$6

- ea: `0x14001785f`
- end: `0x140017895`
- name: `_Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer_::_1_::catch$6`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140011084`

## string_xrefs

- `0x140017870`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::StopServer_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x48,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14001785f  mov     [rsp+arg_8], rdx
0x140017864  push    rbp
0x140017865  sub     rsp, 20h
0x140017869  mov     rbp, rdx
0x14001786c  mov     rcx, [rbp+28h]; this
0x140017870  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x140017877  mov     edx, 48h ; 'H'; void *
0x14001787c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140017881  mov     [rbp+30h], eax
0x140017884  mov     rax, 0
0x14001788e  add     rsp, 20h
0x140017892  pop     rbp
0x140017893  retn
```
