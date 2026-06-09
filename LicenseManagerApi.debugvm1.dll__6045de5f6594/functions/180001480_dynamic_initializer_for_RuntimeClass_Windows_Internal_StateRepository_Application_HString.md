# _dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Application_HString__

- ea: `0x180001480`
- end: `0x1800014c0`
- name: `_dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Application_HString__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001480`
- `0x180001d10`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000149e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000149e`

## pseudocode

```c
int dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Application_HString__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.Application",
                      0x2Cu,
                      &hstringHeader,
                      &string);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x1800014BFLL);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_Application_HString__);
}

```

## disassembly

```asm
0x180001480  sub     rsp, 28h
0x180001484  lea     r9, string; string
0x18000148b  mov     edx, 2Ch ; ','; length
0x180001490  lea     r8, hstringHeader; hstringHeader
0x180001497  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18000149e  call    cs:__imp_WindowsCreateStringReference
0x1800014a4  test    eax, eax
0x1800014a6  js      short loc_1800014B8
0x1800014a8  lea     rcx, _dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_Application_HString__
0x1800014af  add     rsp, 28h
0x1800014b3  jmp     atexit
0x1800014b8  mov     ecx, eax; this
0x1800014ba  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
