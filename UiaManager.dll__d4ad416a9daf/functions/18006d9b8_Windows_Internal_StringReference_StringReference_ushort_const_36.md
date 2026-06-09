# Windows::Internal::StringReference::StringReference(ushort const (&)[36])

- ea: `0x18006d9b8`
- end: `0x18006d9fc`
- name: `??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[36])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18006dbd0`
- `0x18006df9c`

## callees

- `0x18006d9b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006d9ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006d9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006d9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006d9d4`

## string_xrefs

- `0x18006d9cd`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[36])
{
  if ( WindowsCreateStringReference(
         L"Windows.System.Threading.ThreadPool",
         0x23u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18006d9b8  push    rbx
0x18006d9ba  sub     rsp, 20h
0x18006d9be  mov     rbx, rcx
0x18006d9c1  lea     r8, [rcx+8]; hstringHeader
0x18006d9c5  mov     r9, rcx; string
0x18006d9c8  mov     edx, 23h ; '#'; length
0x18006d9cd  lea     rcx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x18006d9d4  call    cs:__imp_WindowsCreateStringReference
0x18006d9da  test    eax, eax
0x18006d9dc  jns     short loc_18006D9F3
0x18006d9de  xor     r9d, r9d; lpArguments
0x18006d9e1  xor     r8d, r8d; nNumberOfArguments
0x18006d9e4  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006d9e9  lea     edx, [r9+1]; dwExceptionFlags
0x18006d9ed  call    cs:__imp_RaiseException
0x18006d9f3  mov     rax, rbx
0x18006d9f6  add     rsp, 20h
0x18006d9fa  pop     rbx
0x18006d9fb  retn
```
