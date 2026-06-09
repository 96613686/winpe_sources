# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800203d8`
- end: `0x18002041b`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010afc`
- `0x180013b0c`
- `0x180017a08`
- `0x18001835c`
- `0x180025910`
- `0x1800277ac`
- `0x180027aa0`
- `0x180027c30`
- `0x180029660`
- `0x1800399b8`
- `0x18005a674`
- `0x180062dbc`
- `0x180065230`
- `0x1800658e0`
- `0x180066670`
- `0x180069490`
- `0x180070700`

## callees

- `0x1800203d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020414`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800203f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800203f3`

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

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x18002041ALL);
  }
}

```

## disassembly

```asm
0x1800203d8  sub     rsp, 28h
0x1800203dc  mov     eax, r9d
0x1800203df  mov     r10, rdx
0x1800203e2  cmp     r9d, r8d
0x1800203e5  jnb     short loc_180020402
0x1800203e7  lea     r9, [rcx+18h]; string
0x1800203eb  mov     r8, rcx; hstringHeader
0x1800203ee  mov     rcx, r10; sourceString
0x1800203f1  mov     edx, eax; length
0x1800203f3  call    cs:__imp_WindowsCreateStringReference
0x1800203f9  test    eax, eax
0x1800203fb  js      short loc_180020408
0x1800203fd  add     rsp, 28h
0x180020401  retn
0x180020402  lea     eax, [r8-1]
0x180020406  jmp     short loc_1800203E7
0x180020408  xor     r9d, r9d; lpArguments
0x18002040b  xor     r8d, r8d; nNumberOfArguments
0x18002040e  mov     ecx, eax; dwExceptionCode
0x180020410  lea     edx, [r9+1]; dwExceptionFlags
0x180020414  call    cs:__imp_RaiseException
```
