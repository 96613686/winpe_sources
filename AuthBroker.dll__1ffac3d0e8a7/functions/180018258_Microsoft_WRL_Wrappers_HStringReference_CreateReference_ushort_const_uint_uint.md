# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180018258`
- end: `0x180018299`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *this, const wchar_t *str, UINT32 bufferLen, UINT32 len)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800054bc`
- `0x1800159f4`
- `0x180018f70`
- `0x18001f474`

## callees

- `0x180018258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001828d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001828d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018277`

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
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180018258  sub     rsp, 28h
0x18001825c  mov     eax, len
0x18001825f  mov     r10, str
0x180018262  cmp     len, bufferLen
0x180018265  jb      short loc_18001826B
0x180018267  lea     eax, [r8-1]
0x18001826b  lea     r9, [this+18h]; string
0x18001826f  mov     r8, this; hstringHeader
0x180018272  mov     this, r10; sourceString
0x180018275  mov     edx, eax; length
0x180018277  call    cs:__imp_WindowsCreateStringReference
0x18001827d  test    eax, eax
0x18001827f  jns     short loc_180018294
0x180018281  xor     len, len; lpArguments
0x180018284  xor     bufferLen, bufferLen; nNumberOfArguments
0x180018287  mov     ecx, eax; dwExceptionCode
0x180018289  lea     edx, [r9+1]; dwExceptionFlags
0x18001828d  call    cs:__imp_RaiseException
0x180018293  int     3; Trap to Debugger
0x180018294  add     rsp, 28h
0x180018298  retn
```
