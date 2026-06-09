# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400064a4`
- end: `0x14000657c`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `216`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000c578`

## callees

- `0x140006418`
- `0x1400064a4`
- `0x1400067e0`
- `0x140009674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006564`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400064b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400064b6`

## string_xrefs

- `0x1400064e3`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000654e`: `avcore\midi2\service\exe\midiservice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  int LastError; // ebx
  unsigned __int64 v9; // rcx
  wil::details *v11; // [rsp+30h] [rbp-38h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, 637, (int)"avcore\\midi2\\service\\exe\\midiservice.cpp", 0, 0, a6, v11);
    LastError = 668;
  }
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  else
    v9 = (unsigned int)LastError;
  v12[0] = v9;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v9, v7);
  v12[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    637,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
    0,
    0,
    a6,
    (__int64)v12,
    0);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400064a4  mov     [rsp+arg_0], rbx
0x1400064a9  mov     [rsp+arg_8], rsi
0x1400064ae  push    rdi
0x1400064af  sub     rsp, 60h
0x1400064b3  mov     rdi, rcx
0x1400064b6  call    cs:__imp_GetLastError
0x1400064bc  mov     ebx, eax
0x1400064be  mov     rsi, [rsp+68h+arg_28]
0x1400064c6  test    eax, eax
0x1400064c8  jnz     short loc_1400064FC
0x1400064ca  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x1400064d2  mov     [rsp+68h+var_40], rsi; __int64
0x1400064d7  mov     [rsp+68h+var_48], 0; __int64
0x1400064e0  xor     r9d, r9d; int
0x1400064e3  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x1400064ea  mov     edx, 27Dh; int
0x1400064ef  mov     rcx, rdi; int
0x1400064f2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400064f7  mov     ebx, 29Ch
0x1400064fc  test    ebx, ebx
0x1400064fe  jg      short loc_140006504
0x140006500  mov     ecx, ebx
0x140006502  jmp     short loc_14000650D
0x140006504  movzx   ecx, bx
0x140006507  or      ecx, 80070000h; this
0x14000650d  mov     [rsp+68h+var_18], ecx
0x140006511  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006516  mov     [rsp+68h+var_14], eax
0x14000651a  mov     [rsp+68h+var_10], 0
0x140006522  mov     [rsp+68h+var_20], 0
0x14000652a  mov     [rsp+68h+var_30], 0
0x140006533  lea     rax, [rsp+68h+var_18]
0x140006538  mov     [rsp+68h+var_38], rax
0x14000653d  mov     [rsp+68h+var_40], rsi
0x140006542  mov     [rsp+68h+var_48], 0
0x14000654b  xor     r9d, r9d
0x14000654e  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x140006555  mov     edx, 27Dh
0x14000655a  mov     rcx, rdi
0x14000655d  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140006562  mov     ecx, ebx; dwErrCode
0x140006564  call    cs:__imp_SetLastError
0x14000656a  mov     eax, ebx
0x14000656c  mov     rbx, [rsp+68h+arg_0]
0x140006571  mov     rsi, [rsp+68h+arg_8]
0x140006576  add     rsp, 60h
0x14000657a  pop     rdi
0x14000657b  retn
```
