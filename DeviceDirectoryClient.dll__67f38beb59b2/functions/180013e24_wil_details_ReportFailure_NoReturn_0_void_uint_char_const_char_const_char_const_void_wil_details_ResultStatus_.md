# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180013e24`
- end: `0x180013f2c`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `264`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013c2c`

## callees

- `0x180002fc0`
- `0x18000a9e4`
- `0x18000e298`
- `0x180013e24`
- `0x180028ad0`
- `0x18002a010`

## string_xrefs

- `0x180013e78`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  bool v8; // si
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v11[4104]; // [rsp+520h] [rbp-1008h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(v10, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    5619,
    "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    0,
    a7,
    0);
  if ( (v10[4] & 1) == 0 )
  {
    if ( v8 )
      ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v10, v11);
    if ( wil::details::g_pfnThrowResultException )
      wil::details::g_pfnThrowResultException((const struct wil::FailureInfo *)v10);
  }
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x180013e24  mov     [rsp+arg_8], rbx
0x180013e29  mov     [rsp+arg_10], rsi
0x180013e2e  push    rdi
0x180013e2f  mov     eax, 1520h
0x180013e34  call    _alloca_probe
0x180013e39  sub     rsp, rax
0x180013e3c  cmp     cs:g_pfnThrowPlatformException, 0
0x180013e44  mov     rdi, rcx
0x180013e47  mov     rbx, [rsp+1528h+arg_28]
0x180013e4f  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180013e57  setnz   sil
0x180013e5b  mov     r8d, 98h; Size
0x180013e61  xor     edx, edx; Val
0x180013e63  call    memset_0
0x180013e68  lea     rax, [rsp+1528h+var_14A8]
0x180013e70  xor     r9d, r9d
0x180013e73  mov     [rsp+1528h+var_14B0], rax
0x180013e78  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013e7f  mov     [rsp+1528h+var_14B8], 0
0x180013e87  lea     rax, [rsp+1528h+var_1408]
0x180013e8f  mov     [rsp+1528h+var_14C8], rax
0x180013e94  mov     edx, 15F3h
0x180013e99  lea     rax, [rsp+1528h+var_1008]
0x180013ea1  mov     rcx, rdi
0x180013ea4  mov     [rsp+1528h+var_14D8], rax
0x180013ea9  mov     rax, [rsp+1528h+arg_30]
0x180013eb1  mov     [rsp+1528h+var_14E8], 0
0x180013eba  mov     [rsp+1528h+var_14F0], rax
0x180013ebf  mov     [rsp+1528h+var_14F8], 0
0x180013ec7  mov     [rsp+1528h+var_1500], rbx
0x180013ecc  mov     [rsp+1528h+var_1508], 0
0x180013ed5  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180013eda  test    [rsp+1528h+var_14A4], 1
0x180013ee2  jnz     short loc_180013F1E
0x180013ee4  test    sil, sil
0x180013ee7  jz      short loc_180013F05
0x180013ee9  mov     rax, cs:g_pfnThrowPlatformException
0x180013ef0  lea     rdx, [rsp+1528h+var_1008]
0x180013ef8  lea     rcx, [rsp+1528h+var_14A8]
0x180013f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f05  mov     rax, cs:?g_pfnThrowResultException@details@wil@@3P6AXAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnThrowResultException)(wil::FailureInfo const &)
0x180013f0c  test    rax, rax
0x180013f0f  jz      short loc_180013F1E
0x180013f11  lea     rcx, [rsp+1528h+var_14A8]
0x180013f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1e  lea     rcx, [rsp+1528h+var_14A8]; this
0x180013f26  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
