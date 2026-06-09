# SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x18001d170`
- end: `0x18001d246`
- name: `?SetProperty@CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `214`
- prototype: `int(SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067fc`
- `0x180019b18`
- `0x18001a1d0`
- `0x18001d170`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::SetProperty(
        HSTRING *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // ebx
  const unsigned __int16 *v8; // r8
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF
  struct IInspectable *v13; // [rsp+58h] [rbp+20h] BYREF

  v13 = a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v13);
  v12 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v12);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v12);
  if ( v7 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180035190, v8) )
    {
      v9 = v12;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 152LL);
      WindowsDeleteString(this[27]);
      this[27] = 0;
      v7 = v10(v9, this + 27);
    }
    else
    {
      v7 = -2147024809;
    }
  }
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d170  mov     [rsp+arg_0], rbx
0x18001d175  push    rbp
0x18001d176  push    rsi
0x18001d177  push    rdi
0x18001d178  sub     rsp, 20h
0x18001d17c  mov     rdi, r8
0x18001d17f  mov     rsi, rdx
0x18001d182  mov     rbp, rcx
0x18001d185  mov     [rsp+38h+arg_18], r8
0x18001d18a  lea     rcx, [rsp+38h+arg_18]
0x18001d18f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18001d194  nop
0x18001d195  mov     [rsp+38h+arg_10], 0
0x18001d19e  mov     rax, [rdi]
0x18001d1a1  mov     rbx, [rax]
0x18001d1a4  lea     rcx, [rsp+38h+arg_10]
0x18001d1a9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001d1ae  lea     r8, [rsp+38h+arg_10]
0x18001d1b3  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001d1ba  mov     rcx, rdi
0x18001d1bd  mov     rax, rbx
0x18001d1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c5  mov     ebx, eax
0x18001d1c7  test    eax, eax
0x18001d1c9  js      short loc_18001D221
0x18001d1cb  lea     rdx, stru_180035190; HSTRING
0x18001d1d2  mov     rcx, rsi; this
0x18001d1d5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001d1da  test    al, al
0x18001d1dc  jz      short loc_18001D21C
0x18001d1de  mov     rsi, [rsp+38h+arg_10]
0x18001d1e3  mov     rax, [rsi]
0x18001d1e6  mov     rdi, [rax+98h]
0x18001d1ed  lea     rbx, [rbp+0D8h]
0x18001d1f4  mov     rcx, [rbx]; string
0x18001d1f7  call    cs:__imp_WindowsDeleteString
0x18001d1fe  nop     dword ptr [rax+rax+00h]
0x18001d203  mov     qword ptr [rbx], 0
0x18001d20a  mov     rdx, rbx
0x18001d20d  mov     rcx, rsi
0x18001d210  mov     rax, rdi
0x18001d213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d218  mov     ebx, eax
0x18001d21a  jmp     short loc_18001D221
0x18001d21c  mov     ebx, 80070057h
0x18001d221  lea     rcx, [rsp+38h+arg_10]
0x18001d226  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001d22b  nop
0x18001d22c  lea     rcx, [rsp+38h+arg_18]
0x18001d231  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001d236  mov     eax, ebx
0x18001d238  mov     rbx, [rsp+38h+arg_0]
0x18001d23d  add     rsp, 20h
0x18001d241  pop     rdi
0x18001d242  pop     rsi
0x18001d243  pop     rbp
0x18001d244  retn
```
