# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002d230`
- end: `0x18002d308`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `216`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180030a48`

## callees

- `0x18000e134`
- `0x18000e340`
- `0x18001012c`
- `0x18002d230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d242`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2f0`

## string_xrefs

- `0x18002d26f`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002d2da`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`

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
    wil::details::ReportFailure_Hr<2>(
      a1,
      320,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      0,
      0,
      a6,
      v11);
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
    320,
    (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
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
0x18002d230  mov     [rsp+arg_0], rbx
0x18002d235  mov     [rsp+arg_8], rsi
0x18002d23a  push    rdi
0x18002d23b  sub     rsp, 60h
0x18002d23f  mov     rdi, rcx
0x18002d242  call    cs:__imp_GetLastError
0x18002d248  mov     ebx, eax
0x18002d24a  mov     rsi, [rsp+68h+arg_28]
0x18002d252  test    eax, eax
0x18002d254  jnz     short loc_18002D288
0x18002d256  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x18002d25e  mov     [rsp+68h+var_40], rsi; __int64
0x18002d263  mov     [rsp+68h+var_48], 0; __int64
0x18002d26c  xor     r9d, r9d; int
0x18002d26f  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d276  mov     edx, 140h; int
0x18002d27b  mov     rcx, rdi; int
0x18002d27e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002d283  mov     ebx, 29Ch
0x18002d288  test    ebx, ebx
0x18002d28a  jg      short loc_18002D290
0x18002d28c  mov     ecx, ebx
0x18002d28e  jmp     short loc_18002D299
0x18002d290  movzx   ecx, bx
0x18002d293  or      ecx, 80070000h; this
0x18002d299  mov     [rsp+68h+var_18], ecx
0x18002d29d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002d2a2  mov     [rsp+68h+var_14], eax
0x18002d2a6  mov     [rsp+68h+var_10], 0
0x18002d2ae  mov     [rsp+68h+var_20], 0
0x18002d2b6  mov     [rsp+68h+var_30], 0
0x18002d2bf  lea     rax, [rsp+68h+var_18]
0x18002d2c4  mov     [rsp+68h+var_38], rax
0x18002d2c9  mov     [rsp+68h+var_40], rsi
0x18002d2ce  mov     [rsp+68h+var_48], 0
0x18002d2d7  xor     r9d, r9d
0x18002d2da  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d2e1  mov     edx, 140h
0x18002d2e6  mov     rcx, rdi
0x18002d2e9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18002d2ee  mov     ecx, ebx; dwErrCode
0x18002d2f0  call    cs:__imp_SetLastError
0x18002d2f6  mov     eax, ebx
0x18002d2f8  mov     rbx, [rsp+68h+arg_0]
0x18002d2fd  mov     rsi, [rsp+68h+arg_8]
0x18002d302  add     rsp, 60h
0x18002d306  pop     rdi
0x18002d307  retn
```
