# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(uint)

- ea: `0x180013f40`
- end: `0x1800140fc`
- name: `?RemoveAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000529c`
- `0x1800052fc`
- `0x180005374`
- `0x180010964`
- `0x180011240`
- `0x180013f40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800140af`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800140ba`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800140af`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800140ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r15
  volatile signed __int32 *v3; // rsi
  __int64 v4; // r12
  void **v5; // r14
  void *v6; // rax
  __int64 v7; // rsi
  void **v8; // r15
  void **i; // rdi
  __int64 v10; // r14
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  HANDLE ProcessHeap; // rax
  int v14; // ebx
  HANDLE v15; // rax
  __int64 v17; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-78h]
  char v19; // [rsp+28h] [rbp-70h]
  int v20; // [rsp+30h] [rbp-68h] BYREF
  const char *v21; // [rsp+38h] [rbp-60h]
  __int64 v22; // [rsp+40h] [rbp-58h]
  _BYTE pExceptionObject[80]; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v19 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v20 = 1727;
    v21 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    v22 = 0;
    winrt::hresult_out_of_bounds::hresult_out_of_bounds(
      (winrt::hresult_out_of_bounds *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v20);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v17 + 168) = *(_DWORD *)winrt::to_hresult(&v24);
      return v24;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (void **)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  lpMem = v6;
  v19 = 1;
  v7 = v2 & -(__int64)(v3 != 0);
  v8 = *(void ***)(v7 + 56);
  for ( i = v5 + 1; i != v8; ++i )
    winrt::hstring::operator=(v5++, i);
  v10 = *(_QWORD *)(v7 + 56);
  v11 = *(volatile signed __int32 **)(v10 - 8);
  if ( v11 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
    }
    *(_QWORD *)(v10 - 8) = 0;
  }
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v19 && lpMem )
  {
    v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v14 )
    {
      if ( v14 < 0 )
        abort();
    }
    else
    {
      v15 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v15, 0, lpMem);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013f40  mov     r11, rsp
