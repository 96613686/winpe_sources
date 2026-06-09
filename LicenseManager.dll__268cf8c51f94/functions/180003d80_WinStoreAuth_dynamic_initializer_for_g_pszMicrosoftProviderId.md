# WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__

- ea: `0x180003d80`
- end: `0x180003dcb`
- name: `WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003d80`
- `0x1800762e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003db4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003db4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d9e`

## string_xrefs

- `0x180003d97`: `https://login.microsoft.com`

## pseudocode

```c
int WinStoreAuth::_dynamic_initializer_for__g_pszMicrosoftProviderId__()
{
  HRESULT StringReference; // eax

  StringReference = WindowsCreateStringReference(
                      L"https://login.microsoft.com",
                      0x1Bu,
                      &WinStoreAuth::g_pszMicrosoftProviderId,
                      &qword_1800F2B88);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  return atexit((void (__cdecl *)())WinStoreAuth::_dynamic_atexit_destructor_for__g_pszMicrosoftProviderId__);
}

```

## disassembly

```asm
0x180003d80  sub     rsp, 28h
0x180003d84  lea     r9, qword_1800F2B88; string
0x180003d8b  mov     edx, 1Bh; length
0x180003d90  lea     r8, ?g_pszMicrosoftProviderId@WinStoreAuth@@3VHStringReference@Wrappers@WRL@Microsoft@@A; hstringHeader
0x180003d97  lea     rcx, aHttpsLoginMicr; "https://login.microsoft.com"
0x180003d9e  call    cs:__imp_WindowsCreateStringReference
0x180003da4  test    eax, eax
0x180003da6  jns     short loc_180003DBB
0x180003da8  xor     r9d, r9d; lpArguments
0x180003dab  xor     r8d, r8d; nNumberOfArguments
0x180003dae  mov     ecx, eax; dwExceptionCode
0x180003db0  lea     edx, [r9+1]; dwExceptionFlags
0x180003db4  call    cs:__imp_RaiseException
0x180003dba  int     3; Trap to Debugger
0x180003dbb  lea     rcx, WinStoreAuth___dynamic_atexit_destructor_for__g_pszMicrosoftProviderId__
0x180003dc2  add     rsp, 28h
0x180003dc6  jmp     atexit
```
