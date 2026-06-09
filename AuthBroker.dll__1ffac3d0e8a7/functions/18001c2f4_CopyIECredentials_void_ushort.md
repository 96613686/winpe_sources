# CopyIECredentials(void *,ushort *)

- ea: `0x18001c2f4`
- end: `0x18001c5ab`
- name: `?CopyIECredentials@@YAKPEAXPEAG@Z`
- size: `695`
- prototype: `__int64 __fastcall(void *hVault, wchar_t *lpwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c980`

## callees

- `0x18001c2f4`
- `0x18001cf28`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18001c48a`
- `ntdll!_wcsicmp` at `0x18001c48a`
- `VAULTCLI!VaultAddItem` at `0x18001c542`
- `VAULTCLI!VaultAddItem` at `0x18001c542`
- `VAULTCLI!VaultGetItem` at `0x18001c4d3`
- `VAULTCLI!VaultGetItem` at `0x18001c4d3`
- `VAULTCLI!VaultFree` at `0x18001c554`
- `VAULTCLI!VaultFree` at `0x18001c570`
- `VAULTCLI!VaultFree` at `0x18001c57b`
- `VAULTCLI!VaultFree` at `0x18001c554`
- `VAULTCLI!VaultFree` at `0x18001c570`
- `VAULTCLI!VaultFree` at `0x18001c57b`
- `VAULTCLI!VaultFindItems` at `0x18001c3ab`
- `VAULTCLI!VaultFindItems` at `0x18001c3ab`

## string_xrefs

- `0x18001c537`: `Web Authentication Broker`

## pseudocode

```c
__int64 __fastcall CopyIECredentials(void *hVault, wchar_t *lpwszUrl)
{
  unsigned int Items; // r14d
  unsigned int i; // esi
  unsigned int j; // edx
  _VAULT_ITEM_ELEMENT *pPropertyElements; // rcx
  __int64 v8; // rax
  unsigned __int8 *pByteArray; // r9
  __int64 v10; // rax
  unsigned int k; // edi
  __int64 v12; // r15
  unsigned int nItems; // [rsp+40h] [rbp-99h] BYREF
  _VAULT_ITEM *pItems; // [rsp+48h] [rbp-91h] BYREF
  _VAULT_ITEM *pItem; // [rsp+50h] [rbp-89h] BYREF
  _VAULT_ITEM_ELEMENT ResourceElement; // [rsp+58h] [rbp-81h] BYREF
  _VAULT_ITEM_ELEMENT PackageSidElement; // [rsp+78h] [rbp-61h] BYREF
  _VAULT_ITEM VaultItem; // [rsp+A0h] [rbp-39h] BYREF

  memset_0(&VaultItem, 0, sizeof(VaultItem));
  *(_QWORD *)&ResourceElement.SchemaElementId = 1;
  pItems = 0;
  PackageSidElement.ItemValue.String = (wchar_t *)&gWABPackageSidBuffer;
  nItems = 0;
  pItem = 0;
  *(_QWORD *)&ResourceElement.ItemValue.Type = 7;
  ResourceElement.ItemValue.8 = ($A5D428126EF00C1ACC863D9D3F0013C1)(unsigned __int64)lpwszUrl;
  *(_QWORD *)&PackageSidElement.SchemaElementId = 5;
  *(_QWORD *)&PackageSidElement.ItemValue.Type = 12;
  PackageSidElement.ItemValue.ByteArray.pByteArray = 0;
  Items = VaultFindItems(hVault, &Vault_Schema_WebPassword, &ResourceElement, 0, 512, &nItems, &pItems);
  if ( Items == 1168 )
  {
    Items = 0;
  }
  else
  {
    for ( i = 0; i < nItems; ++i )
    {
      if ( (pItems[i].dwFlags & 0x800) == 0 && !pItems[i].pPackageSid )
      {
        for ( j = 0; j < pItems[i].dwPropertiesCount; ++j )
        {
          pPropertyElements = pItems[i].pPropertyElements;
          v8 = j;
          if ( pPropertyElements[v8].SchemaElementId == ElementId_AppStart
            && pPropertyElements[v8].ItemValue.Type == ElementType_ByteArray
            && pPropertyElements[v8].ItemValue.Int == 16 )
          {
            pByteArray = pPropertyElements[v8].ItemValue.ByteArray.pByteArray;
            v10 = *(_QWORD *)&gIEApplicationId.Data1 - *(_QWORD *)pByteArray;
            if ( *(_QWORD *)&gIEApplicationId.Data1 == *(_QWORD *)pByteArray )
              v10 = *(_QWORD *)gIEApplicationId.Data4 - *((_QWORD *)pByteArray + 1);
            if ( !v10 )
            {
              for ( k = 0; k < nItems; ++k )
              {
                if ( i != k )
                {
                  v12 = k;
                  if ( IsWABSavedCredential(&pItems[v12]) )
                  {
                    if ( !_wcsicmp(
                            pItems[i].pIdentityElement->ItemValue.String,
                            pItems[v12].pIdentityElement->ItemValue.String) )
                      goto LABEL_24;
                  }
                }
              }
              Items = VaultGetItem(
                        hVault,
                        &Vault_Schema_WebPassword,
                        pItems[i].pResourceElement,
                        pItems[i].pIdentityElement,
                        pItems[i].pPackageSid,
                        0,
                        0,
                        &pItem);
              if ( !Items )
              {
                memset_0(&VaultItem, 0, sizeof(VaultItem));
                VaultItem.pResourceElement = &ResourceElement;
                VaultItem.SchemaId = Vault_Schema_WebPassword;
                VaultItem.pIdentityElement = pItem->pIdentityElement;
                VaultItem.pAuthenticatorElement = pItem->pAuthenticatorElement;
                VaultItem.pPackageSid = &PackageSidElement;
                VaultItem.pszCredentialFriendlyName = L"Web Authentication Broker";
                Items = VaultAddItem(hVault, &VaultItem, 0, 0, 0);
                if ( !Items )
                {
                  VaultFree(pItem);
                  pItem = 0;
                  break;
                }
              }
              goto $Cleanup_6;
            }
          }
        }
      }
LABEL_24:
      ;
    }
  }
$Cleanup_6:
  VaultFree(pItem);
  VaultFree(pItems);
  return Items;
}

