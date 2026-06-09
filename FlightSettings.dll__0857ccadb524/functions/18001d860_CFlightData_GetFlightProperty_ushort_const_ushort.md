# CFlightData::GetFlightProperty(ushort const *,ushort * *)

- ea: `0x18001d860`
- end: `0x18001d96a`
- name: `?GetFlightProperty@CFlightData@@UEAAJPEBGPEAPEAG@Z`
- size: `266`
- prototype: `int(CFlightData *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e870`

## callees

- `0x18000cc8c`
- `0x18001d2bc`
- `0x18001d860`
- `0x18001e0f0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d87a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d93e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d87a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d93e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d908`

## string_xrefs

- `0x18001d8a4`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`
- `0x18001d927`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFlightData::GetFlightProperty(CFlightData *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  CFlightData *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  CFlightData *v14; // rcx
  HSTRING v16; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+58h] [rbp+20h] BYREF

  WindowsDeleteString(0);
  v16 = 0;
  v7 = CFlightData::ConvertStringToLower(v6, a2, &v16);
  v8 = v7;
  if ( v7 >= 0 )
  {
    string = 0;
    v9 = *((_QWORD *)this + 13);
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v9 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, v16, &string);
    v8 = v11;
    if ( v11 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v11 = CFlightData::ReturnCoTaskMemDup(v14, StringRawBuffer, a3);
      v8 = v11;
      if ( v11 >= 0 )
      {
LABEL_8:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_9;
      }
      v12 = 276;
    }
    else
    {
      v12 = 274;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
      (const char *)(unsigned int)v11,
      (int)v16);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10E,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
    (const char *)(unsigned int)v7,
    (int)v16);
LABEL_9:
  WindowsDeleteString(v16);
  return v8;
}

```

## disassembly

```asm
0x18001d860  mov     [rsp+arg_0], rbx
0x18001d865  mov     [rsp+arg_8], rsi
0x18001d86a  push    rdi
0x18001d86b  sub     rsp, 30h
0x18001d86f  mov     rsi, r8
0x18001d872  mov     rbx, rdx
0x18001d875  mov     rdi, rcx
0x18001d878  xor     ecx, ecx; string
0x18001d87a  call    cs:__imp_WindowsDeleteString
0x18001d880  mov     [rsp+38h+var_18], 0; int
0x18001d889  lea     r8, [rsp+38h+var_18]; HSTRING *
0x18001d88e  mov     rdx, rbx; unsigned __int16 *
0x18001d891  call    ?ConvertStringToLower@CFlightData@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; CFlightData::ConvertStringToLower(ushort const *,HSTRING__ * *)
0x18001d896  mov     ebx, eax
0x18001d898  test    eax, eax
0x18001d89a  jns     short loc_18001D8BA
0x18001d89c  mov     rcx, [rsp+38h]; this
0x18001d8a1  mov     r9d, eax; char *
0x18001d8a4  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001d8ab  mov     edx, 10Eh; void *
0x18001d8b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d8b5  jmp     loc_18001D94D
0x18001d8ba  mov     [rsp+38h+string], 0
0x18001d8c3  mov     rdi, [rdi+68h]
0x18001d8c7  mov     rax, [rdi]
0x18001d8ca  mov     rbx, [rax+30h]
0x18001d8ce  xor     ecx, ecx; string
0x18001d8d0  call    cs:__imp_WindowsDeleteString
0x18001d8d6  mov     [rsp+38h+string], 0
0x18001d8df  lea     r8, [rsp+38h+string]
0x18001d8e4  mov     rdx, [rsp+38h+var_18]
0x18001d8e9  mov     rcx, rdi
0x18001d8ec  mov     rax, rbx
0x18001d8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f4  mov     ebx, eax
0x18001d8f6  test    eax, eax
0x18001d8f8  jns     short loc_18001D901
0x18001d8fa  mov     edx, 112h
0x18001d8ff  jmp     short loc_18001D924
0x18001d901  xor     edx, edx; length
0x18001d903  mov     rcx, [rsp+38h+string]; string
0x18001d908  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d90e  mov     r8, rsi; unsigned __int16 **
0x18001d911  mov     rdx, rax; unsigned __int16 *
0x18001d914  call    ?ReturnCoTaskMemDup@CFlightData@@AEAAJPEBGPEAPEAG@Z; CFlightData::ReturnCoTaskMemDup(ushort const *,ushort * *)
0x18001d919  mov     ebx, eax
0x18001d91b  test    eax, eax
0x18001d91d  jns     short loc_18001D939
0x18001d91f  mov     edx, 114h; void *
0x18001d924  mov     r9d, eax; char *
0x18001d927  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001d92e  mov     rcx, [rsp+38h]; this
0x18001d933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d938  nop
0x18001d939  mov     rcx, [rsp+38h+string]; string
0x18001d93e  call    cs:__imp_WindowsDeleteString
0x18001d944  mov     [rsp+38h+string], 0
0x18001d94d  mov     rcx, [rsp+38h+var_18]; string
0x18001d952  call    cs:__imp_WindowsDeleteString
0x18001d958  mov     eax, ebx
0x18001d95a  mov     rbx, [rsp+38h+arg_0]
0x18001d95f  mov     rsi, [rsp+38h+arg_8]
0x18001d964  add     rsp, 30h
0x18001d968  pop     rdi
0x18001d969  retn
```
