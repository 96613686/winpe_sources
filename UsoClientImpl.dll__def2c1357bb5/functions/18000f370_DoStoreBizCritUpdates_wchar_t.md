# DoStoreBizCritUpdates(wchar_t *)

- ea: `0x18000f370`
- end: `0x18000f579`
- name: `?DoStoreBizCritUpdates@@YAXPEA_W@Z`
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
- `0x18000f370`
- `0x1800338a4`
- `0x180033f14`
- `0x180034a30`
- `0x180036b10`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f44a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f44a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f51b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f51b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f506`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f506`

## string_xrefs

- `0x18000f3b8`: `DoStoreBizCritUpdates`
- `0x18000f567`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall DoStoreBizCritUpdates(wchar_t *a1)
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
                              L"DoStoreBizCritUpdates",
                              &dword_18006847C,
                              0);
  if ( traits_2_unsigned_short == v4
    || (v5 = (traits_2_unsigned_short - (__int64)L"DoStoreBizCritUpdates") >> 1, v6 = -1, v5 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v3);
  }
  v16 = L"DoStoreBizCritUpdates";
  v17 = v5;
  TryCreateUnsharableFile(hObject, &v16);
  if ( (((unsigned __int64)hObject[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v20 = 0;
    bstrString = 0;
    DockedClient = Windows::DockedHelpers::GetDockedClient(&v16);
    v8 = *(_QWORD *)DockedClient;
    v9 = *(__int64 (__fastcall **)(__int64, wchar_t *, int *, BSTR *))(**(_QWORD **)DockedClient + 48LL);
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
        (void *)0x1AE,
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
    ReportTelemetryForExpeditedStoreUpdates(L"IA", &v16, a1);
    std::wstring::~wstring(&v18);
    ReportUOWorkCompleted(L"IA", v20);
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
0x18000f370  mov     rax, rsp
0x18000f373  mov     [rax+10h], rbx
0x18000f377  mov     [rax+18h], rsi
0x18000f37b  mov     [rax+20h], rdi
0x18000f37f  push    rbp
0x18000f380  push    r12
0x18000f382  push    r13
0x18000f384  push    r14
0x18000f386  push    r15
0x18000f388  lea     rbp, [rax-5Fh]
0x18000f38c  sub     rsp, 90h
0x18000f393  mov     rax, cs:__security_cookie
0x18000f39a  xor     rax, rsp
0x18000f39d  mov     [rbp+57h+var_30], rax
0x18000f3a1  mov     r12, rcx
0x18000f3a4  xor     r13d, r13d
0x18000f3a7  mov     [rbp+57h+hObject], r13
0x18000f3ab  xor     r8d, r8d
0x18000f3ae  lea     r11, dword_18006847C
0x18000f3b5  mov     rdx, r11
0x18000f3b8  lea     rbx, aDostorebizcrit; "DoStoreBizCritUpdates"
0x18000f3bf  mov     rcx, rbx
0x18000f3c2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000f3c7  cmp     rax, r11
0x18000f3ca  jz      loc_18000F563
0x18000f3d0  sub     rax, rbx
0x18000f3d3  sar     rax, 1
0x18000f3d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f3da  cmp     rax, rdi
0x18000f3dd  jz      loc_18000F563
0x18000f3e3  mov     [rbp+57h+var_70], rbx
0x18000f3e7  mov     [rbp+57h+var_68], rax
0x18000f3eb  lea     rdx, [rbp+57h+var_70]
0x18000f3ef  lea     rcx, [rbp+57h+hObject]
0x18000f3f3  call    ?TryCreateUnsharableFile@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@2@@Z; TryCreateUnsharableFile(wil::basic_zstring_view<wchar_t>)
0x18000f3f8  nop
0x18000f3f9  mov     rax, [rbp+57h+hObject]
0x18000f3fd  inc     rax
0x18000f400  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f406  jnz     short loc_18000F412
0x18000f408  call    ?BizCriticalStoreAppInstallAlreadyRunning@ClientCoreTelemetry@@SAXXZ; ClientCoreTelemetry::BizCriticalStoreAppInstallAlreadyRunning(void)
0x18000f40d  jmp     loc_18000F50D
0x18000f412  mov     [rbp+57h+var_40], r13d
0x18000f416  mov     [rbp+57h+bstrString], r13
0x18000f41a  lea     rcx, [rbp+57h+var_70]
0x18000f41e  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x18000f423  nop
0x18000f424  mov     r14, [rax]
0x18000f427  mov     rax, [r14]
0x18000f42a  mov     r15, [rax+30h]
0x18000f42e  mov     rsi, [rbp+57h+bstrString]
0x18000f432  test    rsi, rsi
0x18000f435  jz      short loc_18000F450
0x18000f437  call    cs:__imp_GetLastError
0x18000f43d  mov     ebx, eax
0x18000f43f  mov     rcx, rsi; bstrString
0x18000f442  call    cs:__imp_SysFreeString
0x18000f448  mov     ecx, ebx; dwErrCode
0x18000f44a  call    cs:__imp_SetLastError
0x18000f450  mov     [rbp+57h+bstrString], r13
0x18000f454  lea     r9, [rbp+57h+bstrString]
0x18000f458  lea     r8, [rbp+57h+var_40]
0x18000f45c  mov     rdx, r12
0x18000f45f  mov     rcx, r14
0x18000f462  mov     rax, r15
0x18000f465  call    _guard_dispatch_icall
0x18000f46a  mov     rcx, [rbp+5Fh]; this
0x18000f46e  test    eax, eax
0x18000f470  js      loc_18000F54E
0x18000f476  mov     rcx, [rbp+57h+var_70]
0x18000f47a  test    rcx, rcx
0x18000f47d  jz      short loc_18000F48C
0x18000f47f  mov     rax, [rcx]
0x18000f482  mov     rax, [rax+10h]
0x18000f486  call    _guard_dispatch_icall
0x18000f48b  nop
0x18000f48c  xorps   xmm0, xmm0
0x18000f48f  movups  [rbp+57h+var_60], xmm0
0x18000f493  xorps   xmm1, xmm1
0x18000f496  movdqu  [rbp+57h+var_50], xmm1
0x18000f49b  mov     rdx, [rbp+57h+bstrString]
0x18000f49f  inc     rdi
0x18000f4a2  cmp     [rdx+rdi*2], r13w
0x18000f4a7  jnz     short loc_18000F49F
0x18000f4a9  mov     r8, rdi
0x18000f4ac  lea     rcx, [rbp+57h+var_60]
0x18000f4b0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000f4b5  nop
0x18000f4b6  lea     rax, [rbp+57h+var_60]
0x18000f4ba  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18000f4bf  cmova   rax, qword ptr [rbp+57h+var_60]
0x18000f4c4  mov     [rbp+57h+var_70], rax
0x18000f4c8  mov     rax, qword ptr [rbp+57h+var_50]
0x18000f4cc  mov     [rbp+57h+var_68], rax
0x18000f4d0  mov     r8, r12
0x18000f4d3  lea     rdx, [rbp+57h+var_70]
0x18000f4d7  lea     rcx, aIa; "IA"
0x18000f4de  call    ?ReportTelemetryForExpeditedStoreUpdates@@YAXPEB_WV?$basic_zstring_view@_W@wil@@PEA_W@Z; ReportTelemetryForExpeditedStoreUpdates(wchar_t const *,wil::basic_zstring_view<wchar_t>,wchar_t *)
0x18000f4e3  nop
0x18000f4e4  lea     rcx, [rbp+57h+var_60]; void *
0x18000f4e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f4ed  mov     edx, [rbp+57h+var_40]; int
0x18000f4f0  lea     rcx, aIa; "IA"
0x18000f4f7  call    ?ReportUOWorkCompleted@@YAXPEB_WH@Z; ReportUOWorkCompleted(wchar_t const *,int)
0x18000f4fc  nop
0x18000f4fd  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000f501  test    rcx, rcx
0x18000f504  jz      short loc_18000F50D
0x18000f506  call    cs:__imp_SysFreeString
0x18000f50c  nop
0x18000f50d  mov     rcx, [rbp+57h+hObject]; hObject
0x18000f511  lea     rax, [rcx-1]
0x18000f515  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f519  ja      short loc_18000F521
0x18000f51b  call    cs:__imp_CloseHandle
0x18000f521  mov     rcx, [rbp+57h+var_30]
0x18000f525  xor     rcx, rsp; StackCookie
0x18000f528  call    __security_check_cookie
0x18000f52d  lea     r11, [rsp+0B0h+var_20]
0x18000f535  mov     rbx, [r11+38h]
0x18000f539  mov     rsi, [r11+40h]
0x18000f53d  mov     rdi, [r11+48h]
0x18000f541  mov     rsp, r11
0x18000f544  pop     r15
0x18000f546  pop     r14
0x18000f548  pop     r13
0x18000f54a  pop     r12
0x18000f54c  pop     rbp
0x18000f54d  retn
0x18000f54e  mov     r9d, eax; char *
0x18000f551  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000f558  mov     edx, 1AEh; void *
0x18000f55d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000f563  mov     rcx, [rbp+5Fh]; this
0x18000f567  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000f56e  mov     edx, 0C9h; void *
0x18000f573  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
