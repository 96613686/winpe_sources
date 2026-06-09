# wil::details::ReportFailure_NtStatus<0>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000fa9c`
- end: `0x18000faf7`
- name: `??$ReportFailure_NtStatus@$0A@@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `91`
- prototype: `void __fastcall __noreturn(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800101b8`

## callees

- `0x180003cc8`
- `0x18000bcb4`

## string_xrefs

- `0x18000fac2`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<0>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  int v9; // r9d

  wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<0,0>(
    a1,
    a2,
    (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
    v9);
}

```

## disassembly

```asm
0x18000fa9c  mov     [rsp+arg_0], rbx
0x18000faa1  mov     [rsp+arg_8], rsi
0x18000faa6  push    rdi
0x18000faa7  sub     rsp, 60h
0x18000faab  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000fab2  mov     rsi, rcx
0x18000fab5  mov     ecx, ebx; this
0x18000fab7  mov     edi, edx
0x18000fab9  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fabe  mov     [rsp+68h+var_18], eax
0x18000fac2  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000fac9  lea     rax, [rsp+68h+var_18]
0x18000face  mov     [rsp+68h+var_14], ebx
0x18000fad2  mov     [rsp+68h+var_38], rax
0x18000fad7  mov     edx, edi
0x18000fad9  mov     rax, [rsp+68h+arg_28]
0x18000fae1  mov     rcx, rsi
0x18000fae4  mov     [rsp+68h+var_40], rax
0x18000fae9  mov     [rsp+68h+var_10], 1
0x18000faf1  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
