# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const (&)[55])

- ea: `0x1400059c0`
- end: `0x1400059fe`
- name: `??$?0$0DH@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0DH@$$CBG@Z`
- size: `62`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *hstringHeader, const unsigned __int16 (*)[55])`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x1400059c0`
- `0x14000ff44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400059e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400059e3`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        const unsigned __int16 (*a2)[55])
{
  HRESULT StringReference; // eax
  int v4; // edx
  unsigned int v5; // r8d

  hstringHeader[1].Reserved.Reserved1 = 0;
  StringReference = WindowsCreateStringReference(
                      L"[UBS] Subscription License faliled to acquire license.",
                      0x36u,
                      hstringHeader,
                      (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v4, v5);
    JUMPOUT(0x1400059FDLL);
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x1400059c0  push    rbx
0x1400059c2  sub     rsp, 20h
0x1400059c6  lea     r9, [rcx+18h]; string
0x1400059ca  mov     rbx, rcx
0x1400059cd  mov     r8, rcx; hstringHeader
0x1400059d0  mov     qword ptr [r9], 0
0x1400059d7  lea     rcx, aUbsSubscriptio_3; "[UBS] Subscription License faliled to a"...
0x1400059de  mov     edx, 36h ; '6'; length
0x1400059e3  call    cs:__imp_WindowsCreateStringReference
0x1400059e9  test    eax, eax
0x1400059eb  js      short loc_1400059F6
0x1400059ed  mov     rax, rbx
0x1400059f0  add     rsp, 20h
0x1400059f4  pop     rbx
0x1400059f5  retn
0x1400059f6  mov     ecx, eax; this
0x1400059f8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
