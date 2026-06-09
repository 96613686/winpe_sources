# Windows::Internal::StringReference::StringReference(ushort const (&)[41])

- ea: `0x180047d94`
- end: `0x180047dd8`
- name: `??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[41])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048c80`
- `0x180052e10`
- `0x180053ae8`

## callees

- `0x180047d94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047dc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047db0`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[41])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.Package",
         0x28u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180047d94  push    rbx
0x180047d96  sub     rsp, 20h
0x180047d9a  mov     rbx, rcx
0x180047d9d  lea     r8, [rcx+8]; hstringHeader
0x180047da1  mov     r9, rcx; string
0x180047da4  mov     edx, 28h ; '('; length
0x180047da9  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180047db0  call    cs:__imp_WindowsCreateStringReference
0x180047db6  test    eax, eax
0x180047db8  jns     short loc_180047DCF
0x180047dba  xor     r9d, r9d; lpArguments
0x180047dbd  xor     r8d, r8d; nNumberOfArguments
0x180047dc0  mov     ecx, 0C000000Dh; dwExceptionCode
0x180047dc5  lea     edx, [r9+1]; dwExceptionFlags
0x180047dc9  call    cs:__imp_RaiseException
0x180047dcf  mov     rax, rbx
0x180047dd2  add     rsp, 20h
0x180047dd6  pop     rbx
0x180047dd7  retn
```
