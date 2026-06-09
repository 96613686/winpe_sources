# Windows::Internal::StringReference::StringReference(ushort const (&)[51])

- ea: `0x180008ab4`
- end: `0x180008af8`
- name: `??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[51])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c790`
- `0x18000d100`

## callees

- `0x180008ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ae9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008ad0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008ad0`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[51])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.UupProductPackage",
         0x32u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180008ab4  push    rbx
0x180008ab6  sub     rsp, 20h
0x180008aba  mov     rbx, rcx
0x180008abd  lea     r8, [rcx+8]; hstringHeader
0x180008ac1  mov     r9, rcx; string
0x180008ac4  mov     edx, 32h ; '2'; length
0x180008ac9  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_UupProductPackage@@3QBGB; "Windows.Internal.StateRepository.UupPro"...
0x180008ad0  call    cs:__imp_WindowsCreateStringReference
0x180008ad6  test    eax, eax
0x180008ad8  jns     short loc_180008AEF
0x180008ada  xor     r9d, r9d; lpArguments
0x180008add  xor     r8d, r8d; nNumberOfArguments
0x180008ae0  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008ae5  lea     edx, [r9+1]; dwExceptionFlags
0x180008ae9  call    cs:__imp_RaiseException
0x180008aef  mov     rax, rbx
0x180008af2  add     rsp, 20h
0x180008af6  pop     rbx
0x180008af7  retn
```
