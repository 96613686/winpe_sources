# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180015684`
- end: `0x180015788`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `260`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800154b0`

## callees

- `0x180015684`
- `0x180016ea0`
- `0x180017518`
- `0x180019722`
- `0x180019810`
- `0x18001b010`

## string_xrefs

- `0x1800156d7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  bool v9; // bp
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[160]; // [rsp+80h] [rbp-14B8h] BYREF
  _BYTE v12[4120]; // [rsp+520h] [rbp-1018h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(v11, 0, 0x98u);
  wil::details::LogFailure(a1, a2, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h", 0, 0, a6, 0, a7, 0);
  if ( (v11[4] & 1) == 0 )
  {
    if ( v9 )
      ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v11, v12);
    if ( wil::details::g_pfnThrowResultException )
      wil::details::g_pfnThrowResultException((const struct wil::FailureInfo *)v11);
  }
  wil::details::WilFailFast((wil::details *)v11, v10);
}

```

## disassembly

```asm
0x180015684  mov     [rsp+arg_10], rbx
0x180015689  push    rbp
0x18001568a  push    rsi
0x18001568b  push    rdi
0x18001568c  mov     eax, 1520h
0x180015691  call    _alloca_probe
0x180015696  sub     rsp, rax
0x180015699  cmp     cs:g_pfnThrowPlatformException, 0
0x1800156a1  mov     esi, edx
0x1800156a3  mov     rbx, [rsp+1538h+arg_28]
0x1800156ab  mov     rdi, rcx
0x1800156ae  setnz   bpl
0x1800156b2  lea     rcx, [rsp+1538h+var_14B8]; void *
0x1800156ba  xor     edx, edx; Val
0x1800156bc  mov     r8d, 98h; Size
0x1800156c2  call    memset_0
0x1800156c7  lea     rax, [rsp+1538h+var_14B8]
0x1800156cf  xor     r9d, r9d
0x1800156d2  mov     [rsp+1538h+var_14C0], rax
0x1800156d7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800156de  mov     [rsp+1538h+var_14C8], 0
0x1800156e6  lea     rax, [rsp+1538h+var_1418]
0x1800156ee  mov     [rsp+1538h+var_14D8], rax
0x1800156f3  mov     edx, esi
0x1800156f5  lea     rax, [rsp+1538h+var_1018]
0x1800156fd  mov     rcx, rdi
0x180015700  mov     [rsp+1538h+var_14E8], rax
0x180015705  mov     rax, [rsp+1538h+arg_30]
0x18001570d  mov     [rsp+1538h+var_14F8], 0
0x180015716  mov     [rsp+1538h+var_1500], rax
0x18001571b  mov     [rsp+1538h+var_1508], 0
0x180015723  mov     [rsp+1538h+var_1510], rbx
0x180015728  mov     [rsp+1538h+var_1518], 0
0x180015731  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180015736  test    [rsp+1538h+var_14B4], 1
0x18001573e  jnz     short loc_18001577A
0x180015740  test    bpl, bpl
0x180015743  jz      short loc_180015761
0x180015745  mov     rax, cs:g_pfnThrowPlatformException
0x18001574c  lea     rdx, [rsp+1538h+var_1018]
0x180015754  lea     rcx, [rsp+1538h+var_14B8]
0x18001575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015761  mov     rax, cs:?g_pfnThrowResultException@details@wil@@3P6AXAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnThrowResultException)(wil::FailureInfo const &)
0x180015768  test    rax, rax
0x18001576b  jz      short loc_18001577A
0x18001576d  lea     rcx, [rsp+1538h+var_14B8]
0x180015775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001577a  lea     rcx, [rsp+1538h+var_14B8]; this
0x180015782  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
