# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Hashval(_GUID const &)

- ea: `0x18000ce94`
- end: `0x18000cf22`
- name: `?_Hashval@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEBA_KAEBU_GUID@@@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008680`
- `0x18000d3c0`
- `0x18000e1a4`

## callees

- `0x18000ce94`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Hashval(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // r9
  unsigned __int64 i; // r10
  __int64 v6; // rax
  unsigned __int64 j; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 result; // rax

  v2 = 0xCBF29CE484222325uLL;
  v3 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
  {
    v6 = *(unsigned __int8 *)(a2 + i);
    v3 = 0x100000001B3LL * (v6 ^ v3);
  }
  for ( j = 0; j < 8; ++j )
  {
    v8 = *(unsigned __int8 *)(a2 + j + 8);
    v2 = 0x100000001B3LL * (v8 ^ v2);
  }
  v9 = *(_QWORD *)(a1 + 40);
  result = v9 & (v2 ^ v3 ^ HIDWORD(v3) ^ HIDWORD(v2));
  if ( *(_QWORD *)(a1 + 48) <= result )
    return result - (v9 >> 1) - 1;
  return result;
}

```

## disassembly

```asm
0x18000ce94  mov     [rsp+arg_0], rbx
0x18000ce99  mov     [rsp+arg_8], rdi
0x18000ce9e  mov     r8, 0CBF29CE484222325h
0x18000cea8  mov     rbx, rdx
0x18000ceab  mov     r9, r8
0x18000ceae  mov     r11, rcx
0x18000ceb1  xor     r10d, r10d
0x18000ceb4  mov     rdi, 100000001B3h
0x18000cebe  movzx   eax, byte ptr [rdx+r10]
0x18000cec3  inc     r10
0x18000cec6  xor     r9, rax
0x18000cec9  imul    r9, rdi
0x18000cecd  cmp     r10, 8
0x18000ced1  jb      short loc_18000CEBE
0x18000ced3  mov     rdx, r9
0x18000ced6  shr     rdx, 20h
0x18000ceda  xor     rdx, r9
0x18000cedd  xor     ecx, ecx
0x18000cedf  movzx   eax, byte ptr [rbx+rcx+8]
0x18000cee4  inc     rcx
0x18000cee7  xor     r8, rax
0x18000ceea  imul    r8, rdi
0x18000ceee  cmp     rcx, 8
0x18000cef2  jb      short loc_18000CEDF
0x18000cef4  mov     rcx, [r11+28h]
0x18000cef8  mov     rax, r8
0x18000cefb  shr     rax, 20h
0x18000ceff  xor     rax, rdx
0x18000cf02  xor     rax, r8
0x18000cf05  and     rax, rcx
0x18000cf08  cmp     [r11+30h], rax
0x18000cf0c  ja      short loc_18000CF17
0x18000cf0e  shr     rcx, 1
0x18000cf11  sub     rax, rcx
0x18000cf14  dec     rax
0x18000cf17  mov     rbx, [rsp+arg_0]
0x18000cf1c  mov     rdi, [rsp+arg_8]
0x18000cf21  retn
```
