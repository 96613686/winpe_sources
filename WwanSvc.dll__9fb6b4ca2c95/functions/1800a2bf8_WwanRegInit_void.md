# WwanRegInit(void)

- ea: `0x1800a2bf8`
- end: `0x1800a2e2c`
- name: `?WwanRegInit@@YAKXZ`
- size: `564`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18009e098`

## callees

- `0x1800085d0`
- `0x180008abc`
- `0x180011650`
- `0x1800117a8`
- `0x180012300`
- `0x1800123cc`
- `0x180013288`
- `0x180013588`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a2bf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2ceb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2d42`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2dad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2ceb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2d42`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2dad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2dd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2dd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2de1`

## string_xrefs

- `0x1800a2c8a`: `GetPersistentRegPathWstring failed, errCode (0x%8x)`
- `0x1800a2cf7`: `RegCreateKeyEx failed, errCode (0x%8x)`
- `0x1800a2d51`: `RegCreateKeyEx failed, errCode (0x%8x)`
- `0x1800a2dc1`: `RegCreateKeyEx DMProfile failed, errCode (0x%8x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 WwanRegInit(void)
{
  unsigned int PersistentRegPathWstring; // ebx
  const WCHAR *v2; // rax
  unsigned int Key; // eax
  HKEY v4; // rcx
  unsigned int v5; // eax
  void *v6; // [rsp+50h] [rbp-38h]
  _BYTE v7[32]; // [rsp+58h] [rbp-30h] BYREF

  WwanLog::Enter("WwanRegInit");
  v6 = operator new(0x20u);
  g_pSSWwansvcInReg = (StateSeparation *)StateSeparation::StateSeparation(v6, 0);
  if ( !g_pSSWwansvcInReg )
  {
    WwanLog::Error("WwanRegInit", 0, L"m_pSSWwansvcInReg failed");
    WwanLog::Exit("WwanRegInit");
    return 14;
  }
  std::wstring::wstring(v7);
  PersistentRegPathWstring = GetPersistentRegPathWstring(0, 0, v7);
  if ( PersistentRegPathWstring )
  {
    WwanLog::Error("WwanRegInit", 0, L"GetPersistentRegPathWstring failed, errCode (0x%8x)", PersistentRegPathWstring);
    goto LABEL_14;
  }
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
  PersistentRegPathWstring = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0x20019u, 0, &phkResult, 0);
  if ( PersistentRegPathWstring )
  {
    WwanLog::Error("WwanRegInit", 0, L"RegCreateKeyEx failed, errCode (0x%8x)", PersistentRegPathWstring);
  }
  else
  {
    Key = RegCreateKeyExW(phkResult, L"Profiles", 0, 0, 0, 0x2001Fu, 0, &qword_180152870, 0);
    PersistentRegPathWstring = Key;
    if ( Key )
    {
      WwanLog::Error("WwanRegInit", 0, L"RegCreateKeyEx failed, errCode (0x%8x)", Key);
      v4 = phkResult;
    }
    else
    {
      v5 = RegCreateKeyExW(phkResult, L"DMProfiles", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
      PersistentRegPathWstring = v5;
      if ( !v5 )
      {
        WwanLog::Verbose("WwanRegInit", 0, L"errCode (0x%8x)", 0);
        PersistentRegPathWstring = 0;
        goto LABEL_14;
      }
      WwanLog::Error("WwanRegInit", 0, L"RegCreateKeyEx DMProfile failed, errCode (0x%8x)", v5);
      RegCloseKey(phkResult);
      v4 = qword_180152870;
    }
    RegCloseKey(v4);
  }
LABEL_14:
  WwanLog::Exit("WwanRegInit");
  std::wstring::_Tidy_deallocate(v7);
  return PersistentRegPathWstring;
}

```

## disassembly

