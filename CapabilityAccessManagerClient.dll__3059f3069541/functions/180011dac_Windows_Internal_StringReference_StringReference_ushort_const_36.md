# Windows::Internal::StringReference::StringReference(ushort const (&)[36])

- ea: `0x180011dac`
- end: `0x180011df0`
- name: `??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[36])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016a38`
- `0x180022dc8`

## callees

- `0x180011dac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011de1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011dc8`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[36])
{
  if ( WindowsCreateStringReference(
         L"Windows.System.Internal.UserManager",
         0x23u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180011dac  push    rbx
0x180011dae  sub     rsp, 20h
0x180011db2  mov     rbx, rcx
0x180011db5  lea     r8, [rcx+8]; hstringHeader
0x180011db9  mov     r9, rcx; string
0x180011dbc  mov     edx, 23h ; '#'; length
0x180011dc1  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180011dc8  call    cs:__imp_WindowsCreateStringReference
0x180011dce  test    eax, eax
0x180011dd0  jns     short loc_180011DE7
0x180011dd2  xor     r9d, r9d; lpArguments
0x180011dd5  xor     r8d, r8d; nNumberOfArguments
0x180011dd8  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011ddd  lea     edx, [r9+1]; dwExceptionFlags
0x180011de1  call    cs:__imp_RaiseException
0x180011de7  mov     rax, rbx
0x180011dea  add     rsp, 20h
0x180011dee  pop     rbx
0x180011def  retn
```
