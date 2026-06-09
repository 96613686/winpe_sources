# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000dab4`
- end: `0x18000db15`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `97`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc58`

## callees

- `0x180002ed8`
- `0x1800078e4`

## string_xrefs

- `0x18000daf6`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

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
  wil::details::ReportFailure_Base<1,0>(a1, a2, "onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp");
  return v10;
}

```

## disassembly

```asm
0x18000dab4  push    rbx
0x18000dab6  push    rbp
0x18000dab7  push    rsi
0x18000dab8  push    rdi
0x18000dab9  sub     rsp, 68h
0x18000dabd  mov     ebx, dword ptr [rsp+88h+arg_30]
0x18000dac4  mov     rbp, rcx
0x18000dac7  mov     ecx, ebx; this
0x18000dac9  mov     esi, edx
0x18000dacb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000dad0  mov     r8, [rsp+88h+arg_28]
0x18000dad8  mov     edi, eax
0x18000dada  mov     [rsp+88h+var_38], eax
0x18000dade  mov     edx, esi
0x18000dae0  lea     rax, [rsp+88h+var_38]
0x18000dae5  mov     [rsp+88h+var_34], ebx
0x18000dae9  mov     [rsp+88h+var_58], rax
0x18000daee  mov     rcx, rbp
0x18000daf1  mov     [rsp+88h+var_60], r8
0x18000daf6  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\StateRepositor"...
0x18000dafd  mov     [rsp+88h+var_30], 1
0x18000db05  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000db0a  mov     eax, edi
0x18000db0c  add     rsp, 68h
0x18000db10  pop     rdi
0x18000db11  pop     rsi
0x18000db12  pop     rbp
0x18000db13  pop     rbx
0x18000db14  retn
```
