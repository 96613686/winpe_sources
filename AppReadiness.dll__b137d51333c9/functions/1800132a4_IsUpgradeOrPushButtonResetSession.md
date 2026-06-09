# IsUpgradeOrPushButtonResetSession

- ea: `0x1800132a4`
- end: `0x180013384`
- name: `IsUpgradeOrPushButtonResetSession`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d1c4`

## callees

- `0x180012630`
- `0x1800132a4`
- `0x1800337b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001335f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001336e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001335f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001336e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013333`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013333`

## string_xrefs

- `0x180013319`: `UpgradeOrPBRAttempts`

## pseudocode

```c
__int64 __fastcall IsUpgradeOrPushButtonResetSession(void *a1)
{
  unsigned int v1; // ebx
  LSTATUS ValueW; // eax
  bool v3; // sf
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-18h] BYREF
  int pvData; // [rsp+88h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+20h] BYREF

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v1 = 0;
  if ( (int)SHGetUserSid(a1, (LPWSTR *)pv) >= 0 )
  {
    memset(lpSubKey, 0, sizeof(lpSubKey));
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                lpSubKey,
                L"%ls\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer",
                pv[0]) >= 0 )
    {
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(HKEY_USERS, lpSubKey[0], L"UpgradeOrPBRAttempts", 0x10u, 0, &pvData, &pcbData);
      v3 = ValueW < 0;
      if ( ValueW > 0 )
        v3 = 1;
      if ( !v3 && pvData )
        v1 = 1;
    }
    if ( lpSubKey[0] )
      CoTaskMemFree((LPVOID)lpSubKey[0]);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return v1;
}

```

## disassembly

```asm
0x1800132a4  mov     [rsp-8+arg_0], rbx
0x1800132a9  push    rbp
0x1800132aa  mov     rbp, rsp
0x1800132ad  sub     rsp, 70h
0x1800132b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800132b5  mov     [rbp+pv], 0
0x1800132bd  lea     rdx, [rbp+pv]; StringSid
0x1800132c1  mov     [rbp+var_10], rax
0x1800132c5  mov     [rbp+var_8], rax
0x1800132c9  xor     ebx, ebx
0x1800132cb  call    SHGetUserSid
0x1800132d0  test    eax, eax
0x1800132d2  js      loc_180013365
0x1800132d8  mov     r8, [rbp+pv]
0x1800132dc  lea     rdx, aLsSoftwareMicr; "%ls\\SOFTWARE\\Microsoft\\Windows\\Curr"...
0x1800132e3  lea     rcx, [rbp+lpSubKey]
0x1800132e7  mov     [rbp+lpSubKey], rbx
0x1800132eb  mov     [rbp+var_28], rbx
0x1800132ef  mov     [rbp+var_20], rbx
0x1800132f3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800132f8  test    eax, eax
0x1800132fa  js      short loc_180013354
0x1800132fc  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180013300  lea     rax, [rbp+arg_10]
0x180013304  mov     [rsp+70h+pcbData], rax; pcbData
0x180013309  lea     r9d, [rbx+10h]; dwFlags
0x18001330d  lea     rax, [rbp+arg_8]
0x180013311  mov     [rbp+arg_8], ebx
0x180013314  mov     [rsp+70h+pvData], rax; pvData
0x180013319  lea     r8, pszValue; "UpgradeOrPBRAttempts"
0x180013320  mov     rcx, 0FFFFFFFF80000003h; hkey
0x180013327  mov     [rsp+70h+pdwType], rbx; pdwType
0x18001332c  mov     [rbp+arg_10], 4
0x180013333  call    cs:__imp_RegGetValueW
0x180013339  test    eax, eax
0x18001333b  jle     short loc_180013347
0x18001333d  movzx   eax, ax
0x180013340  or      eax, 80070000h
0x180013345  test    eax, eax
0x180013347  js      short loc_180013354
0x180013349  cmp     [rbp+arg_8], ebx
0x18001334c  mov     eax, 1
0x180013351  cmova   ebx, eax
0x180013354  cmp     [rbp+lpSubKey], 0
0x180013359  jz      short loc_180013365
0x18001335b  mov     rcx, [rbp+lpSubKey]; pv
0x18001335f  call    cs:__imp_CoTaskMemFree
0x180013365  mov     rcx, [rbp+pv]; pv
0x180013369  test    rcx, rcx
0x18001336c  jz      short loc_180013374
0x18001336e  call    cs:__imp_CoTaskMemFree
0x180013374  mov     eax, ebx
0x180013376  mov     rbx, [rsp+70h+arg_0]
0x18001337e  add     rsp, 70h
0x180013382  pop     rbp
0x180013383  retn
```
