# WalletEncrypter::IsEncryptionKeyExpired(void)

- ea: `0x18001c048`
- end: `0x18001c1d8`
- name: `?IsEncryptionKeyExpired@WalletEncrypter@@QEBAHXZ`
- size: `400`
- prototype: `__int64 __fastcall(WalletEncrypter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800102c0`

## callees

- `0x18001b2b0`
- `0x18001b340`
- `0x18001b394`
- `0x18001b3f4`
- `0x18001c048`
- `0x18001c48c`
- `0x180043090`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001c159`
- `msvcrt!memcpy_s` at `0x18001c159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c16f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c16f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c18f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c18f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c17d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c17d`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001c0bc`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001c0bc`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x18001c12c`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x18001c12c`

## pseudocode

```c
_BOOL8 __fastcall WalletEncrypter::IsEncryptionKeyExpired(WalletEncrypter *this)
{
  BOOL v1; // ebx
  __int64 *v2; // rax
  __int64 *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v7; // [rsp+40h] [rbp-39h] BYREF
  FILETIME Destination; // [rsp+48h] [rbp-31h] BYREF
  __int64 v9; // [rsp+50h] [rbp-29h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-21h] BYREF
  struct _FILETIME FileTime; // [rsp+60h] [rbp-19h] BYREF
  __int128 v12; // [rsp+68h] [rbp-11h] BYREF
  __int128 v13; // [rsp+78h] [rbp-1h]
  __int128 v14; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+98h] [rbp+1Fh]
  _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp+2Fh] BYREF
  __int128 v17; // [rsp+B8h] [rbp+3Fh] BYREF

  v1 = 0;
  FileTime2 = 0;
  v17 = xmmword_180050F80;
  FileTime = 0;
  Destination = 0;
  SystemTime = 0;
  v9 = 0;
  v12 = 0;
  v7 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v2 = tlx::replace<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>(&v7);
  if ( (unsigned int)VaultOpenVault(Vault_DefaultVault_ID, 0x10000000, v2) )
  {
    GetLastError();
  }
  else
  {
    LODWORD(v14) = 1;
    DWORD2(v14) = 7;
    *(_QWORD *)&v15 = L"WalletKeyExpiration";
    DWORD2(v12) = 7;
    *(_QWORD *)&v13 = L"WalletUser";
    LODWORD(v12) = 2;
    v3 = tlx::replace<tlx::handle_traits<_VAULT_ITEM *,void (*)(void *),&void VaultFree(void *),0>>(&v9);
    if ( !(unsigned int)VaultGetItem(v7, &v17, &v14, &v12, 0, 0, 0, v3) && v9 && (v5 = *(_QWORD *)(v9 + 40)) != 0 )
    {
      if ( !memcpy_s(&Destination, 8u, *(const void *const *)(v5 + 24), *(unsigned int *)(v5 + 16)) )
      {
        FileTime2 = Destination;
        GetSystemTime(&SystemTime);
        if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
          v1 = CompareFileTime(&FileTime, &FileTime2) >= 0;
      }
    }
    else
    {
      WalletEncrypter::SaveKeyExpiration(v4, &v7);
    }
  }
  tlx::unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>(&v7);
  tlx::unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&void VaultFree(void *),0>>::~unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&void VaultFree(void *),0>>(&v9);
  return v1;
}

