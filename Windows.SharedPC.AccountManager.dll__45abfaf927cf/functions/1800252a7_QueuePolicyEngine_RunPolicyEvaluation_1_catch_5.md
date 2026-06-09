# _QueuePolicyEngine::RunPolicyEvaluation_::_1_::catch$5

- ea: `0x1800252a7`
- end: `0x1800252e0`
- name: `_QueuePolicyEngine::RunPolicyEvaluation_::_1_::catch$5`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x1800252bb`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\queuepolicyengine.cpp`

## pseudocode

```c
__int64 __fastcall QueuePolicyEngine::RunPolicyEvaluation_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 504),
                           (void *)0x39,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\queuepolicyengine.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800252a7  mov     [rsp+arg_8], rdx
0x1800252ac  push    rbp
0x1800252ad  sub     rsp, 40h
0x1800252b1  mov     rbp, rdx
0x1800252b4  mov     rcx, [rbp+1F8h]; this
0x1800252bb  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800252c2  mov     edx, 39h ; '9'; void *
0x1800252c7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800252cc  mov     [rbp+40h], eax
0x1800252cf  mov     rax, 0
0x1800252d9  add     rsp, 40h
0x1800252dd  pop     rbp
0x1800252de  retn
```
