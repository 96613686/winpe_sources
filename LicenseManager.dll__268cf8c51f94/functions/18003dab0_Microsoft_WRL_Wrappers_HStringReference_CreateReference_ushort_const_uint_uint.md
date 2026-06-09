# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003dab0`
- end: `0x18003daf3`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d928`
- `0x1800401e0`
- `0x180059460`
- `0x180061324`
- `0x180087268`
- `0x18009f05c`
- `0x1800a60f4`
- `0x1800a8170`

## callees

- `0x18003dab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003daec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003daec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dacb`

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
    JUMPOUT(0x18003DAF2LL);
  }
}

```

## disassembly

```asm
0x18003dab0  sub     rsp, 28h
0x18003dab4  mov     eax, r9d
0x18003dab7  mov     r10, rdx
0x18003daba  cmp     r9d, r8d
0x18003dabd  jnb     short loc_18003DADA
0x18003dabf  lea     r9, [rcx+18h]; string
0x18003dac3  mov     r8, rcx; hstringHeader
0x18003dac6  mov     rcx, r10; sourceString
0x18003dac9  mov     edx, eax; length
0x18003dacb  call    cs:__imp_WindowsCreateStringReference
0x18003dad1  test    eax, eax
0x18003dad3  js      short loc_18003DAE0
0x18003dad5  add     rsp, 28h
0x18003dad9  retn
0x18003dada  lea     eax, [r8-1]
0x18003dade  jmp     short loc_18003DABF
0x18003dae0  xor     r9d, r9d; lpArguments
0x18003dae3  xor     r8d, r8d; nNumberOfArguments
0x18003dae6  mov     ecx, eax; dwExceptionCode
0x18003dae8  lea     edx, [r9+1]; dwExceptionFlags
0x18003daec  call    cs:__imp_RaiseException
```
