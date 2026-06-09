# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180005c10`
- end: `0x180005c8b`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f558`
- `0x180025cd4`
- `0x180025d8c`
- `0x180025e44`
- `0x180025efc`
- `0x18002eec8`
- `0x18002ef80`
- `0x18002f038`
- `0x18002f0f0`
- `0x18002f1a8`
- `0x18002f260`
- `0x180031a88`
- `0x180031b40`
- `0x1800350c4`
- `0x18003517c`
- `0x180035234`
- `0x1800352ec`
- `0x1800353a4`

## callees

- `0x180005c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005c60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005c84`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005c60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005c84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005c4a`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  HSTRING *v2; // r9
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdx
  signed int StringReference; // eax

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
    JUMPOUT(0x180005C8ALL);
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
0x180005c10  mov     [rsp+arg_0], rbx
0x180005c15  push    rdi
0x180005c16  sub     rsp, 20h
0x180005c1a  lea     r9, [rcx+18h]; string
0x180005c1e  xor     edi, edi
0x180005c20  mov     [r9], rdi
0x180005c23  mov     rbx, rcx
0x180005c26  mov     rcx, [rdx]; sourceString
0x180005c29  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005c2d  inc     rdx; length
0x180005c30  cmp     [rcx+rdx*2], di
0x180005c34  jnz     short loc_180005C2D
0x180005c36  mov     eax, 0FFFFFFFFh
0x180005c3b  cmp     rdx, rax
0x180005c3e  ja      short loc_180005C75
0x180005c40  lea     eax, [rdx+1]
0x180005c43  cmp     eax, edx
0x180005c45  jb      short loc_180005C75
0x180005c47  mov     r8, rbx; hstringHeader
0x180005c4a  call    cs:__imp_WindowsCreateStringReference
0x180005c50  test    eax, eax
0x180005c52  jns     short loc_180005C67
0x180005c54  xor     r9d, r9d; lpArguments
0x180005c57  xor     r8d, r8d; nNumberOfArguments
0x180005c5a  mov     ecx, eax; dwExceptionCode
0x180005c5c  lea     edx, [r9+1]; dwExceptionFlags
0x180005c60  call    cs:__imp_RaiseException
0x180005c66  int     3; Trap to Debugger
0x180005c67  mov     rax, rbx
0x180005c6a  mov     rbx, [rsp+28h+arg_0]
0x180005c6f  add     rsp, 20h
0x180005c73  pop     rdi
0x180005c74  retn
0x180005c75  xor     r9d, r9d; lpArguments
0x180005c78  xor     r8d, r8d; nNumberOfArguments
0x180005c7b  mov     ecx, 80070216h; dwExceptionCode
0x180005c80  lea     edx, [r9+1]; dwExceptionFlags
0x180005c84  call    cs:__imp_RaiseException
```
