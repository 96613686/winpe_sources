# WinStoreAuth::_dynamic_initializer_for__g_xuidProperty__

- ea: `0x1800021b0`
- end: `0x1800021f0`
- name: `WinStoreAuth::_dynamic_initializer_for__g_xuidProperty__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800021b0`
- `0x180002b30`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800021ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800021ce`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_xuidProperty__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(L"XboxUserId", 0xAu, &WinStoreAuth::g_xuidProperty, &qword_180066548);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x1800021EFLL);
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_xuidProperty__);
}

```

## disassembly

```asm
0x1800021b0  sub     rsp, 28h
0x1800021b4  lea     r9, qword_180066548; string
0x1800021bb  mov     edx, 0Ah; length
0x1800021c0  lea     r8, ?g_xuidProperty@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x1800021c7  lea     rcx, aXboxuserid; "XboxUserId"
0x1800021ce  call    cs:__imp_WindowsCreateStringReference
0x1800021d4  test    eax, eax
0x1800021d6  js      short loc_1800021E8
0x1800021d8  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_xuidProperty__
0x1800021df  add     rsp, 28h
0x1800021e3  jmp     atexit
0x1800021e8  mov     ecx, eax; this
0x1800021ea  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
