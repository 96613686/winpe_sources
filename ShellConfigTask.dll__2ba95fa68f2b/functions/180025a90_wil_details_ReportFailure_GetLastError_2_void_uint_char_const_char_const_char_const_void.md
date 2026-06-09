# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180025a90`
- end: `0x180025b57`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `199`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002dccc`

## callees

- `0x180003fc8`
- `0x1800041d4`
- `0x180008110`
- `0x180025a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a9e`

## string_xrefs

- `0x180025acb`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x180025b33`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  int LastError; // ebx
  unsigned __int64 v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-58h]
  _DWORD v13[14]; // [rsp+50h] [rbp-38h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      a2,
      (int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      0,
      0,
      a6,
      v12);
    LastError = 668;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = (unsigned int)LastError;
  v13[0] = v10;
  v13[1] = wil::details::HrToNtStatus((wil::details *)v10, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
    0,
    0,
    a6,
    (__int64)v13,
    0);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180025a90  push    rbx
0x180025a92  push    rbp
0x180025a93  push    rsi
0x180025a94  push    rdi
0x180025a95  sub     rsp, 68h
0x180025a99  mov     edi, edx
0x180025a9b  mov     rsi, rcx
0x180025a9e  call    cs:__imp_GetLastError
0x180025aa4  mov     ebx, eax
0x180025aa6  mov     rbp, [rsp+88h+arg_28]
0x180025aae  test    eax, eax
0x180025ab0  jnz     short loc_180025AE1
0x180025ab2  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x180025aba  mov     [rsp+88h+var_60], rbp; __int64
0x180025abf  mov     [rsp+88h+var_68], 0; __int64
0x180025ac8  xor     r9d, r9d; int
0x180025acb  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180025ad2  mov     edx, edi; int
0x180025ad4  mov     rcx, rsi; int
0x180025ad7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025adc  mov     ebx, 29Ch
0x180025ae1  test    ebx, ebx
0x180025ae3  jg      short loc_180025AE9
0x180025ae5  mov     ecx, ebx
0x180025ae7  jmp     short loc_180025AF2
0x180025ae9  movzx   ecx, bx
0x180025aec  or      ecx, 80070000h; this
0x180025af2  mov     [rsp+88h+var_38], ecx
0x180025af6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025afb  mov     [rsp+88h+var_34], eax
0x180025aff  mov     [rsp+88h+var_30], 0
0x180025b07  mov     [rsp+88h+var_40], 0
0x180025b0f  mov     [rsp+88h+var_50], 0
0x180025b18  lea     rax, [rsp+88h+var_38]
0x180025b1d  mov     [rsp+88h+var_58], rax
0x180025b22  mov     [rsp+88h+var_60], rbp
0x180025b27  mov     [rsp+88h+var_68], 0
0x180025b30  xor     r9d, r9d
0x180025b33  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180025b3a  mov     edx, edi
0x180025b3c  mov     rcx, rsi
0x180025b3f  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180025b44  mov     ecx, ebx; dwErrCode
0x180025b46  call    cs:__imp_SetLastError
0x180025b4c  mov     eax, ebx
0x180025b4e  add     rsp, 68h
0x180025b52  pop     rdi
0x180025b53  pop     rsi
0x180025b54  pop     rbp
0x180025b55  pop     rbx
0x180025b56  retn
```
