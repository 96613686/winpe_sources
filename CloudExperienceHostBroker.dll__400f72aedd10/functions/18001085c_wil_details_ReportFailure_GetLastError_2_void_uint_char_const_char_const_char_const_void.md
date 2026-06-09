# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18001085c`
- end: `0x1800108e8`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `140`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018bc8`

## callees

- `0x180006a0c`
- `0x180009768`
- `0x18000c088`
- `0x18001085c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108d7`

## string_xrefs

- `0x18001086d`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x1800108a5`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
                    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
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
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x18001085c  push    rbx
0x18001085e  push    rbp
0x18001085f  push    rsi
0x180010860  push    rdi
0x180010861  sub     rsp, 68h
0x180010865  mov     rbp, [rsp+88h+arg_28]
0x18001086d  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180010874  mov     [rsp+88h+var_60], rbp; char *
0x180010879  mov     edi, edx
0x18001087b  mov     rsi, rcx
0x18001087e  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180010883  xor     edx, edx; int
0x180010885  mov     ebx, eax
0x180010887  test    eax, eax
0x180010889  jg      short loc_18001088F
0x18001088b  mov     ecx, eax
0x18001088d  jmp     short loc_180010898
0x18001088f  movzx   ecx, bx
0x180010892  or      ecx, 80070000h; this
0x180010898  mov     [rsp+88h+var_38], ecx
0x18001089c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800108a1  mov     [rsp+88h+var_40], edx
0x1800108a5  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800108ac  mov     [rsp+88h+var_34], eax
0x1800108b0  xor     r9d, r9d
0x1800108b3  lea     rax, [rsp+88h+var_38]
0x1800108b8  mov     [rsp+88h+var_30], edx
0x1800108bc  mov     [rsp+88h+var_58], rax
0x1800108c1  mov     rcx, rsi
0x1800108c4  mov     [rsp+88h+var_60], rbp
0x1800108c9  mov     [rsp+88h+var_68], rdx
0x1800108ce  mov     edx, edi
0x1800108d0  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800108d5  mov     ecx, ebx; dwErrCode
0x1800108d7  call    cs:__imp_SetLastError
0x1800108dd  mov     eax, ebx
0x1800108df  add     rsp, 68h
0x1800108e3  pop     rdi
0x1800108e4  pop     rsi
0x1800108e5  pop     rbp
0x1800108e6  pop     rbx
0x1800108e7  retn
```
