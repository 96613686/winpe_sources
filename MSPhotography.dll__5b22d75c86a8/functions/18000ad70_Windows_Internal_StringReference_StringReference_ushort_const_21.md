# Windows::Internal::StringReference::StringReference(ushort const (&)[21])

- ea: `0x18000ad70`
- end: `0x18000adb4`
- name: `??$?0$0BF@@StringReference@Internal@Windows@@QEAA@AEAY0BF@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[21])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b760`
- `0x18000bbc0`
- `0x18000bf30`
- `0x180019de0`

## callees

- `0x18000ad70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ada5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ada5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ad8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ad8c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[21])
{
  if ( WindowsCreateStringReference(L"SynchronousDetection", 0x14u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000ad70  push    rbx
0x18000ad72  sub     rsp, 20h
0x18000ad76  mov     rbx, rcx
0x18000ad79  lea     r8, [rcx+8]; hstringHeader
0x18000ad7d  mov     r9, rcx; string
0x18000ad80  mov     edx, 14h; length
0x18000ad85  lea     rcx, sourceString; "SynchronousDetection"
0x18000ad8c  call    cs:__imp_WindowsCreateStringReference
0x18000ad92  test    eax, eax
0x18000ad94  jns     short loc_18000ADAB
0x18000ad96  xor     r9d, r9d; lpArguments
0x18000ad99  xor     r8d, r8d; nNumberOfArguments
0x18000ad9c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000ada1  lea     edx, [r9+1]; dwExceptionFlags
0x18000ada5  call    cs:__imp_RaiseException
0x18000adab  mov     rax, rbx
0x18000adae  add     rsp, 20h
0x18000adb2  pop     rbx
0x18000adb3  retn
```
