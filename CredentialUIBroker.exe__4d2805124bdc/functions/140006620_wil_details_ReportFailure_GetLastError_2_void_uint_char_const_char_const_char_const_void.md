# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140006620`
- end: `0x1400066be`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `158`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f28c`

## callees

- `0x140006598`
- `0x140006620`
- `0x14000d980`
- `0x14000e45c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400066a6`
- `KERNEL32!SetLastError` at `0x1400066a6`

## string_xrefs

- `0x140006637`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x140006672`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  DWORD v8; // ebx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  const char *v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x5F,
                    (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
                    a4,
                    v12,
                    a6,
                    v13);
  v8 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v9 = (unsigned int)LastErrorFail;
  v14[0] = v9;
  v14[1] = wil::details::HrToNtStatus((wil::details *)v9, 0);
  v14[2] = v10;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    95,
    (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
    0,
    v10,
    (__int64)a6,
    (__int64)v14);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x140006620  mov     [rsp+arg_0], rbx
0x140006625  mov     [rsp+arg_8], rsi
0x14000662a  push    rdi
0x14000662b  sub     rsp, 60h
0x14000662f  mov     rsi, [rsp+68h+arg_28]
0x140006637  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x14000663e  mov     edx, 5Fh ; '_'; void *
0x140006643  mov     [rsp+68h+var_40], rsi; char *
0x140006648  mov     rdi, rcx
0x14000664b  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140006650  xor     edx, edx; int
0x140006652  mov     ebx, eax
0x140006654  test    eax, eax
0x140006656  jg      short loc_14000665C
0x140006658  mov     ecx, eax
0x14000665a  jmp     short loc_140006665
0x14000665c  movzx   ecx, bx
0x14000665f  or      ecx, 80070000h; this
0x140006665  mov     [rsp+68h+var_18], ecx
0x140006669  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000666e  mov     [rsp+68h+var_20], edx
0x140006672  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140006679  mov     [rsp+68h+var_14], eax
0x14000667d  xor     r9d, r9d
0x140006680  lea     rax, [rsp+68h+var_18]
0x140006685  mov     [rsp+68h+var_10], edx
0x140006689  mov     [rsp+68h+var_38], rax
0x14000668e  mov     rcx, rdi
0x140006691  mov     [rsp+68h+var_40], rsi
0x140006696  mov     [rsp+68h+var_48], rdx
0x14000669b  lea     edx, [r9+5Fh]
0x14000669f  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400066a4  mov     ecx, ebx; dwErrCode
0x1400066a6  call    cs:__imp_SetLastError
0x1400066ac  mov     rsi, [rsp+68h+arg_8]
0x1400066b1  mov     eax, ebx
0x1400066b3  mov     rbx, [rsp+68h+arg_0]
0x1400066b8  add     rsp, 60h
0x1400066bc  pop     rdi
0x1400066bd  retn
```
