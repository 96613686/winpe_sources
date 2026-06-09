# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000f2e0`
- end: `0x18000f371`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001136c`

## callees

- `0x180004f5c`
- `0x1800066e8`
- `0x180007d70`
- `0x18000f2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f360`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f360`

## string_xrefs

- `0x18000f2f1`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x18000f329`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  DWORD v9; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  const char *v13; // [rsp+20h] [rbp-68h]
  void *v14; // [rsp+30h] [rbp-58h]
  _DWORD v15[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
                    a4,
                    v13,
                    a6,
                    v14);
  v9 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v10 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v10 = (unsigned int)LastErrorFail;
  v15[0] = v10;
  v15[1] = wil::details::HrToNtStatus((wil::details *)v10, 0);
  v15[2] = v11;
  wil::details::ReportFailure_Base<2,0>(
    v7,
    v6,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15,
    v11);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x18000f2e0  push    rbx
0x18000f2e2  push    rbp
0x18000f2e3  push    rsi
0x18000f2e4  push    rdi
0x18000f2e5  sub     rsp, 68h
0x18000f2e9  mov     rbp, [rsp+88h+arg_28]
0x18000f2f1  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000f2f8  mov     [rsp+88h+var_60], rbp; char *
0x18000f2fd  mov     edi, edx
0x18000f2ff  mov     rsi, rcx
0x18000f302  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000f307  xor     edx, edx; int
0x18000f309  mov     ebx, eax
0x18000f30b  test    eax, eax
0x18000f30d  jg      short loc_18000F313
0x18000f30f  mov     ecx, eax
0x18000f311  jmp     short loc_18000F31C
0x18000f313  movzx   ecx, bx
0x18000f316  or      ecx, 80070000h; this
0x18000f31c  mov     [rsp+88h+var_38], ecx
0x18000f320  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f325  mov     [rsp+88h+var_40], edx
0x18000f329  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000f330  mov     [rsp+88h+var_50], rdx
0x18000f335  xor     r9d, r9d
0x18000f338  mov     [rsp+88h+var_34], eax
0x18000f33c  mov     rcx, rsi
0x18000f33f  lea     rax, [rsp+88h+var_38]
0x18000f344  mov     [rsp+88h+var_30], edx
0x18000f348  mov     [rsp+88h+var_58], rax
0x18000f34d  mov     [rsp+88h+var_60], rbp
0x18000f352  mov     [rsp+88h+var_68], rdx
0x18000f357  mov     edx, edi
0x18000f359  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000f35e  mov     ecx, ebx; dwErrCode
0x18000f360  call    cs:__imp_SetLastError
0x18000f366  mov     eax, ebx
0x18000f368  add     rsp, 68h
0x18000f36c  pop     rdi
0x18000f36d  pop     rsi
0x18000f36e  pop     rbp
0x18000f36f  pop     rbx
0x18000f370  retn
```
