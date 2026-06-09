# Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)

- ea: `0x18000e5f0`
- end: `0x18000e627`
- name: `?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z`
- size: `55`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::Details *__hidden this, HSTRING, HSTRING)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e4f0`
- `0x180013210`
- `0x18001667c`
- `0x18002694c`
- `0x180028804`
- `0x18005f214`

## callees

- `0x18000e5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e620`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000e601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000e601`

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
    JUMPOUT(0x18000E626LL);
  }
  return (unsigned int)result;
}

```

## disassembly

```asm
0x18000e5f0  sub     rsp, 28h
0x18000e5f4  lea     r8, [rsp+28h+result]; result
0x18000e5f9  mov     [rsp+28h+result], 0
0x18000e601  call    cs:__imp_WindowsCompareStringOrdinal
0x18000e607  test    eax, eax
0x18000e609  js      short loc_18000E614
0x18000e60b  mov     eax, [rsp+28h+result]
0x18000e60f  add     rsp, 28h
0x18000e613  retn
0x18000e614  xor     r9d, r9d; lpArguments
0x18000e617  xor     r8d, r8d; nNumberOfArguments
0x18000e61a  mov     ecx, eax; dwExceptionCode
0x18000e61c  lea     edx, [r9+1]; dwExceptionFlags
0x18000e620  call    cs:__imp_RaiseException
```
