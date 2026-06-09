# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::get_Current(void * *)

- ea: `0x180021090`
- end: `0x18002117e`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800035f0`
- `0x180015ac0`
- `0x18001f994`
- `0x18001f9d0`
- `0x180021090`
- `0x18002c010`

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
  __int64 v14; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[24]; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp-20h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+8h]

  *a2 = 0;
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 24;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v5 + 40LL) != *(_DWORD *)v4 )
  {
    v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v17);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v11);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v13 = &v14;
      *((_DWORD *)v13 + 36) = *(_DWORD *)winrt::to_hresult(v13 + 18);
      return v19;
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
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v18);
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
0x180021090  mov     [rsp+arg_8], rbx
0x180021095  push    rdi
0x180021096  sub     rsp, 80h
0x18002109d  mov     rdi, rdx
0x1800210a0  mov     r9, rcx
0x1800210a3  and     qword ptr [rdx], 0
0x1800210a7  lea     r8, [rcx+8]
0x1800210ab  mov     eax, 18h
0x1800210b0  test    rcx, rcx
0x1800210b3  cmovz   r8, rax
0x1800210b7  lea     rax, [rcx+10h]
0x1800210bb  mov     ecx, 20h ; ' '
0x1800210c0  cmovz   rax, rcx
0x1800210c4  mov     rcx, [rax]
0x1800210c7  mov     edx, 28h ; '('
0x1800210cc  mov     eax, [rcx+rdx]
0x1800210cf  nop
0x1800210d0  cmp     eax, [r8]
0x1800210d3  jnz     short loc_18002112C
0x1800210d5  lea     rax, [r9+18h]
0x1800210d9  test    r9, r9
0x1800210dc  cmovz   rax, rdx
0x1800210e0  mov     rbx, [rax]
0x1800210e3  lea     rax, [r9+20h]
0x1800210e7  mov     ecx, 30h ; '0'
0x1800210ec  cmovz   rax, rcx
0x1800210f0  cmp     rbx, [rax]
0x1800210f3  jz      short loc_180021154
0x1800210f5  mov     rbx, [rbx]
0x1800210f8  test    rbx, rbx
0x1800210fb  jz      short loc_18002110C
0x1800210fd  mov     rax, [rbx]
0x180021100  mov     rcx, rbx
0x180021103  mov     rax, [rax+8]
0x180021107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002110c  mov     [rdi], rbx
0x18002110f  xor     eax, eax
0x180021111  jmp     short loc_18002111A
0x180021113  mov     eax, [rsp+88h+arg_0]
0x18002111a  mov     rbx, [rsp+88h+arg_8]
0x180021122  add     rsp, 80h
0x180021129  pop     rdi
0x18002112a  retn
0x18002112c  lea     rcx, [rsp+88h+var_38]
0x180021131  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180021136  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180021139  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18002113e  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180021143  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18002114a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002114f  call    _CxxThrowException_0
0x180021154  lea     rcx, [rsp+88h+var_20]
0x180021159  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002115e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180021161  lea     rcx, [rsp+88h+var_50]; this
0x180021166  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18002116b  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180021172  lea     rcx, [rsp+88h+var_50]; pExceptionObject
0x180021177  call    _CxxThrowException_0
```
