# _invalid_parameter_internal

- ea: `0x1800073e8`
- end: `0x18000749f`
- name: `_invalid_parameter_internal`
- size: `183`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, __crt_cached_ptd_host *)`
- caller_count: `230`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000734c`
- `0x1800154f0`
- `0x180015610`
- `0x18001aa84`
- `0x18001aba0`
- `0x18001b8a0`
- `0x18001ba30`
- `0x18001be60`
- `0x18001ce5c`
- `0x18001ced8`
- `0x18001dc44`
- `0x18001df20`
- `0x18001e6bc`
- `0x18001e998`
- `0x1800213e8`
- `0x180021b00`
- `0x180021c20`
- `0x180033468`
- `0x1800334fc`
- `0x180033590`
- `0x180033624`
- `0x1800336b8`
- `0x18003374c`
- `0x1800337e0`
- `0x1800338e0`
- `0x1800339e4`
- `0x180033b94`
- `0x180033d4c`
- `0x180033f18`
- `0x1800340ec`
- `0x18003429c`
- `0x180034454`
- `0x1800344e0`
- `0x180034724`
- `0x180034830`
- `0x18003493c`
- `0x180034a48`
- `0x180034bb4`
- `0x180034cbc`
- `0x180034dc4`
- `0x180034ed0`
- `0x18003503c`
- `0x180035148`
- `0x180035254`
- `0x180035360`
- `0x1800354cc`
- `0x1800355d0`
- `0x1800356fc`
- `0x180035804`
- `0x18003590c`

## callees

- `0x180007054`
- `0x180007134`
- `0x1800073e8`
- `0x1800074f0`
- `0x180060150`

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
                                                                                                   &qword_180078418,
                                                                                                   a6),
                                                                                      _security_cookie & 0x3F);
  if ( !v13 )
    invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  return v13(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x1800073e8  mov     [rsp+arg_0], rbx
0x1800073ed  mov     [rsp+arg_8], rbp
0x1800073f2  mov     [rsp+arg_10], rsi
0x1800073f7  push    rdi
0x1800073f8  sub     rsp, 30h
0x1800073fc  mov     rbp, rcx
0x1800073ff  mov     ebx, r9d
0x180007402  mov     rcx, [rsp+38h+arg_28]; this
0x180007407  mov     rdi, r8
0x18000740a  mov     rsi, rdx
0x18000740d  call    ?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd_noexit(void)
0x180007412  test    rax, rax
0x180007415  jz      short loc_180007453
0x180007417  mov     rax, [rax+3B8h]
0x18000741e  test    rax, rax
0x180007421  jz      short loc_180007453
0x180007423  mov     r9d, ebx
0x180007426  mov     r8, rdi
0x180007429  mov     rdx, rsi
0x18000742c  mov     rcx, [rsp+38h+arg_20]
0x180007431  mov     [rsp+38h+Reserved], rcx
0x180007436  mov     rcx, rbp
0x180007439  call    _guard_dispatch_icall
0x18000743e  mov     rbx, [rsp+38h+arg_0]
0x180007443  mov     rbp, [rsp+38h+arg_8]
0x180007448  mov     rsi, [rsp+38h+arg_10]
0x18000744d  add     rsp, 30h
0x180007451  pop     rdi
0x180007452  retn
0x180007453  mov     rdx, [rsp+38h+arg_28]
0x180007458  lea     rcx, qword_180078418
0x18000745f  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x180007464  mov     r9d, ebx; LineNo
0x180007467  mov     r8, rdi; FileName
0x18000746a  mov     rdx, rsi; FunctionName
0x18000746d  mov     r10, [rax]
0x180007470  mov     rax, cs:__security_cookie
0x180007477  xor     r10, rax
0x18000747a  mov     ecx, eax
0x18000747c  and     ecx, 3Fh
0x18000747f  ror     r10, cl
0x180007482  test    r10, r10
0x180007485  jz      short loc_18000748C
0x180007487  mov     rax, r10
0x18000748a  jmp     short loc_18000742C
0x18000748c  mov     rax, [rsp+38h+arg_20]
0x180007491  mov     rcx, rbp; Expression
0x180007494  mov     [rsp+38h+Reserved], rax; Reserved
0x180007499  call    _invoke_watson
```
