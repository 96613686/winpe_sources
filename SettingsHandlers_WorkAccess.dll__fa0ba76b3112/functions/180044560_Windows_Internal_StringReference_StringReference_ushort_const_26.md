# Windows::Internal::StringReference::StringReference(ushort const (&)[26])

- ea: `0x180044560`
- end: `0x1800445b1`
- name: `??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[26])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x180044560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004459b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004459b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004457c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004457c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[26])
{
  if ( WindowsCreateStringReference(L"https://login.windows.net", 0x19u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180044560  push    rbx
0x180044562  sub     rsp, 20h
0x180044566  mov     rbx, rcx
0x180044569  lea     r8, [rcx+8]; hstringHeader
0x18004456d  mov     r9, rcx; string
0x180044570  mov     edx, 19h; length
0x180044575  lea     rcx, aHttpsLoginWind_0; "https://login.windows.net"
0x18004457c  call    cs:__imp_WindowsCreateStringReference
0x180044583  nop     dword ptr [rax+rax+00h]
0x180044588  test    eax, eax
0x18004458a  jns     short loc_1800445A7
0x18004458c  xor     r9d, r9d; lpArguments
0x18004458f  xor     r8d, r8d; nNumberOfArguments
0x180044592  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044597  lea     edx, [r9+1]; dwExceptionFlags
0x18004459b  call    cs:__imp_RaiseException
0x1800445a2  nop     dword ptr [rax+rax+00h]
0x1800445a7  mov     rax, rbx
0x1800445aa  add     rsp, 20h
0x1800445ae  pop     rbx
0x1800445af  retn
```
