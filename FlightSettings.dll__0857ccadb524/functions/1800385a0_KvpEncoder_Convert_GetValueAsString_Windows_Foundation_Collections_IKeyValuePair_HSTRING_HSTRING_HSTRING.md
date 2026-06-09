# KvpEncoder::Convert::GetValueAsString(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,HSTRING__ * *)

- ea: `0x1800385a0`
- end: `0x180038640`
- name: `?GetValueAsString@Convert@KvpEncoder@@SAJPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180035704`

## callees

- `0x18000cc8c`
- `0x1800385a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800385c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003860b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800385c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003860b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038628`

## string_xrefs

- `0x1800385f4`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KvpEncoder::Convert::GetValueAsString(__int64 a1, HSTRING *a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v8; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = string;
    string = 0;
    *a2 = v8;
    WindowsDeleteString(0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v5,
      v9);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x1800385a0  mov     [rsp+arg_8], rbx
0x1800385a5  mov     [rsp+arg_10], rsi
0x1800385aa  push    rdi; int
0x1800385ab  sub     rsp, 20h
0x1800385af  mov     rsi, rdx
0x1800385b2  mov     rdi, rcx
0x1800385b5  mov     [rsp+28h+string], 0
0x1800385be  mov     rax, [rcx]
0x1800385c1  mov     rbx, [rax+38h]
0x1800385c5  xor     ecx, ecx; string
0x1800385c7  call    cs:__imp_WindowsDeleteString
0x1800385cd  mov     [rsp+28h+string], 0
0x1800385d6  lea     rdx, [rsp+28h+string]
0x1800385db  mov     rcx, rdi
0x1800385de  mov     rax, rbx
0x1800385e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385e6  mov     ebx, eax
0x1800385e8  test    eax, eax
0x1800385ea  jns     short loc_180038615
0x1800385ec  mov     rcx, [rsp+28h]; this
0x1800385f1  mov     r9d, eax; char *
0x1800385f4  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x1800385fb  mov     edx, 19Fh; void *
0x180038600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038605  nop
0x180038606  mov     rcx, [rsp+28h+string]; string
0x18003860b  call    cs:__imp_WindowsDeleteString
0x180038611  mov     eax, ebx
0x180038613  jmp     short loc_180038630
0x180038615  mov     rax, [rsp+28h+string]
0x18003861a  mov     [rsp+28h+string], 0
0x180038623  mov     [rsi], rax
0x180038626  xor     ecx, ecx; string
0x180038628  call    cs:__imp_WindowsDeleteString
0x18003862e  xor     eax, eax
0x180038630  mov     rbx, [rsp+28h+arg_8]
0x180038635  mov     rsi, [rsp+28h+arg_10]
0x18003863a  add     rsp, 20h
0x18003863e  pop     rdi
0x18003863f  retn
```
