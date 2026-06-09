# _lambda_28102650c2cc21f48a3bc887a2bc2ff2_::operator()

- ea: `0x18002a9b8`
- end: `0x18002ab8a`
- name: `_lambda_28102650c2cc21f48a3bc887a2bc2ff2_::operator()`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e900`

## callees

- `0x180002a3c`
- `0x180006140`
- `0x180007df0`
- `0x180008344`
- `0x18001dd1c`
- `0x180027e4c`
- `0x18002a9b8`
- `0x18002eaf8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa1f`

## string_xrefs

- `0x18002aa48`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002aa7c`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002aaff`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002ab26`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_28102650c2cc21f48a3bc887a2bc2ff2_::operator()(HSTRING *a1, __int64 a2)
{
  int OOBEUserObject; // eax
  unsigned int v5; // ebx
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, PCWSTR, unsigned int *, unsigned int *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 *v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  int v16; // esi
  __int64 v17; // rax
  int v18; // eax
  int v20; // [rsp+20h] [rbp-30h]
  __int64 *v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  void *v23[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v25; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v26; // [rsp+88h] [rbp+38h] BYREF

  v25 = 0;
  v26 = 0;
  v23[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v23);
  OOBEUserObject = CloudExperienceHostCreateOOBEUserObject(
                     &GUID_86c815aa_4888_4063_b0ab_03c49f788be4,
                     &GUID_426317b8_c7d2_4647_ad76_2554806561b6,
                     v23);
  v5 = OOBEUserObject;
  if ( OOBEUserObject < 0
    || (v6 = v23[0],
        v7 = *(__int64 (__fastcall **)(void *, PCWSTR, unsigned int *, unsigned int *))(*(_QWORD *)v23[0] + 88LL),
        StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0),
        OOBEUserObject = v7(v6, StringRawBuffer, &v25, &v26),
        v5 = OOBEUserObject,
        OOBEUserObject < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)OOBEUserObject,
      v20);
    goto LABEL_15;
  }
  v21 = 0;
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<bool,Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0>>(
          v9,
          &v21);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v10,
      v20);
LABEL_6:
    wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v21);
    goto LABEL_15;
  }
  v12 = 0;
  v13 = v21;
  if ( !v25 )
  {
LABEL_10:
    v22 = 0;
    v17 = *v13;
    v22 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v17 + 64))(v13, &v22);
    v5 = v18;
    if ( v18 >= 0 )
    {
      v18 = Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<bool>>::Set(
              a2,
              v22);
      v5 = v18;
      if ( v18 >= 0 )
      {
        wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v22);
        wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v21);
        v5 = 0;
        goto LABEL_15;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v18,
      v20);
    wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v22);
    goto LABEL_6;
  }
  while ( 1 )
  {
    v14 = v26;
    LOBYTE(v11) = _bittest64(&v14, v12);
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v13 + 104))(v13, v11);
    v16 = v15;
    if ( v15 < 0 )
      break;
    if ( ++v12 >= v25 )
      goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12C,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v15,
    v20);
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v21);
  v5 = v16;
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v23);
  return v5;
}

