# Windows::Internal::StringReference::StringReference(ushort const (&)[39])

- ea: `0x18000c1d8`
- end: `0x18000c21c`
- name: `??$?0$0CH@@StringReference@Internal@Windows@@QEAA@AEAY0CH@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[39])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001937c`
- `0x180019de0`

## callees

- `0x18000c1d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c20d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c20d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1f4`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[39])
{
  if ( WindowsCreateStringReference(
         L"Windows.Media.FaceAnalysis.FaceTracker",
         0x26u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000c1d8  push    rbx
0x18000c1da  sub     rsp, 20h
0x18000c1de  mov     rbx, rcx
0x18000c1e1  lea     r8, [rcx+8]; hstringHeader
0x18000c1e5  mov     r9, rcx; string
0x18000c1e8  mov     edx, 26h ; '&'; length
0x18000c1ed  lea     rcx, ?RuntimeClass_Windows_Media_FaceAnalysis_FaceTracker@@3QBGB; "Windows.Media.FaceAnalysis.FaceTracker"
0x18000c1f4  call    cs:__imp_WindowsCreateStringReference
0x18000c1fa  test    eax, eax
0x18000c1fc  jns     short loc_18000C213
0x18000c1fe  xor     r9d, r9d; lpArguments
0x18000c201  xor     r8d, r8d; nNumberOfArguments
0x18000c204  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000c209  lea     edx, [r9+1]; dwExceptionFlags
0x18000c20d  call    cs:__imp_RaiseException
0x18000c213  mov     rax, rbx
0x18000c216  add     rsp, 20h
0x18000c21a  pop     rbx
0x18000c21b  retn
```
