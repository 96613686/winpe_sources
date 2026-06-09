# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(void)

- ea: `0x180018710`
- end: `0x1800188aa`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800046b8`
- `0x180004718`
- `0x180004784`
- `0x180013ed0`
- `0x180018710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018844`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001884f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018844`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001884f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(
        __int64 a1)
{
  __int64 v1; // rsi
  volatile signed __int32 *v2; // r14
  char v3; // r15
  __int64 v4; // r13
  volatile signed __int32 *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r13
  volatile signed __int32 *v8; // rsi
  int v9; // eax
  HANDLE ProcessHeap; // rax
  int v11; // ebx
  HANDLE v12; // rax
  __int64 v14; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-78h]
  char v16; // [rsp+28h] [rbp-70h]
  int v17; // [rsp+30h] [rbp-68h] BYREF
  const char *v18; // [rsp+38h] [rbp-60h]
  __int64 v19; // [rsp+40h] [rbp-58h]
  _BYTE pExceptionObject[80]; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+8h] BYREF

  v1 = (a1 - 16) & -(__int64)(a1 != 0);
  v2 = (volatile signed __int32 *)(v1 + 40);
  v16 = 0;
  if ( *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x30) == *(_QWORD *)((v1 & -(__int64)(v1 != -40)) + 0x38) )
  {
    v17 = 1750;
    v18 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    v19 = 0;
    winrt::hresult_out_of_bounds::hresult_out_of_bounds(
      (winrt::hresult_out_of_bounds *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v17);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v14 + 160) = *(_DWORD *)winrt::to_hresult(&v21);
      return v21;
    }
  }
  v3 = 1;
  _InterlockedAdd(v2, 1u);
  v4 = *(_QWORD *)((v1 & -(__int64)(v2 != 0)) + 0x38);
  v5 = *(volatile signed __int32 **)(v4 - 8);
  *(_QWORD *)(v4 - 8) = 0;
  lpMem = (LPVOID)v5;
  v16 = 1;
  v6 = v1 & -(__int64)(v2 != 0);
  v7 = *(_QWORD *)(v6 + 56);
  v8 = *(volatile signed __int32 **)(v7 - 8);
  if ( v8 )
  {
    v9 = _InterlockedDecrement(v8 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
    }
    *(_QWORD *)(v7 - 8) = 0;
    v3 = v16;
    v5 = (volatile signed __int32 *)lpMem;
  }
  *(_QWORD *)(v6 + 56) -= 8LL;
  if ( v3 && v5 )
  {
    v11 = _InterlockedDecrement(v5 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      v12 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018710  push    rbx
0x180018712  push    rsi
0x180018713  push    rdi
0x180018714  push    r13
0x180018716  push    r14
0x180018718  push    r15
0x18001871a  sub     rsp, 68h
0x18001871e  lea     rax, [rcx-10h]
0x180018722  neg     rcx
0x180018725  sbb     rsi, rsi
0x180018728  and     rsi, rax
0x18001872b  lea     r14, [rsi+28h]
0x18001872f  mov     [rsp+98h+var_70], 0
0x180018734  mov     rax, r14
0x180018737  neg     rax
0x18001873a  sbb     rcx, rcx
0x18001873d  and     rcx, rsi
0x180018740  mov     rax, [rcx+38h]
0x180018744  cmp     [rcx+30h], rax
0x180018748  jz      loc_18001886B
0x18001874e  mov     r15d, 1
0x180018754  lock add [r14], r15d
0x180018758  mov     rax, r14
0x18001875b  neg     rax
0x18001875e  sbb     rcx, rcx
0x180018761  and     rcx, rsi
0x180018764  mov     r13, [rcx+38h]
0x180018768  or      ebx, 0FFFFFFFFh
0x18001876b  cmp     [rsp+98h+var_70], 0
0x180018770  jz      short loc_1800187B3
0x180018772  mov     rdi, [rsp+98h+lpMem]
0x180018777  test    rdi, rdi
0x18001877a  jz      short loc_1800187AE
0x18001877c  mov     eax, ebx
0x18001877e  lock xadd [rdi+18h], eax
0x180018783  sub     eax, r15d
0x180018786  jnz     short loc_18001879D
0x180018788  nop
0x180018789  call    WINRT_IMPL_GetProcessHeap
0x18001878e  mov     rcx, rax; hHeap
0x180018791  mov     r8, rdi; lpMem
0x180018794  xor     edx, edx; dwFlags
0x180018796  call    WINRT_IMPL_HeapFree
0x18001879b  jmp     short loc_1800187A5
0x18001879d  test    eax, eax
0x18001879f  js      loc_180018844
0x1800187a5  mov     [rsp+98h+lpMem], 0
0x1800187ae  mov     [rsp+98h+var_70], 0
0x1800187b3  mov     rdi, [r13-8]
0x1800187b7  mov     qword ptr [r13-8], 0
0x1800187bf  mov     [rsp+98h+lpMem], rdi
0x1800187c4  mov     [rsp+98h+var_70], r15b
0x1800187c9  neg     r14
0x1800187cc  sbb     r14, r14
0x1800187cf  and     r14, rsi
0x1800187d2  mov     r13, [r14+38h]
0x1800187d6  mov     rsi, [r13-8]
0x1800187da  test    rsi, rsi
0x1800187dd  jz      short loc_180018810
0x1800187df  mov     eax, ebx
0x1800187e1  lock xadd [rsi+18h], eax
0x1800187e6  sub     eax, r15d
0x1800187e9  jnz     short loc_180018840
0x1800187eb  nop
0x1800187ec  call    WINRT_IMPL_GetProcessHeap
0x1800187f1  mov     rcx, rax; hHeap
0x1800187f4  mov     r8, rsi; lpMem
0x1800187f7  xor     edx, edx; dwFlags
0x1800187f9  call    WINRT_IMPL_HeapFree
0x1800187fe  mov     qword ptr [r13-8], 0
0x180018806  mov     r15b, [rsp+98h+var_70]
0x18001880b  mov     rdi, [rsp+98h+lpMem]
0x180018810  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180018815  test    r15b, r15b
0x180018818  jz      short loc_18001883C
0x18001881a  test    rdi, rdi
0x18001881d  jz      short loc_18001883C
0x18001881f  lock xadd [rdi+18h], ebx
0x180018824  sub     ebx, 1
0x180018827  jnz     short loc_18001884B
0x180018829  nop
0x18001882a  call    WINRT_IMPL_GetProcessHeap
0x18001882f  mov     rcx, rax; hHeap
0x180018832  mov     r8, rdi; lpMem
0x180018835  xor     edx, edx; dwFlags
0x180018837  call    WINRT_IMPL_HeapFree
0x18001883c  xor     eax, eax
0x18001883e  jmp     short loc_18001885D
0x180018840  test    eax, eax
0x180018842  jns     short loc_1800187FE
0x180018844  call    cs:__imp_abort
0x18001884b  test    ebx, ebx
0x18001884d  jns     short loc_18001883C
0x18001884f  call    cs:__imp_abort
0x180018856  mov     eax, [rsp+98h+arg_0]
0x18001885d  add     rsp, 68h
0x180018861  pop     r15
0x180018863  pop     r14
0x180018865  pop     r13
0x180018867  pop     rdi
0x180018868  pop     rsi
0x180018869  pop     rbx
0x18001886a  retn
0x18001886b  mov     [rsp+98h+var_68], 6D6h
0x180018873  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001887a  mov     [rsp+98h+var_60], rax
0x18001887f  mov     [rsp+98h+var_58], 0
0x180018888  lea     rdx, [rsp+98h+var_68]; struct winrt::impl::slim_source_location *
0x18001888d  lea     rcx, [rsp+98h+pExceptionObject]; this
0x180018892  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180018897  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001889e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800188a3  call    _CxxThrowException_0
```
