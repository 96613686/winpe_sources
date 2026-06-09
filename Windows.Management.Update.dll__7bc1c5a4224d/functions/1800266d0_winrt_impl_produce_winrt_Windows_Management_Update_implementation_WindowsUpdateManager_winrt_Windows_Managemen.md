# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetProvider(void *,void * *)

- ea: `0x1800266d0`
- end: `0x18002676f`
- name: `?GetProvider@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x1800114a8`
- `0x180014eb4`
- `0x18001c8a0`
- `0x180026600`
- `0x1800266d0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetProvider(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v11[5]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    *a3 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v11, v6);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v9);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v11[0] = a2;
    v7 = a1 + 8;
    if ( !a1 )
      v7 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(
      v7,
      &v12,
      v11);
    *a3 = v12;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800266d0  mov     [rsp+arg_8], rbx
0x1800266d5  mov     [rsp+arg_10], rsi
0x1800266da  push    rdi
0x1800266db  sub     rsp, 60h
0x1800266df  mov     rbx, r8
0x1800266e2  mov     rsi, rdx
0x1800266e5  mov     rdi, rcx
0x1800266e8  mov     qword ptr [r8], 0
0x1800266ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800266f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800266fb  test    al, al
0x1800266fd  jz      short loc_180026745
0x1800266ff  mov     [rsp+68h+var_30], rsi
0x180026704  lea     rcx, [rdi+8]
0x180026708  mov     eax, 20h ; ' '
0x18002670d  test    rdi, rdi
0x180026710  cmovz   rcx, rax
0x180026714  lea     r8, [rsp+68h+var_30]
0x180026719  lea     rdx, [rsp+68h+arg_0]
0x18002671e  call    ?GetProvider@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(winrt::param::hstring const &)
0x180026723  mov     rax, [rsp+68h+arg_0]
0x180026728  mov     [rbx], rax
0x18002672b  xor     eax, eax
0x18002672d  jmp     short loc_180026733
0x18002672f  mov     eax, dword ptr [rsp+68h+arg_0]
0x180026733  lea     r11, [rsp+68h+var_8]
0x180026738  mov     rbx, [r11+18h]
0x18002673c  mov     rsi, [r11+20h]
0x180026740  mov     rsp, r11
0x180026743  pop     rdi
0x180026744  retn
0x180026745  lea     rcx, [rsp+68h+var_30]
0x18002674a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002674f  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180026752  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180026757  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18002675c  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180026763  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180026768  call    _CxxThrowException_0
```
