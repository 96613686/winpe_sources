# WerpAddIfRegisteredForAppLocalDump

- ea: `0x180066d40`
- end: `0x180066f06`
- name: `WerpAddIfRegisteredForAppLocalDump`
- size: `454`
- prototype: `__int64 __fastcall(void *, HANDLE ProcessHandle)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001c650`
- `0x180025bec`
- `0x180040f08`
- `0x180045184`
- `0x180049ee4`
- `0x180050db0`
- `0x180061db4`
- `0x180066d40`
- `0x180097ce0`
- `0x1800a3a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e25`
- `ntdll!wcsstr` at `0x180066e76`
- `ntdll!wcsstr` at `0x180066e76`
- `USERENV!GetAppContainerFolderPath` at `0x180066e41`
- `USERENV!GetAppContainerFolderPath` at `0x180066e41`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066e1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180066e1b`

## pseudocode

```c
__int64 __fastcall WerpAddIfRegisteredForAppLocalDump(void *a1, HANDLE ProcessHandle, __int64 a3)
{
  unsigned int v6; // r8d
  struct CReport *ReportFromHandle; // rdi
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  LPWSTR *v10; // rax
  __int64 v11; // rax
  wchar_t *v12; // rbx
  __int64 v14; // [rsp+28h] [rbp-81h] BYREF
  __int64 v15; // [rsp+30h] [rbp-79h] BYREF
  PSID Sid; // [rsp+38h] [rbp-71h] BYREF
  wchar_t *Str[4]; // [rsp+40h] [rbp-69h] BYREF
  wchar_t pszDest[64]; // [rsp+60h] [rbp-49h] BYREF

  Sid = 0;
  v15 = 0;
  v14 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(Str);
  if ( a1 && ProcessHandle && a3 )
  {
    if ( (int)WerpGetAppLocalDumpSubpath(ProcessHandle, pszDest, v6) >= 0 )
    {
      ReportFromHandle = GetReportFromHandle(a1);
      if ( ReportFromHandle )
      {
        if ( (int)UtilGetProcessAppContainerPackageSid(ProcessHandle) >= 0 )
        {
          v10 = (LPWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&v15);
          if ( ConvertSidToStringSidW(Sid, v10) )
          {
            v11 = ___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___0__Z(&v14);
            if ( (int)GetAppContainerFolderPath(v15, v11) >= 0
              && (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                        Str,
                        L"%ws\\%ws",
                        v14,
                        pszDest) >= 0 )
            {
              v12 = Str[0];
              if ( !wcsstr(Str[0], L"..") )
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                  (char *)ReportFromHandle + 46512,
                  v12);
            }
          }
          else
          {
            GetLastError();
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v9 = 167;
LABEL_19:
          WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
        }
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 166;
      goto LABEL_19;
    }
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Str);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v15);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&Sid);
  return 0;
}

