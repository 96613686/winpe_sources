# Utility::GetAllUserSids(bool)

- ea: `0x18002a36c`
- end: `0x18002a68d`
- name: `?GetAllUserSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `801`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180037cfc`
- `0x180050128`
- `0x180052178`
- `0x1800fc498`
- `0x18010ef38`
- `0x18010f0f8`
- `0x180111bbc`

## callees

- `0x18000e458`
- `0x180018a60`
- `0x180029328`
- `0x18002a36c`
- `0x18003ffec`
- `0x1800493b8`
- `0x180052c34`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x1800679f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a5fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a5fc`
- `ADVAPI32!RegOpenKeyExW` at `0x18002a477`
- `ADVAPI32!RegOpenKeyExW` at `0x18002a477`
- `ADVAPI32!RegEnumKeyExW` at `0x18002a555`
- `ADVAPI32!RegEnumKeyExW` at `0x18002a555`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002a4c9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002a4c9`
- `ADVAPI32!RegCloseKey` at `0x18002a63f`
- `ADVAPI32!RegCloseKey` at `0x18002a63f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a42c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a42c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a64f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a64f`

## string_xrefs

- `0x18002a4e6`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x18002a67b`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Utility::GetAllUserSids(char a1)
{
  char v2; // al
  const WCHAR *v3; // rdx
  int v4; // eax
  __int64 v5; // rdx
  DWORD i; // edi
  WCHAR *v7; // r8
  LSTATUS v8; // eax
  unsigned __int64 v9; // rcx
  LPWSTR *v10; // rcx
  size_t v11; // r8
  LPWSTR *v12; // r10
  __int64 v13; // r10
  __int64 v14; // r11
  void **j; // rbx
  LPWSTR *v16; // rcx
  int phkResult; // [rsp+20h] [rbp-69h]
  int phkResulta; // [rsp+20h] [rbp-69h]
  DWORD cSubKeys; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-25h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-21h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-19h] BYREF
  LPWSTR lpName[2]; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int64 v25; // [rsp+98h] [rbp+Fh]
  unsigned __int64 v26; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  if ( dword_180184140 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180184140);
    if ( dword_180184140 == -1 )
    {
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(qword_180184148);
      atexit(Utility::GetAllUserSids_::_2_::_dynamic_atexit_destructor_for__allUserSids__);
      Init_thread_footer(&dword_180184140);
    }
  }
  if ( byte_180183E90 == a1 )
  {
    v2 = byte_180183E91;
  }
  else
  {
    v2 = 0;
    byte_180183E91 = 0;
    byte_180183E90 = a1;
  }
  if ( !v2 )
  {
    AcquireSRWLockExclusive(&stru_180183E88);
    hKey[2] = (HKEY)&stru_180183E88;
    if ( !byte_180183E91 )
    {
      hKey[0] = 0;
      v3 = (const WCHAR *)&Utility::ProfileListSubKeyPath;
      if ( (unsigned __int64)qword_1801831D8 > 7 )
        v3 = Utility::ProfileListSubKeyPath;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, hKey) )
      {
        cSubKeys = 0;
        cbMaxSubKeyLen = 0;
        v4 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v4 > 0 )
          v4 = (unsigned __int16)v4 | 0x80070000;
        if ( v4 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x267,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
            (const char *)(unsigned int)v4,
            phkResult);
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen + 1;
          *(_OWORD *)lpName = 0;
          v25 = 0;
          v26 = 0;
          std::wstring::_Construct<0,unsigned short>(lpName, v5, cbMaxSubKeyLen + 1);
          v7 = (WCHAR *)lpName;
          if ( v26 > 7 )
            v7 = lpName[0];
          v8 = RegEnumKeyExW(hKey[0], i, v7, &cchName, 0, 0, 0, 0);
          if ( v8 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x275,
              (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
              (const char *)(unsigned int)v8,
              phkResulta);
          v9 = v25;
          if ( cchName > v25 )
          {
            v11 = cchName - v25;
            if ( v11 > v26 - v25 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
                (unsigned int)lpName,
                cchName - v25,
                v11,
                cchName - v25,
                0);
            }
            else
            {
              v25 = cchName;
              v12 = lpName;
              if ( v26 > 7 )
                v12 = (LPWSTR *)lpName[0];
              wmemset((wchar_t *)v12 + v9, 0, v11);
              *(_WORD *)(v13 + 2 * v14) = 0;
            }
          }
          else
          {
            v25 = cchName;
            v10 = lpName;
            if ( v26 > 7 )
              v10 = (LPWSTR *)lpName[0];
            *((_WORD *)v10 + cchName) = 0;
          }
          for ( j = (void **)off_1801318A0; j != &Windows::Compat::Inventory::AepicInvCache::`vftable'; ++j )
          {
            v16 = lpName;
            if ( v26 > 7 )
              v16 = (LPWSTR *)lpName[0];
            if ( !(unsigned int)_o__wcsicmp(v16, *j) && !a1 )
              goto LABEL_37;
          }
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184148, lpName);
LABEL_37:
          std::wstring::~wstring(lpName);
        }
      }
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    byte_180183E91 = 1;
    ReleaseSRWLockExclusive(&stru_180183E88);
  }
  return qword_180184148;
}

