# CWindowsOldJob::Save(void)

- ea: `0x180013590`
- end: `0x18001375d`
- name: `?Save@CWindowsOldJob@@UEAAXXZ`
- size: `461`
- prototype: `void __fastcall(CWindowsOldJob *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800047a8`
- `0x180004c84`
- `0x180006744`
- `0x180013590`

## import_xrefs

- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x1800136bc`
- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x1800136bc`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18001369e`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18001369e`
- `unbcl!?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x18001361d`
- `unbcl!?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x1800136e5`
- `unbcl!?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x18001361d`
- `unbcl!?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x1800136e5`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800135d7`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180013678`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800135d7`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180013678`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800135ee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180013650`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001368f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800136c7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180013718`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800135ee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180013650`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001368f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800136c7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180013718`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800135c3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001360f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013665`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800136af`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800136d8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800135c3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001360f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013665`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800136af`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800136d8`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x1800135a5`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x1800135a5`

## string_xrefs

- `0x1800135b8`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x180013604`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18001365a`: `Windows.old`
- `0x1800136a4`: `Windows.old`
- `0x1800136cd`: `Windows.old`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CWindowsOldJob::Save(CWindowsOldJob *this)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  UnBCL::RegistryKey *v4; // rbx
  const struct UnBCL::String *v5; // rax
  struct UnBCL::RegistryKey *SubKey; // rax
  const struct UnBCL::String *v7; // rax
  struct UnBCL::RegistryKey *v8; // rax
  const struct UnBCL::String *v9; // rax
  const struct UnBCL::String *v10; // rax
  struct UnBCL::RegistryKey *v11; // rax
  void **v12; // [rsp+20h] [rbp-60h] BYREF
  UnBCL::RegistryKey *v13; // [rsp+28h] [rbp-58h]
  void **v14; // [rsp+30h] [rbp-50h] BYREF
  UnBCL::RegistryKey *v15; // [rsp+38h] [rbp-48h]
  void **v16; // [rsp+40h] [rbp-40h] BYREF
  UnBCL::RegistryKey *v17; // [rsp+48h] [rbp-38h]
  _QWORD v18[3]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v19[24]; // [rsp+68h] [rbp-18h] BYREF

  LocalMachine = UnBCL::Registry::GetLocalMachine(this);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v16, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)v18,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
  v3 = UnBCL::RegistryKey::OpenSubKey(v17, v2, 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v12, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)v18);
  v4 = v13;
  if ( !v13 )
  {
    v5 = (const struct UnBCL::String *)UnBCL::String::String(
                                         (UnBCL::String *)v18,
                                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
    SubKey = UnBCL::RegistryKey::CreateSubKey(v17, v5);
    UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v14, (__int64)SubKey);
    UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=((__int64)&v12, (__int64)&v14);
    v14 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v14);
    UnBCL::String::~String((UnBCL::String *)v18);
    v4 = v13;
  }
  v7 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v18, L"Windows.old");
  v8 = UnBCL::RegistryKey::OpenSubKey(v4, v7, 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v14, (__int64)v8);
  UnBCL::String::~String((UnBCL::String *)v18);
  if ( v15 )
  {
    UnBCL::RegistryKey::Close(v15);
    v9 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v18, L"Windows.old");
    UnBCL::RegistryKey::DeleteSubKeyTree(v4, v9);
    UnBCL::String::~String((UnBCL::String *)v18);
  }
  v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v19, L"Windows.old");
  v11 = UnBCL::RegistryKey::CreateSubKey(v4, v10);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v18, (__int64)v11);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=((__int64)&v14, (__int64)v18);
  v18[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v18);
  UnBCL::String::~String((UnBCL::String *)v19);
  v14 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v14);
  v12 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v12);
  v16 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v16);
}

```

## disassembly

