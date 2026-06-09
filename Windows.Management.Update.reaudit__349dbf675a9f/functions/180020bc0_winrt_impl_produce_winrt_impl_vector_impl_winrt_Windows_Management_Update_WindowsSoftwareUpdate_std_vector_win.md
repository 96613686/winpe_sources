# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::SetAt(uint,void *)

- ea: `0x180020bc0`
- end: `0x180020cd4`
- name: `?SetAt@?$produce@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800035f0`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001f9d0`
- `0x180020bc0`
- `0x18002c010`

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
  __int64 v6; // rcx
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
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v15);
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
0x180020bc0  mov     [rsp+arg_0], rbx
0x180020bc5  push    rdi
0x180020bc6  sub     rsp, 60h
0x180020bca  mov     rdi, r8
0x180020bcd  lea     rax, [rcx-10h]
0x180020bd1  neg     rcx
0x180020bd4  sbb     r9, r9
0x180020bd7  and     r9, rax
0x180020bda  lea     r8, [r9+28h]
0x180020bde  mov     [rsp+68h+var_40], 0
0x180020be3  mov     rax, r8
0x180020be6  neg     rax
0x180020be9  sbb     rcx, rcx
0x180020bec  and     rcx, r9
0x180020bef  mov     rax, [rcx+38h]
0x180020bf3  sub     rax, [rcx+30h]
0x180020bf7  sar     rax, 3
0x180020bfb  mov     ecx, edx
0x180020bfd  cmp     rcx, rax
0x180020c00  jnb     loc_180020CAA
0x180020c06  lock inc dword ptr [r8]
0x180020c0a  neg     r8
0x180020c0d  sbb     rax, rax
0x180020c10  and     rax, r9
0x180020c13  mov     rax, [rax+30h]
0x180020c17  lea     rbx, [rax+rcx*8]
0x180020c1b  cmp     [rsp+68h+var_40], 0
0x180020c20  jz      short loc_180020C39
0x180020c22  cmp     [rsp+68h+var_48], 0
0x180020c28  jz      short loc_180020C34
0x180020c2a  lea     rcx, [rsp+68h+var_48]
0x180020c2f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020c34  mov     [rsp+68h+var_40], 0
0x180020c39  mov     rax, [rbx]
0x180020c3c  and     qword ptr [rbx], 0
0x180020c40  mov     [rsp+68h+var_48], rax
0x180020c45  mov     [rsp+68h+var_40], 1
0x180020c4a  lea     rax, [rsp+68h+arg_10]
0x180020c52  cmp     rbx, rax
0x180020c55  jz      short loc_180020C7D
0x180020c57  cmp     qword ptr [rbx], 0
0x180020c5b  jz      short loc_180020C65
0x180020c5d  mov     rcx, rbx
0x180020c60  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020c65  mov     [rbx], rdi
0x180020c68  test    rdi, rdi
0x180020c6b  jz      short loc_180020C7D
0x180020c6d  mov     rax, [rdi]
0x180020c70  mov     rcx, rdi
0x180020c73  mov     rax, [rax+8]
0x180020c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c7c  nop
0x180020c7d  cmp     [rsp+68h+var_40], 0
0x180020c82  jz      short loc_180020C96
0x180020c84  cmp     [rsp+68h+var_48], 0
0x180020c8a  jz      short loc_180020C96
0x180020c8c  lea     rcx, [rsp+68h+var_48]
0x180020c91  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020c96  xor     eax, eax
0x180020c98  jmp     short loc_180020C9E
0x180020c9a  mov     eax, [rsp+68h+arg_8]
0x180020c9e  mov     rbx, [rsp+68h+arg_0]
0x180020ca3  add     rsp, 60h
0x180020ca7  pop     rdi
0x180020ca8  retn
0x180020caa  lea     rcx, [rsp+68h+var_20]
0x180020caf  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180020cb4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020cb7  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180020cbc  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180020cc1  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180020cc8  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020ccd  call    _CxxThrowException_0
```
