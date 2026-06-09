# SettingsCopier::LockedDesktopCopy(void)

- ea: `0x14001271c`
- end: `0x1400127f1`
- name: `?LockedDesktopCopy@SettingsCopier@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(SettingsCopier *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000b250`

## callees

- `0x140006a78`
- `0x140011c60`
- `0x14001271c`
- `0x1400127f8`
- `0x140012a48`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140012793`
- `ADVAPI32!RegCloseKey` at `0x1400127a3`
- `ADVAPI32!RegCloseKey` at `0x1400127d7`
- `ADVAPI32!RegCloseKey` at `0x1400127e7`
- `ADVAPI32!RegCloseKey` at `0x140012793`
- `ADVAPI32!RegCloseKey` at `0x1400127a3`
- `ADVAPI32!RegCloseKey` at `0x1400127d7`
- `ADVAPI32!RegCloseKey` at `0x1400127e7`

## pseudocode

```c
__int64 __fastcall SettingsCopier::LockedDesktopCopy(SettingsCopier *this)
{
  SettingsCopier *v2; // rcx
  HKEY v3; // rcx
  int v5; // eax
  HKEY v6[3]; // [rsp+20h] [rbp-30h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-18h] BYREF

  if ( IsInteractiveUser() )
    return 2147500037LL;
  memset(v6, 0, sizeof(v6));
  if ( SettingsCopier::OpenSessionKey(v2, (struct ATL::CRegKey *)v6, 0x20019u) < 0 )
  {
LABEL_7:
    if ( v6[0] )
      RegCloseKey(v6[0]);
    return 2147500037LL;
  }
  memset(hKey, 0, sizeof(hKey));
  if ( (int)SettingsCopier::OpenUserConfigKey((struct ATL::CRegKey *)hKey, 0x2001Fu) < 0 )
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
0x14001271c  mov     [rsp-8+arg_0], rbx
0x140012721  push    rbp
0x140012722  mov     rbp, rsp
0x140012725  sub     rsp, 50h
0x140012729  mov     rbx, rcx
0x14001272c  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140012731  test    eax, eax
0x140012733  jnz     short loc_1400127A9
0x140012735  mov     [rbp+var_30], 0
0x14001273d  mov     [rbp+var_28], 0
0x140012745  mov     [rbp+var_20], 0
0x14001274d  mov     r8d, 20019h; unsigned int
0x140012753  lea     rdx, [rbp+var_30]; struct ATL::CRegKey *
0x140012757  call    ?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)
0x14001275c  test    eax, eax
0x14001275e  js      short loc_14001279A
0x140012760  mov     [rbp+hKey], 0
0x140012768  mov     [rbp+var_10], 0
0x140012770  mov     [rbp+var_8], 0
0x140012778  mov     edx, 2001Fh; unsigned int
0x14001277d  lea     rcx, [rbp+hKey]; this
0x140012781  call    ?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)
0x140012786  test    eax, eax
0x140012788  jns     short loc_1400127B9
0x14001278a  mov     rcx, [rbp+hKey]; hKey
0x14001278e  test    rcx, rcx
0x140012791  jz      short loc_14001279A
0x140012793  call    cs:__imp_RegCloseKey
0x140012799  nop
0x14001279a  mov     rcx, [rbp+var_30]; hKey
0x14001279e  test    rcx, rcx
0x1400127a1  jz      short loc_1400127A9
0x1400127a3  call    cs:__imp_RegCloseKey
0x1400127a9  mov     eax, 80004005h
0x1400127ae  mov     rbx, [rsp+50h+arg_0]
0x1400127b3  add     rsp, 50h
0x1400127b7  pop     rbp
0x1400127b8  retn
0x1400127b9  lea     r8, [rbp+hKey]; struct ATL::CRegKey *
0x1400127bd  lea     rdx, [rbp+var_30]; struct ATL::CRegKey *
0x1400127c1  mov     rcx, rbx; this
0x1400127c4  call    ?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z; SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)
0x1400127c9  nop
0x1400127ca  mov     rcx, [rbp+hKey]; hKey
0x1400127ce  test    eax, eax
0x1400127d0  js      short loc_14001278E
0x1400127d2  test    rcx, rcx
0x1400127d5  jz      short loc_1400127DE
0x1400127d7  call    cs:__imp_RegCloseKey
0x1400127dd  nop
0x1400127de  mov     rcx, [rbp+var_30]; hKey
0x1400127e2  test    rcx, rcx
0x1400127e5  jz      short loc_1400127ED
0x1400127e7  call    cs:__imp_RegCloseKey
0x1400127ed  xor     eax, eax
0x1400127ef  jmp     short loc_1400127AE
```
