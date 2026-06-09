# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180003a70`
- end: `0x180003ab4`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `68`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `33`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fb7c`
- `0x18000ff9c`
- `0x1800105a4`
- `0x180010810`
- `0x180010e2c`
- `0x180011188`
- `0x180011640`
- `0x180011d60`
- `0x1800197ec`
- `0x180019c90`
- `0x18004da30`
- `0x18005d5ec`
- `0x180072a1c`
- `0x18007334c`
- `0x180074804`
- `0x180076824`
- `0x180076cd0`
- `0x180076d64`
- `0x180078af0`
- `0x180083528`
- `0x18009b9c0`
- `0x18009f6dc`
- `0x1800a1540`
- `0x1800acce0`
- `0x1800b8ba4`
- `0x1800c5b30`
- `0x1800c6ee0`
- `0x1800c7be0`
- `0x1800c7c64`
- `0x1800c89ac`
- `0x1800c94b8`
- `0x1800ca2e8`
- `0x1800cadc0`

## callees

- `0x180003a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003aad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003a8b`

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
    JUMPOUT(0x180003AB3LL);
  }
}

```

## disassembly

```asm
0x180003a70  sub     rsp, 28h
0x180003a74  mov     eax, r9d
0x180003a77  mov     r10, rdx
0x180003a7a  cmp     r9d, r8d
0x180003a7d  jnb     short loc_180003A9A
0x180003a7f  lea     r9, [rcx+18h]; string
0x180003a83  mov     r8, rcx; hstringHeader
0x180003a86  mov     rcx, r10; sourceString
0x180003a89  mov     edx, eax; length
0x180003a8b  call    cs:__imp_WindowsCreateStringReference
0x180003a91  test    eax, eax
0x180003a93  js      short loc_180003AA0
0x180003a95  add     rsp, 28h
0x180003a99  retn
0x180003a9a  lea     eax, [r8-1]
0x180003a9e  jmp     short loc_180003A7F
0x180003aa0  xor     r9d, r9d; lpArguments
0x180003aa3  xor     r8d, r8d; nNumberOfArguments
0x180003aa6  mov     edx, 1; dwExceptionFlags
0x180003aab  mov     ecx, eax; dwExceptionCode
0x180003aad  call    cs:__imp_RaiseException
```
