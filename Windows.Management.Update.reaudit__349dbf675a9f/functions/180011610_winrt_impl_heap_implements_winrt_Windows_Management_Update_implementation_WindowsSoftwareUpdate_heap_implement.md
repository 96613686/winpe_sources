# winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &)

- ea: `0x180011610`
- end: `0x1800117ea`
- name: `??0?$heap_implements@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@AEBW4WindowsSoftwareUpdateInstallationType@Update@Management@Windows@2@000AEBUUri@Foundation@72@_K3AEBUWindowsSoftwareUpdateVersion@5672@4AEBUWindowsSoftwareUpdateAppPackageInfo@5672@AEBUWindowsSoftwareUpdateExecutionInfo@5672@AEBUWindowsSoftwareUpdateOptionalInfo@5672@@Z`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013640`

## callees

- `0x1800035f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180011610`
- `0x18001203c`
- `0x180012078`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001d150`
- `0x18001db60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800117b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800117b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>::heap_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11,
        __int64 *a12,
        _QWORD *a13,
        _QWORD *a14)
{
  __int64 *v18; // rbx
  __int64 *SoftwareUpdate; // rsi
  __int64 v20; // rcx
  void *v21; // rbx
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const struct winrt::impl::slim_source_location *v25; // rax
  __int64 v26; // [rsp+88h] [rbp-49h] BYREF
  __int64 v27; // [rsp+90h] [rbp-41h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-39h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-31h] BYREF
  _BYTE v30[32]; // [rsp+B8h] [rbp-19h] BYREF

  a1[2] = &winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  a1[1] = 1;
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  v18 = a1 + 3;
  a1[3] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v25 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v30);
    winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v25);
    throw (winrt::hresult_not_implemented *)pExceptionObject;
  }
  winrt::hstring::hstring((winrt::hstring *)&lpMem, &dword_180030C44, 0);
  v26 = 0;
  SoftwareUpdate = winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
                     &v27,
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
                     &v26,
                     (__int64)&lpMem);
  if ( v18 != SoftwareUpdate )
  {
    if ( *v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v18);
    v20 = *SoftwareUpdate;
    *SoftwareUpdate = 0;
    *v18 = v20;
  }
  if ( v27 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  if ( v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  v21 = lpMem;
  if ( lpMem )
  {
    v22 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v22 )
    {
      if ( v22 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v21);
    }
  }
  *a1 = &winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180011610  mov     rax, rsp
0x180011613  mov     [rax+10h], rbx
0x180011617  mov     [rax+18h], rsi
0x18001161b  mov     [rax+20h], rdi
0x18001161f  mov     [rax+8], rcx
0x180011623  push    rbp
0x180011624  push    r14
0x180011626  push    r15
0x180011628  lea     rbp, [rax-1Fh]
0x18001162c  sub     rsp, 0D0h
0x180011633  mov     rsi, r9
0x180011636  mov     r14, r8
0x180011639  mov     r15, rdx
0x18001163c  mov     rdi, rcx
0x18001163f  lea     rax, ??_7?$produce@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdate@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdate>::`vftable'
0x180011646  mov     [rcx+10h], rax
0x18001164a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011651  mov     qword ptr [rcx+8], 1
0x180011659  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x180011660  mov     [rcx], rax
0x180011663  lea     rbx, [rcx+18h]
0x180011667  and     qword ptr [rbx], 0
0x18001166b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180011672  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180011677  test    al, al
0x180011679  jz      loc_1800117C4
0x18001167f  xor     r8d, r8d; unsigned int
0x180011682  lea     rdx, dword_180030C44; unsigned __int16 *
0x180011689  lea     rcx, [rbp+17h+lpMem]; this
0x18001168d  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180011692  nop
0x180011693  and     [rbp+17h+var_60], 0
0x180011698  lea     rax, [rbp+17h+lpMem]
0x18001169c  mov     [rsp+0E0h+var_68], rax
0x1800116a1  lea     rax, [rbp+17h+var_60]
0x1800116a5  mov     [rsp+0E0h+var_70], rax
0x1800116aa  mov     rax, [rbp+17h+arg_68]
0x1800116b1  mov     [rsp+0E0h+var_78], rax
0x1800116b6  mov     rax, [rbp+17h+arg_60]
0x1800116bd  mov     [rsp+0E0h+var_80], rax
0x1800116c2  mov     rax, [rbp+17h+arg_58]
0x1800116c6  mov     [rsp+0E0h+var_88], rax
0x1800116cb  mov     rax, [rbp+17h+arg_50]
0x1800116cf  mov     [rsp+0E0h+var_90], rax
0x1800116d4  mov     rax, [rbp+17h+arg_48]
0x1800116d8  mov     [rsp+0E0h+var_98], rax
0x1800116dd  mov     rax, [rbp+17h+arg_40]
0x1800116e1  mov     [rsp+0E0h+var_A0], rax
0x1800116e6  mov     rax, [rbp+17h+arg_38]
0x1800116ea  mov     [rsp+0E0h+var_A8], rax
0x1800116ef  mov     rax, [rbp+17h+arg_30]
0x1800116f3  mov     [rsp+0E0h+var_B0], rax
0x1800116f8  mov     rax, [rbp+17h+arg_28]
0x1800116fc  mov     [rsp+0E0h+var_B8], rax
0x180011701  mov     rax, [rbp+17h+arg_20]
0x180011705  mov     [rsp+0E0h+var_C0], rax
0x18001170a  mov     r9, rsi
0x18001170d  mov     r8, r14
0x180011710  mov     rdx, r15
0x180011713  lea     rcx, [rbp+17h+var_58]
0x180011717  call    ?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x18001171c  mov     rsi, rax
0x18001171f  cmp     rbx, rax
0x180011722  jz      short loc_18001173C
0x180011724  cmp     qword ptr [rbx], 0
0x180011728  jz      short loc_180011732
0x18001172a  mov     rcx, rbx
0x18001172d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011732  mov     rcx, [rsi]
0x180011735  and     qword ptr [rsi], 0
0x180011739  mov     [rbx], rcx
0x18001173c  cmp     [rbp+17h+var_58], 0
0x180011741  jz      short loc_18001174D
0x180011743  lea     rcx, [rbp+17h+var_58]
0x180011747  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001174c  nop
0x18001174d  cmp     [rbp+17h+var_60], 0
0x180011752  jz      short loc_18001175E
0x180011754  lea     rcx, [rbp+17h+var_60]
0x180011758  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001175d  nop
0x18001175e  mov     rbx, [rbp+17h+lpMem]
0x180011762  test    rbx, rbx
0x180011765  jz      short loc_180011788
0x180011767  or      eax, 0FFFFFFFFh
0x18001176a  lock xadd [rbx+18h], eax
0x18001176f  sub     eax, 1
0x180011772  jnz     short loc_1800117B3
0x180011774  nop
0x180011775  call    WINRT_IMPL_GetProcessHeap
0x18001177a  mov     rcx, rax; hHeap
0x18001177d  mov     r8, rbx; lpMem
0x180011780  xor     edx, edx; dwFlags
0x180011782  call    WINRT_IMPL_HeapFree
0x180011787  nop
0x180011788  lea     rax, ??_7WindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@6B@; const winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate::`vftable'
0x18001178f  mov     [rdi], rax
0x180011792  mov     rax, rdi
0x180011795  lea     r11, [rsp+0E0h+var_10]
0x18001179d  mov     rbx, [r11+28h]
0x1800117a1  mov     rsi, [r11+30h]
0x1800117a5  mov     rdi, [r11+38h]
0x1800117a9  mov     rsp, r11
0x1800117ac  pop     r15
0x1800117ae  pop     r14
0x1800117b0  pop     rbp
0x1800117b1  retn
0x1800117b3  test    eax, eax
0x1800117b5  jns     short loc_180011788
0x1800117b7  call    cs:__imp_abort
0x1800117c4  lea     rcx, [rbp+17h+var_30]
0x1800117c8  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800117cd  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800117d0  lea     rcx, [rbp+17h+pExceptionObject]; this
0x1800117d4  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800117d9  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800117e0  lea     rcx, [rbp+17h+pExceptionObject]; pExceptionObject
0x1800117e4  call    _CxxThrowException_0
```
