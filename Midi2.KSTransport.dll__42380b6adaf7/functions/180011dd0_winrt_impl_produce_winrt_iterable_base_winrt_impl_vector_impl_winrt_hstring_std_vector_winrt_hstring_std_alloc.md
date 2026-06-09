# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(uint,void * *,uint *)

- ea: `0x180011dd0`
- end: `0x180011f30`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000526c`
- `0x18000529c`
- `0x1800052fc`
- `0x180005374`
- `0x1800104dc`
- `0x180011dd0`
- `0x180014864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011eb2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011eb2`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(
        __int64 a1,
        unsigned int a2,
        volatile signed __int32 **a3,
        unsigned int *a4)
{
  volatile signed __int32 **v4; // rbx
  unsigned int v5; // edi
  struct winrt::impl::hstring_header *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r14
  winrt::impl **v11; // r15
  __int64 v12; // rax
  unsigned int v13; // r12d
  struct winrt::impl::hstring_header *v14; // r13
  volatile signed __int32 *v15; // rsi
  int v16; // ecx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-58h] BYREF
  const char *v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+88h] [rbp+10h] BYREF
  unsigned int *v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  v4 = a3;
  v5 = a2;
  memset_0(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
    {
      v19 = 1345;
      v20 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
      v21 = 0;
      winrt::hresult_changed_state::hresult_changed_state(
        (winrt::hresult_changed_state *)pExceptionObject,
        (const struct winrt::impl::slim_source_location *)&v19);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    v10 = a1 + 24;
    if ( !a1 )
      v10 = 40;
    v11 = *(winrt::impl ***)v10;
    v12 = a1 + 32;
    if ( !a1 )
      v12 = 48;
    if ( v5 >= (unsigned int)((__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3) )
      v5 = (__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3;
    v13 = v5;
    if ( v5 )
    {
      while ( 1 )
      {
        v14 = winrt::impl::duplicate_hstring(*v11, v7);
        v15 = *v4;
        if ( *v4 )
        {
          v16 = _InterlockedDecrement(v15 + 6);
          if ( v16 )
          {
            if ( v16 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
          }
        }
        *v4 = (volatile signed __int32 *)v14;
        if ( !--v13 )
          break;
        ++v4;
        ++v11;
      }
    }
    *(_QWORD *)v10 += 8LL * v5;
    *v24 = v5;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v23);
  }
  return result;
}

```

## disassembly

```asm
0x180011dd0  mov     [rsp+arg_0], rbx
0x180011dd5  mov     [rsp+arg_10], rsi
0x180011dda  mov     [rsp+arg_18], r9
0x180011ddf  push    rdi
0x180011de0  push    r12
0x180011de2  push    r13
0x180011de4  push    r14
0x180011de6  push    r15
0x180011de8  sub     rsp, 50h
0x180011dec  mov     rbx, r8
0x180011def  mov     edi, edx
0x180011df1  mov     rsi, rcx
0x180011df4  mov     r8d, edi
0x180011df7  shl     r8, 3; Size
0x180011dfb  xor     edx, edx; Val
0x180011dfd  mov     rcx, rbx; void *
0x180011e00  call    memset_0
0x180011e05  lea     r8, [rsi+8]
0x180011e09  mov     eax, 18h
0x180011e0e  test    rsi, rsi
0x180011e11  cmovz   r8, rax
0x180011e15  lea     rax, [rsi+10h]
0x180011e19  mov     ecx, 20h ; ' '
0x180011e1e  cmovz   rax, rcx
0x180011e22  mov     rax, [rax]
0x180011e25  mov     ecx, [rax+28h]
0x180011e28  nop
0x180011e29  cmp     ecx, [r8]
0x180011e2c  jnz     loc_180011EF1
0x180011e32  lea     r14, [rsi+18h]
0x180011e36  mov     eax, 28h ; '('
0x180011e3b  test    rsi, rsi
0x180011e3e  cmovz   r14, rax
0x180011e42  mov     r15, [r14]
0x180011e45  lea     rax, [rsi+20h]
0x180011e49  mov     ecx, 30h ; '0'
0x180011e4e  cmovz   rax, rcx
0x180011e52  mov     rcx, [rax]
0x180011e55  sub     rcx, r15
0x180011e58  sar     rcx, 3
0x180011e5c  cmp     edi, ecx
0x180011e5e  cmovnb  edi, ecx
0x180011e61  mov     r12d, edi
0x180011e64  test    edi, edi
0x180011e66  jz      short loc_180011EB9
0x180011e68  mov     rcx, [r15]; this
0x180011e6b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011e70  mov     r13, rax
0x180011e73  mov     rsi, [rbx]
0x180011e76  test    rsi, rsi
0x180011e79  jz      short loc_180011E9B
0x180011e7b  or      ecx, 0FFFFFFFFh
0x180011e7e  lock xadd [rsi+18h], ecx
0x180011e83  sub     ecx, 1
0x180011e86  jnz     short loc_180011EAE
0x180011e88  nop
0x180011e89  call    WINRT_IMPL_GetProcessHeap
0x180011e8e  mov     rcx, rax; hHeap
0x180011e91  mov     r8, rsi; lpMem
0x180011e94  xor     edx, edx; dwFlags
0x180011e96  call    WINRT_IMPL_HeapFree
0x180011e9b  mov     [rbx], r13
0x180011e9e  add     r12d, 0FFFFFFFFh
0x180011ea2  jz      short loc_180011EB9
0x180011ea4  add     rbx, 8
0x180011ea8  add     r15, 8
0x180011eac  jmp     short loc_180011E68
0x180011eae  test    ecx, ecx
0x180011eb0  jns     short loc_180011E9B
0x180011eb2  call    cs:__imp_abort
0x180011eb9  mov     eax, edi
0x180011ebb  shl     rax, 3
0x180011ebf  add     [r14], rax
0x180011ec2  mov     rax, [rsp+78h+arg_18]
0x180011eca  mov     [rax], edi
0x180011ecc  xor     eax, eax
0x180011ece  jmp     short loc_180011ED7
0x180011ed0  mov     eax, [rsp+78h+arg_8]
0x180011ed7  lea     r11, [rsp+78h+var_28]
0x180011edc  mov     rbx, [r11+30h]
0x180011ee0  mov     rsi, [r11+40h]
0x180011ee4  mov     rsp, r11
0x180011ee7  pop     r15
0x180011ee9  pop     r14
0x180011eeb  pop     r13
0x180011eed  pop     r12
0x180011eef  pop     rdi
0x180011ef0  retn
0x180011ef1  mov     [rsp+78h+var_58], 541h
0x180011ef9  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180011f00  mov     [rsp+78h+var_50], rax
0x180011f05  mov     [rsp+78h+var_48], 0
0x180011f0e  lea     rdx, [rsp+78h+var_58]; struct winrt::impl::slim_source_location *
0x180011f13  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180011f18  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180011f1d  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180011f24  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180011f29  call    _CxxThrowException_0
```
