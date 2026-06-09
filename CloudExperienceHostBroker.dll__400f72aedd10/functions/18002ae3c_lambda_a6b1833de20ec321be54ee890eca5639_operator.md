# _lambda_a6b1833de20ec321be54ee890eca5639_::operator()

- ea: `0x18002ae3c`
- end: `0x18002b01c`
- name: `_lambda_a6b1833de20ec321be54ee890eca5639_::operator()`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e9b0`

## callees

- `0x180002a3c`
- `0x180006140`
- `0x180007df0`
- `0x180008344`
- `0x18001dd1c`
- `0x180027e4c`
- `0x18002ae3c`
- `0x18002eaf8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aeaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aeaa`

## string_xrefs

- `0x18002aed1`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002af07`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002af88`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002afb1`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_a6b1833de20ec321be54ee890eca5639_::operator()(HSTRING *a1, __int64 a2)
{
  int OOBEUserObject; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, PCWSTR, unsigned int *, unsigned int *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // edi
  __int64 *v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  int v17; // esi
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-30h]
  __int64 *v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+38h] [rbp-18h] BYREF
  void *v25[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v27; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v28; // [rsp+88h] [rbp+38h] BYREF

  v27 = 0;
  v28 = 0;
  v25[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  OOBEUserObject = CloudExperienceHostCreateOOBEUserObject(
                     &GUID_86c815aa_4888_4063_b0ab_03c49f788be4,
                     &GUID_426317b8_c7d2_4647_ad76_2554806561b6,
                     v25);
  v5 = OOBEUserObject;
  if ( OOBEUserObject < 0 )
  {
    v6 = 246;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)OOBEUserObject,
      v22);
    goto LABEL_19;
  }
  v7 = v25[0];
  v8 = *(__int64 (__fastcall **)(void *, PCWSTR, unsigned int *, unsigned int *))(*(_QWORD *)v25[0] + 80LL);
  StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
  OOBEUserObject = v8(v7, StringRawBuffer, &v27, &v28);
  v5 = OOBEUserObject;
  if ( OOBEUserObject < 0 )
  {
    v6 = 247;
    goto LABEL_5;
  }
  v23 = 0;
  v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<bool,Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0>>(
          v10,
          &v23);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v11,
      v22);
LABEL_8:
    wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v23);
    goto LABEL_19;
  }
  v13 = 0;
  v14 = v23;
  if ( !v27 )
  {
LABEL_12:
    v24 = 0;
    v18 = *v14;
    v24 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 64))(v14, &v24);
    v5 = v19;
    if ( v19 >= 0 )
    {
      v19 = Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<bool>>::Set(
              a2,
              v24);
      v5 = v19;
      if ( v19 >= 0 )
      {
        wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v24);
        wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v23);
        v5 = 0;
        goto LABEL_19;
      }
      v20 = 260;
    }
    else
    {
      v20 = 259;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v19,
      v22);
    wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(&v24);
    goto LABEL_8;
  }
  while ( 1 )
  {
    v15 = v28;
    LOBYTE(v12) = _bittest64(&v15, v13);
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 104))(v14, v12);
    v17 = v16;
    if ( v16 < 0 )
      break;
    if ( ++v13 >= v27 )
      goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFF,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v16,
    v22);
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v23);
  v5 = v17;
LABEL_19:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  return v5;
}

