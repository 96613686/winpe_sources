# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x18001fe30`
- end: `0x18001fec5`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUWindowsSoftwareUpdate@Update@Management@Windows@2@I@Z`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001fd70`
- `0x18001fdd0`

## callees

- `0x1800035f0`
- `0x180015ac0`
- `0x18001f9d0`
- `0x18001fe30`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  const struct winrt::impl::slim_source_location *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v11[40]; // [rsp+40h] [rbp-28h] BYREF

  v3 = a1 + 8;
  v4 = a1 + 16;
  if ( !a1 )
  {
    v3 = 48;
    v4 = 56;
  }
  if ( a3 >= (unsigned int)((__int64)(*(_QWORD *)v4 - *(_QWORD *)v3) >> 3) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v11);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v9);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v6 = a1 + 8;
  if ( !a1 )
    v6 = 48;
  v7 = *(_QWORD *)(*(_QWORD *)v6 + 8LL * a3);
  *a2 = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  return a2;
}

```

## disassembly

```asm
0x18001fe30  push    rbx
0x18001fe32  sub     rsp, 60h
0x18001fe36  test    rcx, rcx
0x18001fe39  lea     r9, [rcx+8]
0x18001fe3d  mov     r10, rcx
0x18001fe40  lea     rax, [rcx+10h]
0x18001fe44  mov     rbx, rdx
0x18001fe47  mov     edx, 30h ; '0'
0x18001fe4c  cmovz   r9, rdx
0x18001fe50  test    r10, r10
0x18001fe53  lea     ecx, [rdx+8]
0x18001fe56  cmovz   rax, rcx
0x18001fe5a  mov     rax, [rax]
0x18001fe5d  sub     rax, [r9]
0x18001fe60  sar     rax, 3
0x18001fe64  cmp     r8d, eax
0x18001fe67  jnb     short loc_18001FE9C
0x18001fe69  test    r10, r10
0x18001fe6c  mov     ecx, r8d
0x18001fe6f  lea     rax, [r10+8]
0x18001fe73  cmovz   rax, rdx
0x18001fe77  mov     rax, [rax]
0x18001fe7a  mov     rcx, [rax+rcx*8]
0x18001fe7e  mov     [rbx], rcx
0x18001fe81  test    rcx, rcx
0x18001fe84  jz      short loc_18001FE92
0x18001fe86  mov     rax, [rcx]
0x18001fe89  mov     rax, [rax+8]
0x18001fe8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe92  mov     rax, rbx
0x18001fe95  add     rsp, 60h
0x18001fe99  pop     rbx
0x18001fe9a  retn
0x18001fe9c  lea     rcx, [rsp+68h+var_28]
0x18001fea1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fea6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fea9  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001feae  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001feb3  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001feba  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001febf  call    _CxxThrowException_0
```
