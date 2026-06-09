# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &)

- ea: `0x180010acc`
- end: `0x180010ca7`
- name: `??0?$heap_implements@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@AEBW4WindowsSoftwareUpdateInstallationType@Update@Management@Windows@2@000AEBUUri@Foundation@72@_K3AEBUWindowsSoftwareUpdateVersion@5672@4AEBUWindowsSoftwareUpdateAppPackageInfo@5672@AEBUWindowsSoftwareUpdateExecutionInfo@5672@AEBUWindowsSoftwareUpdateOptionalInfo@5672@@Z`
- size: `475`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012a60`

## callees

- `0x18000340c`
- `0x180008653`
- `0x18000866b`
- `0x180010acc`
- `0x1800114a8`
- `0x1800114ec`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001bf00`
- `0x18001c8a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010c7a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010c7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  __int64 *v18; // rdi
  __int64 v19; // rdx
  __int64 *SoftwareUpdate; // rsi
  __int64 v21; // rcx
  void *v22; // rdi
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const struct winrt::impl::slim_source_location *v26; // rax
  __int64 v27; // [rsp+80h] [rbp-51h] BYREF
  __int64 v28; // [rsp+88h] [rbp-49h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-41h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+98h] [rbp-39h] BYREF
  _BYTE v31[80]; // [rsp+B0h] [rbp-21h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  v18 = a1 + 3;
  a1[3] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v26 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v31, v19);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v26);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  pExceptionObject[0] = &dword_18002EB94;
  pExceptionObject[1] = 0;
  winrt::hstring::hstring(&lpMem, pExceptionObject);
  v27 = 0;
  SoftwareUpdate = winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
                     &v28,
                     a2,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7,
                     a8,
                     a9,
                     a10,
                     a11,
                     a12,
                     a13,
                     a14,
                     (__int64)&v27,
                     (__int64)&lpMem);
  if ( v18 != SoftwareUpdate )
  {
    if ( *v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v18);
    v21 = *SoftwareUpdate;
    *SoftwareUpdate = 0;
    *v18 = v21;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
  if ( v27 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  v22 = lpMem;
  if ( lpMem )
  {
    v23 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v23 )
    {
      if ( v23 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v22);
    }
  }
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180010acc  mov     [rsp-8+arg_0], rcx
0x180010ad1  push    rbp
0x180010ad2  push    rbx
0x180010ad3  push    rsi
0x180010ad4  push    rdi
0x180010ad5  push    r14
0x180010ad7  push    r15
0x180010ad9  lea     rbp, [rsp-7]
0x180010ade  sub     rsp, 0D8h
0x180010ae5  mov     rsi, r9
0x180010ae8  mov     r14, r8
0x180010aeb  mov     r15, rdx
0x180010aee  mov     rbx, rcx
0x180010af1  lea     rax, ??_7?$produce@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdate@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable'
0x180010af8  mov     [rcx+10h], rax
0x180010afc  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180010b03  mov     qword ptr [rcx+8], 1
0x180010b0b  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x180010b12  mov     [rcx], rax
0x180010b15  lea     rdi, [rcx+18h]
0x180010b19  mov     qword ptr [rdi], 0
0x180010b20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180010b27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180010b2c  test    al, al
0x180010b2e  jz      loc_180010C81
0x180010b34  lea     rax, dword_18002EB94
0x180010b3b  mov     [rbp+2Fh+pExceptionObject], rax
0x180010b3f  mov     [rbp+2Fh+var_60], 0
0x180010b47  lea     rdx, [rbp+2Fh+pExceptionObject]
0x180010b4b  lea     rcx, [rbp+2Fh+lpMem]
0x180010b4f  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180010b54  nop
0x180010b55  mov     [rbp+2Fh+var_80], 0
0x180010b5d  lea     rax, [rbp+2Fh+lpMem]
0x180010b61  mov     [rsp+100h+var_88], rax
0x180010b66  lea     rax, [rbp+2Fh+var_80]
0x180010b6a  mov     [rsp+100h+var_90], rax
0x180010b6f  mov     rax, [rbp+2Fh+arg_68]
0x180010b76  mov     [rsp+100h+var_98], rax
0x180010b7b  mov     rax, [rbp+2Fh+arg_60]
0x180010b82  mov     [rsp+100h+var_A0], rax
0x180010b87  mov     rax, [rbp+2Fh+arg_58]
0x180010b8e  mov     [rsp+100h+var_A8], rax
0x180010b93  mov     rax, [rbp+2Fh+arg_50]
0x180010b9a  mov     [rsp+100h+var_B0], rax
0x180010b9f  mov     rax, [rbp+2Fh+arg_48]
0x180010ba6  mov     [rsp+100h+var_B8], rax
0x180010bab  mov     rax, [rbp+2Fh+arg_40]
0x180010baf  mov     [rsp+100h+var_C0], rax
0x180010bb4  mov     rax, [rbp+2Fh+arg_38]
0x180010bb8  mov     [rsp+100h+var_C8], rax
0x180010bbd  mov     rax, [rbp+2Fh+arg_30]
0x180010bc1  mov     [rsp+100h+var_D0], rax
0x180010bc6  mov     rax, [rbp+2Fh+arg_28]
0x180010bca  mov     [rsp+100h+var_D8], rax
0x180010bcf  mov     rax, [rbp+2Fh+arg_20]
0x180010bd3  mov     [rsp+100h+var_E0], rax
0x180010bd8  mov     r9, rsi
0x180010bdb  mov     r8, r14
0x180010bde  mov     rdx, r15
0x180010be1  lea     rcx, [rbp+2Fh+var_78]
0x180010be5  call    ?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x180010bea  mov     rsi, rax
0x180010bed  cmp     rdi, rax
0x180010bf0  jz      short loc_180010C0D
0x180010bf2  cmp     qword ptr [rdi], 0
0x180010bf6  jz      short loc_180010C00
0x180010bf8  mov     rcx, rdi
0x180010bfb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010c00  mov     rcx, [rsi]
0x180010c03  mov     qword ptr [rsi], 0
0x180010c0a  mov     [rdi], rcx
0x180010c0d  cmp     [rbp+2Fh+var_78], 0
0x180010c12  jz      short loc_180010C1E
0x180010c14  lea     rcx, [rbp+2Fh+var_78]
0x180010c18  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010c1d  nop
0x180010c1e  cmp     [rbp+2Fh+var_80], 0
0x180010c23  jz      short loc_180010C2F
0x180010c25  lea     rcx, [rbp+2Fh+var_80]
0x180010c29  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010c2e  nop
0x180010c2f  mov     rdi, [rbp+2Fh+lpMem]
0x180010c33  test    rdi, rdi
0x180010c36  jz      short loc_180010C59
0x180010c38  or      eax, 0FFFFFFFFh
0x180010c3b  lock xadd [rdi+18h], eax
0x180010c40  sub     eax, 1
0x180010c43  jnz     short loc_180010C76
0x180010c45  nop
0x180010c46  call    WINRT_IMPL_GetProcessHeap
0x180010c4b  mov     rcx, rax; hHeap
0x180010c4e  mov     r8, rdi; lpMem
0x180010c51  xor     edx, edx; dwFlags
0x180010c53  call    WINRT_IMPL_HeapFree
0x180010c58  nop
0x180010c59  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x180010c60  mov     [rbx], rax
0x180010c63  mov     rax, rbx
0x180010c66  add     rsp, 0D8h
0x180010c6d  pop     r15
0x180010c6f  pop     r14
0x180010c71  pop     rdi
0x180010c72  pop     rsi
0x180010c73  pop     rbx
0x180010c74  pop     rbp
0x180010c75  retn
0x180010c76  test    eax, eax
0x180010c78  jns     short loc_180010C59
0x180010c7a  call    cs:__imp_abort
0x180010c81  lea     rcx, [rbp+2Fh+var_50]
0x180010c85  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180010c8a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180010c8d  lea     rcx, [rbp+2Fh+pExceptionObject]; this
0x180010c91  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180010c96  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180010c9d  lea     rcx, [rbp+2Fh+pExceptionObject]; pExceptionObject
0x180010ca1  call    _CxxThrowException_0
```
