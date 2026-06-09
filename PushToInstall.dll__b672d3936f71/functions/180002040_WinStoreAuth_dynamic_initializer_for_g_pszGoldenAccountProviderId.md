# WinStoreAuth::_dynamic_initializer_for__g_pszGoldenAccountProviderId__

- ea: `0x180002040`
- end: `0x180002080`
- name: `WinStoreAuth::_dynamic_initializer_for__g_pszGoldenAccountProviderId__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002040`
- `0x180002b30`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000205e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000205e`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_pszGoldenAccountProviderId__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(
                      L"https://login.windows.local",
                      0x1Bu,
                      &WinStoreAuth::g_pszGoldenAccountProviderId,
                      &qword_180066588);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x18000207FLL);
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_pszGoldenAccountProviderId__);
}

```

## disassembly

```asm
0x180002040  sub     rsp, 28h
0x180002044  lea     r9, qword_180066588; string
0x18000204b  mov     edx, 1Bh; length
0x180002050  lea     r8, ?g_pszGoldenAccountProviderId@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x180002057  lea     rcx, aHttpsLoginWind_0; "https://login.windows.local"
0x18000205e  call    cs:__imp_WindowsCreateStringReference
0x180002064  test    eax, eax
0x180002066  js      short loc_180002078
0x180002068  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_pszGoldenAccountProviderId__
0x18000206f  add     rsp, 28h
0x180002073  jmp     atexit
0x180002078  mov     ecx, eax; this
0x18000207a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
