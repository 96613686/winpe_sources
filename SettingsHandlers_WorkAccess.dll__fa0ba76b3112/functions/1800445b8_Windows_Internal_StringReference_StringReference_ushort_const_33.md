# Windows::Internal::StringReference::StringReference(ushort const (&)[33])

- ea: `0x1800445b8`
- end: `0x180044609`
- name: `??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[33])`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x1800445b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800445f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800445f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800445d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800445d4`

## string_xrefs

- `0x1800445cd`: `https://login.windows.net/common`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[33])
{
  if ( WindowsCreateStringReference(L"https://login.windows.net/common", 0x20u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800445b8  push    rbx
0x1800445ba  sub     rsp, 20h
0x1800445be  mov     rbx, rcx
0x1800445c1  lea     r8, [rcx+8]; hstringHeader
0x1800445c5  mov     r9, rcx; string
0x1800445c8  mov     edx, 20h ; ' '; length
0x1800445cd  lea     rcx, aHttpsLoginWind; "https://login.windows.net/common"
0x1800445d4  call    cs:__imp_WindowsCreateStringReference
0x1800445db  nop     dword ptr [rax+rax+00h]
0x1800445e0  test    eax, eax
0x1800445e2  jns     short loc_1800445FF
0x1800445e4  xor     r9d, r9d; lpArguments
0x1800445e7  xor     r8d, r8d; nNumberOfArguments
0x1800445ea  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800445ef  lea     edx, [r9+1]; dwExceptionFlags
0x1800445f3  call    cs:__imp_RaiseException
0x1800445fa  nop     dword ptr [rax+rax+00h]
0x1800445ff  mov     rax, rbx
0x180044602  add     rsp, 20h
0x180044606  pop     rbx
0x180044607  retn
```
