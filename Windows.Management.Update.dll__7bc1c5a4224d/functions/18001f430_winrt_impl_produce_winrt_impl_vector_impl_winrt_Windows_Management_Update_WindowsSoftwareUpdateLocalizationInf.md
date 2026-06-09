# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAt(uint)

- ea: `0x18001f430`
- end: `0x18001f56d`
- name: `?RemoveAt@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001e6ec`
- `0x18001f430`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r14
  volatile signed __int32 *v3; // rdi
  __int64 v4; // r8
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 *v8; // r14
  __int64 *i; // rdi
  __int64 v10; // rax
  __int64 *v11; // rcx
  const struct winrt::impl::slim_source_location *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // [rsp+20h] [rbp-68h] BYREF
  char v16; // [rsp+28h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  char v18[64]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v20; // [rsp+98h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v16 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v18);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v13);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v14 + 152) = *(_DWORD *)winrt::to_hresult(&v20);
      return v20;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (__int64 *)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  v15 = v6;
  v16 = 1;
  v7 = v2 & ((unsigned __int128)-(__int128)(unsigned __int64)v3 >> 64);
  v8 = *(__int64 **)(v7 + 0x38);
  for ( i = v5 + 1; i != v8; ++i )
  {
    if ( v5 != i )
    {
      if ( *v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
      v10 = *i;
      *i = 0;
      *v5 = v10;
    }
    ++v5;
  }
  v11 = (__int64 *)(*(_QWORD *)(v7 + 56) - 8LL);
  if ( *v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v11);
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v16 && v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  return 0;
}

```

## disassembly

```asm
0x18001f430  push    rbx
0x18001f432  push    rsi
0x18001f433  push    rdi
0x18001f434  push    r14
0x18001f436  sub     rsp, 68h
0x18001f43a  lea     rax, [rcx-10h]
0x18001f43e  neg     rcx
0x18001f441  sbb     r14, r14
0x18001f444  and     r14, rax
0x18001f447  lea     rdi, [r14+28h]
0x18001f44b  mov     [rsp+88h+var_60], 0
0x18001f450  mov     rax, rdi
0x18001f453  neg     rax
0x18001f456  sbb     rcx, rcx
0x18001f459  and     rcx, r14
0x18001f45c  mov     r8d, edx
0x18001f45f  mov     rax, [rcx+38h]
0x18001f463  sub     rax, [rcx+30h]
0x18001f467  sar     rax, 3
0x18001f46b  cmp     r8, rax
0x18001f46e  jnb     loc_18001F543
0x18001f474  lock inc dword ptr [rdi]
0x18001f477  mov     rax, rdi
0x18001f47a  neg     rax
0x18001f47d  sbb     rax, rax
0x18001f480  and     rax, r14
0x18001f483  mov     rax, [rax+30h]
0x18001f487  lea     rbx, [rax+r8*8]
0x18001f48b  cmp     [rsp+88h+var_60], 0
0x18001f490  jz      short loc_18001F4A9
0x18001f492  cmp     [rsp+88h+var_68], 0
0x18001f498  jz      short loc_18001F4A4
0x18001f49a  lea     rcx, [rsp+88h+var_68]
0x18001f49f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f4a4  mov     [rsp+88h+var_60], 0
0x18001f4a9  mov     rax, [rbx]
0x18001f4ac  mov     qword ptr [rbx], 0
0x18001f4b3  mov     [rsp+88h+var_68], rax
0x18001f4b8  mov     [rsp+88h+var_60], 1
0x18001f4bd  neg     rdi
0x18001f4c0  sbb     rsi, rsi
0x18001f4c3  and     rsi, r14
0x18001f4c6  mov     r14, [rsi+38h]
0x18001f4ca  lea     rdi, [rbx+8]
0x18001f4ce  jmp     short loc_18001F4F8
0x18001f4d0  cmp     rbx, rdi
0x18001f4d3  jz      short loc_18001F4F0
0x18001f4d5  cmp     qword ptr [rbx], 0
0x18001f4d9  jz      short loc_18001F4E3
0x18001f4db  mov     rcx, rbx
0x18001f4de  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f4e3  mov     rax, [rdi]
0x18001f4e6  mov     qword ptr [rdi], 0
0x18001f4ed  mov     [rbx], rax
0x18001f4f0  add     rbx, 8
0x18001f4f4  add     rdi, 8
0x18001f4f8  cmp     rdi, r14
0x18001f4fb  jnz     short loc_18001F4D0
0x18001f4fd  mov     rcx, [rsi+38h]
0x18001f501  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001f505  cmp     qword ptr [rcx], 0
0x18001f509  jz      short loc_18001F510
0x18001f50b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f510  add     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFF8h
0x18001f515  cmp     [rsp+88h+var_60], 0
0x18001f51a  jz      short loc_18001F52E
0x18001f51c  cmp     [rsp+88h+var_68], 0
0x18001f522  jz      short loc_18001F52E
0x18001f524  lea     rcx, [rsp+88h+var_68]
0x18001f529  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f52e  xor     eax, eax
0x18001f530  jmp     short loc_18001F539
0x18001f532  mov     eax, [rsp+88h+arg_8]
0x18001f539  add     rsp, 68h
0x18001f53d  pop     r14
0x18001f53f  pop     rdi
0x18001f540  pop     rsi
0x18001f541  pop     rbx
0x18001f542  retn
0x18001f543  lea     rcx, [rsp+88h+var_40]
0x18001f548  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f54d  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f550  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001f555  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001f55a  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001f561  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001f566  call    _CxxThrowException_0
```
