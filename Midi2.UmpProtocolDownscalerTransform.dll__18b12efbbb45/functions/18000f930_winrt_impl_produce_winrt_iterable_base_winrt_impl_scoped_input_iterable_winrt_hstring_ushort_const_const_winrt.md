# winrt::impl::produce<winrt::iterable_base<winrt::impl::scoped_input_iterable<winrt::hstring,ushort const * const *>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(bool *)

- ea: `0x18000f930`
- end: `0x18000f9d3`
- name: `?MoveNext@?$produce@Uiterator@?$iterable_base@U?$scoped_input_iterable@Uhstring@winrt@@PEBQEBG@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEA_N@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003a50`
- `0x18000cbe4`
- `0x18000f930`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::scoped_input_iterable<winrt::hstring,unsigned short const * const *>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(
        __int64 a1,
        bool *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // r9
  __int64 v6; // rdx
  bool v7; // zf
  __int64 v8; // rax
  __int64 *v10; // rdx
  __int64 v11; // [rsp+0h] [rbp-58h] BYREF
  int v12; // [rsp+20h] [rbp-38h] BYREF
  const char *v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h]
  _BYTE pExceptionObject[32]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+8h]

  v3 = a1 + 8;
  if ( !a1 )
    v3 = 24;
  if ( *(_BYTE *)(*(_QWORD *)v3 + 24LL) )
  {
    v12 = 1309;
    v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    v14 = 0;
    winrt::hresult_illegal_method_call::hresult_illegal_method_call(
      (winrt::hresult_illegal_method_call *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v12);
    try
    {
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    }
    catch ( ... )
    {
      v10 = &v11;
      *((_DWORD *)v10 + 24) = *(_DWORD *)winrt::to_hresult(v10 + 12);
      return v16;
    }
  }
  v4 = a1 + 24;
  if ( !a1 )
    v4 = 40;
  v5 = *(_QWORD *)v4;
  v6 = a1 + 16;
  if ( !a1 )
    v6 = 32;
  v7 = *(_QWORD *)v6 == v5;
  if ( *(_QWORD *)v6 != v5 )
  {
    v8 = *(_QWORD *)v6 + 8LL;
    *(_QWORD *)v6 = v8;
    v7 = v8 == v5;
  }
  *a2 = !v7;
  return 0;
}

```

## disassembly

```asm
0x18000f930  mov     r11, rsp
0x18000f933  sub     rsp, 58h
0x18000f937  mov     r8, rdx
0x18000f93a  lea     rax, [rcx+8]
0x18000f93e  mov     edx, 18h
0x18000f943  test    rcx, rcx
0x18000f946  cmovz   rax, rdx
0x18000f94a  mov     rax, [rax]
0x18000f94d  cmp     byte ptr [rax+18h], 0
0x18000f951  jnz     short loc_18000F998
0x18000f953  lea     rax, [rcx+18h]
0x18000f957  mov     edx, 28h ; '('
0x18000f95c  test    rcx, rcx
0x18000f95f  cmovz   rax, rdx
0x18000f963  mov     r9, [rax]
0x18000f966  lea     rdx, [rcx+10h]
0x18000f96a  mov     eax, 20h ; ' '
0x18000f96f  cmovz   rdx, rax
0x18000f973  mov     rax, [rdx]
0x18000f976  cmp     rax, r9
0x18000f979  jz      short loc_18000F985
0x18000f97b  add     rax, 8
0x18000f97f  mov     [rdx], rax
0x18000f982  cmp     rax, r9
0x18000f985  setnz   al
0x18000f988  mov     [r8], al
0x18000f98b  xor     eax, eax
0x18000f98d  jmp     short loc_18000F993
0x18000f98f  mov     eax, [rsp+58h+arg_0]
0x18000f993  add     rsp, 58h
0x18000f997  retn
0x18000f998  mov     [rsp+58h+var_38], 51Dh
0x18000f9a0  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000f9a7  mov     [r11-30h], rax
0x18000f9ab  mov     qword ptr [r11-28h], 0
0x18000f9b3  lea     rdx, [r11-38h]; struct winrt::impl::slim_source_location *
0x18000f9b7  lea     rcx, [r11-20h]; this
0x18000f9bb  call    ??0hresult_illegal_method_call@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::impl::slim_source_location const &)
0x18000f9c0  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18000f9c7  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000f9cc  call    _CxxThrowException_0
```
