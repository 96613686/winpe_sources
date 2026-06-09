# VfsIsExcludedExtension

- ea: `0x140007bac`
- end: `0x140007c76`
- name: `VfsIsExcludedExtension`
- size: `202`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400034a0`
- `0x14000bbf4`

## callees

- `0x140007bac`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140007bf2`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140007bf2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007c2b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007c2b`

## pseudocode

```c
char __fastcall VfsIsExcludedExtension(PCUNICODE_STRING SourceString)
{
  int v1; // ebx
  int v2; // edi
  int v3; // esi
  LONG v4; // eax
  int v5; // ecx
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  __int64 v8; // [rsp+30h] [rbp-58h] BYREF

  *(_QWORD *)&String1.Length = 0x400000;
  String1.Buffer = (wchar_t *)&v8;
  if ( RtlUpcaseUnicodeString(&String1, SourceString, 0) < 0 )
    return 0;
  v1 = 0;
  v2 = 3;
  while ( 1 )
  {
    v3 = (v2 + v1) / 2;
    v4 = RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)&DefaultExcludedExtensions[2 * v3], 0);
    if ( !v4 )
      break;
    v5 = v3 - 1;
    if ( v4 >= 0 )
      v5 = v2;
    v2 = v5;
    if ( v4 >= 0 )
      v1 = v3 + 1;
    if ( v5 < v1 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140007bac  mov     r11, rsp
0x140007baf  mov     [r11+10h], rbx
0x140007bb3  mov     [r11+18h], rsi
0x140007bb7  push    rdi
0x140007bb8  sub     rsp, 80h
0x140007bbf  mov     rax, cs:__security_cookie
0x140007bc6  xor     rax, rsp
0x140007bc9  mov     [rsp+88h+var_18], rax
0x140007bce  xorps   xmm0, xmm0
0x140007bd1  mov     eax, 40h ; '@'
0x140007bd6  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x140007bdb  mov     [rsp+88h+String1.MaximumLength], ax
0x140007be0  mov     rdx, rcx; SourceString
0x140007be3  lea     rax, [r11-58h]
0x140007be7  xor     r8d, r8d; AllocateDestinationString
0x140007bea  lea     rcx, [r11-68h]; DestinationString
0x140007bee  mov     [r11-60h], rax
0x140007bf2  call    cs:__imp_RtlUpcaseUnicodeString
0x140007bf9  nop     dword ptr [rax+rax+00h]
0x140007bfe  test    eax, eax
0x140007c00  js      short loc_140007C4D
0x140007c02  xor     ebx, ebx
0x140007c04  lea     edi, [rbx+3]
0x140007c07  lea     eax, [rdi+rbx]
0x140007c0a  xor     r8d, r8d; CaseInSensitive
0x140007c0d  cdq
0x140007c0e  lea     rcx, [rsp+88h+String1]; String1
0x140007c13  sub     eax, edx
0x140007c15  sar     eax, 1
0x140007c17  movsxd  rsi, eax
0x140007c1a  lea     rax, DefaultExcludedExtensions
0x140007c21  mov     rdx, rsi
0x140007c24  shl     rdx, 4
0x140007c28  add     rdx, rax; String2
0x140007c2b  call    cs:__imp_RtlCompareUnicodeString
0x140007c32  nop     dword ptr [rax+rax+00h]
0x140007c37  test    eax, eax
0x140007c39  jz      short loc_140007C72
0x140007c3b  lea     ecx, [rsi-1]
0x140007c3e  cmovns  ecx, edi
0x140007c41  mov     edi, ecx
0x140007c43  lea     ecx, [rsi+1]
0x140007c46  cmovns  ebx, ecx
0x140007c49  cmp     edi, ebx
0x140007c4b  jge     short loc_140007C07
0x140007c4d  xor     al, al
0x140007c4f  mov     rcx, [rsp+88h+var_18]
0x140007c54  xor     rcx, rsp; StackCookie
0x140007c57  call    __security_check_cookie
0x140007c5c  lea     r11, [rsp+88h+var_8]
0x140007c64  mov     rbx, [r11+18h]
0x140007c68  mov     rsi, [r11+20h]
0x140007c6c  mov     rsp, r11
0x140007c6f  pop     rdi
0x140007c70  retn
0x140007c72  mov     al, 1
0x140007c74  jmp     short loc_140007C4F
```
