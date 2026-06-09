# LanguageManager::_StoreInstallResult(long,std::vector<LanguageFeature,std::allocator<LanguageFeature>> const &)

- ea: `0x180033a58`
- end: `0x180033bad`
- name: `?_StoreInstallResult@LanguageManager@@CAXJAEBV?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030ca0`
- `0x180030e34`

## callees

- `0x180003a00`
- `0x180011334`
- `0x180012a98`
- `0x1800137bc`
- `0x180014ed0`
- `0x18002f770`
- `0x180033a58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033b05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033b05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033b21`
- `ntdll!RtlPublishWnfStateData` at `0x180033b4f`
- `ntdll!RtlPublishWnfStateData` at `0x180033b4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LanguageManager::_StoreInstallResult(int a1, _QWORD *a2)
{
  _WORD **v3; // rbx
  _WORD **v4; // rdi
  _WORD *v5; // rdx
  unsigned __int64 v6; // r8
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 result; // rax
  const char *v10; // r9
  unsigned int lpData; // [rsp+20h] [rbp-68h]
  LPCWSTR lpValueName[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  BYTE Data[8]; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = (_WORD **)*a2;
  v4 = (_WORD **)a2[1];
  try
  {
    while ( v3 != v4 )
    {
      if ( (unsigned __int64)v3[3] <= 7 )
        v5 = v3;
      else
        v5 = *v3;
      *(_OWORD *)lpValueName = 0;
      v13 = 0;
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      std::wstring::_Construct<1,unsigned short const *>((char **)lpValueName, v5, v6);
      *(_DWORD *)Data = a1;
      SessionIdStore::OpenSessionIdStoreKeyForPayloadType(&hKey, *((_DWORD *)v3 + 8));
      v7 = (const WCHAR *)lpValueName;
      if ( *((_QWORD *)&v13 + 1) > 7u )
        v7 = lpValueName[0];
      v8 = RegSetValueExW(hKey, v7, 0, 4u, Data, 4u);
      if ( v8 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecore\\internal\\shell\\inc\\SessionIdStore.h",
          (const char *)v8,
          lpData);
      if ( hKey )
        RegCloseKey(hKey);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)lpValueName);
      v3 += 5;
    }
    result = (unsigned int)RtlPublishWnfStateData(WNF_LANG_FOD_INSTALLATION_COMPLETED, 0, 0, 0) | 0x10000000;
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)result,
        0);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x486,
             (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
             v10);
  }
  return result;
}

```

## disassembly

```asm
0x180033a58  mov     [rsp+arg_10], rbx
0x180033a5d  push    rsi
0x180033a5e  push    rdi
0x180033a5f  push    r14
0x180033a61  sub     rsp, 70h
0x180033a65  mov     rax, cs:__security_cookie
0x180033a6c  xor     rax, rsp
0x180033a6f  mov     [rsp+88h+var_28], rax
0x180033a74  mov     esi, ecx
0x180033a76  mov     rbx, [rdx]
0x180033a79  mov     rdi, [rdx+8]
0x180033a7d  xor     r14d, r14d
0x180033a80  cmp     rbx, rdi
0x180033a83  jz      loc_180033B3B
0x180033a89  cmp     qword ptr [rbx+18h], 7
0x180033a8e  jbe     short loc_180033A95
0x180033a90  mov     rdx, [rbx]
0x180033a93  jmp     short loc_180033A98
0x180033a95  mov     rdx, rbx
0x180033a98  xorps   xmm0, xmm0
0x180033a9b  movups  xmmword ptr [rsp+88h+lpValueName], xmm0
0x180033aa0  xorps   xmm1, xmm1
0x180033aa3  movdqu  [rsp+88h+var_48], xmm1
0x180033aa9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033aad  inc     r8
0x180033ab0  cmp     [rdx+r8*2], r14w
0x180033ab5  jnz     short loc_180033AAD
0x180033ab7  lea     rcx, [rsp+88h+lpValueName]
0x180033abc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033ac1  nop
0x180033ac2  mov     dword ptr [rsp+88h+Data], esi
0x180033ac6  mov     edx, [rbx+20h]
0x180033ac9  lea     rcx, [rsp+88h+hKey]; phkResult
0x180033ace  call    ?OpenSessionIdStoreKeyForPayloadType@SessionIdStore@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4PayloadType@@K@Z; SessionIdStore::OpenSessionIdStoreKeyForPayloadType(PayloadType,ulong)
0x180033ad3  nop
0x180033ad4  lea     rdx, [rsp+88h+lpValueName]
0x180033ad9  cmp     qword ptr [rsp+88h+var_48+8], 7
0x180033adf  cmova   rdx, [rsp+88h+lpValueName]; lpValueName
0x180033ae5  mov     [rsp+88h+cbData], 4; cbData
0x180033aed  lea     rax, [rsp+88h+Data]
0x180033af2  mov     [rsp+88h+lpData], rax; unsigned int
0x180033af7  mov     r9d, 4; dwType
0x180033afd  xor     r8d, r8d; Reserved
0x180033b00  mov     rcx, [rsp+88h+hKey]; hKey
0x180033b05  call    cs:__imp_RegSetValueExW
0x180033b0b  mov     rcx, [rsp+88h]; this
0x180033b13  test    eax, eax
0x180033b15  jnz     short loc_180033B82
0x180033b17  mov     rcx, [rsp+88h+hKey]; hKey
0x180033b1c  test    rcx, rcx
0x180033b1f  jz      short loc_180033B28
0x180033b21  call    cs:__imp_RegCloseKey
0x180033b27  nop
0x180033b28  lea     rcx, [rsp+88h+lpValueName]; void *
0x180033b2d  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180033b32  add     rbx, 28h ; '('
0x180033b36  jmp     loc_180033A80
0x180033b3b  mov     [rsp+88h+lpData], r14; int
0x180033b40  xor     r9d, r9d
0x180033b43  xor     r8d, r8d
0x180033b46  xor     edx, edx
0x180033b48  mov     rcx, cs:WNF_LANG_FOD_INSTALLATION_COMPLETED
0x180033b4f  call    cs:__imp_RtlPublishWnfStateData
0x180033b55  or      eax, 10000000h
0x180033b5a  mov     rcx, [rsp+88h]; this
0x180033b62  jl      short loc_180033B97
0x180033b64  mov     rcx, [rsp+88h+var_28]
0x180033b69  xor     rcx, rsp; StackCookie
0x180033b6c  call    __security_check_cookie
0x180033b71  mov     rbx, [rsp+88h+arg_10]
0x180033b79  add     rsp, 70h
0x180033b7d  pop     r14
0x180033b7f  pop     rdi
0x180033b80  pop     rsi
0x180033b81  retn
0x180033b82  mov     r9d, eax; char *
0x180033b85  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\SessionI"...
0x180033b8c  mov     edx, 17h; void *
0x180033b91  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180033b97  mov     r9d, eax; char *
0x180033b9a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180033ba1  mov     edx, 35Ah; void *
0x180033ba6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