```

## disassembly

```asm
0x18002a9b8  mov     [rsp-18h+arg_0], rbx
0x18002a9bd  mov     [rsp-18h+arg_8], rsi
0x18002a9c2  push    rbp
0x18002a9c3  push    rdi
0x18002a9c4  push    r14
0x18002a9c6  mov     rbp, rsp
0x18002a9c9  sub     rsp, 50h
0x18002a9cd  mov     r14, rdx
0x18002a9d0  mov     rsi, rcx
0x18002a9d3  mov     [rbp+arg_10], 0
0x18002a9da  mov     [rbp+arg_18], 0
0x18002a9e1  mov     [rbp+var_10], 0
0x18002a9e9  lea     rcx, [rbp+var_10]
0x18002a9ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a9f2  lea     r8, [rbp+var_10]; void **
0x18002a9f6  lea     rdx, _GUID_426317b8_c7d2_4647_ad76_2554806561b6; struct _GUID *
0x18002a9fd  lea     rcx, _GUID_86c815aa_4888_4063_b0ab_03c49f788be4; struct _GUID *
0x18002aa04  call    ?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)
0x18002aa09  mov     ebx, eax
0x18002aa0b  test    eax, eax
0x18002aa0d  js      short loc_18002AA41
0x18002aa0f  mov     rdi, [rbp+var_10]
0x18002aa13  mov     rax, [rdi]
0x18002aa16  mov     rbx, [rax+58h]
0x18002aa1a  xor     edx, edx; length
0x18002aa1c  mov     rcx, [rsi]; string
0x18002aa1f  call    cs:__imp_WindowsGetStringRawBuffer
0x18002aa25  lea     r9, [rbp+arg_18]
0x18002aa29  lea     r8, [rbp+arg_10]
0x18002aa2d  mov     rdx, rax
0x18002aa30  mov     rcx, rdi
0x18002aa33  mov     rax, rbx
0x18002aa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa3b  mov     ebx, eax
0x18002aa3d  test    eax, eax
0x18002aa3f  jns     short loc_18002AA5E
0x18002aa41  mov     rcx, [rbp+18h]; this
0x18002aa45  mov     r9d, eax; char *
0x18002aa48  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002aa4f  mov     edx, 12Ch; void *
0x18002aa54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa59  jmp     loc_18002AB6C
0x18002aa5e  mov     [rbp+var_20], 0
0x18002aa66  lea     rdx, [rbp+var_20]
0x18002aa6a  call    ??$CreateExternalVector@_NV?$AgileVector@_NU?$DefaultEqualityPredicate@_N@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@_N@2345@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@_N@234@@ZPEAPEAV?$AgileVector@_NU?$DefaultEqualityPredicate@_N@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@_N@2345@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<bool,Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<bool> * *),Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0> * *)
0x18002aa6f  mov     ebx, eax
0x18002aa71  test    eax, eax
0x18002aa73  jns     short loc_18002AA9C
0x18002aa75  mov     rcx, [rbp+18h]; this
0x18002aa79  mov     r9d, eax; char *
0x18002aa7c  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002aa83  mov     edx, 12Ch; void *
0x18002aa88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa8d  nop
0x18002aa8e  lea     rcx, [rbp+var_20]
0x18002aa92  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002aa97  jmp     loc_18002AB6C
0x18002aa9c  xor     edi, edi
0x18002aa9e  mov     rbx, [rbp+var_20]
0x18002aaa2  cmp     [rbp+arg_10], edi
0x18002aaa5  jbe     short loc_18002AACF
0x18002aaa7  mov     r8, [rbx]
0x18002aaaa  mov     ecx, edi
0x18002aaac  mov     eax, [rbp+arg_18]
0x18002aaaf  bt      rax, rcx
0x18002aab3  setb    dl
0x18002aab6  mov     rcx, rbx
0x18002aab9  mov     rax, [r8+68h]
0x18002aabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aac2  mov     esi, eax
0x18002aac4  test    eax, eax
0x18002aac6  js      short loc_18002AB1F
0x18002aac8  inc     edi
0x18002aaca  cmp     edi, [rbp+arg_10]
0x18002aacd  jb      short loc_18002AAA7
0x18002aacf  mov     [rbp+var_18], 0
0x18002aad7  mov     rax, [rbx]
0x18002aada  mov     [rbp+var_18], 0
0x18002aae2  lea     rdx, [rbp+var_18]
0x18002aae6  mov     rcx, rbx
0x18002aae9  mov     rax, [rax+40h]
0x18002aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaf2  mov     ebx, eax
0x18002aaf4  test    eax, eax
0x18002aaf6  jns     short loc_18002AB45
0x18002aaf8  mov     rcx, [rbp+18h]; this
0x18002aafc  mov     r9d, eax; char *
0x18002aaff  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002ab06  mov     edx, 12Ch; void *
0x18002ab0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab10  nop
0x18002ab11  lea     rcx, [rbp+var_18]
0x18002ab15  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002ab1a  jmp     loc_18002AA8E
0x18002ab1f  mov     rcx, [rbp+18h]; this
0x18002ab23  mov     r9d, esi; char *
0x18002ab26  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002ab2d  mov     edx, 12Ch; void *
0x18002ab32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab37  nop
0x18002ab38  lea     rcx, [rbp+var_20]
0x18002ab3c  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002ab41  mov     ebx, esi
0x18002ab43  jmp     short loc_18002AB6C
0x18002ab45  mov     rdx, [rbp+var_18]
0x18002ab49  mov     rcx, r14
0x18002ab4c  call    ?Set@?$CMarshaledInterfaceResult@U?$IVectorView@_N@Collections@Foundation@Windows@@@Internal@Windows@@QEAAJPEAU?$IVectorView@_N@Collections@Foundation@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<bool>>::Set(Windows::Foundation::Collections::IVectorView<bool> *)
0x18002ab51  mov     ebx, eax
0x18002ab53  test    eax, eax
0x18002ab55  js      short loc_18002AAF8
0x18002ab57  lea     rcx, [rbp+var_18]
0x18002ab5b  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002ab60  nop
0x18002ab61  lea     rcx, [rbp+var_20]
0x18002ab65  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002ab6a  xor     ebx, ebx
0x18002ab6c  lea     rcx, [rbp+var_10]
0x18002ab70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ab75  mov     eax, ebx
0x18002ab77  mov     rbx, [rsp+50h+arg_0]
0x18002ab7c  mov     rsi, [rsp+50h+arg_8]
0x18002ab81  add     rsp, 50h
0x18002ab85  pop     r14
0x18002ab87  pop     rdi
0x18002ab88  pop     rbp
0x18002ab89  retn
```
