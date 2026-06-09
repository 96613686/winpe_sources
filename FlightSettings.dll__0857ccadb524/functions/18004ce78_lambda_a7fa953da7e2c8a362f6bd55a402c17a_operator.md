# _lambda_a7fa953da7e2c8a362f6bd55a402c17a_::operator()

- ea: `0x18004ce78`
- end: `0x18004cf2e`
- name: `_lambda_a7fa953da7e2c8a362f6bd55a402c17a_::operator()`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ad94`

## callees

- `0x18000cc8c`
- `0x18001d244`
- `0x18004ce78`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cf16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cf16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004cef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004cef2`

## string_xrefs

- `0x18004cecc`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall lambda_a7fa953da7e2c8a362f6bd55a402c17a_::operator()(_QWORD *a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  BOOL v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  UINT32 length; // [rsp+38h] [rbp+10h] BYREF
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
           *a1,
           StringRawBuffer,
           length) == 2;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
      (const char *)(unsigned int)v5,
      v9);
  }
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x18004ce78  mov     [rsp+arg_0], rbx
0x18004ce7d  mov     [rsp+arg_18], rsi
0x18004ce82  push    rdi; int
0x18004ce83  sub     rsp, 20h
0x18004ce87  mov     rdi, rdx
0x18004ce8a  mov     rsi, rcx
0x18004ce8d  mov     [rsp+28h+string], 0
0x18004ce96  mov     rax, [rdx]
0x18004ce99  mov     rbx, [rax+40h]
0x18004ce9d  xor     ecx, ecx; string
0x18004ce9f  call    cs:__imp_WindowsDeleteString
0x18004cea5  mov     [rsp+28h+string], 0
0x18004ceae  lea     rdx, [rsp+28h+string]
0x18004ceb3  mov     rcx, rdi
0x18004ceb6  mov     rax, rbx
0x18004ceb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cebe  mov     ebx, eax
0x18004cec0  test    eax, eax
0x18004cec2  jns     short loc_18004CEE0
0x18004cec4  mov     rcx, [rsp+28h]; this
0x18004cec9  mov     r9d, eax; char *
0x18004cecc  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004ced3  mov     edx, 17Dh; void *
0x18004ced8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cedd  nop
0x18004cede  jmp     short loc_18004CF11
0x18004cee0  mov     [rsp+28h+length], 0
0x18004cee8  lea     rdx, [rsp+28h+length]; length
0x18004ceed  mov     rcx, [rsp+28h+string]; string
0x18004cef2  call    cs:__imp_WindowsGetStringRawBuffer
0x18004cef8  mov     r8d, [rsp+28h+length]
0x18004cefd  mov     rdx, rax
0x18004cf00  mov     rcx, [rsi]
0x18004cf03  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18004cf08  nop
0x18004cf09  xor     ebx, ebx
0x18004cf0b  cmp     eax, 2
0x18004cf0e  setz    bl
0x18004cf11  mov     rcx, [rsp+28h+string]; string
0x18004cf16  call    cs:__imp_WindowsDeleteString
0x18004cf1c  mov     eax, ebx
0x18004cf1e  mov     rbx, [rsp+28h+arg_0]
0x18004cf23  mov     rsi, [rsp+28h+arg_18]
0x18004cf28  add     rsp, 20h
0x18004cf2c  pop     rdi
0x18004cf2d  retn
```
