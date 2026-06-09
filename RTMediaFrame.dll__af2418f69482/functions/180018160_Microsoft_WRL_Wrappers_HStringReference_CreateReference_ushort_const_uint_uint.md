# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180018160`
- end: `0x1800181a4`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `68`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020560`
- `0x180020754`
- `0x1800209f0`
- `0x180021f14`
- `0x1800332f0`
- `0x18003eb54`
- `0x180044afc`
- `0x1800461ac`
- `0x1800468a0`
- `0x1800469a0`
- `0x180048bd4`
- `0x18004b128`
- `0x18004b330`
- `0x18004b4a0`
- `0x18004b608`

## callees

- `0x180018160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018197`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001817b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001817b`

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
0x180018160  sub     rsp, 28h
0x180018164  mov     eax, r9d
0x180018167  mov     r10, rdx
0x18001816a  cmp     r9d, r8d
0x18001816d  jnb     short loc_18001819E
0x18001816f  lea     r9, [rcx+18h]; string
0x180018173  mov     r8, rcx; hstringHeader
0x180018176  mov     rcx, r10; sourceString
0x180018179  mov     edx, eax; length
0x18001817b  call    cs:__imp_WindowsCreateStringReference
0x180018181  test    eax, eax
0x180018183  js      short loc_18001818A
0x180018185  add     rsp, 28h
0x180018189  retn
0x18001818a  xor     r9d, r9d; lpArguments
0x18001818d  xor     r8d, r8d; nNumberOfArguments
0x180018190  mov     edx, 1; dwExceptionFlags
0x180018195  mov     ecx, eax; dwExceptionCode
0x180018197  call    cs:__imp_RaiseException
0x18001819d  int     3; Trap to Debugger
0x18001819e  lea     eax, [r8-1]
0x1800181a2  jmp     short loc_18001816F
```
