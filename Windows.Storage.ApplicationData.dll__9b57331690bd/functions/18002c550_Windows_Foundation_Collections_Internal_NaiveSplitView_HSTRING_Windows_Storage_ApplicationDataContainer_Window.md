# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,Windows::Storage::IApplicationDataContainer * *)

- ea: `0x18002c550`
- end: `0x18002c641`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIApplicationDataContainer@Storage@6@@Z`
- size: `241`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::ChunkView *this, HSTRING__ *key, Windows::Storage::IApplicationDataContainer **value)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c480`
- `0x1800316f0`

## callees

- `0x18000ef7c`
- `0x18002c550`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c60f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c60f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
        Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::ChunkView *this,
        HSTRING__ *key,
        Windows::Storage::IApplicationDataContainer **value)
{
  Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::Chunk *ptr; // rax
  bool v4; // di
  int v5; // ebx
  __int64 v9; // rsi
  unsigned int uSize; // ebp
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *v11; // r14
  XWinRT::StringEquals *v12; // rcx
  int v13; // eax
  bool fIsEqual; // [rsp+60h] [rbp+8h] BYREF
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > sKey; // [rsp+78h] [rbp+20h] BYREF

  ptr = this->_spChunk.ptr_;
  v4 = 0;
  v5 = 0;
  fIsEqual = 0;
  v9 = 0;
  uSize = ptr->_uSize;
  while ( v5 >= 0 )
  {
    if ( (unsigned int)v9 >= uSize )
      goto LABEL_9;
    v11 = this->_spChunk.ptr_->_apPairs[v9];
    sKey._value = 0;
    v5 = v11->get_Key(v11, &sKey._value);
    if ( v5 >= 0 )
    {
      v13 = XWinRT::StringEquals::operator()(v12, key, sKey._value, &fIsEqual);
      v4 = fIsEqual;
      v5 = v13;
      if ( v13 >= 0 && fIsEqual )
      {
        v5 = v11->get_Value(v11, value);
        WindowsDeleteString(sKey._value);
        if ( v5 < 0 )
          break;
LABEL_9:
        if ( v4 )
          return (unsigned int)v5;
        v5 = -2147483637;
        break;
      }
    }
    WindowsDeleteString(sKey._value);
    v9 = (unsigned int)(v9 + 1);
    sKey._value = 0;
  }
  *value = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c550  mov     [rsp+arg_8], rbx
0x18002c555  push    rbp
0x18002c556  push    rsi
0x18002c557  push    rdi
0x18002c558  push    r12
0x18002c55a  push    r13
0x18002c55c  push    r14
0x18002c55e  push    r15
0x18002c560  sub     rsp, 20h
0x18002c564  mov     rax, [this+28h]
0x18002c568  xor     dil, dil
0x18002c56b  xor     ebx, ebx
0x18002c56d  mov     [rsp+58h+fIsEqual], dil
0x18002c572  mov     r15, value
0x18002c575  mov     r12, key
0x18002c578  mov     r13, this
0x18002c57b  xor     esi, esi
0x18002c57d  mov     ebp, [rax+0Ch]
0x18002c580  test    ebx, ebx
0x18002c582  js      loc_18002C623
0x18002c588  cmp     esi, ebp
0x18002c58a  jnb     loc_18002C619
0x18002c590  mov     rax, [r13+28h]
0x18002c594  lea     key, [rsp+58h+sKey]
0x18002c599  mov     r14, [rax+rsi*8+10h]
0x18002c59e  mov     [rsp+58h+sKey._value], 0
0x18002c5a7  mov     this, r14
0x18002c5aa  mov     rax, [r14]
0x18002c5ad  mov     rax, [rax+30h]
0x18002c5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5b6  mov     ebx, eax
0x18002c5b8  test    eax, eax
0x18002c5ba  js      short loc_18002C5DE
0x18002c5bc  mov     value, [rsp+58h+sKey._value]; strRhs
0x18002c5c1  lea     r9, [rsp+58h+fIsEqual]; fEquals
0x18002c5c6  mov     key, r12; strLhs
0x18002c5c9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18002c5ce  mov     dil, [rsp+58h+fIsEqual]
0x18002c5d3  mov     ebx, eax
0x18002c5d5  test    eax, eax
0x18002c5d7  js      short loc_18002C5DE
0x18002c5d9  test    dil, dil
0x18002c5dc  jnz     short loc_18002C5F6
0x18002c5de  mov     this, [rsp+58h+sKey._value]; string
0x18002c5e3  call    cs:__imp_WindowsDeleteString
0x18002c5e9  inc     esi
0x18002c5eb  mov     [rsp+58h+sKey._value], 0
0x18002c5f4  jmp     short loc_18002C580
0x18002c5f6  mov     rax, [r14]
0x18002c5f9  mov     key, r15
0x18002c5fc  mov     this, r14
0x18002c5ff  mov     rax, [rax+38h]
0x18002c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c608  mov     this, [rsp+58h+sKey._value]; string
0x18002c60d  mov     ebx, eax
0x18002c60f  call    cs:__imp_WindowsDeleteString
0x18002c615  test    ebx, ebx
0x18002c617  js      short loc_18002C623
0x18002c619  test    dil, dil
0x18002c61c  jnz     short loc_18002C62A
0x18002c61e  mov     ebx, 8000000Bh
0x18002c623  mov     qword ptr [r15], 0
0x18002c62a  mov     eax, ebx
0x18002c62c  mov     rbx, [rsp+58h+arg_8]
0x18002c631  add     rsp, 20h
0x18002c635  pop     r15
0x18002c637  pop     r14
0x18002c639  pop     r13
0x18002c63b  pop     r12
0x18002c63d  pop     rdi
0x18002c63e  pop     rsi
0x18002c63f  pop     rbp
0x18002c640  retn
```
