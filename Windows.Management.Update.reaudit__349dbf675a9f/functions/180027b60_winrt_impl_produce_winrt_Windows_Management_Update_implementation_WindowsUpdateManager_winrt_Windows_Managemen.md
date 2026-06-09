# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetProvider(void *,void * *)

- ea: `0x180027b60`
- end: `0x180027bfd`
- name: `?GetProvider@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800035f0`
- `0x18001203c`
- `0x180015ac0`
- `0x18001db60`
- `0x180027a98`
- `0x180027b60`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::GetProvider(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v10[5]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    *a3 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v10);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)pExceptionObject, v8);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    }
    v6 = a1 + 8;
    if ( !a1 )
      v6 = 32;
    v10[0] = a2;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(
      v6,
      &v11,
      v10);
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
0x180027b60  mov     [rsp+arg_8], rbx
0x180027b65  mov     [rsp+arg_10], rsi
0x180027b6a  push    rdi
0x180027b6b  sub     rsp, 60h
0x180027b6f  mov     rbx, r8
0x180027b72  mov     rsi, rdx
0x180027b75  mov     rdi, rcx
0x180027b78  and     qword ptr [r8], 0
0x180027b7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180027b83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180027b88  test    al, al
0x180027b8a  jz      short loc_180027BD3
0x180027b8c  lea     rcx, [rdi+8]
0x180027b90  mov     eax, 20h ; ' '
0x180027b95  test    rdi, rdi
0x180027b98  cmovz   rcx, rax
0x180027b9c  mov     [rsp+68h+var_30], rsi
0x180027ba1  lea     r8, [rsp+68h+var_30]
0x180027ba6  lea     rdx, [rsp+68h+arg_0]
0x180027bab  call    ?GetProvider@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::GetProvider(winrt::param::hstring const &)
0x180027bb0  mov     rax, [rsp+68h+arg_0]
0x180027bb5  mov     [rbx], rax
0x180027bb8  xor     eax, eax
0x180027bba  jmp     short loc_180027BC0
0x180027bbc  mov     eax, dword ptr [rsp+68h+arg_0]
0x180027bc0  lea     r11, [rsp+68h+var_8]
0x180027bc5  mov     rbx, [r11+18h]
0x180027bc9  mov     rsi, [r11+20h]
0x180027bcd  mov     rsp, r11
0x180027bd0  pop     rdi
0x180027bd1  retn
0x180027bd3  lea     rcx, [rsp+68h+var_30]
0x180027bd8  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180027bdd  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180027be0  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027be5  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x180027bea  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180027bf1  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027bf6  call    _CxxThrowException_0
```
