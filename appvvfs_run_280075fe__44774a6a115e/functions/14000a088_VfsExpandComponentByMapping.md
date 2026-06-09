# VfsExpandComponentByMapping

- ea: `0x14000a088`
- end: `0x14000a225`
- name: `VfsExpandComponentByMapping`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a22c`

## callees

- `0x14000a088`
- `0x140013030`
- `0x14001322c`
- `0x140013d00`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000a181`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000a1b9`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000a181`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000a1b9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000a13b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000a162`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000a13b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000a162`

## pseudocode

```c
char __fastcall VfsExpandComponentByMapping(__int64 a1, __int64 a2, const UNICODE_STRING *a3, __int64 a4, int a5)
{
  __int64 v5; // r11
  unsigned __int16 v7; // r10
  __int64 *v9; // r12
  __int64 v10; // r15
  __int64 v11; // rbx
  __int64 v12; // r14
  unsigned __int64 Length; // r13
  const UNICODE_STRING *v14; // rcx
  __int64 v15; // r14
  __int64 v16; // r9
  _DWORD v18[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v19; // [rsp+38h] [rbp-10h]
  const UNICODE_STRING *String1; // [rsp+90h] [rbp+48h]

  v5 = *(unsigned __int16 *)(a1 + 8);
  v7 = *(_WORD *)a2;
  v18[1] = 0;
  if ( (unsigned __int16)v5 < v7 )
  {
    v19 = *(_QWORD *)(a2 + 8) + v5;
    LOWORD(v18[0]) = v7 - v5;
    HIWORD(v18[0]) = v7 - v5;
  }
  else
  {
    v19 = 0;
    v18[0] = 0;
  }
  v9 = (__int64 *)(a1 + 40);
  if ( !(unsigned __int8)FileNamePrefixMapping((unsigned int)v18, (int)a1 + 40, (_DWORD)a3, a4) )
    return 0;
  v10 = v9[1];
  v11 = 16LL * (unsigned __int16)GetNumberComponents(v18);
  String1 = (const UNICODE_STRING *)(v11 + *v9 + 24);
  if ( !RtlEqualUnicodeString(String1, a3, 1u) )
  {
    v12 = v11 + v10;
    if ( !v10 || !RtlEqualUnicodeString((PCUNICODE_STRING)(v12 + 24), a3, 1u) )
    {
      Length = String1->Length;
      if ( !RtlPrefixUnicodeString(String1, a3, 1u) || a3->Buffer[Length >> 1] != 58 )
      {
        if ( !v10 )
          return 0;
        v14 = (const UNICODE_STRING *)(v12 + 24);
        v15 = *(_WORD *)(v12 + 24) >> 1;
        if ( !RtlPrefixUnicodeString(v14, a3, 1u) || a3->Buffer[v15] != 58 )
          return 0;
      }
    }
  }
  v16 = *v9;
  if ( a5 - 12 < (unsigned int)*(unsigned __int16 *)(v11 + *v9 + 24) )
    return 0;
  *(_QWORD *)a4 = 0;
  *(_DWORD *)(a4 + 8) = *(unsigned __int16 *)(v11 + v16 + 24);
  memmove((void *)(a4 + 12), *(const void **)(v11 + v16 + 32), *(unsigned __int16 *)(v11 + v16 + 24));
  return 1;
}

```

## disassembly

