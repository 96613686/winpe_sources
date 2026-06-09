# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::get_Current(void * *)

- ea: `0x18001fdc0`
- end: `0x18001feaa`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x18001e6a8`
- `0x18001e6ec`
- `0x18001fdc0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::get_Current(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  const struct winrt::impl::slim_source_location *v11; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v17[40]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+8h]

  *a2 = 0;
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 24;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v5 + 40LL) != *(_DWORD *)v4 )
  {
    v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v17);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v11);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v13 = &v14;
      *((_DWORD *)v13 + 32) = *(_DWORD *)winrt::to_hresult(v13 + 16);
      return v18;
    }
  }
  v6 = a1 + 24;
  if ( !a1 )
    v6 = 40;
  v7 = *(__int64 **)v6;
  v8 = a1 + 32;
  if ( !a1 )
    v8 = 48;
  if ( v7 == *(__int64 **)v8 )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v17);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)v16, v12);
    throw (winrt::hresult_out_of_bounds *)v16;
  }
  v9 = *v7;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x18001fdc0  mov     [rsp+arg_8], rbx
0x18001fdc5  push    rdi
0x18001fdc6  sub     rsp, 70h
0x18001fdca  mov     rdi, rdx
0x18001fdcd  mov     r9, rcx
0x18001fdd0  mov     qword ptr [rdx], 0
0x18001fdd7  lea     r8, [rcx+8]
0x18001fddb  mov     eax, 18h
0x18001fde0  test    rcx, rcx
0x18001fde3  cmovz   r8, rax
0x18001fde7  lea     rax, [rcx+10h]
0x18001fdeb  mov     ecx, 20h ; ' '
0x18001fdf0  cmovz   rax, rcx
0x18001fdf4  mov     rax, [rax]
0x18001fdf7  mov     ecx, [rax+28h]
0x18001fdfa  nop
0x18001fdfb  cmp     ecx, [r8]
0x18001fdfe  jnz     short loc_18001FE58
0x18001fe00  lea     rax, [r9+18h]
0x18001fe04  mov     ecx, 28h ; '('
0x18001fe09  test    r9, r9
0x18001fe0c  cmovz   rax, rcx
0x18001fe10  mov     rbx, [rax]
0x18001fe13  lea     rax, [r9+20h]
0x18001fe17  mov     ecx, 30h ; '0'
0x18001fe1c  cmovz   rax, rcx
0x18001fe20  cmp     rbx, [rax]
0x18001fe23  jz      short loc_18001FE80
0x18001fe25  mov     rbx, [rbx]
0x18001fe28  test    rbx, rbx
0x18001fe2b  jz      short loc_18001FE3C
0x18001fe2d  mov     rax, [rbx]
0x18001fe30  mov     rcx, rbx
0x18001fe33  mov     rax, [rax+8]
0x18001fe37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe3c  mov     [rdi], rbx
0x18001fe3f  xor     eax, eax
0x18001fe41  jmp     short loc_18001FE4A
0x18001fe43  mov     eax, [rsp+78h+arg_0]
0x18001fe4a  mov     rbx, [rsp+78h+arg_8]
0x18001fe52  add     rsp, 70h
0x18001fe56  pop     rdi
0x18001fe57  retn
0x18001fe58  lea     rcx, [rsp+78h+var_28]
0x18001fe5d  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fe62  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fe65  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001fe6a  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x18001fe6f  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18001fe76  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001fe7b  call    _CxxThrowException_0
0x18001fe80  lea     rcx, [rsp+78h+var_28]
0x18001fe85  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fe8a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fe8d  lea     rcx, [rsp+78h+var_40]; this
0x18001fe92  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001fe97  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001fe9e  lea     rcx, [rsp+78h+var_40]; pExceptionObject
0x18001fea3  call    _CxxThrowException_0
```
