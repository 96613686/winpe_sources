# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(uint,void *)

- ea: `0x180013060`
- end: `0x1800131fa`
- name: `?SetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000503c`
- `0x18000509c`
- `0x180005108`
- `0x18000f798`
- `0x180013060`
- `0x1800139ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800131ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800131b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800131ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800131b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(
        __int64 a1,
        struct winrt::impl::hstring_header *a2,
        winrt::impl *a3)
{
  __int64 v3; // r10
  volatile signed __int32 *v4; // r9
  __int64 v5; // r14
  __int64 v6; // rsi
  volatile signed __int32 *v7; // rax
  struct winrt::impl::hstring_header *v8; // r15
  volatile signed __int32 *v9; // rdi
  int v10; // ecx
  HANDLE ProcessHeap; // rax
  int v12; // ebx
  HANDLE v13; // rax
  __int64 result; // rax
  volatile signed __int32 *lpMem; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+30h] [rbp-48h] BYREF
  const char *v17; // [rsp+38h] [rbp-40h]
  __int64 v18; // [rsp+40h] [rbp-38h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-30h] BYREF
  int v20; // [rsp+88h] [rbp+10h] BYREF

  try
  {
    v3 = (a1 - 16) & -(__int64)(a1 != 0);
    v4 = (volatile signed __int32 *)(v3 + 40);
    v5 = (unsigned int)a2;
    if ( (unsigned int)a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38)
                                                        - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3) )
    {
      v16 = 1699;
      v17 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
      v18 = 0;
      winrt::hresult_out_of_bounds::hresult_out_of_bounds(
        (winrt::hresult_out_of_bounds *)pExceptionObject,
        (const struct winrt::impl::slim_source_location *)&v16);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    _InterlockedIncrement(v4);
    v6 = *(_QWORD *)((v3 & -(__int64)(v4 != 0)) + 0x30);
    v7 = *(volatile signed __int32 **)(v6 + 8LL * (unsigned int)a2);
    *(_QWORD *)(v6 + 8LL * (unsigned int)a2) = 0;
    lpMem = v7;
    v8 = winrt::impl::duplicate_hstring(a3, a2);
    v9 = *(volatile signed __int32 **)(v6 + 8 * v5);
    if ( v9 )
    {
      v10 = _InterlockedDecrement(v9 + 6);
      if ( v10 )
      {
        if ( v10 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v9);
      }
    }
    *(_QWORD *)(v6 + 8 * v5) = v8;
    if ( lpMem )
    {
      v12 = _InterlockedDecrement(lpMem + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        v13 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v13, 0, (LPVOID)lpMem);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v20);
  }
  return result;
}

```

## disassembly

