# CFormCreds::FConsentNeeded(ushort const *,ushort const *,ushort const *,int *,int *)

- ea: `0x18001c5b4`
- end: `0x18001c79e`
- name: `?FConsentNeeded@CFormCreds@@QEAAJPEBG00PEAH1@Z`
- size: `490`
- prototype: `__int64 __fastcall(CFormCreds *this, const wchar_t *lpcwszUrl, const wchar_t *lpcwszUserName, const wchar_t *lpcwszPassword, int *pfShowConsent, int *pfSavePreferredUserAccount)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013e10`

## callees

- `0x18001c5b4`
- `0x18001d674`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18001c705`
- `ntdll!_wcsicmp` at `0x18001c705`
- `VAULTCLI!VaultGetItem` at `0x18001c6d3`
- `VAULTCLI!VaultGetItem` at `0x18001c6d3`
- `VAULTCLI!VaultCloseVault` at `0x18001c749`
- `VAULTCLI!VaultCloseVault` at `0x18001c749`
- `VAULTCLI!VaultFree` at `0x18001c739`
- `VAULTCLI!VaultFree` at `0x18001c739`
- `VAULTCLI!VaultOpenVault` at `0x18001c630`
- `VAULTCLI!VaultOpenVault` at `0x18001c630`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CFormCreds::FConsentNeeded(
        CFormCreds *this,
        const wchar_t *lpcwszUrl,
        const wchar_t *lpcwszUserName,
        const wchar_t *lpcwszPassword,
        int *pfShowConsent,
        int *pfSavePreferredUserAccount)
{
  signed int Item; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  int v12; // edi
  const wchar_t *String; // rdx
  _VAULT_ITEM_ELEMENT *pAuthenticatorElement; // rcx
  int v15; // eax
  unsigned int *v16; // rsi
  _VAULT_ITEM *v17; // rcx
  const _GUID *v18; // r8
  _BYTE PackageSidElement_8[96]; // [rsp+48h] [rbp-39h] OVERLAPPED BYREF
  void *hVault; // [rsp+D8h] [rbp+57h] BYREF
  _VAULT_ITEM *pItem; // [rsp+E0h] [rbp+5Fh] BYREF

  hVault = 0;
  pItem = 0;
  memset(PackageSidElement_8, 0, sizeof(PackageSidElement_8));
  if ( lpcwszUrl && lpcwszUserName && lpcwszPassword )
  {
    Item = VaultOpenVault(&Vault_DefaultVault_ID, 0, &hVault);
    v10 = Item;
    v11 = Item <= 0;
    if ( Item )
      goto LABEL_5;
    *(_QWORD *)&PackageSidElement_8[16] = &gWABPackageSidBuffer;
    *(_QWORD *)&PackageSidElement_8[64] = 1;
    v12 = 1;
    *(_QWORD *)&PackageSidElement_8[72] = 7;
    *(_QWORD *)&PackageSidElement_8[88] = 0;
    *(_QWORD *)&PackageSidElement_8[80] = lpcwszUrl;
    *(_QWORD *)&PackageSidElement_8[32] = 2;
    *(_QWORD *)&PackageSidElement_8[40] = 7;
    *(_QWORD *)&PackageSidElement_8[56] = 0;
    *(_QWORD *)&PackageSidElement_8[48] = lpcwszUserName;
    *(_QWORD *)PackageSidElement_8 = 5;
    *(_QWORD *)&PackageSidElement_8[8] = 12;
    *(_QWORD *)&PackageSidElement_8[24] = 0;
    Item = VaultGetItem(
             hVault,
             &Vault_Schema_WebPassword,
             &PackageSidElement_8[64],
             &PackageSidElement_8[32],
             PackageSidElement_8,
             0,
             0,
             &pItem);
    v10 = Item;
    if ( Item == 1168 )
      goto LABEL_12;
    v11 = Item <= 0;
    if ( Item )
    {
LABEL_5:
      if ( !v11 )
        v10 = (unsigned __int16)Item | 0x80070000;
      goto LABEL_16;
    }
    String = &source;
    pAuthenticatorElement = pItem->pAuthenticatorElement;
    if ( pAuthenticatorElement->ItemValue.String )
      String = pAuthenticatorElement->ItemValue.String;
    if ( _wcsicmp(lpcwszPassword, String) )
    {
LABEL_12:
      v15 = 1;
      v12 = 0;
    }
    else
    {
      v15 = 0;
    }
    v10 = 0;
    goto $Cleanup_7;
  }
  v10 = -2147024809;
LABEL_16:
  v15 = 0;
  v12 = 0;
$Cleanup_7:
  v16 = (unsigned int *)pfShowConsent;
  v17 = pItem;
  *pfShowConsent = v15;
  *pfSavePreferredUserAccount = v12;
  VaultFree(v17);
  if ( hVault )
    VaultCloseVault(&hVault);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_DD(WPP_GLOBAL_Control[1].Control.Logger, *v16, v18, v10, *v16);
  }
  return v10;
}

```

