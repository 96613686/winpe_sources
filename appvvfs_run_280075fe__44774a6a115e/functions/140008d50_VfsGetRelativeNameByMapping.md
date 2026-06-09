# VfsGetRelativeNameByMapping

- ea: `0x140008d50`
- end: `0x140008e75`
- name: `VfsGetRelativeNameByMapping`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000437c`
- `0x140008c04`
- `0x14000947c`

## callees

- `0x140008d50`
- `0x14001187c`
- `0x140013294`
- `0x140013384`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140008da6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140008da6`

## pseudocode

```c
int __fastcall VfsGetRelativeNameByMapping(__int64 a1, const UNICODE_STRING *a2, char a3, _OWORD *a4)
{
  const UNICODE_STRING *v6; // r14
  int v9; // r8d
  int v10; // r9d
  __int64 Length; // rcx
  unsigned __int16 v12; // ax
  _WORD *v13; // rcx
  bool v14; // bl
  int result; // eax
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  __int128 v17; // [rsp+40h] [rbp-10h] BYREF
  bool v18; // [rsp+90h] [rbp+40h] BYREF

  v18 = 0;
  v6 = (const UNICODE_STRING *)((a3 != 0 ? 0x10 : 0) + a1 + 8);
  v16 = 0;
  v17 = 0;
  if ( !RtlPrefixUnicodeString(v6, a2, 1u) )
    return -1073741811;
  Length = v6->Length;
  v12 = a2->Length - Length;
  v13 = (wchar_t *)((char *)a2->Buffer + Length);
  LOWORD(v16) = v12;
  WORD1(v16) = v12;
  *((_QWORD *)&v16 + 1) = v13;
  if ( v12 < 2u || *v13 != 92 )
    return -1073741811;
  v14 = 0;
  if ( a3 && (*(_DWORD *)(a1 + 4) & 2) != 0 )
  {
    result = IsProcessElevated(&v18);
    if ( result < 0 )
      return result;
    v14 = v18;
  }
  LOBYTE(v10) = v14;
  LOBYTE(v9) = a3;
  if ( !(unsigned __int8)MappingPrefixFileName((int)a1 + 40, (unsigned int)&v16, v9, v10) )
    return -1073741811;
  result = GetRemainingPath(
             (__int64)&v16,
             *(_WORD *)(*(_QWORD *)((a3 != 0 ? 0x10 : 0) + a1 + 40) + 16LL),
             (__int64)&v17);
  if ( result >= 0 )
  {
    result = 0;
    *a4 = v17;
  }
  return result;
}

```

## disassembly

```asm
0x140008d50  mov     [rsp-28h+arg_0], rbx
0x140008d55  mov     [rsp-28h+arg_8], rsi
0x140008d5a  push    rbp
0x140008d5b  push    rdi
0x140008d5c  push    r13
0x140008d5e  push    r14
0x140008d60  push    r15
0x140008d62  mov     rbp, rsp
0x140008d65  sub     rsp, 50h
0x140008d69  mov     al, r8b
0x140008d6c  mov     [rbp+arg_10], 0
0x140008d70  lea     r14, [rcx+8]
0x140008d74  neg     al
0x140008d76  mov     dil, r8b
0x140008d79  mov     rsi, rcx
0x140008d7c  sbb     r10, r10
0x140008d7f  xorps   xmm0, xmm0
0x140008d82  and     r10d, 10h
0x140008d86  xorps   xmm1, xmm1
0x140008d89  add     r14, r10
0x140008d8c  mov     r13d, 1
0x140008d92  mov     rcx, r14; String1
0x140008d95  mov     r8b, r13b; CaseInSensitive
0x140008d98  mov     r15, r9
0x140008d9b  mov     rbx, rdx
0x140008d9e  movups  [rbp+var_20], xmm0
0x140008da2  movups  [rbp+var_10], xmm1
0x140008da6  call    cs:__imp_RtlPrefixUnicodeString
0x140008dad  nop     dword ptr [rax+rax+00h]
0x140008db2  test    al, al
0x140008db4  jz      loc_140008E56
0x140008dba  movzx   ecx, word ptr [r14]
0x140008dbe  movzx   eax, word ptr [rbx]
0x140008dc1  sub     ax, cx
0x140008dc4  add     rcx, [rbx+8]
0x140008dc8  mov     word ptr [rbp+var_20], ax
0x140008dcc  mov     word ptr [rbp+var_20+2], ax
0x140008dd0  mov     qword ptr [rbp+var_20+8], rcx
0x140008dd4  cmp     ax, 2
0x140008dd8  jb      short loc_140008E56
0x140008dda  cmp     word ptr [rcx], 5Ch ; '\'
0x140008dde  jnz     short loc_140008E56
0x140008de0  xor     bl, bl
0x140008de2  test    dil, dil
0x140008de5  jz      short loc_140008E06
0x140008de7  mov     eax, [rsi+4]
0x140008dea  test    al, 2
0x140008dec  jz      short loc_140008E06
0x140008dee  lea     rcx, [rbp+arg_10]
0x140008df2  call    IsProcessElevated
0x140008df7  test    eax, eax
0x140008df9  js      short loc_140008E5B
0x140008dfb  cmp     [rbp+arg_10], 0
0x140008dff  movzx   ebx, bl
0x140008e02  cmovnz  ebx, r13d
0x140008e06  lea     rcx, [rsi+28h]
0x140008e0a  mov     [rsp+50h+var_28], 0
0x140008e13  mov     r9b, bl
0x140008e16  lea     rdx, [rbp+var_20]
0x140008e1a  mov     r8b, dil
0x140008e1d  call    MappingPrefixFileName
0x140008e22  test    al, al
0x140008e24  jz      short loc_140008E56
0x140008e26  neg     dil
0x140008e29  lea     r8, [rbp+var_10]
0x140008e2d  lea     rcx, [rbp+var_20]
0x140008e31  sbb     rdx, rdx
0x140008e34  and     edx, 10h
0x140008e37  mov     rdx, [rdx+rsi+28h]
0x140008e3c  movzx   edx, word ptr [rdx+10h]
0x140008e40  call    GetRemainingPath
0x140008e45  test    eax, eax
0x140008e47  js      short loc_140008E5B
0x140008e49  movups  xmm0, [rbp+var_10]
0x140008e4d  xor     eax, eax
0x140008e4f  movdqu  xmmword ptr [r15], xmm0
0x140008e54  jmp     short loc_140008E5B
0x140008e56  mov     eax, 0C000000Dh
0x140008e5b  lea     r11, [rsp+50h+var_s0]
0x140008e60  mov     rbx, [r11+30h]
0x140008e64  mov     rsi, [r11+38h]
0x140008e68  mov     rsp, r11
0x140008e6b  pop     r15
0x140008e6d  pop     r14
0x140008e6f  pop     r13
0x140008e71  pop     rdi
0x140008e72  pop     rbp
0x140008e73  retn
```
