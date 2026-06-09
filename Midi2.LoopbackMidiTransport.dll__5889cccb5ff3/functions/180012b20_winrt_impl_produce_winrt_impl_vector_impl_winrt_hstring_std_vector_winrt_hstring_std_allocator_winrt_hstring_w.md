# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAtEnd(void)

- ea: `0x180012b20`
- end: `0x180012cba`
- name: `?RemoveAtEnd@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHXZ`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000503c`
- `0x18000509c`
- `0x180005108`
- `0x18000f798`
- `0x180012b20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012c54`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012c5f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012c54`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012c5f`

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
0x180012b20  push    rbx
0x180012b22  push    rsi
0x180012b23  push    rdi
0x180012b24  push    r13
0x180012b26  push    r14
0x180012b28  push    r15
0x180012b2a  sub     rsp, 68h
0x180012b2e  lea     rax, [rcx-10h]
0x180012b32  neg     rcx
0x180012b35  sbb     rsi, rsi
0x180012b38  and     rsi, rax
0x180012b3b  lea     r14, [rsi+28h]
0x180012b3f  mov     [rsp+98h+var_70], 0
0x180012b44  mov     rax, r14
0x180012b47  neg     rax
0x180012b4a  sbb     rcx, rcx
0x180012b4d  and     rcx, rsi
0x180012b50  mov     rax, [rcx+38h]
0x180012b54  cmp     [rcx+30h], rax
0x180012b58  jz      loc_180012C7B
0x180012b5e  mov     r15d, 1
0x180012b64  lock add [r14], r15d
0x180012b68  mov     rax, r14
0x180012b6b  neg     rax
0x180012b6e  sbb     rcx, rcx
0x180012b71  and     rcx, rsi
0x180012b74  mov     r13, [rcx+38h]
0x180012b78  or      ebx, 0FFFFFFFFh
0x180012b7b  cmp     [rsp+98h+var_70], 0
0x180012b80  jz      short loc_180012BC3
0x180012b82  mov     rdi, [rsp+98h+lpMem]
0x180012b87  test    rdi, rdi
0x180012b8a  jz      short loc_180012BBE
0x180012b8c  mov     eax, ebx
0x180012b8e  lock xadd [rdi+18h], eax
0x180012b93  sub     eax, r15d
0x180012b96  jnz     short loc_180012BAD
0x180012b98  nop
0x180012b99  call    WINRT_IMPL_GetProcessHeap
0x180012b9e  mov     rcx, rax; hHeap
0x180012ba1  mov     r8, rdi; lpMem
0x180012ba4  xor     edx, edx; dwFlags
0x180012ba6  call    WINRT_IMPL_HeapFree
0x180012bab  jmp     short loc_180012BB5
0x180012bad  test    eax, eax
0x180012baf  js      loc_180012C54
0x180012bb5  mov     [rsp+98h+lpMem], 0
0x180012bbe  mov     [rsp+98h+var_70], 0
0x180012bc3  mov     rdi, [r13-8]
0x180012bc7  mov     qword ptr [r13-8], 0
0x180012bcf  mov     [rsp+98h+lpMem], rdi
0x180012bd4  mov     [rsp+98h+var_70], r15b
0x180012bd9  neg     r14
0x180012bdc  sbb     r14, r14
0x180012bdf  and     r14, rsi
0x180012be2  mov     r13, [r14+38h]
0x180012be6  mov     rsi, [r13-8]
0x180012bea  test    rsi, rsi
0x180012bed  jz      short loc_180012C20
0x180012bef  mov     eax, ebx
0x180012bf1  lock xadd [rsi+18h], eax
0x180012bf6  sub     eax, r15d
0x180012bf9  jnz     short loc_180012C50
0x180012bfb  nop
0x180012bfc  call    WINRT_IMPL_GetProcessHeap
0x180012c01  mov     rcx, rax; hHeap
0x180012c04  mov     r8, rsi; lpMem
0x180012c07  xor     edx, edx; dwFlags
0x180012c09  call    WINRT_IMPL_HeapFree
0x180012c0e  mov     qword ptr [r13-8], 0
0x180012c16  mov     r15b, [rsp+98h+var_70]
0x180012c1b  mov     rdi, [rsp+98h+lpMem]
0x180012c20  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180012c25  test    r15b, r15b
0x180012c28  jz      short loc_180012C4C
0x180012c2a  test    rdi, rdi
0x180012c2d  jz      short loc_180012C4C
0x180012c2f  lock xadd [rdi+18h], ebx
0x180012c34  sub     ebx, 1
0x180012c37  jnz     short loc_180012C5B
0x180012c39  nop
0x180012c3a  call    WINRT_IMPL_GetProcessHeap
0x180012c3f  mov     rcx, rax; hHeap
0x180012c42  mov     r8, rdi; lpMem
0x180012c45  xor     edx, edx; dwFlags
0x180012c47  call    WINRT_IMPL_HeapFree
0x180012c4c  xor     eax, eax
0x180012c4e  jmp     short loc_180012C6D
0x180012c50  test    eax, eax
0x180012c52  jns     short loc_180012C0E
0x180012c54  call    cs:__imp_abort
0x180012c5b  test    ebx, ebx
0x180012c5d  jns     short loc_180012C4C
0x180012c5f  call    cs:__imp_abort
0x180012c66  mov     eax, [rsp+98h+arg_0]
0x180012c6d  add     rsp, 68h
0x180012c71  pop     r15
0x180012c73  pop     r14
0x180012c75  pop     r13
0x180012c77  pop     rdi
0x180012c78  pop     rsi
0x180012c79  pop     rbx
0x180012c7a  retn
0x180012c7b  mov     [rsp+98h+var_68], 6D6h
0x180012c83  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180012c8a  mov     [rsp+98h+var_60], rax
0x180012c8f  mov     [rsp+98h+var_58], 0
0x180012c98  lea     rdx, [rsp+98h+var_68]; struct winrt::impl::slim_source_location *
0x180012c9d  lea     rcx, [rsp+98h+pExceptionObject]; this
0x180012ca2  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180012ca7  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180012cae  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180012cb3  call    _CxxThrowException_0
```
