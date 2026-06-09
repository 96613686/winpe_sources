# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800533e4`
- end: `0x18005345f`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036dc0`
- `0x1800530f8`
- `0x18006e7d0`
- `0x1800a979c`
- `0x1800a9878`
- `0x1800ac340`

## callees

- `0x1800533e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005342a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053458`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005342a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053434`

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
    JUMPOUT(0x18005345ELL);
  }
  return a1;
}

```

## disassembly

```asm
0x1800533e4  mov     [rsp+arg_0], rbx
0x1800533e9  push    rdi
0x1800533ea  sub     rsp, 20h
0x1800533ee  lea     r9, [rcx+18h]; string
0x1800533f2  xor     edi, edi
0x1800533f4  mov     [r9], rdi
0x1800533f7  mov     rbx, rcx
0x1800533fa  mov     rcx, [rdx]; sourceString
0x1800533fd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053401  inc     rdx; length
0x180053404  cmp     [rcx+rdx*2], di
0x180053408  jnz     short loc_180053401
0x18005340a  mov     eax, 0FFFFFFFFh
0x18005340f  cmp     rdx, rax
0x180053412  ja      short loc_18005341B
0x180053414  lea     eax, [rdx+1]
0x180053417  cmp     eax, edx
0x180053419  jnb     short loc_180053431
0x18005341b  xor     r9d, r9d; lpArguments
0x18005341e  xor     r8d, r8d; nNumberOfArguments
0x180053421  mov     ecx, 80070216h; dwExceptionCode
0x180053426  lea     edx, [r9+1]; dwExceptionFlags
0x18005342a  call    cs:__imp_RaiseException
0x180053430  int     3; Trap to Debugger
0x180053431  mov     r8, rbx; hstringHeader
0x180053434  call    cs:__imp_WindowsCreateStringReference
0x18005343a  test    eax, eax
0x18005343c  js      short loc_18005344C
0x18005343e  mov     rax, rbx
0x180053441  mov     rbx, [rsp+28h+arg_0]
0x180053446  add     rsp, 20h
0x18005344a  pop     rdi
0x18005344b  retn
0x18005344c  xor     r9d, r9d; lpArguments
0x18005344f  xor     r8d, r8d; nNumberOfArguments
0x180053452  mov     ecx, eax; dwExceptionCode
0x180053454  lea     edx, [r9+1]; dwExceptionFlags
0x180053458  call    cs:__imp_RaiseException
```
