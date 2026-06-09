# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::_Free(XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>> *)

- ea: `0x18001a218`
- end: `0x18001a274`
- name: `?_Free@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@CAXPEAV?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@@Z`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013910`
- `0x18001a18c`

## callees

- `0x180015748`
- `0x180015ab0`
- `0x180018d10`
- `0x18001a218`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a24c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a24c`

## pseudocode

```c
void __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::_Free(
        __int64 a1)
{
  HSTRING *Next; // rbx
  bool v3; // zf
  __int64 StartPosition; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    StartPosition = XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::GetStartPosition(a1);
    if ( StartPosition )
    {
      do
      {
        Next = (HSTRING *)XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::GetNext(
                            a1,
                            &StartPosition);
        WindowsDeleteString(*Next);
        v3 = StartPosition == 0;
        *Next = 0;
      }
      while ( !v3 );
    }
    XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::RemoveAll(a1);
  }
}

```

## disassembly

```asm
0x18001a218  test    rcx, rcx
0x18001a21b  jz      short locret_18001A273
0x18001a21d  mov     [rsp+arg_8], rbx
0x18001a222  push    rdi
0x18001a223  sub     rsp, 20h
0x18001a227  mov     rdi, rcx
0x18001a22a  call    ?GetStartPosition@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEBAPEAUTXPOSITION@2@XZ; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::GetStartPosition(void)
0x18001a22f  mov     [rsp+28h+arg_0], rax
0x18001a234  test    rax, rax
0x18001a237  jz      short loc_18001A261
0x18001a239  lea     rdx, [rsp+28h+arg_0]
0x18001a23e  mov     rcx, rdi
0x18001a241  call    ?GetNext@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAPEAVCPair@12@AEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::GetNext(XWinRT::TXPOSITION * &)
0x18001a246  mov     rbx, rax
0x18001a249  mov     rcx, [rax]; string
0x18001a24c  call    cs:__imp_WindowsDeleteString
0x18001a252  cmp     [rsp+28h+arg_0], 0
0x18001a258  mov     qword ptr [rbx], 0
0x18001a25f  jnz     short loc_18001A239
0x18001a261  mov     rcx, rdi
0x18001a264  call    ?RemoveAll@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAJXZ; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::RemoveAll(void)
0x18001a269  mov     rbx, [rsp+28h+arg_8]
0x18001a26e  add     rsp, 20h
0x18001a272  pop     rdi
0x18001a273  retn
```
