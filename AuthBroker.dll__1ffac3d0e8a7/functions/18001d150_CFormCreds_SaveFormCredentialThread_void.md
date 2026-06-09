# CFormCreds::SaveFormCredentialThread(void *)

- ea: `0x18001d150`
- end: `0x18001d380`
- name: `?SaveFormCredentialThread@CFormCreds@@SAKPEAX@Z`
- size: `560`
- prototype: `unsigned int __fastcall(void *pParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001c7e4`
- `0x18001d150`
- `0x18001d388`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18001d299`
- `ntdll!_wcsicmp` at `0x18001d299`
- `VAULTCLI!VaultAddItem` at `0x18001d31d`
- `VAULTCLI!VaultAddItem` at `0x18001d31d`
- `VAULTCLI!VaultGetItem` at `0x18001d267`
- `VAULTCLI!VaultGetItem` at `0x18001d267`
- `VAULTCLI!VaultCloseVault` at `0x18001d34f`
- `VAULTCLI!VaultCloseVault` at `0x18001d34f`
- `VAULTCLI!VaultFree` at `0x18001d33d`
- `VAULTCLI!VaultFree` at `0x18001d33d`
- `VAULTCLI!VaultOpenVault` at `0x18001d1ca`
- `VAULTCLI!VaultOpenVault` at `0x18001d1ca`

## string_xrefs

- `0x18001d2ef`: `Web Authentication Broker`

## pseudocode

```c
__int64 __fastcall CFormCreds::SaveFormCredentialThread(_SAVE_FORM_CREDENTIAL_PARAM *pParam)
{
  int Item; // eax
  const wchar_t *String; // rdx
  _VAULT_ITEM_ELEMENT *pAuthenticatorElement; // rcx
  void *hVault; // [rsp+40h] [rbp-C0h] BYREF
  _VAULT_ITEM *pItem; // [rsp+48h] [rbp-B8h] BYREF
  _VAULT_ITEM_ELEMENT ResourceElement; // [rsp+50h] [rbp-B0h] BYREF
  _VAULT_ITEM_ELEMENT IdentityElement; // [rsp+70h] [rbp-90h] BYREF
  _VAULT_ITEM_ELEMENT PackageSidElement; // [rsp+90h] [rbp-70h] BYREF
  _VAULT_ITEM_ELEMENT AuthenticatorElement; // [rsp+B0h] [rbp-50h] BYREF
  _VAULT_ITEM VaultItem; // [rsp+D0h] [rbp-30h] BYREF

  hVault = 0;
  pItem = 0;
  memset(&ResourceElement, 0, sizeof(ResourceElement));
  memset(&IdentityElement, 0, sizeof(IdentityElement));
  memset(&AuthenticatorElement, 0, sizeof(AuthenticatorElement));
  memset(&PackageSidElement, 0, sizeof(PackageSidElement));
  memset_0(&VaultItem, 0, sizeof(VaultItem));
  if ( !(unsigned int)VaultOpenVault(&Vault_DefaultVault_ID, 0, &hVault) )
  {
    ResourceElement.ItemValue.8 = ($A5D428126EF00C1ACC863D9D3F0013C1)(unsigned __int64)pParam->lpwszUrl;
    IdentityElement.ItemValue.8 = ($A5D428126EF00C1ACC863D9D3F0013C1)(unsigned __int64)pParam->lpwszUserName;
    PackageSidElement.ItemValue.String = (wchar_t *)&gWABPackageSidBuffer;
    *(_QWORD *)&ResourceElement.SchemaElementId = 1;
    *(_QWORD *)&ResourceElement.ItemValue.Type = 7;
    *(_QWORD *)&IdentityElement.SchemaElementId = 2;
    *(_QWORD *)&IdentityElement.ItemValue.Type = 7;
    *(_QWORD *)&PackageSidElement.SchemaElementId = 5;
    *(_QWORD *)&PackageSidElement.ItemValue.Type = 12;
    PackageSidElement.ItemValue.ByteArray.pByteArray = 0;
    Item = VaultGetItem(
             hVault,
             &Vault_Schema_WebPassword,
             &ResourceElement,
             &IdentityElement,
             &PackageSidElement,
             0,
             0,
             &pItem);
    if ( Item != 1168 )
    {
      if ( Item )
        goto $Cleanup_12;
      String = &source;
      pAuthenticatorElement = pItem->pAuthenticatorElement;
      if ( pAuthenticatorElement->ItemValue.String )
        String = pAuthenticatorElement->ItemValue.String;
      if ( !_wcsicmp(pParam->lpwszPassword, String) )
        goto $UpdateLastUsedUser;
    }
    AuthenticatorElement.ItemValue.8 = ($A5D428126EF00C1ACC863D9D3F0013C1)(unsigned __int64)pParam->lpwszPassword;
    *(_QWORD *)&AuthenticatorElement.SchemaElementId = 3;
    VaultItem.pResourceElement = &ResourceElement;
    VaultItem.pIdentityElement = &IdentityElement;
    VaultItem.pAuthenticatorElement = &AuthenticatorElement;
    VaultItem.pPackageSid = &PackageSidElement;
    VaultItem.pszCredentialFriendlyName = L"Web Authentication Broker";
    *(_QWORD *)&AuthenticatorElement.ItemValue.Type = 7;
    memset(&VaultItem.LastModified, 0, 24);
    VaultItem.SchemaId = Vault_Schema_WebPassword;
    if ( !(unsigned int)VaultAddItem(hVault, &VaultItem, 0, 0, 0) )
$UpdateLastUsedUser:
      SavePreferredAccountForUrl(pParam->lpwszUrl, pParam->lpwszUserName, (CFormCreds *)pParam->pThis);
  }
$Cleanup_12:
  VaultFree(pItem);
  if ( hVault )
    VaultCloseVault(&hVault);
  FreeSaveFormCredentialParam(pParam);
  return 0;
}

