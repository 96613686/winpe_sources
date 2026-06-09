# _invalid_parameter_internal

- ea: `0x14000bea4`
- end: `0x14000bf5b`
- name: `_invalid_parameter_internal`
- size: `183`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, __crt_cached_ptd_host *)`
- caller_count: `26`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000be08`
- `0x14000c9e4`
- `0x14000cc98`
- `0x14000d404`
- `0x14000d608`
- `0x14000d814`
- `0x14000da18`
- `0x14000dc24`
- `0x14000de28`
- `0x14000e8d4`
- `0x14000ec44`
- `0x14000ef08`
- `0x14000f090`
- `0x140010388`
- `0x140010784`
- `0x1400109d8`
- `0x1400141d0`
- `0x140014650`
- `0x140014ae8`
- `0x140015160`
- `0x140018a64`
- `0x140019f30`
- `0x140019fac`
- `0x14001aa38`
- `0x14001ab58`
- `0x14001bdac`

## callees

- `0x14000bbd8`
- `0x14000bc44`
- `0x14000bea4`
- `0x14000bf7c`
- `0x140024c80`

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
                                                                                                   &qword_14003C868,
                                                                                                   a6),
                                                                                      _security_cookie & 0x3F);
  if ( !v13 )
    invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  return v13(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x14000bea4  mov     [rsp+arg_0], rbx
0x14000bea9  mov     [rsp+arg_8], rbp
0x14000beae  mov     [rsp+arg_10], rsi
0x14000beb3  push    rdi
0x14000beb4  sub     rsp, 30h
0x14000beb8  mov     rbp, rcx
0x14000bebb  mov     ebx, r9d
0x14000bebe  mov     rcx, [rsp+38h+arg_28]; this
0x14000bec3  mov     rdi, r8
0x14000bec6  mov     rsi, rdx
0x14000bec9  call    ?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd_noexit(void)
0x14000bece  test    rax, rax
0x14000bed1  jz      short loc_14000BF0F
0x14000bed3  mov     rax, [rax+3B8h]
0x14000beda  test    rax, rax
0x14000bedd  jz      short loc_14000BF0F
0x14000bedf  mov     r9d, ebx
0x14000bee2  mov     r8, rdi
0x14000bee5  mov     rdx, rsi
0x14000bee8  mov     rcx, [rsp+38h+arg_20]
0x14000beed  mov     [rsp+38h+Reserved], rcx
0x14000bef2  mov     rcx, rbp
0x14000bef5  call    _guard_dispatch_icall
0x14000befa  mov     rbx, [rsp+38h+arg_0]
0x14000beff  mov     rbp, [rsp+38h+arg_8]
0x14000bf04  mov     rsi, [rsp+38h+arg_10]
0x14000bf09  add     rsp, 30h
0x14000bf0d  pop     rdi
0x14000bf0e  retn
0x14000bf0f  mov     rdx, [rsp+38h+arg_28]
0x14000bf14  lea     rcx, qword_14003C868
0x14000bf1b  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x14000bf20  mov     r9d, ebx; LineNo
0x14000bf23  mov     r8, rdi; FileName
0x14000bf26  mov     rdx, rsi; FunctionName
0x14000bf29  mov     r10, [rax]
0x14000bf2c  mov     rax, cs:__security_cookie
0x14000bf33  xor     r10, rax
0x14000bf36  mov     ecx, eax
0x14000bf38  and     ecx, 3Fh
0x14000bf3b  ror     r10, cl
0x14000bf3e  test    r10, r10
0x14000bf41  jz      short loc_14000BF48
0x14000bf43  mov     rax, r10
0x14000bf46  jmp     short loc_14000BEE8
0x14000bf48  mov     rax, [rsp+38h+arg_20]
0x14000bf4d  mov     rcx, rbp; Expression
0x14000bf50  mov     [rsp+38h+Reserved], rax; Reserved
0x14000bf55  call    _invoke_watson
```
