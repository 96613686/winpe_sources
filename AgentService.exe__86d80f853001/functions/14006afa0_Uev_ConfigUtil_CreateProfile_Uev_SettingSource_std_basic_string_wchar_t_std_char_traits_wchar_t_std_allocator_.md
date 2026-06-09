# Uev::ConfigUtil::CreateProfile(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006afa0`
- end: `0x14006b1c0`
- name: `?CreateProfile@ConfigUtil@Uev@@UEAA_NW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@Z`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000bacc`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x1400231f8`
- `0x140025560`
- `0x14006afa0`
- `0x14006ba18`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14006b05c`
- `ADVAPI32!RegCreateKeyExW` at `0x14006b136`
- `ADVAPI32!RegCreateKeyExW` at `0x14006b05c`
- `ADVAPI32!RegCreateKeyExW` at `0x14006b136`

## string_xrefs

- `0x14006b189`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall Uev::ConfigUtil::CreateProfile(__int64 *a1, unsigned int a2, __int64 a3, LSTATUS *a4)
{
  __int64 ConfigRoot; // rax
  const WCHAR *v8; // rbx
  __int64 v9; // rax
  HKEY *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 *v13; // r9
  __int64 v14; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+80h] [rbp-80h] BYREF
  char v20[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v21[32]; // [rsp+E0h] [rbp-20h] BYREF

  *a4 = 2;
  if ( a2 - 2 <= 1 )
  {
    hKey = 0;
    ConfigRoot = Uev::ConfigUtil::GetConfigRoot((__int64)a1, (__int64)v20, a2);
    v8 = (const WCHAR *)ConfigRoot;
    if ( *(_QWORD *)(ConfigRoot + 24) > 7u )
      v8 = *(const WCHAR **)ConfigRoot;
    v9 = *a1;
    if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
      v10 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v9 + 40))(a1);
    else
      v10 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v9 + 32))(a1);
    *a4 = RegCreateKeyExW(*v10, v8, 0, 0, 0, 0x2011Du, 0, &hKey, 0);
    std::wstring::_Tidy_deallocate(v20);
    if ( !*a4 )
    {
      phkResult = 0;
      if ( qword_1400D1870 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v13 = &Uev::ConfigUtil::profileKeyName;
      if ( (unsigned __int64)qword_1400D1878 > 7 )
        v13 = (__int64 *)Uev::ConfigUtil::profileKeyName;
      std::wstring::wstring(v20, v11, v12, v13, qword_1400D1870, (void *)L"\\", 1);
      v14 = std::operator+<wchar_t>((__int64)v21, v20);
      if ( *(_QWORD *)(v14 + 24) > 7u )
        v14 = *(_QWORD *)v14;
      if ( !hKey )
      {
        std::wstring::wstring(v18, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, v18);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      *a4 = RegCreateKeyExW(hKey, (LPCWSTR)v14, 0, 0, 0, 0x20119u, 0, &phkResult, 0);
      std::wstring::_Tidy_deallocate(v21);
      std::wstring::_Tidy_deallocate(v20);
      Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&phkResult);
    }
    Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  }
  return *a4 == 0;
}

```

## disassembly

