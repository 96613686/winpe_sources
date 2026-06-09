# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800d2d14`
- end: `0x1800d2dda`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800d2b8c`

## callees

- `0x180039480`
- `0x1800d2d14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2d5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2d86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2db9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2d5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2d86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d2db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d2d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d2d9d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(__int64 a1, __int64 *a2, char a3)
{
  ULONGLONG v4; // rcx
  __int64 v5; // r11
  HRESULT v6; // eax
  const WCHAR *v7; // r11
  UINT32 v8; // edx
  HRESULT StringReference; // eax
  UINT puResult; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(puResult) = a3;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = -1;
  v5 = *a2;
  puResult = 0;
  do
    ++v4;
  while ( *(_WORD *)(v5 + 2 * v4) );
  v6 = ULongLongToUInt(v4, &puResult);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v8 = puResult;
  if ( puResult + 1 < puResult )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v7, v8, (HSTRING_HEADER *)a1, (HSTRING *)(a1 + 24));
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
0x1800d2d14  mov     rax, rsp
0x1800d2d17  mov     [rax+8], rbx
0x1800d2d1b  mov     [rax+10h], rsi
0x1800d2d1f  mov     [rax+18h], r8b
0x1800d2d23  push    rdi
0x1800d2d24  sub     rsp, 20h
0x1800d2d28  xor     esi, esi
0x1800d2d2a  mov     rbx, rcx
0x1800d2d2d  mov     [rcx+18h], rsi
0x1800d2d31  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d2d35  mov     r11, [rdx]
0x1800d2d38  mov     [rax+18h], esi
0x1800d2d3b  inc     rcx; ullOperand
0x1800d2d3e  cmp     [r11+rcx*2], si
0x1800d2d43  jnz     short loc_1800D2D3B
0x1800d2d45  lea     rdx, [rsp+28h+puResult]; puResult
0x1800d2d4a  call    ULongLongToUInt
0x1800d2d4f  test    eax, eax
0x1800d2d51  jns     short loc_1800D2D6C
0x1800d2d53  xor     r9d, r9d; lpArguments
0x1800d2d56  xor     r8d, r8d; nNumberOfArguments
0x1800d2d59  mov     ecx, eax; dwExceptionCode
0x1800d2d5b  lea     edx, [r9+1]; dwExceptionFlags
0x1800d2d5f  call    cs:__imp_RaiseException
0x1800d2d66  nop     dword ptr [rax+rax+00h]
0x1800d2d6b  int     3; Trap to Debugger
0x1800d2d6c  mov     edx, [rsp+28h+puResult]
0x1800d2d70  lea     eax, [rdx+1]
0x1800d2d73  cmp     eax, edx
0x1800d2d75  jnb     short loc_1800D2D93
0x1800d2d77  xor     r9d, r9d; lpArguments
0x1800d2d7a  xor     r8d, r8d; nNumberOfArguments
0x1800d2d7d  mov     ecx, 80070216h; dwExceptionCode
0x1800d2d82  lea     edx, [r9+1]; dwExceptionFlags
0x1800d2d86  call    cs:__imp_RaiseException
0x1800d2d8d  nop     dword ptr [rax+rax+00h]
0x1800d2d92  int     3; Trap to Debugger
0x1800d2d93  lea     r9, [rbx+18h]; string
0x1800d2d97  mov     r8, rbx; hstringHeader
0x1800d2d9a  mov     rcx, r11; sourceString
0x1800d2d9d  call    cs:__imp_WindowsCreateStringReference
0x1800d2da4  nop     dword ptr [rax+rax+00h]
0x1800d2da9  test    eax, eax
0x1800d2dab  jns     short loc_1800D2DC6
0x1800d2dad  xor     r9d, r9d; lpArguments
0x1800d2db0  xor     r8d, r8d; nNumberOfArguments
0x1800d2db3  mov     ecx, eax; dwExceptionCode
0x1800d2db5  lea     edx, [r9+1]; dwExceptionFlags
0x1800d2db9  call    cs:__imp_RaiseException
0x1800d2dc0  nop     dword ptr [rax+rax+00h]
0x1800d2dc5  int     3; Trap to Debugger
0x1800d2dc6  mov     rsi, [rsp+28h+arg_8]
0x1800d2dcb  mov     rax, rbx
0x1800d2dce  mov     rbx, [rsp+28h+arg_0]
0x1800d2dd3  add     rsp, 20h
0x1800d2dd7  pop     rdi
0x1800d2dd8  retn
```
