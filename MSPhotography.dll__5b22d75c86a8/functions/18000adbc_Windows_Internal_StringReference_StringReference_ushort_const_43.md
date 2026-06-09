# Windows::Internal::StringReference::StringReference(ushort const (&)[43])

- ea: `0x18000adbc`
- end: `0x18000adff`
- name: `??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b760`
- `0x1800b4cb0`

## callees

- `0x18000adbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000adf0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000adf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000add7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000add7`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x2Au, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000adbc  push    rbx
0x18000adbe  sub     rsp, 20h
0x18000adc2  mov     rax, rdx
0x18000adc5  lea     r8, [rcx+8]; hstringHeader
0x18000adc9  mov     rbx, rcx
0x18000adcc  mov     r9, rcx; string
0x18000adcf  mov     rcx, rax; sourceString
0x18000add2  mov     edx, 2Ah ; '*'; length
0x18000add7  call    cs:__imp_WindowsCreateStringReference
0x18000addd  test    eax, eax
0x18000addf  jns     short loc_18000ADF6
0x18000ade1  xor     r9d, r9d; lpArguments
0x18000ade4  xor     r8d, r8d; nNumberOfArguments
0x18000ade7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000adec  lea     edx, [r9+1]; dwExceptionFlags
0x18000adf0  call    cs:__imp_RaiseException
0x18000adf6  mov     rax, rbx
0x18000adf9  add     rsp, 20h
0x18000adfd  pop     rbx
0x18000adfe  retn
```
