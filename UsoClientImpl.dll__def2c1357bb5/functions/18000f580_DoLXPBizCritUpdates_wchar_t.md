# DoLXPBizCritUpdates(wchar_t *)

- ea: `0x18000f580`
- end: `0x18000f789`
- name: `?DoLXPBizCritUpdates@@YAXPEA_W@Z`
- size: `521`
- prototype: `void __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180009380`
- `0x18000b828`
- `0x18000eca8`
- `0x18000f0a4`
- `0x18000f21c`
- `0x18000f580`
- `0x1800338a4`
- `0x180033f14`
- `0x180034a30`
- `0x180036b10`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f647`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f65a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f72b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f72b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f652`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f716`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f652`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f716`

## string_xrefs

- `0x18000f5c8`: `DoLXPBizCritUpdates`
- `0x18000f5be`: `%ProgramFiles(x86)%\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe`
- `0x18000f777`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
void __fastcall DoLXPBizCritUpdates(wchar_t *a1)
{
  __int64 traits_2_unsigned_short; // rax
  const char *v3; // r9
  __int64 v4; // r11
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 DockedClient; // rax
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, wchar_t *, int *, BSTR *); // r15
  OLECHAR *v10; // rsi
  DWORD LastError; // ebx
  int v12; // eax
  const wchar_t *v13; // rax
  int v14; // [rsp+28h] [rbp-39h]
  HANDLE hObject[2]; // [rsp+38h] [rbp-29h] BYREF
  const wchar_t *v16; // [rsp+48h] [rbp-19h] BYREF
  __int64 v17; // [rsp+50h] [rbp-11h]
  __int128 v18; // [rsp+58h] [rbp-9h] BYREF
  __int128 v19; // [rsp+68h] [rbp+7h]
  int v20; // [rsp+78h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  hObject[0] = 0;
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"DoLXPBizCritUpdates",
                              L"%ProgramFiles(x86)%\\Microsoft\\EdgeUpdate\\MicrosoftEdgeUpdate.exe",
                              0);
  if ( traits_2_unsigned_short == v4
    || (v5 = (traits_2_unsigned_short - (__int64)L"DoLXPBizCritUpdates") >> 1, v6 = -1, v5 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v3);
  }
  v16 = L"DoLXPBizCritUpdates";
  v17 = v5;
  TryCreateUnsharableFile(hObject, &v16);
  if ( (((unsigned __int64)hObject[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v20 = 0;
    bstrString = 0;
    DockedClient = Windows::DockedHelpers::GetDockedClient(&v16);
    v8 = *(_QWORD *)DockedClient;
    v9 = *(__int64 (__fastcall **)(__int64, wchar_t *, int *, BSTR *))(**(_QWORD **)DockedClient + 72LL);
    v10 = bstrString;
    if ( bstrString )
    {
      LastError = GetLastError();
      SysFreeString(v10);
      SetLastError(LastError);
    }
    bstrString = 0;
    v12 = v9(v8, a1, &v20, &bstrString);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
        (const char *)(unsigned int)v12,
        v14);
    if ( v16 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v16 + 16LL))(v16);
    v18 = 0;
    v19 = 0;
    do
      ++v6;
    while ( bstrString[v6] );
    std::wstring::_Construct<1,wchar_t const *>(&v18);
    v13 = (const wchar_t *)&v18;
    if ( *((_QWORD *)&v19 + 1) > 7u )
      v13 = (const wchar_t *)v18;
    v16 = v13;
    v17 = v19;
    ReportTelemetryForExpeditedStoreUpdates(L"LXP", &v16, a1);
    std::wstring::~wstring(&v18);
    ReportUOWorkCompleted(L"LXP", v20);
    if ( bstrString )
      SysFreeString(bstrString);
  }
  else
  {
    ClientCoreTelemetry::BizCriticalStoreAppInstallAlreadyRunning();
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
}

```

## disassembly

