# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140011b68`
- end: `0x140011ba9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `35`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006d2c`
- `0x140030364`
- `0x14003a01c`
- `0x14003a370`
- `0x14003aa1c`
- `0x14003b84c`
- `0x14003c8d0`
- `0x140051c54`
- `0x140052e9c`
- `0x140053df0`
- `0x140055f9c`
- `0x14005be78`
- `0x14005ce70`
- `0x14005e730`
- `0x14005ed0c`
- `0x14005eeb0`
- `0x14005f054`
- `0x14005fea4`
- `0x140060d70`
- `0x1400611b4`
- `0x140062284`
- `0x140062cc4`
- `0x140062fe0`
- `0x1400630d0`
- `0x140063950`
- `0x140063a90`
- `0x140063bc8`
- `0x140063fac`
- `0x140066bd8`
- `0x140066d94`
- `0x140066e60`
- `0x14006716c`
- `0x140067d08`
- `0x14006bf50`
- `0x1400714e0`

## callees

- `0x140011b68`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140011b9d`
- `KERNEL32!RaiseException` at `0x140011b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011b87`

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
    __debugbreak();
  }
}

```

## disassembly

```asm
0x140011b68  sub     rsp, 28h
0x140011b6c  mov     eax, r9d
0x140011b6f  mov     r10, rdx
0x140011b72  cmp     r9d, r8d
0x140011b75  jb      short loc_140011B7B
0x140011b77  lea     eax, [r8-1]
0x140011b7b  lea     r9, [rcx+18h]; string
0x140011b7f  mov     r8, rcx; hstringHeader
0x140011b82  mov     rcx, r10; sourceString
0x140011b85  mov     edx, eax; length
0x140011b87  call    cs:__imp_WindowsCreateStringReference
0x140011b8d  test    eax, eax
0x140011b8f  jns     short loc_140011BA4
0x140011b91  xor     r9d, r9d; lpArguments
0x140011b94  xor     r8d, r8d; nNumberOfArguments
0x140011b97  mov     ecx, eax; dwExceptionCode
0x140011b99  lea     edx, [r9+1]; dwExceptionFlags
0x140011b9d  call    cs:__imp_RaiseException
0x140011ba3  int     3; Trap to Debugger
0x140011ba4  add     rsp, 28h
0x140011ba8  retn
```
