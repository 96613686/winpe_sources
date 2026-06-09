# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000842c`
- end: `0x1800084a7`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800097ec`
- `0x1800114fc`
- `0x1800116e4`
- `0x180013afc`
- `0x180018838`
- `0x180018a20`
- `0x180019904`
- `0x18001dfb0`
- `0x18001e198`
- `0x1800209ec`

## callees

- `0x18000842c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000847c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800084a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000847c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800084a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008466`

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
    JUMPOUT(0x1800084A6LL);
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
0x18000842c  mov     [rsp+arg_0], rbx
0x180008431  push    rdi
0x180008432  sub     rsp, 20h
0x180008436  lea     r9, [rcx+18h]; string
0x18000843a  xor     edi, edi
0x18000843c  mov     [r9], rdi
0x18000843f  mov     rbx, rcx
0x180008442  mov     rcx, [rdx]; sourceString
0x180008445  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180008449  inc     rdx; length
0x18000844c  cmp     [rcx+rdx*2], di
0x180008450  jnz     short loc_180008449
0x180008452  mov     eax, 0FFFFFFFFh
0x180008457  cmp     rdx, rax
0x18000845a  ja      short loc_180008491
0x18000845c  lea     eax, [rdx+1]
0x18000845f  cmp     eax, edx
0x180008461  jb      short loc_180008491
0x180008463  mov     r8, rbx; hstringHeader
0x180008466  call    cs:__imp_WindowsCreateStringReference
0x18000846c  test    eax, eax
0x18000846e  jns     short loc_180008483
0x180008470  xor     r9d, r9d; lpArguments
0x180008473  xor     r8d, r8d; nNumberOfArguments
0x180008476  mov     ecx, eax; dwExceptionCode
0x180008478  lea     edx, [r9+1]; dwExceptionFlags
0x18000847c  call    cs:__imp_RaiseException
0x180008482  int     3; Trap to Debugger
0x180008483  mov     rax, rbx
0x180008486  mov     rbx, [rsp+28h+arg_0]
0x18000848b  add     rsp, 20h
0x18000848f  pop     rdi
0x180008490  retn
0x180008491  xor     r9d, r9d; lpArguments
0x180008494  xor     r8d, r8d; nNumberOfArguments
0x180008497  mov     ecx, 80070216h; dwExceptionCode
0x18000849c  lea     edx, [r9+1]; dwExceptionFlags
0x1800084a0  call    cs:__imp_RaiseException
```
