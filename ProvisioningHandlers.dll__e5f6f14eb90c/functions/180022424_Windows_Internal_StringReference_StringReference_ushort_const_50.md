# Windows::Internal::StringReference::StringReference(ushort const (&)[50])

- ea: `0x180022424`
- end: `0x180022475`
- name: `??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[50])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800230d8`
- `0x1800235dc`

## callees

- `0x180022424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002245f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002245f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022440`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[50])
{
  if ( WindowsCreateStringReference(
         L"Windows.Management.Provisioning.PackageCollection",
         0x31u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180022424  push    rbx
0x180022426  sub     rsp, 20h
0x18002242a  mov     rbx, rcx
0x18002242d  lea     r8, [rcx+8]; hstringHeader
0x180022431  mov     r9, rcx; string
0x180022434  mov     edx, 31h ; '1'; length
0x180022439  lea     rcx, ?RuntimeClass_Windows_Management_Provisioning_PackageCollection@@3QBGB; "Windows.Management.Provisioning.Package"...
0x180022440  call    cs:__imp_WindowsCreateStringReference
0x180022447  nop     dword ptr [rax+rax+00h]
0x18002244c  test    eax, eax
0x18002244e  jns     short loc_18002246B
0x180022450  xor     r9d, r9d; lpArguments
0x180022453  xor     r8d, r8d; nNumberOfArguments
0x180022456  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002245b  lea     edx, [r9+1]; dwExceptionFlags
0x18002245f  call    cs:__imp_RaiseException
0x180022466  nop     dword ptr [rax+rax+00h]
0x18002246b  mov     rax, rbx
0x18002246e  add     rsp, 20h
0x180022472  pop     rbx
0x180022473  retn
```
