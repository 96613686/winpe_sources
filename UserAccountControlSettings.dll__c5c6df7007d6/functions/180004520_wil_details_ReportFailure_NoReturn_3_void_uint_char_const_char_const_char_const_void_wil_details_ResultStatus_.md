# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004520`
- end: `0x1800045cd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004304`

## callees

- `0x180005e30`
- `0x180006ee8`
- `0x18000b6de`
- `0x18000b7a0`

## string_xrefs

- `0x180004569`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004520  mov     [rsp+arg_10], rbx
0x180004525  mov     [rsp+arg_18], rsi
0x18000452a  push    rdi
0x18000452b  mov     eax, 1520h
0x180004530  call    _alloca_probe
0x180004535  sub     rsp, rax
0x180004538  mov     rbx, [rsp+1528h+arg_28]
0x180004540  mov     esi, edx
0x180004542  mov     rdi, rcx
0x180004545  xor     edx, edx; Val
0x180004547  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18000454f  mov     r8d, 98h; Size
0x180004555  call    memset_0
0x18000455a  xor     ecx, ecx
0x18000455c  lea     rax, [rsp+1528h+var_14A8]
0x180004564  mov     [rsp+1528h+var_14B0], rax
0x180004569  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004570  mov     [rsp+1528h+var_14B8], ecx
0x180004574  lea     rax, [rsp+1528h+var_1408]
0x18000457c  mov     [rsp+1528h+var_14C8], rax
0x180004581  xor     r9d, r9d
0x180004584  lea     rax, [rsp+1528h+var_1008]
0x18000458c  mov     edx, esi
0x18000458e  mov     [rsp+1528h+var_14D8], rax
0x180004593  mov     rax, [rsp+1528h+arg_30]
0x18000459b  mov     [rsp+1528h+var_14E8], rcx
0x1800045a0  mov     [rsp+1528h+var_14F0], rax
0x1800045a5  mov     [rsp+1528h+var_14F8], 3
0x1800045ad  mov     [rsp+1528h+var_1500], rbx
0x1800045b2  mov     [rsp+1528h+var_1508], rcx
0x1800045b7  mov     rcx, rdi
0x1800045ba  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x1800045bf  lea     rcx, [rsp+1528h+var_14A8]; this
0x1800045c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
