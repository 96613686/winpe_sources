# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003ac40`
- end: `0x18003ac7d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `61`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003197c`

## callees

- `0x18003ac40`
- `0x18003fe64`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ac5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ac5f`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax
  int v6; // edx
  unsigned int v7; // r8d

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    JUMPOUT(0x18003AC7CLL);
  }
}

```

## disassembly

```asm
0x18003ac40  sub     rsp, 28h
0x18003ac44  mov     eax, r9d
0x18003ac47  mov     r10, rdx
0x18003ac4a  cmp     r9d, r8d
0x18003ac4d  jb      short loc_18003AC53
0x18003ac4f  lea     eax, [r8-1]
0x18003ac53  lea     r9, [rcx+18h]; string
0x18003ac57  mov     r8, rcx; hstringHeader
0x18003ac5a  mov     rcx, r10; sourceString
0x18003ac5d  mov     edx, eax; length
0x18003ac5f  call    cs:__imp_WindowsCreateStringReference
0x18003ac66  nop     dword ptr [rax+rax+00h]
0x18003ac6b  test    eax, eax
0x18003ac6d  js      short loc_18003AC75
0x18003ac6f  add     rsp, 28h
0x18003ac73  retn
0x18003ac75  mov     ecx, eax; this
0x18003ac77  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
