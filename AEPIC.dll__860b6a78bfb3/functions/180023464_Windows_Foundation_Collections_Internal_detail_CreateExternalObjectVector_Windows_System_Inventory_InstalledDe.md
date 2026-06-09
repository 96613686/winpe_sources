# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Inventory::InstalledDesktopApp,Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> * *)

- ea: `0x180023464`
- end: `0x1800235ff`
- name: `??$CreateExternalObjectVector@VInstalledDesktopApp@Inventory@System@Windows@@V?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@1234@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023250`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x1800231f0`
- `0x180023464`
- `0x1800245b4`
- `0x1800252b0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023579`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023579`

## string_xrefs

- `0x1800234c0`: `Windows.Foundation.Collections.IIterator`1<Windows.System.Inventory.InstalledDesktopApp>`
- `0x1800234a6`: `Windows.Foundation.Collections.IVectorView`1<Windows.System.Inventory.InstalledDesktopApp>`
- `0x18002348c`: `Windows.Foundation.Collections.IVector`1<Windows.System.Inventory.InstalledDesktopApp>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Inventory::InstalledDesktopApp,Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v11; // [rsp+58h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-98h]
  GUID v13; // [rsp+78h] [rbp-88h]
  GUID v14; // [rsp+88h] [rbp-78h]
  GUID v15; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  _BYTE v18[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  _BYTE v20[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  _BYTE v22[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v9[0] = L"Windows.Foundation.Collections.IVector`1<Windows.System.Inventory.InstalledDesktopApp>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, v9);
  v9[0] = L"Windows.Foundation.Collections.IVectorView`1<Windows.System.Inventory.InstalledDesktopApp>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, v9);
  v9[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.System.Inventory.InstalledDesktopApp>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, v9);
  v10[0] = v19;
  v10[1] = v21;
  v10[2] = v23;
  v11 = GUID_75eab8ed_c0bc_5364_4c28_166e0545167a;
  v12 = GUID_f6e390c4_611f_594e_98f0_86e8f13c541b;
  v13 = GUID_ba3a2146_42dd_5fa8_a7f0_36b6973803b5;
  v14 = GUID_b64037f2_dc1a_57de_8b03_18a16f9ddbdf;
  v15 = GUID_af3da06d_0a82_5213_9cb5_f8d2da12fbe9;
  v8 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v4 = v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v4, v10, &v7);
    if ( ActivationFactory >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180023464  mov     [rsp-8+arg_0], rbx
0x180023469  mov     [rsp-8+arg_10], rdi
0x18002346e  push    rbp
0x18002346f  lea     rbp, [rsp-40h]
0x180023474  sub     rsp, 140h
0x18002347b  mov     rax, cs:__security_cookie
0x180023482  xor     rax, rsp
0x180023485  mov     [rbp+40h+var_10], rax
0x180023489  mov     rdi, rdx
0x18002348c  lea     rax, aWindowsFoundat_3; "Windows.Foundation.Collections.IVector`"...
0x180023493  mov     [rsp+140h+var_110], rax
0x180023498  lea     rdx, [rsp+140h+var_110]
0x18002349d  lea     rcx, [rbp+40h+var_70]
0x1800234a1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800234a6  lea     rax, aWindowsFoundat_2; "Windows.Foundation.Collections.IVectorV"...
0x1800234ad  mov     [rsp+140h+var_110], rax
0x1800234b2  lea     rdx, [rsp+140h+var_110]
0x1800234b7  lea     rcx, [rbp+40h+var_50]
0x1800234bb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800234c0  lea     rax, aWindowsFoundat_4; "Windows.Foundation.Collections.IIterato"...
0x1800234c7  mov     [rsp+140h+var_110], rax
0x1800234cc  lea     rdx, [rsp+140h+var_110]
0x1800234d1  lea     rcx, [rbp+40h+var_30]
0x1800234d5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800234da  mov     rax, [rbp+40h+var_58]
0x1800234de  mov     [rsp+140h+var_100], rax
0x1800234e3  mov     rax, [rbp+40h+var_38]
0x1800234e7  mov     [rsp+140h+var_F8], rax
0x1800234ec  mov     rax, [rbp+40h+var_18]
0x1800234f0  mov     [rsp+140h+var_F0], rax
0x1800234f5  movups  xmm0, xmmword ptr cs:_GUID_75eab8ed_c0bc_5364_4c28_166e0545167a.Data1
0x1800234fc  movdqu  [rsp+140h+var_E8], xmm0
0x180023502  movups  xmm1, xmmword ptr cs:_GUID_f6e390c4_611f_594e_98f0_86e8f13c541b.Data1
0x180023509  movdqu  [rsp+140h+var_D8], xmm1
0x18002350f  movups  xmm0, xmmword ptr cs:_GUID_ba3a2146_42dd_5fa8_a7f0_36b6973803b5.Data1
0x180023516  movdqu  [rsp+140h+var_C8], xmm0
0x18002351c  movups  xmm1, xmmword ptr cs:_GUID_b64037f2_dc1a_57de_8b03_18a16f9ddbdf.Data1
0x180023523  movdqu  [rbp+40h+var_B8], xmm1
0x180023528  movups  xmm0, xmmword ptr cs:_GUID_af3da06d_0a82_5213_9cb5_f8d2da12fbe9.Data1
0x18002352f  movdqu  [rbp+40h+var_A8], xmm0
0x180023534  mov     [rsp+140h+var_118], 0
0x18002353d  lea     rcx, [rsp+140h+var_118]
0x180023542  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023547  mov     [rbp+40h+var_78], 0
0x18002354f  mov     r9d, 2Ch ; ','; unsigned int
0x180023555  lea     r8d, [r9+1]; unsigned int
0x180023559  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180023560  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180023564  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180023569  lea     r8, [rsp+140h+var_118]
0x18002356e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180023575  mov     rcx, [rbp+40h+var_78]
0x180023579  call    cs:__imp_RoGetActivationFactory
0x18002357f  mov     ebx, eax
0x180023581  test    eax, eax
0x180023583  js      short loc_1800235D2
0x180023585  mov     [rsp+140h+var_120], 0
0x18002358e  mov     rbx, [rsp+140h+var_118]
0x180023593  lea     rcx, [rsp+140h+var_120]
0x180023598  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002359d  lea     r8, [rsp+140h+var_120]
0x1800235a2  lea     rdx, [rsp+140h+var_100]
0x1800235a7  mov     rcx, rbx
0x1800235aa  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1800235af  mov     ebx, eax
0x1800235b1  test    eax, eax
0x1800235b3  js      short loc_1800235C8
0x1800235b5  mov     rax, [rsp+140h+var_120]
0x1800235ba  mov     [rsp+140h+var_120], 0
0x1800235c3  mov     [rdi], rax
0x1800235c6  xor     ebx, ebx
0x1800235c8  lea     rcx, [rsp+140h+var_120]
0x1800235cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800235d2  lea     rcx, [rsp+140h+var_118]
0x1800235d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800235dc  mov     eax, ebx
0x1800235de  mov     rcx, [rbp+40h+var_10]
0x1800235e2  xor     rcx, rsp; StackCookie
0x1800235e5  call    __security_check_cookie
0x1800235ea  lea     r11, [rsp+140h+var_s0]
0x1800235f2  mov     rbx, [r11+10h]
0x1800235f6  mov     rdi, [r11+20h]
0x1800235fa  mov     rsp, r11
0x1800235fd  pop     rbp
0x1800235fe  retn
```
