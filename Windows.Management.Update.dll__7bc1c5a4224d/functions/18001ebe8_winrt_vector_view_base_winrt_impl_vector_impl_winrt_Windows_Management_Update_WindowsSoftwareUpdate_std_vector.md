# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x18001ebe8`
- end: `0x18001ec7b`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@QEBA?AUWindowsSoftwareUpdate@Update@Management@Windows@2@I@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001eb10`
- `0x18001eb80`

## callees

- `0x18000340c`
- `0x180014eb4`
- `0x18001e6ec`
- `0x18001ebe8`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  const struct winrt::impl::slim_source_location *v10; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v12[40]; // [rsp+40h] [rbp-28h] BYREF

  v3 = a3;
  v5 = a1 + 16;
  v6 = a1 + 8;
  if ( !a1 )
  {
    v5 = 56;
    v6 = 48;
  }
  if ( (unsigned int)v3 >= (unsigned int)((__int64)(*(_QWORD *)v5 - *(_QWORD *)v6) >> 3) )
  {
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v12);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v10);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _mm_lfence();
  v7 = a1 + 8;
  if ( !a1 )
    v7 = 48;
  v8 = *(_QWORD *)(*(_QWORD *)v7 + 8 * v3);
  *a2 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  return a2;
}

```

## disassembly

```asm
0x18001ebe8  push    rbx
0x18001ebea  sub     rsp, 60h
0x18001ebee  test    rcx, rcx
0x18001ebf1  mov     r9d, r8d
0x18001ebf4  mov     rbx, rdx
0x18001ebf7  lea     rax, [rcx+10h]
0x18001ebfb  mov     edx, 38h ; '8'
0x18001ec00  lea     r8, [rcx+8]
0x18001ec04  cmovz   rax, rdx
0x18001ec08  mov     edx, 30h ; '0'
0x18001ec0d  cmovz   r8, rdx
0x18001ec11  mov     rax, [rax]
0x18001ec14  sub     rax, [r8]
0x18001ec17  sar     rax, 3
0x18001ec1b  cmp     r9d, eax
0x18001ec1e  jnb     short loc_18001EC52
0x18001ec20  lfence
0x18001ec23  test    rcx, rcx
0x18001ec26  lea     rax, [rcx+8]
0x18001ec2a  cmovz   rax, rdx
0x18001ec2e  mov     rax, [rax]
0x18001ec31  mov     rcx, [rax+r9*8]
0x18001ec35  mov     [rbx], rcx
0x18001ec38  test    rcx, rcx
0x18001ec3b  jz      short loc_18001EC49
0x18001ec3d  mov     rax, [rcx]
0x18001ec40  mov     rax, [rax+8]
0x18001ec44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec49  mov     rax, rbx
0x18001ec4c  add     rsp, 60h
0x18001ec50  pop     rbx
0x18001ec51  retn
0x18001ec52  lea     rcx, [rsp+68h+var_28]
0x18001ec57  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ec5c  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ec5f  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001ec64  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001ec69  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001ec70  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001ec75  call    _CxxThrowException_0
```
