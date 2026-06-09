# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800155d0`
- end: `0x18001567d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015484`

## callees

- `0x180016ea0`
- `0x180017518`
- `0x180019722`
- `0x180019810`

## string_xrefs

- `0x180015619`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  wil::details::LogFailure(a1, a2, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h", 0, 0, a6, 3, a7, 0);
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x1800155d0  mov     [rsp+arg_10], rbx
0x1800155d5  mov     [rsp+arg_18], rsi
0x1800155da  push    rdi
0x1800155db  mov     eax, 1520h
0x1800155e0  call    _alloca_probe
0x1800155e5  sub     rsp, rax
0x1800155e8  mov     rbx, [rsp+1528h+arg_28]
0x1800155f0  mov     esi, edx
0x1800155f2  mov     rdi, rcx
0x1800155f5  xor     edx, edx; Val
0x1800155f7  lea     rcx, [rsp+1528h+var_14A8]; void *
0x1800155ff  mov     r8d, 98h; Size
0x180015605  call    memset_0
0x18001560a  xor     ecx, ecx
0x18001560c  lea     rax, [rsp+1528h+var_14A8]
0x180015614  mov     [rsp+1528h+var_14B0], rax
0x180015619  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015620  mov     [rsp+1528h+var_14B8], ecx
0x180015624  lea     rax, [rsp+1528h+var_1408]
0x18001562c  mov     [rsp+1528h+var_14C8], rax
0x180015631  xor     r9d, r9d
0x180015634  lea     rax, [rsp+1528h+var_1008]
0x18001563c  mov     edx, esi
0x18001563e  mov     [rsp+1528h+var_14D8], rax
0x180015643  mov     rax, [rsp+1528h+arg_30]
0x18001564b  mov     [rsp+1528h+var_14E8], rcx
0x180015650  mov     [rsp+1528h+var_14F0], rax
0x180015655  mov     [rsp+1528h+var_14F8], 3
0x18001565d  mov     [rsp+1528h+var_1500], rbx
0x180015662  mov     [rsp+1528h+var_1508], rcx
0x180015667  mov     rcx, rdi
0x18001566a  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18001566f  lea     rcx, [rsp+1528h+var_14A8]; this
0x180015677  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
