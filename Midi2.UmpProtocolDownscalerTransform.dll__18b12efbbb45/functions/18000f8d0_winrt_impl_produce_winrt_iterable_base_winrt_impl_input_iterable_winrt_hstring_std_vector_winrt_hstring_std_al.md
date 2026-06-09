# winrt::impl::produce<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(bool *)

- ea: `0x18000f8d0`
- end: `0x18000f91f`
- name: `?MoveNext@?$produce@Uiterator@?$iterable_base@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEA_N@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f8d0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(
        __int64 a1,
        bool *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v5; // rcx
  bool v6; // al

  v2 = a1 + 16;
  if ( !a1 )
    v2 = 32;
  v3 = *(_QWORD *)v2;
  v4 = a1 + 24;
  if ( !a1 )
    v4 = 40;
  v5 = *(_QWORD *)v4;
  v6 = 0;
  if ( v3 != *(_QWORD *)v4 )
  {
    *(_QWORD *)v2 = v3 + 8;
    if ( v3 + 8 != v5 )
      v6 = 1;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x18000f8d0  sub     rsp, 28h
0x18000f8d4  lea     r8, [rcx+10h]
0x18000f8d8  mov     eax, 20h ; ' '
0x18000f8dd  test    rcx, rcx
0x18000f8e0  cmovz   r8, rax
0x18000f8e4  mov     r9, [r8]
0x18000f8e7  lea     rax, [rcx+18h]
0x18000f8eb  mov     r10d, 28h ; '('
0x18000f8f1  cmovz   rax, r10
0x18000f8f5  mov     rcx, [rax]
0x18000f8f8  cmp     r9, rcx
0x18000f8fb  jz      short loc_18000F90D
0x18000f8fd  lea     rax, [r9+8]
0x18000f901  mov     [r8], rax
0x18000f904  cmp     rax, rcx
0x18000f907  jz      short loc_18000F90D
0x18000f909  mov     al, 1
0x18000f90b  jmp     short loc_18000F90F
0x18000f90d  xor     al, al
0x18000f90f  mov     [rdx], al
0x18000f911  xor     eax, eax
0x18000f913  jmp     short loc_18000F919
0x18000f915  mov     eax, [rsp+28h+arg_0]
0x18000f919  add     rsp, 28h
0x18000f91d  retn
```
