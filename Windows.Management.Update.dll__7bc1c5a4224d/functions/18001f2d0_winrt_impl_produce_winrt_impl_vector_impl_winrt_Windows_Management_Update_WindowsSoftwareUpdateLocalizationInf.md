# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::InsertAt(uint,void *)

- ea: `0x18001f2d0`
- end: `0x18001f36e`
- name: `?InsertAt@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x18001e6ec`
- `0x18001f2d0`
- `0x1800200cc`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::InsertAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r8
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = a3;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  v4 = (__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38) - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3;
  if ( a2 > v4 )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v9);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v7);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  if ( v3 == -40 )
  {
    v3 = 0;
    v5 = 48;
  }
  else
  {
    v5 = v3 + 48;
  }
  try
  {
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::insert(
      v5,
      &v10,
      (char *)(*(_QWORD *)(v3 + 48) + 8LL * a2),
      &v12);
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
0x18001f2d0  mov     [rsp+arg_10], r8
0x18001f2d5  sub     rsp, 58h
0x18001f2d9  lea     rax, [rcx-10h]
0x18001f2dd  neg     rcx
0x18001f2e0  sbb     r8, r8
0x18001f2e3  and     r8, rax
0x18001f2e6  lea     r9, [r8+28h]
0x18001f2ea  mov     rax, r9
0x18001f2ed  neg     rax
0x18001f2f0  sbb     rcx, rcx
0x18001f2f3  and     rcx, r8
0x18001f2f6  mov     r10d, edx
0x18001f2f9  mov     rax, [rcx+38h]
0x18001f2fd  sub     rax, [rcx+30h]
0x18001f301  sar     rax, 3
0x18001f305  cmp     r10, rax
0x18001f308  ja      short loc_18001F344
0x18001f30a  lock inc dword ptr [r9]
0x18001f30e  test    r9, r9
0x18001f311  jz      short loc_18001F319
0x18001f313  lea     rcx, [r8+30h]
0x18001f317  jmp     short loc_18001F320
0x18001f319  xor     r8d, r8d
0x18001f31c  lea     ecx, [r8+30h]
0x18001f320  mov     rax, [r8+30h]
0x18001f324  lea     r8, [rax+r10*8]
0x18001f328  lea     r9, [rsp+58h+arg_10]
0x18001f32d  lea     rdx, [rsp+58h+arg_0]
0x18001f332  call    ?insert@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Z; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)
0x18001f337  xor     eax, eax
0x18001f339  jmp     short loc_18001F33F
0x18001f33b  mov     eax, [rsp+58h+arg_8]
0x18001f33f  add     rsp, 58h
0x18001f343  retn
0x18001f344  lea     rcx, [rsp+58h+var_20]
0x18001f349  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f34e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f351  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001f356  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001f35b  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001f362  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001f367  call    _CxxThrowException_0
```