```asm
0x180013590  mov     [rsp-8+arg_0], rbx
0x180013595  mov     [rsp-8+arg_8], rsi
0x18001359a  push    rbp
0x18001359b  mov     rbp, rsp
0x18001359e  sub     rsp, 80h
0x1800135a5  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x1800135ab  mov     rdx, rax
0x1800135ae  lea     rcx, [rbp+var_40]
0x1800135b2  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x1800135b7  nop
0x1800135b8  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800135bf  lea     rcx, [rbp+var_30]
0x1800135c3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800135c9  nop
0x1800135ca  mov     r8d, 1
0x1800135d0  mov     rdx, rax
0x1800135d3  mov     rcx, [rbp+var_38]
0x1800135d7  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x1800135dd  mov     rdx, rax
0x1800135e0  lea     rcx, [rbp+var_60]
0x1800135e4  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x1800135e9  nop
0x1800135ea  lea     rcx, [rbp+var_30]
0x1800135ee  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800135f4  lea     rsi, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x1800135fb  mov     rbx, [rbp+var_58]
0x1800135ff  test    rbx, rbx
0x180013602  jnz     short loc_18001365A
0x180013604  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001360b  lea     rcx, [rbp+var_30]
0x18001360f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180013615  nop
0x180013616  mov     rdx, rax
0x180013619  mov     rcx, [rbp+var_38]
0x18001361d  call    cs:__imp_?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z; UnBCL::RegistryKey::CreateSubKey(UnBCL::String const *)
0x180013623  mov     rdx, rax
0x180013626  lea     rcx, [rbp+var_50]
0x18001362a  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18001362f  nop
0x180013630  lea     rdx, [rbp+var_50]
0x180013634  lea     rcx, [rbp+var_60]
0x180013638  call    ??4?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(UnBCL::SmartPtr<UnBCL::RegistryKey> const &)
0x18001363d  nop
0x18001363e  mov     [rbp+var_50], rsi
0x180013642  lea     rcx, [rbp+var_50]
0x180013646  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18001364b  nop
0x18001364c  lea     rcx, [rbp+var_30]
0x180013650  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180013656  mov     rbx, [rbp+var_58]
0x18001365a  lea     rdx, aWindowsOld_0; "Windows.old"
0x180013661  lea     rcx, [rbp+var_30]
0x180013665  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18001366b  nop
0x18001366c  mov     r8d, 1
0x180013672  mov     rdx, rax
0x180013675  mov     rcx, rbx
0x180013678  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18001367e  mov     rdx, rax
0x180013681  lea     rcx, [rbp+var_50]
0x180013685  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18001368a  nop
0x18001368b  lea     rcx, [rbp+var_30]
0x18001368f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180013695  mov     rcx, [rbp+var_48]
0x180013699  test    rcx, rcx
0x18001369c  jz      short loc_1800136CD
0x18001369e  call    cs:__imp_?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x1800136a4  lea     rdx, aWindowsOld_0; "Windows.old"
0x1800136ab  lea     rcx, [rbp+var_30]
0x1800136af  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800136b5  nop
0x1800136b6  mov     rdx, rax
0x1800136b9  mov     rcx, rbx
0x1800136bc  call    cs:__imp_?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)
0x1800136c2  nop
0x1800136c3  lea     rcx, [rbp+var_30]
0x1800136c7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800136cd  lea     rdx, aWindowsOld_0; "Windows.old"
0x1800136d4  lea     rcx, [rbp+var_18]
0x1800136d8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800136de  nop
0x1800136df  mov     rdx, rax
0x1800136e2  mov     rcx, rbx
0x1800136e5  call    cs:__imp_?CreateSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z; UnBCL::RegistryKey::CreateSubKey(UnBCL::String const *)
0x1800136eb  mov     rdx, rax
0x1800136ee  lea     rcx, [rbp+var_30]
0x1800136f2  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x1800136f7  nop
0x1800136f8  lea     rdx, [rbp+var_30]
0x1800136fc  lea     rcx, [rbp+var_50]
0x180013700  call    ??4?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(UnBCL::SmartPtr<UnBCL::RegistryKey> const &)
0x180013705  nop
0x180013706  mov     [rbp+var_30], rsi
0x18001370a  lea     rcx, [rbp+var_30]
0x18001370e  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180013713  nop
0x180013714  lea     rcx, [rbp+var_18]
0x180013718  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18001371e  nop
0x18001371f  mov     [rbp+var_50], rsi
0x180013723  lea     rcx, [rbp+var_50]
0x180013727  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18001372c  nop
0x18001372d  mov     [rbp+var_60], rsi
0x180013731  lea     rcx, [rbp+var_60]
0x180013735  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18001373a  nop
0x18001373b  mov     [rbp+var_40], rsi
0x18001373f  lea     rcx, [rbp+var_40]
0x180013743  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180013748  lea     r11, [rsp+80h+var_s0]
0x180013750  mov     rbx, [r11+10h]
0x180013754  mov     rsi, [r11+18h]
0x180013758  mov     rsp, r11
0x18001375b  pop     rbp
0x18001375c  retn
```
