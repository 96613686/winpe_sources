# GetBluetoothRadioCount

- ea: `0x180008f80`
- end: `0x180009668`
- name: `GetBluetoothRadioCount`
- size: `1768`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017dc`
- `0x180005d90`
- `0x180006280`
- `0x180006c6c`
- `0x180008130`
- `0x180008f80`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CreateEventExA` at `0x180009148`
- `KERNEL32!CreateEventExA` at `0x180009148`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009443`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009443`
- `KERNEL32!GetLastError` at `0x18000916f`
- `KERNEL32!GetLastError` at `0x180009647`
- `KERNEL32!GetLastError` at `0x18000916f`
- `KERNEL32!GetLastError` at `0x180009647`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000954f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180009569`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000954f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180009569`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008fbd`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008fbd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009058`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009058`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800090c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800091cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800090c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800091cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=1
__int64 __fastcall GetBluetoothRadioCount(_DWORD *a1)
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
  __int64 v46; // rcx
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  _QWORD *v49; // rcx
  signed int v51; // eax
  int v52; // edx
  unsigned int v53; // r8d
  int v54; // [rsp+20h] [rbp-D8h]
  __int64 v55; // [rsp+30h] [rbp-C8h] BYREF
  _QWORD *v56; // [rsp+38h] [rbp-C0h] BYREF
  int v57; // [rsp+40h] [rbp-B8h] BYREF
  _QWORD *v58; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v59; // [rsp+50h] [rbp-A8h] BYREF
  void **v60; // [rsp+58h] [rbp-A0h] BYREF
  HANDLE hHandle; // [rsp+60h] [rbp-98h]
  int v62; // [rsp+68h] [rbp-90h]
  __int64 v63; // [rsp+70h] [rbp-88h] BYREF
  _QWORD *v64; // [rsp+78h] [rbp-80h] BYREF
  _QWORD *v65; // [rsp+80h] [rbp-78h] BYREF
  _QWORD *v66; // [rsp+88h] [rbp-70h]
  _QWORD *v67; // [rsp+90h] [rbp-68h]
  _DWORD *v68; // [rsp+98h] [rbp-60h]
  _QWORD *v69; // [rsp+A0h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v68 = a1;
  v1 = RoInitialize(1);
  v62 = v1;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v57 = 0;
  v56 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Enumeration.DeviceInformation", 0x2Du, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
LABEL_54:
    wil::details::in1diag3::_Throw_Hr(v7, (void *)0xC1, v6, (const char *)(unsigned int)ActivationFactory, v54);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v56);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_54;
  string = 0;
  v58 = 0;
  v8 = Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(&v58);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xC5, v9, (const char *)(unsigned int)v8, v54);
  v10 = v58;
  v11 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v58;
  string = 0;
  v12 = WindowsCreateStringReference(L"System.Devices.DeviceInstanceId", 0x1Fu, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
LABEL_57:
    wil::details::in1diag3::_Throw_Hr(v17, (void *)0xC6, v16, (const char *)(unsigned int)v15, v54);
  }
  v15 = ((__int64 (__fastcall **)(_QWORD *, GUID *, HSTRING))v11)[11](v10, 0, string);
  v17 = retaddr;
  if ( v15 < 0 )
    goto LABEL_57;
  string = 0;
  v59 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v58)(
          v58,
          &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e,
          &v59);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xC9, v19, (const char *)(unsigned int)v18, v54);
  hHandle = CreateEventExA(0, 0, 1u, 0x1F0003u);
  v60 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
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
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xCC, v20, (const char *)(unsigned int)LastError, v54);
  v55 = 0;
  v22 = v56;
  v23 = *v56;
  v24 = v59;
  string = 0;
  v25 = WindowsCreateStringReference(
          L"System.Devices.InterfaceClassGuid:=\"{92383B0E-F90E-4AC9-8D44-8C2D0D0EBDA2}\"",
          0x4Bu,
          &hstringHeader,
          &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
LABEL_61:
    wil::details::in1diag3::_Throw_Hr(v30, (void *)0xD3, v29, (const char *)(unsigned int)v28, v54);
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, __int64 *))(v23 + 120))(v22, string, v24, &v55);
  v30 = retaddr;
  if ( v28 < 0 )
    goto LABEL_61;
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
    v32[2] = &v57;
    *v32 = off_18000C310;
  }
  else
  {
    v32 = 0;
  }
  v69 = v32;
  v33 = v63;
  v66 = v64;
  v67 = v65;
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
    v35[2] = &v60;
    v35[3] = v33;
    v35[4] = v66;
    v35[5] = v67;
    *v35 = off_18000C2E8;
  }
  else
  {
    v35 = 0;
  }
  v67 = v35;
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
    v37[2] = &v60;
    *v37 = off_18000C270;
  }
  else
  {
    v37 = 0;
  }
  v66 = v37;
  v38 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v55 + 48LL))(v55, v32, &v63);
  if ( v38 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x124, v39, (const char *)(unsigned int)v38, v54);
  v40 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v55 + 112LL))(v55, v35, &v64);
  if ( v40 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x125, v41, (const char *)(unsigned int)v40, v54);
  v42 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD **))(*(_QWORD *)v55 + 96LL))(v55, v37, &v65);
  if ( v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x126, v43, (const char *)(unsigned int)v42, v54);
  v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 136LL))(v55);
  if ( v44 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x128, v45, (const char *)(unsigned int)v44, v54);
  WaitForSingleObjectEx(hHandle, 0x7530u, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 144LL))(v55);
  if ( v37 )
    (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
  if ( v35 )
    (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
  if ( v32 )
    (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
  v46 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v60 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v60) )
    {
      v51 = GetLastError();
      if ( v51 > 0 )
        v51 = (unsigned __int16)v51 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v51, v52, v53);
      JUMPOUT(0x180009666LL);
    }
    hHandle = 0;
  }
  v47 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
  }
  v49 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
  }
  *v68 = v57;
  if ( v1 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180008f80  mov     [rsp+arg_8], rbx
0x180008f85  mov     [rsp+arg_10], rsi
0x180008f8a  push    rdi
0x180008f8b  push    r12
0x180008f8d  push    r13
0x180008f8f  push    r14
0x180008f91  push    r15
0x180008f93  sub     rsp, 0D0h
0x180008f9a  mov     rax, cs:__security_cookie
0x180008fa1  xor     rax, rsp
0x180008fa4  mov     [rsp+0F8h+var_30], rax
0x180008fac  mov     [rsp+0F8h+var_60], rcx
0x180008fb4  mov     r13d, 1
0x180008fba  mov     ecx, r13d
0x180008fbd  call    cs:__imp_RoInitialize
0x180008fc4  nop     dword ptr [rax+rax+00h]
0x180008fc9  mov     esi, eax
0x180008fcb  mov     [rsp+0F8h+var_90], eax
0x180008fcf  xor     r14d, r14d
0x180008fd2  mov     [rsp+0F8h+var_88], r14
0x180008fd7  mov     [rsp+0F8h+var_80], r14
0x180008fdc  mov     [rsp+0F8h+var_78], r14
0x180008fe4  mov     [rsp+0F8h+var_B8], r14d
0x180008fe9  mov     [rsp+0F8h+var_C0], r14
0x180008fee  mov     [rsp+0F8h+string], r14
0x180008ff6  lea     r9, [rsp+0F8h+string]; string
0x180008ffe  lea     r8, [rsp+0F8h+hstringHeader]; hstringHeader
0x180009006  lea     edx, [r13+2Ch]; length
0x18000900a  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x180009011  call    cs:__imp_WindowsCreateStringReference
0x180009018  nop     dword ptr [rax+rax+00h]
0x18000901d  test    eax, eax
0x18000901f  js      loc_1800095A7
0x180009025  mov     rbx, [rsp+0F8h+string]
0x18000902d  mov     rcx, [rsp+0F8h+var_C0]
0x180009032  test    rcx, rcx
0x180009035  jz      short loc_180009049
0x180009037  mov     [rsp+0F8h+var_C0], r14
0x18000903c  mov     rax, [rcx]
0x18000903f  mov     rax, [rax+10h]
0x180009043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009048  nop
0x180009049  lea     r8, [rsp+0F8h+var_C0]
0x18000904e  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x180009055  mov     rcx, rbx
0x180009058  call    cs:__imp_RoGetActivationFactory
0x18000905f  nop     dword ptr [rax+rax+00h]
0x180009064  mov     rcx, [rsp+0F8h]
0x18000906c  test    eax, eax
0x18000906e  js      loc_1800095AF
0x180009074  mov     [rsp+0F8h+string], r14
0x18000907c  mov     [rsp+0F8h+var_B0], r14
0x180009081  lea     rcx, [rsp+0F8h+var_B0]
0x180009086  call    ?Make@?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18000908b  mov     rcx, [rsp+0F8h]; this
0x180009093  test    eax, eax
0x180009095  js      loc_1800095BD
0x18000909b  mov     rbx, [rsp+0F8h+var_B0]
0x1800090a0  mov     rdi, [rbx]
0x1800090a3  mov     [rsp+0F8h+string], r14
0x1800090ab  lea     r9, [rsp+0F8h+string]; string
0x1800090b3  lea     r8, [rsp+0F8h+hstringHeader]; hstringHeader
0x1800090bb  mov     edx, 1Fh; length
0x1800090c0  lea     rcx, sourceString; "System.Devices.DeviceInstanceId"
0x1800090c7  call    cs:__imp_WindowsCreateStringReference
0x1800090ce  nop     dword ptr [rax+rax+00h]
0x1800090d3  test    eax, eax
0x1800090d5  js      loc_1800095CA
0x1800090db  mov     r8, [rsp+0F8h+string]
0x1800090e3  xor     edx, edx
0x1800090e5  mov     rcx, rbx
0x1800090e8  mov     rax, [rdi+58h]
0x1800090ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f1  mov     rcx, [rsp+0F8h]
0x1800090f9  test    eax, eax
0x1800090fb  js      loc_1800095D2
0x180009101  mov     [rsp+0F8h+string], r14
0x180009109  mov     [rsp+0F8h+var_A8], r14
0x18000910e  mov     rcx, [rsp+0F8h+var_B0]
0x180009113  mov     rax, [rcx]
0x180009116  lea     r8, [rsp+0F8h+var_A8]
0x18000911b  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x180009122  mov     rax, [rax]
0x180009125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912a  nop
0x18000912b  mov     rcx, [rsp+0F8h]; this
0x180009133  test    eax, eax
0x180009135  js      loc_1800095E0
0x18000913b  mov     r9d, 1F0003h; dwDesiredAccess
0x180009141  mov     r8d, r13d; dwFlags
0x180009144  xor     edx, edx; lpName
0x180009146  xor     ecx, ecx; lpEventAttributes
0x180009148  call    cs:__imp_CreateEventExA
0x18000914f  nop     dword ptr [rax+rax+00h]
0x180009154  mov     [rsp+0F8h+hHandle], rax
0x180009159  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180009160  mov     [rsp+0F8h+var_A0], rcx
0x180009165  test    rax, rax
0x180009168  jz      short loc_18000916F
0x18000916a  mov     eax, r14d
0x18000916d  jmp     short loc_180009187
0x18000916f  call    cs:__imp_GetLastError
0x180009176  nop     dword ptr [rax+rax+00h]
0x18000917b  test    eax, eax
0x18000917d  jle     short loc_180009187
0x18000917f  movzx   eax, ax
0x180009182  or      eax, 80070000h
0x180009187  mov     rcx, [rsp+0F8h]; this
0x18000918f  test    eax, eax
0x180009191  js      loc_1800095EE
0x180009197  mov     [rsp+0F8h+var_C8], r14
0x18000919c  mov     rbx, [rsp+0F8h+var_C0]
0x1800091a1  mov     rdi, [rbx]
0x1800091a4  mov     r15, [rsp+0F8h+var_A8]
0x1800091a9  mov     [rsp+0F8h+string], r14
0x1800091b1  lea     r9, [rsp+0F8h+string]; string
0x1800091b9  lea     r8, [rsp+0F8h+hstringHeader]; hstringHeader
0x1800091c1  mov     edx, 4Bh ; 'K'; length
0x1800091c6  lea     rcx, aSystemDevicesI; "System.Devices.InterfaceClassGuid:=\"{9"...
0x1800091cd  call    cs:__imp_WindowsCreateStringReference
0x1800091d4  nop     dword ptr [rax+rax+00h]
0x1800091d9  test    eax, eax
0x1800091db  js      loc_1800095FC
0x1800091e1  lea     r9, [rsp+0F8h+var_C8]
0x1800091e6  mov     r8, r15
0x1800091e9  mov     rdx, [rsp+0F8h+string]
0x1800091f1  mov     rcx, rbx
0x1800091f4  mov     rax, [rdi+78h]
0x1800091f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091fd  mov     rcx, [rsp+0F8h]
0x180009205  test    eax, eax
0x180009207  js      loc_180009604
0x18000920d  mov     [rsp+0F8h+string], r14
0x180009215  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000921c  mov     ecx, 18h; unsigned __int64
0x180009221  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009226  mov     r15, rax
0x180009229  test    rax, rax
0x18000922c  jz      short loc_180009274
0x18000922e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180009235  mov     [r15], rax
0x180009238  mov     [r15+0Ch], r13d
0x18000923c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAVDeviceInformation@234@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,Windows::Devices::Enumeration::DeviceInformation *>>::`vftable'
0x180009243  mov     [r15], rax
0x180009246  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000924d  test    rcx, rcx
0x180009250  jz      short loc_18000925F
0x180009252  mov     rax, [rcx]
0x180009255  mov     rax, [rax+8]
0x180009259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000925e  nop
0x18000925f  lea     rax, [rsp+0F8h+var_B8]
0x180009264  mov     [r15+10h], rax
0x180009268  lea     rax, off_18000C310
0x18000926f  mov     [r15], rax
0x180009272  jmp     short loc_180009277
0x180009274  mov     r15, r14
0x180009277  mov     [rsp+0F8h+var_58], r15
0x18000927f  mov     rbx, [rsp+0F8h+var_88]
0x180009284  mov     rax, [rsp+0F8h+var_80]
0x180009289  mov     [rsp+0F8h+var_70], rax
0x180009291  mov     rax, [rsp+0F8h+var_78]
0x180009299  mov     [rsp+0F8h+var_68], rax
0x1800092a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800092a8  mov     ecx, 30h ; '0'; unsigned __int64
0x1800092ad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800092b2  mov     rdi, rax
0x1800092b5  test    rax, rax
0x1800092b8  jz      short loc_18000931C
0x1800092ba  lea     r12, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x1800092c1  mov     [rax], r12
0x1800092c4  mov     [rax+0Ch], r13d
0x1800092c8  lea     r13, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable'
0x1800092cf  mov     [rax], r13
0x1800092d2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800092d9  test    rcx, rcx
0x1800092dc  jz      short loc_1800092EB
0x1800092de  mov     rax, [rcx]
0x1800092e1  mov     rax, [rax+8]
0x1800092e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ea  nop
0x1800092eb  lea     rax, [rsp+0F8h+var_A0]
0x1800092f0  mov     [rdi+10h], rax
0x1800092f4  mov     [rdi+18h], rbx
0x1800092f8  mov     rax, [rsp+0F8h+var_70]
0x180009300  mov     [rdi+20h], rax
0x180009304  mov     rax, [rsp+0F8h+var_68]
0x18000930c  mov     [rdi+28h], rax
0x180009310  lea     rax, off_18000C2E8
0x180009317  mov     [rdi], rax
0x18000931a  jmp     short loc_18000932D
0x18000931c  mov     rdi, r14
0x18000931f  lea     r12, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180009326  lea     r13, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVDeviceWatcher@Enumeration@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Enumeration::DeviceWatcher *,IInspectable *>>::`vftable'
0x18000932d  mov     [rsp+0F8h+var_68], rdi
0x180009335  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000933c  mov     ecx, 18h; unsigned __int64
0x180009341  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009346  mov     rbx, rax
0x180009349  test    rax, rax
0x18000934c  jz      short loc_180009389
0x18000934e  mov     [rax], r12
0x180009351  mov     dword ptr [rax+0Ch], 1
0x180009358  mov     [rax], r13
0x18000935b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009362  test    rcx, rcx
0x180009365  jz      short loc_180009374
0x180009367  mov     rax, [rcx]
0x18000936a  mov     rax, [rax+8]
0x18000936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009373  nop
0x180009374  lea     rax, [rsp+0F8h+var_A0]
0x180009379  mov     [rbx+10h], rax
0x18000937d  lea     rax, off_18000C270
0x180009384  mov     [rbx], rax
0x180009387  jmp     short loc_18000938C
0x180009389  mov     rbx, r14
0x18000938c  mov     [rsp+0F8h+var_70], rbx
0x180009394  mov     rcx, [rsp+0F8h+var_C8]
0x180009399  mov     rax, [rcx]
0x18000939c  lea     r8, [rsp+0F8h+var_88]
0x1800093a1  mov     rdx, r15
0x1800093a4  mov     rax, [rax+30h]
0x1800093a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ad  mov     rcx, [rsp+0F8h]; this
0x1800093b5  test    eax, eax
0x1800093b7  js      loc_180009612
0x1800093bd  mov     rcx, [rsp+0F8h+var_C8]
0x1800093c2  mov     rax, [rcx]
0x1800093c5  lea     r8, [rsp+0F8h+var_80]
0x1800093ca  mov     rdx, rdi
0x1800093cd  mov     rax, [rax+70h]
0x1800093d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d6  mov     rcx, [rsp+0F8h]; this
0x1800093de  test    eax, eax
0x1800093e0  js      loc_18000961F
0x1800093e6  mov     rcx, [rsp+0F8h+var_C8]
0x1800093eb  mov     rax, [rcx]
0x1800093ee  lea     r8, [rsp+0F8h+var_78]
0x1800093f6  mov     rdx, rbx
0x1800093f9  mov     rax, [rax+60h]
0x1800093fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009402  mov     rcx, [rsp+0F8h]; this
0x18000940a  test    eax, eax
0x18000940c  js      loc_18000962C
0x180009412  mov     rcx, [rsp+0F8h+var_C8]
0x180009417  mov     rax, [rcx]
0x18000941a  mov     rax, [rax+88h]
0x180009421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009426  mov     rcx, [rsp+0F8h]; this
0x18000942e  test    eax, eax
0x180009430  js      loc_180009639
0x180009436  xor     r8d, r8d; bAlertable
0x180009439  mov     edx, 7530h; dwMilliseconds
0x18000943e  mov     rcx, [rsp+0F8h+hHandle]; hHandle
0x180009443  call    cs:__imp_WaitForSingleObjectEx
0x18000944a  nop     dword ptr [rax+rax+00h]
0x18000944f  mov     rcx, [rsp+0F8h+var_C8]
0x180009454  mov     rax, [rcx]
0x180009457  mov     rax, [rax+90h]
0x18000945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009463  nop
0x180009464  test    rbx, rbx
0x180009467  jz      short loc_180009479
0x180009469  mov     rax, [rbx]
0x18000946c  mov     rcx, rbx
0x18000946f  mov     rax, [rax+10h]
0x180009473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009478  nop
0x180009479  test    rdi, rdi
0x18000947c  jz      short loc_18000948E
0x18000947e  mov     rax, [rdi]
0x180009481  mov     rcx, rdi
0x180009484  mov     rax, [rax+10h]
0x180009488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000948d  nop
0x18000948e  test    r15, r15
0x180009491  jz      short loc_1800094A3
0x180009493  mov     rax, [r15]
0x180009496  mov     rcx, r15
0x180009499  mov     rax, [rax+10h]
0x18000949d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094a2  nop
0x1800094a3  mov     rcx, [rsp+0F8h+var_C8]
0x1800094a8  test    rcx, rcx
0x1800094ab  jz      short loc_1800094BF
0x1800094ad  mov     [rsp+0F8h+var_C8], r14
0x1800094b2  mov     rax, [rcx]
0x1800094b5  mov     rax, [rax+10h]
0x1800094b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094be  nop
0x1800094bf  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800094c6  mov     [rsp+0F8h+var_A0], rax
0x1800094cb  cmp     [rsp+0F8h+hHandle], r14
0x1800094d0  jz      short loc_1800094E9
0x1800094d2  lea     rcx, [rsp+0F8h+var_A0]
0x1800094d7  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800094dc  test    al, al
0x1800094de  jz      loc_180009647
0x1800094e4  mov     [rsp+0F8h+hHandle], r14
  ... truncated ...
```
