# FileProvCbHideStream

- ea: `0x14003b470`
- end: `0x14003b49e`
- name: `FileProvCbHideStream`
- size: `46`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, BOOLEAN)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14003b47e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003b47e`

## pseudocode

```c
__int64 __fastcall FileProvCbHideStream(__int64 a1, const UNICODE_STRING *a2, BOOLEAN a3)
{
  LONG v3; // eax
  unsigned int v4; // ecx

  v3 = RtlCompareUnicodeString(a2, &CompressedStream, a3);
  v4 = 0;
  if ( !v3 )
    return (unsigned int)-1073741275;
  return v4;
}

```

## disassembly

```asm
0x14003b470  sub     rsp, 28h
0x14003b474  mov     rcx, rdx; String1
0x14003b477  lea     rdx, CompressedStream; String2
0x14003b47e  call    cs:__imp_RtlCompareUnicodeString
0x14003b485  nop     dword ptr [rax+rax+00h]
0x14003b48a  xor     ecx, ecx
0x14003b48c  mov     edx, 0C0000225h
0x14003b491  test    eax, eax
0x14003b493  cmovz   ecx, edx
0x14003b496  mov     eax, ecx
0x14003b498  add     rsp, 28h
0x14003b49c  retn
```
