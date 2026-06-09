# Windows::Internal::StringReference::StringReference(ushort const (&)[9])

- ea: `0x180044508`
- end: `0x180044559`
- name: `??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[9])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x180044508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044543`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044524`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[9])
{
  if ( WindowsCreateStringReference(L"resource", 8u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180044508  push    rbx
0x18004450a  sub     rsp, 20h
0x18004450e  mov     rbx, rcx
0x180044511  lea     r8, [rcx+8]; hstringHeader
0x180044515  mov     r9, rcx; string
0x180044518  mov     edx, 8; length
0x18004451d  lea     rcx, aResource; "resource"
0x180044524  call    cs:__imp_WindowsCreateStringReference
0x18004452b  nop     dword ptr [rax+rax+00h]
0x180044530  test    eax, eax
0x180044532  jns     short loc_18004454F
0x180044534  xor     r9d, r9d; lpArguments
0x180044537  xor     r8d, r8d; nNumberOfArguments
0x18004453a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004453f  lea     edx, [r9+1]; dwExceptionFlags
0x180044543  call    cs:__imp_RaiseException
0x18004454a  nop     dword ptr [rax+rax+00h]
0x18004454f  mov     rax, rbx
0x180044552  add     rsp, 20h
0x180044556  pop     rbx
0x180044557  retn
```
