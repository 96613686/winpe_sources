# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140002424`
- end: `0x140002493`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004380`

## callees

- `0x140002064`
- `0x140004418`

## string_xrefs

- `0x14000244a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000247b`: `(status == WAIT_TIMEOUT) || (status == WAIT_OBJECT_0) || (status == WAIT_ABANDONED) || (bAlertable && (status == WAIT_IO_COMPLETION))`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // xmm0_8
  int v8; // r10d
  __int64 v9; // [rsp+50h] [rbp-28h] BYREF
  int v10; // [rsp+58h] [rbp-20h]
  _BYTE v11[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v11, 2147549183LL);
  v7 = *(_QWORD *)v6;
  v10 = *(_DWORD *)(v6 + 8);
  v9 = v7;
  wil::details::ReportFailure_Base<3,0>(
    v8,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (unsigned int)"wil::mutex_t<class wil::details::unique_storage<struct wil::details::resource_policy<void *,void (__cd"
                  "ecl*)(void *) noexcept,&void __cdecl wil::details::CloseHandle(void *),struct wistd::integral_constant"
                  "<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,struct wil::err_returncode_policy>::acquire",
    (__int64)"(status == WAIT_TIMEOUT) || (status == WAIT_OBJECT_0) || (status == WAIT_ABANDONED) || (bAlertable && (stat"
             "us == WAIT_IO_COMPLETION))",
    a6,
    (__int64)&v9,
    0);
}

```

## disassembly

```asm
0x140002424  sub     rsp, 78h
0x140002428  mov     r10, rcx
0x14000242b  mov     edx, 8000FFFFh
0x140002430  lea     rcx, [rsp+78h+var_18]
0x140002435  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000243a  mov     [rsp+78h+var_40], 0
0x140002443  lea     r9, aWilMutexTClass; "wil::mutex_t<class wil::details::unique"...
0x14000244a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002451  mov     edx, 0E01h
0x140002456  mov     rcx, r10
0x140002459  movsd   xmm0, qword ptr [rax]
0x14000245d  mov     eax, [rax+8]
0x140002460  mov     [rsp+78h+var_20], eax
0x140002464  lea     rax, [rsp+78h+var_28]
0x140002469  mov     [rsp+78h+var_48], rax
0x14000246e  mov     rax, [rsp+78h+arg_28]
0x140002476  mov     [rsp+78h+var_50], rax
0x14000247b  lea     rax, aStatusWaitTime; "(status == WAIT_TIMEOUT) || (status == "...
0x140002482  mov     [rsp+78h+var_58], rax
0x140002487  movsd   [rsp+78h+var_28], xmm0
0x14000248d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
