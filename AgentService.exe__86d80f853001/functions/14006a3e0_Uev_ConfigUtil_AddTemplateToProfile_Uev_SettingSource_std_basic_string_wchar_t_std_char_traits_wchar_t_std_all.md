# Uev::ConfigUtil::AddTemplateToProfile(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006a3e0`
- end: `0x14006a637`
- name: `?AddTemplateToProfile@ConfigUtil@Uev@@UEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAJ@Z`
- size: `599`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x140025560`
- `0x14006a3e0`
- `0x14006ba18`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14006a5d4`
- `ADVAPI32!RegSetValueExW` at `0x14006a5d4`
- `ADVAPI32!RegCreateKeyExW` at `0x14006a560`
- `ADVAPI32!RegCreateKeyExW` at `0x14006a560`

## string_xrefs

- `0x14006a608`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall Uev::ConfigUtil::AddTemplateToProfile(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        const WCHAR *a4,
        LSTATUS *a5)
{
  _QWORD *ConfigRoot; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // r14
  __int64 v14; // rax
  HKEY *v15; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int128 v20; // [rsp+78h] [rbp-88h] BYREF
  __int128 v21; // [rsp+88h] [rbp-78h]
  _QWORD v22[4]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v23[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E0h] [rbp-20h] BYREF

  *a5 = 2;
  if ( a2 - 2 <= 1 )
  {
    hKey = 0;
    ConfigRoot = (_QWORD *)Uev::ConfigUtil::GetConfigRoot((__int64)a1, (__int64)v22, a2);
    v9 = std::wstring::_Append<wchar_t>(ConfigRoot, L"\\", 1u);
    v20 = 0;
    v21 = 0;
    v20 = *(_OWORD *)v9;
    v21 = *((_OWORD *)v9 + 1);
    v9[2] = 0;
    v9[3] = 7;
    *(_WORD *)v9 = 0;
    v10 = (_QWORD *)std::operator+<wchar_t>((__int64)pExceptionObject, &v20);
    v11 = std::wstring::_Append<wchar_t>(v10, L"\\", 1u);
    v18 = 0;
    v19 = 0;
    v18 = *(_OWORD *)v11;
    v19 = *((_OWORD *)v11 + 1);
    v11[2] = 0;
    v11[3] = 7;
    *(_WORD *)v11 = 0;
    v12 = std::operator+<wchar_t>((__int64)v23, &v18);
    v13 = (const WCHAR *)v12;
    if ( *(_QWORD *)(v12 + 24) > 7u )
      v13 = *(const WCHAR **)v12;
    v14 = *a1;
    if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
      v15 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v14 + 40))(a1);
    else
      v15 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v14 + 32))(a1);
    *a5 = RegCreateKeyExW(*v15, v13, 0, 0, 0, 0x102u, 0, &hKey, 0);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(&v18);
    std::wstring::_Tidy_deallocate(pExceptionObject);
    std::wstring::_Tidy_deallocate(&v20);
    std::wstring::_Tidy_deallocate(v22);
    if ( !*a5 )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const WCHAR **)a4;
      if ( !hKey )
      {
        std::wstring::wstring(v22, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, v22);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      *a5 = RegSetValueExW(hKey, a4, 0, 1u, &Data, 0);
    }
    Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  }
  return *a5 == 0;
}

