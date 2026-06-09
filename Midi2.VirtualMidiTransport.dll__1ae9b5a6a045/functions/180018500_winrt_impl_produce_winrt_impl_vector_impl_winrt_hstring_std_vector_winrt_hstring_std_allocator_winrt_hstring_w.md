# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(uint)

- ea: `0x180018500`
- end: `0x180018701`
- name: `?RemoveAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800046b8`
- `0x180004718`
- `0x180004784`
- `0x180013ed0`
- `0x180018500`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800186b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800186c3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800186b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800186c3`

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
0x180018500  mov     r11, rsp
0x180018503  mov     [r11+8], rbx
0x180018507  mov     [r11+18h], rsi
0x18001850b  push    rdi
0x18001850c  push    r12
0x18001850e  push    r13
0x180018510  push    r14
0x180018512  push    r15
0x180018514  sub     rsp, 60h
0x180018518  lea     rax, [rcx-10h]
0x18001851c  neg     rcx
0x18001851f  sbb     r15, r15
0x180018522  and     r15, rax
0x180018525  lea     r14, [r15+28h]
0x180018529  xor     r8d, r8d
0x18001852c  mov     [r11-60h], r8b
0x180018530  mov     rax, r14
0x180018533  neg     rax
0x180018536  sbb     rcx, rcx
0x180018539  and     rcx, r15
0x18001853c  mov     r12d, edx
0x18001853f  mov     rax, [rcx+38h]
0x180018543  sub     rax, [rcx+30h]
0x180018547  sar     rax, 3
0x18001854b  cmp     r12, rax
0x18001854e  jnb     loc_1800186CA
0x180018554  lock inc dword ptr [r14]
0x180018558  mov     rax, r14
0x18001855b  neg     rax
0x18001855e  sbb     rcx, rcx
0x180018561  and     rcx, r15
0x180018564  mov     rsi, [rcx+30h]
0x180018568  or      ebx, 0FFFFFFFFh
0x18001856b  cmp     [rsp+88h+var_60], r8b
0x180018570  jz      short loc_1800185B2
0x180018572  mov     rdi, [rsp+88h+lpMem]
0x180018577  test    rdi, rdi
0x18001857a  jz      short loc_1800185AD
0x18001857c  mov     eax, ebx
0x18001857e  lock xadd [rdi+18h], eax
0x180018583  sub     eax, 1
0x180018586  jnz     short loc_1800185A0
0x180018588  nop
0x180018589  call    WINRT_IMPL_GetProcessHeap
0x18001858e  mov     rcx, rax; hHeap
0x180018591  mov     r8, rdi; lpMem
0x180018594  xor     edx, edx; dwFlags
0x180018596  call    WINRT_IMPL_HeapFree
0x18001859b  xor     r8d, r8d
0x18001859e  jmp     short loc_1800185A8
0x1800185a0  test    eax, eax
0x1800185a2  js      loc_1800186B8
0x1800185a8  mov     [rsp+88h+lpMem], r8
0x1800185ad  mov     [rsp+88h+var_60], r8b
0x1800185b2  lea     rsi, [rsi+r12*8]
0x1800185b6  mov     rax, [rsi]
0x1800185b9  mov     [rsi], r8
0x1800185bc  mov     [rsp+88h+lpMem], rax
0x1800185c1  mov     [rsp+88h+var_60], 1
0x1800185c6  neg     r14
0x1800185c9  sbb     r14, r14
0x1800185cc  and     r14, r15
0x1800185cf  mov     r13, [r14+38h]
0x1800185d3  lea     rdi, [rsi+8]
0x1800185d7  jmp     short loc_180018624
0x1800185d9  cmp     rsi, rdi
0x1800185dc  jz      short loc_18001861C
0x1800185de  mov     r12, [rdi]
0x1800185e1  mov     [rdi], r8
0x1800185e4  mov     r15, [rsi]
0x1800185e7  test    r15, r15
0x1800185ea  jz      short loc_180018619
0x1800185ec  mov     eax, ebx
0x1800185ee  lock xadd [r15+18h], eax
0x1800185f4  sub     eax, 1
0x1800185f7  jnz     short loc_180018611
0x1800185f9  nop
0x1800185fa  call    WINRT_IMPL_GetProcessHeap
0x1800185ff  mov     rcx, rax; hHeap
0x180018602  mov     r8, r15; lpMem
0x180018605  xor     edx, edx; dwFlags
0x180018607  call    WINRT_IMPL_HeapFree
0x18001860c  xor     r8d, r8d
0x18001860f  jmp     short loc_180018619
0x180018611  test    eax, eax
0x180018613  js      loc_1800186B8
0x180018619  mov     [rsi], r12
0x18001861c  add     rsi, 8
0x180018620  add     rdi, 8
0x180018624  cmp     rdi, r13
0x180018627  jnz     short loc_1800185D9
0x180018629  mov     rsi, [r14+38h]
0x18001862d  mov     rdi, [rsi-8]
0x180018631  test    rdi, rdi
0x180018634  jz      short loc_18001865C
0x180018636  mov     eax, ebx
0x180018638  lock xadd [rdi+18h], eax
0x18001863d  sub     eax, 1
0x180018640  jnz     short loc_1800186B4
0x180018642  nop
0x180018643  call    WINRT_IMPL_GetProcessHeap
0x180018648  mov     rcx, rax; hHeap
0x18001864b  mov     r8, rdi; lpMem
0x18001864e  xor     edx, edx; dwFlags
0x180018650  call    WINRT_IMPL_HeapFree
0x180018655  xor     r8d, r8d
0x180018658  mov     [rsi-8], r8
0x18001865c  add     qword ptr [r14+38h], 0FFFFFFFFFFFFFFF8h
0x180018661  cmp     [rsp+88h+var_60], r8b
0x180018666  jz      short loc_18001868F
0x180018668  mov     rdi, [rsp+88h+lpMem]
0x18001866d  test    rdi, rdi
0x180018670  jz      short loc_18001868F
0x180018672  lock xadd [rdi+18h], ebx
0x180018677  sub     ebx, 1
0x18001867a  jnz     short loc_1800186BF
0x18001867c  nop
0x18001867d  call    WINRT_IMPL_GetProcessHeap
0x180018682  mov     rcx, rax; hHeap
0x180018685  mov     r8, rdi; lpMem
0x180018688  xor     edx, edx; dwFlags
0x18001868a  call    WINRT_IMPL_HeapFree
0x18001868f  xor     eax, eax
0x180018691  jmp     short loc_18001869A
0x180018693  mov     eax, [rsp+88h+arg_8]
0x18001869a  lea     r11, [rsp+88h+var_28]
0x18001869f  mov     rbx, [r11+30h]
0x1800186a3  mov     rsi, [r11+40h]
0x1800186a7  mov     rsp, r11
0x1800186aa  pop     r15
0x1800186ac  pop     r14
0x1800186ae  pop     r13
0x1800186b0  pop     r12
0x1800186b2  pop     rdi
0x1800186b3  retn
0x1800186b4  test    eax, eax
0x1800186b6  jns     short loc_180018658
0x1800186b8  call    cs:__imp_abort
0x1800186bf  test    ebx, ebx
0x1800186c1  jns     short loc_18001868F
0x1800186c3  call    cs:__imp_abort
0x1800186ca  mov     [rsp+88h+var_58], 6BFh
0x1800186d2  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800186d9  mov     [r11-50h], rax
0x1800186dd  mov     [r11-48h], r8
0x1800186e1  lea     rdx, [r11-58h]; struct winrt::impl::slim_source_location *
0x1800186e5  lea     rcx, [r11-40h]; this
0x1800186e9  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800186ee  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800186f5  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800186fa  call    _CxxThrowException_0
```
