# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140035d34`
- end: `0x140035d77`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002ea80`
- `0x140050440`
- `0x140088cd0`
- `0x14008b1c0`

## callees

- `0x140035d34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140035d70`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140035d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140035d4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140035d4f`

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
    JUMPOUT(0x140035D76LL);
  }
}

```

## disassembly

```asm
0x140035d34  sub     rsp, 28h
0x140035d38  mov     eax, r9d
0x140035d3b  mov     r10, rdx
0x140035d3e  cmp     r9d, r8d
0x140035d41  jnb     short loc_140035D5E
0x140035d43  lea     r9, [rcx+18h]; string
0x140035d47  mov     r8, rcx; hstringHeader
0x140035d4a  mov     rcx, r10; sourceString
0x140035d4d  mov     edx, eax; length
0x140035d4f  call    cs:__imp_WindowsCreateStringReference
0x140035d55  test    eax, eax
0x140035d57  js      short loc_140035D64
0x140035d59  add     rsp, 28h
0x140035d5d  retn
0x140035d5e  lea     eax, [r8-1]
0x140035d62  jmp     short loc_140035D43
0x140035d64  xor     r9d, r9d; lpArguments
0x140035d67  xor     r8d, r8d; nNumberOfArguments
0x140035d6a  mov     ecx, eax; dwExceptionCode
0x140035d6c  lea     edx, [r9+1]; dwExceptionFlags
0x140035d70  call    cs:__imp_RaiseException
```
