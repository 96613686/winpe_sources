# _PolicyEngineController::RuntimeClassInitialize_::_1_::catch$0

- ea: `0x180024fa2`
- end: `0x180024fd8`
- name: `_PolicyEngineController::RuntimeClassInitialize_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c210`

## string_xrefs

- `0x180024fb3`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`

## pseudocode

```c
__int64 __fastcall PolicyEngineController::RuntimeClassInitialize_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x20,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180024fa2  mov     [rsp+arg_8], rdx
0x180024fa7  push    rbp
0x180024fa8  sub     rsp, 20h
0x180024fac  mov     rbp, rdx
0x180024faf  mov     rcx, [rbp+28h]; this
0x180024fb3  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x180024fba  mov     edx, 20h ; ' '; void *
0x180024fbf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180024fc4  mov     [rbp+30h], eax
0x180024fc7  mov     rax, 0
0x180024fd1  add     rsp, 20h
0x180024fd5  pop     rbp
0x180024fd6  retn
```
