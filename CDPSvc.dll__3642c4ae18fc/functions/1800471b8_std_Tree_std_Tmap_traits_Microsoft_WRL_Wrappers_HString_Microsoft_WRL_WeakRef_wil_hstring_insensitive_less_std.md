# std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>,void *> * const,Microsoft::WRL::Wrappers::HString const &)

- ea: `0x1800471b8`
- end: `0x180047223`
- name: `??$_Lower_bound_duplicate@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@PEAX@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `107`
- prototype: `char __fastcall(__int64, __int64, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180046ad8`
- `0x18004fac8`

## callees

- `0x1800471b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180047208`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180047208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800471d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800471ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800471d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800471ea`

## pseudocode

```c
char __fastcall std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(
        __int64 a1,
        __int64 a2,
        HSTRING *a3)
{
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v5; // rax
  char v6; // di
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  UINT32 length; // [rsp+48h] [rbp+10h] BYREF

  v8 = a1;
  if ( *(_BYTE *)(a2 + 25) )
    return 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*a3, &length);
  v5 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 32), (UINT32 *)&v8);
  v6 = 1;
  if ( CompareStringOrdinal(StringRawBuffer, length, v5, v8, 1) == 1 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x1800471b8  mov     [rsp+arg_10], rbx
0x1800471bd  mov     [rsp+arg_0], rcx
0x1800471c2  push    rdi
0x1800471c3  sub     rsp, 30h
0x1800471c7  cmp     byte ptr [rdx+19h], 0
0x1800471cb  mov     rdi, rdx
0x1800471ce  jnz     short loc_180047212
0x1800471d0  mov     rcx, [r8]; string
0x1800471d3  lea     rdx, [rsp+38h+length]; length
0x1800471d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800471de  mov     rcx, [rdi+20h]; string
0x1800471e2  lea     rdx, [rsp+38h+arg_0]; length
0x1800471e7  mov     rbx, rax
0x1800471ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800471f0  mov     r9d, dword ptr [rsp+38h+arg_0]; cchCount2
0x1800471f5  mov     edi, 1
0x1800471fa  mov     edx, [rsp+38h+length]; cchCount1
0x1800471fe  mov     r8, rax; lpString2
0x180047201  mov     rcx, rbx; lpString1
0x180047204  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x180047208  call    cs:__imp_CompareStringOrdinal
0x18004720e  cmp     eax, edi
0x180047210  jnz     short loc_180047215
0x180047212  xor     dil, dil
0x180047215  mov     rbx, [rsp+38h+arg_10]
0x18004721a  mov     al, dil
0x18004721d  add     rsp, 30h
0x180047221  pop     rdi
0x180047222  retn
```
