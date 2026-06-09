# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180011610`
- end: `0x18001168b`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e664`

## callees

- `0x180011610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011660`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011684`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011660`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001164a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001164a`

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
    JUMPOUT(0x18001168ALL);
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
0x180011610  mov     [rsp+arg_0], rbx
0x180011615  push    rdi
0x180011616  sub     rsp, 20h
0x18001161a  lea     r9, [rcx+18h]; string
0x18001161e  xor     edi, edi
0x180011620  mov     [r9], rdi
0x180011623  mov     rbx, rcx
0x180011626  mov     rcx, [rdx]; sourceString
0x180011629  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001162d  inc     rdx; length
0x180011630  cmp     [rcx+rdx*2], di
0x180011634  jnz     short loc_18001162D
0x180011636  mov     eax, 0FFFFFFFFh
0x18001163b  cmp     rdx, rax
0x18001163e  ja      short loc_180011675
0x180011640  lea     eax, [rdx+1]
0x180011643  cmp     eax, edx
0x180011645  jb      short loc_180011675
0x180011647  mov     r8, rbx; hstringHeader
0x18001164a  call    cs:__imp_WindowsCreateStringReference
0x180011650  test    eax, eax
0x180011652  jns     short loc_180011667
0x180011654  xor     r9d, r9d; lpArguments
0x180011657  xor     r8d, r8d; nNumberOfArguments
0x18001165a  mov     ecx, eax; dwExceptionCode
0x18001165c  lea     edx, [r9+1]; dwExceptionFlags
0x180011660  call    cs:__imp_RaiseException
0x180011666  int     3; Trap to Debugger
0x180011667  mov     rax, rbx
0x18001166a  mov     rbx, [rsp+28h+arg_0]
0x18001166f  add     rsp, 20h
0x180011673  pop     rdi
0x180011674  retn
0x180011675  xor     r9d, r9d; lpArguments
0x180011678  xor     r8d, r8d; nNumberOfArguments
0x18001167b  mov     ecx, 80070216h; dwExceptionCode
0x180011680  lea     edx, [r9+1]; dwExceptionFlags
0x180011684  call    cs:__imp_RaiseException
```