```asm
0x14000a088  push    rbp
0x14000a08a  push    rbx
0x14000a08b  push    rsi
0x14000a08c  push    rdi
0x14000a08d  push    r12
0x14000a08f  push    r13
0x14000a091  push    r14
0x14000a093  push    r15
0x14000a095  mov     rbp, rsp
0x14000a098  sub     rsp, 48h
0x14000a09c  movzx   r11d, word ptr [rcx+8]
0x14000a0a1  mov     rdi, r9
0x14000a0a4  movzx   r10d, word ptr [rdx]
0x14000a0a8  mov     rsi, r8
0x14000a0ab  mov     dword ptr [rbp+var_18+4], 0
0x14000a0b2  cmp     r11w, r10w
0x14000a0b6  jb      short loc_14000A0C7
0x14000a0b8  xor     eax, eax
0x14000a0ba  mov     qword ptr [rbp+var_18+8], 0
0x14000a0c2  mov     dword ptr [rbp+var_18], eax
0x14000a0c5  jmp     short loc_14000A0E0
0x14000a0c7  mov     rax, r11
0x14000a0ca  add     rax, [rdx+8]
0x14000a0ce  sub     r10w, r11w
0x14000a0d2  mov     qword ptr [rbp+var_18+8], rax
0x14000a0d6  mov     word ptr [rbp+var_18], r10w
0x14000a0db  mov     word ptr [rbp+var_18+2], r10w
0x14000a0e0  movaps  xmm0, [rbp+var_18]
0x14000a0e4  lea     r12, [rcx+28h]
0x14000a0e8  lea     rax, [rbp+String1]
0x14000a0ec  movdqa  [rbp+var_18], xmm0
0x14000a0f1  mov     rdx, r12
0x14000a0f4  mov     byte ptr [rbp+String1], 0
0x14000a0f8  lea     rcx, [rbp+var_18]
0x14000a0fc  mov     [rsp+48h+var_20], rax
0x14000a101  call    FileNamePrefixMapping
0x14000a106  test    al, al
0x14000a108  jz      loc_14000A211
0x14000a10e  mov     r15, [r12+8]
0x14000a113  lea     rcx, [rbp+var_18]
0x14000a117  call    GetNumberComponents
0x14000a11c  mov     r13, [r12]
0x14000a120  mov     r8b, 1; CaseInSensitive
0x14000a123  movzx   ebx, ax
0x14000a126  add     r13, 18h
0x14000a12a  shl     rbx, 4
0x14000a12e  mov     rdx, rsi; String2
0x14000a131  add     r13, rbx
0x14000a134  mov     rcx, r13; String1
0x14000a137  mov     [rbp+String1], r13
0x14000a13b  call    cs:__imp_RtlEqualUnicodeString
0x14000a142  nop     dword ptr [rax+rax+00h]
0x14000a147  test    al, al
0x14000a149  jnz     loc_14000A1D5
0x14000a14f  lea     r14, [rbx+r15]
0x14000a153  test    r15, r15
0x14000a156  jz      short loc_14000A172
0x14000a158  lea     rcx, [r14+18h]; String1
0x14000a15c  mov     r8b, 1; CaseInSensitive
0x14000a15f  mov     rdx, rsi; String2
0x14000a162  call    cs:__imp_RtlEqualUnicodeString
0x14000a169  nop     dword ptr [rax+rax+00h]
0x14000a16e  test    al, al
0x14000a170  jnz     short loc_14000A1D5
0x14000a172  mov     rcx, [rbp+String1]; String1
0x14000a176  mov     r8b, 1; CaseInSensitive
0x14000a179  movzx   r13d, word ptr [r13+0]
0x14000a17e  mov     rdx, rsi; String2
0x14000a181  call    cs:__imp_RtlPrefixUnicodeString
0x14000a188  nop     dword ptr [rax+rax+00h]
0x14000a18d  test    al, al
0x14000a18f  jz      short loc_14000A1A0
0x14000a191  mov     rax, [rsi+8]
0x14000a195  shr     r13, 1
0x14000a198  cmp     word ptr [rax+r13*2], 3Ah ; ':'
0x14000a19e  jz      short loc_14000A1D5
0x14000a1a0  test    r15, r15
0x14000a1a3  jz      short loc_14000A211
0x14000a1a5  lea     rcx, [r14+18h]; String1
0x14000a1a9  mov     r8b, 1; CaseInSensitive
0x14000a1ac  movzx   eax, word ptr [rcx]
0x14000a1af  mov     rdx, rsi; String2
0x14000a1b2  shr     ax, 1
0x14000a1b5  movzx   r14d, ax
0x14000a1b9  call    cs:__imp_RtlPrefixUnicodeString
0x14000a1c0  nop     dword ptr [rax+rax+00h]
0x14000a1c5  test    al, al
0x14000a1c7  jz      short loc_14000A211
0x14000a1c9  mov     rax, [rsi+8]
0x14000a1cd  cmp     word ptr [rax+r14*2], 3Ah ; ':'
0x14000a1d3  jnz     short loc_14000A211
0x14000a1d5  mov     r9, [r12]
0x14000a1d9  mov     edx, [rbp+arg_20]
0x14000a1dc  add     edx, 0FFFFFFF4h
0x14000a1df  movzx   ecx, word ptr [rbx+r9+18h]
0x14000a1e5  cmp     edx, ecx
0x14000a1e7  jb      short loc_14000A211
0x14000a1e9  mov     qword ptr [rdi], 0
0x14000a1f0  movzx   ecx, word ptr [rbx+r9+18h]
0x14000a1f6  mov     [rdi+8], ecx
0x14000a1f9  lea     rcx, [rdi+0Ch]; void *
0x14000a1fd  movzx   r8d, word ptr [rbx+r9+18h]; Size
0x14000a203  mov     rdx, [rbx+r9+20h]; Src
0x14000a208  call    memmove
0x14000a20d  mov     al, 1
0x14000a20f  jmp     short loc_14000A213
0x14000a211  xor     al, al
0x14000a213  add     rsp, 48h
0x14000a217  pop     r15
0x14000a219  pop     r14
0x14000a21b  pop     r13
0x14000a21d  pop     r12
0x14000a21f  pop     rdi
0x14000a220  pop     rsi
0x14000a221  pop     rbx
0x14000a222  pop     rbp
0x14000a223  retn
```
