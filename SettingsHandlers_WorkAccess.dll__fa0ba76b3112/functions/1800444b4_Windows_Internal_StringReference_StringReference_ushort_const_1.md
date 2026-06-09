# Windows::Internal::StringReference::StringReference(ushort const (&)[1])

- ea: `0x1800444b4`
- end: `0x180044502`
- name: `??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z`
- size: `78`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[1])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x1800444b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800444ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800444ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800444cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800444cd`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[1])
{
  if ( WindowsCreateStringReference(&sourceString, 0, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800444b4  push    rbx
0x1800444b6  sub     rsp, 20h
0x1800444ba  mov     rbx, rcx
0x1800444bd  lea     r8, [rcx+8]; hstringHeader
0x1800444c1  mov     r9, rcx; string
0x1800444c4  xor     edx, edx; length
0x1800444c6  lea     rcx, sourceString; sourceString
0x1800444cd  call    cs:__imp_WindowsCreateStringReference
0x1800444d4  nop     dword ptr [rax+rax+00h]
0x1800444d9  test    eax, eax
0x1800444db  jns     short loc_1800444F8
0x1800444dd  xor     r9d, r9d; lpArguments
0x1800444e0  xor     r8d, r8d; nNumberOfArguments
0x1800444e3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800444e8  lea     edx, [r9+1]; dwExceptionFlags
0x1800444ec  call    cs:__imp_RaiseException
0x1800444f3  nop     dword ptr [rax+rax+00h]
0x1800444f8  mov     rax, rbx
0x1800444fb  add     rsp, 20h
0x1800444ff  pop     rbx
0x180044500  retn
```
