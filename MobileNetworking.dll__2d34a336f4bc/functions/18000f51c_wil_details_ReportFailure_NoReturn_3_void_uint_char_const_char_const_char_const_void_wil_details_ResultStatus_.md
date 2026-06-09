# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000f51c`
- end: `0x18000f5c9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f378`

## callees

- `0x18000a19a`
- `0x1800107d0`
- `0x1800114d8`
- `0x1800118a0`

## string_xrefs

- `0x18000f565`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000f51c  mov     [rsp+arg_10], rbx
0x18000f521  mov     [rsp+arg_18], rsi
0x18000f526  push    rdi
0x18000f527  mov     eax, 1520h
0x18000f52c  call    _alloca_probe
0x18000f531  sub     rsp, rax
0x18000f534  mov     rbx, [rsp+1528h+arg_28]
0x18000f53c  mov     esi, edx
0x18000f53e  mov     rdi, rcx
0x18000f541  xor     edx, edx; Val
0x18000f543  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18000f54b  mov     r8d, 98h; Size
0x18000f551  call    memset_0
0x18000f556  xor     ecx, ecx
0x18000f558  lea     rax, [rsp+1528h+var_14A8]
0x18000f560  mov     [rsp+1528h+var_14B0], rax
0x18000f565  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f56c  mov     [rsp+1528h+var_14B8], ecx
0x18000f570  lea     rax, [rsp+1528h+var_1408]
0x18000f578  mov     [rsp+1528h+var_14C8], rax
0x18000f57d  xor     r9d, r9d
0x18000f580  lea     rax, [rsp+1528h+var_1008]
0x18000f588  mov     edx, esi
0x18000f58a  mov     [rsp+1528h+var_14D8], rax
0x18000f58f  mov     rax, [rsp+1528h+arg_30]
0x18000f597  mov     [rsp+1528h+var_14E8], rcx
0x18000f59c  mov     [rsp+1528h+var_14F0], rax
0x18000f5a1  mov     [rsp+1528h+var_14F8], 3
0x18000f5a9  mov     [rsp+1528h+var_1500], rbx
0x18000f5ae  mov     [rsp+1528h+var_1508], rcx
0x18000f5b3  mov     rcx, rdi
0x18000f5b6  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000f5bb  lea     rcx, [rsp+1528h+var_14A8]; this
0x18000f5c3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
