# _dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_PackageFamily_HString__

- ea: `0x1800014d0`
- end: `0x180001510`
- name: `_dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_PackageFamily_HString__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800014d0`
- `0x180001d10`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800014ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800014ee`

## pseudocode

```c
int dynamic_initializer_for__RuntimeClass_Windows_Internal_StateRepository_PackageFamily_HString__()
{
  HRESULT StringReference; // eax
  int v1; // edx
  unsigned int v2; // r8d

  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.PackageFamily",
                      0x2Eu,
                      &stru_18001A730,
                      &qword_18001A748);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v1, v2);
    JUMPOUT(0x18000150FLL);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_PackageFamily_HString__);
}

```

## disassembly

```asm
0x1800014d0  sub     rsp, 28h
0x1800014d4  lea     r9, qword_18001A748; string
0x1800014db  mov     edx, 2Eh ; '.'; length
0x1800014e0  lea     r8, stru_18001A730; hstringHeader
0x1800014e7  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800014ee  call    cs:__imp_WindowsCreateStringReference
0x1800014f4  test    eax, eax
0x1800014f6  js      short loc_180001508
0x1800014f8  lea     rcx, _dynamic_atexit_destructor_for__RuntimeClass_Windows_Internal_StateRepository_PackageFamily_HString__
0x1800014ff  add     rsp, 28h
0x180001503  jmp     atexit
0x180001508  mov     ecx, eax; this
0x18000150a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
