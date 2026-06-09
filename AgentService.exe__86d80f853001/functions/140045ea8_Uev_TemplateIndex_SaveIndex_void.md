# Uev::TemplateIndex::SaveIndex(void)

- ea: `0x140045ea8`
- end: `0x1400462fc`
- name: `?SaveIndex@TemplateIndex@Uev@@QEBAXXZ`
- size: `1108`
- prototype: `void __fastcall(Uev::TemplateIndex *__hidden this)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003b0a0`
- `0x14003d840`
- `0x14003e0c0`
- `0x14003e500`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000bae4`
- `0x14000bc7c`
- `0x14000c1cc`
- `0x14000c4c8`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x140019190`
- `0x1400380d4`
- `0x14004550c`
- `0x140045ea8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140045f0c`
- `ADVAPI32!RegOpenKeyExW` at `0x140045f0c`
- `ADVAPI32!RegCreateKeyExW` at `0x14004603d`
- `ADVAPI32!RegCreateKeyExW` at `0x1400460ce`
- `ADVAPI32!RegCreateKeyExW` at `0x14004603d`
- `ADVAPI32!RegCreateKeyExW` at `0x1400460ce`
- `ADVAPI32!RegDeleteTreeW` at `0x140045f29`
- `ADVAPI32!RegDeleteTreeW` at `0x140045f29`

## string_xrefs