```

## disassembly

```asm
0x180066d40  mov     [rsp-8+arg_10], rbx
0x180066d45  push    rbp
0x180066d46  push    rsi
0x180066d47  push    rdi
0x180066d48  lea     rbp, [rsp-47h]
0x180066d4d  sub     rsp, 0F0h
0x180066d54  mov     rax, cs:__security_cookie
0x180066d5b  xor     rax, rsp
0x180066d5e  mov     [rbp+57h+var_20], rax
0x180066d62  mov     rdi, rcx
0x180066d65  mov     [rbp+57h+Sid], 0
0x180066d6d  lea     rcx, [rbp+57h+Str]; void *
0x180066d71  mov     [rbp+57h+var_D0], 0
0x180066d79  mov     rsi, r8
0x180066d7c  mov     [rsp+100h+var_D8], 0
0x180066d85  mov     rbx, rdx
0x180066d88  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180066d8d  test    rdi, rdi
0x180066d90  jz      loc_180066E92
0x180066d96  test    rbx, rbx
0x180066d99  jz      loc_180066E92
0x180066d9f  test    rsi, rsi
0x180066da2  jz      loc_180066E92
0x180066da8  lea     rdx, [rbp+57h+pszDest]; pszDest
0x180066dac  mov     rcx, rbx; hProcess
0x180066daf  call    ?WerpGetAppLocalDumpSubpath@@YAJPEAXPEA_WK@Z; WerpGetAppLocalDumpSubpath(void *,wchar_t *,ulong)
0x180066db4  test    eax, eax
0x180066db6  js      loc_180066EC0
0x180066dbc  mov     rcx, rdi; void *
0x180066dbf  call    ?GetReportFromHandle@@YAPEAVCReport@@PEAX@Z; GetReportFromHandle(void *)
0x180066dc4  mov     rdi, rax
0x180066dc7  test    rax, rax
0x180066dca  jnz     short loc_180066DF7
0x180066dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180066dd3  lea     rax, WPP_GLOBAL_Control
0x180066dda  cmp     rcx, rax
0x180066ddd  jz      loc_180066EC0
0x180066de3  test    byte ptr [rcx+1Ch], 1
0x180066de7  jz      loc_180066EC0
0x180066ded  mov     edx, 0A7h
0x180066df2  jmp     loc_180066EB0
0x180066df7  lea     rdx, [rbp+57h+Sid]
0x180066dfb  mov     rcx, rbx; ProcessHandle
0x180066dfe  call    ?UtilGetProcessAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x180066e03  test    eax, eax
0x180066e05  js      loc_180066EC0
0x180066e0b  lea     rcx, [rbp+57h+var_D0]
0x180066e0f  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180066e14  mov     rcx, [rbp+57h+Sid]; Sid
0x180066e18  mov     rdx, rax; StringSid
0x180066e1b  call    cs:__imp_ConvertSidToStringSidW
0x180066e21  test    eax, eax
0x180066e23  jnz     short loc_180066E30
0x180066e25  call    cs:__imp_GetLastError
0x180066e2b  jmp     loc_180066EC0
0x180066e30  lea     rcx, [rsp+100h+var_D8]
0x180066e35  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180066e3a  mov     rcx, [rbp+57h+var_D0]
0x180066e3e  mov     rdx, rax
0x180066e41  call    cs:__imp_GetAppContainerFolderPath
0x180066e47  test    eax, eax
0x180066e49  js      short loc_180066EC0
0x180066e4b  mov     r8, [rsp+100h+var_D8]
0x180066e50  lea     r9, [rbp+57h+pszDest]
0x180066e54  lea     rdx, aWsWs_0; "%ws\\%ws"
0x180066e5b  lea     rcx, [rbp+57h+Str]
0x180066e5f  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180066e64  test    eax, eax
0x180066e66  js      short loc_180066EC0
0x180066e68  mov     rbx, [rbp+57h+Str]
0x180066e6c  lea     rdx, SubStr; ".."
0x180066e73  mov     rcx, rbx; Str
0x180066e76  call    cs:__imp_wcsstr
0x180066e7c  test    rax, rax
0x180066e7f  jnz     short loc_180066EC0
0x180066e81  lea     rcx, [rdi+0B5B0h]
0x180066e88  mov     rdx, rbx
0x180066e8b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180066e90  jmp     short loc_180066EC0
0x180066e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e99  lea     rax, WPP_GLOBAL_Control
0x180066ea0  cmp     rcx, rax
0x180066ea3  jz      short loc_180066EC0
0x180066ea5  test    byte ptr [rcx+1Ch], 1
0x180066ea9  jz      short loc_180066EC0
0x180066eab  mov     edx, 0A6h
0x180066eb0  mov     rcx, [rcx+10h]
0x180066eb4  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180066ebb  call    WPP_SF_
0x180066ec0  lea     rcx, [rbp+57h+Str]; void *
0x180066ec4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180066ec9  lea     rcx, [rsp+100h+var_D8]
0x180066ece  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066ed3  lea     rcx, [rbp+57h+var_D0]
0x180066ed7  call    ??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x180066edc  lea     rcx, [rbp+57h+Sid]; void *
0x180066ee0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180066ee5  xor     eax, eax
0x180066ee7  mov     rcx, [rbp+57h+var_20]
0x180066eeb  xor     rcx, rsp; StackCookie
0x180066eee  call    __security_check_cookie
0x180066ef3  mov     rbx, [rsp+100h+arg_10]
0x180066efb  add     rsp, 0F0h
0x180066f02  pop     rdi
0x180066f03  pop     rsi
0x180066f04  pop     rbp
0x180066f05  retn
```
