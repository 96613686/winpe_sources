# Windows::Internal::StringReference::StringReference(ushort const (&)[22])

- ea: `0x18001595c`
- end: `0x18001599f`
- name: `??$?0$0BG@@StringReference@Internal@Windows@@QEAA@AEAY0BG@$$CBG@Z`
- size: `67`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*stringRef)[22])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ae0`
- `0x18001bc50`
- `0x18001bcb0`

## callees

- `0x18001595c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015990`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015977`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*stringRef)[22])
{
  if ( WindowsCreateStringReference((PCWSTR)stringRef, 0x15u, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x18001595c  push    rbx
0x18001595e  sub     rsp, 20h
0x180015962  mov     rax, stringRef
0x180015965  lea     r8, [this+8]; hstringHeader
0x180015969  mov     rbx, this
0x18001596c  mov     r9, this; string
0x18001596f  mov     this, rax; sourceString
0x180015972  mov     edx, 15h; length
0x180015977  call    cs:__imp_WindowsCreateStringReference
0x18001597d  test    eax, eax
0x18001597f  jns     short loc_180015996
0x180015981  xor     r9d, r9d; lpArguments
0x180015984  xor     r8d, r8d; nNumberOfArguments
0x180015987  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001598c  lea     edx, [r9+1]; dwExceptionFlags
0x180015990  call    cs:__imp_RaiseException
0x180015996  mov     rax, rbx
0x180015999  add     rsp, 20h
0x18001599d  pop     rbx
0x18001599e  retn
```
