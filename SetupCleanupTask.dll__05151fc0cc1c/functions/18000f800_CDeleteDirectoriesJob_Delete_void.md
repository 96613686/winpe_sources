# CDeleteDirectoriesJob::Delete(void)

- ea: `0x18000f800`
- end: `0x18000f923`
- name: `?Delete@CDeleteDirectoriesJob@@UEAAXXZ`
- size: `291`
- prototype: `void __fastcall(CDeleteDirectoriesJob *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800047a8`
- `0x180006744`
- `0x18000f800`

## import_xrefs

- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000f8d3`
- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000f8d3`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18000f8b5`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x18000f8b5`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f83f`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f88f`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f83f`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000f88f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f856`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f8a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f8de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f856`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f8a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000f8de`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f82b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f87c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f8c6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f82b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f87c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000f8c6`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000f80d`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000f80d`

## string_xrefs

- `0x18000f820`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18000f871`: `DeleteDirectories`
- `0x18000f8bb`: `DeleteDirectories`

## pseudocode

```c
void __fastcall CDeleteDirectoriesJob::Delete(CDeleteDirectoriesJob *this)
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
    v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v13, L"DeleteDirectories");
    v6 = UnBCL::RegistryKey::OpenSubKey(v4, v5, 1);
    UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v10, (__int64)v6);
    UnBCL::String::~String((UnBCL::String *)v13);
    if ( v11 )
    {
      UnBCL::RegistryKey::Close(v11);
      v7 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v13, L"DeleteDirectories");
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
0x18000f800  mov     [rsp-8+arg_0], rbx
0x18000f805  push    rbp
0x18000f806  mov     rbp, rsp
0x18000f809  sub     rsp, 70h
0x18000f80d  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000f813  mov     rdx, rax
0x18000f816  lea     rcx, [rbp+var_28]
0x18000f81a  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f81f  nop
0x18000f820  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f827  lea     rcx, [rbp+var_40]
0x18000f82b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f831  nop
0x18000f832  mov     r8d, 1
0x18000f838  mov     rdx, rax
0x18000f83b  mov     rcx, [rbp+var_20]
0x18000f83f  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000f845  mov     rdx, rax
0x18000f848  lea     rcx, [rbp+var_50]
0x18000f84c  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f851  nop
0x18000f852  lea     rcx, [rbp+var_40]
0x18000f856  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000f85c  mov     rbx, [rbp+var_48]
0x18000f860  test    rbx, rbx
0x18000f863  jnz     short loc_18000F871
0x18000f865  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000f86c  jmp     loc_18000F8FA
0x18000f871  lea     rdx, aDeletedirector; "DeleteDirectories"
0x18000f878  lea     rcx, [rbp+var_18]
0x18000f87c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f882  nop
0x18000f883  mov     r8d, 1
0x18000f889  mov     rdx, rax
0x18000f88c  mov     rcx, rbx
0x18000f88f  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000f895  mov     rdx, rax
0x18000f898  lea     rcx, [rbp+var_40]
0x18000f89c  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000f8a1  nop
0x18000f8a2  lea     rcx, [rbp+var_18]
0x18000f8a6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000f8ac  mov     rcx, [rbp+var_38]
0x18000f8b0  test    rcx, rcx
0x18000f8b3  jz      short loc_18000F8E5
0x18000f8b5  call    cs:__imp_?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x18000f8bb  lea     rdx, aDeletedirector; "DeleteDirectories"
0x18000f8c2  lea     rcx, [rbp+var_18]
0x18000f8c6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000f8cc  nop
0x18000f8cd  mov     rdx, rax
0x18000f8d0  mov     rcx, rbx
0x18000f8d3  call    cs:__imp_?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)
0x18000f8d9  nop
0x18000f8da  lea     rcx, [rbp+var_18]
0x18000f8de  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000f8e4  nop
0x18000f8e5  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000f8ec  mov     [rbp+var_40], rbx
0x18000f8f0  lea     rcx, [rbp+var_40]
0x18000f8f4  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000f8f9  nop
0x18000f8fa  mov     [rbp+var_50], rbx
0x18000f8fe  lea     rcx, [rbp+var_50]
0x18000f902  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000f907  nop
0x18000f908  mov     [rbp+var_28], rbx
0x18000f90c  lea     rcx, [rbp+var_28]
0x18000f910  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000f915  mov     rbx, [rsp+70h+arg_0]
0x18000f91d  add     rsp, 70h
0x18000f921  pop     rbp
0x18000f922  retn
```
