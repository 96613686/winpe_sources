# Windows::Internal::StringReference::StringReference(ushort const (&)[48])

- ea: `0x180044668`
- end: `0x1800446b9`
- name: `??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[48])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046768`
- `0x1800468d4`

## callees

- `0x180044668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800446a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800446a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044684`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[48])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.Enrollment.Enroller",
         0x2Fu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180044668  push    rbx
0x18004466a  sub     rsp, 20h
0x18004466e  mov     rbx, rcx
0x180044671  lea     r8, [rcx+8]; hstringHeader
0x180044675  mov     r9, rcx; string
0x180044678  mov     edx, 2Fh ; '/'; length
0x18004467d  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x180044684  call    cs:__imp_WindowsCreateStringReference
0x18004468b  nop     dword ptr [rax+rax+00h]
0x180044690  test    eax, eax
0x180044692  jns     short loc_1800446AF
0x180044694  xor     r9d, r9d; lpArguments
0x180044697  xor     r8d, r8d; nNumberOfArguments
0x18004469a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004469f  lea     edx, [r9+1]; dwExceptionFlags
0x1800446a3  call    cs:__imp_RaiseException
0x1800446aa  nop     dword ptr [rax+rax+00h]
0x1800446af  mov     rax, rbx
0x1800446b2  add     rsp, 20h
0x1800446b6  pop     rbx
0x1800446b7  retn
```
