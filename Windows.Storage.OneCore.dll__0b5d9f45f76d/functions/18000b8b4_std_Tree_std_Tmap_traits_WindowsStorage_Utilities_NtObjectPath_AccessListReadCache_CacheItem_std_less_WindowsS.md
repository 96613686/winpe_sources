# std::_Tree<std::_Tmap_traits<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem,std::less<WindowsStorage::Utilities::NtObjectPath>,std::allocator<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>,0>>::_Find_lower_bound<WindowsStorage::Utilities::NtObjectPath>(WindowsStorage::Utilities::NtObjectPath const &)

- ea: `0x18000b8b4`
- end: `0x18000b96d`
- name: `??$_Find_lower_bound@VNtObjectPath@Utilities@WindowsStorage@@@?$_Tree@V?$_Tmap_traits@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@U?$less@VNtObjectPath@Utilities@WindowsStorage@@@std@@V?$allocator@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@PEAX@std@@@1@AEBVNtObjectPath@Utilities@WindowsStorage@@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b150`

## callees

- `0x18000b8b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b934`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b917`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem,std::less<WindowsStorage::Utilities::NtObjectPath>,std::allocator<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>,0>>::_Find_lower_bound<WindowsStorage::Utilities::NtObjectPath>(
        __int64 a1,
        _QWORD *a2,
        HSTRING *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rdi
  HSTRING v7; // rcx
  PCWSTR StringRawBuffer; // rax
  HSTRING v9; // rcx
  const WCHAR *v10; // rbx
  const WCHAR *v11; // rax
  int v12; // eax
  UINT32 v14; // [rsp+50h] [rbp+8h] BYREF
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
    StringRawBuffer = WindowsGetStringRawBuffer(v7, &length);
    v9 = *a3;
    v10 = StringRawBuffer;
    v14 = 0;
    v11 = WindowsGetStringRawBuffer(v9, &v14);
    if ( CompareStringOrdinal(v10, length, v11, v14, 1) == 1 )
    {
      v6 += 2;
      v12 = 0;
    }
    else
    {
      a2[2] = v6;
      v12 = 1;
    }
    *((_DWORD *)a2 + 2) = v12;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b8b4  mov     [rsp+arg_10], rbx
0x18000b8b9  push    rsi
0x18000b8ba  push    rdi
0x18000b8bb  push    r14
0x18000b8bd  sub     rsp, 30h
0x18000b8c1  mov     rax, [rcx]
0x18000b8c4  mov     r14, r8
0x18000b8c7  mov     rsi, rdx
0x18000b8ca  mov     r9, [rax+8]
0x18000b8ce  mov     [rdx], r9
0x18000b8d1  mov     rdi, r9
0x18000b8d4  mov     qword ptr [rdx+8], 0
0x18000b8dc  mov     rax, [rcx]
0x18000b8df  mov     [rdx+10h], rax
0x18000b8e3  cmp     byte ptr [r9+19h], 0
0x18000b8e8  jnz     short loc_18000B95C
0x18000b8ea  mov     [rsi], rdi
0x18000b8ed  lea     rdx, [rsp+48h+length]; length
0x18000b8f2  mov     rcx, [rdi+20h]; string
0x18000b8f6  mov     [rsp+48h+length], 0
0x18000b8fe  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b904  mov     rcx, [r14]; string
0x18000b907  lea     rdx, [rsp+48h+arg_0]; length
0x18000b90c  mov     rbx, rax
0x18000b90f  mov     [rsp+48h+arg_0], 0
0x18000b917  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b91d  mov     r9d, [rsp+48h+arg_0]; cchCount2
0x18000b922  mov     rcx, rbx; lpString1
0x18000b925  mov     edx, [rsp+48h+length]; cchCount1
0x18000b929  mov     r8, rax; lpString2
0x18000b92c  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18000b934  call    cs:__imp_CompareStringOrdinal
0x18000b93a  cmp     eax, 1
0x18000b93d  jnz     short loc_18000B947
0x18000b93f  add     rdi, 10h
0x18000b943  xor     eax, eax
0x18000b945  jmp     short loc_18000B950
0x18000b947  mov     [rsi+10h], rdi
0x18000b94b  mov     eax, 1
0x18000b950  mov     [rsi+8], eax
0x18000b953  mov     rdi, [rdi]
0x18000b956  cmp     byte ptr [rdi+19h], 0
0x18000b95a  jz      short loc_18000B8EA
0x18000b95c  mov     rbx, [rsp+48h+arg_10]
0x18000b961  mov     rax, rsi
0x18000b964  add     rsp, 30h
0x18000b968  pop     r14
0x18000b96a  pop     rdi
0x18000b96b  pop     rsi
0x18000b96c  retn
```
