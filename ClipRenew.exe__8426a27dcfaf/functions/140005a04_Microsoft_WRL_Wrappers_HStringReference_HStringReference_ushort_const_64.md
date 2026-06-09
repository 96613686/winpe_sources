# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const (&)[64])

- ea: `0x140005a04`
- end: `0x140005a42`
- name: `??$?0$0EA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0EA@$$CBG@Z`
- size: `62`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *hstringHeader, const unsigned __int16 (*)[64])`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140005a04`
- `0x14000ff44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005a27`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const unsigned __int16 (*a2)[64])
{
  HRESULT StringReference; // eax
  int v4; // edx
  unsigned int v5; // r8d

  hstringHeader[1].Reserved.Reserved1 = 0;
  StringReference = WindowsCreateStringReference(
                      L"[UBS] Subscription License failed to verify subscription Status",
                      0x3Fu,
                      hstringHeader,
                      (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v4, v5);
    JUMPOUT(0x140005A41LL);
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x140005a04  push    rbx
0x140005a06  sub     rsp, 20h
0x140005a0a  lea     r9, [rcx+18h]; string
0x140005a0e  mov     rbx, rcx
0x140005a11  mov     r8, rcx; hstringHeader
0x140005a14  mov     qword ptr [r9], 0
0x140005a1b  lea     rcx, aUbsSubscriptio_1; "[UBS] Subscription License failed to ve"...
0x140005a22  mov     edx, 3Fh ; '?'; length
0x140005a27  call    cs:__imp_WindowsCreateStringReference
0x140005a2d  test    eax, eax
0x140005a2f  js      short loc_140005A3A
0x140005a31  mov     rax, rbx
0x140005a34  add     rsp, 20h
0x140005a38  pop     rbx
0x140005a39  retn
0x140005a3a  mov     ecx, eax; this
0x140005a3c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