```

## disassembly

```asm
0x14006a3e0  push    rbp
0x14006a3e2  push    rbx
0x14006a3e3  push    rsi
0x14006a3e4  push    rdi
0x14006a3e5  push    r14
0x14006a3e7  push    r15
0x14006a3e9  lea     rbp, [rsp-38h]
0x14006a3ee  sub     rsp, 138h
0x14006a3f5  mov     rax, cs:__security_cookie
0x14006a3fc  xor     rax, rsp
0x14006a3ff  mov     [rbp+60h+var_40], rax
0x14006a403  mov     rdi, r9
0x14006a406  mov     r14, r8
0x14006a409  mov     r15d, edx
0x14006a40c  mov     rsi, rcx
0x14006a40f  mov     rbx, [rbp+60h+arg_20]
0x14006a416  mov     dword ptr [rbx], 2
0x14006a41c  lea     eax, [rdx-2]
0x14006a41f  cmp     eax, 1
0x14006a422  ja      loc_14006A5E6
0x14006a428  mov     [rsp+160h+hKey], 0
0x14006a431  mov     r8d, edx
0x14006a434  lea     rdx, [rbp+60h+var_C8]
0x14006a438  call    ?GetConfigRoot@ConfigUtil@Uev@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4SettingSource@2@@Z; Uev::ConfigUtil::GetConfigRoot(Uev::SettingSource)
0x14006a43d  nop
0x14006a43e  mov     r8d, 1
0x14006a444  lea     rdx, SubBlock; "\\"
0x14006a44b  mov     rcx, rax; Src
0x14006a44e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14006a453  xorps   xmm0, xmm0
0x14006a456  movups  [rsp+160h+var_E8], xmm0
0x14006a45b  xorps   xmm1, xmm1
0x14006a45e  movdqu  [rbp+60h+var_D8], xmm1
0x14006a463  movups  xmm0, xmmword ptr [rax]
0x14006a466  movups  [rsp+160h+var_E8], xmm0
0x14006a46b  movups  xmm1, xmmword ptr [rax+10h]
0x14006a46f  movups  [rbp+60h+var_D8], xmm1
0x14006a473  mov     qword ptr [rax+10h], 0
0x14006a47b  mov     qword ptr [rax+18h], 7
0x14006a483  xor     ecx, ecx
0x14006a485  mov     [rax], cx
0x14006a488  lea     r8, ?profileKeyName@ConfigUtil@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::ConfigUtil::profileKeyName
0x14006a48f  lea     rdx, [rsp+160h+var_E8]
0x14006a494  lea     rcx, [rbp+60h+pExceptionObject]
0x14006a498  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006a49d  nop
0x14006a49e  mov     r8d, 1
0x14006a4a4  lea     rdx, SubBlock; "\\"
0x14006a4ab  mov     rcx, rax; Src
0x14006a4ae  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14006a4b3  xorps   xmm0, xmm0
0x14006a4b6  movups  [rsp+160h+var_108], xmm0
0x14006a4bb  xorps   xmm1, xmm1
0x14006a4be  movdqu  [rsp+160h+var_F8], xmm1
0x14006a4c4  movups  xmm0, xmmword ptr [rax]
0x14006a4c7  movups  [rsp+160h+var_108], xmm0
0x14006a4cc  movups  xmm1, xmmword ptr [rax+10h]
0x14006a4d0  movups  [rsp+160h+var_F8], xmm1
0x14006a4d5  mov     qword ptr [rax+10h], 0
0x14006a4dd  mov     qword ptr [rax+18h], 7
0x14006a4e5  xor     ecx, ecx
0x14006a4e7  mov     [rax], cx
0x14006a4ea  mov     r8, r14
0x14006a4ed  lea     rdx, [rsp+160h+var_108]
0x14006a4f2  lea     rcx, [rbp+60h+var_A8]
0x14006a4f6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006a4fb  mov     r14, rax
0x14006a4fe  cmp     qword ptr [rax+18h], 7
0x14006a503  jbe     short loc_14006A508
0x14006a505  mov     r14, [rax]
0x14006a508  lea     eax, [r15-1]
0x14006a50c  mov     rcx, rsi
0x14006a50f  test    eax, 0FFFFFFFDh
0x14006a514  mov     rax, [rsi]
0x14006a517  jz      short loc_14006A51F
0x14006a519  mov     rax, [rax+28h]
0x14006a51d  jmp     short loc_14006A523
0x14006a51f  mov     rax, [rax+20h]
0x14006a523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a528  mov     [rsp+160h+lpdwDisposition], 0; lpdwDisposition
0x14006a531  lea     rcx, [rsp+160h+hKey]
0x14006a536  mov     [rsp+160h+phkResult], rcx; phkResult
0x14006a53b  mov     [rsp+160h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006a544  mov     [rsp+160h+samDesired], 102h; samDesired
0x14006a54c  mov     [rsp+160h+dwOptions], 0; dwOptions
0x14006a554  xor     r9d, r9d; lpClass
0x14006a557  xor     r8d, r8d; Reserved
0x14006a55a  mov     rdx, r14; lpSubKey
0x14006a55d  mov     rcx, [rax]; hKey
0x14006a560  call    cs:__imp_RegCreateKeyExW
0x14006a566  mov     [rbx], eax
0x14006a568  lea     rcx, [rbp+60h+var_A8]
0x14006a56c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a571  nop
0x14006a572  lea     rcx, [rsp+160h+var_108]
0x14006a577  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a57c  nop
0x14006a57d  lea     rcx, [rbp+60h+pExceptionObject]
0x14006a581  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a586  nop
0x14006a587  lea     rcx, [rsp+160h+var_E8]
0x14006a58c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a591  nop
0x14006a592  lea     rcx, [rbp+60h+var_C8]
0x14006a596  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a59b  cmp     dword ptr [rbx], 0
0x14006a59e  jnz     short loc_14006A5DC
0x14006a5a0  cmp     qword ptr [rdi+18h], 7
0x14006a5a5  jbe     short loc_14006A5AA
0x14006a5a7  mov     rdi, [rdi]
0x14006a5aa  mov     rcx, [rsp+160h+hKey]; hKey
0x14006a5af  test    rcx, rcx
0x14006a5b2  jz      short loc_14006A608
0x14006a5b4  mov     [rsp+160h+samDesired], 0; cbData
0x14006a5bc  lea     rax, Data
0x14006a5c3  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x14006a5c8  mov     r9d, 1; dwType
0x14006a5ce  xor     r8d, r8d; Reserved
0x14006a5d1  mov     rdx, rdi; lpValueName
0x14006a5d4  call    cs:__imp_RegSetValueExW
0x14006a5da  mov     [rbx], eax
0x14006a5dc  lea     rcx, [rsp+160h+hKey]
0x14006a5e1  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006a5e6  cmp     dword ptr [rbx], 0
0x14006a5e9  setz    al
0x14006a5ec  mov     rcx, [rbp+60h+var_40]
0x14006a5f0  xor     rcx, rsp; StackCookie
0x14006a5f3  call    __security_check_cookie
0x14006a5f8  add     rsp, 138h
0x14006a5ff  pop     r15
0x14006a601  pop     r14
0x14006a603  pop     rdi
0x14006a604  pop     rsi
0x14006a605  pop     rbx
0x14006a606  pop     rbp
0x14006a607  retn
0x14006a608  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006a60f  lea     rcx, [rbp+60h+var_C8]
0x14006a613  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006a618  nop
0x14006a619  lea     rdx, [rbp+60h+var_C8]
0x14006a61d  lea     rcx, [rbp+60h+pExceptionObject]
0x14006a621  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006a626  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006a62d  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x14006a631  call    _CxxThrowException_0
```
