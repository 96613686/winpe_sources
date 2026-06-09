# CFlightData::SetFlightProperty(ushort const *,ushort const *)

- ea: `0x18001e5b0`
- end: `0x18001e6cd`
- name: `?SetFlightProperty@CFlightData@@UEAAJPEBG0@Z`
- size: `285`
- prototype: `int(CFlightData *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cc8c`
- `0x18001ce88`
- `0x18001d2bc`
- `0x18001e5b0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6b8`

## string_xrefs

- `0x18001e5ed`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`
- `0x18001e628`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`
- `0x18001e657`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFlightData::SetFlightProperty(
        CFlightData *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v5; // rax
  unsigned int v6; // ebx
  CFlightData *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-20h]
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v14; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp+30h] BYREF
  char v17; // [rsp+78h] [rbp+38h] BYREF

  v16 = a3;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 <= 0xFF )
  {
    WindowsDeleteString(0);
    v14 = 0;
    v8 = CFlightData::ConvertStringToLower(v7, a2, &v14);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
        (const char *)(unsigned int)v8,
        v12);
LABEL_14:
      WindowsDeleteString(v14);
      return v6;
    }
    string = 0;
    v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v16);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v17 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING, char *))(**((_QWORD **)this + 13) + 80LL))(
             *((_QWORD *)this + 13),
             v14,
             string,
             &v17);
      v6 = v9;
      if ( v9 >= 0 )
      {
        WindowsDeleteString(string);
        v6 = 0;
        goto LABEL_13;
      }
      v10 = 303;
    }
    else
    {
      v10 = 299;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
      (const char *)(unsigned int)v9,
      v12);
    WindowsDeleteString(string);
LABEL_13:
    string = 0;
    goto LABEL_14;
  }
  v6 = -2147024785;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x122,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
    (const char *)0x8007006FLL,
    v12);
  return v6;
}

```

## disassembly

```asm
0x18001e5b0  mov     [rsp-18h+arg_0], rbx
0x18001e5b5  mov     [rsp-18h+arg_10], r8
0x18001e5ba  push    rbp
0x18001e5bb  push    rsi
0x18001e5bc  push    rdi
0x18001e5bd  mov     rbp, rsp
0x18001e5c0  sub     rsp, 40h
0x18001e5c4  mov     rbx, rdx
0x18001e5c7  mov     rdi, rcx
0x18001e5ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e5ce  xor     esi, esi
0x18001e5d0  inc     rax
0x18001e5d3  cmp     [rdx+rax*2], si
0x18001e5d7  jnz     short loc_18001E5D0
0x18001e5d9  cmp     rax, 0FFh
0x18001e5df  jbe     short loc_18001E603
0x18001e5e1  mov     rcx, [rbp+18h]; this
0x18001e5e5  mov     ebx, 8007006Fh
0x18001e5ea  mov     r9d, ebx; char *
0x18001e5ed  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001e5f4  mov     edx, 122h; void *
0x18001e5f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5fe  jmp     loc_18001E6BE
0x18001e603  xor     ecx, ecx; string
0x18001e605  call    cs:__imp_WindowsDeleteString
0x18001e60b  mov     [rbp+var_8], rsi
0x18001e60f  lea     r8, [rbp+var_8]; HSTRING *
0x18001e613  mov     rdx, rbx; unsigned __int16 *
0x18001e616  call    ?ConvertStringToLower@CFlightData@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; CFlightData::ConvertStringToLower(ushort const *,HSTRING__ * *)
0x18001e61b  mov     ebx, eax
0x18001e61d  test    eax, eax
0x18001e61f  jns     short loc_18001E63B
0x18001e621  mov     rcx, [rbp+18h]; this
0x18001e625  mov     r9d, eax; char *
0x18001e628  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001e62f  mov     edx, 127h; void *
0x18001e634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e639  jmp     short loc_18001E6B4
0x18001e63b  mov     [rbp+string], rsi
0x18001e63f  lea     rdx, [rbp+arg_10]
0x18001e643  lea     rcx, [rbp+string]
0x18001e647  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e64c  mov     ebx, eax
0x18001e64e  test    eax, eax
0x18001e650  jns     short loc_18001E677
0x18001e652  mov     edx, 12Bh; void *
0x18001e657  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001e65e  mov     r9d, eax; char *
0x18001e661  mov     rcx, [rbp+18h]; this
0x18001e665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e66a  nop
0x18001e66b  mov     rcx, [rbp+string]; string
0x18001e66f  call    cs:__imp_WindowsDeleteString
0x18001e675  jmp     short loc_18001E6B0
0x18001e677  mov     [rbp+arg_18], sil
0x18001e67b  mov     rcx, [rdi+68h]
0x18001e67f  mov     rax, [rcx]
0x18001e682  lea     r9, [rbp+arg_18]
0x18001e686  mov     r8, [rbp+string]
0x18001e68a  mov     rdx, [rbp+var_8]
0x18001e68e  mov     rax, [rax+50h]
0x18001e692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e697  mov     ebx, eax
0x18001e699  test    eax, eax
0x18001e69b  jns     short loc_18001E6A4
0x18001e69d  mov     edx, 12Fh
0x18001e6a2  jmp     short loc_18001E657
0x18001e6a4  mov     rcx, [rbp+string]; string
0x18001e6a8  call    cs:__imp_WindowsDeleteString
0x18001e6ae  mov     ebx, esi
0x18001e6b0  mov     [rbp+string], rsi
0x18001e6b4  mov     rcx, [rbp+var_8]; string
0x18001e6b8  call    cs:__imp_WindowsDeleteString
0x18001e6be  mov     eax, ebx
0x18001e6c0  mov     rbx, [rsp+40h+arg_0]
0x18001e6c5  add     rsp, 40h
0x18001e6c9  pop     rdi
0x18001e6ca  pop     rsi
0x18001e6cb  pop     rbp
0x18001e6cc  retn
```
