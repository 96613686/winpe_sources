# _dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Package_HString__

- ea: `0x180001520`
- end: `0x180001560`
- name: `_dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Package_HString__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001520`
- `0x180001d10`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000153e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000153e`

## pseudocode

```c
int dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_Package_HString__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.Package",
                      0x28u,
                      &stru_18001A710,
                      &qword_18001A728);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x18000155FLL);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_Package_HString__);
}

```

## disassembly

```asm
0x180001520  sub     rsp, 28h
0x180001524  lea     r9, qword_18001A728; string
0x18000152b  mov     edx, 28h ; '('; length
0x180001530  lea     r8, stru_18001A710; hstringHeader
0x180001537  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18000153e  call    cs:__imp_WindowsCreateStringReference
0x180001544  test    eax, eax
0x180001546  js      short loc_180001558
0x180001548  lea     rcx, _dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_Package_HString__
0x18000154f  add     rsp, 28h
0x180001553  jmp     atexit
0x180001558  mov     ecx, eax; this
0x18000155a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
