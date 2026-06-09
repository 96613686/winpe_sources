# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::ReplaceAll(uint,void * *)

- ea: `0x1800209b0`
- end: `0x180020bac`
- name: `?ReplaceAll@?$produce@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180017c3c`
- `0x18001fa3c`
- `0x1800209b0`
- `0x180020cdc`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::ReplaceAll(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v4; // r8
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // r12
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  signed __int64 v10; // rsi
  __int64 v11; // rcx
  unsigned __int64 v12; // r15
  __int64 v13; // rcx
  __int64 *v14; // rsi
  __int64 *i; // rdi
  __int64 result; // rax
  __int64 v17; // rcx
  __int64 v18; // r14
  signed __int64 v19; // rsi
  __int64 v20; // rcx
  __int128 v21; // [rsp+20h] [rbp-38h] BYREF
  __int64 v22; // [rsp+30h] [rbp-28h]
  int v23; // [rsp+68h] [rbp+10h] BYREF

  v4 = (a1 - 16) & -(__int64)(a1 != 0);
  v21 = 0;
  v22 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 40));
  if ( &v21 != (__int128 *)((v4 & -(__int64)(v4 != -40)) + 48) )
  {
    *(_QWORD *)&v21 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30) = 0;
    *((_QWORD *)&v21 + 1) = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38) = 0;
    v22 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40);
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
      v9 = *(__int64 **)((v4 & -(__int64)(v4 != -40)) + 0x38);
      v12 = v9 - v8;
      if ( (unsigned int)a2 > v12 )
      {
        while ( v8 != v9 )
        {
          if ( v8 != a3 )
          {
            if ( *v8 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
            v17 = *a3;
            *v8 = *a3;
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          }
          ++v8;
          ++a3;
          v9 = *(__int64 **)(v7 + 8);
        }
        v18 = v5 - v12;
        if ( v18 )
        {
          v19 = (char *)a3 - (char *)v9;
          do
          {
            v20 = *(__int64 *)((char *)v9 + v19);
            *v9 = v20;
            if ( v20 )
              (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, a2, v4, v6);
            ++v9;
            --v18;
          }
          while ( v18 );
        }
      }
      else
      {
        v9 = &v8[(unsigned int)a2];
        if ( (_DWORD)a2 )
        {
          do
          {
            if ( v8 != a3 )
            {
              if ( *v8 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
              v13 = *a3;
              *v8 = *a3;
              if ( v13 )
                (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, a2, v4, v6);
            }
            ++v8;
            ++a3;
            --v5;
          }
          while ( v5 );
        }
        v14 = *(__int64 **)(v7 + 8);
        for ( i = v9; i != v14; ++i )
        {
          if ( *i )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(i);
        }
      }
    }
    else
    {
      std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(
        (v4 & -(__int64)(v4 != -40)) + 48,
        (unsigned int)a2);
      v9 = *(__int64 **)v7;
      if ( v5 )
      {
        v10 = (char *)a3 - (char *)v9;
        do
        {
          v11 = *(__int64 *)((char *)v9 + v10);
          *v9 = v11;
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          ++v9;
          --v5;
        }
        while ( v5 );
      }
    }
    *(_QWORD *)(v7 + 8) = v9;
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>((__int64)&v21);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v23);
  }
  return result;
}

