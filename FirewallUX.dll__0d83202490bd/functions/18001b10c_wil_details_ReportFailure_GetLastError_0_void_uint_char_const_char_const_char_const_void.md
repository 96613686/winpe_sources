# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18001b10c`
- end: `0x18001b184`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `120`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022dc8`

## callees

- `0x180006ea8`
- `0x180007650`
- `0x18000be74`
- `0x18001b10c`

## string_xrefs

- `0x18001b11e`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`
- `0x18001b14f`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  _BYTE v16[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x8F,
                    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v16, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v15 = *(_DWORD *)(v8 + 8);
  v14 = v9;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    143,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)&v14);
}

```

## disassembly

```asm
0x18001b10c  mov     [rsp+arg_0], rbx
0x18001b111  push    rdi
0x18001b112  sub     rsp, 70h
0x18001b116  mov     rdi, [rsp+78h+arg_28]
0x18001b11e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001b125  mov     edx, 8Fh; void *
0x18001b12a  mov     [rsp+78h+var_50], rdi; char *
0x18001b12f  mov     rbx, rcx
0x18001b132  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18001b137  test    eax, eax
0x18001b139  jle     short loc_18001B143
0x18001b13b  movzx   eax, ax
0x18001b13e  or      eax, 80070000h
0x18001b143  mov     edx, eax
0x18001b145  lea     rcx, [rsp+78h+var_18]
0x18001b14a  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18001b14f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001b156  mov     edx, 8Fh
0x18001b15b  mov     rcx, rbx
0x18001b15e  movsd   xmm0, qword ptr [rax]
0x18001b162  mov     eax, [rax+8]
0x18001b165  mov     [rsp+78h+var_20], eax
0x18001b169  lea     rax, [rsp+78h+var_28]
0x18001b16e  mov     [rsp+78h+var_48], rax
0x18001b173  mov     [rsp+78h+var_50], rdi
0x18001b178  movsd   [rsp+78h+var_28], xmm0
0x18001b17e  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
