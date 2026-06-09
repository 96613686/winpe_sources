# AipNtPathToDosPath

- ea: `0x1400369f0`
- end: `0x140036ae9`
- name: `AipNtPathToDosPath`
- size: `249`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140031d90`

## callees

- `0x140006c40`
- `0x140032a50`
- `0x1400369f0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140036a0f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140036a3d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140036a0f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140036a3d`

## pseudocode

```c
__int64 __fastcall AipNtPathToDosPath(PCUNICODE_STRING String2, UNICODE_STRING *a2)
{
  const UNICODE_STRING *v3; // rdi
  __int64 *v5; // rbp
  __int16 v6; // ax
  bool v7; // zf
  USHORT v8; // ax
  __int64 result; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // r14

  v3 = &stru_140009020;
  if ( RtlPrefixUnicodeString(&stru_140009020, String2, 1u) )
  {
    v5 = &qword_1400093E0;
    v6 = -12;
  }
  else
  {
    v3 = &stru_140009030;
    if ( !RtlPrefixUnicodeString(&stru_140009030, String2, 1u) )
    {
      result = 0;
      *a2 = *String2;
      return result;
    }
    v5 = &qword_1400093D0;
    v6 = -8;
  }
  v7 = String2->Length + v6 == 0;
  v8 = String2->Length + v6;
  a2->Length = v8;
  a2->MaximumLength = v8;
  if ( v7 )
    return 3221225485LL;
  v10 = (WCHAR *)AiAlloc(v8);
  a2->Buffer = v10;
  v11 = v10;
  if ( !v10 )
    return 3221225495LL;
  memmove(v10, (const void *)v5[1], *(unsigned __int16 *)v5);
  memmove(
    &v11[(unsigned __int64)*(unsigned __int16 *)v5 >> 1],
    &String2->Buffer[(unsigned __int64)v3->Length >> 1],
    String2->Length - (unsigned __int64)v3->Length);
  return 0;
}

```

## disassembly

```asm
0x1400369f0  push    rbx
0x1400369f2  push    rbp
0x1400369f3  push    rsi
0x1400369f4  push    rdi
0x1400369f5  sub     rsp, 28h
0x1400369f9  mov     rsi, rdx
0x1400369fc  lea     rdi, stru_140009020
0x140036a03  mov     rdx, rcx; String2
0x140036a06  mov     rbx, rcx
0x140036a09  mov     rcx, rdi; String1
0x140036a0c  mov     r8b, 1; CaseInSensitive
0x140036a0f  call    cs:__imp_RtlPrefixUnicodeString
0x140036a16  nop     dword ptr [rax+rax+00h]
0x140036a1b  test    al, al
0x140036a1d  jz      short loc_140036A2D
0x140036a1f  lea     rbp, qword_1400093E0
0x140036a26  mov     eax, 0FFF4h
0x140036a2b  jmp     short loc_140036A5D
0x140036a2d  lea     rdi, stru_140009030
0x140036a34  mov     r8b, 1; CaseInSensitive
0x140036a37  mov     rcx, rdi; String1
0x140036a3a  mov     rdx, rbx; String2
0x140036a3d  call    cs:__imp_RtlPrefixUnicodeString
0x140036a44  nop     dword ptr [rax+rax+00h]
0x140036a49  test    al, al
0x140036a4b  jz      loc_140036AD7
0x140036a51  lea     rbp, qword_1400093D0
0x140036a58  mov     eax, 0FFF8h
0x140036a5d  add     ax, [rbx]
0x140036a60  mov     [rsi], ax
0x140036a63  mov     [rsi+2], ax
0x140036a67  jnz     short loc_140036A70
0x140036a69  mov     eax, 0C000000Dh
0x140036a6e  jmp     short loc_140036A93
0x140036a70  movzx   ecx, ax
0x140036a73  mov     [rsp+48h+arg_0], r14
0x140036a78  call    AiAlloc
0x140036a7d  mov     [rsi+8], rax
0x140036a81  mov     r14, rax
0x140036a84  test    rax, rax
0x140036a87  jnz     short loc_140036A9D
0x140036a89  mov     eax, 0C0000017h
0x140036a8e  mov     r14, [rsp+48h+arg_0]
0x140036a93  add     rsp, 28h
0x140036a97  pop     rdi
0x140036a98  pop     rsi
0x140036a99  pop     rbp
0x140036a9a  pop     rbx
0x140036a9b  retn
0x140036a9d  movzx   r8d, word ptr [rbp+0]; Size
0x140036aa2  mov     rcx, r14; void *
0x140036aa5  mov     rdx, [rbp+8]; Src
0x140036aa9  call    memmove
0x140036aae  movzx   edx, word ptr [rdi]
0x140036ab1  mov     rcx, [rbx+8]
0x140036ab5  movzx   r8d, word ptr [rbx]
0x140036ab9  sub     r8, rdx; Size
0x140036abc  shr     rdx, 1
0x140036abf  lea     rdx, [rcx+rdx*2]; Src
0x140036ac3  movzx   ecx, word ptr [rbp+0]
0x140036ac7  shr     rcx, 1
0x140036aca  lea     rcx, [r14+rcx*2]; void *
0x140036ace  call    memmove
0x140036ad3  xor     eax, eax
0x140036ad5  jmp     short loc_140036A8E
0x140036ad7  movups  xmm0, xmmword ptr [rbx]
0x140036ada  xor     eax, eax
0x140036adc  movups  xmmword ptr [rsi], xmm0
0x140036adf  add     rsp, 28h
0x140036ae3  pop     rdi
0x140036ae4  pop     rsi
0x140036ae5  pop     rbp
0x140036ae6  pop     rbx
0x140036ae7  retn
```
