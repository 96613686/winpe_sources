# CopyEnterpriseId

- ea: `0x1400043b0`
- end: `0x140004407`
- name: `CopyEnterpriseId`
- size: `87`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString, void *, PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a70`
- `0x14000540c`

## callees

- `0x140006f40`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400043ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400043ee`

## pseudocode

```c
__int64 __fastcall CopyEnterpriseId(PUNICODE_STRING DestinationString, void *a2, PCUNICODE_STRING SourceString)
{
  unsigned int v5; // edi

  v5 = (unsigned __int16)(SourceString->Length + 2);
  memset(a2, 0, (unsigned __int16)(SourceString->Length + 2));
  DestinationString->MaximumLength = v5;
  DestinationString->Length = 0;
  DestinationString->Buffer = (PWSTR)a2;
  RtlCopyUnicodeString(DestinationString, SourceString);
  return v5;
}

```

## disassembly

```asm
0x1400043b0  push    rbx
0x1400043b2  push    rsi
0x1400043b3  push    rdi
0x1400043b4  push    r14
0x1400043b6  sub     rsp, 28h
0x1400043ba  movzx   eax, word ptr [r8]
0x1400043be  mov     rbx, rdx
0x1400043c1  add     ax, 2
0x1400043c5  mov     r14, r8
0x1400043c8  movzx   edi, ax
0x1400043cb  mov     rsi, rcx
0x1400043ce  mov     r8d, edi; Size
0x1400043d1  xor     edx, edx; Val
0x1400043d3  mov     rcx, rbx; void *
0x1400043d6  call    memset
0x1400043db  xor     eax, eax
0x1400043dd  mov     [rsi+2], di
0x1400043e1  mov     rdx, r14; SourceString
0x1400043e4  mov     [rsi], ax
0x1400043e7  mov     rcx, rsi; DestinationString
0x1400043ea  mov     [rsi+8], rbx
0x1400043ee  call    cs:__imp_RtlCopyUnicodeString
0x1400043f5  nop     dword ptr [rax+rax+00h]
0x1400043fa  mov     eax, edi
0x1400043fc  add     rsp, 28h
0x140004400  pop     r14
0x140004402  pop     rdi
0x140004403  pop     rsi
0x140004404  pop     rbx
0x140004405  retn
```
