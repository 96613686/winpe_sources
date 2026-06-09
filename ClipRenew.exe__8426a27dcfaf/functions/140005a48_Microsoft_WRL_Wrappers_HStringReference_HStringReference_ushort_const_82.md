# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const (&)[82])

- ea: `0x140005a48`
- end: `0x140005a86`
- name: `??$?0$0FC@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0FC@$$CBG@Z`
- size: `62`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *hstringHeader, const unsigned __int16 (*)[82])`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140005a48`
- `0x14000ff44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005a6b`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const unsigned __int16 (*a2)[82])
{
  HRESULT StringReference; // eax
  int v4; // edx
  unsigned int v5; // r8d

  hstringHeader[1].Reserved.Reserved1 = 0;
  StringReference = WindowsCreateStringReference(
                      L"[UBS] Subscription License refresh is not needed(based on last licensing status).",
                      0x51u,
                      hstringHeader,
                      (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v4, v5);
    JUMPOUT(0x140005A85LL);
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x140005a48  push    rbx
0x140005a4a  sub     rsp, 20h
0x140005a4e  lea     r9, [rcx+18h]; string
0x140005a52  mov     rbx, rcx
0x140005a55  mov     r8, rcx; hstringHeader
0x140005a58  mov     qword ptr [r9], 0
0x140005a5f  lea     rcx, aUbsSubscriptio_0; "[UBS] Subscription License refresh is n"...
0x140005a66  mov     edx, 51h ; 'Q'; length
0x140005a6b  call    cs:__imp_WindowsCreateStringReference
0x140005a71  test    eax, eax
0x140005a73  js      short loc_140005A7E
0x140005a75  mov     rax, rbx
0x140005a78  add     rsp, 20h
0x140005a7c  pop     rbx
0x140005a7d  retn
0x140005a7e  mov     ecx, eax; this
0x140005a80  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
