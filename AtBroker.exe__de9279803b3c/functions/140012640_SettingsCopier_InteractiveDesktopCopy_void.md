# SettingsCopier::InteractiveDesktopCopy(void)

- ea: `0x140012640`
- end: `0x140012715`
- name: `?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(SettingsCopier *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400048b8`
- `0x14000b250`
- `0x140010244`

## callees

- `0x140006a78`
- `0x140011c60`
- `0x140012640`
- `0x1400127f8`
- `0x140012a48`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400126b7`
- `ADVAPI32!RegCloseKey` at `0x1400126c7`
- `ADVAPI32!RegCloseKey` at `0x1400126fb`
- `ADVAPI32!RegCloseKey` at `0x14001270b`
- `ADVAPI32!RegCloseKey` at `0x1400126b7`
- `ADVAPI32!RegCloseKey` at `0x1400126c7`
- `ADVAPI32!RegCloseKey` at `0x1400126fb`
- `ADVAPI32!RegCloseKey` at `0x14001270b`

## pseudocode

```c
__int64 __fastcall SettingsCopier::InteractiveDesktopCopy(SettingsCopier *this)
{
  SettingsCopier *v2; // rcx
  HKEY v3; // rcx
  int v5; // eax
  HKEY v6[3]; // [rsp+20h] [rbp-30h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-18h] BYREF

  if ( !IsInteractiveUser() )
    return 2147500037LL;
  memset(v6, 0, sizeof(v6));
  if ( (int)SettingsCopier::OpenUserConfigKey((struct ATL::CRegKey *)v6, 0x20019u) < 0 )
  {
LABEL_7:
    if ( v6[0] )
      RegCloseKey(v6[0]);
    return 2147500037LL;
  }
  memset(hKey, 0, sizeof(hKey));
  if ( SettingsCopier::OpenSessionKey(v2, (struct ATL::CRegKey *)hKey, 0x2001Fu) < 0 )
  {
    v3 = hKey[0];
    goto LABEL_5;
  }
  v5 = SettingsCopier::CopyATSettings(this, (struct ATL::CRegKey *)v6, (struct ATL::CRegKey *)hKey);
  v3 = hKey[0];
  if ( v5 < 0 )
  {
LABEL_5:
    if ( v3 )
      RegCloseKey(v3);
    goto LABEL_7;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v6[0] )
    RegCloseKey(v6[0]);
  return 0;
}

```

## disassembly

```asm
0x140012640  mov     [rsp-8+arg_0], rbx
0x140012645  push    rbp
0x140012646  mov     rbp, rsp
0x140012649  sub     rsp, 50h
0x14001264d  mov     rbx, rcx
0x140012650  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140012655  test    eax, eax
0x140012657  jz      short loc_1400126CD
0x140012659  mov     [rbp+var_30], 0
0x140012661  mov     [rbp+var_28], 0
0x140012669  mov     [rbp+var_20], 0
0x140012671  mov     edx, 20019h; unsigned int
0x140012676  lea     rcx, [rbp+var_30]; this
0x14001267a  call    ?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)
0x14001267f  test    eax, eax
0x140012681  js      short loc_1400126BE
0x140012683  mov     [rbp+hKey], 0
0x14001268b  mov     [rbp+var_10], 0
0x140012693  mov     [rbp+var_8], 0
0x14001269b  mov     r8d, 2001Fh; unsigned int
0x1400126a1  lea     rdx, [rbp+hKey]; struct ATL::CRegKey *
0x1400126a5  call    ?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)
0x1400126aa  test    eax, eax
0x1400126ac  jns     short loc_1400126DD
0x1400126ae  mov     rcx, [rbp+hKey]; hKey
0x1400126b2  test    rcx, rcx
0x1400126b5  jz      short loc_1400126BE
0x1400126b7  call    cs:__imp_RegCloseKey
0x1400126bd  nop
0x1400126be  mov     rcx, [rbp+var_30]; hKey
0x1400126c2  test    rcx, rcx
0x1400126c5  jz      short loc_1400126CD
0x1400126c7  call    cs:__imp_RegCloseKey
0x1400126cd  mov     eax, 80004005h
0x1400126d2  mov     rbx, [rsp+50h+arg_0]
0x1400126d7  add     rsp, 50h
0x1400126db  pop     rbp
0x1400126dc  retn
0x1400126dd  lea     r8, [rbp+hKey]; struct ATL::CRegKey *
0x1400126e1  lea     rdx, [rbp+var_30]; struct ATL::CRegKey *
0x1400126e5  mov     rcx, rbx; this
0x1400126e8  call    ?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z; SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)
0x1400126ed  nop
0x1400126ee  mov     rcx, [rbp+hKey]; hKey
0x1400126f2  test    eax, eax
0x1400126f4  js      short loc_1400126B2
0x1400126f6  test    rcx, rcx
0x1400126f9  jz      short loc_140012702
0x1400126fb  call    cs:__imp_RegCloseKey
0x140012701  nop
0x140012702  mov     rcx, [rbp+var_30]; hKey
0x140012706  test    rcx, rcx
0x140012709  jz      short loc_140012711
0x14001270b  call    cs:__imp_RegCloseKey
0x140012711  xor     eax, eax
0x140012713  jmp     short loc_1400126D2
```
