# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(void)

- ea: `0x180014110`
- end: `0x1800142aa`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000529c`
- `0x1800052fc`
- `0x180005374`
- `0x180010964`
- `0x180014110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014244`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001424f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014244`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001424f`

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
0x180014110  push    rbx
0x180014112  push    rsi
0x180014113  push    rdi
0x180014114  push    r13
0x180014116  push    r14
0x180014118  push    r15
0x18001411a  sub     rsp, 68h
0x18001411e  lea     rax, [rcx-10h]
0x180014122  neg     rcx
0x180014125  sbb     rsi, rsi
0x180014128  and     rsi, rax
0x18001412b  lea     r14, [rsi+28h]
0x18001412f  mov     [rsp+98h+var_70], 0
0x180014134  mov     rax, r14
0x180014137  neg     rax
0x18001413a  sbb     rcx, rcx
0x18001413d  and     rcx, rsi
0x180014140  mov     rax, [rcx+38h]
0x180014144  cmp     [rcx+30h], rax
0x180014148  jz      loc_18001426B
0x18001414e  mov     r15d, 1
0x180014154  lock add [r14], r15d
0x180014158  mov     rax, r14
0x18001415b  neg     rax
0x18001415e  sbb     rcx, rcx
0x180014161  and     rcx, rsi
0x180014164  mov     r13, [rcx+38h]
0x180014168  or      ebx, 0FFFFFFFFh
0x18001416b  cmp     [rsp+98h+var_70], 0
0x180014170  jz      short loc_1800141B3
0x180014172  mov     rdi, [rsp+98h+lpMem]
0x180014177  test    rdi, rdi
0x18001417a  jz      short loc_1800141AE
0x18001417c  mov     eax, ebx
0x18001417e  lock xadd [rdi+18h], eax
0x180014183  sub     eax, r15d
0x180014186  jnz     short loc_18001419D
0x180014188  nop
0x180014189  call    WINRT_IMPL_GetProcessHeap
0x18001418e  mov     rcx, rax; hHeap
0x180014191  mov     r8, rdi; lpMem
0x180014194  xor     edx, edx; dwFlags
0x180014196  call    WINRT_IMPL_HeapFree
0x18001419b  jmp     short loc_1800141A5
0x18001419d  test    eax, eax
0x18001419f  js      loc_180014244
0x1800141a5  mov     [rsp+98h+lpMem], 0
0x1800141ae  mov     [rsp+98h+var_70], 0
0x1800141b3  mov     rdi, [r13-8]
0x1800141b7  mov     qword ptr [r13-8], 0
0x1800141bf  mov     [rsp+98h+lpMem], rdi
0x1800141c4  mov     [rsp+98h+var_70], r15b
0x1800141c9  neg     r14
0x1800141cc  sbb     r14, r14
0x1800141cf  and     r14, rsi
0x1800141d2  mov     r13, [r14+38h]
0x1800141d6  mov     rsi, [r13-8]
0x1800141da  test    rsi, rsi
0x1800141dd  jz      short loc_180014210
0x1800141df  mov     eax, ebx
0x1800141e1  lock xadd [rsi+18h], eax
0x1800141e6  sub     eax, r15d
0x1800141e9  jnz     short loc_180014240
0x1800141eb  nop
0x1800141ec  call    WINRT_IMPL_GetProcessHeap
0x1800141f1  mov     rcx, rax; hHeap
0x1800141f4  mov     r8, rsi; lpMem
0x1800141f7  xor     edx, edx; dwFlags
0x1800141f9  call    WINRT_IMPL_HeapFree
0x1800141fe  mov     qword ptr [r13-8], 0
0x180014206  mov     r15b, [rsp+98h+var_70]
0x18001420b  mov     rdi, [rsp+98h+lpMem]
0x180014210  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180014215  test    r15b, r15b
0x180014218  jz      short loc_18001423C
0x18001421a  test    rdi, rdi
0x18001421d  jz      short loc_18001423C
0x18001421f  lock xadd [rdi+18h], ebx
0x180014224  sub     ebx, 1
0x180014227  jnz     short loc_18001424B
0x180014229  nop
0x18001422a  call    WINRT_IMPL_GetProcessHeap
0x18001422f  mov     rcx, rax; hHeap
0x180014232  mov     r8, rdi; lpMem
0x180014235  xor     edx, edx; dwFlags
0x180014237  call    WINRT_IMPL_HeapFree
0x18001423c  xor     eax, eax
0x18001423e  jmp     short loc_18001425D
0x180014240  test    eax, eax
0x180014242  jns     short loc_1800141FE
0x180014244  call    cs:__imp_abort
0x18001424b  test    ebx, ebx
0x18001424d  jns     short loc_18001423C
0x18001424f  call    cs:__imp_abort
0x180014256  mov     eax, [rsp+98h+arg_0]
0x18001425d  add     rsp, 68h
0x180014261  pop     r15
0x180014263  pop     r14
0x180014265  pop     r13
0x180014267  pop     rdi
0x180014268  pop     rsi
0x180014269  pop     rbx
0x18001426a  retn
0x18001426b  mov     [rsp+98h+var_68], 6D6h
0x180014273  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001427a  mov     [rsp+98h+var_60], rax
0x18001427f  mov     [rsp+98h+var_58], 0
0x180014288  lea     rdx, [rsp+98h+var_68]; struct winrt::impl::slim_source_location *
0x18001428d  lea     rcx, [rsp+98h+pExceptionObject]; this
0x180014292  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180014297  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001429e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800142a3  call    _CxxThrowException_0
```
