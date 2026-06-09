# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetMany(uint,void * *,uint *)

- ea: `0x18001ed90`
- end: `0x18001eea7`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800033e8`
- `0x18000340c`
- `0x180014eb4`
- `0x180016fe4`
- `0x18001e6a8`
- `0x18001ed90`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int *a4)
{
  __int64 *v5; // rbx
  unsigned int v6; // edi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v20[80]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+10h]

  v5 = a3;
  v6 = a2;
  memset_0(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
  {
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v20);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v16);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v17 = &v18;
      *((_DWORD *)v17 + 38) = *(_DWORD *)winrt::to_hresult(v17 + 19);
      return v21;
    }
  }
  v10 = a1 + 24;
  if ( !a1 )
    v10 = 40;
  v11 = *(__int64 **)v10;
  v12 = a1 + 32;
  if ( !a1 )
    v12 = 48;
  if ( v6 >= (unsigned int)((__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3) )
    v6 = (__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3;
  v13 = v6;
  if ( v6 )
  {
    while ( 1 )
    {
      if ( v5 != v11 )
      {
        if ( *v5 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
        v14 = *v11;
        *v5 = *v11;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      }
      if ( !--v13 )
        break;
      ++v5;
      ++v11;
    }
  }
  *(_QWORD *)v10 += 8LL * v6;
  *a4 = v6;
  return 0;
}

```

## disassembly

```asm
0x18001ed90  push    rbx
0x18001ed92  push    rsi
0x18001ed93  push    rdi
0x18001ed94  push    r12
0x18001ed96  push    r14
0x18001ed98  push    r15
0x18001ed9a  sub     rsp, 58h
0x18001ed9e  mov     r12, r9
0x18001eda1  mov     rbx, r8
0x18001eda4  mov     edi, edx
0x18001eda6  mov     r14, rcx
0x18001eda9  mov     r8d, edi
0x18001edac  shl     r8, 3; Size
0x18001edb0  xor     edx, edx; Val
0x18001edb2  mov     rcx, rbx; void *
0x18001edb5  call    memset_0
0x18001edba  lea     r8, [r14+8]
0x18001edbe  mov     eax, 18h
0x18001edc3  test    r14, r14
0x18001edc6  cmovz   r8, rax
0x18001edca  lea     rax, [r14+10h]
0x18001edce  mov     ecx, 20h ; ' '
0x18001edd3  cmovz   rax, rcx
0x18001edd7  mov     rax, [rax]
0x18001edda  mov     ecx, [rax+28h]
0x18001eddd  nop
0x18001edde  cmp     ecx, [r8]
0x18001ede1  jnz     loc_18001EE7D
0x18001ede7  lea     r15, [r14+18h]
0x18001edeb  mov     eax, 28h ; '('
0x18001edf0  test    r14, r14
0x18001edf3  cmovz   r15, rax
0x18001edf7  mov     rsi, [r15]
0x18001edfa  lea     rax, [r14+20h]
0x18001edfe  mov     ecx, 30h ; '0'
0x18001ee03  cmovz   rax, rcx
0x18001ee07  mov     rcx, [rax]
0x18001ee0a  sub     rcx, rsi
0x18001ee0d  sar     rcx, 3
0x18001ee11  cmp     edi, ecx
0x18001ee13  cmovnb  edi, ecx
0x18001ee16  mov     r14d, edi
0x18001ee19  test    edi, edi
0x18001ee1b  jz      short loc_18001EE57
0x18001ee1d  cmp     rbx, rsi
0x18001ee20  jz      short loc_18001EE47
0x18001ee22  cmp     qword ptr [rbx], 0
0x18001ee26  jz      short loc_18001EE30
0x18001ee28  mov     rcx, rbx
0x18001ee2b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ee30  mov     rcx, [rsi]
0x18001ee33  mov     [rbx], rcx
0x18001ee36  test    rcx, rcx
0x18001ee39  jz      short loc_18001EE47
0x18001ee3b  mov     rax, [rcx]
0x18001ee3e  mov     rax, [rax+8]
0x18001ee42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee47  add     r14d, 0FFFFFFFFh
0x18001ee4b  jz      short loc_18001EE57
0x18001ee4d  add     rbx, 8
0x18001ee51  add     rsi, 8
0x18001ee55  jmp     short loc_18001EE1D
0x18001ee57  mov     eax, edi
0x18001ee59  shl     rax, 3
0x18001ee5d  add     [r15], rax
0x18001ee60  mov     [r12], edi
0x18001ee64  xor     eax, eax
0x18001ee66  jmp     short loc_18001EE6F
0x18001ee68  mov     eax, [rsp+88h+arg_8]
0x18001ee6f  add     rsp, 58h
0x18001ee73  pop     r15
0x18001ee75  pop     r14
0x18001ee77  pop     r12
0x18001ee79  pop     rdi
0x18001ee7a  pop     rsi
0x18001ee7b  pop     rbx
0x18001ee7c  retn
0x18001ee7d  lea     rcx, [rsp+88h+var_50]
0x18001ee82  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ee87  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ee8a  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001ee8f  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x18001ee94  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18001ee9b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001eea0  call    _CxxThrowException_0
```
