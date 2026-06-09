# _invalid_parameter_internal

- ea: `0x180007b48`
- end: `0x180007bff`
- name: `_invalid_parameter_internal`
- size: `183`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, __crt_cached_ptd_host *)`
- caller_count: `230`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007aac`
- `0x180015c50`
- `0x180015d70`
- `0x18001b1e4`
- `0x18001b300`
- `0x18001c000`
- `0x18001c190`
- `0x18001c5c0`
- `0x18001d5bc`
- `0x18001d638`
- `0x18001e3a4`
- `0x18001e680`
- `0x18001ee1c`
- `0x18001f0f8`
- `0x180021b48`
- `0x180022260`
- `0x180022380`
- `0x180033748`
- `0x1800337dc`
- `0x180033870`
- `0x180033904`
- `0x180033998`
- `0x180033a2c`
- `0x180033ac0`
- `0x180033bc0`
- `0x180033cc4`
- `0x180033e74`
- `0x18003402c`
- `0x1800341f8`
- `0x1800343cc`
- `0x18003457c`
- `0x180034734`
- `0x1800347c0`
- `0x180034a04`
- `0x180034b10`
- `0x180034c1c`
- `0x180034d28`
- `0x180034e94`
- `0x180034f9c`
- `0x1800350a4`
- `0x1800351b0`
- `0x18003531c`
- `0x180035428`
- `0x180035534`
- `0x180035640`
- `0x1800357ac`
- `0x1800358b0`
- `0x1800359dc`
- `0x180035ae4`
- `0x180035bec`

## callees

- `0x1800077b4`
- `0x180007894`
- `0x180007b48`
- `0x180007c50`
- `0x180060430`

## pseudocode

```c
__int64 __fastcall invalid_parameter_internal(
        wchar_t *Expression,
        wchar_t *FunctionName,
        wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved,
        __crt_cached_ptd_host *a6)
{
  struct __acrt_ptd *raw_ptd_noexit; // rax
  __int64 (__fastcall *v11)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t); // rax
  __int64 (__fastcall *v13)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t); // r10

  raw_ptd_noexit = __crt_cached_ptd_host::get_raw_ptd_noexit(a6);
  if ( raw_ptd_noexit )
  {
    v11 = (__int64 (__fastcall *)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t))*((_QWORD *)raw_ptd_noexit + 119);
    if ( v11 )
      return v11(Expression, FunctionName, FileName, LineNo, Reserved);
  }
  v13 = (__int64 (__fastcall *)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t))__ROR8__(
                                                                                      _security_cookie
                                                                                    ^ *(_QWORD *)__crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
                                                                                                   &qword_18007BEC8,
                                                                                                   a6),
                                                                                      _security_cookie & 0x3F);
  if ( !v13 )
    invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  return v13(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x180007b48  mov     [rsp+arg_0], rbx
0x180007b4d  mov     [rsp+arg_8], rbp
0x180007b52  mov     [rsp+arg_10], rsi
0x180007b57  push    rdi
0x180007b58  sub     rsp, 30h
0x180007b5c  mov     rbp, rcx
0x180007b5f  mov     ebx, r9d
0x180007b62  mov     rcx, [rsp+38h+arg_28]; this
0x180007b67  mov     rdi, r8
0x180007b6a  mov     rsi, rdx
0x180007b6d  call    ?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd_noexit(void)
0x180007b72  test    rax, rax
0x180007b75  jz      short loc_180007BB3
0x180007b77  mov     rax, [rax+3B8h]
0x180007b7e  test    rax, rax
0x180007b81  jz      short loc_180007BB3
0x180007b83  mov     r9d, ebx
0x180007b86  mov     r8, rdi
0x180007b89  mov     rdx, rsi
0x180007b8c  mov     rcx, [rsp+38h+arg_20]
0x180007b91  mov     [rsp+38h+Reserved], rcx
0x180007b96  mov     rcx, rbp
0x180007b99  call    _guard_dispatch_icall
0x180007b9e  mov     rbx, [rsp+38h+arg_0]
0x180007ba3  mov     rbp, [rsp+38h+arg_8]
0x180007ba8  mov     rsi, [rsp+38h+arg_10]
0x180007bad  add     rsp, 30h
0x180007bb1  pop     rdi
0x180007bb2  retn
0x180007bb3  mov     rdx, [rsp+38h+arg_28]
0x180007bb8  lea     rcx, qword_18007BEC8
0x180007bbf  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x180007bc4  mov     r9d, ebx; LineNo
0x180007bc7  mov     r8, rdi; FileName
0x180007bca  mov     rdx, rsi; FunctionName
0x180007bcd  mov     r10, [rax]
0x180007bd0  mov     rax, cs:__security_cookie
0x180007bd7  xor     r10, rax
0x180007bda  mov     ecx, eax
0x180007bdc  and     ecx, 3Fh
0x180007bdf  ror     r10, cl
0x180007be2  test    r10, r10
0x180007be5  jz      short loc_180007BEC
0x180007be7  mov     rax, r10
0x180007bea  jmp     short loc_180007B8C
0x180007bec  mov     rax, [rsp+38h+arg_20]
0x180007bf1  mov     rcx, rbp; Expression
0x180007bf4  mov     [rsp+38h+Reserved], rax; Reserved
0x180007bf9  call    _invoke_watson
```
