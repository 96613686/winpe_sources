# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18003cc4c`
- end: `0x18003ccc7`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003cb0c`
- `0x18003cbac`

## callees

- `0x18003cc4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003cc9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ccc0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003cc9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ccc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cc86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cc86`

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
    JUMPOUT(0x18003CCC6LL);
  }
  StringReference = WindowsCreateStringReference(v4, v5, a1, v2);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x18003cc4c  mov     [rsp+arg_0], rbx
0x18003cc51  push    rdi
0x18003cc52  sub     rsp, 20h
0x18003cc56  lea     r9, [rcx+18h]; string
0x18003cc5a  xor     edi, edi
0x18003cc5c  mov     [r9], rdi
0x18003cc5f  mov     rbx, rcx
0x18003cc62  mov     rcx, [rdx]; sourceString
0x18003cc65  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003cc69  inc     rdx; length
0x18003cc6c  cmp     [rcx+rdx*2], di
0x18003cc70  jnz     short loc_18003CC69
0x18003cc72  mov     eax, 0FFFFFFFFh
0x18003cc77  cmp     rdx, rax
0x18003cc7a  ja      short loc_18003CCB1
0x18003cc7c  lea     eax, [rdx+1]
0x18003cc7f  cmp     eax, edx
0x18003cc81  jb      short loc_18003CCB1
0x18003cc83  mov     r8, rbx; hstringHeader
0x18003cc86  call    cs:__imp_WindowsCreateStringReference
0x18003cc8c  test    eax, eax
0x18003cc8e  jns     short loc_18003CCA3
0x18003cc90  xor     r9d, r9d; lpArguments
0x18003cc93  xor     r8d, r8d; nNumberOfArguments
0x18003cc96  mov     ecx, eax; dwExceptionCode
0x18003cc98  lea     edx, [r9+1]; dwExceptionFlags
0x18003cc9c  call    cs:__imp_RaiseException
0x18003cca2  int     3; Trap to Debugger
0x18003cca3  mov     rax, rbx
0x18003cca6  mov     rbx, [rsp+28h+arg_0]
0x18003ccab  add     rsp, 20h
0x18003ccaf  pop     rdi
0x18003ccb0  retn
0x18003ccb1  xor     r9d, r9d; lpArguments
0x18003ccb4  xor     r8d, r8d; nNumberOfArguments
0x18003ccb7  mov     ecx, 80070216h; dwExceptionCode
0x18003ccbc  lea     edx, [r9+1]; dwExceptionFlags
0x18003ccc0  call    cs:__imp_RaiseException
```
