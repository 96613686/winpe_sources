# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000d700`
- end: `0x18000d77c`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `124`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025df4`
- `0x18002607c`
- `0x18002d124`
- `0x18003019c`
- `0x180035be4`
- `0x180035f68`

## callees

- `0x18000d700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d74b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d775`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d74b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d755`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  HSTRING *v2; // r9
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdx
  signed int StringReference; // eax

  v2 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v4 = *a2;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  if ( v5 > 0xFFFFFFFF || (int)v5 + 1 < (unsigned int)v5 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v4, v5, a1, v2);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x18000D77BLL);
  }
  return a1;
}

```

## disassembly

```asm
0x18000d700  push    rbx
0x18000d702  sub     rsp, 20h
0x18000d706  lea     r9, [rcx+18h]; string
0x18000d70a  mov     rbx, rcx
0x18000d70d  mov     qword ptr [r9], 0
0x18000d714  mov     rcx, [rdx]; sourceString
0x18000d717  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000d71e  xchg    ax, ax
0x18000d720  inc     rdx; length
0x18000d723  cmp     word ptr [rcx+rdx*2], 0
0x18000d728  jnz     short loc_18000D720
0x18000d72a  mov     eax, 0FFFFFFFFh
0x18000d72f  cmp     rdx, rax
0x18000d732  ja      short loc_18000D73B
0x18000d734  lea     eax, [rdx+1]
0x18000d737  cmp     eax, edx
0x18000d739  jnb     short loc_18000D752
0x18000d73b  xor     r9d, r9d; lpArguments
0x18000d73e  xor     r8d, r8d; nNumberOfArguments
0x18000d741  mov     edx, 1; dwExceptionFlags
0x18000d746  mov     ecx, 80070216h; dwExceptionCode
0x18000d74b  call    cs:__imp_RaiseException
0x18000d751  int     3; Trap to Debugger
0x18000d752  mov     r8, rbx; hstringHeader
0x18000d755  call    cs:__imp_WindowsCreateStringReference
0x18000d75b  test    eax, eax
0x18000d75d  js      short loc_18000D768
0x18000d75f  mov     rax, rbx
0x18000d762  add     rsp, 20h
0x18000d766  pop     rbx
0x18000d767  retn
0x18000d768  xor     r9d, r9d; lpArguments
0x18000d76b  xor     r8d, r8d; nNumberOfArguments
0x18000d76e  mov     edx, 1; dwExceptionFlags
0x18000d773  mov     ecx, eax; dwExceptionCode
0x18000d775  call    cs:__imp_RaiseException
```
