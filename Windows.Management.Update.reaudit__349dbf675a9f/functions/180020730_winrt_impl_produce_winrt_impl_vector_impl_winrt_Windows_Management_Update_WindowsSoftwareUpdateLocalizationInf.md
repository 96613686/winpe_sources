# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAt(uint)

- ea: `0x180020730`
- end: `0x18002087e`
- name: `?RemoveAt@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800035f0`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001f9d0`
- `0x180020730`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // rsi
  volatile signed __int32 *v3; // rdi
  __int64 v4; // rcx
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 *v8; // r14
  __int64 *i; // rax
  __int64 *v10; // rsi
  __int64 v11; // rax
  __int64 *v12; // rcx
  const struct winrt::impl::slim_source_location *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // [rsp+20h] [rbp-48h] BYREF
  char v17; // [rsp+28h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v17 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v19);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v14);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v15 + 120) = *(_DWORD *)winrt::to_hresult(&v21);
      return v21;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (__int64 *)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  v16 = v6;
  v17 = 1;
  v7 = v2 & -(__int64)(v3 != 0);
  v8 = *(__int64 **)(v7 + 56);
  for ( i = v5 + 1; i != v8; i = v10 + 1 )
  {
    v10 = v5 + 1;
    if ( *v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
    v11 = *v10;
    *v10 = 0;
    *v5++ = v11;
  }
  v12 = (__int64 *)(*(_QWORD *)(v7 + 56) - 8LL);
  if ( *v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v12);
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v17 && v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  return 0;
}

```

## disassembly

```asm
0x180020730  mov     r11, rsp
0x180020733  mov     [r11+8], rbx
0x180020737  mov     [r11+18h], rsi
0x18002073b  mov     [r11+20h], rdi
0x18002073f  push    r14
0x180020741  sub     rsp, 60h
0x180020745  lea     rax, [rcx-10h]
0x180020749  neg     rcx
0x18002074c  sbb     rsi, rsi
0x18002074f  and     rsi, rax
0x180020752  lea     rdi, [rsi+28h]
0x180020756  mov     [rsp+68h+var_40], 0
0x18002075b  mov     rax, rdi
0x18002075e  neg     rax
0x180020761  sbb     rcx, rcx
0x180020764  and     rcx, rsi
0x180020767  mov     rax, [rcx+38h]
0x18002076b  sub     rax, [rcx+30h]
0x18002076f  sar     rax, 3
0x180020773  mov     ecx, edx
0x180020775  cmp     rcx, rax
0x180020778  jnb     loc_180020855
0x18002077e  lock inc dword ptr [rdi]
0x180020781  mov     rax, rdi
0x180020784  neg     rax
0x180020787  sbb     rax, rax
0x18002078a  and     rax, rsi
0x18002078d  mov     rax, [rax+30h]
0x180020791  lea     rbx, [rax+rcx*8]
0x180020795  cmp     [rsp+68h+var_40], 0
0x18002079a  jz      short loc_1800207B3
0x18002079c  cmp     [rsp+68h+var_48], 0
0x1800207a2  jz      short loc_1800207AE
0x1800207a4  lea     rcx, [rsp+68h+var_48]
0x1800207a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800207ae  mov     [rsp+68h+var_40], 0
0x1800207b3  mov     rax, [rbx]
0x1800207b6  and     qword ptr [rbx], 0
0x1800207ba  mov     [rsp+68h+var_48], rax
0x1800207bf  mov     [rsp+68h+var_40], 1
0x1800207c4  neg     rdi
0x1800207c7  sbb     rdi, rdi
0x1800207ca  and     rdi, rsi
0x1800207cd  mov     r14, [rdi+38h]
0x1800207d1  lea     rax, [rbx+8]
0x1800207d5  jmp     short loc_1800207FF
0x1800207d7  lea     rsi, [rbx+8]
0x1800207db  cmp     rbx, rsi
0x1800207de  jz      short loc_1800207F8
0x1800207e0  cmp     qword ptr [rbx], 0
0x1800207e4  jz      short loc_1800207EE
0x1800207e6  mov     rcx, rbx
0x1800207e9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800207ee  mov     rax, [rsi]
0x1800207f1  and     qword ptr [rsi], 0
0x1800207f5  mov     [rbx], rax
0x1800207f8  mov     rbx, rsi
0x1800207fb  lea     rax, [rsi+8]
0x1800207ff  cmp     rax, r14
0x180020802  jnz     short loc_1800207D7
0x180020804  mov     rcx, [rdi+38h]
0x180020808  sub     rcx, 8
0x18002080c  cmp     qword ptr [rcx], 0
0x180020810  jz      short loc_180020817
0x180020812  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020817  add     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFF8h
0x18002081c  cmp     [rsp+68h+var_40], 0
0x180020821  jz      short loc_180020835
0x180020823  cmp     [rsp+68h+var_48], 0
0x180020829  jz      short loc_180020835
0x18002082b  lea     rcx, [rsp+68h+var_48]
0x180020830  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020835  xor     eax, eax
0x180020837  jmp     short loc_18002083D
0x180020839  mov     eax, [rsp+68h+arg_8]
0x18002083d  lea     r11, [rsp+68h+var_8]
0x180020842  mov     rbx, [r11+10h]
0x180020846  mov     rsi, [r11+20h]
0x18002084a  mov     rdi, [r11+28h]
0x18002084e  mov     rsp, r11
0x180020851  pop     r14
0x180020853  retn
0x180020855  lea     rcx, [r11-20h]
0x180020859  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002085e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020861  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180020866  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18002086b  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180020872  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020877  call    _CxxThrowException_0
```
