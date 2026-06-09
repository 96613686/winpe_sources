# InvStrCmpIW(ushort const *,ushort const *)

- ea: `0x180016b7c`
- end: `0x180016c1a`
- name: `?InvStrCmpIW@@YAHPEBG0@Z`
- size: `158`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000620c`

## callees

- `0x180016c20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016bfa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016bfa`

## pseudocode

```c
__int64 __fastcall InvStrCmpIW(PCNZWCH lpString1, const unsigned __int16 *a2)
{
  int v3; // eax
  int v4; // r11d
  int cchCount2; // ecx
  unsigned __int64 v7; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  StringCchLengthW(lpString1, 0x7FFFFFFFu, &v7);
  v3 = StringCchLengthW(L"User", 0x7FFFFFFFu, &v8);
  cchCount2 = v8;
  if ( v3 < 0 )
    cchCount2 = -1;
  return (unsigned int)(CompareStringW(0x409u, 1u, lpString1, v4, L"User", cchCount2) - 2);
}

```

## disassembly

```asm
0x180016b7c  mov     rax, rsp
0x180016b7f  mov     [rax+8], rbx
0x180016b83  mov     [rax+20h], rsi
0x180016b87  mov     [rax+10h], rdx
0x180016b8b  push    rdi
0x180016b8c  sub     rsp, 30h
0x180016b90  mov     edi, 7FFFFFFFh
0x180016b95  mov     qword ptr [rax+10h], 0
0x180016b9d  mov     edx, edi; unsigned __int64
0x180016b9f  mov     qword ptr [rax+18h], 0
0x180016ba7  lea     r8, [rax+10h]; unsigned __int64 *
0x180016bab  mov     rbx, rcx
0x180016bae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016bb3  mov     r11, [rsp+38h+arg_8]
0x180016bb8  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x180016bbd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016bc1  mov     edx, edi; unsigned __int64
0x180016bc3  test    eax, eax
0x180016bc5  lea     rdi, String2; "User"
0x180016bcc  mov     rcx, rdi; unsigned __int16 *
0x180016bcf  cmovs   r11, rsi
0x180016bd3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180016bd8  mov     rcx, [rsp+38h+arg_10]
0x180016bdd  lea     edx, [rsi+2]; dwCmpFlags
0x180016be0  test    eax, eax
0x180016be2  mov     r9d, r11d; cchCount1
0x180016be5  mov     r8, rbx; lpString1
0x180016be8  cmovs   rcx, rsi
0x180016bec  mov     [rsp+38h+cchCount2], ecx; cchCount2
0x180016bf0  mov     ecx, 409h; Locale
0x180016bf5  mov     [rsp+38h+lpString2], rdi; lpString2
0x180016bfa  call    cs:__imp_CompareStringW
0x180016c01  nop     dword ptr [rax+rax+00h]
0x180016c06  mov     rbx, [rsp+38h+arg_0]
0x180016c0b  sub     eax, 2
0x180016c0e  mov     rsi, [rsp+38h+arg_18]
0x180016c13  add     rsp, 30h
0x180016c17  pop     rdi
0x180016c18  retn
```
