# std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Eqrange<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)

- ea: `0x180046d48`
- end: `0x180046e9b`
- name: `??$_Eqrange@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@PEAX@std@@PEAU12@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `339`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004fa38`

## callees

- `0x180046d48`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046df6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046e5f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046df6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046e44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Eqrange<Microsoft::WRL::Wrappers::HString>(
        __int64 *a1,
        __int64 *a2,
        HSTRING *a3)
{
  __int64 v3; // r14
  __int64 v7; // rsi
  __int64 i; // rdi
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v10; // rax
  const WCHAR *v11; // rbx
  const WCHAR *v12; // rax
  __int64 j; // rdi
  const WCHAR *v14; // rbx
  const WCHAR *v15; // rax
  __int64 *result; // rax
  UINT32 v17[4]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 v18; // [rsp+80h] [rbp+40h] BYREF
  UINT32 length; // [rsp+88h] [rbp+48h] BYREF
  UINT32 v20; // [rsp+98h] [rbp+58h] BYREF

  v3 = *a1;
  v7 = *a1;
  for ( i = *(_QWORD *)(*a1 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)i )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(i + 32), &length);
    v10 = WindowsGetStringRawBuffer(*a3, &v18);
    if ( CompareStringOrdinal(StringRawBuffer, length, v10, v18, 1) == 1 )
    {
      i += 16;
    }
    else
    {
      if ( *(_BYTE *)(v7 + 25) )
      {
        v11 = WindowsGetStringRawBuffer(*a3, v17);
        v12 = WindowsGetStringRawBuffer(*(HSTRING *)(i + 32), &v20);
        if ( CompareStringOrdinal(v11, v17[0], v12, v20, 1) == 1 )
          v7 = i;
      }
      v3 = i;
    }
  }
  if ( *(_BYTE *)(v7 + 25) )
    j = *a1 + 8;
  else
    j = v7;
LABEL_13:
  for ( j = *(_QWORD *)j; !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 16) )
  {
    v14 = WindowsGetStringRawBuffer(*a3, &length);
    v15 = WindowsGetStringRawBuffer(*(HSTRING *)(j + 32), &v18);
    if ( CompareStringOrdinal(v14, length, v15, v18, 1) == 1 )
    {
      v7 = j;
      goto LABEL_13;
    }
  }
  result = a2;
  *a2 = v3;
  a2[1] = v7;
  return result;
}

```

## disassembly

```asm
0x180046d48  mov     [rsp-38h+arg_10], rbx
0x180046d4d  push    rbp
0x180046d4e  push    rsi
0x180046d4f  push    rdi
0x180046d50  push    r12
0x180046d52  push    r13
0x180046d54  push    r14
0x180046d56  push    r15
0x180046d58  mov     rbp, rsp
0x180046d5b  sub     rsp, 40h
0x180046d5f  mov     r14, [rcx]
0x180046d62  mov     r13, r8
0x180046d65  mov     r15, rdx
0x180046d68  mov     r12, rcx
0x180046d6b  mov     rsi, r14
0x180046d6e  mov     rdi, [r14+8]
0x180046d72  jmp     loc_180046E09
0x180046d77  mov     rcx, [rdi+20h]; string
0x180046d7b  lea     rdx, [rbp+length]; length
0x180046d7f  call    cs:__imp_WindowsGetStringRawBuffer
0x180046d85  mov     rcx, [r13+0]; string
0x180046d89  lea     rdx, [rbp+arg_0]; length
0x180046d8d  mov     rbx, rax
0x180046d90  call    cs:__imp_WindowsGetStringRawBuffer
0x180046d96  mov     r9d, [rbp+arg_0]; cchCount2
0x180046d9a  mov     rcx, rbx; lpString1
0x180046d9d  mov     edx, [rbp+length]; cchCount1
0x180046da0  mov     r8, rax; lpString2
0x180046da3  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180046dab  call    cs:__imp_CompareStringOrdinal
0x180046db1  cmp     eax, 1
0x180046db4  jnz     short loc_180046DBC
0x180046db6  add     rdi, 10h
0x180046dba  jmp     short loc_180046E06
0x180046dbc  cmp     byte ptr [rsi+19h], 0
0x180046dc0  jz      short loc_180046E03
0x180046dc2  mov     rcx, [r13+0]; string
0x180046dc6  lea     rdx, [rbp+var_10]; length
0x180046dca  call    cs:__imp_WindowsGetStringRawBuffer
0x180046dd0  mov     rcx, [rdi+20h]; string
0x180046dd4  lea     rdx, [rbp+arg_18]; length
0x180046dd8  mov     rbx, rax
0x180046ddb  call    cs:__imp_WindowsGetStringRawBuffer
0x180046de1  mov     r9d, [rbp+arg_18]; cchCount2
0x180046de5  mov     rcx, rbx; lpString1
0x180046de8  mov     edx, [rbp+var_10]; cchCount1
0x180046deb  mov     r8, rax; lpString2
0x180046dee  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180046df6  call    cs:__imp_CompareStringOrdinal
0x180046dfc  cmp     eax, 1
0x180046dff  cmovz   rsi, rdi
0x180046e03  mov     r14, rdi
0x180046e06  mov     rdi, [rdi]
0x180046e09  cmp     byte ptr [rdi+19h], 0
0x180046e0d  jz      loc_180046D77
0x180046e13  cmp     byte ptr [rsi+19h], 0
0x180046e17  jz      short loc_180046E23
0x180046e19  mov     rdi, [r12]
0x180046e1d  add     rdi, 8
0x180046e21  jmp     short loc_180046E26
0x180046e23  mov     rdi, rsi
0x180046e26  mov     rdi, [rdi]
0x180046e29  jmp     short loc_180046E73
0x180046e2b  mov     rcx, [r13+0]; string
0x180046e2f  lea     rdx, [rbp+length]; length
0x180046e33  call    cs:__imp_WindowsGetStringRawBuffer
0x180046e39  mov     rcx, [rdi+20h]; string
0x180046e3d  lea     rdx, [rbp+arg_0]; length
0x180046e41  mov     rbx, rax
0x180046e44  call    cs:__imp_WindowsGetStringRawBuffer
0x180046e4a  mov     r9d, [rbp+arg_0]; cchCount2
0x180046e4e  mov     rcx, rbx; lpString1
0x180046e51  mov     edx, [rbp+length]; cchCount1
0x180046e54  mov     r8, rax; lpString2
0x180046e57  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180046e5f  call    cs:__imp_CompareStringOrdinal
0x180046e65  cmp     eax, 1
0x180046e68  jnz     short loc_180046E6F
0x180046e6a  mov     rsi, rdi
0x180046e6d  jmp     short loc_180046E26
0x180046e6f  mov     rdi, [rdi+10h]
0x180046e73  cmp     byte ptr [rdi+19h], 0
0x180046e77  jz      short loc_180046E2B
0x180046e79  mov     rbx, [rsp+40h+arg_10]
0x180046e81  mov     rax, r15
0x180046e84  mov     [r15], r14
0x180046e87  mov     [r15+8], rsi
0x180046e8b  add     rsp, 40h
0x180046e8f  pop     r15
0x180046e91  pop     r14
0x180046e93  pop     r13
0x180046e95  pop     r12
0x180046e97  pop     rdi
0x180046e98  pop     rsi
0x180046e99  pop     rbp
0x180046e9a  retn
```