```asm
0x1800a2bf8  mov     [rsp+arg_0], rbx
0x1800a2bfd  push    rdi
0x1800a2bfe  sub     rsp, 80h
0x1800a2c05  mov     rax, cs:__security_cookie
0x1800a2c0c  xor     rax, rsp
0x1800a2c0f  mov     [rsp+88h+var_10], rax
0x1800a2c14  lea     rdi, aWwanreginit; "WwanRegInit"
0x1800a2c1b  mov     rcx, rdi; char *
0x1800a2c1e  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a2c23  mov     ecx, 20h ; ' '; Size
0x1800a2c28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a2c2d  mov     [rsp+88h+var_38], rax
0x1800a2c32  xor     edx, edx
0x1800a2c34  mov     rcx, rax
0x1800a2c37  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x1800a2c3c  nop
0x1800a2c3d  mov     cs:?g_pSSWwansvcInReg@@3PEAVStateSeparation@@EA, rax; StateSeparation * g_pSSWwansvcInReg
0x1800a2c44  test    rax, rax
0x1800a2c47  jnz     short loc_1800A2C6C
0x1800a2c49  lea     r8, aMPsswwansvcinr; "m_pSSWwansvcInReg failed"
0x1800a2c50  xor     edx, edx; struct _GUID *
0x1800a2c52  mov     rcx, rdi; char *
0x1800a2c55  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2c5a  mov     rcx, rdi; char *
0x1800a2c5d  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a2c62  mov     eax, 0Eh
0x1800a2c67  jmp     loc_1800A2E0E
0x1800a2c6c  lea     rcx, [rsp+88h+var_30]
0x1800a2c71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a2c76  lea     r8, [rsp+88h+var_30]
0x1800a2c7b  xor     edx, edx
0x1800a2c7d  xor     ecx, ecx
0x1800a2c7f  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x1800a2c84  mov     ebx, eax
0x1800a2c86  test    eax, eax
0x1800a2c88  jz      short loc_1800A2CA3
0x1800a2c8a  lea     r8, aGetpersistentr_2; "GetPersistentRegPathWstring failed, err"...
0x1800a2c91  mov     r9d, ebx
0x1800a2c94  xor     edx, edx; struct _GUID *
0x1800a2c96  mov     rcx, rdi; char *
0x1800a2c99  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2c9e  jmp     loc_1800A2DFA
0x1800a2ca3  lea     rcx, [rsp+88h+var_30]
0x1800a2ca8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a2cad  mov     rdx, rax; lpSubKey
0x1800a2cb0  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800a2cb9  lea     rax, phkResult
0x1800a2cc0  mov     [rsp+88h+phkResult], rax; phkResult
0x1800a2cc5  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2cce  mov     [rsp+88h+samDesired], 20019h; samDesired
0x1800a2cd6  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800a2cde  xor     r9d, r9d; lpClass
0x1800a2ce1  xor     r8d, r8d; Reserved
0x1800a2ce4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2ceb  call    cs:__imp_RegCreateKeyExW
0x1800a2cf1  mov     ebx, eax
0x1800a2cf3  test    eax, eax
0x1800a2cf5  jz      short loc_1800A2D00
0x1800a2cf7  lea     r8, aRegcreatekeyex_0; "RegCreateKeyEx failed, errCode (0x%8x)"
0x1800a2cfe  jmp     short loc_1800A2C91
0x1800a2d00  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800a2d09  lea     rax, qword_180152870
0x1800a2d10  mov     [rsp+88h+phkResult], rax; phkResult
0x1800a2d15  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2d1e  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x1800a2d26  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800a2d2e  xor     r9d, r9d; lpClass
0x1800a2d31  xor     r8d, r8d; Reserved
0x1800a2d34  lea     rdx, aProfiles; "Profiles"
0x1800a2d3b  mov     rcx, cs:phkResult; hKey
0x1800a2d42  call    cs:__imp_RegCreateKeyExW
0x1800a2d48  mov     ebx, eax
0x1800a2d4a  test    eax, eax
0x1800a2d4c  jz      short loc_1800A2D6B
0x1800a2d4e  mov     r9d, eax
0x1800a2d51  lea     r8, aRegcreatekeyex_0; "RegCreateKeyEx failed, errCode (0x%8x)"
0x1800a2d58  xor     edx, edx; struct _GUID *
0x1800a2d5a  mov     rcx, rdi; char *
0x1800a2d5d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2d62  mov     rcx, cs:phkResult
0x1800a2d69  jmp     short loc_1800A2DE1
0x1800a2d6b  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800a2d74  lea     rax, hKey
0x1800a2d7b  mov     [rsp+88h+phkResult], rax; phkResult
0x1800a2d80  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2d89  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x1800a2d91  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800a2d99  xor     r9d, r9d; lpClass
0x1800a2d9c  xor     r8d, r8d; Reserved
0x1800a2d9f  lea     rdx, aDmprofiles; "DMProfiles"
0x1800a2da6  mov     rcx, cs:phkResult; hKey
0x1800a2dad  call    cs:__imp_RegCreateKeyExW
0x1800a2db3  mov     ebx, eax
0x1800a2db5  xor     edx, edx; struct _GUID *
0x1800a2db7  mov     rcx, rdi; char *
0x1800a2dba  test    eax, eax
0x1800a2dbc  jz      short loc_1800A2DE9
0x1800a2dbe  mov     r9d, eax
0x1800a2dc1  lea     r8, aRegcreatekeyex_1; "RegCreateKeyEx DMProfile failed, errCod"...
0x1800a2dc8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2dcd  mov     rcx, cs:phkResult; hKey
0x1800a2dd4  call    cs:__imp_RegCloseKey
0x1800a2dda  mov     rcx, cs:qword_180152870; hKey
0x1800a2de1  call    cs:__imp_RegCloseKey
0x1800a2de7  jmp     short loc_1800A2DFA
0x1800a2de9  xor     r9d, r9d
0x1800a2dec  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x1800a2df3  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a2df8  xor     ebx, ebx
0x1800a2dfa  mov     rcx, rdi; char *
0x1800a2dfd  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a2e02  lea     rcx, [rsp+88h+var_30]
0x1800a2e07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a2e0c  mov     eax, ebx
0x1800a2e0e  mov     rcx, [rsp+88h+var_10]
0x1800a2e13  xor     rcx, rsp; StackCookie
0x1800a2e16  call    __security_check_cookie
0x1800a2e1b  mov     rbx, [rsp+88h+arg_0]
0x1800a2e23  add     rsp, 80h
0x1800a2e2a  pop     rdi
0x1800a2e2b  retn
```