```

## disassembly

```asm
0x18001c2f4  mov     [rsp-8+arg_10], rbx
0x18001c2f9  push    rbp
0x18001c2fa  push    rsi
0x18001c2fb  push    rdi
0x18001c2fc  push    r12
0x18001c2fe  push    r13
0x18001c300  push    r14
0x18001c302  push    r15
0x18001c304  lea     rbp, [rsp-27h]
0x18001c309  sub     rsp, 100h
0x18001c310  mov     rax, cs:__security_cookie
0x18001c317  xor     rax, rsp
0x18001c31a  mov     [rbp+57h+var_40], rax
0x18001c31e  mov     rbx, lpwszUrl
0x18001c321  mov     r12, hVault
0x18001c324  xor     edx, edx; Val
0x18001c326  lea     hVault, [rbp+57h+VaultItem]; void *
0x18001c32a  lea     r8d, [lpwszUrl+50h]; Size
0x18001c32e  call    memset_0
0x18001c333  xor     r13d, r13d
0x18001c336  mov     qword ptr [rsp+130h+ResourceElement.SchemaElementId], 1
0x18001c33f  lea     rax, ?gWABPackageSidBuffer@@3U_SID_BUFFER@@A; _SID_BUFFER gWABPackageSidBuffer
0x18001c346  mov     [rsp+130h+pItems], r13
0x18001c34b  mov     qword ptr [rbp+57h+PackageSidElement.ItemValue.___u1], rax
0x18001c34f  lea     r8, [rsp+130h+ResourceElement]
0x18001c354  lea     rax, [rsp+130h+pItems]
0x18001c359  mov     [rsp+130h+nItems], r13d
0x18001c35e  mov     [rsp+130h+var_100], rax
0x18001c363  lea     lpwszUrl, Vault_Schema_WebPassword
0x18001c36a  lea     rax, [rsp+130h+nItems]
0x18001c36f  mov     [rsp+130h+pItem], r13
0x18001c374  mov     [rsp+130h+var_108], rax
0x18001c379  xor     r9d, r9d
0x18001c37c  mov     hVault, r12
0x18001c37f  mov     dword ptr [rsp+130h+var_110], 200h
0x18001c387  mov     qword ptr [rbp+57h+ResourceElement.ItemValue.Type], 7
0x18001c38f  mov     qword ptr [rbp+57h+ResourceElement.ItemValue.___u1+8], r13
0x18001c393  mov     qword ptr [rbp+57h+ResourceElement.ItemValue.___u1], rbx
0x18001c397  mov     qword ptr [rbp+57h+PackageSidElement.SchemaElementId], 5
0x18001c39f  mov     qword ptr [rbp+57h+PackageSidElement.ItemValue.Type], 0Ch
0x18001c3a7  mov     qword ptr [rbp+57h+PackageSidElement.ItemValue.___u1+8], r13
0x18001c3ab  call    cs:__imp_VaultFindItems
0x18001c3b1  mov     r14d, eax
0x18001c3b4  cmp     eax, 490h
0x18001c3b9  jnz     short loc_18001C3C3
0x18001c3bb  mov     r14d, r13d
0x18001c3be  jmp     $Cleanup_6
0x18001c3c3  mov     esi, r13d
0x18001c3c6  cmp     [rsp+130h+nItems], r13d
0x18001c3cb  jbe     $Cleanup_6
0x18001c3d1  mov     r8, [rsp+130h+pItems]
0x18001c3d6  mov     eax, esi
0x18001c3d8  lea     rbx, [rax+rax*4]
0x18001c3dc  add     rbx, rbx
0x18001c3df  test    dword ptr [r8+rbx*8+40h], 800h
0x18001c3e8  jnz     loc_18001C55F
0x18001c3ee  cmp     [r8+rbx*8+30h], r13
0x18001c3f3  jnz     loc_18001C55F
0x18001c3f9  mov     edx, r13d
0x18001c3fc  cmp     edx, [r8+rbx*8+44h]
0x18001c401  jnb     loc_18001C55F
0x18001c407  mov     hVault, [r8+rbx*8+48h]
0x18001c40c  mov     eax, edx
0x18001c40e  shl     rax, 5
0x18001c412  cmp     dword ptr [rax+hVault], 64h ; 'd'
0x18001c416  jnz     short loc_18001C447
0x18001c418  cmp     dword ptr [rax+hVault+8], 8
0x18001c41d  jnz     short loc_18001C447
0x18001c41f  cmp     dword ptr [rax+hVault+10h], 10h
0x18001c424  jnz     short loc_18001C447
0x18001c426  mov     r9, [rax+hVault+18h]
0x18001c42b  mov     rax, qword ptr cs:?gIEApplicationId@@3U_GUID@@A.Data1; _GUID gIEApplicationId ...
0x18001c432  sub     rax, [r9]
0x18001c435  jnz     short loc_18001C442
0x18001c437  mov     rax, qword ptr cs:?gIEApplicationId@@3U_GUID@@A.Data4; _GUID gIEApplicationId ...
0x18001c43e  sub     rax, [r9+8]
0x18001c442  test    rax, rax
0x18001c445  jz      short loc_18001C44B
0x18001c447  inc     edx
0x18001c449  jmp     short loc_18001C3FC
0x18001c44b  mov     edi, r13d
0x18001c44e  cmp     edi, [rsp+130h+nItems]
0x18001c452  jnb     short loc_18001C49C
0x18001c454  cmp     esi, edi
0x18001c456  jz      short loc_18001C498
0x18001c458  mov     hVault, [rsp+130h+pItems]
0x18001c45d  mov     eax, edi
0x18001c45f  lea     r15, [rax+rax*4]
0x18001c463  shl     r15, 4
0x18001c467  add     hVault, r15; pItem
0x18001c46a  call    ?IsWABSavedCredential@@YAEPEAU_VAULT_ITEM@@@Z; IsWABSavedCredential(_VAULT_ITEM *)
0x18001c46f  test    al, al
0x18001c471  jz      short loc_18001C498
0x18001c473  mov     rax, [rsp+130h+pItems]
0x18001c478  mov     lpwszUrl, [r15+rax+20h]
0x18001c47d  mov     hVault, [rax+rbx*8+20h]
0x18001c482  mov     lpwszUrl, [lpwszUrl+10h]; String2
0x18001c486  mov     hVault, [hVault+10h]; String1
0x18001c48a  call    cs:__imp__wcsicmp
0x18001c490  test    eax, eax
0x18001c492  jz      loc_18001C55F
0x18001c498  inc     edi
0x18001c49a  jmp     short loc_18001C44E
0x18001c49c  mov     r8, [rsp+130h+pItems]
0x18001c4a1  lea     rax, [rsp+130h+pItem]
0x18001c4a6  mov     [rsp+130h+var_F8], rax
0x18001c4ab  lea     lpwszUrl, Vault_Schema_WebPassword
0x18001c4b2  mov     dword ptr [rsp+130h+var_100], r13d
0x18001c4b7  mov     hVault, r12
0x18001c4ba  mov     [rsp+130h+var_108], r13
0x18001c4bf  mov     rax, [r8+rbx*8+30h]
0x18001c4c4  mov     r9, [r8+rbx*8+20h]
0x18001c4c9  mov     r8, [r8+rbx*8+18h]
0x18001c4ce  mov     [rsp+130h+var_110], rax
0x18001c4d3  call    cs:__imp_VaultGetItem
0x18001c4d9  mov     r14d, eax
0x18001c4dc  test    eax, eax
0x18001c4de  jnz     $Cleanup_6
0x18001c4e4  xor     edx, edx; Val
0x18001c4e6  lea     r8d, [rax+50h]; Size
0x18001c4ea  lea     hVault, [rbp+57h+VaultItem]; void *
0x18001c4ee  call    memset_0
0x18001c4f3  mov     hVault, [rsp+130h+pItem]
0x18001c4f8  lea     rax, [rsp+130h+ResourceElement]
0x18001c4fd  movups  xmm0, xmmword ptr cs:Vault_Schema_WebPassword.Data1
0x18001c504  mov     [rbp+57h+VaultItem.pResourceElement], rax
0x18001c508  lea     lpwszUrl, [rbp+57h+VaultItem]
0x18001c50c  xor     r9d, r9d
0x18001c50f  mov     dword ptr [rsp+130h+var_110], r13d
0x18001c514  movdqu  xmmword ptr [rbp+57h+VaultItem.SchemaId.Data1], xmm0
0x18001c519  mov     rax, [hVault+20h]
0x18001c51d  xor     r8d, r8d
0x18001c520  mov     [rbp+57h+VaultItem.pIdentityElement], rax
0x18001c524  mov     rax, [hVault+28h]
0x18001c528  mov     hVault, r12
0x18001c52b  mov     [rbp+57h+VaultItem.pAuthenticatorElement], rax
0x18001c52f  lea     rax, [rbp+57h+PackageSidElement]
0x18001c533  mov     [rbp+57h+VaultItem.pPackageSid], rax
0x18001c537  lea     rax, aWebAuthenticat; "Web Authentication Broker"
0x18001c53e  mov     [rbp+57h+VaultItem.pszCredentialFriendlyName], rax
0x18001c542  call    cs:__imp_VaultAddItem
0x18001c548  mov     r14d, eax
0x18001c54b  test    eax, eax
0x18001c54d  jnz     short $Cleanup_6
0x18001c54f  mov     hVault, [rsp+130h+pItem]
0x18001c554  call    cs:__imp_VaultFree
0x18001c55a  mov     [rsp+130h+pItem], r13
0x18001c55f  inc     esi
0x18001c561  cmp     esi, [rsp+130h+nItems]
0x18001c565  jb      loc_18001C3D1
0x18001c56b  mov     hVault, [rsp+130h+pItem]
0x18001c570  call    cs:__imp_VaultFree
0x18001c576  mov     hVault, [rsp+130h+pItems]
0x18001c57b  call    cs:__imp_VaultFree
0x18001c581  mov     eax, r14d
0x18001c584  mov     hVault, [rbp+57h+var_40]
0x18001c588  xor     hVault, rsp; StackCookie
0x18001c58b  call    __security_check_cookie
0x18001c590  mov     rbx, [rsp+130h+arg_10]
0x18001c598  add     rsp, 100h
0x18001c59f  pop     r15
0x18001c5a1  pop     r14
0x18001c5a3  pop     r13
0x18001c5a5  pop     r12
0x18001c5a7  pop     rdi
0x18001c5a8  pop     rsi
0x18001c5a9  pop     rbp
0x18001c5aa  retn
```
