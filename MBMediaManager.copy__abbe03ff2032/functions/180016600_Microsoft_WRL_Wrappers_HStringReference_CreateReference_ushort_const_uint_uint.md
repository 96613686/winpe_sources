# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180016600`
- end: `0x180016643`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020988`
- `0x180020b8c`
- `0x18002711c`
- `0x180038ce4`

## callees

- `0x180016600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001663c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001663c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001661b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001661b`

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
    JUMPOUT(0x180016642LL);
  }
}

```

## disassembly

```asm
0x180016600  sub     rsp, 28h
0x180016604  mov     eax, r9d
0x180016607  mov     r10, rdx
0x18001660a  cmp     r9d, r8d
0x18001660d  jnb     short loc_18001662A
0x18001660f  lea     r9, [rcx+18h]; string
0x180016613  mov     r8, rcx; hstringHeader
0x180016616  mov     rcx, r10; sourceString
0x180016619  mov     edx, eax; length
0x18001661b  call    cs:__imp_WindowsCreateStringReference
0x180016621  test    eax, eax
0x180016623  js      short loc_180016630
0x180016625  add     rsp, 28h
0x180016629  retn
0x18001662a  lea     eax, [r8-1]
0x18001662e  jmp     short loc_18001660F
0x180016630  xor     r9d, r9d; lpArguments
0x180016633  xor     r8d, r8d; nNumberOfArguments
0x180016636  mov     ecx, eax; dwExceptionCode
0x180016638  lea     edx, [r9+1]; dwExceptionFlags
0x18001663c  call    cs:__imp_RaiseException
```
