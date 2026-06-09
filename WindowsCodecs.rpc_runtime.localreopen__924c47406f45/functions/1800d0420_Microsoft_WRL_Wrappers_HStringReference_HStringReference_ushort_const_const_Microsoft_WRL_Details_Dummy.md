# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800d0420`
- end: `0x1800d04cd`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800d02ac`

## callees

- `0x18006ac40`
- `0x1800d0420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d046b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d048c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d04b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d046b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d048c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d04b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d049d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d049d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(__int64 a1, __int64 *a2, char a3)
{
  ULONGLONG v4; // rcx
  __int64 v5; // r11
  HRESULT v6; // eax
  const WCHAR *v7; // r11
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
  if ( puResult + 1 < puResult )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v7, puResult, (HSTRING_HEADER *)a1, (HSTRING *)(a1 + 24));
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
0x1800d0420  mov     rax, rsp
0x1800d0423  mov     [rax+8], rbx
0x1800d0427  mov     [rax+10h], rsi
0x1800d042b  mov     [rax+18h], r8b
0x1800d042f  push    rdi
0x1800d0430  sub     rsp, 20h
0x1800d0434  xor     esi, esi
0x1800d0436  mov     rbx, rcx
0x1800d0439  mov     [rcx+18h], rsi
0x1800d043d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d0441  mov     r11, [rdx]
0x1800d0444  mov     [rax+18h], esi
0x1800d0447  inc     rcx; ullOperand
0x1800d044a  cmp     [r11+rcx*2], si
0x1800d044f  jnz     short loc_1800D0447
0x1800d0451  lea     rdx, [rsp+28h+puResult]; puResult
0x1800d0456  call    ULongLongToUInt
0x1800d045b  test    eax, eax
0x1800d045d  jns     short loc_1800D0472
0x1800d045f  xor     r9d, r9d; lpArguments
0x1800d0462  xor     r8d, r8d; nNumberOfArguments
0x1800d0465  mov     ecx, eax; dwExceptionCode
0x1800d0467  lea     edx, [r9+1]; dwExceptionFlags
0x1800d046b  call    cs:__imp_RaiseException
0x1800d0471  int     3; Trap to Debugger
0x1800d0472  mov     edx, [rsp+28h+puResult]; length
0x1800d0476  lea     eax, [rdx+1]
0x1800d0479  cmp     eax, edx
0x1800d047b  jnb     short loc_1800D0493
0x1800d047d  xor     r9d, r9d; lpArguments
0x1800d0480  xor     r8d, r8d; nNumberOfArguments
0x1800d0483  mov     ecx, 80070216h; dwExceptionCode
0x1800d0488  lea     edx, [r9+1]; dwExceptionFlags
0x1800d048c  call    cs:__imp_RaiseException
0x1800d0492  int     3; Trap to Debugger
0x1800d0493  lea     r9, [rbx+18h]; string
0x1800d0497  mov     r8, rbx; hstringHeader
0x1800d049a  mov     rcx, r11; sourceString
0x1800d049d  call    cs:__imp_WindowsCreateStringReference
0x1800d04a3  test    eax, eax
0x1800d04a5  jns     short loc_1800D04BA
0x1800d04a7  xor     r9d, r9d; lpArguments
0x1800d04aa  xor     r8d, r8d; nNumberOfArguments
0x1800d04ad  mov     ecx, eax; dwExceptionCode
0x1800d04af  lea     edx, [r9+1]; dwExceptionFlags
0x1800d04b3  call    cs:__imp_RaiseException
0x1800d04b9  int     3; Trap to Debugger
0x1800d04ba  mov     rsi, [rsp+28h+arg_8]
0x1800d04bf  mov     rax, rbx
0x1800d04c2  mov     rbx, [rsp+28h+arg_0]
0x1800d04c7  add     rsp, 20h
0x1800d04cb  pop     rdi
0x1800d04cc  retn
```
