# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x18002bec0`
- end: `0x18002bf76`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::ChunkView *this, HSTRING__ *key, unsigned __int8 *found)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002be40`
- `0x180031300`

## callees

- `0x18000ef7c`
- `0x18002bec0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bf5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bf5d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::ChunkView::HasKey(
        Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::ChunkView *this,
        HSTRING__ *key,
        unsigned __int8 *found)
{
  int v3; // ebx
  Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::Chunk *ptr; // rax
  __int64 v8; // rdi
  unsigned int uSize; // ebp
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *v10; // rcx
  XWinRT::StringEquals *v11; // rcx
  HSTRING__ *value; // rcx
  bool fEquals; // [rsp+50h] [rbp+8h] BYREF
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > sKey; // [rsp+60h] [rbp+18h] BYREF

  *found = 0;
  v3 = 0;
  ptr = this->_spChunk.ptr_;
  fEquals = 0;
  v8 = 0;
  uSize = ptr->_uSize;
  while ( v3 >= 0 && (unsigned int)v8 < uSize )
  {
    v10 = this->_spChunk.ptr_->_apPairs[v8];
    sKey._value = 0;
    v3 = v10->get_Key(v10, &sKey._value);
    if ( v3 >= 0 )
    {
      v3 = XWinRT::StringEquals::operator()(v11, key, sKey._value, &fEquals);
      if ( v3 >= 0 && fEquals )
      {
        value = sKey._value;
        *found = 1;
        WindowsDeleteString(value);
        return (unsigned int)v3;
      }
    }
    WindowsDeleteString(sKey._value);
    v8 = (unsigned int)(v8 + 1);
    sKey._value = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002bec0  mov     [rsp+arg_8], rbx
0x18002bec5  push    rbp
0x18002bec6  push    rsi
0x18002bec7  push    rdi
0x18002bec8  push    r14
0x18002beca  push    r15
0x18002becc  sub     rsp, 20h
0x18002bed0  mov     byte ptr [found], 0
0x18002bed4  xor     ebx, ebx
0x18002bed6  mov     rax, [this+28h]
0x18002beda  mov     rsi, found
0x18002bedd  mov     r15, key
0x18002bee0  mov     [rsp+48h+fEquals], 0
0x18002bee5  mov     r14, this
0x18002bee8  xor     edi, edi
0x18002beea  mov     ebp, [rax+0Ch]
0x18002beed  test    ebx, ebx
0x18002beef  js      short loc_18002BF63
0x18002bef1  cmp     edi, ebp
0x18002bef3  jnb     short loc_18002BF63
0x18002bef5  mov     rax, [r14+28h]
0x18002bef9  lea     key, [rsp+48h+sKey]
0x18002befe  mov     this, [rax+rdi*8+10h]
0x18002bf03  mov     [rsp+48h+sKey._value], 0
0x18002bf0c  mov     rax, [this]
0x18002bf0f  mov     rax, [rax+30h]
0x18002bf13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf18  mov     ebx, eax
0x18002bf1a  test    eax, eax
0x18002bf1c  js      short loc_18002BF3D
0x18002bf1e  mov     found, [rsp+48h+sKey._value]; strRhs
0x18002bf23  lea     r9, [rsp+48h+fEquals]; fEquals
0x18002bf28  mov     key, r15; strLhs
0x18002bf2b  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18002bf30  mov     ebx, eax
0x18002bf32  test    eax, eax
0x18002bf34  js      short loc_18002BF3D
0x18002bf36  cmp     [rsp+48h+fEquals], 0
0x18002bf3b  jnz     short loc_18002BF55
0x18002bf3d  mov     this, [rsp+48h+sKey._value]; string
0x18002bf42  call    cs:__imp_WindowsDeleteString
0x18002bf48  inc     edi
0x18002bf4a  mov     [rsp+48h+sKey._value], 0
0x18002bf53  jmp     short loc_18002BEED
0x18002bf55  mov     this, [rsp+48h+sKey._value]; string
0x18002bf5a  mov     byte ptr [rsi], 1
0x18002bf5d  call    cs:__imp_WindowsDeleteString
0x18002bf63  mov     eax, ebx
0x18002bf65  mov     rbx, [rsp+48h+arg_8]
0x18002bf6a  add     rsp, 20h
0x18002bf6e  pop     r15
0x18002bf70  pop     r14
0x18002bf72  pop     rdi
0x18002bf73  pop     rsi
0x18002bf74  pop     rbp
0x18002bf75  retn
```