```

## disassembly

```asm
0x18002ae3c  mov     [rsp-18h+arg_0], rbx
0x18002ae41  mov     [rsp-18h+arg_8], rsi
0x18002ae46  push    rbp
0x18002ae47  push    rdi
0x18002ae48  push    r14
0x18002ae4a  mov     rbp, rsp
0x18002ae4d  sub     rsp, 50h
0x18002ae51  mov     r14, rdx
0x18002ae54  mov     rsi, rcx
0x18002ae57  mov     [rbp+arg_10], 0
0x18002ae5e  mov     [rbp+arg_18], 0
0x18002ae65  mov     [rbp+var_10], 0
0x18002ae6d  lea     rcx, [rbp+var_10]
0x18002ae71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae76  lea     r8, [rbp+var_10]; void **
0x18002ae7a  lea     rdx, _GUID_426317b8_c7d2_4647_ad76_2554806561b6; struct _GUID *
0x18002ae81  lea     rcx, _GUID_86c815aa_4888_4063_b0ab_03c49f788be4; struct _GUID *
0x18002ae88  call    ?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)
0x18002ae8d  mov     ebx, eax
0x18002ae8f  test    eax, eax
0x18002ae91  jns     short loc_18002AE9A
0x18002ae93  mov     edx, 0F6h
0x18002ae98  jmp     short loc_18002AED1
0x18002ae9a  mov     rdi, [rbp+var_10]
0x18002ae9e  mov     rax, [rdi]
0x18002aea1  mov     rbx, [rax+50h]
0x18002aea5  xor     edx, edx; length
0x18002aea7  mov     rcx, [rsi]; string
0x18002aeaa  call    cs:__imp_WindowsGetStringRawBuffer
0x18002aeb0  lea     r9, [rbp+arg_18]
0x18002aeb4  lea     r8, [rbp+arg_10]
0x18002aeb8  mov     rdx, rax
0x18002aebb  mov     rcx, rdi
0x18002aebe  mov     rax, rbx
0x18002aec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aec6  mov     ebx, eax
0x18002aec8  test    eax, eax
0x18002aeca  jns     short loc_18002AEE9
0x18002aecc  mov     edx, 0F7h; void *
0x18002aed1  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002aed8  mov     r9d, eax; char *
0x18002aedb  mov     rcx, [rbp+18h]; this
0x18002aedf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aee4  jmp     loc_18002AFFE
0x18002aee9  mov     [rbp+var_20], 0
0x18002aef1  lea     rdx, [rbp+var_20]
0x18002aef5  call    ??$CreateExternalVector@_NV?$AgileVector@_NU?$DefaultEqualityPredicate@_N@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@_N@2345@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@_N@234@@ZPEAPEAV?$AgileVector@_NU?$DefaultEqualityPredicate@_N@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@_N@2345@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<bool,Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<bool> * *),Windows::Foundation::Collections::Internal::AgileVector<bool,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<bool>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<bool>,0> * *)
0x18002aefa  mov     ebx, eax
0x18002aefc  test    eax, eax
0x18002aefe  jns     short loc_18002AF27
0x18002af00  mov     rcx, [rbp+18h]; this
0x18002af04  mov     r9d, eax; char *
0x18002af07  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002af0e  mov     edx, 0FBh; void *
0x18002af13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af18  nop
0x18002af19  lea     rcx, [rbp+var_20]
0x18002af1d  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002af22  jmp     loc_18002AFFE
0x18002af27  xor     edi, edi
0x18002af29  mov     rbx, [rbp+var_20]
0x18002af2d  cmp     [rbp+arg_10], edi
0x18002af30  jbe     short loc_18002AF5A
0x18002af32  mov     r8, [rbx]
0x18002af35  mov     ecx, edi
0x18002af37  mov     eax, [rbp+arg_18]
0x18002af3a  bt      rax, rcx
0x18002af3e  setb    dl
0x18002af41  mov     rcx, rbx
0x18002af44  mov     rax, [r8+68h]
0x18002af48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af4d  mov     esi, eax
0x18002af4f  test    eax, eax
0x18002af51  js      short loc_18002AFAA
0x18002af53  inc     edi
0x18002af55  cmp     edi, [rbp+arg_10]
0x18002af58  jb      short loc_18002AF32
0x18002af5a  mov     [rbp+var_18], 0
0x18002af62  mov     rax, [rbx]
0x18002af65  mov     [rbp+var_18], 0
0x18002af6d  lea     rdx, [rbp+var_18]
0x18002af71  mov     rcx, rbx
0x18002af74  mov     rax, [rax+40h]
0x18002af78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af7d  mov     ebx, eax
0x18002af7f  test    eax, eax
0x18002af81  jns     short loc_18002AFD0
0x18002af83  mov     edx, 103h; void *
0x18002af88  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002af8f  mov     r9d, eax; char *
0x18002af92  mov     rcx, [rbp+18h]; this
0x18002af96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af9b  nop
0x18002af9c  lea     rcx, [rbp+var_18]
0x18002afa0  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002afa5  jmp     loc_18002AF19
0x18002afaa  mov     rcx, [rbp+18h]; this
0x18002afae  mov     r9d, esi; char *
0x18002afb1  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002afb8  mov     edx, 0FFh; void *
0x18002afbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afc2  nop
0x18002afc3  lea     rcx, [rbp+var_20]
0x18002afc7  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002afcc  mov     ebx, esi
0x18002afce  jmp     short loc_18002AFFE
0x18002afd0  mov     rdx, [rbp+var_18]
0x18002afd4  mov     rcx, r14
0x18002afd7  call    ?Set@?$CMarshaledInterfaceResult@U?$IVectorView@_N@Collections@Foundation@Windows@@@Internal@Windows@@QEAAJPEAU?$IVectorView@_N@Collections@Foundation@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<bool>>::Set(Windows::Foundation::Collections::IVectorView<bool> *)
0x18002afdc  mov     ebx, eax
0x18002afde  test    eax, eax
0x18002afe0  jns     short loc_18002AFE9
0x18002afe2  mov     edx, 104h
0x18002afe7  jmp     short loc_18002AF88
0x18002afe9  lea     rcx, [rbp+var_18]
0x18002afed  call    ??1?$com_ptr_t@UIOOBEOneDriveOptin@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>::~com_ptr_t<IOOBEOneDriveOptin,wil::err_exception_policy>(void)
0x18002aff2  nop
0x18002aff3  lea     rcx, [rbp+var_20]
0x18002aff7  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002affc  xor     ebx, ebx
0x18002affe  lea     rcx, [rbp+var_10]
0x18002b002  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b007  mov     eax, ebx
0x18002b009  mov     rbx, [rsp+50h+arg_0]
0x18002b00e  mov     rsi, [rsp+50h+arg_8]
0x18002b013  add     rsp, 50h
0x18002b017  pop     r14
0x18002b019  pop     rdi
0x18002b01a  pop     rbp
0x18002b01b  retn
```
