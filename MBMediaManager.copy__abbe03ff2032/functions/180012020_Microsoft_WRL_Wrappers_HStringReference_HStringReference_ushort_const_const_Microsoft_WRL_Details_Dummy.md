# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180012020`
- end: `0x18001209c`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038ce4`

## callees

- `0x180012020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001206b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012095`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001206b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012075`

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
    JUMPOUT(0x18001209BLL);
  }
  return a1;
}

```

## disassembly

```asm
0x180012020  push    rbx
0x180012022  sub     rsp, 20h
0x180012026  lea     r9, [rcx+18h]; string
0x18001202a  mov     rbx, rcx
0x18001202d  mov     qword ptr [r9], 0
0x180012034  mov     rcx, [rdx]; sourceString
0x180012037  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001203e  xchg    ax, ax
0x180012040  inc     rdx; length
0x180012043  cmp     word ptr [rcx+rdx*2], 0
0x180012048  jnz     short loc_180012040
0x18001204a  mov     eax, 0FFFFFFFFh
0x18001204f  cmp     rdx, rax
0x180012052  ja      short loc_18001205B
0x180012054  lea     eax, [rdx+1]
0x180012057  cmp     eax, edx
0x180012059  jnb     short loc_180012072
0x18001205b  xor     r9d, r9d; lpArguments
0x18001205e  xor     r8d, r8d; nNumberOfArguments
0x180012061  mov     edx, 1; dwExceptionFlags
0x180012066  mov     ecx, 80070216h; dwExceptionCode
0x18001206b  call    cs:__imp_RaiseException
0x180012071  int     3; Trap to Debugger
0x180012072  mov     r8, rbx; hstringHeader
0x180012075  call    cs:__imp_WindowsCreateStringReference
0x18001207b  test    eax, eax
0x18001207d  js      short loc_180012088
0x18001207f  mov     rax, rbx
0x180012082  add     rsp, 20h
0x180012086  pop     rbx
0x180012087  retn
0x180012088  xor     r9d, r9d; lpArguments
0x18001208b  xor     r8d, r8d; nNumberOfArguments
0x18001208e  mov     edx, 1; dwExceptionFlags
0x180012093  mov     ecx, eax; dwExceptionCode
0x180012095  call    cs:__imp_RaiseException
```
