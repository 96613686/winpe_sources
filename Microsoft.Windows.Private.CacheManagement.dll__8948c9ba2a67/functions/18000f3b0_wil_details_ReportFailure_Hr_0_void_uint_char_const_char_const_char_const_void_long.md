# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000f3b0`
- end: `0x18000f405`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110J@Z`
- size: `85`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f410`

## callees

- `0x180003320`
- `0x1800035f0`

## string_xrefs

- `0x18000f3c8`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v9, a7);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    87,
    (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
    v7);
}

```

## disassembly

```asm
0x18000f3b0  sub     rsp, 78h
0x18000f3b4  mov     edx, [rsp+78h+arg_30]
0x18000f3bb  mov     r10, rcx
0x18000f3be  lea     rcx, [rsp+78h+var_18]
0x18000f3c3  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000f3c8  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000f3cf  mov     edx, 57h ; 'W'
0x18000f3d4  mov     rcx, r10
0x18000f3d7  movsd   xmm0, qword ptr [rax]
0x18000f3db  mov     eax, [rax+8]
0x18000f3de  mov     [rsp+78h+var_20], eax
0x18000f3e2  lea     rax, [rsp+78h+var_28]
0x18000f3e7  mov     [rsp+78h+var_48], rax
0x18000f3ec  mov     rax, [rsp+78h+arg_28]
0x18000f3f4  mov     [rsp+78h+var_50], rax
0x18000f3f9  movsd   [rsp+78h+var_28], xmm0
0x18000f3ff  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)
```
