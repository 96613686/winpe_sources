# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18002646c`
- end: `0x1800264cf`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `99`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002937c`

## callees

- `0x180006ea8`
- `0x18000be74`
- `0x18002646c`

## string_xrefs

- `0x180026494`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Win32<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  __int64 v7; // rdx
  int v8; // r9d
  int v9; // r10d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::ResultStatus::FromResult(v10, v7);
  wil::details::ReportFailure_Base<0,0>(
    v9,
    v8,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
    v8);
}

```

## disassembly

```asm
0x18002646c  sub     rsp, 78h
0x180026470  mov     r9d, edx
0x180026473  mov     r10, rcx
0x180026476  mov     edx, [rsp+78h+arg_30]
0x18002647d  test    edx, edx
0x18002647f  jle     short loc_18002648A
0x180026481  movzx   edx, dx
0x180026484  or      edx, 80070000h
0x18002648a  lea     rcx, [rsp+78h+var_18]
0x18002648f  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180026494  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002649b  mov     edx, r9d
0x18002649e  mov     rcx, r10
0x1800264a1  movsd   xmm0, qword ptr [rax]
0x1800264a5  mov     eax, [rax+8]
0x1800264a8  mov     [rsp+78h+var_20], eax
0x1800264ac  lea     rax, [rsp+78h+var_28]
0x1800264b1  mov     [rsp+78h+var_48], rax
0x1800264b6  mov     rax, [rsp+78h+arg_28]
0x1800264be  mov     [rsp+78h+var_50], rax
0x1800264c3  movsd   [rsp+78h+var_28], xmm0
0x1800264c9  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
