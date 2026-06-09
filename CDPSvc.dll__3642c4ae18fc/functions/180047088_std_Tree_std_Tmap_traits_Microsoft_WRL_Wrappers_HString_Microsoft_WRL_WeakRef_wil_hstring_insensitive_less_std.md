# std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)

- ea: `0x180047088`
- end: `0x180047125`
- name: `??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64 *, __int64, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180046ad8`
- `0x18004fac8`

## callees

- `0x180047088`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800470ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800470ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800470be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800470cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800470be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800470cf`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
        __int64 *a1,
        __int64 a2,
        HSTRING *a3)
{
  __int64 v3; // rax
  __int64 *v6; // rdi
  HSTRING v7; // rcx
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v9; // rax
  int v10; // eax
  UINT32 v12; // [rsp+50h] [rbp+8h] BYREF
  UINT32 length; // [rsp+58h] [rbp+10h] BYREF

  v3 = *a1;
  *(_DWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = v3;
  v6 = *(__int64 **)(v3 + 8);
  *(_QWORD *)a2 = v6;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v7 = (HSTRING)v6[4];
    *(_QWORD *)a2 = v6;
    StringRawBuffer = WindowsGetStringRawBuffer(v7, &length);
    v9 = WindowsGetStringRawBuffer(*a3, &v12);
    if ( CompareStringOrdinal(StringRawBuffer, length, v9, v12, 1) == 1 )
    {
      v10 = 0;
      v6 += 2;
    }
    else
    {
      *(_QWORD *)(a2 + 16) = v6;
      v10 = 1;
    }
    v6 = (__int64 *)*v6;
    *(_DWORD *)(a2 + 8) = v10;
  }
  return a2;
}

```

## disassembly

```asm
0x180047088  mov     [rsp+arg_10], rbx
0x18004708d  push    rsi
0x18004708e  push    rdi
0x18004708f  push    r14
0x180047091  sub     rsp, 30h
0x180047095  mov     rax, [rcx]
0x180047098  mov     r14, r8
0x18004709b  mov     rsi, rdx
0x18004709e  mov     dword ptr [rdx+8], 0
0x1800470a5  mov     [rdx+10h], rax
0x1800470a9  mov     rdi, [rax+8]
0x1800470ad  mov     [rdx], rdi
0x1800470b0  jmp     short loc_18004710E
0x1800470b2  mov     rcx, [rdi+20h]; string
0x1800470b6  lea     rdx, [rsp+48h+length]; length
0x1800470bb  mov     [rsi], rdi
0x1800470be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800470c4  mov     rcx, [r14]; string
0x1800470c7  lea     rdx, [rsp+48h+arg_0]; length
0x1800470cc  mov     rbx, rax
0x1800470cf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800470d5  mov     r9d, [rsp+48h+arg_0]; cchCount2
0x1800470da  mov     rcx, rbx; lpString1
0x1800470dd  mov     edx, [rsp+48h+length]; cchCount1
0x1800470e1  mov     r8, rax; lpString2
0x1800470e4  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x1800470ec  call    cs:__imp_CompareStringOrdinal
0x1800470f2  cmp     eax, 1
0x1800470f5  jnz     short loc_1800470FF
0x1800470f7  xor     eax, eax
0x1800470f9  add     rdi, 10h
0x1800470fd  jmp     short loc_180047108
0x1800470ff  mov     [rsi+10h], rdi
0x180047103  mov     eax, 1
0x180047108  mov     rdi, [rdi]
0x18004710b  mov     [rsi+8], eax
0x18004710e  cmp     byte ptr [rdi+19h], 0
0x180047112  jz      short loc_1800470B2
0x180047114  mov     rbx, [rsp+48h+arg_10]
0x180047119  mov     rax, rsi
0x18004711c  add     rsp, 30h
0x180047120  pop     r14
0x180047122  pop     rdi
0x180047123  pop     rsi
0x180047124  retn
```
