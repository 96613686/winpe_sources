# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(uint)

- ea: `0x180012910`
- end: `0x180012b11`
- name: `?RemoveAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000503c`
- `0x18000509c`
- `0x180005108`
- `0x18000f798`
- `0x180012910`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012ac8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012ad3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012ac8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012ad3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r15
  volatile signed __int32 *v3; // r14
  __int64 v4; // r12
  void **v5; // rsi
  void *v6; // rax
  __int64 v7; // r14
  void **v8; // r13
  void **i; // rdi
  void *v10; // r12
  volatile signed __int32 *v11; // r15
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rsi
  volatile signed __int32 *v15; // rdi
  int v16; // eax
  HANDLE v17; // rax
  int v18; // ebx
  HANDLE v19; // rax
  __int64 v21; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-68h]
  char v23; // [rsp+28h] [rbp-60h]
  int v24; // [rsp+30h] [rbp-58h] BYREF
  const char *v25; // [rsp+38h] [rbp-50h]
  __int64 v26; // [rsp+40h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v28; // [rsp+98h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v23 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v24 = 1727;
    v25 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    v26 = 0;
    winrt::hresult_out_of_bounds::hresult_out_of_bounds(
      (winrt::hresult_out_of_bounds *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v24);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v21 + 152) = *(_DWORD *)winrt::to_hresult(&v28);
      return v28;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (void **)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  lpMem = v6;
  v23 = 1;
  v7 = v2 & -(__int64)(v3 != 0);
  v8 = *(void ***)(v7 + 56);
  for ( i = v5 + 1; i != v8; ++i )
  {
    if ( v5 != i )
    {
      v10 = *i;
      *i = 0;
      v11 = (volatile signed __int32 *)*v5;
      if ( *v5 )
      {
        v12 = _InterlockedDecrement(v11 + 6);
        if ( v12 )
        {
          if ( v12 < 0 )
            goto LABEL_21;
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
        }
      }
      *v5 = v10;
    }
    ++v5;
  }
  v14 = *(_QWORD *)(v7 + 56);
  v15 = *(volatile signed __int32 **)(v14 - 8);
  if ( v15 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
LABEL_21:
        abort();
    }
    else
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v15);
    }
    *(_QWORD *)(v14 - 8) = 0;
  }
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v23 && lpMem )
  {
    v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, lpMem);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012910  mov     r11, rsp
