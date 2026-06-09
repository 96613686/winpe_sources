# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetMany(uint,void * *,uint *)

- ea: `0x180020010`
- end: `0x18002013e`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800035cc`
- `0x1800035f0`
- `0x180015ac0`
- `0x180017c3c`
- `0x18001f994`
- `0x180020010`
- `0x18002c010`

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
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  const struct winrt::impl::slim_source_location *v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // [rsp+0h] [rbp-68h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+10h]

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
    v16 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v16);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v17 = &v18;
      *((_DWORD *)v17 + 30) = *(_DWORD *)winrt::to_hresult(v17 + 15);
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
      ++v5;
      if ( !--v13 )
        break;
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
0x180020010  mov     [rsp+arg_0], rbx
0x180020015  mov     [rsp+arg_10], rsi
0x18002001a  mov     [rsp+arg_18], rdi
0x18002001f  push    r12
0x180020021  push    r14
0x180020023  push    r15
0x180020025  sub     rsp, 50h
0x180020029  mov     r12, r9
0x18002002c  mov     rbx, r8
0x18002002f  mov     edi, edx
0x180020031  mov     r14, rcx
0x180020034  mov     r8d, edi
0x180020037  shl     r8, 3; Size
0x18002003b  xor     edx, edx; Val
0x18002003d  mov     rcx, rbx; void *
0x180020040  call    memset_0
0x180020045  lea     rdx, [r14+8]
0x180020049  mov     eax, 18h
0x18002004e  test    r14, r14
0x180020051  cmovz   rdx, rax
0x180020055  lea     rax, [r14+10h]
0x180020059  mov     ecx, 20h ; ' '
0x18002005e  cmovz   rax, rcx
0x180020062  mov     rcx, [rax]
0x180020065  mov     r8d, 28h ; '('
0x18002006b  mov     eax, [rcx+r8]
0x18002006f  nop
0x180020070  cmp     eax, [rdx]
0x180020072  jnz     loc_180020114
0x180020078  lea     r15, [r14+18h]
0x18002007c  test    r14, r14
0x18002007f  cmovz   r15, r8
0x180020083  mov     rsi, [r15]
0x180020086  lea     rax, [r14+20h]
0x18002008a  mov     ecx, 30h ; '0'
0x18002008f  cmovz   rax, rcx
0x180020093  mov     rcx, [rax]
0x180020096  sub     rcx, rsi
0x180020099  sar     rcx, 3
0x18002009d  cmp     edi, ecx
0x18002009f  cmovnb  edi, ecx
0x1800200a2  mov     r14d, edi
0x1800200a5  test    edi, edi
0x1800200a7  jz      short loc_1800200E3
0x1800200a9  cmp     rbx, rsi
0x1800200ac  jz      short loc_1800200D3
0x1800200ae  cmp     qword ptr [rbx], 0
0x1800200b2  jz      short loc_1800200BC
0x1800200b4  mov     rcx, rbx
0x1800200b7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800200bc  mov     rcx, [rsi]
0x1800200bf  mov     [rbx], rcx
0x1800200c2  test    rcx, rcx
0x1800200c5  jz      short loc_1800200D3
0x1800200c7  mov     rax, [rcx]
0x1800200ca  mov     rax, [rax+8]
0x1800200ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200d3  add     rbx, 8
0x1800200d7  add     r14d, 0FFFFFFFFh
0x1800200db  jz      short loc_1800200E3
0x1800200dd  add     rsi, 8
0x1800200e1  jmp     short loc_1800200A9
0x1800200e3  mov     eax, edi
0x1800200e5  shl     rax, 3
0x1800200e9  add     [r15], rax
0x1800200ec  mov     [r12], edi
0x1800200f0  xor     eax, eax
0x1800200f2  jmp     short loc_1800200F8
0x1800200f4  mov     eax, [rsp+68h+arg_8]
0x1800200f8  lea     r11, [rsp+68h+var_18]
0x1800200fd  mov     rbx, [r11+20h]
0x180020101  mov     rsi, [r11+30h]
0x180020105  mov     rdi, [r11+38h]
0x180020109  mov     rsp, r11
0x18002010c  pop     r15
0x18002010e  pop     r14
0x180020110  pop     r12
0x180020112  retn
0x180020114  lea     rcx, [rsp+68h+var_30]
0x180020119  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002011e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180020121  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180020126  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x18002012b  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180020132  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020137  call    _CxxThrowException_0
```
