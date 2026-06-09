# SetRetryAttempt(ulong)

- ea: `0x18000c23c`
- end: `0x18000c3cd`
- name: `?SetRetryAttempt@@YAXK@Z`
- size: `401`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006838`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x1800047a8`
- `0x180006744`
- `0x18000c23c`
- `0x18000cfbc`

## import_xrefs

- `unbcl!?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@H@Z` at `0x18000c304`
- `unbcl!?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@H@Z` at `0x18000c304`
- `unbcl!?DeleteValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000c2c7`
- `unbcl!?DeleteValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z` at `0x18000c2c7`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000c281`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000c281`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000c38c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000c38c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000c395`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000c395`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c371`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000c371`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18000c359`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18000c359`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000c367`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000c367`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c29a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c2d3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c310`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c29a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c2d3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000c310`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c26c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c2ba`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c2f4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c26c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c2ba`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000c2f4`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000c24c`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000c24c`

## string_xrefs

- `0x18000c260`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18000c34b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18000c2ae`: `RetryAttempt`
- `0x18000c2e8`: `RetryAttempt`
- `0x18000c3a7`: `void __cdecl SetRetryAttempt(unsigned long)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SetRetryAttempt(__int64 a1)
{
  int v1; // edi
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v3; // rax
  struct UnBCL::RegistryKey *v4; // rax
  UnBCL::RegistryKey *v5; // rbx
  const struct UnBCL::String *v6; // rax
  const struct UnBCL::String *v7; // rax
  struct UnBCL::String *v8; // rax
  UnBCL::Exception *v9; // rax
  SetupCleanupTaskException *v10; // rbx
  UnBCL::String *v11; // rax
  const unsigned __int16 *CString; // rax
  UnBCL::Exception *pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  void (__fastcall ***v14)(_QWORD, __int64); // [rsp+28h] [rbp-50h] BYREF
  void **v15; // [rsp+30h] [rbp-48h] BYREF
  UnBCL::RegistryKey *v16; // [rsp+38h] [rbp-40h]
  _QWORD v17[2]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v18[40]; // [rsp+50h] [rbp-28h] BYREF
  int v19; // [rsp+80h] [rbp+8h]

  v19 = a1;
  v1 = a1;
  LocalMachine = UnBCL::Registry::GetLocalMachine(a1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v17, LocalMachine);
  v3 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)v18,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
  v4 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v17[1], v3, 1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v15, (__int64)v4);
  UnBCL::String::~String((UnBCL::String *)v18);
  v5 = v16;
  if ( !v16 )
  {
    v8 = UnBCL::String::Format(
           L"HKLM\\%s key doesn't exist",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v18, v8);
    v9 = (UnBCL::Exception *)UnBCL::Object::operator new(0x38u);
    v10 = v9;
    if ( v9 )
    {
      v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v18);
      CString = UnBCL::String::get_CString(v11);
      v9 = SetupCleanupTaskException::SetupCleanupTaskException(v10, CString);
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v9,
                         "void __cdecl SetRetryAttempt(unsigned long)");
    throw (SetupCleanupTaskException **)&pExceptionObject;
  }
  try
  {
    v6 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v18, L"RetryAttempt");
    UnBCL::RegistryKey::DeleteValue(v5, v6);
    UnBCL::String::~String((UnBCL::String *)v18);
  }
  catch ( UnBCL::Exception *v14 )
  {
    if ( v14 )
      (**v14)(v14, 1);
    v1 = v19;
    v5 = v16;
  }
  v7 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v18, L"RetryAttempt");
  UnBCL::RegistryKey::SetValue(v5, v7, v1);
  UnBCL::String::~String((UnBCL::String *)v18);
  v15 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v15);
  v17[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v17);
}

```

## disassembly

