# WalletEncrypter::InitializeWalletCredVaultSchema(void *)

- ea: `0x18001bee0`
- end: `0x18001c040`
- name: `?InitializeWalletCredVaultSchema@WalletEncrypter@@CAJPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001be00`

## callees

- `0x18001b394`
- `0x18001bee0`
- `0x180043090`

## import_xrefs

- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x18001bff8`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCreateItemType` at `0x18001bff8`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x18001bf43`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItemType` at `0x18001bf43`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::InitializeWalletCredVaultSchema(void *a1)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  bool v4; // sf
  signed int ItemType; // eax
  bool v6; // sf
  _QWORD v8[2]; // [rsp+28h] [rbp-49h] BYREF
  _OWORD v9[4]; // [rsp+38h] [rbp-39h] BYREF
  __int128 v10; // [rsp+78h] [rbp+7h] BYREF
  __int128 v11; // [rsp+88h] [rbp+17h] BYREF
  __int128 v12; // [rsp+98h] [rbp+27h] BYREF

  v8[0] = 0;
  v10 = 0;
  v2 = 0;
  v11 = 0;
  v12 = 0;
  memset((char *)v9 + 4, 0, 48);
  v3 = ((__int64 (__fastcall *)(void *, __int128 *, _QWORD, _QWORD *))VaultGetItemType)(a1, &xmmword_180050F80, 0, v8);
  if ( v3 )
  {
    if ( v3 == 1168 )
      goto LABEL_7;
    v4 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = v3 < 0;
    }
    if ( !v4 )
    {
LABEL_7:
      HIDWORD(v9[0]) = 649905552;
      LODWORD(v10) = 1;
      *(_QWORD *)&v9[1] = L"Wallet Encryption Schema";
      *((_QWORD *)&v9[1] + 1) = &v10;
      *(_QWORD *)&v9[2] = &v11;
      *((_QWORD *)&v9[2] + 1) = &v12;
      *(_QWORD *)((char *)&v10 + 4) = 7;
      HIDWORD(v10) = 4;
      LODWORD(v11) = 2;
      *(_QWORD *)((char *)&v11 + 4) = 7;
      HIDWORD(v11) = 0;
      LODWORD(v12) = 3;
      *(_QWORD *)((char *)&v12 + 4) = 8;
      HIDWORD(v12) = 0;
      LODWORD(v9[0]) = 834059076;
      *(_QWORD *)((char *)v9 + 4) = 0x82D4C7A2449343A4uLL;
      v9[3] = 0;
      ItemType = VaultCreateItemType(a1, v9, 0);
      v6 = ItemType < 0;
      if ( ItemType > 0 )
      {
        ItemType = (unsigned __int16)ItemType | 0x80070000;
        v6 = ItemType < 0;
      }
      if ( v6 )
        v2 = ItemType;
    }
    else
    {
      v2 = v3;
    }
  }
  tlx::unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&void VaultFree(void *),0>>::~unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&void VaultFree(void *),0>>(v8);
  return v2;
}

