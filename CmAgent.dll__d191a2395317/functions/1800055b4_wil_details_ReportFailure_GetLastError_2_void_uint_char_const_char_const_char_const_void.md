# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800055b4`
- end: `0x180005688`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `212`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800095d8`

## callees

- `0x1800032b8`
- `0x18000339c`
- `0x1800041f8`
- `0x1800055b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005670`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005670`

## string_xrefs

- `0x1800055f5`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`
- `0x18000565d`: `onecore\base\gendrv\silos\clem\agent\service\service.cpp`

## pseudocode

```c
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
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
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
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\service.cpp",
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
0x1800055b4  push    rbx
0x1800055b6  push    rbp
0x1800055b7  push    rsi
0x1800055b8  push    rdi
0x1800055b9  sub     rsp, 68h
0x1800055bd  mov     edi, edx
0x1800055bf  mov     rsi, rcx
0x1800055c2  call    cs:__imp_GetLastError
0x1800055c9  nop     dword ptr [rax+rax+00h]
0x1800055ce  mov     ebx, eax
0x1800055d0  mov     rbp, [rsp+88h+arg_28]
0x1800055d8  test    eax, eax
0x1800055da  jnz     short loc_18000560B
0x1800055dc  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x1800055e4  mov     [rsp+88h+var_60], rbp; __int64
0x1800055e9  mov     [rsp+88h+var_68], 0; __int64
0x1800055f2  xor     r9d, r9d; int
0x1800055f5  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800055fc  mov     edx, edi; int
0x1800055fe  mov     rcx, rsi; int
0x180005601  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005606  mov     ebx, 29Ch
0x18000560b  test    ebx, ebx
0x18000560d  jg      short loc_180005613
0x18000560f  mov     ecx, ebx
0x180005611  jmp     short loc_18000561C
0x180005613  movzx   ecx, bx
0x180005616  or      ecx, 80070000h; this
0x18000561c  mov     [rsp+88h+var_38], ecx
0x180005620  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005625  mov     [rsp+88h+var_34], eax
0x180005629  mov     [rsp+88h+var_30], 0
0x180005631  mov     [rsp+88h+var_40], 0
0x180005639  mov     [rsp+88h+var_50], 0
0x180005642  lea     rax, [rsp+88h+var_38]
0x180005647  mov     [rsp+88h+var_58], rax
0x18000564c  mov     [rsp+88h+var_60], rbp
0x180005651  mov     [rsp+88h+var_68], 0
0x18000565a  xor     r9d, r9d
0x18000565d  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180005664  mov     edx, edi
0x180005666  mov     rcx, rsi
0x180005669  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000566e  mov     ecx, ebx; dwErrCode
0x180005670  call    cs:__imp_SetLastError
0x180005677  nop     dword ptr [rax+rax+00h]
0x18000567c  mov     eax, ebx
0x18000567e  add     rsp, 68h
0x180005682  pop     rdi
0x180005683  pop     rsi
0x180005684  pop     rbp
0x180005685  pop     rbx
0x180005686  retn
```