```asm
0x18000c23c  mov     [rsp+arg_10], rbx
0x18000c241  mov     [rsp+arg_0], ecx
0x18000c245  push    rdi
0x18000c246  sub     rsp, 70h
0x18000c24a  mov     edi, ecx
0x18000c24c  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000c252  mov     rdx, rax
0x18000c255  lea     rcx, [rsp+78h+var_38]
0x18000c25a  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000c25f  nop
0x18000c260  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c267  lea     rcx, [rsp+78h+var_28]
0x18000c26c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000c272  nop
0x18000c273  mov     r8d, 1
0x18000c279  mov     rdx, rax
0x18000c27c  mov     rcx, [rsp+78h+var_30]
0x18000c281  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000c287  mov     rdx, rax
0x18000c28a  lea     rcx, [rsp+78h+var_48]
0x18000c28f  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000c294  nop
0x18000c295  lea     rcx, [rsp+78h+var_28]
0x18000c29a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000c2a0  mov     rbx, [rsp+78h+var_40]
0x18000c2a5  test    rbx, rbx
0x18000c2a8  jz      loc_18000C34B
0x18000c2ae  lea     rdx, aRetryattempt; "RetryAttempt"
0x18000c2b5  lea     rcx, [rsp+78h+var_28]
0x18000c2ba  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000c2c0  nop
0x18000c2c1  mov     rdx, rax
0x18000c2c4  mov     rcx, rbx
0x18000c2c7  call    cs:__imp_?DeleteValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@@Z; UnBCL::RegistryKey::DeleteValue(UnBCL::String const *)
0x18000c2cd  nop
0x18000c2ce  lea     rcx, [rsp+78h+var_28]
0x18000c2d3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000c2d9  nop
0x18000c2da  jmp     short loc_18000C2E8
0x18000c2dc  mov     edi, [rsp+78h+arg_0]
0x18000c2e3  mov     rbx, [rsp+78h+var_40]
0x18000c2e8  lea     rdx, aRetryattempt; "RetryAttempt"
0x18000c2ef  lea     rcx, [rsp+78h+var_28]
0x18000c2f4  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000c2fa  nop
0x18000c2fb  mov     r8d, edi
0x18000c2fe  mov     rdx, rax
0x18000c301  mov     rcx, rbx
0x18000c304  call    cs:__imp_?SetValue@RegistryKey@UnBCL@@QEAAXPEBVString@2@H@Z; UnBCL::RegistryKey::SetValue(UnBCL::String const *,int)
0x18000c30a  nop
0x18000c30b  lea     rcx, [rsp+78h+var_28]
0x18000c310  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000c316  nop
0x18000c317  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000c31e  mov     [rsp+78h+var_48], rbx
0x18000c323  lea     rcx, [rsp+78h+var_48]
0x18000c328  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000c32d  nop
0x18000c32e  mov     [rsp+78h+var_38], rbx
0x18000c333  lea     rcx, [rsp+78h+var_38]
0x18000c338  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000c33d  mov     rbx, [rsp+78h+arg_10]
0x18000c345  add     rsp, 70h
0x18000c349  pop     rdi
0x18000c34a  retn
0x18000c34b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c352  lea     rcx, aHklmSKeyDoesnT; "HKLM\\%s key doesn't exist"
0x18000c359  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18000c35f  mov     rdx, rax
0x18000c362  lea     rcx, [rsp+78h+var_28]
0x18000c367  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18000c36d  nop
0x18000c36e  lea     ecx, [rbx+38h]
0x18000c371  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000c377  mov     rbx, rax
0x18000c37a  mov     [rsp+78h+arg_8], rax
0x18000c382  test    rax, rax
0x18000c385  jz      short loc_18000C3A7
0x18000c387  lea     rcx, [rsp+78h+var_28]
0x18000c38c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18000c392  mov     rcx, rax
0x18000c395  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18000c39b  mov     rdx, rax; unsigned __int16 *
0x18000c39e  mov     rcx, rbx; this
0x18000c3a1  call    ??0SetupCleanupTaskException@@QEAA@PEBG@Z; SetupCleanupTaskException::SetupCleanupTaskException(ushort const *)
0x18000c3a6  nop
0x18000c3a7  lea     rdx, aVoidCdeclSetre; "void __cdecl SetRetryAttempt(unsigned l"...
0x18000c3ae  mov     rcx, rax
0x18000c3b1  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000c3b6  mov     [rsp+78h+pExceptionObject], rax
0x18000c3bb  lea     rdx, _TI4PEAVSetupCleanupTaskException@@; pThrowInfo
0x18000c3c2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000c3c7  call    _CxxThrowException_0
```
