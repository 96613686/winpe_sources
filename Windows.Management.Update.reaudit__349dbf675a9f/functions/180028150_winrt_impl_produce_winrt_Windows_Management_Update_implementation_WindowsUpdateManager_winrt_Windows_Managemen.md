# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::PerformScan(void *,void * *)

- ea: `0x180028150`
- end: `0x1800281de`
- name: `?PerformScan@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x18001db60`
- `0x180028088`
- `0x180028150`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::PerformScan(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = a2;
  try
  {
    *a3 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v7);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v5 = a1 + 8;
    if ( !a1 )
      v5 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(
      v5,
      &v10,
      &v11);
    *a3 = v10;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v10);
  }
  return result;
}

```

## disassembly

```asm
0x180028150  mov     [rsp+arg_10], rbx
0x180028155  mov     [rsp+arg_8], rdx
0x18002815a  push    rdi
0x18002815b  sub     rsp, 50h
0x18002815f  mov     rbx, r8
0x180028162  mov     rdi, rcx
0x180028165  and     qword ptr [r8], 0
0x180028169  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180028170  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180028175  test    al, al
0x180028177  jz      short loc_1800281B4
0x180028179  lea     rcx, [rdi+8]
0x18002817d  mov     eax, 20h ; ' '
0x180028182  test    rdi, rdi
0x180028185  cmovz   rcx, rax
0x180028189  lea     r8, [rsp+58h+arg_8]
0x18002818e  lea     rdx, [rsp+58h+arg_0]
0x180028193  call    ?PerformScan@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUWindowsUpdateManagerScanOptions@Update@Management@Windows@3@@Z; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::PerformScan(winrt::Windows::Management::Update::WindowsUpdateManagerScanOptions const &)
0x180028198  mov     rax, [rsp+58h+arg_0]
0x18002819d  mov     [rbx], rax
0x1800281a0  xor     eax, eax
0x1800281a2  jmp     short loc_1800281A8
0x1800281a4  mov     eax, dword ptr [rsp+58h+arg_0]
0x1800281a8  mov     rbx, [rsp+58h+arg_10]
0x1800281ad  add     rsp, 50h
0x1800281b1  pop     rdi
0x1800281b2  retn
0x1800281b4  lea     rcx, [rsp+58h+var_20]
0x1800281b9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800281be  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800281c1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800281c6  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800281cb  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800281d2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800281d7  call    _CxxThrowException_0
```
