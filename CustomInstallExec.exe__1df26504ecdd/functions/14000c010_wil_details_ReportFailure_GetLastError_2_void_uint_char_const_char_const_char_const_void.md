# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000c010`
- end: `0x14000c0af`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `159`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000d534`

## callees

- `0x1400048b0`
- `0x140005d30`
- `0x140006170`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c097`

## string_xrefs

- `0x14000c027`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`
- `0x14000c062`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`

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
                    (void *)0x217,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
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
    535,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
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
0x14000c010  mov     [rsp+arg_0], rbx
0x14000c015  mov     [rsp+arg_8], rsi
0x14000c01a  push    rdi
0x14000c01b  sub     rsp, 60h
0x14000c01f  mov     rsi, [rsp+68h+arg_28]
0x14000c027  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000c02e  mov     edx, 217h; void *
0x14000c033  mov     [rsp+68h+var_40], rsi; char *
0x14000c038  mov     rdi, rcx
0x14000c03b  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14000c040  xor     edx, edx; int
0x14000c042  mov     ebx, eax
0x14000c044  test    eax, eax
0x14000c046  jg      short loc_14000C04C
0x14000c048  mov     ecx, eax
0x14000c04a  jmp     short loc_14000C055
0x14000c04c  movzx   ecx, bx
0x14000c04f  or      ecx, 80070000h; this
0x14000c055  mov     [rsp+68h+var_18], ecx
0x14000c059  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000c05e  mov     [rsp+68h+var_20], edx
0x14000c062  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000c069  mov     [rsp+68h+var_14], eax
0x14000c06d  xor     r9d, r9d
0x14000c070  lea     rax, [rsp+68h+var_18]
0x14000c075  mov     [rsp+68h+var_10], edx
0x14000c079  mov     [rsp+68h+var_38], rax
0x14000c07e  mov     rcx, rdi
0x14000c081  mov     [rsp+68h+var_40], rsi
0x14000c086  mov     [rsp+68h+var_48], rdx
0x14000c08b  mov     edx, 217h
0x14000c090  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000c095  mov     ecx, ebx; dwErrCode
0x14000c097  call    cs:__imp_SetLastError
0x14000c09d  mov     rsi, [rsp+68h+arg_8]
0x14000c0a2  mov     eax, ebx
0x14000c0a4  mov     rbx, [rsp+68h+arg_0]
0x14000c0a9  add     rsp, 60h
0x14000c0ad  pop     rdi
0x14000c0ae  retn
```