0x180012913  mov     [r11+8], rbx
0x180012917  mov     [r11+18h], rsi
0x18001291b  push    rdi
0x18001291c  push    r12
0x18001291e  push    r13
0x180012920  push    r14
0x180012922  push    r15
0x180012924  sub     rsp, 60h
0x180012928  lea     rax, [rcx-10h]
0x18001292c  neg     rcx
0x18001292f  sbb     r15, r15
0x180012932  and     r15, rax
0x180012935  lea     r14, [r15+28h]
0x180012939  xor     r8d, r8d
0x18001293c  mov     [r11-60h], r8b
0x180012940  mov     rax, r14
0x180012943  neg     rax
0x180012946  sbb     rcx, rcx
0x180012949  and     rcx, r15
0x18001294c  mov     r12d, edx
0x18001294f  mov     rax, [rcx+38h]
0x180012953  sub     rax, [rcx+30h]
0x180012957  sar     rax, 3
0x18001295b  cmp     r12, rax
0x18001295e  jnb     loc_180012ADA
0x180012964  lock inc dword ptr [r14]
0x180012968  mov     rax, r14
0x18001296b  neg     rax
0x18001296e  sbb     rcx, rcx
0x180012971  and     rcx, r15
0x180012974  mov     rsi, [rcx+30h]
0x180012978  or      ebx, 0FFFFFFFFh
0x18001297b  cmp     [rsp+88h+var_60], r8b
0x180012980  jz      short loc_1800129C2
0x180012982  mov     rdi, [rsp+88h+lpMem]
0x180012987  test    rdi, rdi
0x18001298a  jz      short loc_1800129BD
0x18001298c  mov     eax, ebx
0x18001298e  lock xadd [rdi+18h], eax
0x180012993  sub     eax, 1
0x180012996  jnz     short loc_1800129B0
0x180012998  nop
0x180012999  call    WINRT_IMPL_GetProcessHeap
0x18001299e  mov     rcx, rax; hHeap
0x1800129a1  mov     r8, rdi; lpMem
0x1800129a4  xor     edx, edx; dwFlags
0x1800129a6  call    WINRT_IMPL_HeapFree
0x1800129ab  xor     r8d, r8d
0x1800129ae  jmp     short loc_1800129B8
0x1800129b0  test    eax, eax
0x1800129b2  js      loc_180012AC8
0x1800129b8  mov     [rsp+88h+lpMem], r8
0x1800129bd  mov     [rsp+88h+var_60], r8b
0x1800129c2  lea     rsi, [rsi+r12*8]
0x1800129c6  mov     rax, [rsi]
0x1800129c9  mov     [rsi], r8
0x1800129cc  mov     [rsp+88h+lpMem], rax
0x1800129d1  mov     [rsp+88h+var_60], 1
0x1800129d6  neg     r14
0x1800129d9  sbb     r14, r14
0x1800129dc  and     r14, r15
0x1800129df  mov     r13, [r14+38h]
0x1800129e3  lea     rdi, [rsi+8]
0x1800129e7  jmp     short loc_180012A34
0x1800129e9  cmp     rsi, rdi
0x1800129ec  jz      short loc_180012A2C
0x1800129ee  mov     r12, [rdi]
0x1800129f1  mov     [rdi], r8
0x1800129f4  mov     r15, [rsi]
0x1800129f7  test    r15, r15
0x1800129fa  jz      short loc_180012A29
0x1800129fc  mov     eax, ebx
0x1800129fe  lock xadd [r15+18h], eax
0x180012a04  sub     eax, 1
0x180012a07  jnz     short loc_180012A21
0x180012a09  nop
0x180012a0a  call    WINRT_IMPL_GetProcessHeap
0x180012a0f  mov     rcx, rax; hHeap
0x180012a12  mov     r8, r15; lpMem
0x180012a15  xor     edx, edx; dwFlags
0x180012a17  call    WINRT_IMPL_HeapFree
0x180012a1c  xor     r8d, r8d
0x180012a1f  jmp     short loc_180012A29
0x180012a21  test    eax, eax
0x180012a23  js      loc_180012AC8
0x180012a29  mov     [rsi], r12
0x180012a2c  add     rsi, 8
0x180012a30  add     rdi, 8
0x180012a34  cmp     rdi, r13
0x180012a37  jnz     short loc_1800129E9
0x180012a39  mov     rsi, [r14+38h]
0x180012a3d  mov     rdi, [rsi-8]
0x180012a41  test    rdi, rdi
0x180012a44  jz      short loc_180012A6C
0x180012a46  mov     eax, ebx
0x180012a48  lock xadd [rdi+18h], eax
0x180012a4d  sub     eax, 1
0x180012a50  jnz     short loc_180012AC4
0x180012a52  nop
0x180012a53  call    WINRT_IMPL_GetProcessHeap
0x180012a58  mov     rcx, rax; hHeap
0x180012a5b  mov     r8, rdi; lpMem
0x180012a5e  xor     edx, edx; dwFlags
0x180012a60  call    WINRT_IMPL_HeapFree
0x180012a65  xor     r8d, r8d
0x180012a68  mov     [rsi-8], r8
0x180012a6c  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180012a71  cmp     [rsp+88h+var_60], r8b
0x180012a76  jz      short loc_180012A9F
0x180012a78  mov     rdi, [rsp+88h+lpMem]
0x180012a7d  test    rdi, rdi
0x180012a80  jz      short loc_180012A9F
0x180012a82  lock xadd [rdi+18h], ebx
0x180012a87  sub     ebx, 1
0x180012a8a  jnz     short loc_180012ACF
0x180012a8c  nop
0x180012a8d  call    WINRT_IMPL_GetProcessHeap
0x180012a92  mov     rcx, rax; hHeap
0x180012a95  mov     r8, rdi; lpMem
0x180012a98  xor     edx, edx; dwFlags
0x180012a9a  call    WINRT_IMPL_HeapFree
0x180012a9f  xor     eax, eax
0x180012aa1  jmp     short loc_180012AAA
0x180012aa3  mov     eax, [rsp+88h+arg_8]
0x180012aaa  lea     r11, [rsp+88h+var_28]
0x180012aaf  mov     rbx, [r11+30h]
0x180012ab3  mov     rsi, [r11+40h]
0x180012ab7  mov     rsp, r11
0x180012aba  pop     r15
0x180012abc  pop     r14
0x180012abe  pop     r13
0x180012ac0  pop     r12
0x180012ac2  pop     rdi
0x180012ac3  retn
0x180012ac4  test    eax, eax
0x180012ac6  jns     short loc_180012A68
0x180012ac8  call    cs:__imp_abort
0x180012acf  test    ebx, ebx
0x180012ad1  jns     short loc_180012A9F
0x180012ad3  call    cs:__imp_abort
0x180012ada  mov     [rsp+88h+var_58], 6BFh
0x180012ae2  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180012ae9  mov     [r11-50h], rax
0x180012aed  mov     [r11-48h], r8
0x180012af1  lea     rdx, [r11-58h]; struct winrt::impl::slim_source_location *
0x180012af5  lea     rcx, [r11-40h]; this
0x180012af9  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180012afe  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180012b05  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180012b0a  call    _CxxThrowException_0
```
