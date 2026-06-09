# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::Windows::Management::Update::WindowsSoftwareUpdate>)

- ea: `0x180020144`
- end: `0x180020221`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@2@@Z`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001fed0`
- `0x18001ff70`

## callees

- `0x180017c3c`
- `0x180020144`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r11
  __int64 v4; // rax
  __int64 v5; // r9
  unsigned int v8; // ebp
  __int64 v9; // rax
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned int v15; // esi
  __int64 *i; // rdi
  __int64 v17; // rcx

  v3 = a2;
  v4 = a1 + 16;
  v5 = a1 + 8;
  if ( !a1 )
  {
    v5 = 48;
    v4 = 56;
  }
  if ( a2 >= (unsigned int)((__int64)(*(_QWORD *)v4 - *(_QWORD *)v5) >> 3) )
    return 0;
  v8 = *(_DWORD *)(a3 + 8);
  v9 = a1 + 8;
  v10 = *(__int64 **)a3;
  v11 = a1 + 16;
  if ( !a1 )
  {
    v11 = 56;
    v9 = 48;
  }
  v12 = *(_QWORD *)v11 - *(_QWORD *)v9;
  v13 = a1 + 8;
  v14 = (v12 >> 3) - v3;
  if ( v8 >= v14 )
    v8 = v14;
  v15 = v8;
  if ( !a1 )
    v13 = 48;
  if ( v8 )
  {
    for ( i = (__int64 *)(*(_QWORD *)v13 + 8 * v3); ; ++i )
    {
      if ( v10 != i )
      {
        if ( *v10 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
        v17 = *i;
        *v10 = *i;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      }
      ++v10;
      if ( !--v15 )
        break;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180020144  mov     [rsp+arg_0], rbx
0x180020149  mov     [rsp+arg_8], rbp
0x18002014e  mov     [rsp+arg_10], rsi
0x180020153  push    rdi
0x180020154  sub     rsp, 20h
0x180020158  test    rcx, rcx
0x18002015b  mov     r11d, edx
0x18002015e  mov     edi, 30h ; '0'
0x180020163  lea     rax, [rcx+10h]
0x180020167  lea     r9, [rcx+8]
0x18002016b  mov     r10, rcx
0x18002016e  cmovz   r9, rdi
0x180020172  lea     edx, [rdi+8]
0x180020175  cmovz   rax, rdx
0x180020179  mov     rax, [rax]
0x18002017c  sub     rax, [r9]
0x18002017f  sar     rax, 3
0x180020183  cmp     r11d, eax
0x180020186  jb      short loc_18002018C
0x180020188  xor     eax, eax
0x18002018a  jmp     short loc_18002020B
0x18002018c  mov     ebp, [r8+8]
0x180020190  lea     rax, [r10+8]
0x180020194  mov     rbx, [r8]
0x180020197  add     rcx, 10h
0x18002019b  test    r10, r10
0x18002019e  cmovz   rcx, rdx
0x1800201a2  cmovz   rax, rdi
0x1800201a6  mov     rdx, [rcx]
0x1800201a9  sub     rdx, [rax]
0x1800201ac  lea     rax, [r10+8]
0x1800201b0  sar     rdx, 3
0x1800201b4  sub     edx, r11d
0x1800201b7  cmp     ebp, edx
0x1800201b9  cmovnb  ebp, edx
0x1800201bc  test    r10, r10
0x1800201bf  mov     esi, ebp
0x1800201c1  cmovz   rax, rdi
0x1800201c5  mov     rcx, [rax]
0x1800201c8  test    ebp, ebp
0x1800201ca  jz      short loc_180020209
0x1800201cc  lea     rdi, [rcx+r11*8]
0x1800201d0  cmp     rbx, rdi
0x1800201d3  jz      short loc_1800201FA
0x1800201d5  cmp     qword ptr [rbx], 0
0x1800201d9  jz      short loc_1800201E3
0x1800201db  mov     rcx, rbx
0x1800201de  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800201e3  mov     rcx, [rdi]
0x1800201e6  mov     [rbx], rcx
0x1800201e9  test    rcx, rcx
0x1800201ec  jz      short loc_1800201FA
0x1800201ee  mov     rax, [rcx]
0x1800201f1  mov     rax, [rax+8]
0x1800201f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201fa  add     rbx, 8
0x1800201fe  add     esi, 0FFFFFFFFh
0x180020201  jz      short loc_180020209
0x180020203  add     rdi, 8
0x180020207  jmp     short loc_1800201D0
0x180020209  mov     eax, ebp
0x18002020b  mov     rbx, [rsp+28h+arg_0]
0x180020210  mov     rbp, [rsp+28h+arg_8]
0x180020215  mov     rsi, [rsp+28h+arg_10]
0x18002021a  add     rsp, 20h
0x18002021e  pop     rdi
0x18002021f  retn
```
