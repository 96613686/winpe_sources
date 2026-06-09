# GetRetryAttempt(void)

- ea: `0x180009838`
- end: `0x180009994`
- name: `?GetRetryAttempt@@YAKXZ`
- size: `348`
- prototype: `__int64 __fastcall(__int64)`
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
- `0x180009838`
- `0x18000cfbc`

## import_xrefs

- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x1800098be`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x1800098be`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000987c`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000987c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009953`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009953`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000995c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000995c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180009938`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180009938`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180009920`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180009920`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000992e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000992e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180009895`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800098cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180009895`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800098cf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000986a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800098b1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000986a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800098b1`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000984a`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000984a`

## string_xrefs

- `0x18000985e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x180009912`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x18000996e`: `unsigned long __cdecl GetRetryAttempt(void)`
- `0x1800098a5`: `RetryAttempt`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetRetryAttempt(__int64 a1)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  UnBCL::RegistryKey *v4; // rbx
  const struct UnBCL::String *v5; // rax
  unsigned int Value; // ebx
  struct UnBCL::String *v8; // rax
  UnBCL::Exception *v9; // rax
  SetupCleanupTaskException *v10; // rbx
  UnBCL::String *v11; // rax
  const unsigned __int16 *CString; // rax
  unsigned int v13; // [rsp+20h] [rbp-58h]
  UnBCL::Exception *pExceptionObject; // [rsp+28h] [rbp-50h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64); // [rsp+30h] [rbp-48h] BYREF
  void **v16; // [rsp+38h] [rbp-40h] BYREF
  UnBCL::RegistryKey *v17; // [rsp+40h] [rbp-38h]
  _QWORD v18[2]; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-20h] BYREF

  LocalMachine = UnBCL::Registry::GetLocalMachine(a1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v18, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)v19,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
  v3 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v18[1], v2, 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v16, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)v19);
  v4 = v17;
  if ( !v17 )
  {
    v8 = UnBCL::String::Format(
           L"HKLM\\%s key doesn't exist",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v19, v8);
    v9 = (UnBCL::Exception *)UnBCL::Object::operator new(0x38u);
    v10 = v9;
    if ( v9 )
    {
      v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v19);
      CString = UnBCL::String::get_CString(v11);
      v9 = SetupCleanupTaskException::SetupCleanupTaskException(v10, CString);
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v9,
                         "unsigned long __cdecl GetRetryAttempt(void)");
    throw (SetupCleanupTaskException **)&pExceptionObject;
  }
  try
  {
    v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v19, L"RetryAttempt");
    Value = UnBCL::RegistryKey::GetValue(v4, v5);
    v13 = Value;
    UnBCL::String::~String((UnBCL::String *)v19);
  }
  catch ( UnBCL::Exception *v15 )
  {
    if ( v15 )
      (**v15)(v15, 1);
    Value = v13;
  }
  v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v19, L"RetryAttempt");
  Value = UnBCL::RegistryKey::GetValue(v4, v5);
  v13 = Value;
  UnBCL::String::~String((UnBCL::String *)v19);
  if ( v15 )
    (**v15)(v15, 1);
}

```

## disassembly

```asm
0x180009838  mov     [rsp+arg_8], rbx
0x18000983d  push    rdi
0x18000983e  sub     rsp, 70h
0x180009842  mov     [rsp+78h+var_58], 0
0x18000984a  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x180009850  mov     rdx, rax
0x180009853  lea     rcx, [rsp+78h+var_30]
0x180009858  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000985d  nop
0x18000985e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009865  lea     rcx, [rsp+78h+var_20]
0x18000986a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180009870  nop
0x180009871  xor     r8d, r8d
0x180009874  mov     rdx, rax
0x180009877  mov     rcx, [rsp+78h+var_28]
0x18000987c  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x180009882  mov     rdx, rax
0x180009885  lea     rcx, [rsp+78h+var_40]
0x18000988a  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000988f  nop
0x180009890  lea     rcx, [rsp+78h+var_20]
0x180009895  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000989b  mov     rbx, [rsp+78h+var_38]
0x1800098a0  test    rbx, rbx
0x1800098a3  jz      short loc_180009912
0x1800098a5  lea     rdx, aRetryattempt; "RetryAttempt"
0x1800098ac  lea     rcx, [rsp+78h+var_20]
0x1800098b1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800098b7  nop
0x1800098b8  mov     rdx, rax
0x1800098bb  mov     rcx, rbx
0x1800098be  call    cs:__imp_?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z; UnBCL::RegistryKey::GetValue(UnBCL::String const *)
0x1800098c4  mov     ebx, eax
0x1800098c6  mov     [rsp+78h+var_58], eax
0x1800098ca  lea     rcx, [rsp+78h+var_20]
0x1800098cf  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800098d5  nop
0x1800098d6  jmp     short loc_1800098DC
0x1800098d8  mov     ebx, [rsp+78h+var_58]
0x1800098dc  lea     rdi, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x1800098e3  mov     [rsp+78h+var_40], rdi
0x1800098e8  lea     rcx, [rsp+78h+var_40]
0x1800098ed  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x1800098f2  nop
0x1800098f3  mov     [rsp+78h+var_30], rdi
0x1800098f8  lea     rcx, [rsp+78h+var_30]
0x1800098fd  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180009902  mov     eax, ebx
0x180009904  mov     rbx, [rsp+78h+arg_8]
0x18000990c  add     rsp, 70h
0x180009910  pop     rdi
0x180009911  retn
0x180009912  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009919  lea     rcx, aHklmSKeyDoesnT; "HKLM\\%s key doesn't exist"
0x180009920  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180009926  mov     rdx, rax
0x180009929  lea     rcx, [rsp+78h+var_20]
0x18000992e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180009934  nop
0x180009935  lea     ecx, [rbx+38h]
0x180009938  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000993e  mov     rbx, rax
0x180009941  mov     [rsp+78h+arg_0], rax
0x180009949  test    rax, rax
0x18000994c  jz      short loc_18000996E
0x18000994e  lea     rcx, [rsp+78h+var_20]
0x180009953  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180009959  mov     rcx, rax
0x18000995c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180009962  mov     rdx, rax; unsigned __int16 *
0x180009965  mov     rcx, rbx; this
0x180009968  call    ??0SetupCleanupTaskException@@QEAA@PEBG@Z; SetupCleanupTaskException::SetupCleanupTaskException(ushort const *)
0x18000996d  nop
0x18000996e  lea     rdx, aUnsignedLongCd; "unsigned long __cdecl GetRetryAttempt(v"...
0x180009975  mov     rcx, rax
0x180009978  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000997d  mov     [rsp+78h+pExceptionObject], rax
0x180009982  lea     rdx, _TI4PEAVSetupCleanupTaskException@@; pThrowInfo
0x180009989  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000998e  call    _CxxThrowException_0
```
