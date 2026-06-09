# GetBluetoothInstanceId

- ea: `0x1800087a0`
- end: `0x180008f6e`
- name: `GetBluetoothInstanceId`
- size: `1998`
- prototype: `__int64 __fastcall(HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800017dc`
- `0x180005d90`
- `0x180006280`
- `0x180006c6c`
- `0x180008130`
- `0x1800087a0`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008e01`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e01`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e3c`
- `KERNEL32!CreateEventExA` at `0x180008977`
- `KERNEL32!CreateEventExA` at `0x180008977`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008c7e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008c7e`
- `KERNEL32!GetLastError` at `0x18000899e`
- `KERNEL32!GetLastError` at `0x180008f3b`
- `KERNEL32!GetLastError` at `0x18000899e`
- `KERNEL32!GetLastError` at `0x180008f3b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e1f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e1f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008e5d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800087dd`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800087dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008887`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800088f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800089fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800088f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800089fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008deb`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall GetBluetoothInstanceId(HSTRING *a1)
{
  int v1; // esi
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  unsigned int v6; // r8d
  wil::details::in1diag3 *v7; // rcx
  int v8; // eax
  unsigned int v9; // r8d
  _QWORD *v10; // rbx
  __int64 (__fastcall **v11)(_QWORD *, GUID *, _QWORD *); // rdi
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // r8d
  wil::details::in1diag3 *v17; // rcx
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  signed int LastError; // eax
  _QWORD *v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // r15
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  wil::details::in1diag3 *v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // r15
  __int64 v33; // rbx
  _QWORD *v34; // rax
  _QWORD *v35; // rdi
  _QWORD *v36; // rax
  _QWORD *v37; // rbx
  int v38; // eax
  unsigned int v39; // r8d
  int v40; // eax
  unsigned int v41; // r8d
  int v42; // eax
  unsigned int v43; // r8d
  int v44; // eax
  unsigned int v45; // r8d
  unsigned int v46; // r8d
  __int64 v47; // rcx
  __int64 v48; // rcx
  _QWORD *v49; // rcx
  _QWORD *v50; // rcx
  WCHAR *v51; // rcx
  signed __int64 v52; // rdx
  HRESULT v53; // eax
  int v54; // edx
  unsigned int v55; // r8d
  HSTRING *v56; // rbx
  signed int v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  int v61; // [rsp+20h] [rbp-E8h]
  __int64 v62; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD *v63; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v64; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v65; // [rsp+48h] [rbp-C0h] BYREF
  void **v66; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE hHandle; // [rsp+58h] [rbp-B0h]
  int v68; // [rsp+60h] [rbp-A8h]
  PCWSTR sourceString[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+78h] [rbp-90h]
  __int64 v71; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v72; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v73; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v74; // [rsp+98h] [rbp-70h]
  _QWORD *v75; // [rsp+A0h] [rbp-68h]
  HSTRING *newString; // [rsp+A8h] [rbp-60h]
  _QWORD *v77; // [rsp+B0h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  newString = a1;
  v1 = RoInitialize(1);
  v68 = v1;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  *(_OWORD *)sourceString = 0;
  v70 = 0;
  v63 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Enumeration.DeviceInformation", 0x2Du, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
LABEL_60:
    wil::details::in1diag3::_Throw_Hr(v7, (void *)0x14F, v6, (const char *)(unsigned int)ActivationFactory, v61);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v63);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_60;
  string = 0;
  v64 = 0;
  v8 = Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(&v64);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x153, v9, (const char *)(unsigned int)v8, v61);
  v10 = v64;
  v11 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v64;
  string = 0;
  v12 = WindowsCreateStringReference(L"System.Devices.DeviceInstanceId", 0x1Fu, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
LABEL_63:
    wil::details::in1diag3::_Throw_Hr(v17, (void *)0x154, v16, (const char *)(unsigned int)v15, v61);
  }
  v15 = ((__int64 (__fastcall **)(_QWORD *, GUID *, HSTRING))v11)[11](v10, 0, string);
  v17 = retaddr;
  if ( v15 < 0 )
    goto LABEL_63;
  string = 0;
  v65 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v64)(
          v64,
          &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e,
          &v65);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x157, v19, (const char *)(unsigned int)v18, v61);
  hHandle = CreateEventExA(0, 0, 1u, 0x1F0003u);
  v66 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x15A, v20, (const char *)(unsigned int)LastError, v61);
  v62 = 0;
  v22 = v63;
  v23 = *v63;
  v24 = v65;
  string = 0;
  v25 = WindowsCreateStringReference(
          L"System.Devices.InterfaceClassGuid:=\"{92383B0E-F90E-4AC9-8D44-8C2D0D0EBDA2}\"",
          0x4Bu,
          &hstringHeader,
          &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
LABEL_67:
    wil::details::in1diag3::_Throw_Hr(v30, (void *)0x161, v29, (const char *)(unsigned int)v28, v61);
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, __int64 *))(v23 + 120))(v22, string, v24, &v62);
  v30 = retaddr;
  if ( v28 < 0 )
    goto LABEL_67;
  string = 0;
  v31 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v32 = v31;
  if ( v31 )
  {
    *v31 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
    *((_DWORD *)v31 + 3) = 1;
    *v31 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,Windows::Devices::Enumeration::DeviceInformation *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v32[2] = sourceString;
    *v32 = off_18000C2C0;
  }
  else
  {
    v32 = 0;
  }
  v77 = v32;
  v33 = v71;
  v74 = v72;
  v75 = v73;
  v34 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v34;
  if ( v34 )
  {
    *v34 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
    *((_DWORD *)v34 + 3) = 1;
    *v34 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v35[2] = &v66;
    v35[3] = v33;
    v35[4] = v74;
    v35[5] = v75;
    *v35 = off_18000C298;
  }
  else
  {
    v35 = 0;
  }
  v75 = v35;
  v36 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = v36;
  if ( v36 )
  {
    *v36 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
    *((_DWORD *)v36 + 3) = 1;
    *v36 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v37[2] = &v66;
    *v37 = off_18000C270;
  }
  else
  {
    v37 = 0;
  }
  v74 = v37;
  v38 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v62 + 48LL))(v62, v32, &v71);
  if ( v38 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1B5, v39, (const char *)(unsigned int)v38, v61);
  v40 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v62 + 112LL))(v62, v35, &v72);
  if ( v40 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1B6, v41, (const char *)(unsigned int)v40, v61);
  v42 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v62 + 96LL))(v62, v37, &v73);
  if ( v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1B7, v43, (const char *)(unsigned int)v42, v61);
  v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 136LL))(v62);
  if ( v44 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1B9, v45, (const char *)(unsigned int)v44, v61);
  WaitForSingleObjectEx(hHandle, 0x7530u, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 144LL))(v62);
  if ( v37 )
    (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
  if ( v35 )
    (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
  if ( v32 )
    (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
  v47 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v66 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v66) )
    {
      v58 = GetLastError();
      if ( v58 > 0 )
        v58 = (unsigned __int16)v58 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
      goto LABEL_75;
    }
    hHandle = 0;
  }
  v48 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
  }
  v50 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
  }
  v51 = (WCHAR *)sourceString[0];
  if ( sourceString[0] != sourceString[1] )
  {
    v52 = sourceString[1] - sourceString[0];
    string = 0;
    if ( !(_DWORD)v52 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, 0, v46);
      JUMPOUT(0x180008F6DLL);
    }
    v53 = WindowsCreateStringReference(sourceString[0], v52 - 1, &hstringHeader, &string);
    if ( v53 >= 0 )
    {
      v56 = newString;
      WindowsDeleteString(*newString);
      *v56 = 0;
      WindowsDuplicateString(string, v56);
      v51 = (WCHAR *)sourceString[0];
      goto LABEL_54;
    }
