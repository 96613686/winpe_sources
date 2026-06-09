# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::Windows::Management::Update::WindowsSoftwareUpdate>)

- ea: `0x18001eeb0`
- end: `0x18001ef58`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@2@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ec90`
- `0x18001ed10`

## callees

- `0x180016fe4`
- `0x18001eeb0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v8; // esi
  __int64 v9; // rax
  unsigned int v10; // ecx
  unsigned int v11; // ebp
  __int64 *v12; // rbx
  __int64 *i; // rdi
  __int64 v14; // rcx

  v3 = a1 + 16;
  if ( !a1 )
    v3 = 56;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  v6 = (__int64)(*(_QWORD *)v3 - *(_QWORD *)v5) >> 3;
  if ( a2 >= (unsigned int)v6 )
    return 0;
  v8 = *(_DWORD *)(a3 + 8);
  v9 = a1 + 8;
  v10 = v6 - a2;
  if ( v8 >= v10 )
    v8 = v10;
  v11 = v8;
  if ( !a1 )
    v9 = 48;
  if ( v8 )
  {
    v12 = *(__int64 **)a3;
    for ( i = (__int64 *)(*(_QWORD *)v9 + 8LL * a2); ; ++i )
    {
      if ( v12 != i )
      {
        if ( *v12 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v12);
        v14 = *i;
        *v12 = *i;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      }
      if ( !--v11 )
        break;
      ++v12;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001eeb0  push    rbx
0x18001eeb2  push    rbp
0x18001eeb3  push    rsi
0x18001eeb4  push    rdi
0x18001eeb5  sub     rsp, 28h
0x18001eeb9  test    rcx, rcx
0x18001eebc  lea     r9, [rcx+10h]
0x18001eec0  mov     r10, rcx
0x18001eec3  mov     eax, 38h ; '8'
0x18001eec8  cmovz   r9, rax
0x18001eecc  mov     r11d, 30h ; '0'
0x18001eed2  lea     rax, [rcx+8]
0x18001eed6  cmovz   rax, r11
0x18001eeda  mov     rcx, [r9]
0x18001eedd  sub     rcx, [rax]
0x18001eee0  sar     rcx, 3
0x18001eee4  cmp     edx, ecx
0x18001eee6  jb      short loc_18001EEEC
0x18001eee8  xor     eax, eax
0x18001eeea  jmp     short loc_18001EF4F
0x18001eeec  mov     esi, [r8+8]
0x18001eef0  lea     rax, [r10+8]
0x18001eef4  sub     ecx, edx
0x18001eef6  cmp     esi, ecx
0x18001eef8  cmovnb  esi, ecx
0x18001eefb  test    r10, r10
0x18001eefe  mov     ebp, esi
0x18001ef00  cmovz   rax, r11
0x18001ef04  test    esi, esi
0x18001ef06  jz      short loc_18001EF4D
0x18001ef08  mov     rax, [rax]
0x18001ef0b  mov     rbx, [r8]
0x18001ef0e  mov     ecx, edx
0x18001ef10  lea     rdi, [rax+rcx*8]
0x18001ef14  cmp     rbx, rdi
0x18001ef17  jz      short loc_18001EF3E
0x18001ef19  cmp     qword ptr [rbx], 0
0x18001ef1d  jz      short loc_18001EF27
0x18001ef1f  mov     rcx, rbx
0x18001ef22  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ef27  mov     rcx, [rdi]
0x18001ef2a  mov     [rbx], rcx
0x18001ef2d  test    rcx, rcx
0x18001ef30  jz      short loc_18001EF3E
0x18001ef32  mov     rax, [rcx]
0x18001ef35  mov     rax, [rax+8]
0x18001ef39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef3e  add     ebp, 0FFFFFFFFh
0x18001ef41  jz      short loc_18001EF4D
0x18001ef43  add     rbx, 8
0x18001ef47  add     rdi, 8
0x18001ef4b  jmp     short loc_18001EF14
0x18001ef4d  mov     eax, esi
0x18001ef4f  add     rsp, 28h
0x18001ef53  pop     rdi
0x18001ef54  pop     rsi
0x18001ef55  pop     rbp
0x18001ef56  pop     rbx
0x18001ef57  retn
```
