# sub_1800BDFA0

- ea: `0x1800bdfa0`
- end: `0x1800be061`
- name: `sub_1800BDFA0`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bca60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bdffc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bdffc`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800be046`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultRemoveItem` at `0x1800be046`

## pseudocode

```c
__int64 __fastcall sub_1800BDFA0(__int64 *a1, void *a2)
{
  DWORD LengthSid; // eax
  __int64 v5; // rcx
  __int128 v7; // [rsp+60h] [rbp+17h] BYREF
  __int128 v8; // [rsp+70h] [rbp+27h]
  __int64 v9; // [rsp+80h] [rbp+37h] BYREF
  int v10; // [rsp+88h] [rbp+3Fh]
  int v11; // [rsp+8Ch] [rbp+43h]
  const wchar_t *v12; // [rsp+90h] [rbp+47h]
  __int64 v13; // [rsp+98h] [rbp+4Fh]

  v9 = 1;
  v10 = 7;
  v11 = 0;
  v12 = L"WinBio CredProv Resource";
  v7 = 0;
  v13 = 0;
  v8 = 0;
  LengthSid = GetLengthSid(a2);
  v5 = *a1;
  *(_QWORD *)&v8 = LengthSid;
  LODWORD(v7) = 2;
  *((_QWORD *)&v7 + 1) = 8;
  *((_QWORD *)&v8 + 1) = a2;
  return VaultRemoveItem(v5, &xmmword_18010FC18, &v9, &v7, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x1800bdfa0  mov     [rsp-8+arg_0], rbx
0x1800bdfa5  mov     [rsp-8+arg_8], rdi
0x1800bdfaa  push    rbp
0x1800bdfab  lea     rbp, [rsp-57h]
0x1800bdfb0  sub     rsp, 0A0h
0x1800bdfb7  mov     rdi, rcx
0x1800bdfba  mov     [rbp+57h+var_20], 1
0x1800bdfc2  xorps   xmm0, xmm0
0x1800bdfc5  mov     [rbp+57h+var_18], 7
0x1800bdfcc  xorps   xmm1, xmm1
0x1800bdfcf  xor     eax, eax
0x1800bdfd1  movups  [rbp+57h+var_58], xmm1
0x1800bdfd5  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x1800bdfd8  mov     rbx, rdx
0x1800bdfdb  mov     [rbp+57h+var_14], ecx
0x1800bdfde  lea     rcx, aWinbioCredprov; "WinBio CredProv Resource"
0x1800bdfe5  mov     [rbp+57h+var_10], rcx
0x1800bdfe9  mov     rcx, rdx; pSid
0x1800bdfec  movups  [rbp+57h+var_40], xmm0
0x1800bdff0  mov     [rbp+57h+var_8], rax
0x1800bdff4  movups  [rbp+57h+var_30], xmm0
0x1800bdff8  movups  [rbp+57h+var_70], xmm0
0x1800bdffc  call    cs:GetLengthSid
0x1800be002  mov     ecx, dword ptr [rbp+57h+var_70+4]
0x1800be005  lea     r9, [rbp+57h+var_40]
0x1800be009  mov     dword ptr [rbp+57h+var_40+0Ch], ecx
0x1800be00c  lea     r8, [rbp+57h+var_20]
0x1800be010  mov     rcx, [rdi]
0x1800be013  lea     rdx, xmmword_18010FC18
0x1800be01a  mov     dword ptr [rbp+57h+var_30], eax
0x1800be01d  mov     eax, dword ptr [rbp+57h+var_70+0Ch]
0x1800be020  mov     [rsp+0A0h+var_78], 0
0x1800be028  mov     dword ptr [rbp+57h+var_30+4], eax
0x1800be02b  mov     dword ptr [rbp+57h+var_40], 2
0x1800be032  mov     dword ptr [rbp+57h+var_40+8], 8
0x1800be039  mov     qword ptr [rbp+57h+var_30+8], rbx
0x1800be03d  mov     [rsp+0A0h+var_80], 0
0x1800be046  call    cs:VaultRemoveItem
0x1800be04c  lea     r11, [rsp+0A0h+var_s0]
0x1800be054  mov     rbx, [r11+10h]
0x1800be058  mov     rdi, [r11+18h]
0x1800be05c  mov     rsp, r11
0x1800be05f  pop     rbp
0x1800be060  retn
```
