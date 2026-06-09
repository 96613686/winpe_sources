# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::InsertAt(uint,void *)

- ea: `0x180013540`
- end: `0x1800136b8`
- name: `?InsertAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000529c`
- `0x1800052fc`
- `0x180005374`
- `0x18000f3b8`
- `0x180010964`
- `0x180011240`
- `0x180013540`
- `0x180014864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013649`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013649`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::InsertAt(
        __int64 a1,
        struct winrt::impl::hstring_header *a2,
        winrt::impl *a3)
{
  __int64 v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // r14
  _QWORD *v7; // rdi
  _QWORD *v8; // rsi
  __int64 v9; // rax
  void *v10; // rbx
  int v11; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem[2]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+38h] [rbp-30h] BYREF
  winrt::impl *v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = a3;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  if ( (unsigned int)a2 > (unsigned __int64)((__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38)
                                                     - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3) )
  {
    LODWORD(v14) = 1713;
    lpMem[0] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    lpMem[1] = 0;
    winrt::hresult_out_of_bounds::hresult_out_of_bounds(
      (winrt::hresult_out_of_bounds *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v14);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  if ( v3 == -40 )
  {
    v3 = 0;
    v4 = 48;
  }
  else
  {
    v4 = v3 + 48;
  }
  v5 = *(_QWORD *)(v3 + 48);
  v6 = (_QWORD *)(v5 + 8LL * (unsigned int)a2);
  v7 = *(_QWORD **)(v4 + 8);
  if ( v7 == *(_QWORD **)(v4 + 16) )
  {
    std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(v4, v5 + 8LL * (unsigned int)a2, &v17);
  }
  else if ( v6 == v7 )
  {
    *v7 = winrt::impl::duplicate_hstring(a3, a2);
    *(_QWORD *)(v4 + 8) += 8LL;
  }
  else
  {
    v14 = v4;
    lpMem[0] = winrt::impl::duplicate_hstring(a3, a2);
    v8 = v7 - 1;
    v9 = *(v7 - 1);
    *(v7 - 1) = 0;
    *v7 = v9;
    *(_QWORD *)(v4 + 8) += 8LL;
    while ( v8 != v6 )
      winrt::hstring::operator=(--v7, --v8);
    winrt::hstring::operator=(v6, lpMem);
    v10 = lpMem[0];
    if ( lpMem[0] )
    {
      v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v10);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013540  mov     [rsp+arg_0], rbx
0x180013545  mov     [rsp+arg_10], r8
0x18001354a  push    rsi
0x18001354b  push    rdi
0x18001354c  push    r14
0x18001354e  sub     rsp, 50h
0x180013552  lea     rax, [rcx-10h]
0x180013556  neg     rcx
0x180013559  sbb     r9, r9
0x18001355c  and     r9, rax
0x18001355f  lea     r10, [r9+28h]
0x180013563  mov     rax, r10
0x180013566  neg     rax
0x180013569  sbb     rcx, rcx
0x18001356c  and     rcx, r9
0x18001356f  mov     r11d, edx
0x180013572  mov     rax, [rcx+38h]
0x180013576  sub     rax, [rcx+30h]
0x18001357a  sar     rax, 3
0x18001357e  cmp     r11, rax
0x180013581  ja      loc_180013679
0x180013587  lock inc dword ptr [r10]
0x18001358b  test    r10, r10
0x18001358e  jz      short loc_180013596
0x180013590  lea     rbx, [r9+30h]
0x180013594  jmp     short loc_18001359D
0x180013596  xor     r9d, r9d
0x180013599  lea     ebx, [r9+30h]
0x18001359d  mov     rax, [r9+30h]
0x1800135a1  lea     r14, [rax+r11*8]
0x1800135a5  mov     rdi, [rbx+8]
0x1800135a9  cmp     rdi, [rbx+10h]
0x1800135ad  jz      loc_180013650
0x1800135b3  mov     rcx, r8; this
0x1800135b6  cmp     r14, rdi
0x1800135b9  jnz     short loc_1800135CD
0x1800135bb  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800135c0  mov     [rdi], rax
0x1800135c3  add     qword ptr [rbx+8], 8
0x1800135c8  jmp     loc_180013663
0x1800135cd  mov     [rsp+68h+var_48], rbx
0x1800135d2  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800135d7  mov     [rsp+68h+lpMem], rax
0x1800135dc  lea     rsi, [rdi-8]
0x1800135e0  mov     rax, [rsi]
0x1800135e3  mov     qword ptr [rsi], 0
0x1800135ea  mov     [rdi], rax
0x1800135ed  add     qword ptr [rbx+8], 8
0x1800135f2  jmp     short loc_180013607
0x1800135f4  sub     rsi, 8
0x1800135f8  sub     rdi, 8
0x1800135fc  mov     rdx, rsi
0x1800135ff  mov     rcx, rdi
0x180013602  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x180013607  cmp     rsi, r14
0x18001360a  jnz     short loc_1800135F4
0x18001360c  lea     rdx, [rsp+68h+lpMem]
0x180013611  mov     rcx, r14
0x180013614  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x180013619  mov     rbx, [rsp+68h+lpMem]
0x18001361e  test    rbx, rbx
0x180013621  jz      short loc_180013663
0x180013623  or      eax, 0FFFFFFFFh
0x180013626  lock xadd [rbx+18h], eax
0x18001362b  sub     eax, 1
0x18001362e  jnz     short loc_180013645
0x180013630  nop
0x180013631  call    WINRT_IMPL_GetProcessHeap
0x180013636  mov     rcx, rax; hHeap
0x180013639  mov     r8, rbx; lpMem
0x18001363c  xor     edx, edx; dwFlags
0x18001363e  call    WINRT_IMPL_HeapFree
0x180013643  jmp     short loc_180013663
0x180013645  test    eax, eax
0x180013647  jns     short loc_180013663
0x180013649  call    cs:__imp_abort
0x180013650  lea     r8, [rsp+68h+arg_10]
0x180013658  mov     rdx, r14
0x18001365b  mov     rcx, rbx
0x18001365e  call    ??$_Emplace_reallocate@AEBUhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@AEBU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(winrt::hstring * const,winrt::hstring const &)
0x180013663  xor     eax, eax
0x180013665  jmp     short loc_18001366B
0x180013667  mov     eax, [rsp+68h+arg_8]
0x18001366b  mov     rbx, [rsp+68h+arg_0]
0x180013670  add     rsp, 50h
0x180013674  pop     r14
0x180013676  pop     rdi
0x180013677  pop     rsi
0x180013678  retn
0x180013679  mov     dword ptr [rsp+68h+var_48], 6B1h
0x180013681  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180013688  mov     [rsp+68h+lpMem], rax
0x18001368d  mov     [rsp+68h+var_38], 0
0x180013696  lea     rdx, [rsp+68h+var_48]; struct winrt::impl::slim_source_location *
0x18001369b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800136a0  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800136a5  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800136ac  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800136b1  call    _CxxThrowException_0
```
