# Windows::Internal::StringReference::StringReference(ushort const (&)[9])

- ea: `0x1800728c8`
- end: `0x180072919`
- name: `??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[9])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800759c0`

## callees

- `0x1800728c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072903`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800728e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800728e4`

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
0x1800728c8  push    rbx
0x1800728ca  sub     rsp, 20h
0x1800728ce  mov     rbx, rcx
0x1800728d1  lea     r8, [rcx+8]; hstringHeader
0x1800728d5  mov     r9, rcx; string
0x1800728d8  mov     edx, 8; length
0x1800728dd  lea     rcx, sourceString; "resource"
0x1800728e4  call    cs:__imp_WindowsCreateStringReference
0x1800728eb  nop     dword ptr [rax+rax+00h]
0x1800728f0  test    eax, eax
0x1800728f2  jns     short loc_18007290F
0x1800728f4  xor     r9d, r9d; lpArguments
0x1800728f7  xor     r8d, r8d; nNumberOfArguments
0x1800728fa  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800728ff  lea     edx, [r9+1]; dwExceptionFlags
0x180072903  call    cs:__imp_RaiseException
0x18007290a  nop     dword ptr [rax+rax+00h]
0x18007290f  mov     rax, rbx
0x180072912  add     rsp, 20h
0x180072916  pop     rbx
0x180072917  retn
```
