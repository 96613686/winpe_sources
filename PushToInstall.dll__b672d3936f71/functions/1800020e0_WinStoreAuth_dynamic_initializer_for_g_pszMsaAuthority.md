# WinStoreAuth::_dynamic_initializer_for__g_pszMsaAuthority__

- ea: `0x1800020e0`
- end: `0x180002120`
- name: `WinStoreAuth::_dynamic_initializer_for__g_pszMsaAuthority__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020e0`
- `0x180002b30`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800020fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800020fe`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_pszMsaAuthority__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(L"consumers", 9u, &WinStoreAuth::g_pszMsaAuthority, &qword_1800665A8);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x18000211FLL);
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_pszMsaAuthority__);
}

```

## disassembly

```asm
0x1800020e0  sub     rsp, 28h
0x1800020e4  lea     r9, qword_1800665A8; string
0x1800020eb  mov     edx, 9; length
0x1800020f0  lea     r8, ?g_pszMsaAuthority@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x1800020f7  lea     rcx, aConsumers; "consumers"
0x1800020fe  call    cs:__imp_WindowsCreateStringReference
0x180002104  test    eax, eax
0x180002106  js      short loc_180002118
0x180002108  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_pszMsaAuthority__
0x18000210f  add     rsp, 28h
0x180002113  jmp     atexit
0x180002118  mov     ecx, eax; this
0x18000211a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
