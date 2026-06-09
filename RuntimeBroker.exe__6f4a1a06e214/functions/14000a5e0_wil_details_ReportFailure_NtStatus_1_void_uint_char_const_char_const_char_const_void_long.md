# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x14000a5e0`
- end: `0x14000a641`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `97`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c5fc`

## callees

- `0x140004d30`
- `0x140008008`

## string_xrefs

- `0x14000a622`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v10; // [rsp+50h] [rbp-38h]

  v10 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(a1, a2, "onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp");
  return v10;
}

```

## disassembly

```asm
0x14000a5e0  push    rbx
0x14000a5e2  push    rbp
0x14000a5e3  push    rsi
0x14000a5e4  push    rdi
0x14000a5e5  sub     rsp, 68h
0x14000a5e9  mov     ebx, dword ptr [rsp+88h+arg_30]
0x14000a5f0  mov     rbp, rcx
0x14000a5f3  mov     ecx, ebx; this
0x14000a5f5  mov     esi, edx
0x14000a5f7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000a5fc  mov     r8, [rsp+88h+arg_28]
0x14000a604  mov     edi, eax
0x14000a606  mov     [rsp+88h+var_38], eax
0x14000a60a  mov     edx, esi
0x14000a60c  lea     rax, [rsp+88h+var_38]
0x14000a611  mov     [rsp+88h+var_34], ebx
0x14000a615  mov     [rsp+88h+var_58], rax
0x14000a61a  mov     rcx, rbp
0x14000a61d  mov     [rsp+88h+var_60], r8
0x14000a622  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x14000a629  mov     [rsp+88h+var_30], 1
0x14000a631  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000a636  mov     eax, edi
0x14000a638  add     rsp, 68h
0x14000a63c  pop     rdi
0x14000a63d  pop     rsi
0x14000a63e  pop     rbp
0x14000a63f  pop     rbx
0x14000a640  retn
```
