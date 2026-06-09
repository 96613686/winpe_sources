# std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)

- ea: `0x18000b7f4`
- end: `0x18000b8ad`
- name: `??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ba78`

## callees

- `0x18000b7f4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b874`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b857`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
        __int64 a1,
        _QWORD *a2,
        HSTRING *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rdi
  HSTRING v7; // rcx
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v9; // rax
  int v10; // eax
  UINT32 v12; // [rsp+50h] [rbp+8h] BYREF
  UINT32 length; // [rsp+58h] [rbp+10h] BYREF

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (HSTRING)v6[4];
    length = 0;
    v12 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v7, &length);
    v9 = WindowsGetStringRawBuffer(*a3, &v12);
    if ( CompareStringOrdinal(StringRawBuffer, length, v9, v12, 1) == 1 )
    {
      v6 += 2;
      v10 = 0;
    }
    else
    {
      a2[2] = v6;
      v10 = 1;
    }
    *((_DWORD *)a2 + 2) = v10;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b7f4  mov     [rsp+arg_10], rbx
0x18000b7f9  push    rsi
0x18000b7fa  push    rdi
0x18000b7fb  push    r14
0x18000b7fd  sub     rsp, 30h
0x18000b801  mov     rax, [rcx]
0x18000b804  mov     r14, r8
0x18000b807  mov     rsi, rdx
0x18000b80a  mov     r9, [rax+8]
0x18000b80e  mov     [rdx], r9
0x18000b811  mov     rdi, r9
0x18000b814  mov     qword ptr [rdx+8], 0
0x18000b81c  mov     rax, [rcx]
0x18000b81f  mov     [rdx+10h], rax
0x18000b823  cmp     byte ptr [r9+19h], 0
0x18000b828  jnz     short loc_18000B89C
0x18000b82a  mov     [rsi], rdi
0x18000b82d  lea     rdx, [rsp+48h+length]; length
0x18000b832  mov     rcx, [rdi+20h]; string
0x18000b836  mov     [rsp+48h+length], 0
0x18000b83e  mov     [rsp+48h+arg_0], 0
0x18000b846  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b84c  mov     rcx, [r14]; string
0x18000b84f  lea     rdx, [rsp+48h+arg_0]; length
0x18000b854  mov     rbx, rax
0x18000b857  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b85d  mov     r9d, [rsp+48h+arg_0]; cchCount2
0x18000b862  mov     rcx, rbx; lpString1
0x18000b865  mov     edx, [rsp+48h+length]; cchCount1
0x18000b869  mov     r8, rax; lpString2
0x18000b86c  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18000b874  call    cs:__imp_CompareStringOrdinal
0x18000b87a  cmp     eax, 1
0x18000b87d  jnz     short loc_18000B887
0x18000b87f  add     rdi, 10h
0x18000b883  xor     eax, eax
0x18000b885  jmp     short loc_18000B890
0x18000b887  mov     [rsi+10h], rdi
0x18000b88b  mov     eax, 1
0x18000b890  mov     [rsi+8], eax
0x18000b893  mov     rdi, [rdi]
0x18000b896  cmp     byte ptr [rdi+19h], 0
0x18000b89a  jz      short loc_18000B82A
0x18000b89c  mov     rbx, [rsp+48h+arg_10]
0x18000b8a1  mov     rax, rsi
0x18000b8a4  add     rsp, 30h
0x18000b8a8  pop     r14
0x18000b8aa  pop     rdi
0x18000b8ab  pop     rsi
0x18000b8ac  retn
```
