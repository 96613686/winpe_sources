# Windows::Internal::StringReference::StringReference(ushort const (&)[37])

- ea: `0x180044610`
- end: `0x180044661`
- name: `??$?0$0CF@@StringReference@Internal@Windows@@QEAA@AEAY0CF@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[37])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x180044610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004464b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004464b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004462c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004462c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[37])
{
  if ( WindowsCreateStringReference(
         L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
         0x24u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180044610  push    rbx
0x180044612  sub     rsp, 20h
0x180044616  mov     rbx, rcx
0x180044619  lea     r8, [rcx+8]; hstringHeader
0x18004461d  mov     r9, rcx; string
0x180044620  mov     edx, 24h ; '$'; length
0x180044625  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x18004462c  call    cs:__imp_WindowsCreateStringReference
0x180044633  nop     dword ptr [rax+rax+00h]
0x180044638  test    eax, eax
0x18004463a  jns     short loc_180044657
0x18004463c  xor     r9d, r9d; lpArguments
0x18004463f  xor     r8d, r8d; nNumberOfArguments
0x180044642  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044647  lea     edx, [r9+1]; dwExceptionFlags
0x18004464b  call    cs:__imp_RaiseException
0x180044652  nop     dword ptr [rax+rax+00h]
0x180044657  mov     rax, rbx
0x18004465a  add     rsp, 20h
0x18004465e  pop     rbx
0x18004465f  retn
```
