# Windows::Internal::StringReference::StringReference(ushort const (&)[45])

- ea: `0x180051584`
- end: `0x1800515c7`
- name: `??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z`
- size: `67`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180052e10`
- `0x180053ae8`

## callees

- `0x180051584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800515b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800515b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005159f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005159f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x2Cu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180051584  push    rbx
0x180051586  sub     rsp, 20h
0x18005158a  mov     rax, rdx
0x18005158d  lea     r8, [rcx+8]; hstringHeader
0x180051591  mov     rbx, rcx
0x180051594  mov     r9, rcx; string
0x180051597  mov     rcx, rax; sourceString
0x18005159a  mov     edx, 2Ch ; ','; length
0x18005159f  call    cs:__imp_WindowsCreateStringReference
0x1800515a5  test    eax, eax
0x1800515a7  jns     short loc_1800515BE
0x1800515a9  xor     r9d, r9d; lpArguments
0x1800515ac  xor     r8d, r8d; nNumberOfArguments
0x1800515af  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800515b4  lea     edx, [r9+1]; dwExceptionFlags
0x1800515b8  call    cs:__imp_RaiseException
0x1800515be  mov     rax, rbx
0x1800515c1  add     rsp, 20h
0x1800515c5  pop     rbx
0x1800515c6  retn
```
