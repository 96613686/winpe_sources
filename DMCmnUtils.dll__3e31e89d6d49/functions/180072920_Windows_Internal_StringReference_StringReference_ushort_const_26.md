# Windows::Internal::StringReference::StringReference(ushort const (&)[26])

- ea: `0x180072920`
- end: `0x180072971`
- name: `??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[26])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800759c0`
- `0x18007759c`

## callees

- `0x180072920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007295b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007295b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007293c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007293c`

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
0x180072920  push    rbx
0x180072922  sub     rsp, 20h
0x180072926  mov     rbx, rcx
0x180072929  lea     r8, [rcx+8]; hstringHeader
0x18007292d  mov     r9, rcx; string
0x180072930  mov     edx, 19h; length
0x180072935  lea     rcx, aHttpsLoginWind_0; "https://login.windows.net"
0x18007293c  call    cs:__imp_WindowsCreateStringReference
0x180072943  nop     dword ptr [rax+rax+00h]
0x180072948  test    eax, eax
0x18007294a  jns     short loc_180072967
0x18007294c  xor     r9d, r9d; lpArguments
0x18007294f  xor     r8d, r8d; nNumberOfArguments
0x180072952  mov     ecx, 0C000000Dh; dwExceptionCode
0x180072957  lea     edx, [r9+1]; dwExceptionFlags
0x18007295b  call    cs:__imp_RaiseException
0x180072962  nop     dword ptr [rax+rax+00h]
0x180072967  mov     rax, rbx
0x18007296a  add     rsp, 20h
0x18007296e  pop     rbx
0x18007296f  retn
```
