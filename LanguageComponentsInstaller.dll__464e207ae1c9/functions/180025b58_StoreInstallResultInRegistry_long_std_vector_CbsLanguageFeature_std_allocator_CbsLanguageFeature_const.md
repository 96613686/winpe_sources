# StoreInstallResultInRegistry(long,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x180025b58`
- end: `0x180025c29`
- name: `?StoreInstallResultInRegistry@@YAXJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `209`
- prototype: `void __fastcall(int, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025d20`

## callees

- `0x180003520`
- `0x180021494`
- `0x18002502c`
- `0x180025b58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025be6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025be6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bcd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bcd`

## pseudocode

```c
void __fastcall StoreInstallResultInRegistry(int a1, __int64 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  const WCHAR *v5; // rdi
  unsigned int v6; // eax
  const char *v7; // r9
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  BYTE Data[8]; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a2;
  v4 = a2[1];
  while ( v3 != v4 )
  {
    try
    {
      v5 = (const WCHAR *)(v3 + 152);
      *(_DWORD *)Data = a1;
      SessionIdStore::OpenSessionIdStoreKeyForPayloadType(&hKey, *(_DWORD *)(v3 + 184));
      if ( *(_QWORD *)(v3 + 176) > 7u )
        v5 = *(const WCHAR **)v5;
      v6 = RegSetValueExW(hKey, v5, 0, 4u, Data, 4u);
      if ( v6 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecore\\internal\\shell\\inc\\SessionIdStore.h",
          (const char *)v6,
          lpData);
      if ( hKey )
        RegCloseKey(hKey);
      v3 += 192;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\installerrequests.cpp",
        v7);
      return;
    }
  }
}

```

## disassembly

```asm
0x180025b58  mov     [rsp+arg_10], rbx
0x180025b5d  push    rsi
0x180025b5e  push    rdi
0x180025b5f  push    r14
0x180025b61  sub     rsp, 50h
0x180025b65  mov     rax, cs:__security_cookie
0x180025b6c  xor     rax, rsp
0x180025b6f  mov     [rsp+68h+var_28], rax
0x180025b74  mov     r14d, ecx
0x180025b77  mov     rbx, [rdx]
0x180025b7a  mov     rsi, [rdx+8]
0x180025b7e  cmp     rbx, rsi
0x180025b81  jz      short loc_180025BF5
0x180025b83  lea     rdi, [rbx+98h]
0x180025b8a  mov     dword ptr [rsp+68h+Data], r14d
0x180025b8f  mov     edx, [rbx+0B8h]
0x180025b95  lea     rcx, [rsp+68h+hKey]; phkResult
0x180025b9a  call    ?OpenSessionIdStoreKeyForPayloadType@SessionIdStore@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4PayloadType@@K@Z; SessionIdStore::OpenSessionIdStoreKeyForPayloadType(PayloadType,ulong)
0x180025b9f  nop
0x180025ba0  cmp     qword ptr [rdi+18h], 7
0x180025ba5  jbe     short loc_180025BAA
0x180025ba7  mov     rdi, [rdi]
0x180025baa  mov     [rsp+68h+cbData], 4; cbData
0x180025bb2  lea     rax, [rsp+68h+Data]
0x180025bb7  mov     [rsp+68h+lpData], rax; unsigned int
0x180025bbc  mov     r9d, 4; dwType
0x180025bc2  xor     r8d, r8d; Reserved
0x180025bc5  mov     rdx, rdi; lpValueName
0x180025bc8  mov     rcx, [rsp+68h+hKey]; hKey
0x180025bcd  call    cs:__imp_RegSetValueExW
0x180025bd3  mov     rcx, [rsp+68h]; this
0x180025bd8  test    eax, eax
0x180025bda  jnz     short loc_180025C13
0x180025bdc  mov     rcx, [rsp+68h+hKey]; hKey
0x180025be1  test    rcx, rcx
0x180025be4  jz      short loc_180025BEC
0x180025be6  call    cs:__imp_RegCloseKey
0x180025bec  add     rbx, 0C0h
0x180025bf3  jmp     short loc_180025B7E
0x180025bf5  mov     rcx, [rsp+68h+var_28]
0x180025bfa  xor     rcx, rsp; StackCookie
0x180025bfd  call    __security_check_cookie
0x180025c02  mov     rbx, [rsp+68h+arg_10]
0x180025c0a  add     rsp, 50h
0x180025c0e  pop     r14
0x180025c10  pop     rdi
0x180025c11  pop     rsi
0x180025c12  retn
0x180025c13  mov     r9d, eax; char *
0x180025c16  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\SessionI"...
0x180025c1d  mov     edx, 17h; void *
0x180025c22  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
