# pDeleteSetupCleanupJobs(void)

- ea: `0x1800177bc`
- end: `0x18001787f`
- name: `?pDeleteSetupCleanupJobs@@YAXXZ`
- size: `195`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800174c4`

## callees

- `0x1800047a8`
- `0x180006744`
- `0x1800177bc`

## import_xrefs

- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x180017840`
- `unbcl!?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x180017840`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x180017821`
- `unbcl!?Close@RegistryKey@UnBCL@@QEAAXXZ` at `0x180017821`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800177fb`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800177fb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180017812`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001784b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180017812`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001784b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800177e7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180017832`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800177e7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180017832`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x1800177c9`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x1800177c9`

## string_xrefs

- `0x1800177dc`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x180017827`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall pDeleteSetupCleanupJobs(__int64 a1)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  const struct UnBCL::String *v4; // rax
  void **v5; // [rsp+20h] [rbp-40h] BYREF
  UnBCL::RegistryKey *v6; // [rsp+28h] [rbp-38h]
  void **v7; // [rsp+30h] [rbp-30h] BYREF
  UnBCL::RegistryKey *v8; // [rsp+38h] [rbp-28h]
  _BYTE v9[32]; // [rsp+40h] [rbp-20h] BYREF

  LocalMachine = UnBCL::Registry::GetLocalMachine(a1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v5, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)v9,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
  v3 = UnBCL::RegistryKey::OpenSubKey(v6, v2, 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v7, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)v9);
  if ( v8 )
  {
    UnBCL::RegistryKey::Close(v8);
    v4 = (const struct UnBCL::String *)UnBCL::String::String(
                                         (UnBCL::String *)v9,
                                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
    UnBCL::RegistryKey::DeleteSubKeyTree(v6, v4);
    UnBCL::String::~String((UnBCL::String *)v9);
  }
  v7 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v7);
  v5 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v5);
}

```

## disassembly

```asm
0x1800177bc  mov     [rsp-8+arg_0], rbx
0x1800177c1  push    rbp
0x1800177c2  mov     rbp, rsp
0x1800177c5  sub     rsp, 60h
0x1800177c9  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x1800177cf  mov     rdx, rax
0x1800177d2  lea     rcx, [rbp+var_40]
0x1800177d6  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x1800177db  nop
0x1800177dc  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800177e3  lea     rcx, [rbp+var_20]
0x1800177e7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800177ed  nop
0x1800177ee  mov     r8d, 1
0x1800177f4  mov     rdx, rax
0x1800177f7  mov     rcx, [rbp+var_38]
0x1800177fb  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x180017801  mov     rdx, rax
0x180017804  lea     rcx, [rbp+var_30]
0x180017808  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18001780d  nop
0x18001780e  lea     rcx, [rbp+var_20]
0x180017812  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180017818  mov     rcx, [rbp+var_28]
0x18001781c  test    rcx, rcx
0x18001781f  jz      short loc_180017852
0x180017821  call    cs:__imp_?Close@RegistryKey@UnBCL@@QEAAXXZ; UnBCL::RegistryKey::Close(void)
0x180017827  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001782e  lea     rcx, [rbp+var_20]
0x180017832  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180017838  nop
0x180017839  mov     rdx, rax
0x18001783c  mov     rcx, [rbp+var_38]
0x180017840  call    cs:__imp_?DeleteSubKeyTree@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteSubKeyTree(UnBCL::String const *)
0x180017846  nop
0x180017847  lea     rcx, [rbp+var_20]
0x18001784b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180017851  nop
0x180017852  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x180017859  mov     [rbp+var_30], rbx
0x18001785d  lea     rcx, [rbp+var_30]
0x180017861  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180017866  nop
0x180017867  mov     [rbp+var_40], rbx
0x18001786b  lea     rcx, [rbp+var_40]
0x18001786f  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180017874  mov     rbx, [rsp+60h+arg_0]
0x180017879  add     rsp, 60h
0x18001787d  pop     rbp
0x18001787e  retn
```