- `0x140046248`: `Attempting to assign an already-valid handle.`
- `0x140046217`: `Attempting to use an invalid handle.`
- `0x1400462cb`: `Attempting to use an invalid handle.`
- `0x1400461e6`: `Unable to open index registry key.`
- `0x14004629a`: `Unable to create a template index subkey.`
- `0x14004619d`: `Unable to create index registry key.`
- `0x140046154`: `Unable to access the template index.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall Uev::TemplateIndex::SaveIndex(Uev::TemplateIndex *this)
{
  const WCHAR *v2; // rbx
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  __int64 v5; // rcx
  LSTATUS v6; // eax
  __int64 v7; // r8
  _QWORD *v8; // rbx
  HKEY *v9; // rdx
  LPCWSTR *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rcx
  const WCHAR *v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  _BYTE v20[64]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+F0h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+110h] [rbp+10h] BYREF
  HKEY v25; // [rsp+118h] [rbp+18h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+120h] [rbp+20h] BYREF
  HKEY *v27; // [rsp+130h] [rbp+30h]
  unsigned __int64 v28; // [rsp+138h] [rbp+38h]

  hKey = 0;
  v2 = (const WCHAR *)&Uev::TemplateIndex::s_templateIndexKeyName;
  v3 = (const WCHAR *)&Uev::TemplateIndex::s_templateIndexKeyName;
  if ( (unsigned __int64)qword_1400D17E8 > 7 )
    v3 = Uev::TemplateIndex::s_templateIndexKeyName;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x3010Fu, &hKey);
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( v4 == 5 )
      {
        if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
          McTemplateU0q_EventWriteTransfer(v5, TemplateMsg_AccessDeniedToTheTemplateIndexKey, 5);
        std::wstring::wstring(v20, L"Unable to access the template index.");
        Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, v20);
        throw (Uev::TemplateIndexException *)pExceptionObject;
      }
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v5, TemplateMsg_UnableToOpenIndexRegistryKey, v4);
      std::wstring::wstring(v20, L"Unable to open index registry key.");
      Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, v20);
      throw (Uev::TemplateIndexException *)pExceptionObject;
    }
    if ( hKey )
    {
      std::wstring::wstring(lpSubKey, L"Attempting to assign an already-valid handle.");
      Uev::SmartHandleException::SmartHandleException(v20, lpSubKey);
      throw (Uev::SmartHandleException *)v20;
    }
    if ( (unsigned __int64)qword_1400D17E8 > 7 )
      v2 = Uev::TemplateIndex::s_templateIndexKeyName;
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0xF013Fu, 0, &hKey, 0);
    if ( v11 )
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v12, TemplateMsg_UnableToCreateTemplateIndexKey, v11);
      std::wstring::wstring(lpSubKey, L"Unable to create index registry key.");
      Uev::TemplateIndexException::TemplateIndexException(v20, lpSubKey);
      throw (Uev::TemplateIndexException *)v20;
    }
  }
  else
  {
    if ( !hKey )
    {
      std::wstring::wstring(lpSubKey, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(v20, lpSubKey);
      throw (Uev::SmartHandleException *)v20;
    }
    v6 = RegDeleteTreeW(hKey, 0);
    if ( v6 && (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
    {
      LODWORD(v25) = v6;
      v27 = &v25;
      v28 = 4;
      McGenEventWrite_EventWriteTransfer(
        UevAppAgentProvider_Context,
        TemplateMsg_UnableToDeleteExistingTemplateIndex,
        v7,
        2,
        lpSubKey);
    }
  }
  v8 = (_QWORD *)*((_QWORD *)this + 2);
  while ( 1 )
  {
    v8 = (_QWORD *)*v8;
    if ( v8 == *((_QWORD **)this + 2) )
      break;
    std::wstring::wstring(v23, v8 + 2);
    std::wstring::wstring(v22, v8 + 6);
    std::wstring::wstring(lpSubKey, v8 + 2);
    v9 = v27;
    v10 = lpSubKey;
    if ( (unsigned __int64)v27 >= v28 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(lpSubKey);
    }
    else
    {
      v27 = (HKEY *)((char *)v27 + 1);
      if ( v28 > 7 )
        v10 = (LPCWSTR *)lpSubKey[0];
      *(_DWORD *)((char *)v10 + 2 * (_QWORD)v9) = 92;
    }
    std::wstring::_Append<wchar_t>(lpSubKey);
    v25 = 0;
    v13 = (const WCHAR *)lpSubKey;
    if ( v28 > 7 )
      v13 = lpSubKey[0];
    if ( !hKey )
    {
      std::wstring::wstring(v20, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v20);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    v14 = RegCreateKeyExW(hKey, v13, 0, 0, 0, 0x20106u, 0, &v25, 0);
    if ( v14 )
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
      {
        v17 = std::wstring::c_str(lpSubKey, v15, v16, v14);
        McTemplateU0zq_EventWriteTransfer(v18, TemplateMsg_UnableToCreateTemplateIndexSubKey, v17, v19);
      }
      std::wstring::wstring(v20, L"Unable to create a template index subkey.");
      Uev::TemplateIndexException::TemplateIndexException(pExceptionObject, v20);
      throw (Uev::TemplateIndexException *)pExceptionObject;
    }
    Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&v25);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v23);
  }
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
}

```

## disassembly

