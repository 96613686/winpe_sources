# Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180009388`
- end: `0x180009403`
- name: `??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z`
- size: `123`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012abc`
- `0x180012ca4`
- `0x180012e8c`
- `0x180013074`
- `0x18001325c`
- `0x180013454`
- `0x18001363c`
- `0x180013824`
- `0x180013aa4`
- `0x180013d24`
- `0x180013fa4`
- `0x180014224`
- `0x1800144b8`
- `0x180014738`
- `0x1800149b8`
- `0x18001c7c8`
- `0x18001c934`
- `0x18001caa0`
- `0x18001cc0c`
- `0x18001cd78`
- `0x18001cee4`
- `0x18001d09c`
- `0x18001ec28`
- `0x18001f1f0`

## callees

- `0x180009388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800093d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800093fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800093d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800093fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800093c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800093c2`

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
    JUMPOUT(0x180009402LL);
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
0x180009388  mov     [rsp+arg_0], rbx
0x18000938d  push    rdi
0x18000938e  sub     rsp, 20h
0x180009392  lea     r9, [rcx+18h]; string
0x180009396  xor     edi, edi
0x180009398  mov     [r9], rdi
0x18000939b  mov     rbx, rcx
0x18000939e  mov     rcx, [rdx]; sourceString
0x1800093a1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800093a5  inc     rdx; length
0x1800093a8  cmp     [rcx+rdx*2], di
0x1800093ac  jnz     short loc_1800093A5
0x1800093ae  mov     eax, 0FFFFFFFFh
0x1800093b3  cmp     rdx, rax
0x1800093b6  ja      short loc_1800093ED
0x1800093b8  lea     eax, [rdx+1]
0x1800093bb  cmp     eax, edx
0x1800093bd  jb      short loc_1800093ED
0x1800093bf  mov     r8, rbx; hstringHeader
0x1800093c2  call    cs:__imp_WindowsCreateStringReference
0x1800093c8  test    eax, eax
0x1800093ca  jns     short loc_1800093DF
0x1800093cc  xor     r9d, r9d; lpArguments
0x1800093cf  xor     r8d, r8d; nNumberOfArguments
0x1800093d2  mov     ecx, eax; dwExceptionCode
0x1800093d4  lea     edx, [r9+1]; dwExceptionFlags
0x1800093d8  call    cs:__imp_RaiseException
0x1800093de  int     3; Trap to Debugger
0x1800093df  mov     rax, rbx
0x1800093e2  mov     rbx, [rsp+28h+arg_0]
0x1800093e7  add     rsp, 20h
0x1800093eb  pop     rdi
0x1800093ec  retn
0x1800093ed  xor     r9d, r9d; lpArguments
0x1800093f0  xor     r8d, r8d; nNumberOfArguments
0x1800093f3  mov     ecx, 80070216h; dwExceptionCode
0x1800093f8  lea     edx, [r9+1]; dwExceptionFlags
0x1800093fc  call    cs:__imp_RaiseException
```
