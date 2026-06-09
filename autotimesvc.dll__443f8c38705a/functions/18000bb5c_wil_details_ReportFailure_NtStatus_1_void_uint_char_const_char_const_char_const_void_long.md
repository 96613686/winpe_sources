# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000bb5c`
- end: `0x18000bbd4`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `120`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000bd10`

## callees

- `0x180003c30`
- `0x18000bcb4`

## string_xrefs

- `0x18000bb84`: `onecore\base\time\autotime\timeservice\wnfsubscription.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v8 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v12[0] = v8;
  v12[1] = (_DWORD)a7;
  v12[2] = 1;
  wil::details::ReportFailure_Base<1,0>(
    a1,
    76,
    (int)"onecore\\base\\time\\autotime\\timeservice\\wnfsubscription.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v8;
}

```

## disassembly

```asm
0x18000bb5c  mov     [rsp+arg_0], rbx
0x18000bb61  mov     [rsp+arg_8], rsi
0x18000bb66  push    rdi
0x18000bb67  sub     rsp, 60h
0x18000bb6b  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000bb72  mov     rsi, rcx
0x18000bb75  mov     ecx, ebx; this
0x18000bb77  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000bb7c  mov     rdx, [rsp+68h+arg_28]
0x18000bb84  lea     r8, aOnecoreBaseTim_6; "onecore\\base\\time\\autotime\\timeserv"...
0x18000bb8b  mov     edi, eax
0x18000bb8d  mov     [rsp+68h+var_18], eax
0x18000bb91  lea     rax, [rsp+68h+var_18]
0x18000bb96  mov     [rsp+68h+var_30], 0
0x18000bb9f  mov     [rsp+68h+var_38], rax
0x18000bba4  mov     rcx, rsi
0x18000bba7  mov     [rsp+68h+var_40], rdx
0x18000bbac  mov     edx, 4Ch ; 'L'
0x18000bbb1  mov     [rsp+68h+var_14], ebx
0x18000bbb5  mov     [rsp+68h+var_10], 1
0x18000bbbd  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000bbc2  mov     rbx, [rsp+68h+arg_0]
0x18000bbc7  mov     eax, edi
0x18000bbc9  mov     rsi, [rsp+68h+arg_8]
0x18000bbce  add     rsp, 60h
0x18000bbd2  pop     rdi
0x18000bbd3  retn
```