```

## disassembly

```asm
0x18001d150  mov     [rsp-8+arg_8], rbx
0x18001d155  mov     [rsp-8+arg_10], rdi
0x18001d15a  push    rbp
0x18001d15b  lea     rbp, [rsp-30h]
0x18001d160  sub     rsp, 130h
0x18001d167  mov     rax, cs:__security_cookie
0x18001d16e  xor     rax, rsp
0x18001d171  mov     [rbp+30h+var_10], rax
0x18001d175  xorps   xmm0, xmm0
0x18001d178  xorps   xmm1, xmm1
0x18001d17b  xor     edi, edi
0x18001d17d  mov     rbx, pParam
0x18001d180  xor     edx, edx; Val
0x18001d182  mov     [rsp+130h+hVault], rdi
0x18001d187  lea     pParam, [rbp+30h+VaultItem]; void *
0x18001d18b  mov     [rsp+130h+pItem], rdi
0x18001d190  movups  xmmword ptr [rsp+130h+ResourceElement.SchemaElementId], xmm0
0x18001d195  lea     r8d, [rdi+50h]; Size
0x18001d199  movups  xmmword ptr [rsp+130h+ResourceElement.ItemValue.___u1], xmm0
0x18001d19e  movups  xmmword ptr [rsp+130h+IdentityElement.SchemaElementId], xmm1
0x18001d1a3  movups  xmmword ptr [rbp+30h+IdentityElement.ItemValue.___u1], xmm1
0x18001d1a7  movups  xmmword ptr [rbp+30h+AuthenticatorElement.SchemaElementId], xmm0
0x18001d1ab  movups  xmmword ptr [rbp+30h+AuthenticatorElement.ItemValue.___u1], xmm0
0x18001d1af  movups  xmmword ptr [rbp+30h+PackageSidElement.SchemaElementId], xmm1
0x18001d1b3  movups  xmmword ptr [rbp+30h+PackageSidElement.ItemValue.___u1], xmm1
0x18001d1b7  call    memset_0
0x18001d1bc  lea     r8, [rsp+130h+hVault]
0x18001d1c1  xor     edx, edx
0x18001d1c3  lea     pParam, Vault_DefaultVault_ID
0x18001d1ca  call    cs:__imp_VaultOpenVault
0x18001d1d0  test    eax, eax
0x18001d1d2  jnz     $Cleanup_12
0x18001d1d8  mov     rax, [rbx+8]
0x18001d1dc  lea     r9, [rsp+130h+IdentityElement]
0x18001d1e1  mov     pParam, [rsp+130h+hVault]
0x18001d1e6  lea     r8, [rsp+130h+ResourceElement]
0x18001d1eb  mov     qword ptr [rsp+130h+ResourceElement.ItemValue.___u1], rax
0x18001d1f0  lea     rdx, Vault_Schema_WebPassword
0x18001d1f7  mov     rax, [rbx+10h]
0x18001d1fb  mov     qword ptr [rbp+30h+IdentityElement.ItemValue.___u1], rax
0x18001d1ff  lea     rax, ?gWABPackageSidBuffer@@3U_SID_BUFFER@@A; _SID_BUFFER gWABPackageSidBuffer
0x18001d206  mov     qword ptr [rbp+30h+PackageSidElement.ItemValue.___u1], rax
0x18001d20a  lea     rax, [rsp+130h+pItem]
0x18001d20f  mov     [rsp+130h+var_F8], rax
0x18001d214  lea     rax, [rbp+30h+PackageSidElement]
0x18001d218  mov     [rsp+130h+var_100], edi
0x18001d21c  mov     [rsp+130h+var_108], rdi
0x18001d221  mov     [rsp+130h+var_110], rax
0x18001d226  mov     qword ptr [rsp+130h+ResourceElement.SchemaElementId], 1
0x18001d22f  mov     qword ptr [rsp+130h+ResourceElement.ItemValue.Type], 7
0x18001d238  mov     qword ptr [rsp+130h+ResourceElement.ItemValue.___u1+8], rdi
0x18001d23d  mov     qword ptr [rsp+130h+IdentityElement.SchemaElementId], 2
0x18001d246  mov     qword ptr [rsp+130h+IdentityElement.ItemValue.Type], 7
0x18001d24f  mov     qword ptr [rbp+30h+IdentityElement.ItemValue.___u1+8], rdi
0x18001d253  mov     qword ptr [rbp+30h+PackageSidElement.SchemaElementId], 5
0x18001d25b  mov     qword ptr [rbp+30h+PackageSidElement.ItemValue.Type], 0Ch
0x18001d263  mov     qword ptr [rbp+30h+PackageSidElement.ItemValue.___u1+8], rdi
0x18001d267  call    cs:__imp_VaultGetItem
0x18001d26d  cmp     eax, 490h
0x18001d272  jz      short loc_18001D2A7
0x18001d274  test    eax, eax
0x18001d276  jnz     $Cleanup_12
0x18001d27c  mov     rax, [rsp+130h+pItem]
0x18001d281  lea     rdx, source
0x18001d288  mov     pParam, [rax+28h]
0x18001d28c  cmp     [pParam+10h], rdi
0x18001d290  cmovnz  rdx, [pParam+10h]; String2
0x18001d295  mov     pParam, [rbx+18h]; String1
0x18001d299  call    cs:__imp__wcsicmp
0x18001d29f  test    eax, eax
0x18001d2a1  jz      $UpdateLastUsedUser
0x18001d2a7  mov     rax, [rbx+18h]
0x18001d2ab  lea     rdx, [rbp+30h+VaultItem]
0x18001d2af  movups  xmm0, xmmword ptr cs:Vault_Schema_WebPassword.Data1
0x18001d2b6  mov     pParam, [rsp+130h+hVault]
0x18001d2bb  xor     r9d, r9d
0x18001d2be  mov     qword ptr [rbp+30h+AuthenticatorElement.ItemValue.___u1], rax
0x18001d2c2  xor     r8d, r8d
0x18001d2c5  lea     rax, [rsp+130h+ResourceElement]
0x18001d2ca  mov     qword ptr [rbp+30h+AuthenticatorElement.SchemaElementId], 3
0x18001d2d2  mov     [rbp+30h+VaultItem.pResourceElement], rax
0x18001d2d6  lea     rax, [rsp+130h+IdentityElement]
0x18001d2db  mov     [rbp+30h+VaultItem.pIdentityElement], rax
0x18001d2df  lea     rax, [rbp+30h+AuthenticatorElement]
0x18001d2e3  mov     [rbp+30h+VaultItem.pAuthenticatorElement], rax
0x18001d2e7  lea     rax, [rbp+30h+PackageSidElement]
0x18001d2eb  mov     [rbp+30h+VaultItem.pPackageSid], rax
0x18001d2ef  lea     rax, aWebAuthenticat; "Web Authentication Broker"
0x18001d2f6  mov     [rbp+30h+VaultItem.pszCredentialFriendlyName], rax
0x18001d2fa  mov     qword ptr [rbp+30h+AuthenticatorElement.ItemValue.Type], 7
0x18001d302  mov     qword ptr [rbp+30h+AuthenticatorElement.ItemValue.___u1+8], rdi
0x18001d306  mov     qword ptr [rbp+30h+VaultItem.LastModified.dwLowDateTime], rdi
0x18001d30a  mov     qword ptr [rbp+30h+VaultItem.dwPropertiesCount], rdi
0x18001d30e  mov     dword ptr [rbp+30h+VaultItem.pPropertyElements+4], edi
0x18001d311  movdqu  xmmword ptr [rbp+30h+VaultItem.SchemaId.Data1], xmm0
0x18001d316  mov     [rbp+30h+VaultItem.dwFlags], edi
0x18001d319  mov     dword ptr [rsp+130h+var_110], edi
0x18001d31d  call    cs:__imp_VaultAddItem
0x18001d323  test    eax, eax
0x18001d325  jnz     short $Cleanup_12
0x18001d327  mov     r8, [rbx+20h]; pThis
0x18001d32b  mov     rdx, [rbx+10h]; lpwszUserName
0x18001d32f  mov     pParam, [rbx+8]; lpwszUrl
0x18001d333  call    ?SavePreferredAccountForUrl@@YAKPEBG0PEAVCFormCreds@@@Z; SavePreferredAccountForUrl(ushort const *,ushort const *,CFormCreds *)
0x18001d338  mov     pParam, [rsp+130h+pItem]
0x18001d33d  call    cs:__imp_VaultFree
0x18001d343  cmp     [rsp+130h+hVault], rdi
0x18001d348  jz      short loc_18001D355
0x18001d34a  lea     pParam, [rsp+130h+hVault]
0x18001d34f  call    cs:__imp_VaultCloseVault
0x18001d355  mov     pParam, rbx; pParam
0x18001d358  call    ?FreeSaveFormCredentialParam@@YAXPEAU_SAVE_FORM_CREDENTIAL_PARAM@@@Z; FreeSaveFormCredentialParam(_SAVE_FORM_CREDENTIAL_PARAM *)
0x18001d35d  xor     eax, eax
0x18001d35f  mov     pParam, [rbp+30h+var_10]
0x18001d363  xor     pParam, rsp; StackCookie
0x18001d366  call    __security_check_cookie
0x18001d36b  lea     r11, [rsp+130h+var_s0]
0x18001d373  mov     rbx, [r11+18h]
0x18001d377  mov     rdi, [r11+20h]
0x18001d37b  mov     rsp, r11
0x18001d37e  pop     rbp
0x18001d37f  retn
```
