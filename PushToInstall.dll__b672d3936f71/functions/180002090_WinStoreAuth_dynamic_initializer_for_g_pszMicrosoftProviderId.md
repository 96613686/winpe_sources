# WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__

- ea: `0x180002090`
- end: `0x1800020d0`
- name: `WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002090`
- `0x180002b30`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800020ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800020ae`

## string_xrefs

- `0x1800020a7`: `https://login.microsoft.com`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(
                      L"https://login.microsoft.com",
                      0x1Bu,
                      &WinStoreAuth::g_pszMicrosoftProviderId,
                      &string2);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x1800020CFLL);
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_pszMicrosoftProviderId__);
}

```

## disassembly

```asm
0x180002090  sub     rsp, 28h
0x180002094  lea     r9, string2; string
0x18000209b  mov     edx, 1Bh; length
0x1800020a0  lea     r8, ?g_pszMicrosoftProviderId@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x1800020a7  lea     rcx, aHttpsLoginMicr; "https://login.microsoft.com"
0x1800020ae  call    cs:__imp_WindowsCreateStringReference
0x1800020b4  test    eax, eax
0x1800020b6  js      short loc_1800020C8
0x1800020b8  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_pszMicrosoftProviderId__
0x1800020bf  add     rsp, 28h
0x1800020c3  jmp     atexit
0x1800020c8  mov     ecx, eax; this
0x1800020ca  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