```

## disassembly

```asm
0x18002a36c  push    rbp
0x18002a36e  push    rbx
0x18002a36f  push    rsi
0x18002a370  push    rdi
0x18002a371  push    r14
0x18002a373  push    r15
0x18002a375  lea     rbp, [rsp-2Fh]
0x18002a37a  sub     rsp, 0B8h
0x18002a381  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x18002a389  mov     rax, cs:__security_cookie
0x18002a390  xor     rax, rsp
0x18002a393  mov     [rbp+57h+var_38], rax
0x18002a397  mov     sil, cl
0x18002a39a  mov     edx, cs:_tls_index
0x18002a3a0  mov     rax, gs:58h
0x18002a3a9  mov     ecx, 4
0x18002a3ae  mov     rax, [rax+rdx*8]
0x18002a3b2  mov     eax, [rcx+rax]
0x18002a3b5  cmp     cs:dword_180184140, eax
0x18002a3bb  jle     short loc_18002A3F6
0x18002a3bd  lea     rcx, dword_180184140
0x18002a3c4  call    _Init_thread_header
0x18002a3c9  cmp     cs:dword_180184140, 0FFFFFFFFh
0x18002a3d0  jnz     short loc_18002A3F6
0x18002a3d2  lea     rcx, qword_180184148
0x18002a3d9  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x18002a3de  lea     rcx, _Utility__GetAllUserSids____2____dynamic_atexit_destructor_for__allUserSids__; void (__cdecl *)()
0x18002a3e5  call    atexit
0x18002a3ea  lea     rcx, dword_180184140
0x18002a3f1  call    _Init_thread_footer
0x18002a3f6  xor     r14d, r14d
0x18002a3f9  cmp     cs:byte_180183E90, sil
0x18002a400  jz      short loc_18002A414
0x18002a402  mov     al, r14b
0x18002a405  mov     cs:byte_180183E91, al
0x18002a40b  mov     cs:byte_180183E90, sil
0x18002a412  jmp     short loc_18002A41A
0x18002a414  mov     al, cs:byte_180183E91
0x18002a41a  test    al, al
0x18002a41c  jnz     loc_18002A655
0x18002a422  lea     r15, stru_180183E88
0x18002a429  mov     rcx, r15; SRWLock
0x18002a42c  call    cs:__imp_AcquireSRWLockExclusive
0x18002a432  mov     [rbp+57h+var_60], r15
0x18002a436  cmp     cs:byte_180183E91, r14b
0x18002a43d  jnz     loc_18002A645
0x18002a443  mov     [rbp+57h+hKey], r14
0x18002a447  lea     rdx, ?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileListSubKeyPath
0x18002a44e  cmp     cs:qword_1801831D8, 7
0x18002a456  cmova   rdx, cs:?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x18002a45e  lea     rax, [rbp+57h+hKey]
0x18002a462  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002a467  mov     r9d, 20019h; samDesired
0x18002a46d  xor     r8d, r8d; ulOptions
0x18002a470  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a477  call    cs:__imp_RegOpenKeyExW
0x18002a47d  test    eax, eax
0x18002a47f  jnz     loc_18002A636
0x18002a485  mov     [rbp+57h+cSubKeys], r14d
0x18002a489  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18002a48d  mov     [rsp+0E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002a492  mov     [rsp+0E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18002a497  mov     [rsp+0E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18002a49c  mov     [rsp+0E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18002a4a1  mov     [rsp+0E0h+lpcValues], r14; lpcValues
0x18002a4a6  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002a4ab  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18002a4af  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002a4b4  lea     rax, [rbp+57h+cSubKeys]
0x18002a4b8  mov     [rsp+0E0h+phkResult], rax; int
0x18002a4bd  xor     r9d, r9d; lpReserved
0x18002a4c0  xor     r8d, r8d; lpcchClass
0x18002a4c3  xor     edx, edx; lpClass
0x18002a4c5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002a4c9  call    cs:__imp_RegQueryInfoKeyW
0x18002a4cf  test    eax, eax
0x18002a4d1  jle     short loc_18002A4DB
0x18002a4d3  movzx   eax, ax
0x18002a4d6  or      eax, 80070000h
0x18002a4db  mov     rcx, [rbp+5Fh]; this
0x18002a4df  test    eax, eax
0x18002a4e1  jns     short loc_18002A4F8
0x18002a4e3  mov     r9d, eax; char *
0x18002a4e6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18002a4ed  mov     edx, 267h; void *
0x18002a4f2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a4f8  mov     edi, r14d
0x18002a4fb  cmp     [rbp+57h+cSubKeys], r14d
0x18002a4ff  jbe     loc_18002A636
0x18002a505  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18002a508  inc     eax
0x18002a50a  mov     [rbp+57h+cchName], eax
0x18002a50d  xorps   xmm0, xmm0
0x18002a510  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x18002a514  mov     [rbp+57h+var_48], r14
0x18002a518  mov     [rbp+57h+var_40], r14
0x18002a51c  mov     r8d, eax
0x18002a51f  lea     rcx, [rbp+57h+lpName]
0x18002a523  call    ??$_Construct@$0A@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXG_K@Z; std::wstring::_Construct<0,ushort>(ushort,unsigned __int64)
0x18002a528  nop
0x18002a529  lea     r8, [rbp+57h+lpName]
0x18002a52d  cmp     [rbp+57h+var_40], 7
0x18002a532  cmova   r8, [rbp+57h+lpName]; lpName
0x18002a537  mov     [rsp+0E0h+lpcValues], r14; lpftLastWriteTime
0x18002a53c  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcchClass
0x18002a541  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r14; lpClass
0x18002a546  mov     [rsp+0E0h+phkResult], r14; int
0x18002a54b  lea     r9, [rbp+57h+cchName]; lpcchName
0x18002a54f  mov     edx, edi; dwIndex
0x18002a551  mov     rcx, [rbp+57h+hKey]; hKey
0x18002a555  call    cs:__imp_RegEnumKeyExW
0x18002a55b  mov     rcx, [rbp+5Fh]; this
0x18002a55f  test    eax, eax
0x18002a561  js      loc_18002A678
0x18002a567  mov     r11d, [rbp+57h+cchName]
0x18002a56b  mov     rcx, [rbp+57h+var_48]
0x18002a56f  cmp     r11, rcx
0x18002a572  ja      short loc_18002A58D
0x18002a574  mov     [rbp+57h+var_48], r11
0x18002a578  lea     rcx, [rbp+57h+lpName]
0x18002a57c  cmp     [rbp+57h+var_40], 7
0x18002a581  cmova   rcx, [rbp+57h+lpName]
0x18002a586  mov     [rcx+r11*2], r14w
0x18002a58b  jmp     short loc_18002A5D8
0x18002a58d  mov     r8, r11
0x18002a590  sub     r8, rcx; N
0x18002a593  mov     rax, [rbp+57h+var_40]
0x18002a597  sub     rax, rcx
0x18002a59a  cmp     r8, rax
0x18002a59d  ja      short loc_18002A5C3
0x18002a59f  mov     [rbp+57h+var_48], r11
0x18002a5a3  lea     r10, [rbp+57h+lpName]
0x18002a5a7  cmp     [rbp+57h+var_40], 7
0x18002a5ac  cmova   r10, [rbp+57h+lpName]
0x18002a5b1  xor     edx, edx; C
0x18002a5b3  lea     rcx, [r10+rcx*2]; S
0x18002a5b7  call    wmemset
0x18002a5bc  mov     [r10+r11*2], r14w
0x18002a5c1  jmp     short loc_18002A5D8
0x18002a5c3  mov     word ptr [rsp+0E0h+phkResult], r14w
0x18002a5c9  mov     r9, r8
0x18002a5cc  mov     rdx, r8
0x18002a5cf  lea     rcx, [rbp+57h+lpName]
0x18002a5d3  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18002a5d8  lea     rbx, off_1801318A0; "s-1-5-18"
0x18002a5df  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x18002a5e6  cmp     rbx, rax
0x18002a5e9  jz      short loc_18002A611
0x18002a5eb  lea     rcx, [rbp+57h+lpName]
0x18002a5ef  cmp     [rbp+57h+var_40], 7
0x18002a5f4  cmova   rcx, [rbp+57h+lpName]
0x18002a5f9  mov     rdx, [rbx]
0x18002a5fc  call    cs:__imp__o__wcsicmp
0x18002a602  test    eax, eax
0x18002a604  jnz     short loc_18002A60B
0x18002a606  test    sil, sil
0x18002a609  jz      short loc_18002A622
0x18002a60b  add     rbx, 8
0x18002a60f  jmp     short loc_18002A5DF
0x18002a611  lea     rdx, [rbp+57h+lpName]
0x18002a615  lea     rcx, qword_180184148
0x18002a61c  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002a621  nop
0x18002a622  lea     rcx, [rbp+57h+lpName]
0x18002a626  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a62b  inc     edi
0x18002a62d  cmp     edi, [rbp+57h+cSubKeys]
0x18002a630  jb      loc_18002A505
0x18002a636  mov     rcx, [rbp+57h+hKey]; hKey
0x18002a63a  test    rcx, rcx
0x18002a63d  jz      short loc_18002A645
0x18002a63f  call    cs:__imp_RegCloseKey
0x18002a645  mov     cs:byte_180183E91, 1
0x18002a64c  mov     rcx, r15; SRWLock
0x18002a64f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a655  lea     rax, qword_180184148
0x18002a65c  mov     rcx, [rbp+57h+var_38]
0x18002a660  xor     rcx, rsp; StackCookie
0x18002a663  call    __security_check_cookie
0x18002a668  add     rsp, 0B8h
0x18002a66f  pop     r15
0x18002a671  pop     r14
0x18002a673  pop     rdi
0x18002a674  pop     rsi
0x18002a675  pop     rbx
0x18002a676  pop     rbp
0x18002a677  retn
0x18002a678  mov     r9d, eax; char *
0x18002a67b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18002a682  mov     edx, 275h; void *
0x18002a687  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
