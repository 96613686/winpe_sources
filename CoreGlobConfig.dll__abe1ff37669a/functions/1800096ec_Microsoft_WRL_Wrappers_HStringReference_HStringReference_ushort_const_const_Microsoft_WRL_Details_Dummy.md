# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800096ec`
- end: `0x180009767`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df9c`
- `0x18000e24c`
- `0x18001250c`
- `0x180014160`

## callees

- `0x1800096ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000973c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009760`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000973c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009726`

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
    JUMPOUT(0x180009766LL);
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
0x1800096ec  mov     [rsp+arg_0], rbx
0x1800096f1  push    rdi
0x1800096f2  sub     rsp, 20h
0x1800096f6  lea     r9, [rcx+18h]; string
0x1800096fa  xor     edi, edi
0x1800096fc  mov     [r9], rdi
0x1800096ff  mov     rbx, rcx
0x180009702  mov     rcx, [rdx]; sourceString
0x180009705  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009709  inc     rdx; length
0x18000970c  cmp     [rcx+rdx*2], di
0x180009710  jnz     short loc_180009709
0x180009712  mov     eax, 0FFFFFFFFh
0x180009717  cmp     rdx, rax
0x18000971a  ja      short loc_180009751
0x18000971c  lea     eax, [rdx+1]
0x18000971f  cmp     eax, edx
0x180009721  jb      short loc_180009751
0x180009723  mov     r8, rbx; hstringHeader
0x180009726  call    cs:__imp_WindowsCreateStringReference
0x18000972c  test    eax, eax
0x18000972e  jns     short loc_180009743
0x180009730  xor     r9d, r9d; lpArguments
0x180009733  xor     r8d, r8d; nNumberOfArguments
0x180009736  mov     ecx, eax; dwExceptionCode
0x180009738  lea     edx, [r9+1]; dwExceptionFlags
0x18000973c  call    cs:__imp_RaiseException
0x180009742  int     3; Trap to Debugger
0x180009743  mov     rax, rbx
0x180009746  mov     rbx, [rsp+28h+arg_0]
0x18000974b  add     rsp, 20h
0x18000974f  pop     rdi
0x180009750  retn
0x180009751  xor     r9d, r9d; lpArguments
0x180009754  xor     r8d, r8d; nNumberOfArguments
0x180009757  mov     ecx, 80070216h; dwExceptionCode
0x18000975c  lea     edx, [r9+1]; dwExceptionFlags
0x180009760  call    cs:__imp_RaiseException
```
