# IsContextAllowed

- ea: `0x140004e28`
- end: `0x140004e86`
- name: `IsContextAllowed`
- size: `94`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004e8c`

## callees

- `0x140004e28`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140004e63`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140004e63`

## pseudocode

```c
void __fastcall IsContextAllowed(PCUNICODE_STRING String1, char a2, unsigned int a3, __int64 a4, _BYTE *a5)
{
  unsigned int i; // ebx

  *a5 = 0;
  if ( (a2 & 1) != 0 )
  {
LABEL_7:
    *a5 = 1;
  }
  else if ( a4 )
  {
    for ( i = 0; i < a3; ++i )
    {
      if ( !RtlCompareUnicodeString(String1, (PCUNICODE_STRING)(a4 + 16LL * i), 0) )
        goto LABEL_7;
    }
  }
}

```

## disassembly

```asm
0x140004e28  push    rbx
0x140004e2a  push    rbp
0x140004e2b  push    rsi
0x140004e2c  push    rdi
0x140004e2d  push    r14
0x140004e2f  sub     rsp, 20h
0x140004e33  mov     rdi, [rsp+48h+arg_20]
0x140004e38  mov     rsi, r9
0x140004e3b  mov     ebp, r8d
0x140004e3e  mov     r14, rcx
0x140004e41  mov     byte ptr [rdi], 0
0x140004e44  test    dl, 1
0x140004e47  jnz     short loc_140004E77
0x140004e49  test    r9, r9
0x140004e4c  jz      short loc_140004E7A
0x140004e4e  xor     ebx, ebx
0x140004e50  cmp     ebx, ebp
0x140004e52  jnb     short loc_140004E7A
0x140004e54  mov     edx, ebx
0x140004e56  xor     r8d, r8d; CaseInSensitive
0x140004e59  shl     rdx, 4
0x140004e5d  mov     rcx, r14; String1
0x140004e60  add     rdx, rsi; String2
0x140004e63  call    cs:__imp_RtlCompareUnicodeString
0x140004e6a  nop     dword ptr [rax+rax+00h]
0x140004e6f  test    eax, eax
0x140004e71  jz      short loc_140004E77
0x140004e73  inc     ebx
0x140004e75  jmp     short loc_140004E50
0x140004e77  mov     byte ptr [rdi], 1
0x140004e7a  add     rsp, 20h
0x140004e7e  pop     r14
0x140004e80  pop     rdi
0x140004e81  pop     rsi
0x140004e82  pop     rbp
0x140004e83  pop     rbx
0x140004e84  retn
```