LABEL_75:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v53, v54, v55);
    __debugbreak();
  }
LABEL_54:
  if ( v51 )
  {
    operator delete(v51);
    *(_OWORD *)sourceString = 0;
    v70 = 0;
  }
  if ( v1 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800087a0  mov     [rsp+arg_8], rbx
0x1800087a5  mov     [rsp+arg_10], rsi
0x1800087aa  push    rdi
0x1800087ab  push    r12
0x1800087ad  push    r13
0x1800087af  push    r14
0x1800087b1  push    r15
0x1800087b3  sub     rsp, 0E0h
0x1800087ba  mov     rax, cs:__security_cookie
0x1800087c1  xor     rax, rsp
0x1800087c4  mov     [rsp+108h+var_30], rax
0x1800087cc  mov     [rsp+108h+newString], rcx
0x1800087d4  mov     r13d, 1
0x1800087da  mov     ecx, r13d
0x1800087dd  call    cs:__imp_RoInitialize
0x1800087e4  nop     dword ptr [rax+rax+00h]
0x1800087e9  mov     esi, eax
0x1800087eb  mov     [rsp+108h+var_A8], eax
0x1800087ef  xor     r14d, r14d
0x1800087f2  mov     [rsp+108h+var_88], r14
0x1800087fa  mov     [rsp+108h+var_80], r14
0x180008802  mov     [rsp+108h+var_78], r14
0x18000880a  xorps   xmm0, xmm0
0x18000880d  movdqu  xmmword ptr [rsp+108h+sourceString], xmm0
0x180008813  mov     [rsp+108h+var_90], r14
0x180008818  mov     [rsp+108h+var_D0], r14
0x18000881d  mov     [rsp+108h+string], r14
0x180008825  lea     r9, [rsp+108h+string]; string
0x18000882d  lea     r8, [rsp+108h+hstringHeader]; hstringHeader
0x180008835  lea     edx, [r13+2Ch]; length
0x180008839  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x180008840  call    cs:__imp_WindowsCreateStringReference
0x180008847  nop     dword ptr [rax+rax+00h]
0x18000884c  test    eax, eax
0x18000884e  js      loc_180008E9B
0x180008854  mov     rbx, [rsp+108h+string]
0x18000885c  mov     rcx, [rsp+108h+var_D0]
0x180008861  test    rcx, rcx
0x180008864  jz      short loc_180008878
0x180008866  mov     [rsp+108h+var_D0], r14
0x18000886b  mov     rax, [rcx]
0x18000886e  mov     rax, [rax+10h]
0x180008872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008877  nop
0x180008878  lea     r8, [rsp+108h+var_D0]
0x18000887d  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x180008884  mov     rcx, rbx
0x180008887  call    cs:__imp_RoGetActivationFactory
0x18000888e  nop     dword ptr [rax+rax+00h]
0x180008893  mov     rcx, [rsp+108h]
0x18000889b  test    eax, eax
0x18000889d  js      loc_180008EA3
0x1800088a3  mov     [rsp+108h+string], r14
0x1800088ab  mov     [rsp+108h+var_C8], r14
0x1800088b0  lea     rcx, [rsp+108h+var_C8]
0x1800088b5  call    ?Make@?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1800088ba  mov     rcx, [rsp+108h]; this
0x1800088c2  test    eax, eax
0x1800088c4  js      loc_180008EB1
0x1800088ca  mov     rbx, [rsp+108h+var_C8]
0x1800088cf  mov     rdi, [rbx]
0x1800088d2  mov     [rsp+108h+string], r14
0x1800088da  lea     r9, [rsp+108h+string]; string
0x1800088e2  lea     r8, [rsp+108h+hstringHeader]; hstringHeader
0x1800088ea  mov     edx, 1Fh; length
0x1800088ef  lea     rcx, sourceString; "System.Devices.DeviceInstanceId"
0x1800088f6  call    cs:__imp_WindowsCreateStringReference
0x1800088fd  nop     dword ptr [rax+rax+00h]
0x180008902  test    eax, eax
0x180008904  js      loc_180008EBE
0x18000890a  mov     r8, [rsp+108h+string]
0x180008912  xor     edx, edx
0x180008914  mov     rcx, rbx
0x180008917  mov     rax, [rdi+58h]
0x18000891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008920  mov     rcx, [rsp+108h]
0x180008928  test    eax, eax
0x18000892a  js      loc_180008EC6
0x180008930  mov     [rsp+108h+string], r14
0x180008938  mov     [rsp+108h+var_C0], r14
0x18000893d  mov     rcx, [rsp+108h+var_C8]
0x180008942  mov     rax, [rcx]
0x180008945  lea     r8, [rsp+108h+var_C0]
0x18000894a  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x180008951  mov     rax, [rax]
0x180008954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008959  nop
0x18000895a  mov     rcx, [rsp+108h]; this
0x180008962  test    eax, eax
0x180008964  js      loc_180008ED4
0x18000896a  mov     r9d, 1F0003h; dwDesiredAccess
0x180008970  mov     r8d, r13d; dwFlags
0x180008973  xor     edx, edx; lpName
0x180008975  xor     ecx, ecx; lpEventAttributes
0x180008977  call    cs:__imp_CreateEventExA
0x18000897e  nop     dword ptr [rax+rax+00h]
0x180008983  mov     [rsp+108h+hHandle], rax
0x180008988  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000898f  mov     [rsp+108h+var_B8], rcx
0x180008994  test    rax, rax
0x180008997  jz      short loc_18000899E
0x180008999  mov     eax, r14d
0x18000899c  jmp     short loc_1800089B6
0x18000899e  call    cs:__imp_GetLastError
0x1800089a5  nop     dword ptr [rax+rax+00h]
0x1800089aa  test    eax, eax
0x1800089ac  jle     short loc_1800089B6
0x1800089ae  movzx   eax, ax
0x1800089b1  or      eax, 80070000h
0x1800089b6  mov     rcx, [rsp+108h]; this
0x1800089be  test    eax, eax
0x1800089c0  js      loc_180008EE2
0x1800089c6  mov     [rsp+108h+var_D8], r14
0x1800089cb  mov     rbx, [rsp+108h+var_D0]
0x1800089d0  mov     rdi, [rbx]
0x1800089d3  mov     r15, [rsp+108h+var_C0]
0x1800089d8  mov     [rsp+108h+string], r14
0x1800089e0  lea     r9, [rsp+108h+string]; string
0x1800089e8  lea     r8, [rsp+108h+hstringHeader]; hstringHeader
0x1800089f0  mov     edx, 4Bh ; 'K'; length
0x1800089f5  lea     rcx, aSystemDevicesI; "System.Devices.InterfaceClassGuid:=\"{9"...
0x1800089fc  call    cs:__imp_WindowsCreateStringReference
0x180008a03  nop     dword ptr [rax+rax+00h]
0x180008a08  test    eax, eax
0x180008a0a  js      loc_180008EF0
0x180008a10  lea     r9, [rsp+108h+var_D8]
0x180008a15  mov     r8, r15
0x180008a18  mov     rdx, [rsp+108h+string]
0x180008a20  mov     rcx, rbx
0x180008a23  mov     rax, [rdi+78h]
0x180008a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2c  mov     rcx, [rsp+108h]
0x180008a34  test    eax, eax
0x180008a36  js      loc_180008EF8
0x180008a3c  mov     [rsp+108h+string], r14
0x180008a44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008a4b  mov     ecx, 18h; unsigned __int64
0x180008a50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008a55  mov     r15, rax
0x180008a58  test    rax, rax
0x180008a5b  jz      short loc_180008AA3
0x180008a5d  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180008a64  mov     [r15], rax
0x180008a67  mov     [r15+0Ch], r13d
0x180008a6b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAVDeviceInformation@234@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,Windows::Devices::Enumeration::DeviceInformation *>>::`vftable'
0x180008a72  mov     [r15], rax
0x180008a75  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008a7c  test    rcx, rcx
0x180008a7f  jz      short loc_180008A8E
0x180008a81  mov     rax, [rcx]
0x180008a84  mov     rax, [rax+8]
0x180008a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8d  nop
0x180008a8e  lea     rax, [rsp+108h+sourceString]
0x180008a93  mov     [r15+10h], rax
0x180008a97  lea     rax, off_18000C2C0
0x180008a9e  mov     [r15], rax
0x180008aa1  jmp     short loc_180008AA6
0x180008aa3  mov     r15, r14
0x180008aa6  mov     [rsp+108h+var_58], r15
0x180008aae  mov     rbx, [rsp+108h+var_88]
0x180008ab6  mov     rax, [rsp+108h+var_80]
0x180008abe  mov     [rsp+108h+var_70], rax
0x180008ac6  mov     rax, [rsp+108h+var_78]
0x180008ace  mov     [rsp+108h+var_68], rax
0x180008ad6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008add  mov     ecx, 30h ; '0'; unsigned __int64
0x180008ae2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008ae7  mov     rdi, rax
0x180008aea  test    rax, rax
0x180008aed  jz      short loc_180008B51
0x180008aef  lea     r12, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180008af6  mov     [rax], r12
0x180008af9  mov     [rax+0Ch], r13d
0x180008afd  lea     r13, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable'
0x180008b04  mov     [rax], r13
0x180008b07  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008b0e  test    rcx, rcx
0x180008b11  jz      short loc_180008B20
0x180008b13  mov     rax, [rcx]
0x180008b16  mov     rax, [rax+8]
0x180008b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b1f  nop
0x180008b20  lea     rax, [rsp+108h+var_B8]
0x180008b25  mov     [rdi+10h], rax
0x180008b29  mov     [rdi+18h], rbx
0x180008b2d  mov     rax, [rsp+108h+var_70]
0x180008b35  mov     [rdi+20h], rax
0x180008b39  mov     rax, [rsp+108h+var_68]
0x180008b41  mov     [rdi+28h], rax
0x180008b45  lea     rax, off_18000C298
0x180008b4c  mov     [rdi], rax
0x180008b4f  jmp     short loc_180008B62
0x180008b51  mov     rdi, r14
0x180008b54  lea     r12, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180008b5b  lea     r13, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable'
0x180008b62  mov     [rsp+108h+var_68], rdi
0x180008b6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008b71  mov     ecx, 18h; unsigned __int64
0x180008b76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008b7b  mov     rbx, rax
0x180008b7e  test    rax, rax
0x180008b81  jz      short loc_180008BBE
0x180008b83  mov     [rax], r12
0x180008b86  mov     dword ptr [rax+0Ch], 1
0x180008b8d  mov     [rax], r13
0x180008b90  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008b97  test    rcx, rcx
0x180008b9a  jz      short loc_180008BA9
0x180008b9c  mov     rax, [rcx]
0x180008b9f  mov     rax, [rax+8]
0x180008ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba8  nop
0x180008ba9  lea     rax, [rsp+108h+var_B8]
0x180008bae  mov     [rbx+10h], rax
0x180008bb2  lea     rax, off_18000C270
0x180008bb9  mov     [rbx], rax
0x180008bbc  jmp     short loc_180008BC1
0x180008bbe  mov     rbx, r14
0x180008bc1  mov     [rsp+108h+var_70], rbx
0x180008bc9  mov     rcx, [rsp+108h+var_D8]
0x180008bce  mov     rax, [rcx]
0x180008bd1  lea     r8, [rsp+108h+var_88]
0x180008bd9  mov     rdx, r15
0x180008bdc  mov     rax, [rax+30h]
0x180008be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be5  mov     rcx, [rsp+108h]; this
0x180008bed  test    eax, eax
0x180008bef  js      loc_180008F06
0x180008bf5  mov     rcx, [rsp+108h+var_D8]
0x180008bfa  mov     rax, [rcx]
0x180008bfd  lea     r8, [rsp+108h+var_80]
0x180008c05  mov     rdx, rdi
0x180008c08  mov     rax, [rax+70h]
0x180008c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c11  mov     rcx, [rsp+108h]; this
0x180008c19  test    eax, eax
0x180008c1b  js      loc_180008F13
0x180008c21  mov     rcx, [rsp+108h+var_D8]
0x180008c26  mov     rax, [rcx]
0x180008c29  lea     r8, [rsp+108h+var_78]
0x180008c31  mov     rdx, rbx
0x180008c34  mov     rax, [rax+60h]
0x180008c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3d  mov     rcx, [rsp+108h]; this
0x180008c45  test    eax, eax
0x180008c47  js      loc_180008F20
0x180008c4d  mov     rcx, [rsp+108h+var_D8]
0x180008c52  mov     rax, [rcx]
0x180008c55  mov     rax, [rax+88h]
0x180008c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c61  mov     rcx, [rsp+108h]; this
0x180008c69  test    eax, eax
0x180008c6b  js      loc_180008F2D
0x180008c71  xor     r8d, r8d; bAlertable
0x180008c74  mov     edx, 7530h; dwMilliseconds
0x180008c79  mov     rcx, [rsp+108h+hHandle]; hHandle
0x180008c7e  call    cs:__imp_WaitForSingleObjectEx
0x180008c85  nop     dword ptr [rax+rax+00h]
0x180008c8a  mov     rcx, [rsp+108h+var_D8]
0x180008c8f  mov     rax, [rcx]
0x180008c92  mov     rax, [rax+90h]
0x180008c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9e  nop
0x180008c9f  test    rbx, rbx
0x180008ca2  jz      short loc_180008CB4
0x180008ca4  mov     rax, [rbx]
0x180008ca7  mov     rcx, rbx
0x180008caa  mov     rax, [rax+10h]
0x180008cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb3  nop
0x180008cb4  test    rdi, rdi
0x180008cb7  jz      short loc_180008CC9
0x180008cb9  mov     rax, [rdi]
0x180008cbc  mov     rcx, rdi
0x180008cbf  mov     rax, [rax+10h]
0x180008cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc8  nop
0x180008cc9  test    r15, r15
0x180008ccc  jz      short loc_180008CDE
0x180008cce  mov     rax, [r15]
0x180008cd1  mov     rcx, r15
0x180008cd4  mov     rax, [rax+10h]
0x180008cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdd  nop
0x180008cde  mov     rcx, [rsp+108h+var_D8]
0x180008ce3  test    rcx, rcx
0x180008ce6  jz      short loc_180008CFA
0x180008ce8  mov     [rsp+108h+var_D8], r14
0x180008ced  mov     rax, [rcx]
0x180008cf0  mov     rax, [rax+10h]
0x180008cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf9  nop
0x180008cfa  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180008d01  mov     [rsp+108h+var_B8], rax
0x180008d06  cmp     [rsp+108h+hHandle], r14
0x180008d0b  jz      short loc_180008D24
0x180008d0d  lea     rcx, [rsp+108h+var_B8]
0x180008d12  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180008d17  test    al, al
  ... truncated ...
```
