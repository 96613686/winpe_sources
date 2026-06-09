# CWindowsOldJob::GetMigScopeValue(void)

- ea: `0x18000ffc8`
- end: `0x1800100b8`
- name: `?GetMigScopeValue@CWindowsOldJob@@AEAAKXZ`
- size: `240`
- prototype: `__int64 __fastcall(CWindowsOldJob *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180011214`

## callees

- `0x1800047a8`
- `0x180006744`
- `0x18000ffc8`

## import_xrefs

- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x180010046`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x180010046`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180010004`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180010004`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001001d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180010053`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001001d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180010053`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000fff2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180010039`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000fff2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180010039`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000ffd2`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000ffd2`

## pseudocode

```c
__int64 __fastcall CWindowsOldJob::GetMigScopeValue(CWindowsOldJob *this)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  UnBCL::RegistryKey *v4; // rbx
  const struct UnBCL::String *v5; // rax
  unsigned int Value; // edi
  void (__fastcall ***v8)(_QWORD, __int64); // [rsp+20h] [rbp-48h] BYREF
  void **v9; // [rsp+28h] [rbp-40h] BYREF
  UnBCL::RegistryKey *v10; // [rsp+30h] [rbp-38h]
  _QWORD v11[2]; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v12[32]; // [rsp+48h] [rbp-20h] BYREF

  LocalMachine = UnBCL::Registry::GetLocalMachine(this);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v11, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v12, L"SYSTEM\\Setup");
  v3 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v11[1], v2, 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v9, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)v12);
  v4 = v10;
  if ( v10 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v12, L"LastMigrationScope");
      Value = UnBCL::RegistryKey::GetValue(v4, v5);
      UnBCL::String::~String((UnBCL::String *)v12);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v8) )
      {
        if ( v8 )
          (**v8)(v8, 1);
        __eh34_try_continuation(0, &UnBCL::Exception * `RTTI Type Descriptor', &loc_180010084);
        goto LABEL_4;
      }
    }
    v9 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v9);
    v11[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
    UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v11);
    return Value;
  }
LABEL_4:
  v9 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v9);
  v11[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v11);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000ffc8  mov     [rsp+arg_0], rbx
0x18000ffcd  push    rdi
0x18000ffce  sub     rsp, 60h
0x18000ffd2  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000ffd8  mov     rdx, rax
0x18000ffdb  lea     rcx, [rsp+68h+var_30]
0x18000ffe0  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000ffe5  nop
0x18000ffe6  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000ffed  lea     rcx, [rsp+68h+var_20]
0x18000fff2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000fff8  nop
0x18000fff9  xor     r8d, r8d
0x18000fffc  mov     rdx, rax
0x18000ffff  mov     rcx, [rsp+68h+var_28]
0x180010004  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18001000a  mov     rdx, rax
0x18001000d  lea     rcx, [rsp+68h+var_40]
0x180010012  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x180010017  nop
0x180010018  lea     rcx, [rsp+68h+var_20]
0x18001001d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180010023  mov     rbx, [rsp+68h+var_38]
0x180010028  test    rbx, rbx
0x18001002b  jz      short loc_180010084
0x18001002d  lea     rdx, aLastmigrations; "LastMigrationScope"
0x180010034  lea     rcx, [rsp+68h+var_20]
0x180010039  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18001003f  nop
0x180010040  mov     rdx, rax
0x180010043  mov     rcx, rbx
0x180010046  call    cs:__imp_?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z; UnBCL::RegistryKey::GetValue(UnBCL::String const *)
0x18001004c  mov     edi, eax
0x18001004e  lea     rcx, [rsp+68h+var_20]
0x180010053  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180010059  nop
0x18001005a  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x180010061  mov     [rsp+68h+var_40], rbx
0x180010066  lea     rcx, [rsp+68h+var_40]
0x18001006b  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180010070  nop
0x180010071  mov     [rsp+68h+var_30], rbx
0x180010076  lea     rcx, [rsp+68h+var_30]
0x18001007b  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180010080  mov     eax, edi
0x180010082  jmp     short loc_1800100AD
0x180010084  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18001008b  mov     [rsp+68h+var_40], rbx
0x180010090  lea     rcx, [rsp+68h+var_40]
0x180010095  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18001009a  nop
0x18001009b  mov     [rsp+68h+var_30], rbx
0x1800100a0  lea     rcx, [rsp+68h+var_30]
0x1800100a5  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x1800100aa  or      eax, 0FFFFFFFFh
0x1800100ad  mov     rbx, [rsp+68h+arg_0]
0x1800100b2  add     rsp, 60h
0x1800100b6  pop     rdi
0x1800100b7  retn
```
