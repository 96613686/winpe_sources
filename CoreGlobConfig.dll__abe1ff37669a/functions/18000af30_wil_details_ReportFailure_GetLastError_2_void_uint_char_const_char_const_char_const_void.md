# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000af30`
- end: `0x18000afc1`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d38c`

## callees

- `0x180005c3c`
- `0x180007150`
- `0x180007754`
- `0x18000af30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afb0`

## string_xrefs

- `0x18000af41`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18000af79`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
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
                    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
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
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
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
0x18000af30  push    rbx
0x18000af32  push    rbp
0x18000af33  push    rsi
0x18000af34  push    rdi
0x18000af35  sub     rsp, 68h
0x18000af39  mov     rbp, [rsp+88h+arg_28]
0x18000af41  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000af48  mov     [rsp+88h+var_60], rbp; char *
0x18000af4d  mov     edi, edx
0x18000af4f  mov     rsi, rcx
0x18000af52  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000af57  xor     edx, edx; int
0x18000af59  mov     ebx, eax
0x18000af5b  test    eax, eax
0x18000af5d  jg      short loc_18000AF63
0x18000af5f  mov     ecx, eax
0x18000af61  jmp     short loc_18000AF6C
0x18000af63  movzx   ecx, bx
0x18000af66  or      ecx, 80070000h; this
0x18000af6c  mov     [rsp+88h+var_38], ecx
0x18000af70  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000af75  mov     [rsp+88h+var_40], edx
0x18000af79  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000af80  mov     [rsp+88h+var_50], rdx
0x18000af85  xor     r9d, r9d
0x18000af88  mov     [rsp+88h+var_34], eax
0x18000af8c  mov     rcx, rsi
0x18000af8f  lea     rax, [rsp+88h+var_38]
0x18000af94  mov     [rsp+88h+var_30], edx
0x18000af98  mov     [rsp+88h+var_58], rax
0x18000af9d  mov     [rsp+88h+var_60], rbp
0x18000afa2  mov     [rsp+88h+var_68], rdx
0x18000afa7  mov     edx, edi
0x18000afa9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000afae  mov     ecx, ebx; dwErrCode
0x18000afb0  call    cs:__imp_SetLastError
0x18000afb6  mov     eax, ebx
0x18000afb8  add     rsp, 68h
0x18000afbc  pop     rdi
0x18000afbd  pop     rsi
0x18000afbe  pop     rbp
0x18000afbf  pop     rbx
0x18000afc0  retn
```
