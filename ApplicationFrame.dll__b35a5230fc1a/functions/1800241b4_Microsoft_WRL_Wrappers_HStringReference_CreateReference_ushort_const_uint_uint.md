# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800241b4`
- end: `0x1800241f7`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180059310`

## callees

- `0x1800241b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800241f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800241f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800241cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800241cf`

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
    JUMPOUT(0x1800241F6LL);
  }
}

```

## disassembly

```asm
0x1800241b4  sub     rsp, 28h
0x1800241b8  mov     eax, r9d
0x1800241bb  mov     r10, rdx
0x1800241be  cmp     r9d, r8d
0x1800241c1  jnb     short loc_1800241DE
0x1800241c3  lea     r9, [rcx+18h]; string
0x1800241c7  mov     r8, rcx; hstringHeader
0x1800241ca  mov     rcx, r10; sourceString
0x1800241cd  mov     edx, eax; length
0x1800241cf  call    cs:__imp_WindowsCreateStringReference
0x1800241d5  test    eax, eax
0x1800241d7  js      short loc_1800241E4
0x1800241d9  add     rsp, 28h
0x1800241dd  retn
0x1800241de  lea     eax, [r8-1]
0x1800241e2  jmp     short loc_1800241C3
0x1800241e4  xor     r9d, r9d; lpArguments
0x1800241e7  xor     r8d, r8d; nNumberOfArguments
0x1800241ea  mov     ecx, eax; dwExceptionCode
0x1800241ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800241f0  call    cs:__imp_RaiseException
```
