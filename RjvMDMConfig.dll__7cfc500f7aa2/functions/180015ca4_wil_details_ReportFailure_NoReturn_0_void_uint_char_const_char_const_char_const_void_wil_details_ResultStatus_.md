# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180015ca4`
- end: `0x180015dae`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015c28`

## callees

- `0x1800026d8`
- `0x18000af94`
- `0x180010ab4`
- `0x180011170`
- `0x180015ca4`
- `0x18001cf10`
- `0x18001e010`

## string_xrefs

- `0x180015cf8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  bool v8; // si
  const struct wil::FailureInfo *v9; // rdx
  const struct wil::FailureInfo *v10; // rdx
  __int64 v11; // [rsp+48h] [rbp-14E0h]
  __int64 v12; // [rsp+58h] [rbp-14D0h]
  __int64 v13; // [rsp+68h] [rbp-14C0h]
  _BYTE v14[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v15[1024]; // [rsp+120h] [rbp-1408h] BYREF
  _BYTE v16[4104]; // [rsp+520h] [rbp-1008h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(v14, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    5331,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    0,
    a7,
    0,
    v11,
    (wil *)v16,
    v12,
    v15,
    v13,
    0,
    (unsigned __int64)v14);
  if ( (v14[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v14, v9);
  if ( v8 )
    ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v14, v16);
  wil::ThrowResultException((wil *)v14, v9);
  wil::details::WilFailFast((wil::details *)v14, v10);
}

```

## disassembly

```asm
0x180015ca4  mov     [rsp+arg_8], rbx
0x180015ca9  mov     [rsp+arg_10], rsi
0x180015cae  push    rdi
0x180015caf  mov     eax, 1520h
0x180015cb4  call    _alloca_probe
0x180015cb9  sub     rsp, rax
0x180015cbc  cmp     cs:g_pfnThrowPlatformException, 0
0x180015cc4  mov     rdi, rcx
0x180015cc7  mov     rbx, [rsp+1528h+arg_28]
0x180015ccf  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180015cd7  setnz   sil
0x180015cdb  mov     r8d, 98h; Size
0x180015ce1  xor     edx, edx; Val
0x180015ce3  call    memset_0
0x180015ce8  lea     rax, [rsp+1528h+var_14A8]
0x180015cf0  xor     r9d, r9d
0x180015cf3  mov     [rsp+1528h+var_14B0], rax
0x180015cf8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015cff  mov     [rsp+1528h+var_14B8], 0
0x180015d07  lea     rax, [rsp+1528h+var_1408]
0x180015d0f  mov     [rsp+1528h+var_14C8], rax
0x180015d14  mov     edx, 14D3h
0x180015d19  lea     rax, [rsp+1528h+var_1008]
0x180015d21  mov     rcx, rdi
0x180015d24  mov     [rsp+1528h+var_14D8], rax
0x180015d29  mov     rax, [rsp+1528h+arg_30]
0x180015d31  mov     [rsp+1528h+var_14E8], 0
0x180015d3a  mov     [rsp+1528h+var_14F0], rax
0x180015d3f  mov     [rsp+1528h+var_14F8], 0
0x180015d47  mov     [rsp+1528h+var_1500], rbx
0x180015d4c  mov     [rsp+1528h+var_1508], 0
0x180015d55  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180015d5a  test    [rsp+1528h+var_14A4], 1
0x180015d62  jz      short loc_180015D72
0x180015d64  lea     rcx, [rsp+1528h+var_14A8]; this
0x180015d6c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015d72  test    sil, sil
0x180015d75  jz      short loc_180015D93
0x180015d77  mov     rax, cs:g_pfnThrowPlatformException
0x180015d7e  lea     rdx, [rsp+1528h+var_1008]
0x180015d86  lea     rcx, [rsp+1528h+var_14A8]
0x180015d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d93  lea     rcx, [rsp+1528h+var_14A8]; this
0x180015d9b  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180015da0  lea     rcx, [rsp+1528h+var_14A8]; this
0x180015da8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
