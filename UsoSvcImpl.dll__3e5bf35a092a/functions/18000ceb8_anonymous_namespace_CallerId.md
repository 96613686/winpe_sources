# _anonymous_namespace_::CallerId

- ea: `0x18000ceb8`
- end: `0x18000d3f6`
- name: `_anonymous_namespace_::CallerId`
- size: `1342`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d400`

## callees

- `0x18000cc74`
- `0x18000ceb8`
- `0x18000ed3c`
- `0x18000edb0`
- `0x18000f3a8`
- `0x18000f780`
- `0x1800108b4`
- `0x180010e80`
- `0x180010f24`
- `0x1800112d0`
- `0x180011320`
- `0x18001151c`
- `0x180011680`
- `0x180042350`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d36a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cf91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d36a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000cf98`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d160`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d1ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d371`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000cf98`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d160`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d1ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d371`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000cef0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000cef0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000cf25`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000cf25`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cf4a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000cf4a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000cff7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000cff7`

## string_xrefs

- `0x18000d3ad`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::CallerId(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // eax
  char *v4; // rbx
  const char *v5; // r9
  __int64 result; // rax
  const char *v7; // r9
  __int64 v8; // r8
  __int128 *v9; // r14
  char *v10; // rdi
  __int64 traits_2_unsigned_short; // rax
  __int64 v12; // rax
  __int64 ServiceName; // rdi
  _QWORD *v14; // r14
  char *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  char v19; // di
  char v20; // di
  unsigned int v21; // [rsp+20h] [rbp-348h]
  _BYTE v23[32]; // [rsp+50h] [rbp-318h] BYREF
  char *v24; // [rsp+70h] [rbp-2F8h]
  _BYTE v25[32]; // [rsp+78h] [rbp-2F0h] BYREF
  _BYTE v26[32]; // [rsp+98h] [rbp-2D0h] BYREF
  _BYTE v27[32]; // [rsp+B8h] [rbp-2B0h] BYREF
  unsigned int Pid; // [rsp+D8h] [rbp-290h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-288h] BYREF
  __int64 v30[2]; // [rsp+F0h] [rbp-278h]
  DWORD dwSize; // [rsp+100h] [rbp-268h] BYREF
  _QWORD v32[2]; // [rsp+108h] [rbp-260h] BYREF
  __int64 v33; // [rsp+118h] [rbp-250h]
  unsigned __int64 v34; // [rsp+120h] [rbp-248h]
  WCHAR ExeName[264]; // [rsp+130h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  v2 = CoImpersonateClient();
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v2,
        v21);
    Pid = 0;
    v3 = I_RpcBindingInqLocalClientPID(0, &Pid);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x11D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
        (const char *)v3,
        v21);
    v4 = (char *)OpenProcess(0x400u, 0, Pid);
    v24 = v4;
    if ( ((unsigned __int64)(v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a1);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      CoRevertToSelf();
      return a1;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl'::`2'::impl) )
    {
      memset(ExeName, 0, 0x208u);
      dwSize = 260;
      if ( !QueryFullProcessImageNameW(v4, 0, ExeName, &dwSize) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x12E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
          v7);
      v29 = 0;
      v30[0] = 0;
      v30[1] = 0;
      v8 = -1;
      do
        ++v8;
      while ( ExeName[v8] );
      std::wstring::_Construct<1,wchar_t const *>(&v29);
      v9 = &v29;
      if ( v30[1] > 7uLL )
        v9 = (__int128 *)v29;
      if ( v30[0] < 0xBuLL )
      {
        v12 = -1;
      }
      else
      {
        v10 = (char *)v9 + 2 * v30[0];
        traits_2_unsigned_short = anonymous_namespace_::__std_search_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                    v9,
                                    v10,
                                    L"svchost.exe",
                                    11);
        if ( (char *)traits_2_unsigned_short == v10 )
          goto LABEL_21;
        v12 = (traits_2_unsigned_short - (__int64)v9) >> 1;
      }
      if ( v12 != -1 )
      {
        ServiceName = anonymous_namespace_::GetServiceName(v25, Pid);
        if ( v30[0] == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        std::wstring::wstring(v23, v30[0], L":", 1);
        std::operator+<wchar_t>(a1, v23, ServiceName);
        std::wstring::~wstring(v23);
        std::wstring::~wstring(v25);
        std::wstring::~wstring(&v29);
        CloseHandle(v4);
        CoRevertToSelf();
        return a1;
      }
LABEL_21:
      *(_OWORD *)a1 = v29;
      *(_OWORD *)(a1 + 16) = *(_OWORD *)v30;
      v30[0] = 0;
      v30[1] = 7;
      LOWORD(v29) = 0;
      std::wstring::~wstring(&v29);
      CloseHandle(v4);
      CoRevertToSelf();
      return a1;
    }
    wil::QueryFullProcessImageNameW<std::wstring,256>(v32, v4);
    v14 = v32;
    if ( v34 > 7 )
      v14 = (_QWORD *)v32[0];
    if ( (unsigned __int64)v33 < 0xB
      || (v15 = (char *)v14 + 2 * v33,
          v16 = anonymous_namespace_::__std_search_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                  v14,
                  v15,
                  L"svchost.exe",
                  11),
          (char *)v16 == v15)
      || (v16 - (__int64)v14) >> 1 == -1 )
    {
      v18 = std::wstring::wstring(v25, v32);
      v19 = 48;
    }
    else
    {
      v17 = anonymous_namespace_::GetServiceName(v27, Pid);
      if ( v33 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(v23, v33, L":", 1);
      v18 = std::operator+<wchar_t>(v26, v23, v17);
      v19 = -82;
    }
    std::wstring::wstring(a1, v18);
    v20 = v19 | 1;
    if ( (v20 & 0x10) != 0 )
    {
      v20 &= ~0x10u;
      std::wstring::~wstring(v25);
    }
    if ( (v20 & 8) != 0 )
    {
      v20 &= ~8u;
      std::wstring::~wstring(v26);
    }
    if ( (v20 & 4) != 0 )
    {
      v20 &= ~4u;
      std::wstring::~wstring(v23);
    }
    if ( (v20 & 2) != 0 )
      std::wstring::~wstring(v27);
    std::wstring::~wstring(v32);
    CloseHandle(v4);
    CoRevertToSelf();
    result = a1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x13A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      v5);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a1);
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ceb8  mov     [rsp+arg_8], rbx
0x18000cebd  mov     [rsp+arg_10], rsi
0x18000cec2  push    rdi
0x18000cec3  push    r14
0x18000cec5  push    r15
0x18000cec7  sub     rsp, 350h
0x18000cece  mov     rax, cs:__security_cookie
0x18000ced5  xor     rax, rsp
0x18000ced8  mov     [rsp+368h+var_28], rax
0x18000cee0  mov     rsi, rcx
0x18000cee3  mov     [rsp+368h+var_320], rcx
0x18000cee8  xor     r15d, r15d
0x18000ceeb  mov     [rsp+368h+var_328], r15d
0x18000cef0  call    cs:__imp_CoImpersonateClient
0x18000cef6  mov     rcx, [rsp+368h]; this
0x18000cefe  test    eax, eax
0x18000cf00  js      loc_18000D3AA
0x18000cf06  mov     [rsp+368h+var_324], 1
0x18000cf0b  mov     [rsp+368h+var_328], 20h ; ' '
0x18000cf13  mov     [rsp+368h+Pid], r15d
0x18000cf1b  lea     rdx, [rsp+368h+Pid]; Pid
0x18000cf23  xor     ecx, ecx; Binding
0x18000cf25  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000cf2b  mov     rcx, [rsp+368h]; this
0x18000cf33  test    eax, eax
0x18000cf35  jnz     loc_18000D3BF
0x18000cf3b  mov     r8d, [rsp+368h+Pid]; dwProcessId
0x18000cf43  xor     edx, edx; bInheritHandle
0x18000cf45  mov     ecx, 400h; dwDesiredAccess
0x18000cf4a  call    cs:__imp_OpenProcess
0x18000cf50  mov     rbx, rax
0x18000cf53  mov     [rsp+368h+var_2F8], rax
0x18000cf58  inc     rax
0x18000cf5b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000cf61  jnz     short loc_18000CFA6
0x18000cf63  xorps   xmm0, xmm0
0x18000cf66  movups  xmmword ptr [rsi], xmm0
0x18000cf69  mov     [rsi+10h], r15
0x18000cf6d  mov     [rsi+18h], r15
0x18000cf71  xor     r8d, r8d
0x18000cf74  lea     rdx, S1
0x18000cf7b  mov     rcx, rsi
0x18000cf7e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000cf83  nop
0x18000cf84  lea     rcx, [rbx-1]
0x18000cf88  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000cf8c  ja      short loc_18000CF98
0x18000cf8e  mov     rcx, rbx; hObject
0x18000cf91  call    cs:__imp_CloseHandle
0x18000cf97  nop
0x18000cf98  call    cs:__imp_CoRevertToSelf
0x18000cf9e  mov     rax, rsi
0x18000cfa1  jmp     loc_18000D381
0x18000cfa6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl(void)'::`2'::impl
0x18000cfad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(void)
0x18000cfb2  test    al, al
0x18000cfb4  jnz     loc_18000D1C8
0x18000cfba  xor     edx, edx; Val
0x18000cfbc  mov     r8d, 208h; Size
0x18000cfc2  lea     rcx, [rsp+368h+ExeName]; void *
0x18000cfca  call    memset
0x18000cfcf  mov     [rsp+368h+dwSize], 104h
0x18000cfda  mov     rdi, [rsp+368h]
0x18000cfe2  lea     r9, [rsp+368h+dwSize]; lpdwSize
0x18000cfea  lea     r8, [rsp+368h+ExeName]; lpExeName
0x18000cff2  xor     edx, edx; dwFlags
0x18000cff4  mov     rcx, rbx; hProcess
0x18000cff7  call    cs:__imp_QueryFullProcessImageNameW
0x18000cffd  test    eax, eax
0x18000cfff  jz      loc_18000D3D4
0x18000d005  xorps   xmm0, xmm0
0x18000d008  movups  [rsp+368h+var_288], xmm0
0x18000d010  mov     [rsp+368h+var_278], r15
0x18000d018  mov     [rsp+368h+var_278+8], r15
0x18000d020  lea     rax, [rsp+368h+ExeName]
0x18000d028  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d02c  inc     r8
0x18000d02f  cmp     [rax+r8*2], r15w
0x18000d034  jnz     short loc_18000D02C
0x18000d036  lea     rdx, [rsp+368h+ExeName]
0x18000d03e  lea     rcx, [rsp+368h+var_288]
0x18000d046  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d04b  nop
0x18000d04c  lea     r14, [rsp+368h+var_288]
0x18000d054  cmp     [rsp+368h+var_278+8], 7
0x18000d05d  cmova   r14, qword ptr [rsp+368h+var_288]
0x18000d066  mov     rax, [rsp+368h+var_278]
0x18000d06e  cmp     rax, 0Bh
0x18000d072  jb      short loc_18000D0A1
0x18000d074  lea     rdi, [r14+rax*2]
0x18000d078  mov     r9d, 0Bh
0x18000d07e  lea     r8, aSvchostExe; "svchost.exe"
0x18000d085  mov     rdx, rdi
0x18000d088  mov     rcx, r14
0x18000d08b  call    _anonymous_namespace_____std_search_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000d090  cmp     rax, rdi
0x18000d093  jz      loc_18000D16E
0x18000d099  sub     rax, r14
0x18000d09c  sar     rax, 1
0x18000d09f  jmp     short loc_18000D0A5
0x18000d0a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d0a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d0a9  jz      loc_18000D16E
0x18000d0af  mov     edx, [rsp+368h+Pid]
0x18000d0b6  lea     rcx, [rsp+368h+var_2F0]
0x18000d0bb  call    _anonymous_namespace___GetServiceName
0x18000d0c0  mov     rdi, rax
0x18000d0c3  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000d0cd  mov     rdx, [rsp+368h+var_278]
0x18000d0d5  sub     rcx, rdx
0x18000d0d8  cmp     rcx, 1
0x18000d0dc  jb      loc_18000D3E9
0x18000d0e2  lea     r9, [rsp+368h+var_288]
0x18000d0ea  cmp     [rsp+368h+var_278+8], 7
0x18000d0f3  cmova   r9, qword ptr [rsp+368h+var_288]
0x18000d0fc  mov     [rsp+368h+var_338], 1; __int64
0x18000d105  lea     rax, asc_1800F9CB8; ":"
0x18000d10c  mov     [rsp+368h+Src], rax; Src
0x18000d111  mov     [rsp+368h+var_348], rdx; __int64
0x18000d116  lea     rcx, [rsp+368h+var_318]; void *
0x18000d11b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18000d120  nop
0x18000d121  mov     r8, rdi
0x18000d124  lea     rdx, [rsp+368h+var_318]
0x18000d129  mov     rcx, rsi
0x18000d12c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x18000d131  nop
0x18000d132  lea     rcx, [rsp+368h+var_318]; void *
0x18000d137  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d13c  nop
0x18000d13d  lea     rcx, [rsp+368h+var_2F0]; void *
0x18000d142  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d147  nop
0x18000d148  lea     rcx, [rsp+368h+var_288]; void *
0x18000d150  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d155  nop
0x18000d156  mov     rcx, rbx; hObject
0x18000d159  call    cs:__imp_CloseHandle
0x18000d15f  nop
0x18000d160  call    cs:__imp_CoRevertToSelf
0x18000d166  mov     rax, rsi
0x18000d169  jmp     loc_18000D381
0x18000d16e  movups  xmm0, [rsp+368h+var_288]
0x18000d176  movups  xmmword ptr [rsi], xmm0
0x18000d179  movups  xmm1, xmmword ptr [rsp+368h+var_278]
0x18000d181  movups  xmmword ptr [rsi+10h], xmm1
0x18000d185  mov     [rsp+368h+var_278], r15
0x18000d18d  mov     [rsp+368h+var_278+8], 7
0x18000d199  mov     word ptr [rsp+368h+var_288], r15w
0x18000d1a2  lea     rcx, [rsp+368h+var_288]; void *
0x18000d1aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d1af  nop
0x18000d1b0  mov     rcx, rbx; hObject
0x18000d1b3  call    cs:__imp_CloseHandle
0x18000d1b9  nop
0x18000d1ba  call    cs:__imp_CoRevertToSelf
0x18000d1c0  mov     rax, rsi
0x18000d1c3  jmp     loc_18000D381
0x18000d1c8  mov     rdx, rbx
0x18000d1cb  lea     rcx, [rsp+368h+var_260]
0x18000d1d3  call    ??$QueryFullProcessImageNameW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAXK@Z; wil::QueryFullProcessImageNameW<std::wstring,256>(void *,ulong)
0x18000d1d8  nop
0x18000d1d9  lea     r14, [rsp+368h+var_260]
0x18000d1e1  cmp     [rsp+368h+var_248], 7
0x18000d1ea  cmova   r14, [rsp+368h+var_260]
0x18000d1f3  mov     rax, [rsp+368h+var_250]
0x18000d1fb  cmp     rax, 0Bh
0x18000d1ff  jb      loc_18000D2DC
0x18000d205  lea     rdi, [r14+rax*2]
0x18000d209  mov     r9d, 0Bh
0x18000d20f  lea     r8, aSvchostExe; "svchost.exe"
0x18000d216  mov     rdx, rdi
0x18000d219  mov     rcx, r14
0x18000d21c  call    _anonymous_namespace_____std_search_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000d221  cmp     rax, rdi
0x18000d224  jz      loc_18000D2DC
0x18000d22a  sub     rax, r14
0x18000d22d  sar     rax, 1
0x18000d230  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d234  jz      loc_18000D2DC
0x18000d23a  mov     edx, [rsp+368h+Pid]
0x18000d241  lea     rcx, [rsp+368h+var_2B0]
0x18000d249  call    _anonymous_namespace___GetServiceName
0x18000d24e  mov     rdi, rax
0x18000d251  mov     [rsp+368h+var_328], 22h ; '"'
0x18000d259  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000d263  mov     rdx, [rsp+368h+var_250]
0x18000d26b  sub     rcx, rdx
0x18000d26e  cmp     rcx, 1
0x18000d272  jb      loc_18000D3EF
0x18000d278  lea     r9, [rsp+368h+var_260]
0x18000d280  cmp     [rsp+368h+var_248], 7
0x18000d289  cmova   r9, [rsp+368h+var_260]
0x18000d292  mov     [rsp+368h+var_338], 1; __int64
0x18000d29b  lea     rax, asc_1800F9CB8; ":"
0x18000d2a2  mov     [rsp+368h+Src], rax; Src
0x18000d2a7  mov     [rsp+368h+var_348], rdx; __int64
0x18000d2ac  lea     rcx, [rsp+368h+var_318]; void *
0x18000d2b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18000d2b6  nop
0x18000d2b7  mov     [rsp+368h+var_328], 0A6h
0x18000d2bf  mov     r8, rdi
0x18000d2c2  lea     rdx, [rsp+368h+var_318]
0x18000d2c7  lea     rcx, [rsp+368h+var_2D0]
0x18000d2cf  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x18000d2d4  nop
0x18000d2d5  mov     edi, 0AEh
0x18000d2da  jmp     short loc_18000D2F4
0x18000d2dc  lea     rdx, [rsp+368h+var_260]
0x18000d2e4  lea     rcx, [rsp+368h+var_2F0]
0x18000d2e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d2ee  nop
0x18000d2ef  mov     edi, 30h ; '0'
0x18000d2f4  mov     [rsp+368h+var_328], edi
0x18000d2f8  mov     rdx, rax
0x18000d2fb  mov     rcx, rsi
0x18000d2fe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d303  or      edi, 1
0x18000d306  test    dil, 10h
0x18000d30a  jz      short loc_18000D31A
0x18000d30c  and     edi, 0FFFFFFEFh
0x18000d30f  lea     rcx, [rsp+368h+var_2F0]; void *
0x18000d314  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d319  nop
0x18000d31a  test    dil, 8
0x18000d31e  jz      short loc_18000D331
0x18000d320  and     edi, 0FFFFFFF7h
0x18000d323  lea     rcx, [rsp+368h+var_2D0]; void *
0x18000d32b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d330  nop
0x18000d331  test    dil, 4
0x18000d335  jz      short loc_18000D345
0x18000d337  and     edi, 0FFFFFFFBh
0x18000d33a  lea     rcx, [rsp+368h+var_318]; void *
0x18000d33f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d344  nop
0x18000d345  test    dil, 2
0x18000d349  jz      short loc_18000D359
0x18000d34b  lea     rcx, [rsp+368h+var_2B0]; void *
0x18000d353  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d358  nop
0x18000d359  lea     rcx, [rsp+368h+var_260]; void *
0x18000d361  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d366  nop
0x18000d367  mov     rcx, rbx; hObject
0x18000d36a  call    cs:__imp_CloseHandle
0x18000d370  nop
0x18000d371  call    cs:__imp_CoRevertToSelf
0x18000d377  mov     rax, rsi
0x18000d37a  jmp     short loc_18000D381
0x18000d37c  mov     rax, [rsp+368h+var_320]
0x18000d381  mov     rcx, [rsp+368h+var_28]
0x18000d389  xor     rcx, rsp; StackCookie
0x18000d38c  call    __security_check_cookie
0x18000d391  lea     r11, [rsp+368h+var_18]
0x18000d399  mov     rbx, [r11+28h]
0x18000d39d  mov     rsi, [r11+30h]
0x18000d3a1  mov     rsp, r11
0x18000d3a4  pop     r15
0x18000d3a6  pop     r14
0x18000d3a8  pop     rdi
0x18000d3a9  retn
0x18000d3aa  mov     r9d, eax; char *
0x18000d3ad  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000d3b4  mov     edx, 1262h; void *
0x18000d3b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d3bf  mov     r9d, eax; char *
0x18000d3c2  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000d3c9  mov     edx, 11Dh; void *
0x18000d3ce  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000d3d4  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000d3db  mov     edx, 12Eh; void *
0x18000d3e0  mov     rcx, rdi; this
0x18000d3e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000d3e9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000d3ef  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
