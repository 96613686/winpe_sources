# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000aab8`
- end: `0x14000aaf9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004dbc`
- `0x14000aedc`
- `0x14000cdfc`
- `0x140012980`
- `0x140014834`
- `0x140014d1c`
- `0x140014df8`
- `0x140014ef0`
- `0x1400152cc`
- `0x14001563c`
- `0x1400159a4`
- `0x14001a290`
- `0x14001b470`
- `0x14001bb60`
- `0x14001bcc0`
- `0x14001be70`
- `0x14001bf70`
- `0x14001f838`
- `0x140025884`
- `0x140025e84`
- `0x140025f88`

## callees

- `0x14000aab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000aaed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000aaed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000aad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000aad7`

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
0x14000aab8  sub     rsp, 28h
0x14000aabc  mov     eax, r9d
0x14000aabf  mov     r10, rdx
0x14000aac2  cmp     r9d, r8d
0x14000aac5  jb      short loc_14000AACB
0x14000aac7  lea     eax, [r8-1]
0x14000aacb  lea     r9, [rcx+18h]; string
0x14000aacf  mov     r8, rcx; hstringHeader
0x14000aad2  mov     rcx, r10; sourceString
0x14000aad5  mov     edx, eax; length
0x14000aad7  call    cs:__imp_WindowsCreateStringReference
0x14000aadd  test    eax, eax
0x14000aadf  jns     short loc_14000AAF4
0x14000aae1  xor     r9d, r9d; lpArguments
0x14000aae4  xor     r8d, r8d; nNumberOfArguments
0x14000aae7  mov     ecx, eax; dwExceptionCode
0x14000aae9  lea     edx, [r9+1]; dwExceptionFlags
0x14000aaed  call    cs:__imp_RaiseException
0x14000aaf3  int     3; Trap to Debugger
0x14000aaf4  add     rsp, 28h
0x14000aaf8  retn
```
