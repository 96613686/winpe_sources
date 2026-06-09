# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::get_ProviderIds(uint *,void * * *)

- ea: `0x180027310`
- end: `0x180027471`
- name: `?get_ProviderIds@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAIPEAPEAPEAX@Z`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000340c`
- `0x180008891`
- `0x1800113e0`
- `0x1800114a8`
- `0x180014eb4`
- `0x180014ee0`
- `0x18001c8a0`
- `0x180026228`
- `0x18002629c`
- `0x180026d58`
- `0x180027310`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::get_ProviderIds(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  struct winrt::impl::hstring_header *v7; // rdx
  winrt::impl **v8; // rdi
  winrt::impl **v9; // r15
  _QWORD *v10; // rsi
  int v11; // r14d
  __int64 v12; // rbx
  _QWORD *v13; // rbx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v15; // rax
  _QWORD *v16; // [rsp+20h] [rbp-88h] BYREF
  _QWORD *v17; // [rsp+28h] [rbp-80h]
  __int128 v18; // [rsp+30h] [rbp-78h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-48h] BYREF
  int v21; // [rsp+B0h] [rbp+8h] BYREF

  *a3 = 0;
  try
  {
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)&v18);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)v20, v15);
      throw (winrt::hresult_not_implemented *)v20;
    }
    v6 = a1 + 8;
    if ( !a1 )
      v6 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(
      v6,
      &v18);
    v8 = (winrt::impl **)v18;
    v9 = (winrt::impl **)(v18 + 8LL * DWORD2(v18));
    v10 = 0;
    v11 = 0;
    v12 = (8LL * DWORD2(v18)) >> 3;
    if ( (_DWORD)v12 )
    {
      v10 = WINRT_IMPL_CoTaskMemAlloc(8LL * (unsigned int)v12);
      if ( !v10 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v11 = v12;
    }
    v16 = v10;
    v13 = v10;
    v17 = v10;
    while ( v8 != v9 )
    {
      *v13++ = winrt::impl::duplicate_hstring(*v8, v7);
      v17 = v13;
      ++v8;
    }
    v16 = v13;
    std::_Uninitialized_backout<winrt::hstring *>::~_Uninitialized_backout<winrt::hstring *>(&v16);
    winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>((__int64)&v18);
    v18 = 0;
    *a2 = v11;
    *a3 = v10;
    winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>((__int64)&v18);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v21);
  }
  return result;
}

```

## disassembly

```asm
0x180027310  mov     [rsp+arg_8], rbx
0x180027315  mov     [rsp+arg_10], rsi
0x18002731a  push    rdi
0x18002731b  push    r12
0x18002731d  push    r13
0x18002731f  push    r14
0x180027321  push    r15
0x180027323  sub     rsp, 80h
0x18002732a  mov     r12, r8
0x18002732d  mov     r13, rdx
0x180027330  mov     rbx, rcx
0x180027333  mov     qword ptr [r8], 0
0x18002733a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180027341  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180027346  test    al, al
0x180027348  jz      loc_180027447
0x18002734e  lea     rcx, [rbx+8]
0x180027352  mov     eax, 20h ; ' '
0x180027357  test    rbx, rbx
0x18002735a  cmovz   rcx, rax
0x18002735e  lea     rdx, [rsp+0A8h+var_78]
0x180027363  call    ?ProviderIds@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(void)
0x180027368  nop
0x180027369  mov     eax, dword ptr [rsp+0A8h+var_78+8]
0x18002736d  mov     rdi, qword ptr [rsp+0A8h+var_78]
0x180027372  lea     r15, [rdi+rax*8]
0x180027376  xor     esi, esi
0x180027378  xor     r14d, r14d
0x18002737b  mov     rbx, r15
0x18002737e  sub     rbx, rdi
0x180027381  sar     rbx, 3
0x180027385  test    ebx, ebx
0x180027387  jz      short loc_1800273A3
0x180027389  mov     ecx, ebx
0x18002738b  shl     rcx, 3; cb
0x18002738f  call    WINRT_IMPL_CoTaskMemAlloc
0x180027394  mov     rsi, rax
0x180027397  test    rax, rax
0x18002739a  jz      loc_18002742B
0x1800273a0  mov     r14d, ebx
0x1800273a3  mov     [rsp+0A8h+var_88], rsi
0x1800273a8  mov     rbx, rsi
0x1800273ab  mov     [rsp+0A8h+var_80], rbx
0x1800273b0  cmp     rdi, r15
0x1800273b3  jz      short loc_1800273CF
0x1800273b5  mov     rcx, [rdi]; this
0x1800273b8  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800273bd  mov     [rbx], rax
0x1800273c0  add     rbx, 8
0x1800273c4  mov     [rsp+0A8h+var_80], rbx
0x1800273c9  add     rdi, 8
0x1800273cd  jmp     short loc_1800273B0
0x1800273cf  mov     [rsp+0A8h+var_88], rbx
0x1800273d4  lea     rcx, [rsp+0A8h+var_88]
0x1800273d9  call    ??1?$_Uninitialized_backout@PEAUhstring@winrt@@@std@@QEAA@XZ; std::_Uninitialized_backout<winrt::hstring *>::~_Uninitialized_backout<winrt::hstring *>(void)
0x1800273de  nop
0x1800273df  lea     rcx, [rsp+0A8h+var_78]
0x1800273e4  call    ??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ; winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)
0x1800273e9  xorps   xmm0, xmm0
0x1800273ec  movups  [rsp+0A8h+var_78], xmm0
0x1800273f1  mov     [r13+0], r14d
0x1800273f5  mov     [r12], rsi
0x1800273f9  lea     rcx, [rsp+0A8h+var_78]
0x1800273fe  call    ??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ; winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)
0x180027403  xor     eax, eax
0x180027405  jmp     short loc_18002740E
0x180027407  mov     eax, [rsp+0A8h+arg_0]
0x18002740e  lea     r11, [rsp+0A8h+var_28]
0x180027416  mov     rbx, [r11+38h]
0x18002741a  mov     rsi, [r11+40h]
0x18002741e  mov     rsp, r11
0x180027421  pop     r15
0x180027423  pop     r14
0x180027425  pop     r13
0x180027427  pop     r12
0x180027429  pop     rdi
0x18002742a  retn
0x18002742b  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180027430  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180027435  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002743c  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180027441  call    _CxxThrowException_0
0x180027447  lea     rcx, [rsp+0A8h+var_78]
0x18002744c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180027451  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180027454  lea     rcx, [rsp+0A8h+var_48]; this
0x180027459  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x18002745e  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180027465  lea     rcx, [rsp+0A8h+var_48]; pExceptionObject
0x18002746a  call    _CxxThrowException_0
```
