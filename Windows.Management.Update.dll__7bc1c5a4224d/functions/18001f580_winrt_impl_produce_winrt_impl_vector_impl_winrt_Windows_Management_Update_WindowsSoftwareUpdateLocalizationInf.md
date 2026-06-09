# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAtEnd(void)

- ea: `0x18001f580`
- end: `0x18001f684`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001e6ec`
- `0x18001f580`

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
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 *v7; // rcx
  const struct winrt::impl::slim_source_location *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-68h] BYREF
  char v12; // [rsp+28h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v14[64]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF

  v1 = (a1 - 16) & ((unsigned __int128)-(__int128)a1 >> 64);
  v2 = (volatile signed __int32 *)(v1 + 40);
  v12 = 0;
  if ( *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x30) == *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x38) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v14);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v9);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v10 + 144) = *(_DWORD *)winrt::to_hresult(&v16);
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
0x18001f580  push    rbx
0x18001f582  push    rsi
0x18001f583  push    rdi
0x18001f584  push    r14
0x18001f586  sub     rsp, 68h
0x18001f58a  lea     rax, [rcx-10h]
0x18001f58e  neg     rcx
0x18001f591  sbb     rbx, rbx
0x18001f594  and     rbx, rax
0x18001f597  lea     rdi, [rbx+28h]
0x18001f59b  mov     [rsp+88h+var_60], 0
0x18001f5a0  mov     rax, rdi
0x18001f5a3  neg     rax
0x18001f5a6  sbb     rcx, rcx
0x18001f5a9  and     rcx, rbx
0x18001f5ac  mov     rax, [rcx+38h]
0x18001f5b0  cmp     [rcx+30h], rax
0x18001f5b4  jz      loc_18001F65A
0x18001f5ba  mov     esi, 1
0x18001f5bf  lock add [rdi], esi
0x18001f5c2  mov     rax, rdi
0x18001f5c5  neg     rax
0x18001f5c8  sbb     rcx, rcx
0x18001f5cb  and     rcx, rbx
0x18001f5ce  mov     r14, [rcx+38h]
0x18001f5d2  cmp     [rsp+88h+var_60], 0
0x18001f5d7  jz      short loc_18001F5F0
0x18001f5d9  cmp     [rsp+88h+var_68], 0
0x18001f5df  jz      short loc_18001F5EB
0x18001f5e1  lea     rcx, [rsp+88h+var_68]
0x18001f5e6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f5eb  mov     [rsp+88h+var_60], 0
0x18001f5f0  mov     rdx, [r14-8]
0x18001f5f4  mov     qword ptr [r14-8], 0
0x18001f5fc  mov     [rsp+88h+var_68], rdx
0x18001f601  mov     [rsp+88h+var_60], sil
0x18001f606  neg     rdi
0x18001f609  sbb     rdi, rdi
0x18001f60c  and     rdi, rbx
0x18001f60f  mov     rcx, [rdi+38h]
0x18001f613  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001f617  cmp     qword ptr [rcx], 0
0x18001f61b  jz      short loc_18001F62C
0x18001f61d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f622  mov     sil, [rsp+88h+var_60]
0x18001f627  mov     rdx, [rsp+88h+var_68]
0x18001f62c  add     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFF8h
0x18001f631  test    sil, sil
0x18001f634  jz      short loc_18001F645
0x18001f636  test    rdx, rdx
0x18001f639  jz      short loc_18001F645
0x18001f63b  lea     rcx, [rsp+88h+var_68]
0x18001f640  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f645  xor     eax, eax
0x18001f647  jmp     short loc_18001F650
0x18001f649  mov     eax, [rsp+88h+arg_0]
0x18001f650  add     rsp, 68h
0x18001f654  pop     r14
0x18001f656  pop     rdi
0x18001f657  pop     rsi
0x18001f658  pop     rbx
0x18001f659  retn
0x18001f65a  lea     rcx, [rsp+88h+var_40]
0x18001f65f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f664  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f667  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001f66c  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001f671  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001f678  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001f67d  call    _CxxThrowException_0
```
