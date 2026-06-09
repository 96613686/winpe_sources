# VfsCreateInitialNameForNormalize

- ea: `0x1400109f4`
- end: `0x140010aa1`
- name: `VfsCreateInitialNameForNormalize`
- size: `173`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140010cb4`

## callees

- `0x1400109f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140010a57`
- `ntoskrnl!ExAllocatePool2` at `0x140010a57`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010a7b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010a7b`

## pseudocode

```c
__int64 __fastcall VfsCreateInitialNameForNormalize(
        PCUNICODE_STRING SourceString,
        unsigned __int16 *a2,
        struct _UNICODE_STRING *a3)
{
  unsigned __int64 Length; // r9
  unsigned int v6; // ebx
  unsigned int v8; // ebx
  __int64 Pool2; // rax

  Length = SourceString->Length;
  v6 = Length + *a2 + 2;
  if ( SourceString->Buffer[(Length >> 1) - 1] != 92 )
    v6 = Length + *a2;
  if ( v6 > 0xFFFF )
    return 3221225734LL;
  v8 = v6 + 512;
  if ( v8 > 0xFFFF )
    LOWORD(v8) = -2;
  Pool2 = ExAllocatePool2(256, (unsigned __int16)v8, 1951614550);
  a3->Buffer = (wchar_t *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  a3->MaximumLength = v8;
  a3->Length = 0;
  RtlCopyUnicodeString(a3, SourceString);
  return 0;
}

```

## disassembly

```asm
0x1400109f4  mov     [rsp+arg_0], rbx
0x1400109f9  mov     [rsp+arg_8], rsi
0x1400109fe  push    rdi
0x1400109ff  sub     rsp, 20h
0x140010a03  movzx   r9d, word ptr [rcx]
0x140010a07  mov     rdi, r8
0x140010a0a  mov     rax, [rcx+8]
0x140010a0e  mov     rsi, rcx
0x140010a11  movzx   r10d, word ptr [rdx]
0x140010a15  add     r10d, r9d
0x140010a18  shr     r9, 1
0x140010a1b  cmp     word ptr [rax+r9*2-2], 5Ch ; '\'
0x140010a22  lea     ebx, [r10+2]
0x140010a26  mov     eax, 0FFFFh
0x140010a2b  cmovnz  ebx, r10d
0x140010a2f  cmp     ebx, eax
0x140010a31  jbe     short loc_140010A3A
0x140010a33  mov     eax, 0C0000106h
0x140010a38  jmp     short loc_140010A90
0x140010a3a  add     ebx, 200h
0x140010a40  cmp     ebx, eax
0x140010a42  jbe     short loc_140010A49
0x140010a44  mov     ebx, 0FFFEh
0x140010a49  movzx   edx, bx
0x140010a4c  mov     ecx, 100h
0x140010a51  mov     r8d, 74534656h
0x140010a57  call    cs:__imp_ExAllocatePool2
0x140010a5e  nop     dword ptr [rax+rax+00h]
0x140010a63  mov     [rdi+8], rax
0x140010a67  test    rax, rax
0x140010a6a  jz      short loc_140010A8B
0x140010a6c  xor     eax, eax
0x140010a6e  mov     [rdi+2], bx
0x140010a72  mov     rdx, rsi; SourceString
0x140010a75  mov     [rdi], ax
0x140010a78  mov     rcx, rdi; DestinationString
0x140010a7b  call    cs:__imp_RtlCopyUnicodeString
0x140010a82  nop     dword ptr [rax+rax+00h]
0x140010a87  xor     eax, eax
0x140010a89  jmp     short loc_140010A90
0x140010a8b  mov     eax, 0C000009Ah
0x140010a90  mov     rbx, [rsp+28h+arg_0]
0x140010a95  mov     rsi, [rsp+28h+arg_8]
0x140010a9a  add     rsp, 20h
0x140010a9e  pop     rdi
0x140010a9f  retn
```
