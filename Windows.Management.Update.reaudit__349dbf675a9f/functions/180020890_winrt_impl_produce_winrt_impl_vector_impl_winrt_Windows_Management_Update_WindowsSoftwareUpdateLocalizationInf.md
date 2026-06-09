# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAtEnd(void)

- ea: `0x180020890`
- end: `0x1800209a5`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800035f0`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001f9d0`
- `0x180020890`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAtEnd(
        unsigned __int64 a1)
{
  __int64 v1; // rbx
  volatile signed __int32 *v2; // rdi
  char v3; // si
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 *v7; // rcx
  const struct winrt::impl::slim_source_location *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF

  v1 = (a1 - 16) & ((unsigned __int128)-(__int128)a1 >> 64);
  v2 = (volatile signed __int32 *)(v1 + 40);
  v12 = 0;
  if ( *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x30) == *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x38) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v14);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v9);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v10 + 112) = *(_DWORD *)winrt::to_hresult(&v16);
      return v16;
    }
  }
  v3 = 1;
  _InterlockedAdd(v2, 1u);
  v4 = *(_QWORD *)((v1 & -(__int64)(v2 != 0)) + 0x38);
  v5 = *(_QWORD *)(v4 - 8);
  *(_QWORD *)(v4 - 8) = 0;
  v11 = v5;
  v12 = 1;
  v6 = v1 & -(__int64)(v2 != 0);
  v7 = (__int64 *)(*(_QWORD *)(v6 + 56) - 8LL);
  if ( *v7 )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    v3 = v12;
    v5 = v11;
  }
  *(_QWORD *)(v6 + 56) -= 8LL;
  if ( v3 && v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return 0;
}

```

## disassembly

```asm
0x180020890  mov     r11, rsp
0x180020893  mov     [r11+10h], rbx
0x180020897  mov     [r11+18h], rsi
0x18002089b  mov     [r11+20h], rdi
0x18002089f  push    r14
0x1800208a1  sub     rsp, 60h
0x1800208a5  lea     rax, [rcx-10h]
0x1800208a9  neg     rcx
0x1800208ac  sbb     rbx, rbx
0x1800208af  and     rbx, rax
0x1800208b2  lea     rdi, [rbx+28h]
0x1800208b6  mov     [rsp+68h+var_40], 0
0x1800208bb  mov     rax, rdi
0x1800208be  neg     rax
0x1800208c1  sbb     rcx, rcx
0x1800208c4  and     rcx, rbx
0x1800208c7  mov     rax, [rcx+38h]
0x1800208cb  cmp     [rcx+30h], rax
0x1800208cf  jz      loc_18002097B
0x1800208d5  mov     esi, 1
0x1800208da  lock add [rdi], esi
0x1800208dd  mov     rax, rdi
0x1800208e0  neg     rax
0x1800208e3  sbb     rcx, rcx
0x1800208e6  and     rcx, rbx
0x1800208e9  mov     r14, [rcx+38h]
0x1800208ed  cmp     [rsp+68h+var_40], 0
0x1800208f2  jz      short loc_180020909
0x1800208f4  cmp     qword ptr [r11-48h], 0
0x1800208f9  jz      short loc_180020904
0x1800208fb  lea     rcx, [r11-48h]
0x1800208ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020904  mov     [rsp+68h+var_40], 0
0x180020909  mov     rax, [r14-8]
0x18002090d  and     qword ptr [r14-8], 0
0x180020912  mov     [rsp+68h+var_48], rax
0x180020917  mov     [rsp+68h+var_40], sil
0x18002091c  neg     rdi
0x18002091f  sbb     rdi, rdi
0x180020922  and     rdi, rbx
0x180020925  mov     rcx, [rdi+38h]
0x180020929  sub     rcx, 8
0x18002092d  cmp     qword ptr [rcx], 0
0x180020931  jz      short loc_180020942
0x180020933  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020938  mov     sil, [rsp+68h+var_40]
0x18002093d  mov     rax, [rsp+68h+var_48]
0x180020942  add     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFF8h
0x180020947  test    sil, sil
0x18002094a  jz      short loc_18002095B
0x18002094c  test    rax, rax
0x18002094f  jz      short loc_18002095B
0x180020951  lea     rcx, [rsp+68h+var_48]
0x180020956  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002095b  xor     eax, eax
0x18002095d  jmp     short loc_180020963
0x18002095f  mov     eax, [rsp+68h+arg_0]
0x180020963  lea     r11, [rsp+68h+var_8]
0x180020968  mov     rbx, [r11+18h]
0x18002096c  mov     rsi, [r11+20h]
0x180020970  mov     rdi, [r11+28h]
0x180020974  mov     rsp, r11
0x180020977  pop     r14
0x180020979  retn
0x18002097b  lea     rcx, [rsp+68h+var_20]
0x180020980  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180020985  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020988  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002098d  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180020992  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180020999  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002099e  call    _CxxThrowException_0
```
