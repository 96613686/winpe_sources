# Windows::Internal::StringReference::StringReference(ushort const (&)[37])

- ea: `0x18005b728`
- end: `0x18005b76c`
- name: `??$?0$0CF@@StringReference@Internal@Windows@@QEAA@AEAY0CF@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[37])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005c910`
- `0x18007d734`

## callees

- `0x18005b728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b75d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b75d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b744`

## string_xrefs

- `0x18005b73d`: `Windows.Networking.UX.StaticIpConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[37])
{
  if ( WindowsCreateStringReference(
         L"Windows.Networking.UX.StaticIpConfig",
         0x24u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18005b728  push    rbx
0x18005b72a  sub     rsp, 20h
0x18005b72e  mov     rbx, rcx
0x18005b731  lea     r8, [rcx+8]; hstringHeader
0x18005b735  mov     r9, rcx; string
0x18005b738  mov     edx, 24h ; '$'; length
0x18005b73d  lea     rcx, ?RuntimeClass_Windows_Networking_UX_StaticIpConfig@@3QBGB; "Windows.Networking.UX.StaticIpConfig"
0x18005b744  call    cs:__imp_WindowsCreateStringReference
0x18005b74a  test    eax, eax
0x18005b74c  jns     short loc_18005B763
0x18005b74e  xor     r9d, r9d; lpArguments
0x18005b751  xor     r8d, r8d; nNumberOfArguments
0x18005b754  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005b759  lea     edx, [r9+1]; dwExceptionFlags
0x18005b75d  call    cs:__imp_RaiseException
0x18005b763  mov     rax, rbx
0x18005b766  add     rsp, 20h
0x18005b76a  pop     rbx
0x18005b76b  retn
```
