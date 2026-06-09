# Windows::Internal::StringReference::StringReference(ushort const (&)[56])

- ea: `0x180020d48`
- end: `0x180020d99`
- name: `??$?0$0DI@@StringReference@Internal@Windows@@QEAA@AEAY0DI@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[56])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800297d0`

## callees

- `0x180020d48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020d83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020d83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020d64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020d64`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[56])
{
  if ( WindowsCreateStringReference(
         L"EnterpriseDeviceManagement.Enrollment.ReflectedEnroller",
         0x37u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180020d48  push    rbx
0x180020d4a  sub     rsp, 20h
0x180020d4e  mov     rbx, rcx
0x180020d51  lea     r8, [rcx+8]; hstringHeader
0x180020d55  mov     r9, rcx; string
0x180020d58  mov     edx, 37h ; '7'; length
0x180020d5d  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Enrollment_ReflectedEnroller@@3QBGB; "EnterpriseDeviceManagement.Enrollment.R"...
0x180020d64  call    cs:__imp_WindowsCreateStringReference
0x180020d6b  nop     dword ptr [rax+rax+00h]
0x180020d70  test    eax, eax
0x180020d72  jns     short loc_180020D8F
0x180020d74  xor     r9d, r9d; lpArguments
0x180020d77  xor     r8d, r8d; nNumberOfArguments
0x180020d7a  mov     ecx, 0C000000Dh; dwExceptionCode
0x180020d7f  lea     edx, [r9+1]; dwExceptionFlags
0x180020d83  call    cs:__imp_RaiseException
0x180020d8a  nop     dword ptr [rax+rax+00h]
0x180020d8f  mov     rax, rbx
0x180020d92  add     rsp, 20h
0x180020d96  pop     rbx
0x180020d97  retn
```
