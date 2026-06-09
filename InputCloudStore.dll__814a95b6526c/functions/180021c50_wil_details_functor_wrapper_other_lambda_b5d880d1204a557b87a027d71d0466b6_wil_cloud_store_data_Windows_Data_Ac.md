# wil::details::functor_wrapper_other<_lambda_b5d880d1204a557b87a027d71d0466b6_ &,wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>::Run(void)

- ea: `0x180021c50`
- end: `0x180021d25`
- name: `?Run@?$functor_wrapper_other@AEAV_lambda_b5d880d1204a557b87a027d71d0466b6_@@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@details@wil@@UEAAJXZ`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003560`
- `0x18001325c`
- `0x1800197b8`
- `0x18001b128`
- `0x18001b964`
- `0x18001b9f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::functor_wrapper_other<_lambda_b5d880d1204a557b87a027d71d0466b6_ &,wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>::Run(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  __int128 v5; // [rsp+38h] [rbp-51h] BYREF
  __int64 v6; // [rsp+48h] [rbp-41h]
  __int64 v7; // [rsp+50h] [rbp-39h]
  __int64 v8; // [rsp+58h] [rbp-31h] BYREF
  char v9; // [rsp+60h] [rbp-29h]
  char v10; // [rsp+61h] [rbp-28h]
  int v11; // [rsp+64h] [rbp-25h]
  char v12; // [rsp+68h] [rbp-21h]
  _BYTE v13[96]; // [rsp+70h] [rbp-19h] BYREF

  v2 = *(_QWORD *)(a1 + 8);
  wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
    (__int64)v13,
    **(_QWORD **)(v2 + 16));
  wil::cloud_store::call_load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
    *(_QWORD *)v2,
    (__int64)&v5,
    (__int64)v13,
    **(_DWORD **)(v2 + 8),
    v2 + 24);
  wil::cloud_store::validated_data_reference::~validated_data_reference((wil::cloud_store::validated_data_reference *)v13);
  v3 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v3 = v5;
  *(_QWORD *)(v3 + 16) = v6;
  *(_QWORD *)(v3 + 24) = v7;
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
    (__int64 *)(v3 + 32),
    &v8);
  *(_BYTE *)(v3 + 40) = v9;
  *(_BYTE *)(v3 + 41) = v10;
  *(_DWORD *)(v3 + 44) = v11;
  *(_BYTE *)(v3 + 48) = v12;
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v8);
  return 0;
}

```

## disassembly

```asm
0x180021c50  mov     [rsp-8+arg_8], rbx
0x180021c55  mov     [rsp-8+arg_10], rdi
0x180021c5a  push    rbp
0x180021c5b  lea     rbp, [rsp-57h]
0x180021c60  sub     rsp, 0E0h
0x180021c67  mov     rax, cs:__security_cookie
0x180021c6e  xor     rax, rsp
0x180021c71  mov     [rbp+57h+var_10], rax
0x180021c75  mov     rdi, rcx
0x180021c78  mov     rbx, [rcx+8]
0x180021c7c  mov     rdx, [rbx+10h]
0x180021c80  mov     rdx, [rdx]
0x180021c83  lea     rcx, [rbp+57h+var_70]
0x180021c87  call    ??$validate_cloud_store_data_reference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@Platform@Data@Windows@@@Z; wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Accessibility::EyeControl::SyncedSettings>(Windows::Data::Platform::ItemReference<Windows::Data::Accessibility::EyeControl::SyncedSettings> const *)
0x180021c8c  nop
0x180021c8d  lea     rax, [rbx+18h]
0x180021c91  mov     r9, [rbx+8]
0x180021c95  mov     [rsp+0E0h+var_C0], rax
0x180021c9a  mov     r9d, [r9]
0x180021c9d  lea     r8, [rbp+57h+var_70]
0x180021ca1  lea     rdx, [rbp+57h+var_A8]
0x180021ca5  mov     rcx, [rbx]
0x180021ca8  call    ??$call_load@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::call_load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::string const &)
0x180021cad  nop
0x180021cae  lea     rcx, [rbp+57h+var_70]; this
0x180021cb2  call    ??1validated_data_reference@cloud_store@wil@@QEAA@XZ; wil::cloud_store::validated_data_reference::~validated_data_reference(void)
0x180021cb7  mov     rbx, [rdi+10h]
0x180021cbb  movups  xmm0, [rbp+57h+var_A8]
0x180021cbf  movups  xmmword ptr [rbx], xmm0
0x180021cc2  movsd   xmm1, [rbp+57h+var_98]
0x180021cc7  movsd   qword ptr [rbx+10h], xmm1
0x180021ccc  mov     rax, [rbp+57h+var_90]
0x180021cd0  mov     [rbx+18h], rax
0x180021cd4  lea     rcx, [rbx+20h]
0x180021cd8  lea     rdx, [rbp+57h+var_88]
0x180021cdc  call    ??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy> &&)
0x180021ce1  mov     al, [rbp+57h+var_80]
0x180021ce4  mov     [rbx+28h], al
0x180021ce7  mov     al, [rbp+57h+var_7F]
0x180021cea  mov     [rbx+29h], al
0x180021ced  mov     eax, [rbp+57h+var_7C]
0x180021cf0  mov     [rbx+2Ch], eax
0x180021cf3  mov     al, [rbp+57h+var_78]
0x180021cf6  mov     [rbx+30h], al
0x180021cf9  lea     rcx, [rbp+57h+var_88]
0x180021cfd  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180021d02  xor     eax, eax
0x180021d04  mov     rcx, [rbp+57h+var_10]
0x180021d08  xor     rcx, rsp; StackCookie
0x180021d0b  call    __security_check_cookie
0x180021d10  lea     r11, [rsp+0E0h+var_s0]
0x180021d18  mov     rbx, [r11+18h]
0x180021d1c  mov     rdi, [r11+20h]
0x180021d20  mov     rsp, r11
0x180021d23  pop     rbp
0x180021d24  retn
```
