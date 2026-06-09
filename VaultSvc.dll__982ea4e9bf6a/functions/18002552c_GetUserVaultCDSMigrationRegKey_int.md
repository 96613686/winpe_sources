# GetUserVaultCDSMigrationRegKey(int *)

- ea: `0x18002552c`
- end: `0x1800256a3`
- name: `?GetUserVaultCDSMigrationRegKey@@YAKPEAH@Z`
- size: `375`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001cecc`

## callees

- `0x180003140`
- `0x18002552c`
- `0x18003a580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025655`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800255f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800255f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025566`

## pseudocode

```c
__int64 __fastcall GetUserVaultCDSMigrationRegKey(int *a1)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // r8
  WCHAR *v5; // r9
  wchar_t v6; // dx
  WCHAR *v7; // rcx
  unsigned int v8; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  LSTATUS (__stdcall *v13)(HKEY); // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v13 = RegCloseKey;
  hKey = 0;
  v15 = 0;
  *a1 = 0;
  v2 = 2147483646;
  v3 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Vault\\";
  v4 = 260;
  v5 = SubKey;
  do
  {
    if ( !v2 )
      break;
    v6 = *v3;
    if ( !*v3 )
      break;
    ++v3;
    *v5++ = v6;
    --v2;
    --v4;
  }
  while ( v4 );
  v7 = v5 - 1;
  if ( v4 )
    v7 = v5;
  *v7 = 0;
  if ( !v4 )
  {
    v8 = v4 == 0 ? 0x7A : 0;
    goto LABEL_9;
  }
  v8 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &hKey);
  if ( v8 )
  {
LABEL_9:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
    return v8;
  }
  v8 = RegQueryValueExW(hKey, L"VaultCDSMigration", 0, &Type, Data, &cbData);
  if ( !v8 && Type == 4 )
    *a1 = *(_DWORD *)Data == 1;
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
  return v8;
}

```

## disassembly

```asm
0x18002552c  push    rbp
0x18002552e  push    rbx
0x18002552f  push    rsi
0x180025530  push    rdi
0x180025531  lea     rbp, [rsp-188h]
0x180025539  sub     rsp, 288h
0x180025540  mov     rax, cs:__security_cookie
0x180025547  xor     rax, rsp
0x18002554a  mov     [rbp+1A0h+var_30], rax
0x180025551  mov     rdi, rcx
0x180025554  xor     esi, esi
0x180025556  mov     dword ptr [rsp+2A0h+Data], esi
0x18002555a  mov     [rsp+2A0h+cbData], 4
0x180025562  mov     [rsp+2A0h+Type], esi
0x180025566  mov     rax, cs:__imp_RegCloseKey
0x18002556d  mov     [rsp+2A0h+var_260], rax
0x180025572  mov     [rsp+2A0h+hKey], rsi
0x180025577  mov     [rsp+2A0h+var_250], esi
0x18002557b  mov     [rcx], esi
0x18002557d  mov     eax, 7FFFFFFEh
0x180025582  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180025589  mov     r8d, 104h
0x18002558f  lea     r9, [rsp+2A0h+SubKey]
0x180025594  test    rax, rax
0x180025597  jz      short loc_1800255B6
0x180025599  movzx   edx, word ptr [rcx]
0x18002559c  test    dx, dx
0x18002559f  jz      short loc_1800255B6
0x1800255a1  add     rcx, 2
0x1800255a5  mov     [r9], dx
0x1800255a9  add     r9, 2
0x1800255ad  dec     rax
0x1800255b0  sub     r8, 1
0x1800255b4  jnz     short loc_180025594
0x1800255b6  mov     rax, r8
0x1800255b9  neg     rax
0x1800255bc  sbb     edx, edx
0x1800255be  not     edx
0x1800255c0  and     edx, 8007007Ah
0x1800255c6  lea     rcx, [r9-2]
0x1800255ca  test    r8, r8
0x1800255cd  cmovnz  rcx, r9
0x1800255d1  mov     [rcx], si
0x1800255d4  jz      loc_180025681
0x1800255da  lea     rax, [rsp+2A0h+hKey]
0x1800255df  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800255e4  mov     r9d, 20019h; samDesired
0x1800255ea  xor     r8d, r8d; ulOptions
0x1800255ed  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800255f2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800255f9  call    cs:__imp_RegOpenKeyExW
0x1800255ff  mov     ebx, eax
0x180025601  test    eax, eax
0x180025603  jz      short loc_18002562D
0x180025605  lea     rcx, [rsp+2A0h+var_260]
0x18002560a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002560f  nop
0x180025610  mov     eax, ebx
0x180025612  mov     rcx, [rbp+1A0h+var_30]
0x180025619  xor     rcx, rsp; StackCookie
0x18002561c  call    __security_check_cookie
0x180025621  add     rsp, 288h
0x180025628  pop     rdi
0x180025629  pop     rsi
0x18002562a  pop     rbx
0x18002562b  pop     rbp
0x18002562c  retn
0x18002562d  lea     rax, [rsp+2A0h+cbData]
0x180025632  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180025637  lea     rax, [rsp+2A0h+Data]
0x18002563c  mov     [rsp+2A0h+phkResult], rax; lpData
0x180025641  lea     r9, [rsp+2A0h+Type]; lpType
0x180025646  xor     r8d, r8d; lpReserved
0x180025649  lea     rdx, ValueName; "VaultCDSMigration"
0x180025650  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025655  call    cs:__imp_RegQueryValueExW
0x18002565b  mov     ebx, eax
0x18002565d  test    eax, eax
0x18002565f  jnz     short loc_180025674
0x180025661  cmp     [rsp+2A0h+Type], 4
0x180025666  jnz     short loc_180025674
0x180025668  mov     ecx, esi
0x18002566a  cmp     dword ptr [rsp+2A0h+Data], 1
0x18002566f  setz    cl
0x180025672  mov     [rdi], ecx
0x180025674  lea     rcx, [rsp+2A0h+var_260]
0x180025679  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002567e  nop
0x18002567f  jmp     short loc_180025610
0x180025681  mov     eax, edx
0x180025683  and     eax, 1FFF0000h
0x180025688  movzx   ebx, dx
0x18002568b  cmp     eax, 70000h
0x180025690  cmovnz  ebx, edx
0x180025693  lea     rcx, [rsp+2A0h+var_260]
0x180025698  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002569d  nop
0x18002569e  jmp     loc_180025610
```
