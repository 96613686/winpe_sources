# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000f9f0`
- end: `0x18000fa6b`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013c90`

## callees

- `0x18000f9f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fa2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fa2a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fa40`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fa64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fa40`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fa64`

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
    JUMPOUT(0x18000FA6ALL);
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
0x18000f9f0  mov     [rsp+arg_0], rbx
0x18000f9f5  push    rdi
0x18000f9f6  sub     rsp, 20h
0x18000f9fa  lea     r9, [rcx+18h]; string
0x18000f9fe  xor     edi, edi
0x18000fa00  mov     [r9], rdi
0x18000fa03  mov     rbx, rcx
0x18000fa06  mov     rcx, [rdx]; sourceString
0x18000fa09  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fa0d  inc     rdx; length
0x18000fa10  cmp     [rcx+rdx*2], di
0x18000fa14  jnz     short loc_18000FA0D
0x18000fa16  mov     eax, 0FFFFFFFFh
0x18000fa1b  cmp     rdx, rax
0x18000fa1e  ja      short loc_18000FA55
0x18000fa20  lea     eax, [rdx+1]
0x18000fa23  cmp     eax, edx
0x18000fa25  jb      short loc_18000FA55
0x18000fa27  mov     r8, rbx; hstringHeader
0x18000fa2a  call    cs:__imp_WindowsCreateStringReference
0x18000fa30  test    eax, eax
0x18000fa32  jns     short loc_18000FA47
0x18000fa34  xor     r9d, r9d; lpArguments
0x18000fa37  xor     r8d, r8d; nNumberOfArguments
0x18000fa3a  mov     ecx, eax; dwExceptionCode
0x18000fa3c  lea     edx, [r9+1]; dwExceptionFlags
0x18000fa40  call    cs:__imp_RaiseException
0x18000fa46  int     3; Trap to Debugger
0x18000fa47  mov     rax, rbx
0x18000fa4a  mov     rbx, [rsp+28h+arg_0]
0x18000fa4f  add     rsp, 20h
0x18000fa53  pop     rdi
0x18000fa54  retn
0x18000fa55  xor     r9d, r9d; lpArguments
0x18000fa58  xor     r8d, r8d; nNumberOfArguments
0x18000fa5b  mov     ecx, 80070216h; dwExceptionCode
0x18000fa60  lea     edx, [r9+1]; dwExceptionFlags
0x18000fa64  call    cs:__imp_RaiseException
```
