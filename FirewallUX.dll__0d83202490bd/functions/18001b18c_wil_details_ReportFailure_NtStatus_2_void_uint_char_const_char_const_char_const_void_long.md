# wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18001b18c`
- end: `0x18001b20e`
- name: `??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `130`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022974`

## callees

- `0x180003f58`
- `0x18001f978`

## string_xrefs

- `0x18001b1b4`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  _DWORD v10[6]; // [rsp+50h] [rbp-18h] BYREF

  v10[0] = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v8 = v10[0];
  v10[1] = (_DWORD)a7;
  v10[2] = 1;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    151,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
    0,
    0,
    a6,
    (__int64)v10,
    0);
  return v8;
}

```

## disassembly

```asm
0x18001b18c  mov     [rsp+arg_0], rbx
0x18001b191  mov     [rsp+arg_8], rsi
0x18001b196  push    rdi
0x18001b197  sub     rsp, 60h
0x18001b19b  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18001b1a2  mov     rsi, rcx
0x18001b1a5  mov     ecx, ebx; this
0x18001b1a7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001b1ac  mov     rdx, [rsp+68h+arg_28]
0x18001b1b4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001b1bb  xor     ecx, ecx
0x18001b1bd  mov     [rsp+68h+var_18], eax
0x18001b1c1  mov     [rsp+68h+var_20], ecx
0x18001b1c5  mov     edi, eax
0x18001b1c7  mov     [rsp+68h+var_30], rcx
0x18001b1cc  lea     rax, [rsp+68h+var_18]
0x18001b1d1  mov     [rsp+68h+var_38], rax
0x18001b1d6  xor     r9d, r9d
0x18001b1d9  mov     [rsp+68h+var_40], rdx
0x18001b1de  mov     edx, 97h
0x18001b1e3  mov     [rsp+68h+var_48], rcx
0x18001b1e8  mov     rcx, rsi
0x18001b1eb  mov     [rsp+68h+var_14], ebx
0x18001b1ef  mov     [rsp+68h+var_10], 1
0x18001b1f7  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001b1fc  mov     rbx, [rsp+68h+arg_0]
0x18001b201  mov     eax, edi
0x18001b203  mov     rsi, [rsp+68h+arg_8]
0x18001b208  add     rsp, 60h
0x18001b20c  pop     rdi
0x18001b20d  retn
```
