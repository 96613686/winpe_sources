# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18002c218`
- end: `0x18002c2b7`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, const WCHAR **, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c40c`
- `0x18003d7a4`

## callees

- `0x18001f11c`
- `0x18002c218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c25c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c27d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c2a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c25c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c27d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c2a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c28e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c28e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(__int64 a1, const WCHAR **a2, char a3)
{
  unsigned __int64 v4; // rcx
  const WCHAR *v5; // rdi
  signed int v6; // eax
  HRESULT StringReference; // eax
  UINT32 length; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(length) = a3;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = -1;
  v5 = *a2;
  length = 0;
  do
    ++v4;
  while ( v5[v4] );
  v6 = ULongLongToUInt(v4, &length);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  if ( length + 1 < length )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v5, length, (HSTRING_HEADER *)a1, (HSTRING *)(a1 + 24));
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
0x18002c218  mov     byte ptr [rsp+length], r8b
0x18002c21d  push    rbx
0x18002c21e  push    rbp
0x18002c21f  push    rsi
0x18002c220  push    rdi
0x18002c221  sub     rsp, 28h
0x18002c225  xor     ebp, ebp
0x18002c227  mov     rbx, rcx
0x18002c22a  mov     [rcx+18h], rbp
0x18002c22e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c232  mov     rdi, [rdx]
0x18002c235  mov     [rsp+48h+length], ebp
0x18002c239  inc     rcx; unsigned __int64
0x18002c23c  cmp     [rdi+rcx*2], bp
0x18002c240  jnz     short loc_18002C239
0x18002c242  lea     rdx, [rsp+48h+length]; unsigned int *
0x18002c247  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18002c24c  test    eax, eax
0x18002c24e  jns     short loc_18002C263
0x18002c250  xor     r9d, r9d; lpArguments
0x18002c253  xor     r8d, r8d; nNumberOfArguments
0x18002c256  mov     ecx, eax; dwExceptionCode
0x18002c258  lea     edx, [r9+1]; dwExceptionFlags
0x18002c25c  call    cs:__imp_RaiseException
0x18002c262  int     3; Trap to Debugger
0x18002c263  mov     edx, [rsp+48h+length]; length
0x18002c267  lea     eax, [rdx+1]
0x18002c26a  cmp     eax, edx
0x18002c26c  jnb     short loc_18002C284
0x18002c26e  xor     r9d, r9d; lpArguments
0x18002c271  xor     r8d, r8d; nNumberOfArguments
0x18002c274  mov     ecx, 80070216h; dwExceptionCode
0x18002c279  lea     edx, [r9+1]; dwExceptionFlags
0x18002c27d  call    cs:__imp_RaiseException
0x18002c283  int     3; Trap to Debugger
0x18002c284  lea     r9, [rbx+18h]; string
0x18002c288  mov     r8, rbx; hstringHeader
0x18002c28b  mov     rcx, rdi; sourceString
0x18002c28e  call    cs:__imp_WindowsCreateStringReference
0x18002c294  test    eax, eax
0x18002c296  jns     short loc_18002C2AB
0x18002c298  xor     r9d, r9d; lpArguments
0x18002c29b  xor     r8d, r8d; nNumberOfArguments
0x18002c29e  mov     ecx, eax; dwExceptionCode
0x18002c2a0  lea     edx, [r9+1]; dwExceptionFlags
0x18002c2a4  call    cs:__imp_RaiseException
0x18002c2aa  int     3; Trap to Debugger
0x18002c2ab  mov     rax, rbx
0x18002c2ae  add     rsp, 28h
0x18002c2b2  pop     rdi
0x18002c2b3  pop     rsi
0x18002c2b4  pop     rbp
0x18002c2b5  pop     rbx
0x18002c2b6  retn
```
