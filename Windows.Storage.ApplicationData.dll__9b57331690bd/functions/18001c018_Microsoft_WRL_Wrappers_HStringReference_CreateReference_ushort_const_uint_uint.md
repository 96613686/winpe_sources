# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001c018`
- end: `0x18001c05b`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *this, const wchar_t *str, unsigned int bufferLen, unsigned int len)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001bfb8`

## callees

- `0x18001c018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c054`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c033`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        Microsoft::WRL::Wrappers::HStringReference *this,
        const wchar_t *str,
        UINT32 bufferLen,
        UINT32 len)
{
  UINT32 v4; // eax
  signed int StringReference; // eax

  v4 = len;
  if ( len >= bufferLen )
    v4 = bufferLen - 1;
  StringReference = WindowsCreateStringReference(str, v4, &this->header_, &this->hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x18001C05ALL);
  }
}

```

## disassembly

```asm
0x18001c018  sub     rsp, 28h
0x18001c01c  mov     eax, len
0x18001c01f  mov     r10, str
0x18001c022  cmp     len, bufferLen
0x18001c025  jnb     short loc_18001C042
0x18001c027  lea     r9, [this+18h]; string
0x18001c02b  mov     r8, this; hstringHeader
0x18001c02e  mov     this, r10; sourceString
0x18001c031  mov     edx, eax; length
0x18001c033  call    cs:__imp_WindowsCreateStringReference
0x18001c039  test    eax, eax
0x18001c03b  js      short loc_18001C048
0x18001c03d  add     rsp, 28h
0x18001c041  retn
0x18001c042  lea     eax, [r8-1]
0x18001c046  jmp     short loc_18001C027
0x18001c048  xor     len, len; lpArguments
0x18001c04b  xor     bufferLen, bufferLen; nNumberOfArguments
0x18001c04e  mov     ecx, eax; dwExceptionCode
0x18001c050  lea     edx, [r9+1]; dwExceptionFlags
0x18001c054  call    cs:__imp_RaiseException
```