```asm
0x140045ea8  push    rbp
0x140045eaa  push    rbx
0x140045eab  push    rsi
0x140045eac  push    rdi
0x140045ead  push    r13
0x140045eaf  push    r14
0x140045eb1  lea     rbp, [rsp-58h]
0x140045eb6  sub     rsp, 158h
0x140045ebd  mov     rax, cs:__security_cookie
0x140045ec4  xor     rax, rsp
0x140045ec7  mov     [rbp+80h+var_40], rax
0x140045ecb  mov     r14, rcx
0x140045ece  mov     [rbp+80h+hKey], 0
0x140045ed6  lea     rbx, ?s_templateIndexKeyName@TemplateIndex@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Uev::TemplateIndex::s_templateIndexKeyName
0x140045edd  mov     rdx, rbx
0x140045ee0  cmp     cs:qword_1400D17E8, 7
0x140045ee8  cmova   rdx, cs:?s_templateIndexKeyName@TemplateIndex@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; lpSubKey
0x140045ef0  lea     rax, [rbp+80h+hKey]
0x140045ef4  mov     [rsp+180h+phkResult], rax; phkResult
0x140045ef9  mov     r9d, 3010Fh; samDesired
0x140045eff  xor     r8d, r8d; ulOptions
0x140045f02  mov     rdi, 0FFFFFFFF80000002h
0x140045f09  mov     rcx, rdi; hKey
0x140045f0c  call    cs:__imp_RegOpenKeyExW
0x140045f12  test    eax, eax
0x140045f14  jnz     loc_140045FE2
0x140045f1a  mov     rcx, [rbp+80h+hKey]; hKey
0x140045f1e  test    rcx, rcx
0x140045f21  jz      loc_140046217
0x140045f27  xor     edx, edx; lpSubKey
0x140045f29  call    cs:__imp_RegDeleteTreeW
0x140045f2f  test    eax, eax
0x140045f31  jz      short loc_140045F71
0x140045f33  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140045f3a  jz      short loc_140045F71
0x140045f3c  mov     dword ptr [rbp+80h+var_68], eax
0x140045f3f  lea     rax, [rbp+80h+var_68]
0x140045f43  mov     [rbp+80h+var_50], rax
0x140045f47  mov     [rbp+80h+var_48], 4
0x140045f4f  lea     rax, [rbp+80h+lpSubKey]
0x140045f53  mov     [rsp+180h+phkResult], rax
0x140045f58  mov     r9d, 2
0x140045f5e  lea     rdx, TemplateMsg_UnableToDeleteExistingTemplateIndex
0x140045f65  lea     rcx, UevAppAgentProvider_Context
0x140045f6c  call    McGenEventWrite_EventWriteTransfer
0x140045f71  mov     rbx, [r14+10h]
0x140045f75  mov     r13d, 5Ch ; '\'
0x140045f7b  mov     rbx, [rbx]
0x140045f7e  cmp     rbx, [r14+10h]
0x140045f82  jz      loc_14004610B
0x140045f88  lea     rdx, [rbx+10h]
0x140045f8c  lea     rcx, [rbp+80h+var_90]
0x140045f90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045f95  nop
0x140045f96  lea     rsi, [rbx+30h]
0x140045f9a  mov     rdx, rsi
0x140045f9d  lea     rcx, [rbp+80h+var_B0]
0x140045fa1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045fa6  nop
0x140045fa7  lea     rdx, [rbx+10h]
0x140045fab  lea     rcx, [rbp+80h+lpSubKey]
0x140045faf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045fb4  nop
0x140045fb5  mov     rdx, [rbp+80h+var_50]
0x140045fb9  lea     rcx, [rbp+80h+lpSubKey]; Src
0x140045fbd  cmp     rdx, [rbp+80h+var_48]
0x140045fc1  jnb     loc_140046050
0x140045fc7  lea     rax, [rdx+1]
0x140045fcb  mov     [rbp+80h+var_50], rax
0x140045fcf  cmp     [rbp+80h+var_48], 7
0x140045fd4  cmova   rcx, [rbp+80h+lpSubKey]
0x140045fd9  mov     dword ptr [rcx+rdx*2], 5Ch ; '\'
0x140045fe0  jmp     short loc_140046060
0x140045fe2  cmp     eax, 2
0x140045fe5  jnz     loc_140046130
0x140045feb  cmp     [rbp+80h+hKey], 0
0x140045ff0  jnz     loc_140046248
0x140045ff6  cmp     cs:qword_1400D17E8, 7
0x140045ffe  cmova   rbx, cs:?s_templateIndexKeyName@TemplateIndex@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Uev::TemplateIndex::s_templateIndexKeyName
0x140046006  mov     [rsp+180h+lpdwDisposition], 0; lpdwDisposition
0x14004600f  lea     rax, [rbp+80h+hKey]
0x140046013  mov     [rsp+180h+var_148], rax; phkResult
0x140046018  mov     [rsp+180h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140046021  mov     [rsp+180h+samDesired], 0F013Fh; samDesired
0x140046029  mov     dword ptr [rsp+180h+phkResult], 0; dwOptions
0x140046031  xor     r9d, r9d; lpClass
0x140046034  xor     r8d, r8d; Reserved
0x140046037  mov     rdx, rbx; lpSubKey
0x14004603a  mov     rcx, rdi; hKey
0x14004603d  call    cs:__imp_RegCreateKeyExW
0x140046043  test    eax, eax
0x140046045  jnz     loc_140046185
0x14004604b  jmp     loc_140045F71
0x140046050  xor     r8b, r8b
0x140046053  mov     r9d, r13d
0x140046056  mov     edx, 1
0x14004605b  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x140046060  cmp     qword ptr [rbx+48h], 7
0x140046065  jbe     short loc_14004606A
0x140046067  mov     rsi, [rsi]
0x14004606a  mov     r8, [rbx+40h]
0x14004606e  mov     rdx, rsi
0x140046071  lea     rcx, [rbp+80h+lpSubKey]; Src
0x140046075  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14004607a  mov     [rbp+80h+var_68], 0
0x140046082  lea     rdx, [rbp+80h+lpSubKey]
0x140046086  cmp     [rbp+80h+var_48], 7
0x14004608b  cmova   rdx, [rbp+80h+lpSubKey]; lpSubKey
0x140046090  mov     rcx, [rbp+80h+hKey]; hKey
0x140046094  test    rcx, rcx
0x140046097  jz      loc_1400462CB
0x14004609d  mov     [rsp+180h+lpdwDisposition], 0; lpdwDisposition
0x1400460a6  lea     rax, [rbp+80h+var_68]
0x1400460aa  mov     [rsp+180h+var_148], rax; phkResult
0x1400460af  mov     [rsp+180h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400460b8  mov     [rsp+180h+samDesired], 20106h; samDesired
0x1400460c0  mov     dword ptr [rsp+180h+phkResult], 0; dwOptions
0x1400460c8  xor     r9d, r9d; lpClass
0x1400460cb  xor     r8d, r8d; Reserved
0x1400460ce  call    cs:__imp_RegCreateKeyExW
0x1400460d4  mov     r9d, eax
0x1400460d7  test    eax, eax
0x1400460d9  jnz     loc_140046279
0x1400460df  lea     rcx, [rbp+80h+var_68]
0x1400460e3  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x1400460e8  nop
0x1400460e9  lea     rcx, [rbp+80h+lpSubKey]
0x1400460ed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400460f2  nop
0x1400460f3  lea     rcx, [rbp+80h+var_B0]
0x1400460f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400460fc  nop
0x1400460fd  lea     rcx, [rbp+80h+var_90]
0x140046101  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140046106  jmp     loc_140045F7B
0x14004610b  lea     rcx, [rbp+80h+hKey]
0x14004610f  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x140046114  mov     rcx, [rbp+80h+var_40]
0x140046118  xor     rcx, rsp; StackCookie
0x14004611b  call    __security_check_cookie
0x140046120  add     rsp, 158h
0x140046127  pop     r14
0x140046129  pop     r13
0x14004612b  pop     rdi
0x14004612c  pop     rsi
0x14004612d  pop     rbx
0x14004612e  pop     rbp
0x14004612f  retn
0x140046130  mov     r8d, 5
0x140046136  cmp     eax, r8d
0x140046139  jnz     loc_1400461CE
0x14004613f  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140046146  jz      short loc_140046154
0x140046148  lea     rdx, TemplateMsg_AccessDeniedToTheTemplateIndexKey
0x14004614f  call    McTemplateU0q_EventWriteTransfer
0x140046154  lea     rdx, aUnableToAccess; "Unable to access the template index."
0x14004615b  lea     rcx, [rsp+180h+var_130]
0x140046160  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140046165  nop
0x140046166  lea     rdx, [rsp+180h+var_130]
0x14004616b  lea     rcx, [rbp+80h+pExceptionObject]
0x14004616f  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x140046174  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x14004617b  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x14004617f  call    _CxxThrowException_0
0x140046185  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x14004618c  jz      short loc_14004619D
0x14004618e  mov     r8d, eax
0x140046191  lea     rdx, TemplateMsg_UnableToCreateTemplateIndexKey
0x140046198  call    McTemplateU0q_EventWriteTransfer
0x14004619d  lea     rdx, aUnableToCreate; "Unable to create index registry key."
0x1400461a4  lea     rcx, [rbp+80h+lpSubKey]
0x1400461a8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400461ad  nop
0x1400461ae  lea     rdx, [rbp+80h+lpSubKey]
0x1400461b2  lea     rcx, [rsp+180h+var_130]
0x1400461b7  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x1400461bc  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x1400461c3  lea     rcx, [rsp+180h+var_130]; pExceptionObject
0x1400461c8  call    _CxxThrowException_0
0x1400461ce  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x1400461d5  jz      short loc_1400461E6
0x1400461d7  mov     r8d, eax
0x1400461da  lea     rdx, TemplateMsg_UnableToOpenIndexRegistryKey
0x1400461e1  call    McTemplateU0q_EventWriteTransfer
0x1400461e6  lea     rdx, aUnableToOpenIn; "Unable to open index registry key."
0x1400461ed  lea     rcx, [rsp+180h+var_130]
0x1400461f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400461f7  nop
0x1400461f8  lea     rdx, [rsp+180h+var_130]
0x1400461fd  lea     rcx, [rbp+80h+pExceptionObject]
0x140046201  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x140046206  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x14004620d  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x140046211  call    _CxxThrowException_0
0x140046217  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14004621e  lea     rcx, [rbp+80h+lpSubKey]
0x140046222  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140046227  nop
0x140046228  lea     rdx, [rbp+80h+lpSubKey]
0x14004622c  lea     rcx, [rsp+180h+var_130]
0x140046231  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140046236  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14004623d  lea     rcx, [rsp+180h+var_130]; pExceptionObject
0x140046242  call    _CxxThrowException_0
0x140046248  lea     rdx, aAttemptingToAs; "Attempting to assign an already-valid h"...
0x14004624f  lea     rcx, [rbp+80h+lpSubKey]
0x140046253  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140046258  nop
0x140046259  lea     rdx, [rbp+80h+lpSubKey]
0x14004625d  lea     rcx, [rsp+180h+var_130]
0x140046262  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140046267  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14004626e  lea     rcx, [rsp+180h+var_130]; pExceptionObject
0x140046273  call    _CxxThrowException_0
0x140046279  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x140046280  jz      short loc_14004629A
0x140046282  lea     rcx, [rbp+80h+lpSubKey]
0x140046286  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x14004628b  mov     r8, rax
0x14004628e  lea     rdx, TemplateMsg_UnableToCreateTemplateIndexSubKey
0x140046295  call    McTemplateU0zq_EventWriteTransfer
0x14004629a  lea     rdx, aUnableToCreate_0; "Unable to create a template index subke"...
0x1400462a1  lea     rcx, [rsp+180h+var_130]
0x1400462a6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400462ab  nop
0x1400462ac  lea     rdx, [rsp+180h+var_130]
0x1400462b1  lea     rcx, [rbp+80h+pExceptionObject]
0x1400462b5  call    ??0TemplateIndexException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::TemplateIndexException::TemplateIndexException(std::wstring const &)
0x1400462ba  lea     rdx, _TI3?AVTemplateIndexException@Uev@@; pThrowInfo
0x1400462c1  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x1400462c5  call    _CxxThrowException_0
0x1400462cb  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x1400462d2  lea     rcx, [rsp+180h+var_130]
0x1400462d7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400462dc  nop
0x1400462dd  lea     rdx, [rsp+180h+var_130]
0x1400462e2  lea     rcx, [rbp+80h+pExceptionObject]
0x1400462e6  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x1400462eb  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x1400462f2  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x1400462f6  call    _CxxThrowException_0
```
