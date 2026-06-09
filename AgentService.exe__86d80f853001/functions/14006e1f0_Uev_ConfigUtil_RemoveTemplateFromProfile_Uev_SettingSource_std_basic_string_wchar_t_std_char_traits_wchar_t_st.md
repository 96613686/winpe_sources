# Uev::ConfigUtil::RemoveTemplateFromProfile(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006e1f0`
- end: `0x14006e40e`
- name: `?RemoveTemplateFromProfile@ConfigUtil@Uev@@UEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAJ@Z`
- size: `542`
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
- `0x14006ba18`
- `0x14006e1f0`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e351`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e351`
- `ADVAPI32!RegDeleteValueW` at `0x14006e3a9`
- `ADVAPI32!RegDeleteValueW` at `0x14006e3a9`

## string_xrefs

- `0x14006e3dd`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall Uev::ConfigUtil::RemoveTemplateFromProfile(
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
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+48h] [rbp-B8h]
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+68h] [rbp-98h]
  _QWORD v22[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v23[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+C0h] [rbp-40h] BYREF

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
    *a5 = RegOpenKeyExW(*v15, v13, 0, 0x102u, &hKey);
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
      *a5 = RegDeleteValueW(hKey, a4);
    }
    Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  }
  return *a5 == 0;
}

```

## disassembly

```asm
0x14006e1f0  push    rbp
0x14006e1f2  push    rbx
0x14006e1f3  push    rsi
0x14006e1f4  push    rdi
0x14006e1f5  push    r14
0x14006e1f7  push    r15
0x14006e1f9  lea     rbp, [rsp-18h]
0x14006e1fe  sub     rsp, 118h
0x14006e205  mov     rax, cs:__security_cookie
0x14006e20c  xor     rax, rsp
0x14006e20f  mov     [rbp+40h+var_40], rax
0x14006e213  mov     rdi, r9
0x14006e216  mov     r14, r8
0x14006e219  mov     r15d, edx
0x14006e21c  mov     rsi, rcx
0x14006e21f  mov     rbx, [rbp+40h+arg_20]
0x14006e223  mov     dword ptr [rbx], 2
0x14006e229  lea     eax, [rdx-2]
0x14006e22c  cmp     eax, 1
0x14006e22f  ja      loc_14006E3BB
0x14006e235  mov     [rsp+140h+hKey], 0
0x14006e23e  mov     r8d, edx
0x14006e241  lea     rdx, [rsp+140h+var_C8]
0x14006e246  call    ?GetConfigRoot@ConfigUtil@Uev@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4SettingSource@2@@Z; Uev::ConfigUtil::GetConfigRoot(Uev::SettingSource)
0x14006e24b  nop
0x14006e24c  mov     r8d, 1
0x14006e252  lea     rdx, SubBlock; "\\"
0x14006e259  mov     rcx, rax; Src
0x14006e25c  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14006e261  xorps   xmm0, xmm0
0x14006e264  movups  [rsp+140h+var_E8], xmm0
0x14006e269  xorps   xmm1, xmm1
0x14006e26c  movdqu  [rsp+140h+var_D8], xmm1
0x14006e272  movups  xmm0, xmmword ptr [rax]
0x14006e275  movups  [rsp+140h+var_E8], xmm0
0x14006e27a  movups  xmm1, xmmword ptr [rax+10h]
0x14006e27e  movups  [rsp+140h+var_D8], xmm1
0x14006e283  mov     qword ptr [rax+10h], 0
0x14006e28b  mov     qword ptr [rax+18h], 7
0x14006e293  xor     ecx, ecx
0x14006e295  mov     [rax], cx
0x14006e298  lea     r8, ?profileKeyName@ConfigUtil@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::ConfigUtil::profileKeyName
0x14006e29f  lea     rdx, [rsp+140h+var_E8]
0x14006e2a4  lea     rcx, [rbp+40h+pExceptionObject]
0x14006e2a8  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006e2ad  nop
0x14006e2ae  mov     r8d, 1
0x14006e2b4  lea     rdx, SubBlock; "\\"
0x14006e2bb  mov     rcx, rax; Src
0x14006e2be  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14006e2c3  xorps   xmm0, xmm0
0x14006e2c6  movups  [rsp+140h+var_108], xmm0
0x14006e2cb  xorps   xmm1, xmm1
0x14006e2ce  movdqu  [rsp+140h+var_F8], xmm1
0x14006e2d4  movups  xmm0, xmmword ptr [rax]
0x14006e2d7  movups  [rsp+140h+var_108], xmm0
0x14006e2dc  movups  xmm1, xmmword ptr [rax+10h]
0x14006e2e0  movups  [rsp+140h+var_F8], xmm1
0x14006e2e5  mov     qword ptr [rax+10h], 0
0x14006e2ed  mov     qword ptr [rax+18h], 7
0x14006e2f5  xor     ecx, ecx
0x14006e2f7  mov     [rax], cx
0x14006e2fa  mov     r8, r14
0x14006e2fd  lea     rdx, [rsp+140h+var_108]
0x14006e302  lea     rcx, [rbp+40h+var_A8]
0x14006e306  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006e30b  mov     r14, rax
0x14006e30e  cmp     qword ptr [rax+18h], 7
0x14006e313  jbe     short loc_14006E318
0x14006e315  mov     r14, [rax]
0x14006e318  lea     eax, [r15-1]
0x14006e31c  mov     rcx, rsi
0x14006e31f  test    eax, 0FFFFFFFDh
0x14006e324  mov     rax, [rsi]
0x14006e327  jz      short loc_14006E32F
0x14006e329  mov     rax, [rax+28h]
0x14006e32d  jmp     short loc_14006E333
0x14006e32f  mov     rax, [rax+20h]
0x14006e333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e338  lea     rcx, [rsp+140h+hKey]
0x14006e33d  mov     [rsp+140h+phkResult], rcx; phkResult
0x14006e342  mov     r9d, 102h; samDesired
0x14006e348  xor     r8d, r8d; ulOptions
0x14006e34b  mov     rdx, r14; lpSubKey
0x14006e34e  mov     rcx, [rax]; hKey
0x14006e351  call    cs:__imp_RegOpenKeyExW
0x14006e357  mov     [rbx], eax
0x14006e359  lea     rcx, [rbp+40h+var_A8]
0x14006e35d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006e362  nop
0x14006e363  lea     rcx, [rsp+140h+var_108]
0x14006e368  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006e36d  nop
0x14006e36e  lea     rcx, [rbp+40h+pExceptionObject]
0x14006e372  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006e377  nop
0x14006e378  lea     rcx, [rsp+140h+var_E8]
0x14006e37d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006e382  nop
0x14006e383  lea     rcx, [rsp+140h+var_C8]
0x14006e388  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006e38d  cmp     dword ptr [rbx], 0
0x14006e390  jnz     short loc_14006E3B1
0x14006e392  cmp     qword ptr [rdi+18h], 7
0x14006e397  jbe     short loc_14006E39C
0x14006e399  mov     rdi, [rdi]
0x14006e39c  mov     rcx, [rsp+140h+hKey]; hKey
0x14006e3a1  test    rcx, rcx
0x14006e3a4  jz      short loc_14006E3DD
0x14006e3a6  mov     rdx, rdi; lpValueName
0x14006e3a9  call    cs:__imp_RegDeleteValueW
0x14006e3af  mov     [rbx], eax
0x14006e3b1  lea     rcx, [rsp+140h+hKey]
0x14006e3b6  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006e3bb  cmp     dword ptr [rbx], 0
0x14006e3be  setz    al
0x14006e3c1  mov     rcx, [rbp+40h+var_40]
0x14006e3c5  xor     rcx, rsp; StackCookie
0x14006e3c8  call    __security_check_cookie
0x14006e3cd  add     rsp, 118h
0x14006e3d4  pop     r15
0x14006e3d6  pop     r14
0x14006e3d8  pop     rdi
0x14006e3d9  pop     rsi
0x14006e3da  pop     rbx
0x14006e3db  pop     rbp
0x14006e3dc  retn
0x14006e3dd  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006e3e4  lea     rcx, [rsp+140h+var_C8]
0x14006e3e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006e3ee  nop
0x14006e3ef  lea     rdx, [rsp+140h+var_C8]
0x14006e3f4  lea     rcx, [rbp+40h+pExceptionObject]
0x14006e3f8  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006e3fd  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006e404  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x14006e408  call    _CxxThrowException_0
```
