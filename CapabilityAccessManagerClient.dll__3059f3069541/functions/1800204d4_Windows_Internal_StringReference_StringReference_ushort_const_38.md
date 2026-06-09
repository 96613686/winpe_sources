# Windows::Internal::StringReference::StringReference(ushort const (&)[38])

- ea: `0x1800204d4`
- end: `0x180020518`
- name: `??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[38])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022a4c`

## callees

- `0x1800204d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020509`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800204f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800204f0`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[38])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.User",
         0x25u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800204d4  push    rbx
0x1800204d6  sub     rsp, 20h
0x1800204da  mov     rbx, rcx
0x1800204dd  lea     r8, [rcx+8]; hstringHeader
0x1800204e1  mov     r9, rcx; string
0x1800204e4  mov     edx, 25h ; '%'; length
0x1800204e9  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x1800204f0  call    cs:__imp_WindowsCreateStringReference
0x1800204f6  test    eax, eax
0x1800204f8  jns     short loc_18002050F
0x1800204fa  xor     r9d, r9d; lpArguments
0x1800204fd  xor     r8d, r8d; nNumberOfArguments
0x180020500  mov     ecx, 0C000000Dh; dwExceptionCode
0x180020505  lea     edx, [r9+1]; dwExceptionFlags
0x180020509  call    cs:__imp_RaiseException
0x18002050f  mov     rax, rbx
0x180020512  add     rsp, 20h
0x180020516  pop     rbx
0x180020517  retn
```
