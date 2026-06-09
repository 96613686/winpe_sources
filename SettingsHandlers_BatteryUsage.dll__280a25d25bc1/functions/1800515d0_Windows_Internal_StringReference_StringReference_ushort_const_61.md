# Windows::Internal::StringReference::StringReference(ushort const (&)[61])

- ea: `0x1800515d0`
- end: `0x180051613`
- name: `??$?0$0DN@@StringReference@Internal@Windows@@QEAA@AEAY0DN@$$CBG@Z`
- size: `67`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180052e10`
- `0x180053ae8`

## callees

- `0x1800515d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051604`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800515eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800515eb`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x3Cu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800515d0  push    rbx
0x1800515d2  sub     rsp, 20h
0x1800515d6  mov     rax, rdx
0x1800515d9  lea     r8, [rcx+8]; hstringHeader
0x1800515dd  mov     rbx, rcx
0x1800515e0  mov     r9, rcx; string
0x1800515e3  mov     rcx, rax; sourceString
0x1800515e6  mov     edx, 3Ch ; '<'; length
0x1800515eb  call    cs:__imp_WindowsCreateStringReference
0x1800515f1  test    eax, eax
0x1800515f3  jns     short loc_18005160A
0x1800515f5  xor     r9d, r9d; lpArguments
0x1800515f8  xor     r8d, r8d; nNumberOfArguments
0x1800515fb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180051600  lea     edx, [r9+1]; dwExceptionFlags
0x180051604  call    cs:__imp_RaiseException
0x18005160a  mov     rax, rbx
0x18005160d  add     rsp, 20h
0x180051611  pop     rbx
0x180051612  retn
```
