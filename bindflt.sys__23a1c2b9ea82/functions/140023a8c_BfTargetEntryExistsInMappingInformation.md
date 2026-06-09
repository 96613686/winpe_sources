# BfTargetEntryExistsInMappingInformation

- ea: `0x140023a8c`
- end: `0x140023ae1`
- name: `BfTargetEntryExistsInMappingInformation`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019c44`

## callees

- `0x140023a8c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140023abc`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140023abc`

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
0x140023a8c  push    rbx
0x140023a8e  push    rbp
0x140023a8f  push    rsi
0x140023a90  push    rdi
0x140023a91  sub     rsp, 28h
0x140023a95  lea     rsi, [rdx+40h]
0x140023a99  mov     rbp, rcx
0x140023a9c  mov     rbx, [rsi]
0x140023a9f  xor     dil, dil
0x140023aa2  cmp     rbx, rsi
0x140023aa5  jz      short loc_140023AD4
0x140023aa7  mov     rax, [rbp+10h]
0x140023aab  cmp     [rbx+10h], rax
0x140023aaf  jnz     short loc_140023ACC
0x140023ab1  lea     rdx, [rbp+28h]; String2
0x140023ab5  mov     r8b, 1; CaseInSensitive
0x140023ab8  lea     rcx, [rbx+28h]; String1
0x140023abc  call    cs:__imp_RtlCompareUnicodeString
0x140023ac3  nop     dword ptr [rax+rax+00h]
0x140023ac8  test    eax, eax
0x140023aca  jz      short loc_140023AD1
0x140023acc  mov     rbx, [rbx]
0x140023acf  jmp     short loc_140023AA2
0x140023ad1  mov     dil, 1
0x140023ad4  mov     al, dil
0x140023ad7  add     rsp, 28h
0x140023adb  pop     rdi
0x140023adc  pop     rsi
0x140023add  pop     rbp
0x140023ade  pop     rbx
0x140023adf  retn
```
