# winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::get_ProviderIds(uint *,void * * *)

- ea: `0x180028770`
- end: `0x1800288cb`
- name: `?get_ProviderIds@?$produce@UWindowsUpdateManager@implementation@Update@Management@Windows@winrt@@UIWindowsUpdateManager2@3456@@impl@winrt@@UEAAHPEAIPEAPEAPEAX@Z`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800035f0`
- `0x180008e45`
- `0x180011f80`
- `0x18001203c`
- `0x180015ac0`
- `0x180015ae8`
- `0x18001db60`
- `0x1800276b8`
- `0x180027730`
- `0x1800281e4`
- `0x180028770`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::implementation::WindowsUpdateManager,winrt::Windows::Management::Update::IWindowsUpdateManager2>::get_ProviderIds(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  struct winrt::impl::hstring_header *v8; // rdx
  winrt::impl **v9; // rsi
  winrt::impl **v10; // r15
  _QWORD *v11; // r14
  __int64 v12; // rdi
  _QWORD *v13; // rdi
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v15; // rax
  _QWORD *v16; // [rsp+20h] [rbp-88h] BYREF
  _QWORD *v17; // [rsp+28h] [rbp-80h]
  __int128 v18; // [rsp+38h] [rbp-70h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-48h] BYREF
  int v21; // [rsp+B0h] [rbp+8h] BYREF

  v6 = 0;
  *a3 = 0;
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
    {
      v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v16);
      winrt::hresult_not_implemented::hresult_not_implemented((winrt::hresult_not_implemented *)v20, v15);
      throw (winrt::hresult_not_implemented *)v20;
    }
    v7 = a1 + 8;
    if ( !a1 )
      v7 = 32;
    winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(
      v7,
      &v18);
    v9 = (winrt::impl **)v18;
    v10 = (winrt::impl **)(v18 + 8LL * DWORD2(v18));
    v11 = 0;
    v12 = (8LL * DWORD2(v18)) >> 3;
    if ( (_DWORD)v12 )
    {
      v11 = WINRT_IMPL_CoTaskMemAlloc(8LL * (unsigned int)v12);
      if ( !v11 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v6 = v12;
    }
    v16 = v11;
    v13 = v11;
    v17 = v11;
    while ( v9 != v10 )
    {
      *v13++ = winrt::impl::duplicate_hstring(*v9, v8);
      v17 = v13;
      ++v9;
    }
    v16 = v13;
    std::_Uninitialized_backout<winrt::hstring *>::~_Uninitialized_backout<winrt::hstring *>(&v16);
    winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(&v18);
    v18 = 0;
    *a2 = v6;
    *a3 = v11;
    winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(&v18);
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
0x180028770  mov     [rsp+arg_8], rbx
0x180028775  mov     [rsp+arg_10], rsi
0x18002877a  push    rdi
0x18002877b  push    r12
0x18002877d  push    r13
0x18002877f  push    r14
0x180028781  push    r15
0x180028783  sub     rsp, 80h
0x18002878a  mov     r12, r8
0x18002878d  mov     r13, rdx
0x180028790  mov     rdi, rcx
0x180028793  xor     ebx, ebx
0x180028795  mov     [r8], rbx
0x180028798  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18002879f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800287a4  test    al, al
0x1800287a6  jz      loc_1800288A1
0x1800287ac  lea     rcx, [rdi+8]
0x1800287b0  lea     eax, [rbx+20h]
0x1800287b3  test    rdi, rdi
0x1800287b6  cmovz   rcx, rax
0x1800287ba  lea     rdx, [rsp+0A8h+var_70]
0x1800287bf  call    ?ProviderIds@?$consume_Windows_Management_Update_IWindowsUpdateManager2@UWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Update_IWindowsUpdateManager2<winrt::Windows::Management::Update::WindowsUpdateManager>::ProviderIds(void)
0x1800287c4  nop
0x1800287c5  mov     eax, dword ptr [rsp+0A8h+var_70+8]
0x1800287c9  mov     rsi, qword ptr [rsp+0A8h+var_70]
0x1800287ce  lea     r15, [rsi+rax*8]
0x1800287d2  mov     r14d, ebx
0x1800287d5  mov     rdi, r15
0x1800287d8  sub     rdi, rsi
0x1800287db  sar     rdi, 3
0x1800287df  test    edi, edi
0x1800287e1  jz      short loc_1800287FC
0x1800287e3  mov     ecx, edi
0x1800287e5  shl     rcx, 3; cb
0x1800287e9  call    WINRT_IMPL_CoTaskMemAlloc
0x1800287ee  mov     r14, rax
0x1800287f1  test    rax, rax
0x1800287f4  jz      loc_180028885
0x1800287fa  mov     ebx, edi
0x1800287fc  mov     [rsp+0A8h+var_88], r14
0x180028801  mov     rdi, r14
0x180028804  mov     [rsp+0A8h+var_80], r14
0x180028809  cmp     rsi, r15
0x18002880c  jz      short loc_180028828
0x18002880e  mov     rcx, [rsi]; this
0x180028811  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180028816  mov     [rdi], rax
0x180028819  add     rdi, 8
0x18002881d  mov     [rsp+0A8h+var_80], rdi
0x180028822  add     rsi, 8
0x180028826  jmp     short loc_180028809
0x180028828  mov     [rsp+0A8h+var_88], rdi
0x18002882d  lea     rcx, [rsp+0A8h+var_88]
0x180028832  call    ??1?$_Uninitialized_backout@PEAUhstring@winrt@@@std@@QEAA@XZ; std::_Uninitialized_backout<winrt::hstring *>::~_Uninitialized_backout<winrt::hstring *>(void)
0x180028837  nop
0x180028838  lea     rcx, [rsp+0A8h+var_70]
0x18002883d  call    ??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ; winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)
0x180028842  xorps   xmm0, xmm0
0x180028845  movups  [rsp+0A8h+var_70], xmm0
0x18002884a  mov     [r13+0], ebx
0x18002884e  mov     [r12], r14
0x180028852  lea     rcx, [rsp+0A8h+var_70]
0x180028857  call    ??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ; winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)
0x18002885c  xor     eax, eax
0x18002885e  jmp     short loc_180028867
0x180028860  mov     eax, [rsp+0A8h+arg_0]
0x180028867  lea     r11, [rsp+0A8h+var_28]
0x18002886f  mov     rbx, [r11+38h]
0x180028873  mov     rsi, [r11+40h]
0x180028877  mov     rsp, r11
0x18002887a  pop     r15
0x18002887c  pop     r14
0x18002887e  pop     r13
0x180028880  pop     r12
0x180028882  pop     rdi
0x180028883  retn
0x180028885  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18002888a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18002888f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180028896  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002889b  call    _CxxThrowException_0
0x1800288a1  lea     rcx, [rsp+0A8h+var_88]
0x1800288a6  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800288ab  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800288ae  lea     rcx, [rsp+0A8h+var_48]; this
0x1800288b3  call    ??0hresult_not_implemented@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::impl::slim_source_location const &)
0x1800288b8  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800288bf  lea     rcx, [rsp+0A8h+var_48]; pExceptionObject
0x1800288c4  call    _CxxThrowException_0
```
