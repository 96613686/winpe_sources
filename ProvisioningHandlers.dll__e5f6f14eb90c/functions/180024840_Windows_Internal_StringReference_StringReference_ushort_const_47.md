# Windows::Internal::StringReference::StringReference(ushort const (&)[47])

- ea: `0x180024840`
- end: `0x180024891`
- name: `??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[47])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180024f40`
- `0x180026280`
- `0x180026b60`

## callees

- `0x180024840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002487b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002487b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002485c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002485c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[47])
{
  if ( WindowsCreateStringReference(
         L"Windows.Management.Provisioning.PackageManager",
         0x2Eu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180024840  push    rbx
0x180024842  sub     rsp, 20h
0x180024846  mov     rbx, rcx
0x180024849  lea     r8, [rcx+8]; hstringHeader
0x18002484d  mov     r9, rcx; string
0x180024850  mov     edx, 2Eh ; '.'; length
0x180024855  lea     rcx, ?RuntimeClass_Windows_Management_Provisioning_PackageManager@@3QBGB; "Windows.Management.Provisioning.Package"...
0x18002485c  call    cs:__imp_WindowsCreateStringReference
0x180024863  nop     dword ptr [rax+rax+00h]
0x180024868  test    eax, eax
0x18002486a  jns     short loc_180024887
0x18002486c  xor     r9d, r9d; lpArguments
0x18002486f  xor     r8d, r8d; nNumberOfArguments
0x180024872  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024877  lea     edx, [r9+1]; dwExceptionFlags
0x18002487b  call    cs:__imp_RaiseException
0x180024882  nop     dword ptr [rax+rax+00h]
0x180024887  mov     rax, rbx
0x18002488a  add     rsp, 20h
0x18002488e  pop     rbx
0x18002488f  retn
```
