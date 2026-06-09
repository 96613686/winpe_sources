# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::SetAt(uint,void *)

- ea: `0x18001f890`
- end: `0x18001f9a7`
- name: `?SetAt@?$produce@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001e6ec`
- `0x18001f890`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::SetAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v4; // r9
  volatile signed __int32 *v5; // r8
  __int64 v6; // r10
  __int64 *v7; // rbx
  __int64 v8; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  char v13; // [rsp+28h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF
  char v18; // [rsp+80h] [rbp+18h] BYREF

  v4 = (a1 - 16) & -(__int64)(a1 != 0);
  v5 = (volatile signed __int32 *)(v4 + 40);
  v13 = 0;
  v6 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38)
                                        - *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30)) >> 3) )
  {
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v15);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v10);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v11 + 120) = *(_DWORD *)winrt::to_hresult(&v17);
      return v17;
    }
  }
  _InterlockedIncrement(v5);
  v7 = (__int64 *)(*(_QWORD *)((v4 & -(__int64)(v5 != 0)) + 0x30) + 8 * v6);
  v8 = *v7;
  *v7 = 0;
  v12 = v8;
  v13 = 1;
  if ( v7 != (__int64 *)&v18 )
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = a3;
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  if ( v13 && v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return 0;
}

```

## disassembly

```asm
0x18001f890  mov     [rsp+arg_0], rbx
0x18001f895  push    rdi
0x18001f896  sub     rsp, 60h
0x18001f89a  mov     rdi, r8
0x18001f89d  lea     rax, [rcx-10h]
0x18001f8a1  neg     rcx
0x18001f8a4  sbb     r9, r9
0x18001f8a7  and     r9, rax
0x18001f8aa  lea     r8, [r9+28h]
0x18001f8ae  mov     [rsp+68h+var_40], 0
0x18001f8b3  mov     rax, r8
0x18001f8b6  neg     rax
0x18001f8b9  sbb     rcx, rcx
0x18001f8bc  and     rcx, r9
0x18001f8bf  mov     r10d, edx
0x18001f8c2  mov     rax, [rcx+38h]
0x18001f8c6  sub     rax, [rcx+30h]
0x18001f8ca  sar     rax, 3
0x18001f8ce  cmp     r10, rax
0x18001f8d1  jnb     loc_18001F97D
0x18001f8d7  lock inc dword ptr [r8]
0x18001f8db  neg     r8
0x18001f8de  sbb     rax, rax
0x18001f8e1  and     rax, r9
0x18001f8e4  mov     rax, [rax+30h]
0x18001f8e8  lea     rbx, [rax+r10*8]
0x18001f8ec  cmp     [rsp+68h+var_40], 0
0x18001f8f1  jz      short loc_18001F90A
0x18001f8f3  cmp     [rsp+68h+var_48], 0
0x18001f8f9  jz      short loc_18001F905
0x18001f8fb  lea     rcx, [rsp+68h+var_48]
0x18001f900  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f905  mov     [rsp+68h+var_40], 0
0x18001f90a  mov     rax, [rbx]
0x18001f90d  mov     qword ptr [rbx], 0
0x18001f914  mov     [rsp+68h+var_48], rax
0x18001f919  mov     [rsp+68h+var_40], 1
0x18001f91e  lea     rax, [rsp+68h+arg_10]
0x18001f926  cmp     rbx, rax
0x18001f929  jz      short loc_18001F951
0x18001f92b  cmp     qword ptr [rbx], 0
0x18001f92f  jz      short loc_18001F939
0x18001f931  mov     rcx, rbx
0x18001f934  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f939  mov     [rbx], rdi
0x18001f93c  test    rdi, rdi
0x18001f93f  jz      short loc_18001F951
0x18001f941  mov     rax, [rdi]
0x18001f944  mov     rcx, rdi
0x18001f947  mov     rax, [rax+8]
0x18001f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f950  nop
0x18001f951  cmp     [rsp+68h+var_40], 0
0x18001f956  jz      short loc_18001F96A
0x18001f958  cmp     [rsp+68h+var_48], 0
0x18001f95e  jz      short loc_18001F96A
0x18001f960  lea     rcx, [rsp+68h+var_48]
0x18001f965  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f96a  xor     eax, eax
0x18001f96c  jmp     short loc_18001F972
0x18001f96e  mov     eax, [rsp+68h+arg_8]
0x18001f972  mov     rbx, [rsp+68h+arg_0]
0x18001f977  add     rsp, 60h
0x18001f97b  pop     rdi
0x18001f97c  retn
0x18001f97d  lea     rcx, [rsp+68h+var_20]
0x18001f982  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001f987  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001f98a  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001f98f  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001f994  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001f99b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001f9a0  call    _CxxThrowException_0
```
