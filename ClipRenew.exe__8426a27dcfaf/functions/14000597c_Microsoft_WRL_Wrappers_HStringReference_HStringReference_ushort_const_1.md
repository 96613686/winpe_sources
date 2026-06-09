# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const (&)[1])

- ea: `0x14000597c`
- end: `0x1400059b7`
- name: `??$?0$00@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY00$$CBG@Z`
- size: `59`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *hstringHeader, const unsigned __int16 (*)[1])`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x14000597c`
- `0x14000ff44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000599c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000599c`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const unsigned __int16 (*a2)[1])
{
  HRESULT StringReference; // eax
  int v4; // edx
  unsigned int v5; // r8d

  hstringHeader[1].Reserved.Reserved1 = 0;
  StringReference = WindowsCreateStringReference(&psz, 0, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v4, v5);
    JUMPOUT(0x1400059B6LL);
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x14000597c  push    rbx
0x14000597e  sub     rsp, 20h
0x140005982  lea     r9, [rcx+18h]; string
0x140005986  mov     rbx, rcx
0x140005989  mov     r8, rcx; hstringHeader
0x14000598c  mov     qword ptr [r9], 0
0x140005993  lea     rcx, psz; sourceString
0x14000599a  xor     edx, edx; length
0x14000599c  call    cs:__imp_WindowsCreateStringReference
0x1400059a2  test    eax, eax
0x1400059a4  js      short loc_1400059AF
0x1400059a6  mov     rax, rbx
0x1400059a9  add     rsp, 20h
0x1400059ad  pop     rbx
0x1400059ae  retn
0x1400059af  mov     ecx, eax; this
0x1400059b1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