```

## disassembly

```asm
0x18001bee0  mov     rax, rsp
0x18001bee3  mov     [rax+10h], rbx
0x18001bee7  mov     [rax+18h], rdi
0x18001beeb  push    rbp
0x18001beec  lea     rbp, [rax-5Fh]
0x18001bef0  sub     rsp, 0C0h
0x18001bef7  movaps  xmmword ptr [rax-18h], xmm6
0x18001befb  mov     rax, cs:__security_cookie
0x18001bf02  xor     rax, rsp
0x18001bf05  mov     [rbp+57h+var_20], rax
0x18001bf09  xorps   xmm6, xmm6
0x18001bf0c  lea     r9, [rbp+57h+var_A0]
0x18001bf10  xorps   xmm0, xmm0
0x18001bf13  lea     rdx, xmmword_180050F80
0x18001bf1a  xorps   xmm1, xmm1
0x18001bf1d  xor     eax, eax
0x18001bf1f  xor     r8d, r8d
0x18001bf22  mov     [rbp+57h+var_A0], rax
0x18001bf26  movups  [rbp+57h+var_50], xmm0
0x18001bf2a  mov     rdi, rcx
0x18001bf2d  xor     ebx, ebx
0x18001bf2f  movups  [rbp+57h+var_40], xmm1
0x18001bf33  movups  [rbp+57h+var_30], xmm0
0x18001bf37  movups  [rbp+57h+var_8C], xmm6
0x18001bf3b  movups  [rbp+57h+var_7C], xmm6
0x18001bf3f  movups  [rbp+57h+var_6C], xmm6
0x18001bf43  call    cs:__imp_VaultGetItemType
0x18001bf49  test    eax, eax
0x18001bf4b  jz      loc_18001C00F
0x18001bf51  cmp     eax, 490h
0x18001bf56  jz      short loc_18001BF6F
0x18001bf58  test    eax, eax
0x18001bf5a  jle     short loc_18001BF66
0x18001bf5c  movzx   eax, ax
0x18001bf5f  or      eax, 80070000h
0x18001bf64  test    eax, eax
0x18001bf66  jns     short loc_18001BF6F
0x18001bf68  mov     ebx, eax
0x18001bf6a  jmp     loc_18001C00F
0x18001bf6f  mov     eax, dword ptr cs:xmmword_180050F80+0Ch
0x18001bf75  lea     rdx, [rbp+57h+var_90]
0x18001bf79  movsd   xmm0, qword ptr cs:xmmword_180050F80+4
0x18001bf81  xor     r8d, r8d
0x18001bf84  mov     dword ptr [rbp+57h+var_8C+8], eax
0x18001bf87  mov     rcx, rdi
0x18001bf8a  lea     rax, ?sc_szWalletEncryptionSchemaName@WalletEncrypter@@1QBGB; "Wallet Encryption Schema"
0x18001bf91  mov     dword ptr [rbp+57h+var_50], 1
0x18001bf98  mov     qword ptr [rbp+57h+var_8C+0Ch], rax
0x18001bf9c  lea     rax, [rbp+57h+var_50]
0x18001bfa0  mov     qword ptr [rbp+57h+var_7C+4], rax
0x18001bfa4  lea     rax, [rbp+57h+var_40]
0x18001bfa8  mov     qword ptr [rbp+57h+var_7C+0Ch], rax
0x18001bfac  lea     rax, [rbp+57h+var_30]
0x18001bfb0  mov     qword ptr [rbp+57h+var_6C+4], rax
0x18001bfb4  mov     qword ptr [rbp+57h+var_50+4], 7
0x18001bfbc  mov     dword ptr [rbp+57h+var_50+0Ch], 4
0x18001bfc3  mov     dword ptr [rbp+57h+var_40], 2
0x18001bfca  mov     qword ptr [rbp+57h+var_40+4], 7
0x18001bfd2  mov     dword ptr [rbp+57h+var_40+0Ch], ebx
0x18001bfd5  mov     dword ptr [rbp+57h+var_30], 3
0x18001bfdc  mov     qword ptr [rbp+57h+var_30+4], 8
0x18001bfe4  mov     dword ptr [rbp+57h+var_30+0Ch], ebx
0x18001bfe7  mov     [rbp+57h+var_90], 31B6BB44h
0x18001bfee  movsd   qword ptr [rbp+57h+var_8C], xmm0
0x18001bff3  movdqu  [rbp+57h+var_6C+0Ch], xmm6
0x18001bff8  call    cs:__imp_VaultCreateItemType
0x18001bffe  test    eax, eax
0x18001c000  jle     short loc_18001C00C
0x18001c002  movzx   eax, ax
0x18001c005  or      eax, 80070000h
0x18001c00a  test    eax, eax
0x18001c00c  cmovs   ebx, eax
0x18001c00f  lea     rcx, [rbp+57h+var_A0]
0x18001c013  call    ??1?$unique_any@U?$handle_traits@PEAU_VAULT_ITEM_SCHEMA@@P6AXPEAX@Z$1?VaultFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&VaultFree(void *),0>>::~unique_any<tlx::handle_traits<_VAULT_ITEM_SCHEMA *,void (*)(void *),&VaultFree(void *),0>>(void)
0x18001c018  mov     eax, ebx
0x18001c01a  mov     rcx, [rbp+57h+var_20]
0x18001c01e  xor     rcx, rsp; StackCookie
0x18001c021  call    __security_check_cookie
0x18001c026  lea     r11, [rsp+0C0h+var_s0]
0x18001c02e  mov     rbx, [r11+18h]
0x18001c032  mov     rdi, [r11+20h]
0x18001c036  movaps  xmm6, xmmword ptr [r11-10h]
0x18001c03b  mov     rsp, r11
0x18001c03e  pop     rbp
0x18001c03f  retn
```