```asm
0x180013060  mov     r11, rsp
0x180013063  mov     [r11+8], rbx
0x180013067  mov     [r11+18h], rsi
0x18001306b  push    rdi
0x18001306c  push    r14
0x18001306e  push    r15
0x180013070  sub     rsp, 60h
0x180013074  mov     r15, r8
0x180013077  lea     rax, [rcx-10h]
0x18001307b  neg     rcx
0x18001307e  sbb     r10, r10
0x180013081  and     r10, rax
0x180013084  lea     r9, [r10+28h]
0x180013088  mov     [rsp+78h+var_50], 0
0x18001308d  mov     rax, r9
0x180013090  neg     rax
0x180013093  sbb     rcx, rcx
0x180013096  and     rcx, r10
0x180013099  mov     r14d, edx
0x18001309c  mov     rax, [rcx+38h]
0x1800130a0  sub     rax, [rcx+30h]
0x1800130a4  sar     rax, 3
0x1800130a8  cmp     r14, rax
0x1800130ab  jnb     loc_1800131BF
0x1800130b1  lock inc dword ptr [r9]
0x1800130b5  neg     r9
0x1800130b8  sbb     rax, rax
0x1800130bb  and     rax, r10
0x1800130be  mov     rsi, [rax+30h]
0x1800130c2  or      ebx, 0FFFFFFFFh
0x1800130c5  cmp     [rsp+78h+var_50], 0
0x1800130ca  jz      short loc_18001310D
0x1800130cc  mov     rdi, [rsp+78h+lpMem]
0x1800130d1  test    rdi, rdi
0x1800130d4  jz      short loc_180013108
0x1800130d6  mov     eax, ebx
0x1800130d8  lock xadd [rdi+18h], eax
0x1800130dd  sub     eax, 1
0x1800130e0  jnz     short loc_1800130F7
0x1800130e2  nop
0x1800130e3  call    WINRT_IMPL_GetProcessHeap
0x1800130e8  mov     rcx, rax; hHeap
0x1800130eb  mov     r8, rdi; lpMem
0x1800130ee  xor     edx, edx; dwFlags
0x1800130f0  call    WINRT_IMPL_HeapFree
0x1800130f5  jmp     short loc_1800130FF
0x1800130f7  test    eax, eax
0x1800130f9  js      loc_1800131AD
0x1800130ff  mov     [rsp+78h+lpMem], 0
0x180013108  mov     [rsp+78h+var_50], 0
0x18001310d  mov     rax, [rsi+r14*8]
0x180013111  mov     qword ptr [rsi+r14*8], 0
0x180013119  mov     [rsp+78h+lpMem], rax
0x18001311e  mov     [rsp+78h+var_50], 1
0x180013123  mov     rcx, r15; this
0x180013126  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001312b  mov     r15, rax
0x18001312e  mov     rdi, [rsi+r14*8]
0x180013132  test    rdi, rdi
0x180013135  jz      short loc_180013156
0x180013137  mov     ecx, ebx
0x180013139  lock xadd [rdi+18h], ecx
0x18001313e  sub     ecx, 1
0x180013141  jnz     short loc_1800131A9
0x180013143  nop
0x180013144  call    WINRT_IMPL_GetProcessHeap
0x180013149  mov     rcx, rax; hHeap
0x18001314c  mov     r8, rdi; lpMem
0x18001314f  xor     edx, edx; dwFlags
0x180013151  call    WINRT_IMPL_HeapFree
0x180013156  mov     [rsi+r14*8], r15
0x18001315a  cmp     [rsp+78h+var_50], 0
0x18001315f  jz      short loc_180013188
0x180013161  mov     rdi, [rsp+78h+lpMem]
0x180013166  test    rdi, rdi
0x180013169  jz      short loc_180013188
0x18001316b  lock xadd [rdi+18h], ebx
0x180013170  sub     ebx, 1
0x180013173  jnz     short loc_1800131B4
0x180013175  nop
0x180013176  call    WINRT_IMPL_GetProcessHeap
0x18001317b  mov     rcx, rax; hHeap
0x18001317e  mov     r8, rdi; lpMem
0x180013181  xor     edx, edx; dwFlags
0x180013183  call    WINRT_IMPL_HeapFree
0x180013188  xor     eax, eax
0x18001318a  jmp     short loc_180013193
0x18001318c  mov     eax, [rsp+78h+arg_8]
0x180013193  lea     r11, [rsp+78h+var_18]
0x180013198  mov     rbx, [r11+20h]
0x18001319c  mov     rsi, [r11+30h]
0x1800131a0  mov     rsp, r11
0x1800131a3  pop     r15
0x1800131a5  pop     r14
0x1800131a7  pop     rdi
0x1800131a8  retn
0x1800131a9  test    ecx, ecx
0x1800131ab  jns     short loc_180013156
0x1800131ad  call    cs:__imp_abort
0x1800131b4  test    ebx, ebx
0x1800131b6  jns     short loc_180013188
0x1800131b8  call    cs:__imp_abort
0x1800131bf  mov     [rsp+78h+var_48], 6A3h
0x1800131c7  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800131ce  mov     [r11-40h], rax
0x1800131d2  mov     qword ptr [r11-38h], 0
0x1800131da  lea     rdx, [r11-48h]; struct winrt::impl::slim_source_location *
0x1800131de  lea     rcx, [r11-30h]; this
0x1800131e2  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800131e7  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800131ee  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800131f3  call    _CxxThrowException_0
```