## disassembly

```asm
0x18001c5b4  mov     rax, rsp
0x18001c5b7  mov     [rax+18h], rbx
0x18001c5bb  mov     [rax+20h], rsi
0x18001c5bf  mov     [rax+8], rcx
0x18001c5c3  push    rbp
0x18001c5c4  push    rdi
0x18001c5c5  push    r12
0x18001c5c7  push    r14
0x18001c5c9  push    r15
0x18001c5cb  lea     rbp, [rax-4Fh]
0x18001c5cf  sub     rsp, 0A0h
0x18001c5d6  xorps   xmm0, xmm0
0x18001c5d9  xor     r12d, r12d
0x18001c5dc  mov     [rbp+47h+hVault], r12
0x18001c5e0  xorps   xmm1, xmm1
0x18001c5e3  mov     [rbp+47h+pItem], r12
0x18001c5e7  mov     r14, lpcwszPassword
0x18001c5ea  mov     rsi, lpcwszUserName
0x18001c5ed  mov     r15, lpcwszUrl
0x18001c5f0  movups  xmmword ptr [rbp+47h+ResourceElement.ItemValue.Type], xmm0
0x18001c5f4  movups  xmmword ptr [rbp+47h+ResourceElement.ItemValue.___u1+8], xmm0
0x18001c5f8  movups  xmmword ptr [rbp+47h+IdentityElement.ItemValue.Type], xmm1
0x18001c5fc  movups  xmmword ptr [rbp+47h+IdentityElement.ItemValue.___u1+8], xmm1
0x18001c600  movups  xmmword ptr [rbp+47h+PackageSidElement.ItemValue.Type], xmm0
0x18001c604  movups  xmmword ptr [rbp+47h+PackageSidElement.ItemValue.___u1+8], xmm0
0x18001c608  test    lpcwszUrl, lpcwszUrl
0x18001c60b  jz      loc_18001C71E
0x18001c611  test    lpcwszUserName, lpcwszUserName
0x18001c614  jz      loc_18001C71E
0x18001c61a  test    lpcwszPassword, lpcwszPassword
0x18001c61d  jz      loc_18001C71E
0x18001c623  lea     lpcwszUserName, [rbp+47h+hVault]
0x18001c627  xor     edx, edx
0x18001c629  lea     rcx, Vault_DefaultVault_ID
0x18001c630  call    cs:__imp_VaultOpenVault
0x18001c636  mov     ebx, eax
0x18001c638  test    eax, eax
0x18001c63a  jz      short loc_18001C650
0x18001c63c  jle     loc_18001C723
0x18001c642  movzx   ebx, ax
0x18001c645  or      ebx, 80070000h
0x18001c64b  jmp     loc_18001C723
0x18001c650  mov     rcx, [rbp+47h+hVault]
0x18001c654  lea     rax, ?gWABPackageSidBuffer@@3U_SID_BUFFER@@A; _SID_BUFFER gWABPackageSidBuffer
0x18001c65b  mov     qword ptr [rbp+47h+PackageSidElement.ItemValue.___u1+8], rax
0x18001c65f  lea     lpcwszPassword, [rbp+47h+IdentityElement.ItemValue]
0x18001c663  lea     rax, [rbp+47h+pItem]
0x18001c667  mov     qword ptr [rbp+47h+ResourceElement.ItemValue.Type], 1
0x18001c66f  mov     qword ptr [rsp+0C0h+PackageSidElement.SchemaElementId], rax
0x18001c674  lea     lpcwszUserName, [rbp+47h+ResourceElement.ItemValue]
0x18001c678  mov     dword ptr [rsp+0C0h+var_90], r12d
0x18001c67d  lea     rax, [rbp+47h+PackageSidElement.ItemValue]
0x18001c681  mov     qword ptr [rsp+0C0h+var_98], r12
0x18001c686  lea     lpcwszUrl, Vault_Schema_WebPassword
0x18001c68d  mov     qword ptr [rsp+0C0h+id], rax
0x18001c692  mov     edi, 1
0x18001c697  mov     qword ptr [rbp+47h+ResourceElement.ItemValue.___u1], 7
0x18001c69f  mov     [rbp+47h+var_28], r12
0x18001c6a3  mov     qword ptr [rbp+47h+ResourceElement.ItemValue.___u1+8], r15
0x18001c6a7  mov     qword ptr [rbp+47h+IdentityElement.ItemValue.Type], 2
0x18001c6af  mov     qword ptr [rbp+47h+IdentityElement.ItemValue.___u1], 7
0x18001c6b7  mov     qword ptr [rbp+47h+ResourceElement.SchemaElementId], r12
0x18001c6bb  mov     qword ptr [rbp+47h+IdentityElement.ItemValue.___u1+8], rsi
0x18001c6bf  mov     qword ptr [rbp+47h+PackageSidElement.ItemValue.Type], 5
0x18001c6c7  mov     qword ptr [rbp+47h+PackageSidElement.ItemValue.___u1], 0Ch
0x18001c6cf  mov     qword ptr [rbp+47h+IdentityElement.SchemaElementId], r12
0x18001c6d3  call    cs:__imp_VaultGetItem
0x18001c6d9  mov     ebx, eax
0x18001c6db  cmp     eax, 490h
0x18001c6e0  jz      short loc_18001C70F
0x18001c6e2  test    eax, eax
0x18001c6e4  jnz     loc_18001C63C
0x18001c6ea  mov     rax, [rbp+47h+pItem]
0x18001c6ee  lea     lpcwszUrl, source
0x18001c6f5  mov     rcx, [rax+28h]
0x18001c6f9  cmp     [rcx+10h], r12
0x18001c6fd  cmovnz  lpcwszUrl, [rcx+10h]; String2
0x18001c702  mov     rcx, r14; String1
0x18001c705  call    cs:__imp__wcsicmp
0x18001c70b  test    eax, eax
0x18001c70d  jz      short loc_18001C716
0x18001c70f  mov     eax, edi
0x18001c711  mov     edi, r12d
0x18001c714  jmp     short loc_18001C719
0x18001c716  mov     eax, r12d
0x18001c719  mov     ebx, r12d
0x18001c71c  jmp     short $Cleanup_7
0x18001c71e  mov     ebx, 80070057h
0x18001c723  mov     eax, r12d
0x18001c726  mov     edi, r12d
0x18001c729  mov     rsi, [rbp+47h+arg_20]
0x18001c72d  mov     rcx, [rbp+47h+pItem]
0x18001c731  mov     [rsi], eax
0x18001c733  mov     rax, [rbp+47h+arg_28]
0x18001c737  mov     [rax], edi
0x18001c739  call    cs:__imp_VaultFree
0x18001c73f  cmp     [rbp+47h+hVault], r12
0x18001c743  jz      short loc_18001C74F
0x18001c745  lea     rcx, [rbp+47h+hVault]
0x18001c749  call    cs:__imp_VaultCloseVault
0x18001c74f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c756  lea     rax, WPP_GLOBAL_Control
0x18001c75d  cmp     rcx, rax
0x18001c760  jz      short loc_18001C780
0x18001c762  test    byte ptr [rcx+44h], 8
0x18001c766  jz      short loc_18001C780
0x18001c768  cmp     byte ptr [rcx+41h], 5
0x18001c76c  jb      short loc_18001C780
0x18001c76e  mov     edx, [rsi]; _a1
0x18001c770  mov     r9d, ebx; Logger
0x18001c773  mov     rcx, [rcx+38h]; Logger
0x18001c777  mov     [rsp+0C0h+id], edx; id
0x18001c77b  call    WPP_SF_DD
0x18001c780  lea     r11, [rsp+0C0h+var_20]
0x18001c788  mov     eax, ebx
0x18001c78a  mov     rbx, [r11+40h]
0x18001c78e  mov     rsi, [r11+48h]
0x18001c792  mov     rsp, r11
0x18001c795  pop     r15
0x18001c797  pop     r14
0x18001c799  pop     r12
0x18001c79b  pop     rdi
0x18001c79c  pop     rbp
0x18001c79d  retn
```