0x180013f43  push    rbx
0x180013f44  push    rsi
0x180013f45  push    rdi
0x180013f46  push    r12
0x180013f48  push    r14
0x180013f4a  push    r15
0x180013f4c  sub     rsp, 68h
0x180013f50  lea     rax, [rcx-10h]
0x180013f54  neg     rcx
0x180013f57  sbb     r15, r15
0x180013f5a  and     r15, rax
0x180013f5d  lea     rsi, [r15+28h]
0x180013f61  mov     [rsp+98h+var_70], 0
0x180013f66  mov     rax, rsi
0x180013f69  neg     rax
0x180013f6c  sbb     rcx, rcx
0x180013f6f  and     rcx, r15
0x180013f72  mov     r12d, edx
0x180013f75  mov     rax, [rcx+38h]
0x180013f79  sub     rax, [rcx+30h]
0x180013f7d  sar     rax, 3
0x180013f81  cmp     r12, rax
0x180013f84  jnb     loc_1800140C1
0x180013f8a  lock inc dword ptr [rsi]
0x180013f8d  mov     rax, rsi
0x180013f90  neg     rax
0x180013f93  sbb     rcx, rcx
0x180013f96  and     rcx, r15
0x180013f99  mov     r14, [rcx+30h]
0x180013f9d  or      ebx, 0FFFFFFFFh
0x180013fa0  cmp     [rsp+98h+var_70], 0
0x180013fa5  jz      short loc_180013FE8
0x180013fa7  mov     rdi, [rsp+98h+lpMem]
0x180013fac  test    rdi, rdi
0x180013faf  jz      short loc_180013FE3
0x180013fb1  mov     eax, ebx
0x180013fb3  lock xadd [rdi+18h], eax
0x180013fb8  sub     eax, 1
0x180013fbb  jnz     short loc_180013FD2
0x180013fbd  nop
0x180013fbe  call    WINRT_IMPL_GetProcessHeap
0x180013fc3  mov     rcx, rax; hHeap
0x180013fc6  mov     r8, rdi; lpMem
0x180013fc9  xor     edx, edx; dwFlags
0x180013fcb  call    WINRT_IMPL_HeapFree
0x180013fd0  jmp     short loc_180013FDA
0x180013fd2  test    eax, eax
0x180013fd4  js      loc_1800140AF
0x180013fda  mov     [rsp+98h+lpMem], 0
0x180013fe3  mov     [rsp+98h+var_70], 0
0x180013fe8  lea     r14, [r14+r12*8]
0x180013fec  mov     rax, [r14]
0x180013fef  mov     qword ptr [r14], 0
0x180013ff6  mov     [rsp+98h+lpMem], rax
0x180013ffb  mov     [rsp+98h+var_70], 1
0x180014000  neg     rsi
0x180014003  sbb     rsi, rsi
0x180014006  and     rsi, r15
0x180014009  mov     r15, [rsi+38h]
0x18001400d  lea     rdi, [r14+8]
0x180014011  jmp     short loc_180014026
0x180014013  mov     rdx, rdi
0x180014016  mov     rcx, r14
0x180014019  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18001401e  add     r14, 8
0x180014022  add     rdi, 8
0x180014026  cmp     rdi, r15
0x180014029  jnz     short loc_180014013
0x18001402b  mov     r14, [rsi+38h]
0x18001402f  mov     rdi, [r14-8]
0x180014033  test    rdi, rdi
0x180014036  jz      short loc_18001405F
0x180014038  mov     eax, ebx
0x18001403a  lock xadd [rdi+18h], eax
0x18001403f  sub     eax, 1
0x180014042  jnz     short loc_1800140AB
0x180014044  nop
0x180014045  call    WINRT_IMPL_GetProcessHeap
0x18001404a  mov     rcx, rax; hHeap
0x18001404d  mov     r8, rdi; lpMem
0x180014050  xor     edx, edx; dwFlags
0x180014052  call    WINRT_IMPL_HeapFree
0x180014057  mov     qword ptr [r14-8], 0
0x18001405f  add     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFF8h
0x180014064  cmp     [rsp+98h+var_70], 0
0x180014069  jz      short loc_180014092
0x18001406b  mov     rdi, [rsp+98h+lpMem]
0x180014070  test    rdi, rdi
0x180014073  jz      short loc_180014092
0x180014075  lock xadd [rdi+18h], ebx
0x18001407a  sub     ebx, 1
0x18001407d  jnz     short loc_1800140B6
0x18001407f  nop
0x180014080  call    WINRT_IMPL_GetProcessHeap
0x180014085  mov     rcx, rax; hHeap
0x180014088  mov     r8, rdi; lpMem
0x18001408b  xor     edx, edx; dwFlags
0x18001408d  call    WINRT_IMPL_HeapFree
0x180014092  xor     eax, eax
0x180014094  jmp     short loc_18001409D
0x180014096  mov     eax, [rsp+98h+arg_8]
0x18001409d  add     rsp, 68h
0x1800140a1  pop     r15
0x1800140a3  pop     r14
0x1800140a5  pop     r12
0x1800140a7  pop     rdi
0x1800140a8  pop     rsi
0x1800140a9  pop     rbx
0x1800140aa  retn
0x1800140ab  test    eax, eax
0x1800140ad  jns     short loc_180014057
0x1800140af  call    cs:__imp_abort
0x1800140b6  test    ebx, ebx
0x1800140b8  jns     short loc_180014092
0x1800140ba  call    cs:__imp_abort
0x1800140c1  mov     [rsp+98h+var_68], 6BFh
0x1800140c9  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800140d0  mov     [r11-60h], rax
0x1800140d4  mov     qword ptr [r11-58h], 0
0x1800140dc  lea     rdx, [r11-68h]; struct winrt::impl::slim_source_location *
0x1800140e0  lea     rcx, [r11-50h]; this
0x1800140e4  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800140e9  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800140f0  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800140f5  call    _CxxThrowException_0
```
