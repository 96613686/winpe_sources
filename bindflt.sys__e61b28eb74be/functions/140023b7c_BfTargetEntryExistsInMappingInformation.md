# BfTargetEntryExistsInMappingInformation

- ea: `0x140023b7c`
- end: `0x140023bd1`
- name: `BfTargetEntryExistsInMappingInformation`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019c44`

## callees

- `0x140023b7c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140023bac`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140023bac`

## pseudocode

```c
char __fastcall BfTargetEntryExistsInMappingInformation(__int64 a1, __int64 a2)
{
  __int64 *v2; // rsi
  __int64 *v4; // rbx
  char v5; // di

  v2 = (__int64 *)(a2 + 64);
  v4 = *(__int64 **)(a2 + 64);
  v5 = 0;
  while ( v4 != v2 )
  {
    if ( v4[2] == *(_QWORD *)(a1 + 16)
      && !RtlCompareUnicodeString((PCUNICODE_STRING)(v4 + 5), (PCUNICODE_STRING)(a1 + 40), 1u) )
    {
      return 1;
    }
    v4 = (__int64 *)*v4;
  }
  return v5;
}

```

## disassembly

```asm
0x140023b7c  push    rbx
0x140023b7e  push    rbp
0x140023b7f  push    rsi
0x140023b80  push    rdi
0x140023b81  sub     rsp, 28h
0x140023b85  lea     rsi, [rdx+40h]
0x140023b89  mov     rbp, rcx
0x140023b8c  mov     rbx, [rsi]
0x140023b8f  xor     dil, dil
0x140023b92  cmp     rbx, rsi
0x140023b95  jz      short loc_140023BC4
0x140023b97  mov     rax, [rbp+10h]
0x140023b9b  cmp     [rbx+10h], rax
0x140023b9f  jnz     short loc_140023BBC
0x140023ba1  lea     rdx, [rbp+28h]; String2
0x140023ba5  mov     r8b, 1; CaseInSensitive
0x140023ba8  lea     rcx, [rbx+28h]; String1
0x140023bac  call    cs:__imp_RtlCompareUnicodeString
0x140023bb3  nop     dword ptr [rax+rax+00h]
0x140023bb8  test    eax, eax
0x140023bba  jz      short loc_140023BC1
0x140023bbc  mov     rbx, [rbx]
0x140023bbf  jmp     short loc_140023B92
0x140023bc1  mov     dil, 1
0x140023bc4  mov     al, dil
0x140023bc7  add     rsp, 28h
0x140023bcb  pop     rdi
0x140023bcc  pop     rsi
0x140023bcd  pop     rbp
0x140023bce  pop     rbx
0x140023bcf  retn
```
