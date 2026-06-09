# BfpRBComparePathNodes

- ea: `0x140019b40`
- end: `0x140019bdc`
- name: `BfpRBComparePathNodes`
- size: `156`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011264`
- `0x140017f00`
- `0x1400194b0`
- `0x140019c44`
- `0x14001b280`

## callees

- `0x140019b40`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140019b63`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019b82`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019b63`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019b82`

## pseudocode

```c
__int64 __fastcall BfpRBComparePathNodes(__int64 a1, __int64 a2)
{
  const UNICODE_STRING *v2; // rdi
  const UNICODE_STRING *v3; // rsi
  char v4; // bl
  LONG v5; // eax
  LONG v6; // ecx

  v2 = *(const UNICODE_STRING **)a1;
  v3 = (const UNICODE_STRING *)(a2 + 24);
  v4 = *(_BYTE *)(a1 + 8);
  v5 = RtlCompareUnicodeString(*(PCUNICODE_STRING *)a1, (PCUNICODE_STRING)(a2 + 24), 1u);
  if ( v5 < 0 )
    return 0xFFFFFFFFLL;
  if ( v5 <= 0 )
  {
    if ( v4 )
      return 0;
    v6 = RtlCompareUnicodeString(v2, v3, 0);
    if ( v6 >= 0 )
      return v6 > 0;
    return 0xFFFFFFFFLL;
  }
  return 1;
}

```

## disassembly

```asm
0x140019b40  mov     [rsp+arg_0], rbx
0x140019b45  mov     [rsp+arg_8], rsi
0x140019b4a  push    rdi
0x140019b4b  sub     rsp, 20h
0x140019b4f  mov     rdi, [rcx]
0x140019b52  lea     rsi, [rdx+18h]
0x140019b56  movzx   ebx, byte ptr [rcx+8]
0x140019b5a  mov     rdx, rsi; String2
0x140019b5d  mov     rcx, rdi; String1
0x140019b60  mov     r8b, 1; CaseInSensitive
0x140019b63  call    cs:__imp_RtlCompareUnicodeString
0x140019b6a  nop     dword ptr [rax+rax+00h]
0x140019b6f  test    eax, eax
0x140019b71  js      short loc_140019BBF
0x140019b73  jg      short loc_140019BC6
0x140019b75  test    bl, bl
0x140019b77  jnz     short loc_140019BAC
0x140019b79  xor     r8d, r8d; CaseInSensitive
0x140019b7c  mov     rdx, rsi; String2
0x140019b7f  mov     rcx, rdi; String1
0x140019b82  call    cs:__imp_RtlCompareUnicodeString
0x140019b89  nop     dword ptr [rax+rax+00h]
0x140019b8e  mov     ecx, eax
0x140019b90  test    eax, eax
0x140019b92  js      short loc_140019BBF
0x140019b94  xor     eax, eax
0x140019b96  test    ecx, ecx
0x140019b98  setnle  al
0x140019b9b  mov     rbx, [rsp+28h+arg_0]
0x140019ba0  mov     rsi, [rsp+28h+arg_8]
0x140019ba5  add     rsp, 20h
0x140019ba9  pop     rdi
0x140019baa  retn
0x140019bac  xor     eax, eax
0x140019bae  mov     rbx, [rsp+28h+arg_0]
0x140019bb3  mov     rsi, [rsp+28h+arg_8]
0x140019bb8  add     rsp, 20h
0x140019bbc  pop     rdi
0x140019bbd  retn
0x140019bbf  mov     eax, 0FFFFFFFFh
0x140019bc4  jmp     short loc_140019BAE
0x140019bc6  mov     rbx, [rsp+28h+arg_0]
0x140019bcb  mov     eax, 1
0x140019bd0  mov     rsi, [rsp+28h+arg_8]
0x140019bd5  add     rsp, 20h
0x140019bd9  pop     rdi
0x140019bda  retn
```
