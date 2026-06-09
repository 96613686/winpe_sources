# Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HStringReference const &)

- ea: `0x180042b58`
- end: `0x180042b9a`
- name: `??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@AEBVHStringReference@012@@Z`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004a1bc`

## callees

- `0x180042b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042b93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180042b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180042b70`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Wrappers::operator==(HSTRING *a1, __int64 a2)
{
  HSTRING v2; // rdx
  HSTRING v3; // rcx
  HRESULT v4; // eax
  INT32 result; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(HSTRING *)(a2 + 24);
  v3 = *a1;
  result = 0;
  v4 = WindowsCompareStringOrdinal(v3, v2, &result);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    JUMPOUT(0x180042B99LL);
  }
  return result == 0;
}

```

## disassembly

```asm
0x180042b58  sub     rsp, 28h
0x180042b5c  mov     rdx, [rdx+18h]; string2
0x180042b60  lea     r8, [rsp+28h+result]; result
0x180042b65  mov     rcx, [rcx]; string1
0x180042b68  mov     [rsp+28h+result], 0
0x180042b70  call    cs:__imp_WindowsCompareStringOrdinal
0x180042b76  test    eax, eax
0x180042b78  js      short loc_180042B87
0x180042b7a  cmp     [rsp+28h+result], 0
0x180042b7f  setz    al
0x180042b82  add     rsp, 28h
0x180042b86  retn
0x180042b87  xor     r9d, r9d; lpArguments
0x180042b8a  xor     r8d, r8d; nNumberOfArguments
0x180042b8d  mov     ecx, eax; dwExceptionCode
0x180042b8f  lea     edx, [r9+1]; dwExceptionFlags
0x180042b93  call    cs:__imp_RaiseException
```
