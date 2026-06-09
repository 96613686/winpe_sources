# _lambda_82bbb6323568aa3c7a004da0cdf3e836_::operator()

- ea: `0x1800258a0`
- end: `0x1800259cd`
- name: `_lambda_82bbb6323568aa3c7a004da0cdf3e836_::operator()`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024ca0`

## callees

- `0x18000cc8c`
- `0x180020790`
- `0x1800258a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800259a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800259b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800259a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800259b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025974`

## string_xrefs

- `0x1800258f0`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`
- `0x18002593f`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_82bbb6323568aa3c7a004da0cdf3e836_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v11; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  HSTRING v16; // [rsp+50h] [rbp+30h] BYREF

  v16 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v16 = 0;
  v5 = v4(a2, &v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    string = 0;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(a2, &string);
    v6 = v8;
    if ( v8 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v11 = WindowsGetStringRawBuffer(v16, 0);
      v8 = RegWow64Helpers::SetString(*(HKEY *)(*(_QWORD *)a1 + 24LL), L"Properties", v11, StringRawBuffer);
      v6 = v8;
      if ( v8 >= 0 )
      {
        WindowsDeleteString(string);
        v6 = 0;
        goto LABEL_9;
      }
      v9 = 234;
    }
    else
    {
      v9 = 231;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
    WindowsDeleteString(string);
LABEL_9:
    string = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE3,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
    (const char *)(unsigned int)v5,
    savedregs);
LABEL_10:
  WindowsDeleteString(v16);
  return v6;
}

```

## disassembly

```asm
0x1800258a0  mov     [rsp-18h+arg_0], rbx
0x1800258a5  push    rbp
0x1800258a6  push    rsi
0x1800258a7  push    rdi; int
0x1800258a8  mov     rbp, rsp
0x1800258ab  sub     rsp, 20h
0x1800258af  mov     rdi, rdx
0x1800258b2  mov     rsi, rcx
0x1800258b5  mov     [rbp+arg_10], 0
0x1800258bd  mov     rax, [rdx]
0x1800258c0  mov     rbx, [rax+30h]
0x1800258c4  xor     ecx, ecx; string
0x1800258c6  call    cs:__imp_WindowsDeleteString
0x1800258cc  mov     [rbp+arg_10], 0
0x1800258d4  lea     rdx, [rbp+arg_10]
0x1800258d8  mov     rcx, rdi
0x1800258db  mov     rax, rbx
0x1800258de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258e3  mov     ebx, eax
0x1800258e5  test    eax, eax
0x1800258e7  jns     short loc_180025906
0x1800258e9  mov     rcx, [rbp+18h]; this
0x1800258ed  mov     r9d, eax; char *
0x1800258f0  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x1800258f7  mov     edx, 0E3h; void *
0x1800258fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025901  jmp     loc_1800259B4
0x180025906  mov     [rbp+string], 0
0x18002590e  mov     rax, [rdi]
0x180025911  mov     rbx, [rax+38h]
0x180025915  xor     ecx, ecx; string
0x180025917  call    cs:__imp_WindowsDeleteString
0x18002591d  mov     [rbp+string], 0
0x180025925  lea     rdx, [rbp+string]
0x180025929  mov     rcx, rdi
0x18002592c  mov     rax, rbx
0x18002592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025934  mov     ebx, eax
0x180025936  test    eax, eax
0x180025938  jns     short loc_18002595F
0x18002593a  mov     edx, 0E7h; void *
0x18002593f  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180025946  mov     r9d, eax; char *
0x180025949  mov     rcx, [rbp+18h]; this
0x18002594d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025952  nop
0x180025953  mov     rcx, [rbp+string]; string
0x180025957  call    cs:__imp_WindowsDeleteString
0x18002595d  jmp     short loc_1800259AC
0x18002595f  xor     edx, edx; length
0x180025961  mov     rcx, [rbp+string]; string
0x180025965  call    cs:__imp_WindowsGetStringRawBuffer
0x18002596b  mov     rbx, rax
0x18002596e  xor     edx, edx; length
0x180025970  mov     rcx, [rbp+arg_10]; string
0x180025974  call    cs:__imp_WindowsGetStringRawBuffer
0x18002597a  mov     rcx, [rsi]
0x18002597d  mov     r9, rbx; unsigned __int16 *
0x180025980  mov     r8, rax; unsigned __int16 *
0x180025983  lea     rdx, aProperties; "Properties"
0x18002598a  mov     rcx, [rcx+18h]; HKEY
0x18002598e  call    ?SetString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG11@Z; RegWow64Helpers::SetString(HKEY__ * const,ushort const * const,ushort const * const,ushort const * const)
0x180025993  mov     ebx, eax
0x180025995  test    eax, eax
0x180025997  jns     short loc_1800259A0
0x180025999  mov     edx, 0EAh
0x18002599e  jmp     short loc_18002593F
0x1800259a0  mov     rcx, [rbp+string]; string
0x1800259a4  call    cs:__imp_WindowsDeleteString
0x1800259aa  xor     ebx, ebx
0x1800259ac  mov     [rbp+string], 0
0x1800259b4  mov     rcx, [rbp+arg_10]; string
0x1800259b8  call    cs:__imp_WindowsDeleteString
0x1800259be  mov     eax, ebx
0x1800259c0  mov     rbx, [rsp+20h+arg_0]
0x1800259c5  add     rsp, 20h
0x1800259c9  pop     rdi
0x1800259ca  pop     rsi
0x1800259cb  pop     rbp
0x1800259cc  retn
```
