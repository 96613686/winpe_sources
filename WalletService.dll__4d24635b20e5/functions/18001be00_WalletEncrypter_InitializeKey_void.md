# WalletEncrypter::InitializeKey(void)

- ea: `0x18001be00`
- end: `0x18001bed9`
- name: `?InitializeKey@WalletEncrypter@@AEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(WalletEncrypter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800110f0`

## callees

- `0x18001b340`
- `0x18001b3f4`
- `0x18001b584`
- `0x18001ba14`
- `0x18001bc58`
- `0x18001be00`
- `0x18001bee0`
- `0x18001c230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be40`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001be36`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001be36`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::InitializeKey(void **this)
{
  __int64 *v2; // rax
  signed int LastError; // eax
  int ExistingKey; // ebx
  int v6; // [rsp+38h] [rbp+10h] BYREF
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  v2 = tlx::replace<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>((__int64 *)&v7);
  if ( (unsigned int)VaultOpenVault(Vault_DefaultVault_ID, 0x10000000, v2) )
  {
    LastError = GetLastError();
    ExistingKey = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        ExistingKey = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      ExistingKey = -2143748092;
    }
  }
  else
  {
    ExistingKey = WalletEncrypter::InitializeWalletCredVaultSchema(v7);
    if ( ExistingKey >= 0 )
    {
      if ( (int)WalletEncrypter::GetKeyFromRegistry((WalletEncrypter *)this) >= 0
        || (ExistingKey = WalletEncrypter::GetExistingKey(this, &v7, &v6), ExistingKey >= 0)
        && (v6
         || (ExistingKey = WalletEncrypter::CreateKey((__int64)this, this + 3), ExistingKey >= 0)
         && (ExistingKey = WalletEncrypter::SaveKey((__int64)this, (__int64 *)&v7), ExistingKey >= 0)) )
      {
        ExistingKey = 0;
      }
    }
  }
  tlx::unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>(&v7);
  return (unsigned int)ExistingKey;
}

```

## disassembly

```asm
0x18001be00  mov     rax, rsp
0x18001be03  mov     [rax+8], rbx
0x18001be07  push    rdi
0x18001be08  sub     rsp, 20h
0x18001be0c  mov     rdi, rcx
0x18001be0f  mov     dword ptr [rax+10h], 0
0x18001be16  lea     rcx, [rax+18h]
0x18001be1a  mov     qword ptr [rax+18h], 0
0x18001be22  call    ??$replace@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001be27  mov     r8, rax
0x18001be2a  lea     rcx, Vault_DefaultVault_ID
0x18001be31  mov     edx, 10000000h
0x18001be36  call    cs:__imp_VaultOpenVault
0x18001be3c  test    eax, eax
0x18001be3e  jz      short loc_18001BE60
0x18001be40  call    cs:__imp_GetLastError
0x18001be46  mov     ebx, eax
0x18001be48  test    eax, eax
0x18001be4a  jz      short loc_18001BE59
0x18001be4c  jle     short loc_18001BEC2
0x18001be4e  movzx   ebx, ax
0x18001be51  or      ebx, 80070000h
0x18001be57  jmp     short loc_18001BEC2
0x18001be59  mov     ebx, 80390004h
0x18001be5e  jmp     short loc_18001BEC2
0x18001be60  mov     rcx, [rsp+28h+arg_10]; void *
0x18001be65  call    ?InitializeWalletCredVaultSchema@WalletEncrypter@@CAJPEAX@Z; WalletEncrypter::InitializeWalletCredVaultSchema(void *)
0x18001be6a  mov     ebx, eax
0x18001be6c  test    eax, eax
0x18001be6e  js      short loc_18001BEC2
0x18001be70  mov     rcx, rdi; this
0x18001be73  call    ?GetKeyFromRegistry@WalletEncrypter@@AEAAJXZ; WalletEncrypter::GetKeyFromRegistry(void)
0x18001be78  test    eax, eax
0x18001be7a  jns     short loc_18001BEC0
0x18001be7c  lea     r8, [rsp+28h+arg_8]
0x18001be81  mov     rcx, rdi
0x18001be84  lea     rdx, [rsp+28h+arg_10]
0x18001be89  call    ?GetExistingKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@AEAH@Z; WalletEncrypter::GetExistingKey(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &,int &)
0x18001be8e  mov     ebx, eax
0x18001be90  test    eax, eax
0x18001be92  js      short loc_18001BEC2
0x18001be94  cmp     [rsp+28h+arg_8], 0
0x18001be99  jnz     short loc_18001BEC0
0x18001be9b  lea     rdx, [rdi+18h]
0x18001be9f  mov     rcx, rdi
0x18001bea2  call    ?CreateKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; WalletEncrypter::CreateKey(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001bea7  mov     ebx, eax
0x18001bea9  test    eax, eax
0x18001beab  js      short loc_18001BEC2
0x18001bead  lea     rdx, [rsp+28h+arg_10]
0x18001beb2  mov     rcx, rdi
0x18001beb5  call    ?SaveKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@@Z; WalletEncrypter::SaveKey(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001beba  mov     ebx, eax
0x18001bebc  test    eax, eax
0x18001bebe  js      short loc_18001BEC2
0x18001bec0  xor     ebx, ebx
0x18001bec2  lea     rcx, [rsp+28h+arg_10]
0x18001bec7  call    ??1?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(void)
0x18001becc  mov     eax, ebx
0x18001bece  mov     rbx, [rsp+28h+arg_0]
0x18001bed3  add     rsp, 20h
0x18001bed7  pop     rdi
0x18001bed8  retn
```
