# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180008f74`
- end: `0x180009021`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008dd8`

## callees

- `0x18000a2f8`
- `0x18000b200`
- `0x1800119c2`
- `0x180011ab0`

## string_xrefs

- `0x180008fbd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180008f74  mov     [rsp+arg_10], rbx
0x180008f79  mov     [rsp+arg_18], rsi
0x180008f7e  push    rdi
0x180008f7f  mov     eax, 1520h
0x180008f84  call    _alloca_probe
0x180008f89  sub     rsp, rax
0x180008f8c  mov     rbx, [rsp+1528h+arg_28]
0x180008f94  mov     esi, edx
0x180008f96  mov     rdi, rcx
0x180008f99  xor     edx, edx; Val
0x180008f9b  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180008fa3  mov     r8d, 98h; Size
0x180008fa9  call    memset_0
0x180008fae  xor     ecx, ecx
0x180008fb0  lea     rax, [rsp+1528h+var_14A8]
0x180008fb8  mov     [rsp+1528h+var_14B0], rax
0x180008fbd  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008fc4  mov     [rsp+1528h+var_14B8], ecx
0x180008fc8  lea     rax, [rsp+1528h+var_1408]
0x180008fd0  mov     [rsp+1528h+var_14C8], rax
0x180008fd5  xor     r9d, r9d
0x180008fd8  lea     rax, [rsp+1528h+var_1008]
0x180008fe0  mov     edx, esi
0x180008fe2  mov     [rsp+1528h+var_14D8], rax
0x180008fe7  mov     rax, [rsp+1528h+arg_30]
0x180008fef  mov     [rsp+1528h+var_14E8], rcx
0x180008ff4  mov     [rsp+1528h+var_14F0], rax
0x180008ff9  mov     [rsp+1528h+var_14F8], 3
0x180009001  mov     [rsp+1528h+var_1500], rbx
0x180009006  mov     [rsp+1528h+var_1508], rcx
0x18000900b  mov     rcx, rdi
0x18000900e  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180009013  lea     rcx, [rsp+1528h+var_14A8]; this
0x18000901b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
