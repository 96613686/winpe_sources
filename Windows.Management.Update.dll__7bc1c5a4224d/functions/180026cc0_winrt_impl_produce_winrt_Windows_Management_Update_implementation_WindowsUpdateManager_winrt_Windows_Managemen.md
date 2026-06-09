# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::PerformScan(void *,void * *)

- ea: `0x180026cc0`
- end: `0x180026d50`
- name: `?PerformScan@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x18001c8a0`
- `0x180026be8`
- `0x180026cc0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::PerformScan(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = a2;
  try
  {
    *a3 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10, v5);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v8);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v6 = a1 + 8;
    if ( !a1 )
      v6 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(
      v6,
      &v11,
      &v12);
    *a3 = v11;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180026cc0  mov     [rsp+arg_10], rbx
0x180026cc5  mov     [rsp+arg_8], rdx
0x180026cca  push    rdi
0x180026ccb  sub     rsp, 50h
0x180026ccf  mov     rbx, r8
0x180026cd2  mov     rdi, rcx
0x180026cd5  mov     qword ptr [r8], 0
0x180026cdc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180026ce3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180026ce8  test    al, al
0x180026cea  jz      short loc_180026D26
0x180026cec  lea     rcx, [rdi+8]
0x180026cf0  mov     eax, 20h ; ' '
0x180026cf5  test    rdi, rdi
0x180026cf8  cmovz   rcx, rax
0x180026cfc  lea     r8, [rsp+58h+arg_8]
0x180026d01  lea     rdx, [rsp+58h+arg_0]
0x180026d06  call    ?PerformScan@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUWindowsUpdateManagerScanOptions@Update@Management@Windows@3@@Z; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(winrt::Windows::Management::Update::WindowsUpdateManagerScanOptions const &)
0x180026d0b  mov     rax, [rsp+58h+arg_0]
0x180026d10  mov     [rbx], rax
0x180026d13  xor     eax, eax
0x180026d15  jmp     short loc_180026D1B
0x180026d17  mov     eax, dword ptr [rsp+58h+arg_0]
0x180026d1b  mov     rbx, [rsp+58h+arg_10]
0x180026d20  add     rsp, 50h
0x180026d24  pop     rdi
0x180026d25  retn
0x180026d26  lea     rcx, [rsp+58h+var_20]
0x180026d2b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026d30  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180026d33  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180026d38  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180026d3d  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180026d44  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180026d49  call    _CxxThrowException_0
```