```

## disassembly

```asm
0x18001c048  mov     [rsp-8+arg_0], rbx
0x18001c04d  push    rbp
0x18001c04e  lea     rbp, [rsp-57h]
0x18001c053  sub     rsp, 0D0h
0x18001c05a  mov     rax, cs:__security_cookie
0x18001c061  xor     rax, rsp
0x18001c064  mov     [rbp+57h+var_8], rax
0x18001c068  movups  xmm0, cs:xmmword_180050F80
0x18001c06f  xor     ebx, ebx
0x18001c071  lea     rcx, [rbp+57h+var_90]
0x18001c075  xorps   xmm1, xmm1
0x18001c078  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rbx
0x18001c07c  movdqu  [rbp+57h+var_18], xmm0
0x18001c081  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x18001c085  xorps   xmm0, xmm0
0x18001c088  mov     [rbp+57h+Destination], rbx
0x18001c08c  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c090  mov     [rbp+57h+var_80], rbx
0x18001c094  movups  [rbp+57h+var_68], xmm0
0x18001c098  mov     [rbp+57h+var_90], rbx
0x18001c09c  movups  [rbp+57h+var_58], xmm0
0x18001c0a0  movups  [rbp+57h+var_48], xmm1
0x18001c0a4  movups  [rbp+57h+var_38], xmm1
0x18001c0a8  call    ??$replace@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001c0ad  mov     r8, rax
0x18001c0b0  lea     rcx, Vault_DefaultVault_ID
0x18001c0b7  mov     edx, 10000000h
0x18001c0bc  call    cs:__imp_VaultOpenVault
0x18001c0c2  test    eax, eax
0x18001c0c4  jz      short loc_18001C0D1
0x18001c0c6  call    cs:__imp_GetLastError
0x18001c0cc  jmp     loc_18001C1A7
0x18001c0d1  mov     ecx, 7
0x18001c0d6  mov     dword ptr [rbp+57h+var_48], 1
0x18001c0dd  lea     rax, ?sc_szWalletKeyExpiration@WalletEncrypter@@1QBGB; "WalletKeyExpiration"
0x18001c0e4  mov     dword ptr [rbp+57h+var_48+8], ecx
0x18001c0e7  mov     qword ptr [rbp+57h+var_38], rax
0x18001c0eb  lea     rax, ?sc_szWalletUser@WalletEncrypter@@1QBGB; "WalletUser"
0x18001c0f2  mov     dword ptr [rbp+57h+var_68+8], ecx
0x18001c0f5  lea     rcx, [rbp+57h+var_80]
0x18001c0f9  mov     qword ptr [rbp+57h+var_58], rax
0x18001c0fd  mov     dword ptr [rbp+57h+var_68], 2
0x18001c104  call    ??$replace@U?$handle_traits@PEAU_VAULT_ITEM@@P6AXPEAX@Z$1?VaultFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAU_VAULT_ITEM@@AEAV?$unique_any@U?$handle_traits@PEAU_VAULT_ITEM@@P6AXPEAX@Z$1?VaultFree@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<_VAULT_ITEM *,void (*)(void *),&VaultFree(void *),0>>(tlx::unique_any<tlx::handle_traits<_VAULT_ITEM *,void (*)(void *),&VaultFree(void *),0>> &)
0x18001c109  mov     rcx, [rbp+57h+var_90]
0x18001c10d  lea     r9, [rbp+57h+var_68]
0x18001c111  mov     [rsp+0D0h+var_98], rax
0x18001c116  lea     r8, [rbp+57h+var_48]
0x18001c11a  mov     [rsp+0D0h+var_A0], ebx
0x18001c11e  lea     rdx, [rbp+57h+var_18]
0x18001c122  mov     [rsp+0D0h+var_A8], rbx
0x18001c127  mov     [rsp+0D0h+var_B0], rbx
0x18001c12c  call    cs:__imp_VaultGetItem
0x18001c132  test    eax, eax
0x18001c134  jnz     short loc_18001C19E
0x18001c136  mov     rax, [rbp+57h+var_80]
0x18001c13a  test    rax, rax
0x18001c13d  jz      short loc_18001C19E
0x18001c13f  mov     r8, [rax+28h]
0x18001c143  test    r8, r8
0x18001c146  jz      short loc_18001C19E
0x18001c148  mov     r9d, [r8+10h]; SourceSize
0x18001c14c  lea     rcx, [rbp+57h+Destination]; Destination
0x18001c150  mov     r8, [r8+18h]; Source
0x18001c154  mov     edx, 8; DestinationSize
0x18001c159  call    cs:__imp_memcpy_s
0x18001c15f  test    eax, eax
0x18001c161  jnz     short loc_18001C1A7
0x18001c163  mov     rax, [rbp+57h+Destination]
0x18001c167  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c16b  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x18001c16f  call    cs:__imp_GetSystemTime
0x18001c175  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001c179  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c17d  call    cs:__imp_SystemTimeToFileTime
0x18001c183  test    eax, eax
0x18001c185  jz      short loc_18001C1A7
0x18001c187  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x18001c18b  lea     rcx, [rbp+57h+FileTime]; lpFileTime1
0x18001c18f  call    cs:__imp_CompareFileTime
0x18001c195  mov     ebx, eax
0x18001c197  not     ebx
0x18001c199  shr     ebx, 1Fh
0x18001c19c  jmp     short loc_18001C1A7
0x18001c19e  lea     rdx, [rbp+57h+var_90]
0x18001c1a2  call    ?SaveKeyExpiration@WalletEncrypter@@AEBAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@@Z; WalletEncrypter::SaveKeyExpiration(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001c1a7  lea     rcx, [rbp+57h+var_90]
0x18001c1ab  call    ??1?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(void)
0x18001c1b0  lea     rcx, [rbp+57h+var_80]
0x18001c1b4  call    ??1?$unique_any@U?$handle_traits@PEAU_VAULT_ITEM_SCHEMA@@P6AXPEAX@Z$1?VaultFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&VaultFree(void *),0>>::~unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&VaultFree(void *),0>>(void)
0x18001c1b9  mov     eax, ebx
0x18001c1bb  mov     rcx, [rbp+57h+var_8]
0x18001c1bf  xor     rcx, rsp; StackCookie
0x18001c1c2  call    __security_check_cookie
0x18001c1c7  mov     rbx, [rsp+0D0h+arg_0]
0x18001c1cf  add     rsp, 0D0h
0x18001c1d6  pop     rbp
0x18001c1d7  retn
```
