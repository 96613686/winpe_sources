# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14001051c`
- end: `0x140010595`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `121`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010884`

## callees

- `0x140003f50`
- `0x1400044bc`
- `0x1400076c0`
- `0x14001051c`

## string_xrefs

- `0x14001052e`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x140010564`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int v8; // r9d
  const char *v9; // [rsp+20h] [rbp-48h]
  void *v10; // [rsp+30h] [rbp-38h]

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x3C,
                    (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
                    a4,
                    v9,
                    a6,
                    v10);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, 0);
  wil::details::ReportFailure_Base<0,0>(
    v6,
    60,
    (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
    v8);
}

```

## disassembly

```asm
0x14001051c  mov     [rsp+arg_0], rbx
0x140010521  push    rdi
0x140010522  sub     rsp, 60h
0x140010526  mov     rdi, [rsp+68h+arg_28]
0x14001052e  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010535  mov     edx, 3Ch ; '<'; void *
0x14001053a  mov     [rsp+68h+var_40], rdi; char *
0x14001053f  mov     rbx, rcx
0x140010542  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140010547  xor     edx, edx; int
0x140010549  test    eax, eax
0x14001054b  jle     short loc_140010555
0x14001054d  movzx   eax, ax
0x140010550  or      eax, 80070000h
0x140010555  mov     ecx, eax; this
0x140010557  mov     [rsp+68h+var_18], eax
0x14001055b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140010560  mov     [rsp+68h+var_28], edx
0x140010564  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001056b  mov     [rsp+68h+var_30], rdx
0x140010570  mov     rcx, rbx
0x140010573  mov     [rsp+68h+var_14], eax
0x140010577  lea     rax, [rsp+68h+var_18]
0x14001057c  mov     [rsp+68h+var_10], edx
0x140010580  mov     edx, 3Ch ; '<'
0x140010585  mov     [rsp+68h+var_38], rax
0x14001058a  mov     [rsp+68h+var_40], rdi
0x14001058f  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
