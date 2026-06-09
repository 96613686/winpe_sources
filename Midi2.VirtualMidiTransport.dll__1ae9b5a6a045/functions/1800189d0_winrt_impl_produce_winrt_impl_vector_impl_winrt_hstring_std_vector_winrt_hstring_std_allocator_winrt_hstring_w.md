# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::SetAt(uint,void *)

- ea: `0x1800189d0`
- end: `0x180018b6a`
- name: `?SetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800046b8`
- `0x180004718`
- `0x180004784`
- `0x180013ed0`
- `0x1800189d0`
- `0x1800194c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018b1d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018b28`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018b1d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018b28`

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
0x1800189d0  mov     r11, rsp
0x1800189d3  mov     [r11+8], rbx
0x1800189d7  mov     [r11+18h], rsi
0x1800189db  push    rdi
0x1800189dc  push    r14
0x1800189de  push    r15
0x1800189e0  sub     rsp, 60h
0x1800189e4  mov     r15, r8
0x1800189e7  lea     rax, [rcx-10h]
0x1800189eb  neg     rcx
0x1800189ee  sbb     r10, r10
0x1800189f1  and     r10, rax
0x1800189f4  lea     r9, [r10+28h]
0x1800189f8  mov     [rsp+78h+var_50], 0
0x1800189fd  mov     rax, r9
0x180018a00  neg     rax
0x180018a03  sbb     rcx, rcx
0x180018a06  and     rcx, r10
0x180018a09  mov     r14d, edx
0x180018a0c  mov     rax, [rcx+38h]
0x180018a10  sub     rax, [rcx+30h]
0x180018a14  sar     rax, 3
0x180018a18  cmp     r14, rax
0x180018a1b  jnb     loc_180018B2F
0x180018a21  lock inc dword ptr [r9]
0x180018a25  neg     r9
0x180018a28  sbb     rax, rax
0x180018a2b  and     rax, r10
0x180018a2e  mov     rsi, [rax+30h]
0x180018a32  or      ebx, 0FFFFFFFFh
0x180018a35  cmp     [rsp+78h+var_50], 0
0x180018a3a  jz      short loc_180018A7D
0x180018a3c  mov     rdi, [rsp+78h+lpMem]
0x180018a41  test    rdi, rdi
0x180018a44  jz      short loc_180018A78
0x180018a46  mov     eax, ebx
0x180018a48  lock xadd [rdi+18h], eax
0x180018a4d  sub     eax, 1
0x180018a50  jnz     short loc_180018A67
0x180018a52  nop
0x180018a53  call    WINRT_IMPL_GetProcessHeap
0x180018a58  mov     rcx, rax; hHeap
0x180018a5b  mov     r8, rdi; lpMem
0x180018a5e  xor     edx, edx; dwFlags
0x180018a60  call    WINRT_IMPL_HeapFree
0x180018a65  jmp     short loc_180018A6F
0x180018a67  test    eax, eax
0x180018a69  js      loc_180018B1D
0x180018a6f  mov     [rsp+78h+lpMem], 0
0x180018a78  mov     [rsp+78h+var_50], 0
0x180018a7d  mov     rax, [rsi+r14*8]
0x180018a81  mov     qword ptr [rsi+r14*8], 0
0x180018a89  mov     [rsp+78h+lpMem], rax
0x180018a8e  mov     [rsp+78h+var_50], 1
0x180018a93  mov     rcx, r15; this
0x180018a96  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180018a9b  mov     r15, rax
0x180018a9e  mov     rdi, [rsi+r14*8]
0x180018aa2  test    rdi, rdi
0x180018aa5  jz      short loc_180018AC6
0x180018aa7  mov     ecx, ebx
0x180018aa9  lock xadd [rdi+18h], ecx
0x180018aae  sub     ecx, 1
0x180018ab1  jnz     short loc_180018B19
0x180018ab3  nop
0x180018ab4  call    WINRT_IMPL_GetProcessHeap
0x180018ab9  mov     rcx, rax; hHeap
0x180018abc  mov     r8, rdi; lpMem
0x180018abf  xor     edx, edx; dwFlags
0x180018ac1  call    WINRT_IMPL_HeapFree
0x180018ac6  mov     [rsi+r14*8], r15
0x180018aca  cmp     [rsp+78h+var_50], 0
0x180018acf  jz      short loc_180018AF8
0x180018ad1  mov     rdi, [rsp+78h+lpMem]
0x180018ad6  test    rdi, rdi
0x180018ad9  jz      short loc_180018AF8
0x180018adb  lock xadd [rdi+18h], ebx
0x180018ae0  sub     ebx, 1
0x180018ae3  jnz     short loc_180018B24
0x180018ae5  nop
0x180018ae6  call    WINRT_IMPL_GetProcessHeap
0x180018aeb  mov     rcx, rax; hHeap
0x180018aee  mov     r8, rdi; lpMem
0x180018af1  xor     edx, edx; dwFlags
0x180018af3  call    WINRT_IMPL_HeapFree
0x180018af8  xor     eax, eax
0x180018afa  jmp     short loc_180018B03
0x180018afc  mov     eax, [rsp+78h+arg_8]
0x180018b03  lea     r11, [rsp+78h+var_18]
0x180018b08  mov     rbx, [r11+20h]
0x180018b0c  mov     rsi, [r11+30h]
0x180018b10  mov     rsp, r11
0x180018b13  pop     r15
0x180018b15  pop     r14
0x180018b17  pop     rdi
0x180018b18  retn
0x180018b19  test    ecx, ecx
0x180018b1b  jns     short loc_180018AC6
0x180018b1d  call    cs:__imp_abort
0x180018b24  test    ebx, ebx
0x180018b26  jns     short loc_180018AF8
0x180018b28  call    cs:__imp_abort
0x180018b2f  mov     [rsp+78h+var_48], 6A3h
0x180018b37  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180018b3e  mov     [r11-40h], rax
0x180018b42  mov     qword ptr [r11-38h], 0
0x180018b4a  lea     rdx, [r11-48h]; struct winrt::impl::slim_source_location *
0x180018b4e  lea     rcx, [r11-30h]; this
0x180018b52  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180018b57  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180018b5e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180018b63  call    _CxxThrowException_0
```
