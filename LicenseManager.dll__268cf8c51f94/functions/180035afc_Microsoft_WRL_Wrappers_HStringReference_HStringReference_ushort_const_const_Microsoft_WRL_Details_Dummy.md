# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180035afc`
- end: `0x180035b77`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180059460`
- `0x18006c288`
- `0x180074b30`
- `0x180074ec8`
- `0x18009f05c`
- `0x18009f15c`

## callees

- `0x180035afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035b42`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035b70`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035b42`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035b4c`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  HSTRING *v2; // r9
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdx
  HRESULT StringReference; // eax

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
    JUMPOUT(0x180035B76LL);
  }
  return a1;
}

```

## disassembly

```asm
0x180035afc  mov     [rsp+arg_0], rbx
0x180035b01  push    rdi
0x180035b02  sub     rsp, 20h
0x180035b06  lea     r9, [rcx+18h]; string
0x180035b0a  xor     edi, edi
0x180035b0c  mov     [r9], rdi
0x180035b0f  mov     rbx, rcx
0x180035b12  mov     rcx, [rdx]; sourceString
0x180035b15  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035b19  inc     rdx; length
0x180035b1c  cmp     [rcx+rdx*2], di
0x180035b20  jnz     short loc_180035B19
0x180035b22  mov     eax, 0FFFFFFFFh
0x180035b27  cmp     rdx, rax
0x180035b2a  ja      short loc_180035B33
0x180035b2c  lea     eax, [rdx+1]
0x180035b2f  cmp     eax, edx
0x180035b31  jnb     short loc_180035B49
0x180035b33  xor     r9d, r9d; lpArguments
0x180035b36  xor     r8d, r8d; nNumberOfArguments
0x180035b39  mov     ecx, 80070216h; dwExceptionCode
0x180035b3e  lea     edx, [r9+1]; dwExceptionFlags
0x180035b42  call    cs:__imp_RaiseException
0x180035b48  int     3; Trap to Debugger
0x180035b49  mov     r8, rbx; hstringHeader
0x180035b4c  call    cs:__imp_WindowsCreateStringReference
0x180035b52  test    eax, eax
0x180035b54  js      short loc_180035B64
0x180035b56  mov     rax, rbx
0x180035b59  mov     rbx, [rsp+28h+arg_0]
0x180035b5e  add     rsp, 20h
0x180035b62  pop     rdi
0x180035b63  retn
0x180035b64  xor     r9d, r9d; lpArguments
0x180035b67  xor     r8d, r8d; nNumberOfArguments
0x180035b6a  mov     ecx, eax; dwExceptionCode
0x180035b6c  lea     edx, [r9+1]; dwExceptionFlags
0x180035b70  call    cs:__imp_RaiseException
```
