# WalletEncrypter::CommitNewEncryptionKey(void)

- ea: `0x18001b4d8`
- end: `0x18001b57e`
- name: `?CommitNewEncryptionKey@WalletEncrypter@@QEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(WalletEncrypter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011924`

## callees

- `0x18001b310`
- `0x18001b340`
- `0x18001b3f4`
- `0x18001b4d8`
- `0x18001c230`
- `0x18001c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b50d`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001b503`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultOpenVault` at `0x18001b503`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::CommitNewEncryptionKey(WalletEncrypter *this)
{
  __int64 *v2; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  void **v5; // rdx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v2 = tlx::replace<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>(&v7);
  if ( !(unsigned int)VaultOpenVault(Vault_DefaultVault_ID, 0x10000000, v2) )
  {
    if ( *((_QWORD *)this + 4) )
    {
      tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&long BCryptDestroyKey(void *),0>>::swap((char *)this + 24);
      tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long BCryptDestroyKey(void *),0>>(v5);
      v4 = WalletEncrypter::SaveKey(this, &v7);
      if ( v4 >= 0 )
      {
        v4 = 0;
        goto LABEL_13;
      }
    }
    else
    {
      v4 = -2147418113;
    }
    goto LABEL_11;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v4 = -2143748092;
  }
  if ( v4 < 0 )
LABEL_11:
    __int2c();
LABEL_13:
  tlx::unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,unsigned long (*)(void * const &),&unsigned long wp::detail::_WpCloseVaultHandle(void * const &),0>>(&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b4d8  push    rbx
0x18001b4da  sub     rsp, 20h
0x18001b4de  mov     rbx, rcx
0x18001b4e1  mov     [rsp+28h+arg_8], 0
0x18001b4ea  lea     rcx, [rsp+28h+arg_8]
0x18001b4ef  call    ??$replace@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001b4f4  mov     r8, rax
0x18001b4f7  lea     rcx, Vault_DefaultVault_ID
0x18001b4fe  mov     edx, 10000000h
0x18001b503  call    cs:__imp_VaultOpenVault
0x18001b509  test    eax, eax
0x18001b50b  jz      short loc_18001B531
0x18001b50d  call    cs:__imp_GetLastError
0x18001b513  mov     ebx, eax
0x18001b515  test    eax, eax
0x18001b517  jz      short loc_18001B526
0x18001b519  jle     short loc_18001B52B
0x18001b51b  movzx   ebx, ax
0x18001b51e  or      ebx, 80070000h
0x18001b524  jmp     short loc_18001B52B
0x18001b526  mov     ebx, 80390004h
0x18001b52b  test    ebx, ebx
0x18001b52d  jns     short loc_18001B56C
0x18001b52f  jmp     short loc_18001B566
0x18001b531  lea     rdx, [rbx+20h]
0x18001b535  cmp     qword ptr [rdx], 0
0x18001b539  jnz     short loc_18001B542
0x18001b53b  mov     ebx, 8000FFFFh
0x18001b540  jmp     short loc_18001B566
0x18001b542  lea     rcx, [rbx+18h]
0x18001b546  call    ?swap@?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAAXAEAV12@@Z; tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>>::swap(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001b54b  mov     rcx, rdx
0x18001b54e  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001b553  lea     rdx, [rsp+28h+arg_8]
0x18001b558  mov     rcx, rbx
0x18001b55b  call    ?SaveKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@@Z; WalletEncrypter::SaveKey(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001b560  mov     ebx, eax
0x18001b562  test    eax, eax
0x18001b564  jns     short loc_18001B56A
0x18001b566  int     2Ch; Windows NT - assertion failure
0x18001b568  jmp     short loc_18001B56C
0x18001b56a  xor     ebx, ebx
0x18001b56c  lea     rcx, [rsp+28h+arg_8]
0x18001b571  call    ??1?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>::~unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>>(void)
0x18001b576  mov     eax, ebx
0x18001b578  add     rsp, 20h
0x18001b57c  pop     rbx
0x18001b57d  retn
```