```

## disassembly

```asm
0x1800209b0  mov     r11, rsp
0x1800209b3  mov     [r11+8], rbx
0x1800209b7  mov     [r11+18h], rsi
0x1800209bb  mov     [r11+20h], rdi
0x1800209bf  push    r12
0x1800209c1  push    r14
0x1800209c3  push    r15
0x1800209c5  sub     rsp, 40h
0x1800209c9  mov     rsi, r8
0x1800209cc  lea     rax, [rcx-10h]
0x1800209d0  neg     rcx
0x1800209d3  sbb     r8, r8
0x1800209d6  and     r8, rax
0x1800209d9  lea     r9, [r8+28h]
0x1800209dd  xorps   xmm0, xmm0
0x1800209e0  movdqu  [rsp+58h+var_38], xmm0
0x1800209e6  and     qword ptr [r11-28h], 0
0x1800209eb  lock inc dword ptr [r9]
0x1800209ef  mov     rax, r9
0x1800209f2  neg     rax
0x1800209f5  sbb     rcx, rcx
0x1800209f8  and     rcx, r8
0x1800209fb  add     rcx, 30h ; '0'
0x1800209ff  lea     rax, [r11-38h]
0x180020a03  cmp     rax, rcx
0x180020a06  jz      short loc_180020A2D
0x180020a08  mov     rax, [rcx]
0x180020a0b  mov     [r11-38h], rax
0x180020a0f  and     qword ptr [rcx], 0
0x180020a13  mov     rax, [rcx+8]
0x180020a17  mov     [r11-30h], rax
0x180020a1b  and     qword ptr [rcx+8], 0
0x180020a20  mov     rax, [rcx+10h]
0x180020a24  mov     [r11-28h], rax
0x180020a28  and     qword ptr [rcx+10h], 0
0x180020a2d  mov     r14d, edx
0x180020a30  neg     r9
0x180020a33  sbb     rax, rax
0x180020a36  and     rax, r8
0x180020a39  lea     r12, [rax+30h]
0x180020a3d  mov     rdi, [r12]
0x180020a41  mov     rax, [r12+10h]
0x180020a46  sub     rax, rdi
0x180020a49  sar     rax, 3
0x180020a4d  cmp     r14, rax
0x180020a50  jbe     short loc_180020A91
0x180020a52  mov     edx, r14d
0x180020a55  mov     rcx, r12
0x180020a58  call    ?_Clear_and_reserve_geometric@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAX_K@Z; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(unsigned __int64)
0x180020a5d  mov     rbx, [r12]
0x180020a61  test    r14, r14
0x180020a64  jz      loc_180020B0D
0x180020a6a  sub     rsi, rbx
0x180020a6d  mov     rcx, [rbx+rsi]
0x180020a71  mov     [rbx], rcx
0x180020a74  test    rcx, rcx
0x180020a77  jz      short loc_180020A85
0x180020a79  mov     rax, [rcx]
0x180020a7c  mov     rax, [rax+8]
0x180020a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a85  add     rbx, 8
0x180020a89  sub     r14, 1
0x180020a8d  jnz     short loc_180020A6D
0x180020a8f  jmp     short loc_180020B0D
0x180020a91  mov     rbx, [r12+8]
0x180020a96  mov     r15, rbx
0x180020a99  sub     r15, rdi
0x180020a9c  sar     r15, 3
0x180020aa0  cmp     r14, r15
0x180020aa3  ja      loc_180020B76
0x180020aa9  lea     rbx, [rdi+r14*8]
0x180020aad  test    edx, edx
0x180020aaf  jz      short loc_180020AE9
0x180020ab1  cmp     rdi, rsi
0x180020ab4  jz      short loc_180020ADB
0x180020ab6  cmp     qword ptr [rdi], 0
0x180020aba  jz      short loc_180020AC4
0x180020abc  mov     rcx, rdi
0x180020abf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020ac4  mov     rcx, [rsi]
0x180020ac7  mov     [rdi], rcx
0x180020aca  test    rcx, rcx
0x180020acd  jz      short loc_180020ADB
0x180020acf  mov     rax, [rcx]
0x180020ad2  mov     rax, [rax+8]
0x180020ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020adb  add     rdi, 8
0x180020adf  add     rsi, 8
0x180020ae3  sub     r14, 1
0x180020ae7  jnz     short loc_180020AB1
0x180020ae9  mov     rsi, [r12+8]
0x180020aee  mov     rdi, rbx
0x180020af1  cmp     rbx, rsi
0x180020af4  jz      short loc_180020B0D
0x180020af6  cmp     qword ptr [rdi], 0
0x180020afa  jz      short loc_180020B04
0x180020afc  mov     rcx, rdi
0x180020aff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020b04  add     rdi, 8
0x180020b08  cmp     rdi, rsi
0x180020b0b  jnz     short loc_180020AF6
0x180020b0d  mov     [r12+8], rbx
0x180020b12  lea     rcx, [rsp+58h+var_38]
0x180020b17  call    ??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(void)
0x180020b1c  xor     eax, eax
0x180020b1e  jmp     short loc_180020B24
0x180020b20  mov     eax, [rsp+58h+arg_8]
0x180020b24  mov     rbx, [rsp+58h+arg_0]
0x180020b29  mov     rsi, [rsp+58h+arg_10]
0x180020b2e  mov     rdi, [rsp+58h+arg_18]
0x180020b33  add     rsp, 40h
0x180020b37  pop     r15
0x180020b39  pop     r14
0x180020b3b  pop     r12
0x180020b3d  retn
0x180020b3f  cmp     rdi, rsi
0x180020b42  jz      short loc_180020B69
0x180020b44  cmp     qword ptr [rdi], 0
0x180020b48  jz      short loc_180020B52
0x180020b4a  mov     rcx, rdi
0x180020b4d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020b52  mov     rcx, [rsi]
0x180020b55  mov     [rdi], rcx
0x180020b58  test    rcx, rcx
0x180020b5b  jz      short loc_180020B69
0x180020b5d  mov     rax, [rcx]
0x180020b60  mov     rax, [rax+8]
0x180020b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b69  add     rdi, 8
0x180020b6d  add     rsi, 8
0x180020b71  mov     rbx, [r12+8]
0x180020b76  cmp     rdi, rbx
0x180020b79  jnz     short loc_180020B3F
0x180020b7b  sub     r14, r15
0x180020b7e  jz      short loc_180020B0D
0x180020b80  sub     rsi, rbx
0x180020b83  mov     rcx, [rbx+rsi]
0x180020b87  mov     [rbx], rcx
0x180020b8a  test    rcx, rcx
0x180020b8d  jz      short loc_180020B9B
0x180020b8f  mov     rax, [rcx]
0x180020b92  mov     rax, [rax+8]
0x180020b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b9b  add     rbx, 8
0x180020b9f  sub     r14, 1
0x180020ba3  jnz     short loc_180020B83
0x180020ba5  jmp     loc_180020B0D
```
