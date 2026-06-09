# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(uint,void *)

- ea: `0x1800143b0`
- end: `0x18001454a`
- name: `?SetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000529c`
- `0x1800052fc`
- `0x180005374`
- `0x180010964`
- `0x1800143b0`
- `0x180014864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800144fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014508`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800144fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014508`

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
0x1800143b0  mov     r11, rsp
0x1800143b3  mov     [r11+8], rbx
0x1800143b7  mov     [r11+18h], rsi
0x1800143bb  push    rdi
0x1800143bc  push    r14
0x1800143be  push    r15
0x1800143c0  sub     rsp, 60h
0x1800143c4  mov     r15, r8
0x1800143c7  lea     rax, [rcx-10h]
0x1800143cb  neg     rcx
0x1800143ce  sbb     r10, r10
0x1800143d1  and     r10, rax
0x1800143d4  lea     r9, [r10+28h]
0x1800143d8  mov     [rsp+78h+var_50], 0
0x1800143dd  mov     rax, r9
0x1800143e0  neg     rax
0x1800143e3  sbb     rcx, rcx
0x1800143e6  and     rcx, r10
0x1800143e9  mov     r14d, edx
0x1800143ec  mov     rax, [rcx+38h]
0x1800143f0  sub     rax, [rcx+30h]
0x1800143f4  sar     rax, 3
0x1800143f8  cmp     r14, rax
0x1800143fb  jnb     loc_18001450F
0x180014401  lock inc dword ptr [r9]
0x180014405  neg     r9
0x180014408  sbb     rax, rax
0x18001440b  and     rax, r10
0x18001440e  mov     rsi, [rax+30h]
0x180014412  or      ebx, 0FFFFFFFFh
0x180014415  cmp     [rsp+78h+var_50], 0
0x18001441a  jz      short loc_18001445D
0x18001441c  mov     rdi, [rsp+78h+lpMem]
0x180014421  test    rdi, rdi
0x180014424  jz      short loc_180014458
0x180014426  mov     eax, ebx
0x180014428  lock xadd [rdi+18h], eax
0x18001442d  sub     eax, 1
0x180014430  jnz     short loc_180014447
0x180014432  nop
0x180014433  call    WINRT_IMPL_GetProcessHeap
0x180014438  mov     rcx, rax; hHeap
0x18001443b  mov     r8, rdi; lpMem
0x18001443e  xor     edx, edx; dwFlags
0x180014440  call    WINRT_IMPL_HeapFree
0x180014445  jmp     short loc_18001444F
0x180014447  test    eax, eax
0x180014449  js      loc_1800144FD
0x18001444f  mov     [rsp+78h+lpMem], 0
0x180014458  mov     [rsp+78h+var_50], 0
0x18001445d  mov     rax, [rsi+r14*8]
0x180014461  mov     qword ptr [rsi+r14*8], 0
0x180014469  mov     [rsp+78h+lpMem], rax
0x18001446e  mov     [rsp+78h+var_50], 1
0x180014473  mov     rcx, r15; this
0x180014476  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001447b  mov     r15, rax
0x18001447e  mov     rdi, [rsi+r14*8]
0x180014482  test    rdi, rdi
0x180014485  jz      short loc_1800144A6
0x180014487  mov     ecx, ebx
0x180014489  lock xadd [rdi+18h], ecx
0x18001448e  sub     ecx, 1
0x180014491  jnz     short loc_1800144F9
0x180014493  nop
0x180014494  call    WINRT_IMPL_GetProcessHeap
0x180014499  mov     rcx, rax; hHeap
0x18001449c  mov     r8, rdi; lpMem
0x18001449f  xor     edx, edx; dwFlags
0x1800144a1  call    WINRT_IMPL_HeapFree
0x1800144a6  mov     [rsi+r14*8], r15
0x1800144aa  cmp     [rsp+78h+var_50], 0
0x1800144af  jz      short loc_1800144D8
0x1800144b1  mov     rdi, [rsp+78h+lpMem]
0x1800144b6  test    rdi, rdi
0x1800144b9  jz      short loc_1800144D8
0x1800144bb  lock xadd [rdi+18h], ebx
0x1800144c0  sub     ebx, 1
0x1800144c3  jnz     short loc_180014504
0x1800144c5  nop
0x1800144c6  call    WINRT_IMPL_GetProcessHeap
0x1800144cb  mov     rcx, rax; hHeap
0x1800144ce  mov     r8, rdi; lpMem
0x1800144d1  xor     edx, edx; dwFlags
0x1800144d3  call    WINRT_IMPL_HeapFree
0x1800144d8  xor     eax, eax
0x1800144da  jmp     short loc_1800144E3
0x1800144dc  mov     eax, [rsp+78h+arg_8]
0x1800144e3  lea     r11, [rsp+78h+var_18]
0x1800144e8  mov     rbx, [r11+20h]
0x1800144ec  mov     rsi, [r11+30h]
0x1800144f0  mov     rsp, r11
0x1800144f3  pop     r15
0x1800144f5  pop     r14
0x1800144f7  pop     rdi
0x1800144f8  retn
0x1800144f9  test    ecx, ecx
0x1800144fb  jns     short loc_1800144A6
0x1800144fd  call    cs:__imp_abort
0x180014504  test    ebx, ebx
0x180014506  jns     short loc_1800144D8
0x180014508  call    cs:__imp_abort
0x18001450f  mov     [rsp+78h+var_48], 6A3h
0x180014517  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001451e  mov     [r11-40h], rax
0x180014522  mov     qword ptr [r11-38h], 0
0x18001452a  lea     rdx, [r11-48h]; struct winrt::impl::slim_source_location *
0x18001452e  lea     rcx, [r11-30h]; this
0x180014532  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180014537  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001453e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180014543  call    _CxxThrowException_0
```