```asm
0x14006afa0  push    rbp
0x14006afa2  push    rbx
0x14006afa3  push    rsi
0x14006afa4  push    rdi
0x14006afa5  push    r14
0x14006afa7  push    r15
0x14006afa9  lea     rbp, [rsp-18h]
0x14006afae  sub     rsp, 118h
0x14006afb5  mov     rax, cs:__security_cookie
0x14006afbc  xor     rax, rsp
0x14006afbf  mov     [rbp+40h+var_40], rax
0x14006afc3  mov     rsi, r9
0x14006afc6  mov     r15, r8
0x14006afc9  mov     r14d, edx
0x14006afcc  mov     rdi, rcx
0x14006afcf  mov     dword ptr [r9], 2
0x14006afd6  lea     eax, [rdx-2]
0x14006afd9  cmp     eax, 1
0x14006afdc  ja      loc_14006B167
0x14006afe2  mov     [rsp+140h+hKey], 0
0x14006afeb  mov     r8d, edx
0x14006afee  lea     rdx, [rbp+40h+var_80]
0x14006aff2  call    ?GetConfigRoot@ConfigUtil@Uev@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4SettingSource@2@@Z; Uev::ConfigUtil::GetConfigRoot(Uev::SettingSource)
0x14006aff7  mov     rbx, rax
0x14006affa  cmp     qword ptr [rax+18h], 7
0x14006afff  jbe     short loc_14006B004
0x14006b001  mov     rbx, [rax]
0x14006b004  lea     eax, [r14-1]
0x14006b008  mov     rcx, rdi
0x14006b00b  test    eax, 0FFFFFFFDh
0x14006b010  mov     rax, [rdi]
0x14006b013  jz      short loc_14006B01B
0x14006b015  mov     rax, [rax+28h]
0x14006b019  jmp     short loc_14006B01F
0x14006b01b  mov     rax, [rax+20h]
0x14006b01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b024  mov     [rsp+140h+lpdwDisposition], 0; lpdwDisposition
0x14006b02d  lea     rcx, [rsp+140h+hKey]
0x14006b032  mov     [rsp+140h+phkResult], rcx; phkResult
0x14006b037  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006b040  mov     [rsp+140h+samDesired], 2011Dh; samDesired
0x14006b048  mov     [rsp+140h+dwOptions], 0; dwOptions
0x14006b050  xor     r9d, r9d; lpClass
0x14006b053  xor     r8d, r8d; Reserved
0x14006b056  mov     rdx, rbx; lpSubKey
0x14006b059  mov     rcx, [rax]; hKey
0x14006b05c  call    cs:__imp_RegCreateKeyExW
0x14006b062  mov     [rsi], eax
0x14006b064  lea     rcx, [rbp+40h+var_80]
0x14006b068  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b06d  cmp     dword ptr [rsi], 0
0x14006b070  jnz     loc_14006B15D
0x14006b076  mov     [rsp+140h+var_E8], 0
0x14006b07f  mov     rcx, cs:qword_1400D1870
0x14006b086  mov     rax, 7FFFFFFFFFFFFFFEh
0x14006b090  sub     rax, rcx
0x14006b093  cmp     rax, 1
0x14006b097  jb      loc_14006B1BA
0x14006b09d  lea     r9, ?profileKeyName@ConfigUtil@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::ConfigUtil::profileKeyName
0x14006b0a4  cmp     cs:qword_1400D1878, 7
0x14006b0ac  cmova   r9, cs:?profileKeyName@ConfigUtil@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::ConfigUtil::profileKeyName
0x14006b0b4  mov     [rsp+140h+lpSecurityAttributes], 1
0x14006b0bd  lea     rax, SubBlock; "\\"
0x14006b0c4  mov     qword ptr [rsp+140h+samDesired], rax
0x14006b0c9  mov     qword ptr [rsp+140h+dwOptions], rcx
0x14006b0ce  lea     rcx, [rbp+40h+var_80]
0x14006b0d2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14006b0d7  nop
0x14006b0d8  mov     r8, r15
0x14006b0db  lea     rdx, [rbp+40h+var_80]
0x14006b0df  lea     rcx, [rbp+40h+var_60]
0x14006b0e3  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x14006b0e8  nop
0x14006b0e9  cmp     qword ptr [rax+18h], 7
0x14006b0ee  jbe     short loc_14006B0F3
0x14006b0f0  mov     rax, [rax]
0x14006b0f3  mov     rcx, [rsp+140h+hKey]; hKey
0x14006b0f8  test    rcx, rcx
0x14006b0fb  jz      loc_14006B189
0x14006b101  mov     [rsp+140h+lpdwDisposition], 0; lpdwDisposition
0x14006b10a  lea     rdx, [rsp+140h+var_E8]
0x14006b10f  mov     [rsp+140h+phkResult], rdx; phkResult
0x14006b114  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006b11d  mov     [rsp+140h+samDesired], 20119h; samDesired
0x14006b125  mov     [rsp+140h+dwOptions], 0; dwOptions
0x14006b12d  xor     r9d, r9d; lpClass
0x14006b130  xor     r8d, r8d; Reserved
0x14006b133  mov     rdx, rax; lpSubKey
0x14006b136  call    cs:__imp_RegCreateKeyExW
0x14006b13c  mov     [rsi], eax
0x14006b13e  lea     rcx, [rbp+40h+var_60]
0x14006b142  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b147  nop
0x14006b148  lea     rcx, [rbp+40h+var_80]
0x14006b14c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b151  nop
0x14006b152  lea     rcx, [rsp+140h+var_E8]
0x14006b157  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006b15c  nop
0x14006b15d  lea     rcx, [rsp+140h+hKey]
0x14006b162  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006b167  cmp     dword ptr [rsi], 0
0x14006b16a  setz    al
0x14006b16d  mov     rcx, [rbp+40h+var_40]
0x14006b171  xor     rcx, rsp; StackCookie
0x14006b174  call    __security_check_cookie
0x14006b179  add     rsp, 118h
0x14006b180  pop     r15
0x14006b182  pop     r14
0x14006b184  pop     rdi
0x14006b185  pop     rsi
0x14006b186  pop     rbx
0x14006b187  pop     rbp
0x14006b188  retn
0x14006b189  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006b190  lea     rcx, [rsp+140h+var_E0]
0x14006b195  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006b19a  nop
0x14006b19b  lea     rdx, [rsp+140h+var_E0]
0x14006b1a0  lea     rcx, [rbp+40h+pExceptionObject]
0x14006b1a4  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006b1a9  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006b1b0  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x14006b1b4  call    _CxxThrowException_0
0x14006b1ba  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
