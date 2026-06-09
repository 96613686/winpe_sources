# Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)

- ea: `0x180020e1c`
- end: `0x180020e53`
- name: `?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z`
- size: `55`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::Details *__hidden this, HSTRING, HSTRING)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800245c0`
- `0x180028780`

## callees

- `0x180020e1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020e4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180020e2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180020e2d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
        Microsoft::WRL::Wrappers::Details *this,
        HSTRING a2,
        HSTRING a3)
{
  HRESULT v3; // eax
  INT32 result; // [rsp+40h] [rbp+18h] BYREF

  result = 0;
  v3 = WindowsCompareStringOrdinal((HSTRING)this, a2, &result);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    JUMPOUT(0x180020E52LL);
  }
  return (unsigned int)result;
}

```

## disassembly

```asm
0x180020e1c  sub     rsp, 28h
0x180020e20  lea     r8, [rsp+28h+result]; result
0x180020e25  mov     [rsp+28h+result], 0
0x180020e2d  call    cs:__imp_WindowsCompareStringOrdinal
0x180020e33  test    eax, eax
0x180020e35  js      short loc_180020E40
0x180020e37  mov     eax, [rsp+28h+result]
0x180020e3b  add     rsp, 28h
0x180020e3f  retn
0x180020e40  xor     r9d, r9d; lpArguments
0x180020e43  xor     r8d, r8d; nNumberOfArguments
0x180020e46  mov     ecx, eax; dwExceptionCode
0x180020e48  lea     edx, [r9+1]; dwExceptionFlags
0x180020e4c  call    cs:__imp_RaiseException
```
