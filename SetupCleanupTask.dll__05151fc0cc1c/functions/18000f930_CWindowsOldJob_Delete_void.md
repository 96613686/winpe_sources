# CWindowsOldJob::Delete(void)

- ea: `0x18000f930`
- end: `0x18000fa53`
- name: `?Delete@CWindowsOldJob@@UEAAXXZ`
- size: `291`
- prototype: `void __fastcall(CWindowsOldJob *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800047a8`
- `0x180006744`
- `0x18000f930`

## import_xrefs

- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000fa03`
- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000fa03`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18000f9e5`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18000f9e5`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f96f`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f9bf`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f96f`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f9bf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f986`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f9d6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000fa0e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f986`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f9d6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000fa0e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f95b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f9ac`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f9f6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f95b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f9ac`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f9f6`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000f93d`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000f93d`

## string_xrefs

- `0x18000f950`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18000f9a1`: `Windows.old`
- `0x18000f9eb`: `Windows.old`

## pseudocode

```c
void __fastcall CWindowsOldJob::Delete(CWindowsOldJob *this)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  UnBCL::RegistryKey *v4; // rbx
  const struct UnBCL::String *v5; // rax
  struct UnBCL::RegistryKey *v6; // rax
  const struct UnBCL::String *v7; // rax
  void **v8; // [rsp+20h] [rbp-50h] BYREF
  UnBCL::RegistryKey *v9; // [rsp+28h] [rbp-48h]
  void **v10; // [rsp+30h] [rbp-40h] BYREF
  UnBCL::RegistryKey *v11; // [rsp+38h] [rbp-38h]
  _QWORD v12[2]; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v13[24]; // [rsp+58h] [rbp-18h] BYREF

  LocalMachine = UnBCL::Registry::GetLocalMachine(this);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v12, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)&v10,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
  v3 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v12[1], v2, 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v8, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)&v10);
  v4 = v9;
  if ( v9 )
  {
    v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v13, L"Windows.old");
    v6 = UnBCL::RegistryKey::OpenSubKey(v4, v5, 1);
    UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v10, (__int64)v6);
    UnBCL::String::~String((UnBCL::String *)v13);
    if ( v11 )
    {
      UnBCL::RegistryKey::Close(v11);
      v7 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v13, L"Windows.old");
      UnBCL::RegistryKey::DeleteSubKeyTree(v4, v7);
      UnBCL::String::~String((UnBCL::String *)v13);
    }
    v10 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v10);
  }
  v8 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v8);
  v12[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v12);
}

```

## disassembly

```asm
0x18000f930  mov     [rsp-8+arg_0], rbx
0x18000f935  push    rbp
0x18000f936  mov     rbp, rsp
0x18000f939  sub     rsp, 70h
0x18000f93d  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000f943  mov     rdx, rax
0x18000f946  lea     rcx, [rbp+var_28]
0x18000f94a  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f94f  nop
0x18000f950  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f957  lea     rcx, [rbp+var_40]
0x18000f95b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f961  nop
0x18000f962  mov     r8d, 1
0x18000f968  mov     rdx, rax
0x18000f96b  mov     rcx, [rbp+var_20]
0x18000f96f  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000f975  mov     rdx, rax
0x18000f978  lea     rcx, [rbp+var_50]
0x18000f97c  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f981  nop
0x18000f982  lea     rcx, [rbp+var_40]
0x18000f986  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000f98c  mov     rbx, [rbp+var_48]
0x18000f990  test    rbx, rbx
0x18000f993  jnz     short loc_18000F9A1
0x18000f995  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000f99c  jmp     loc_18000FA2A
0x18000f9a1  lea     rdx, aWindowsOld_0; "Windows.old"
0x18000f9a8  lea     rcx, [rbp+var_18]
0x18000f9ac  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f9b2  nop
0x18000f9b3  mov     r8d, 1
0x18000f9b9  mov     rdx, rax
0x18000f9bc  mov     rcx, rbx
0x18000f9bf  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000f9c5  mov     rdx, rax
0x18000f9c8  lea     rcx, [rbp+var_40]
0x18000f9cc  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f9d1  nop
0x18000f9d2  lea     rcx, [rbp+var_18]
0x18000f9d6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000f9dc  mov     rcx, [rbp+var_38]
0x18000f9e0  test    rcx, rcx
0x18000f9e3  jz      short loc_18000FA15
0x18000f9e5  call    cs:__imp_?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x18000f9eb  lea     rdx, aWindowsOld_0; "Windows.old"
0x18000f9f2  lea     rcx, [rbp+var_18]
0x18000f9f6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f9fc  nop
0x18000f9fd  mov     rdx, rax
0x18000fa00  mov     rcx, rbx
0x18000fa03  call    cs:__imp_?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)
0x18000fa09  nop
0x18000fa0a  lea     rcx, [rbp+var_18]
0x18000fa0e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000fa14  nop
0x18000fa15  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000fa1c  mov     [rbp+var_40], rbx
0x18000fa20  lea     rcx, [rbp+var_40]
0x18000fa24  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000fa29  nop
0x18000fa2a  mov     [rbp+var_50], rbx
0x18000fa2e  lea     rcx, [rbp+var_50]
0x18000fa32  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000fa37  nop
0x18000fa38  mov     [rbp+var_28], rbx
0x18000fa3c  lea     rcx, [rbp+var_28]
0x18000fa40  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000fa45  mov     rbx, [rsp+70h+arg_0]
0x18000fa4d  add     rsp, 70h
0x18000fa51  pop     rbp
0x18000fa52  retn
```
