# _ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch$8

- ea: `0x180025359`
- end: `0x180025392`
- name: `_ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x18002536d`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\exemptionpolicyengine.cpp`

## pseudocode

```c
__int64 __fastcall ExemptionPolicyEngine::RunPolicyEvaluation_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 488),
                           (void *)0x31,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\exemptionpolicyengine.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180025359  mov     [rsp+arg_8], rdx
0x18002535e  push    rbp
0x18002535f  sub     rsp, 20h
0x180025363  mov     rbp, rdx
0x180025366  mov     rcx, [rbp+1E8h]; this
0x18002536d  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\sharedpc\\accountma"...
0x180025374  mov     edx, 31h ; '1'; void *
0x180025379  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002537e  mov     [rbp+20h], eax
0x180025381  mov     rax, 0
0x18002538b  add     rsp, 20h
0x18002538f  pop     rbp
0x180025390  retn
```
