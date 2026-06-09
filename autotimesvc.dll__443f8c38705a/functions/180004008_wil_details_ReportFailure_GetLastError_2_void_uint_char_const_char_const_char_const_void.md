# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004008`
- end: `0x180004099`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180007e24`

## callees

- `0x180003c3c`
- `0x180004008`
- `0x180006ca0`
- `0x180007278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004088`

## string_xrefs

- `0x180004019`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`
- `0x180004051`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

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
                    (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
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
    (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
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
0x180004008  push    rbx
0x18000400a  push    rbp
0x18000400b  push    rsi
0x18000400c  push    rdi
0x18000400d  sub     rsp, 68h
0x180004011  mov     rbp, [rsp+88h+arg_28]
0x180004019  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180004020  mov     [rsp+88h+var_60], rbp; char *
0x180004025  mov     edi, edx
0x180004027  mov     rsi, rcx
0x18000402a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000402f  xor     edx, edx; int
0x180004031  mov     ebx, eax
0x180004033  test    eax, eax
0x180004035  jg      short loc_18000403B
0x180004037  mov     ecx, eax
0x180004039  jmp     short loc_180004044
0x18000403b  movzx   ecx, bx
0x18000403e  or      ecx, 80070000h; this
0x180004044  mov     [rsp+88h+var_38], ecx
0x180004048  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000404d  mov     [rsp+88h+var_40], edx
0x180004051  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180004058  mov     [rsp+88h+var_50], rdx
0x18000405d  xor     r9d, r9d
0x180004060  mov     [rsp+88h+var_34], eax
0x180004064  mov     rcx, rsi
0x180004067  lea     rax, [rsp+88h+var_38]
0x18000406c  mov     [rsp+88h+var_30], edx
0x180004070  mov     [rsp+88h+var_58], rax
0x180004075  mov     [rsp+88h+var_60], rbp
0x18000407a  mov     [rsp+88h+var_68], rdx
0x18000407f  mov     edx, edi
0x180004081  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180004086  mov     ecx, ebx; dwErrCode
0x180004088  call    cs:__imp_SetLastError
0x18000408e  mov     eax, ebx
0x180004090  add     rsp, 68h
0x180004094  pop     rdi
0x180004095  pop     rsi
0x180004096  pop     rbp
0x180004097  pop     rbx
0x180004098  retn
```
