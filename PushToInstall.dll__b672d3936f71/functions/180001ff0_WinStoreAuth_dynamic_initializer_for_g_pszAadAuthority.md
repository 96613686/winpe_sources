# WinStoreAuth::_dynamic_initializer_for__g_pszAadAuthority__

- ea: `0x180001ff0`
- end: `0x180002030`
- name: `WinStoreAuth::_dynamic_initializer_for__g_pszAadAuthority__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001ff0`
- `0x180002b30`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000200e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000200e`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_pszAadAuthority__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(L"organizations", 0xDu, &WinStoreAuth::g_pszAadAuthority, &string);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x18000202FLL);
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_pszAadAuthority__);
}

```

## disassembly

```asm
0x180001ff0  sub     rsp, 28h
0x180001ff4  lea     r9, string; string
0x180001ffb  mov     edx, 0Dh; length
0x180002000  lea     r8, ?g_pszAadAuthority@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x180002007  lea     rcx, sourceString; "organizations"
0x18000200e  call    cs:__imp_WindowsCreateStringReference
0x180002014  test    eax, eax
0x180002016  js      short loc_180002028
0x180002018  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_pszAadAuthority__
0x18000201f  add     rsp, 28h
0x180002023  jmp     atexit
0x180002028  mov     ecx, eax; this
0x18000202a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
