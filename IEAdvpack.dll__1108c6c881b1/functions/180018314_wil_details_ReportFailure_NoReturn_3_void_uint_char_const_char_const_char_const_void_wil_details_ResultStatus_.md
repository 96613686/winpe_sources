# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180018314`
- end: `0x1800183c1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800180f8`

## callees

- `0x1800199e0`
- `0x18001af78`
- `0x18001b94e`
- `0x18001ba10`

## string_xrefs

- `0x18001835d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+80h] [rbp-14A8h] BYREF

  memset_0(v10, 0, 0x98u);
  wil::details::LogFailure(a1, a2, "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h", 0, 0, a6, 3, a7, 0);
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x180018314  mov     [rsp+arg_10], rbx
0x180018319  mov     [rsp+arg_18], rsi
0x18001831e  push    rdi
0x18001831f  mov     eax, 1520h
0x180018324  call    _alloca_probe
0x180018329  sub     rsp, rax
0x18001832c  mov     rbx, [rsp+1528h+arg_28]
0x180018334  mov     esi, edx
0x180018336  mov     rdi, rcx
0x180018339  xor     edx, edx; Val
0x18001833b  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180018343  mov     r8d, 98h; Size
0x180018349  call    memset_0
0x18001834e  xor     ecx, ecx
0x180018350  lea     rax, [rsp+1528h+var_14A8]
0x180018358  mov     [rsp+1528h+var_14B0], rax
0x18001835d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018364  mov     [rsp+1528h+var_14B8], ecx
0x180018368  lea     rax, [rsp+1528h+var_1408]
0x180018370  mov     [rsp+1528h+var_14C8], rax
0x180018375  xor     r9d, r9d
0x180018378  lea     rax, [rsp+1528h+var_1008]
0x180018380  mov     edx, esi
0x180018382  mov     [rsp+1528h+var_14D8], rax
0x180018387  mov     rax, [rsp+1528h+arg_30]
0x18001838f  mov     [rsp+1528h+var_14E8], rcx
0x180018394  mov     [rsp+1528h+var_14F0], rax
0x180018399  mov     [rsp+1528h+var_14F8], 3
0x1800183a1  mov     [rsp+1528h+var_1500], rbx
0x1800183a6  mov     [rsp+1528h+var_1508], rcx
0x1800183ab  mov     rcx, rdi
0x1800183ae  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x1800183b3  lea     rcx, [rsp+1528h+var_14A8]; this
0x1800183bb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
