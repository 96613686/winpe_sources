# Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)

- ea: `0x18002c520`
- end: `0x18002c557`
- name: `?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z`
- size: `55`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::Details *__hidden this, HSTRING, HSTRING)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002bb4c`
- `0x180036f90`
- `0x1800462a0`
- `0x18004640c`

## callees

- `0x18002c520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c550`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18002c531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18002c531`

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
    JUMPOUT(0x18002C556LL);
  }
  return (unsigned int)result;
}

```

## disassembly

```asm
0x18002c520  sub     rsp, 28h
0x18002c524  lea     r8, [rsp+28h+result]; result
0x18002c529  mov     [rsp+28h+result], 0
0x18002c531  call    cs:__imp_WindowsCompareStringOrdinal
0x18002c537  test    eax, eax
0x18002c539  js      short loc_18002C544
0x18002c53b  mov     eax, [rsp+28h+result]
0x18002c53f  add     rsp, 28h
0x18002c543  retn
0x18002c544  xor     r9d, r9d; lpArguments
0x18002c547  xor     r8d, r8d; nNumberOfArguments
0x18002c54a  mov     ecx, eax; dwExceptionCode
0x18002c54c  lea     edx, [r9+1]; dwExceptionFlags
0x18002c550  call    cs:__imp_RaiseException
```
