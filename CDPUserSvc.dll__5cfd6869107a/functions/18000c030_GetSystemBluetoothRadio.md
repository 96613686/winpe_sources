# GetSystemBluetoothRadio

- ea: `0x18000c030`
- end: `0x18000c234`
- name: `GetSystemBluetoothRadio`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be20`
- `0x18000bebc`

## callees

- `0x180003678`
- `0x18000c030`
- `0x18000c23c`
- `0x18001fa48`
- `0x180021ad8`
- `0x18002c570`
- `0x180041054`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c092`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c07c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c0b7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c0b7`

## string_xrefs

- `0x18000c0cc`: `onecoreuap\windows\cdp\common\internal\winshared\BluetoothRadioHelpers.h`
- `0x18000c158`: `onecoreuap\windows\cdp\common\internal\winshared\BluetoothRadioHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall GetSystemBluetoothRadio(__int64 *a1)
{
  HRESULT v2; // eax
  HSTRING v3; // rbx
  int ActivationFactory; // eax
  int i; // eax
  _QWORD *v6; // rbx
  int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v13; // [rsp+28h] [rbp-60h] BYREF
  int v14[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-48h]
  __int64 v17; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+50h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-30h] BYREF
  HSTRING string; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v13 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Radios.Radio", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
    RaiseException(v2, 1u, 0, 0);
  v3 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4, &v13);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\winshared\\BluetoothRadioHelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      v12[0]);
  ___call_and_wait_for_completion_UIRadioStatics_Radios_Devices_Windows__PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVRadio_Radios_Devices_Windows___Collections_Foundation_Windows___Foundation_4___Z__V_wil__YA_A_PPEAUIRadioStatics_Radios_Devices_Windows__P81234_EAAJPEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVRadio_Radios_Devices_Windows___Collections_Foundation_Windows___Foundation_4__Z_Z(
    (__int64)v14,
    v13);
  *(_QWORD *)v12 = *(_QWORD *)v14;
  v15 = *(_QWORD *)v14;
  v16 = 0;
  v17 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>,wil::err_exception_policy>::end(
    v12,
    &hstringHeader);
  for ( i = v16; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v16 )
  {
    v6 = (_QWORD *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>,wil::err_exception_policy>::vector_iterator::operator*(&v15);
    v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v6 + 88LL))(*v6, v12);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\winshared\\BluetoothRadioHelpers.h",
        (const char *)(unsigned int)v7,
        v12[0]);
    if ( v12[0] == 3 )
    {
      v8 = *v6;
      if ( *a1 != v8 )
      {
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        v18 = *a1;
        *a1 = v8;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      }
      break;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v9 = *(_QWORD *)v14;
  if ( *(_QWORD *)v14 )
  {
    *(_QWORD *)v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c030  mov     [rsp+arg_8], rbx
0x18000c035  push    rdi
0x18000c036  sub     rsp, 80h
0x18000c03d  mov     rax, cs:__security_cookie
0x18000c044  xor     rax, rsp
0x18000c047  mov     [rsp+88h+var_10], rax
0x18000c04c  mov     rdi, rcx
0x18000c04f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c054  mov     [rsp+88h+var_60], 0
0x18000c05d  mov     [rsp+88h+string], 0
0x18000c066  lea     r9, [rsp+88h+string]; string
0x18000c06b  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x18000c070  mov     edx, 1Ch; length
0x18000c075  lea     rcx, ?RuntimeClass_Windows_Devices_Radios_Radio@@3QBGB; "Windows.Devices.Radios.Radio"
0x18000c07c  call    cs:__imp_WindowsCreateStringReference
0x18000c082  test    eax, eax
0x18000c084  jns     short loc_18000C099
0x18000c086  xor     r9d, r9d; lpArguments
0x18000c089  xor     r8d, r8d; nNumberOfArguments
0x18000c08c  lea     edx, [r9+1]; dwExceptionFlags
0x18000c090  mov     ecx, eax; dwExceptionCode
0x18000c092  call    cs:__imp_RaiseException
0x18000c098  nop
0x18000c099  mov     rbx, [rsp+88h+string]
0x18000c09e  lea     rcx, [rsp+88h+var_60]
0x18000c0a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c0a8  lea     r8, [rsp+88h+var_60]
0x18000c0ad  lea     rdx, _GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4
0x18000c0b4  mov     rcx, rbx
0x18000c0b7  call    cs:__imp_RoGetActivationFactory
0x18000c0bd  mov     rcx, [rsp+88h]; this
0x18000c0c5  test    eax, eax
0x18000c0c7  jns     short loc_18000C0DE
0x18000c0c9  mov     r9d, eax; char *
0x18000c0cc  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000c0d3  mov     edx, 11h; void *
0x18000c0d8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c0de  mov     rdx, [rsp+88h+var_60]
0x18000c0e3  lea     rcx, [rsp+88h+var_58]
0x18000c0e8  call    ??$call_and_wait_for_completion@UIRadioStatics@Radios@Devices@Windows@@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@4@$$Z$$V@wil@@YA?A_PPEAUIRadioStatics@Radios@Devices@Windows@@P81234@EAAJPEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@4@@Z@Z
0x18000c0ed  nop
0x18000c0ee  mov     rax, qword ptr [rsp+88h+var_58]
0x18000c0f3  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000c0f8  mov     [rsp+88h+var_50], rax
0x18000c0fd  mov     [rsp+88h+var_48], 0
0x18000c105  mov     [rsp+88h+var_40], 0
0x18000c10e  lea     rdx, [rsp+88h+hstringHeader]
0x18000c113  lea     rcx, [rsp+88h+var_68]
0x18000c118  call    ?end@?$vector_range@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>,wil::err_exception_policy>::end(void)
0x18000c11d  nop
0x18000c11e  mov     eax, [rsp+88h+var_48]
0x18000c122  cmp     eax, dword ptr [rsp+88h+hstringHeader.Reserved+8]
0x18000c126  jz      short loc_18000C1A7
0x18000c128  lea     rcx, [rsp+88h+var_50]
0x18000c12d  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIRadio@Radios@Devices@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18000c132  mov     rbx, rax
0x18000c135  mov     rcx, [rax]
0x18000c138  mov     rdx, [rcx]
0x18000c13b  mov     rax, [rdx+58h]
0x18000c13f  lea     rdx, [rsp+88h+var_68]
0x18000c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c149  mov     rcx, [rsp+88h]; this
0x18000c151  test    eax, eax
0x18000c153  jns     short loc_18000C169
0x18000c155  mov     r9d, eax; char *
0x18000c158  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000c15f  mov     edx, 1Ah; void *
0x18000c164  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c169  cmp     [rsp+88h+var_68], 3
0x18000c16e  jnz     loc_18000C223
0x18000c174  mov     rbx, [rbx]
0x18000c177  cmp     [rdi], rbx
0x18000c17a  jz      short loc_18000C1A7
0x18000c17c  test    rbx, rbx
0x18000c17f  jz      short loc_18000C191
0x18000c181  mov     rax, [rbx]
0x18000c184  mov     rcx, rbx
0x18000c187  mov     rax, [rax+8]
0x18000c18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c190  nop
0x18000c191  mov     rax, [rdi]
0x18000c194  mov     [rsp+88h+var_38], rax
0x18000c199  mov     [rdi], rbx
0x18000c19c  lea     rcx, [rsp+88h+var_38]
0x18000c1a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c1a6  nop
0x18000c1a7  lea     rcx, [rsp+88h+hstringHeader.Reserved+10h]
0x18000c1ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c1b1  nop
0x18000c1b2  lea     rcx, [rsp+88h+var_40]
0x18000c1b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c1bc  nop
0x18000c1bd  mov     rcx, qword ptr [rsp+88h+var_58]
0x18000c1c2  test    rcx, rcx
0x18000c1c5  jz      short loc_18000C1DD
0x18000c1c7  mov     qword ptr [rsp+88h+var_58], 0
0x18000c1d0  mov     rax, [rcx]
0x18000c1d3  mov     rax, [rax+10h]
0x18000c1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1dc  nop
0x18000c1dd  mov     rcx, [rsp+88h+var_60]
0x18000c1e2  test    rcx, rcx
0x18000c1e5  jz      short loc_18000C1FD
0x18000c1e7  mov     [rsp+88h+var_60], 0
0x18000c1f0  mov     rax, [rcx]
0x18000c1f3  mov     rax, [rax+10h]
0x18000c1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1fc  nop
0x18000c1fd  xor     eax, eax
0x18000c1ff  jmp     short loc_18000C205
0x18000c201  mov     eax, [rsp+88h+var_68]
0x18000c205  mov     rcx, [rsp+88h+var_10]
0x18000c20a  xor     rcx, rsp; StackCookie
0x18000c20d  call    __security_check_cookie
0x18000c212  mov     rbx, [rsp+88h+arg_8]
0x18000c21a  add     rsp, 80h
0x18000c221  pop     rdi
0x18000c222  retn
0x18000c223  mov     eax, [rsp+88h+var_48]
0x18000c227  inc     eax
0x18000c229  mov     [rsp+88h+var_48], eax
0x18000c22d  jmp     loc_18000C122
```
