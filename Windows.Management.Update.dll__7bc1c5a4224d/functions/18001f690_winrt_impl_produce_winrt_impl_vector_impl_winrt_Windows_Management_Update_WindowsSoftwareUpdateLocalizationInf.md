# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::ReplaceAll(uint,void * *)

- ea: `0x18001f690`
- end: `0x18001f87e`
- name: `?ReplaceAll@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180016fe4`
- `0x18001e75c`
- `0x18001f690`
- `0x18001f9b0`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::ReplaceAll(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v4; // r9
  __int64 v5; // r14
  __int64 v6; // r8
  __int64 v7; // r15
  __int64 *v8; // rbx
  __int64 *k; // rdi
  __int64 v10; // rcx
  unsigned __int64 v11; // r12
  __int64 v12; // rcx
  __int64 *v13; // rsi
  __int64 *j; // rbx
  __int64 result; // rax
  __int64 v16; // rcx
  __int64 i; // r14
  __int64 v18; // rcx
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]
  int v21; // [rsp+88h] [rbp+10h] BYREF

  v4 = (a1 - 16) & -(__int64)(a1 != 0);
  v19 = 0;
  v20 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 40));
  if ( &v19 != (__int128 *)((v4 & -(__int64)(v4 != -40)) + 48) )
  {
    *(_QWORD *)&v19 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30) = 0;
    *((_QWORD *)&v19 + 1) = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38) = 0;
    v20 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40) = 0;
  }
  try
  {
    v5 = (unsigned int)a2;
    v6 = -(v4 + 40);
    v7 = (v4 & -(__int64)(v4 != -40)) + 48;
    v8 = *(__int64 **)((v4 & -(__int64)(v4 != -40)) + 0x30);
    if ( (unsigned int)a2 <= (unsigned __int64)((__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40) - (_QWORD)v8) >> 3) )
    {
      k = *(__int64 **)((v4 & -(__int64)(v4 != -40)) + 0x38);
      v11 = k - v8;
      if ( (unsigned int)a2 > v11 )
      {
        while ( v8 != k )
        {
          if ( v8 != a3 )
          {
            if ( *v8 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
            v16 = *a3;
            *v8 = *a3;
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
          }
          ++v8;
          ++a3;
          k = *(__int64 **)(v7 + 8);
        }
        for ( i = v5 - v11; i; --i )
        {
          v18 = *a3;
          *k = *a3;
          if ( v18 )
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, a2, v6);
          ++k;
          ++a3;
        }
      }
      else
      {
        k = &v8[(unsigned int)a2];
        if ( (_DWORD)a2 )
        {
          do
          {
            if ( v8 != a3 )
            {
              if ( *v8 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
              v12 = *a3;
              *v8 = *a3;
              if ( v12 )
                (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, a2, v6);
            }
            ++v8;
            ++a3;
            --v5;
          }
          while ( v5 );
        }
        v13 = *(__int64 **)(v7 + 8);
        for ( j = k; j != v13; ++j )
        {
          if ( *j )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(j);
        }
      }
    }
    else
    {
      std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(
        (v4 & -(__int64)(v4 != -40)) + 48,
        (unsigned int)a2);
      for ( k = *(__int64 **)v7; v5; --v5 )
      {
        v10 = *a3;
        *k = *a3;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        ++k;
        ++a3;
      }
    }
    *(_QWORD *)(v7 + 8) = k;
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>((__int64)&v19);
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
0x18001f690  mov     r11, rsp
0x18001f693  push    rbx
0x18001f694  push    rsi
0x18001f695  push    rdi
0x18001f696  push    r12
0x18001f698  push    r14
0x18001f69a  push    r15
0x18001f69c  sub     rsp, 48h
0x18001f6a0  mov     rsi, r8
0x18001f6a3  lea     rax, [rcx-10h]
0x18001f6a7  neg     rcx
0x18001f6aa  sbb     r9, r9
0x18001f6ad  and     r9, rax
0x18001f6b0  lea     r8, [r9+28h]
0x18001f6b4  xorps   xmm0, xmm0
0x18001f6b7  movdqu  [rsp+78h+var_58], xmm0
0x18001f6bd  mov     qword ptr [r11-48h], 0
0x18001f6c5  lock inc dword ptr [r8]
0x18001f6c9  mov     rax, r8
0x18001f6cc  neg     rax
0x18001f6cf  sbb     rcx, rcx
0x18001f6d2  and     rcx, r9
0x18001f6d5  add     rcx, 30h ; '0'
0x18001f6d9  lea     rax, [r11-58h]
0x18001f6dd  cmp     rax, rcx
0x18001f6e0  jz      short loc_18001F710
0x18001f6e2  mov     rax, [rcx]
0x18001f6e5  mov     [r11-58h], rax
0x18001f6e9  mov     qword ptr [rcx], 0
0x18001f6f0  mov     rax, [rcx+8]
0x18001f6f4  mov     [r11-50h], rax
0x18001f6f8  mov     qword ptr [rcx+8], 0
0x18001f700  mov     rax, [rcx+10h]
0x18001f704  mov     [r11-48h], rax
0x18001f708  mov     qword ptr [rcx+10h], 0
0x18001f710  mov     r14d, edx
0x18001f713  neg     r8
0x18001f716  sbb     rax, rax
0x18001f719  and     rax, r9
0x18001f71c  lea     r15, [rax+30h]
0x18001f720  mov     rbx, [r15]
0x18001f723  mov     rax, [r15+10h]
0x18001f727  sub     rax, rbx
0x18001f72a  sar     rax, 3
0x18001f72e  cmp     r14, rax
0x18001f731  jbe     short loc_18001F771
0x18001f733  mov     edx, r14d
0x18001f736  mov     rcx, r15
0x18001f739  call    ?_Clear_and_reserve_geometric@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAX_K@Z; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(unsigned __int64)
0x18001f73e  mov     rdi, [r15]
0x18001f741  test    r14, r14
0x18001f744  jz      loc_18001F7EB
0x18001f74a  mov     rcx, [rsi]
0x18001f74d  mov     [rdi], rcx
0x18001f750  test    rcx, rcx
0x18001f753  jz      short loc_18001F761
0x18001f755  mov     rax, [rcx]
0x18001f758  mov     rax, [rax+8]
0x18001f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f761  add     rdi, 8
0x18001f765  add     rsi, 8
0x18001f769  sub     r14, 1
0x18001f76d  jnz     short loc_18001F74A
0x18001f76f  jmp     short loc_18001F7EB
0x18001f771  mov     rdi, [r15+8]
0x18001f775  mov     r12, rdi
0x18001f778  sub     r12, rbx
0x18001f77b  sar     r12, 3
0x18001f77f  cmp     r14, r12
0x18001f782  ja      loc_18001F848
0x18001f788  lea     rdi, [rbx+r14*8]
0x18001f78c  test    edx, edx
0x18001f78e  jz      short loc_18001F7C8
0x18001f790  cmp     rbx, rsi
0x18001f793  jz      short loc_18001F7BA
0x18001f795  cmp     qword ptr [rbx], 0
0x18001f799  jz      short loc_18001F7A3
0x18001f79b  mov     rcx, rbx
0x18001f79e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f7a3  mov     rcx, [rsi]
0x18001f7a6  mov     [rbx], rcx
0x18001f7a9  test    rcx, rcx
0x18001f7ac  jz      short loc_18001F7BA
0x18001f7ae  mov     rax, [rcx]
0x18001f7b1  mov     rax, [rax+8]
0x18001f7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ba  add     rbx, 8
0x18001f7be  add     rsi, 8
0x18001f7c2  sub     r14, 1
0x18001f7c6  jnz     short loc_18001F790
0x18001f7c8  mov     rsi, [r15+8]
0x18001f7cc  mov     rbx, rdi
0x18001f7cf  cmp     rdi, rsi
0x18001f7d2  jz      short loc_18001F7EB
0x18001f7d4  cmp     qword ptr [rbx], 0
0x18001f7d8  jz      short loc_18001F7E2
0x18001f7da  mov     rcx, rbx
0x18001f7dd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f7e2  add     rbx, 8
0x18001f7e6  cmp     rbx, rsi
0x18001f7e9  jnz     short loc_18001F7D4
0x18001f7eb  mov     [r15+8], rdi
0x18001f7ef  lea     rcx, [rsp+78h+var_58]
0x18001f7f4  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x18001f7f9  xor     eax, eax
0x18001f7fb  jmp     short loc_18001F804
0x18001f7fd  mov     eax, [rsp+78h+arg_8]
0x18001f804  add     rsp, 48h
0x18001f808  pop     r15
0x18001f80a  pop     r14
0x18001f80c  pop     r12
0x18001f80e  pop     rdi
0x18001f80f  pop     rsi
0x18001f810  pop     rbx
0x18001f811  retn
0x18001f812  cmp     rbx, rsi
0x18001f815  jz      short loc_18001F83C
0x18001f817  cmp     qword ptr [rbx], 0
0x18001f81b  jz      short loc_18001F825
0x18001f81d  mov     rcx, rbx
0x18001f820  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f825  mov     rcx, [rsi]
0x18001f828  mov     [rbx], rcx
0x18001f82b  test    rcx, rcx
0x18001f82e  jz      short loc_18001F83C
0x18001f830  mov     rax, [rcx]
0x18001f833  mov     rax, [rax+8]
0x18001f837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f83c  add     rbx, 8
0x18001f840  add     rsi, 8
0x18001f844  mov     rdi, [r15+8]
0x18001f848  cmp     rbx, rdi
0x18001f84b  jnz     short loc_18001F812
0x18001f84d  sub     r14, r12
0x18001f850  jz      short loc_18001F7EB
0x18001f852  mov     rcx, [rsi]
0x18001f855  mov     [rdi], rcx
0x18001f858  test    rcx, rcx
0x18001f85b  jz      short loc_18001F869
0x18001f85d  mov     rax, [rcx]
0x18001f860  mov     rax, [rax+8]
0x18001f864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f869  add     rdi, 8
0x18001f86d  add     rsi, 8
0x18001f871  sub     r14, 1
0x18001f875  jnz     short loc_18001F852
0x18001f877  jmp     loc_18001F7EB
```
