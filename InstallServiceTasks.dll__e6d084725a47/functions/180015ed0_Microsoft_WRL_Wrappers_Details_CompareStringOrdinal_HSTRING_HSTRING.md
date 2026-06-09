# Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)

- ea: `0x180015ed0`
- end: `0x180015f07`
- name: `?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z`
- size: `55`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::Details *__hidden this, HSTRING, HSTRING)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017b80`
- `0x180018a10`
- `0x180027178`

## callees

- `0x180015ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180015ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180015ee1`

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
    JUMPOUT(0x180015F06LL);
  }
  return (unsigned int)result;
}

```

## disassembly

```asm
0x180015ed0  sub     rsp, 28h
0x180015ed4  lea     r8, [rsp+28h+result]; result
0x180015ed9  mov     [rsp+28h+result], 0
0x180015ee1  call    cs:__imp_WindowsCompareStringOrdinal
0x180015ee7  test    eax, eax
0x180015ee9  js      short loc_180015EF4
0x180015eeb  mov     eax, [rsp+28h+result]
0x180015eef  add     rsp, 28h
0x180015ef3  retn
0x180015ef4  xor     r9d, r9d; lpArguments
0x180015ef7  xor     r8d, r8d; nNumberOfArguments
0x180015efa  mov     ecx, eax; dwExceptionCode
0x180015efc  lea     edx, [r9+1]; dwExceptionFlags
0x180015f00  call    cs:__imp_RaiseException
```
