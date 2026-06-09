# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(uint,void * *,uint *)

- ea: `0x180010bf0`
- end: `0x180010d50`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000500c`
- `0x18000503c`
- `0x18000509c`
- `0x180005108`
- `0x18000f32c`
- `0x180010bf0`
- `0x1800139ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010cd2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010cd2`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(
        __int64 a1,
        unsigned int a2,
        volatile signed __int32 **a3,
        unsigned int *a4)
{
  volatile signed __int32 **v4; // rbx
  unsigned int v5; // edi
  struct winrt::impl::hstring_header *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r14
  winrt::impl **v11; // r15
  __int64 v12; // rax
  unsigned int v13; // r12d
  struct winrt::impl::hstring_header *v14; // r13
  volatile signed __int32 *v15; // rsi
  int v16; // ecx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-58h] BYREF
  const char *v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+88h] [rbp+10h] BYREF
  unsigned int *v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  v4 = a3;
  v5 = a2;
  memset_0(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
    {
      v19 = 1345;
      v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
      v21 = 0;
      winrt::hresult_changed_state::hresult_changed_state(
        (winrt::hresult_changed_state *)pExceptionObject,
        (const struct winrt::impl::slim_source_location *)&v19);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    v10 = a1 + 24;
    if ( !a1 )
      v10 = 40;
    v11 = *(winrt::impl ***)v10;
    v12 = a1 + 32;
    if ( !a1 )
      v12 = 48;
    if ( v5 >= (unsigned int)((__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3) )
      v5 = (__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3;
    v13 = v5;
    if ( v5 )
    {
      while ( 1 )
      {
        v14 = winrt::impl::duplicate_hstring(*v11, v7);
        v15 = *v4;
        if ( *v4 )
        {
          v16 = _InterlockedDecrement(v15 + 6);
          if ( v16 )
          {
            if ( v16 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
          }
        }
        *v4 = (volatile signed __int32 *)v14;
        if ( !--v13 )
          break;
        ++v4;
        ++v11;
      }
    }
    *(_QWORD *)v10 += 8LL * v5;
    *v24 = v5;
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
0x180010bf0  mov     [rsp+arg_0], rbx
0x180010bf5  mov     [rsp+arg_10], rsi
0x180010bfa  mov     [rsp+arg_18], r9
0x180010bff  push    rdi
0x180010c00  push    r12
0x180010c02  push    r13
0x180010c04  push    r14
0x180010c06  push    r15
0x180010c08  sub     rsp, 50h
0x180010c0c  mov     rbx, r8
0x180010c0f  mov     edi, edx
0x180010c11  mov     rsi, rcx
0x180010c14  mov     r8d, edi
0x180010c17  shl     r8, 3; Size
0x180010c1b  xor     edx, edx; Val
0x180010c1d  mov     rcx, rbx; void *
0x180010c20  call    memset_0
0x180010c25  lea     r8, [rsi+8]
0x180010c29  mov     eax, 18h
0x180010c2e  test    rsi, rsi
0x180010c31  cmovz   r8, rax
0x180010c35  lea     rax, [rsi+10h]
0x180010c39  mov     ecx, 20h ; ' '
0x180010c3e  cmovz   rax, rcx
0x180010c42  mov     rax, [rax]
0x180010c45  mov     ecx, [rax+28h]
0x180010c48  nop
0x180010c49  cmp     ecx, [r8]
0x180010c4c  jnz     loc_180010D11
0x180010c52  lea     r14, [rsi+18h]
0x180010c56  mov     eax, 28h ; '('
0x180010c5b  test    rsi, rsi
0x180010c5e  cmovz   r14, rax
0x180010c62  mov     r15, [r14]
0x180010c65  lea     rax, [rsi+20h]
0x180010c69  mov     ecx, 30h ; '0'
0x180010c6e  cmovz   rax, rcx
0x180010c72  mov     rcx, [rax]
0x180010c75  sub     rcx, r15
0x180010c78  sar     rcx, 3
0x180010c7c  cmp     edi, ecx
0x180010c7e  cmovnb  edi, ecx
0x180010c81  mov     r12d, edi
0x180010c84  test    edi, edi
0x180010c86  jz      short loc_180010CD9
0x180010c88  mov     rcx, [r15]; this
0x180010c8b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180010c90  mov     r13, rax
0x180010c93  mov     rsi, [rbx]
0x180010c96  test    rsi, rsi
0x180010c99  jz      short loc_180010CBB
0x180010c9b  or      ecx, 0FFFFFFFFh
0x180010c9e  lock xadd [rsi+18h], ecx
0x180010ca3  sub     ecx, 1
0x180010ca6  jnz     short loc_180010CCE
0x180010ca8  nop
0x180010ca9  call    WINRT_IMPL_GetProcessHeap
0x180010cae  mov     rcx, rax; hHeap
0x180010cb1  mov     r8, rsi; lpMem
0x180010cb4  xor     edx, edx; dwFlags
0x180010cb6  call    WINRT_IMPL_HeapFree
0x180010cbb  mov     [rbx], r13
0x180010cbe  add     r12d, 0FFFFFFFFh
0x180010cc2  jz      short loc_180010CD9
0x180010cc4  add     rbx, 8
0x180010cc8  add     r15, 8
0x180010ccc  jmp     short loc_180010C88
0x180010cce  test    ecx, ecx
0x180010cd0  jns     short loc_180010CBB
0x180010cd2  call    cs:__imp_abort
0x180010cd9  mov     eax, edi
0x180010cdb  shl     rax, 3
0x180010cdf  add     [r14], rax
0x180010ce2  mov     rax, [rsp+78h+arg_18]
0x180010cea  mov     [rax], edi
0x180010cec  xor     eax, eax
0x180010cee  jmp     short loc_180010CF7
0x180010cf0  mov     eax, [rsp+78h+arg_8]
0x180010cf7  lea     r11, [rsp+78h+var_28]
0x180010cfc  mov     rbx, [r11+30h]
0x180010d00  mov     rsi, [r11+40h]
0x180010d04  mov     rsp, r11
0x180010d07  pop     r15
0x180010d09  pop     r14
0x180010d0b  pop     r13
0x180010d0d  pop     r12
0x180010d0f  pop     rdi
0x180010d10  retn
0x180010d11  mov     [rsp+78h+var_58], 541h
0x180010d19  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010d20  mov     [rsp+78h+var_50], rax
0x180010d25  mov     [rsp+78h+var_48], 0
0x180010d2e  lea     rdx, [rsp+78h+var_58]; struct winrt::impl::slim_source_location *
0x180010d33  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180010d38  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180010d3d  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180010d44  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180010d49  call    _CxxThrowException_0
```