```asm
0x18000f580  mov     rax, rsp
0x18000f583  mov     [rax+10h], rbx
0x18000f587  mov     [rax+18h], rsi
0x18000f58b  mov     [rax+20h], rdi
0x18000f58f  push    rbp
0x18000f590  push    r12
0x18000f592  push    r13
0x18000f594  push    r14
0x18000f596  push    r15
0x18000f598  lea     rbp, [rax-5Fh]
0x18000f59c  sub     rsp, 90h
0x18000f5a3  mov     rax, cs:__security_cookie
0x18000f5aa  xor     rax, rsp
0x18000f5ad  mov     [rbp+57h+var_30], rax
0x18000f5b1  mov     r12, rcx
0x18000f5b4  xor     r13d, r13d
0x18000f5b7  mov     [rbp+57h+hObject], r13
0x18000f5bb  xor     r8d, r8d
0x18000f5be  lea     r11, aProgramfilesX8; "%ProgramFiles(x86)%\\Microsoft\\EdgeUpd"...
0x18000f5c5  mov     rdx, r11
0x18000f5c8  lea     rbx, aDolxpbizcritup; "DoLXPBizCritUpdates"
0x18000f5cf  mov     rcx, rbx
0x18000f5d2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000f5d7  cmp     rax, r11
0x18000f5da  jz      loc_18000F773
0x18000f5e0  sub     rax, rbx
0x18000f5e3  sar     rax, 1
0x18000f5e6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f5ea  cmp     rax, rdi
0x18000f5ed  jz      loc_18000F773
0x18000f5f3  mov     [rbp+57h+var_70], rbx
0x18000f5f7  mov     [rbp+57h+var_68], rax
0x18000f5fb  lea     rdx, [rbp+57h+var_70]
0x18000f5ff  lea     rcx, [rbp+57h+hObject]
0x18000f603  call    ?TryCreateUnsharableFile@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@2@@Z; TryCreateUnsharableFile(wil::basic_zstring_view<wchar_t>)
0x18000f608  nop
0x18000f609  mov     rax, [rbp+57h+hObject]
0x18000f60d  inc     rax
0x18000f610  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f616  jnz     short loc_18000F622
0x18000f618  call    ?BizCriticalStoreAppInstallAlreadyRunning@ClientCoreTelemetry@@SAXXZ; ClientCoreTelemetry::BizCriticalStoreAppInstallAlreadyRunning(void)
0x18000f61d  jmp     loc_18000F71D
0x18000f622  mov     [rbp+57h+var_40], r13d
0x18000f626  mov     [rbp+57h+bstrString], r13
0x18000f62a  lea     rcx, [rbp+57h+var_70]
0x18000f62e  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x18000f633  nop
0x18000f634  mov     r14, [rax]
0x18000f637  mov     rax, [r14]
0x18000f63a  mov     r15, [rax+48h]
0x18000f63e  mov     rsi, [rbp+57h+bstrString]
0x18000f642  test    rsi, rsi
0x18000f645  jz      short loc_18000F660
0x18000f647  call    cs:__imp_GetLastError
0x18000f64d  mov     ebx, eax
0x18000f64f  mov     rcx, rsi; bstrString
0x18000f652  call    cs:__imp_SysFreeString
0x18000f658  mov     ecx, ebx; dwErrCode
0x18000f65a  call    cs:__imp_SetLastError
0x18000f660  mov     [rbp+57h+bstrString], r13
0x18000f664  lea     r9, [rbp+57h+bstrString]
0x18000f668  lea     r8, [rbp+57h+var_40]
0x18000f66c  mov     rdx, r12
0x18000f66f  mov     rcx, r14
0x18000f672  mov     rax, r15
0x18000f675  call    _guard_dispatch_icall
0x18000f67a  mov     rcx, [rbp+5Fh]; this
0x18000f67e  test    eax, eax
0x18000f680  js      loc_18000F75E
0x18000f686  mov     rcx, [rbp+57h+var_70]
0x18000f68a  test    rcx, rcx
0x18000f68d  jz      short loc_18000F69C
0x18000f68f  mov     rax, [rcx]
0x18000f692  mov     rax, [rax+10h]
0x18000f696  call    _guard_dispatch_icall
0x18000f69b  nop
0x18000f69c  xorps   xmm0, xmm0
0x18000f69f  movups  [rbp+57h+var_60], xmm0
0x18000f6a3  xorps   xmm1, xmm1
0x18000f6a6  movdqu  [rbp+57h+var_50], xmm1
0x18000f6ab  mov     rdx, [rbp+57h+bstrString]
0x18000f6af  inc     rdi
0x18000f6b2  cmp     [rdx+rdi*2], r13w
0x18000f6b7  jnz     short loc_18000F6AF
0x18000f6b9  mov     r8, rdi
0x18000f6bc  lea     rcx, [rbp+57h+var_60]
0x18000f6c0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000f6c5  nop
0x18000f6c6  lea     rax, [rbp+57h+var_60]
0x18000f6ca  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18000f6cf  cmova   rax, qword ptr [rbp+57h+var_60]
0x18000f6d4  mov     [rbp+57h+var_70], rax
0x18000f6d8  mov     rax, qword ptr [rbp+57h+var_50]
0x18000f6dc  mov     [rbp+57h+var_68], rax
0x18000f6e0  mov     r8, r12
0x18000f6e3  lea     rdx, [rbp+57h+var_70]
0x18000f6e7  lea     rcx, aLxp; "LXP"
0x18000f6ee  call    ?ReportTelemetryForExpeditedStoreUpdates@@YAXPEB_WV?$basic_zstring_view@_W@wil@@PEA_W@Z; ReportTelemetryForExpeditedStoreUpdates(wchar_t const *,wil::basic_zstring_view<wchar_t>,wchar_t *)
0x18000f6f3  nop
0x18000f6f4  lea     rcx, [rbp+57h+var_60]; void *
0x18000f6f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f6fd  mov     edx, [rbp+57h+var_40]; int
0x18000f700  lea     rcx, aLxp; "LXP"
0x18000f707  call    ?ReportUOWorkCompleted@@YAXPEB_WH@Z; ReportUOWorkCompleted(wchar_t const *,int)
0x18000f70c  nop
0x18000f70d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000f711  test    rcx, rcx
0x18000f714  jz      short loc_18000F71D
0x18000f716  call    cs:__imp_SysFreeString
0x18000f71c  nop
0x18000f71d  mov     rcx, [rbp+57h+hObject]; hObject
0x18000f721  lea     rax, [rcx-1]
0x18000f725  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f729  ja      short loc_18000F731
0x18000f72b  call    cs:__imp_CloseHandle
0x18000f731  mov     rcx, [rbp+57h+var_30]
0x18000f735  xor     rcx, rsp; StackCookie
0x18000f738  call    __security_check_cookie
0x18000f73d  lea     r11, [rsp+0B0h+var_20]
0x18000f745  mov     rbx, [r11+38h]
0x18000f749  mov     rsi, [r11+40h]
0x18000f74d  mov     rdi, [r11+48h]
0x18000f751  mov     rsp, r11
0x18000f754  pop     r15
0x18000f756  pop     r14
0x18000f758  pop     r13
0x18000f75a  pop     r12
0x18000f75c  pop     rbp
0x18000f75d  retn
0x18000f75e  mov     r9d, eax; char *
0x18000f761  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000f768  mov     edx, 1C2h; void *
0x18000f76d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000f773  mov     rcx, [rbp+5Fh]; this
0x18000f777  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000f77e  mov     edx, 0C9h; void *
0x18000f783  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
