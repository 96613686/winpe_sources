# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetMany(uint,void * *,uint *)

- ea: `0x1800155a0`
- end: `0x180015700`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800046a0`
- `0x1800046b8`
- `0x180004718`
- `0x180004784`
- `0x180013a64`
- `0x1800155a0`
- `0x1800194c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015682`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015682`

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
0x1800155a0  mov     [rsp+arg_0], rbx
0x1800155a5  mov     [rsp+arg_10], rsi
0x1800155aa  mov     [rsp+arg_18], r9
0x1800155af  push    rdi
0x1800155b0  push    r12
0x1800155b2  push    r13
0x1800155b4  push    r14
0x1800155b6  push    r15
0x1800155b8  sub     rsp, 50h
0x1800155bc  mov     rbx, r8
0x1800155bf  mov     edi, edx
0x1800155c1  mov     rsi, rcx
0x1800155c4  mov     r8d, edi
0x1800155c7  shl     r8, 3; Size
0x1800155cb  xor     edx, edx; Val
0x1800155cd  mov     rcx, rbx; void *
0x1800155d0  call    memset_0
0x1800155d5  lea     r8, [rsi+8]
0x1800155d9  mov     eax, 18h
0x1800155de  test    rsi, rsi
0x1800155e1  cmovz   r8, rax
0x1800155e5  lea     rax, [rsi+10h]
0x1800155e9  mov     ecx, 20h ; ' '
0x1800155ee  cmovz   rax, rcx
0x1800155f2  mov     rax, [rax]
0x1800155f5  mov     ecx, [rax+28h]
0x1800155f8  nop
0x1800155f9  cmp     ecx, [r8]
0x1800155fc  jnz     loc_1800156C1
0x180015602  lea     r14, [rsi+18h]
0x180015606  mov     eax, 28h ; '('
0x18001560b  test    rsi, rsi
0x18001560e  cmovz   r14, rax
0x180015612  mov     r15, [r14]
0x180015615  lea     rax, [rsi+20h]
0x180015619  mov     ecx, 30h ; '0'
0x18001561e  cmovz   rax, rcx
0x180015622  mov     rcx, [rax]
0x180015625  sub     rcx, r15
0x180015628  sar     rcx, 3
0x18001562c  cmp     edi, ecx
0x18001562e  cmovnb  edi, ecx
0x180015631  mov     r12d, edi
0x180015634  test    edi, edi
0x180015636  jz      short loc_180015689
0x180015638  mov     rcx, [r15]; this
0x18001563b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180015640  mov     r13, rax
0x180015643  mov     rsi, [rbx]
0x180015646  test    rsi, rsi
0x180015649  jz      short loc_18001566B
0x18001564b  or      ecx, 0FFFFFFFFh
0x18001564e  lock xadd [rsi+18h], ecx
0x180015653  sub     ecx, 1
0x180015656  jnz     short loc_18001567E
0x180015658  nop
0x180015659  call    WINRT_IMPL_GetProcessHeap
0x18001565e  mov     rcx, rax; hHeap
0x180015661  mov     r8, rsi; lpMem
0x180015664  xor     edx, edx; dwFlags
0x180015666  call    WINRT_IMPL_HeapFree
0x18001566b  mov     [rbx], r13
0x18001566e  add     r12d, 0FFFFFFFFh
0x180015672  jz      short loc_180015689
0x180015674  add     rbx, 8
0x180015678  add     r15, 8
0x18001567c  jmp     short loc_180015638
0x18001567e  test    ecx, ecx
0x180015680  jns     short loc_18001566B
0x180015682  call    cs:__imp_abort
0x180015689  mov     eax, edi
0x18001568b  shl     rax, 3
0x18001568f  add     [r14], rax
0x180015692  mov     rax, [rsp+78h+arg_18]
0x18001569a  mov     [rax], edi
0x18001569c  xor     eax, eax
0x18001569e  jmp     short loc_1800156A7
0x1800156a0  mov     eax, [rsp+78h+arg_8]
0x1800156a7  lea     r11, [rsp+78h+var_28]
0x1800156ac  mov     rbx, [r11+30h]
0x1800156b0  mov     rsi, [r11+40h]
0x1800156b4  mov     rsp, r11
0x1800156b7  pop     r15
0x1800156b9  pop     r14
0x1800156bb  pop     r13
0x1800156bd  pop     r12
0x1800156bf  pop     rdi
0x1800156c0  retn
0x1800156c1  mov     [rsp+78h+var_58], 541h
0x1800156c9  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800156d0  mov     [rsp+78h+var_50], rax
0x1800156d5  mov     [rsp+78h+var_48], 0
0x1800156de  lea     rdx, [rsp+78h+var_58]; struct winrt::impl::slim_source_location *
0x1800156e3  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800156e8  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x1800156ed  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x1800156f4  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800156f9  call    _CxxThrowException_0
```
