# _lambda_f4377e5c10386feccc25feba97aef5cc_::operator()(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *)

- ea: `0x180035704`
- end: `0x18003585f`
- name: `??R_lambda_f4377e5c10386feccc25feba97aef5cc_@@QEBAJPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034434`

## callees

- `0x18000cc8c`
- `0x180035704`
- `0x1800385a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003572c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800357c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035839`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003572c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800357c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035839`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800357e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800357f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800357e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800357f2`

## string_xrefs

- `0x180035761`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x1800357ab`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x18003581f`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_f4377e5c10386feccc25feba97aef5cc_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rdi
  int *v5; // rbx
  int v6; // edi
  int *v7; // rbx
  HSTRING v8; // rcx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, PCWSTR, PCWSTR); // rbp
  HSTRING v11; // rbx
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v13; // rax
  int *v14; // rsi
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING v18; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+58h] [rbp+10h] BYREF

  v18 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v18 = 0;
  v5 = *(int **)a1;
  *v5 = v4(a2, &v18);
  v6 = **(_DWORD **)a1;
  if ( v6 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v7 = *(int **)a1;
    *v7 = KvpEncoder::Convert::GetValueAsString(a2, &string);
    v6 = **(_DWORD **)a1;
    if ( v6 >= 0 )
    {
      v9 = **(_QWORD **)(a1 + 8);
      v10 = *(__int64 (__fastcall **)(__int64, PCWSTR, PCWSTR))(*(_QWORD *)v9 + 16LL);
      v11 = string;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v13 = WindowsGetStringRawBuffer(v18, 0);
      v14 = *(int **)a1;
      *v14 = v10(v9, v13, StringRawBuffer);
      v6 = **(_DWORD **)a1;
      if ( v6 >= 0 )
      {
        WindowsDeleteString(v11);
        v6 = 0;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v6,
        v16);
      v8 = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v6,
        v16);
      v8 = string;
    }
    WindowsDeleteString(v8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v6,
      v16);
  }
LABEL_9:
  WindowsDeleteString(v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180035704  mov     [rsp+arg_10], rbx
0x180035709  push    rbp
0x18003570a  push    rsi
0x18003570b  push    rdi
0x18003570c  push    r14
0x18003570e  push    r15; int
0x180035710  sub     rsp, 20h
0x180035714  mov     rsi, rdx
0x180035717  mov     r15, rcx
0x18003571a  mov     [rsp+48h+arg_0], 0
0x180035723  mov     rax, [rdx]
0x180035726  mov     rdi, [rax+30h]
0x18003572a  xor     ecx, ecx; string
0x18003572c  call    cs:__imp_WindowsDeleteString
0x180035732  mov     [rsp+48h+arg_0], 0
0x18003573b  mov     rbx, [r15]
0x18003573e  lea     rdx, [rsp+48h+arg_0]
0x180035743  mov     rcx, rsi
0x180035746  mov     rax, rdi
0x180035749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003574e  mov     [rbx], eax
0x180035750  mov     rax, [r15]
0x180035753  mov     edi, [rax]
0x180035755  test    edi, edi
0x180035757  jns     short loc_180035777
0x180035759  mov     rcx, [rsp+48h]; this
0x18003575e  mov     r9d, edi; char *
0x180035761  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x180035768  mov     edx, 186h; void *
0x18003576d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035772  jmp     loc_180035841
0x180035777  xor     ecx, ecx; string
0x180035779  call    cs:__imp_WindowsDeleteString
0x18003577f  mov     [rsp+48h+string], 0
0x180035788  mov     rbx, [r15]
0x18003578b  lea     rdx, [rsp+48h+string]
0x180035790  mov     rcx, rsi
0x180035793  call    ?GetValueAsString@Convert@KvpEncoder@@SAJPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; KvpEncoder::Convert::GetValueAsString(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,HSTRING__ * *)
0x180035798  mov     [rbx], eax
0x18003579a  mov     rax, [r15]
0x18003579d  mov     edi, [rax]
0x18003579f  test    edi, edi
0x1800357a1  jns     short loc_1800357CA
0x1800357a3  mov     rcx, [rsp+48h]; this
0x1800357a8  mov     r9d, edi; char *
0x1800357ab  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x1800357b2  mov     edx, 18Ah; void *
0x1800357b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800357bc  nop
0x1800357bd  mov     rcx, [rsp+48h+string]; string
0x1800357c2  call    cs:__imp_WindowsDeleteString
0x1800357c8  jmp     short loc_180035841
0x1800357ca  mov     rax, [r15+8]
0x1800357ce  mov     r14, [rax]
0x1800357d1  mov     rax, [r14]
0x1800357d4  mov     rbp, [rax+10h]
0x1800357d8  xor     edx, edx; length
0x1800357da  mov     rbx, [rsp+48h+string]
0x1800357df  mov     rcx, rbx; string
0x1800357e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800357e8  mov     rdi, rax
0x1800357eb  xor     edx, edx; length
0x1800357ed  mov     rcx, [rsp+48h+arg_0]; string
0x1800357f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800357f8  mov     rsi, [r15]
0x1800357fb  mov     r8, rdi
0x1800357fe  mov     rdx, rax
0x180035801  mov     rcx, r14
0x180035804  mov     rax, rbp
0x180035807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003580c  mov     [rsi], eax
0x18003580e  mov     rax, [r15]
0x180035811  mov     edi, [rax]
0x180035813  test    edi, edi
0x180035815  jns     short loc_180035836
0x180035817  mov     rcx, [rsp+48h]; this
0x18003581c  mov     r9d, edi; char *
0x18003581f  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x180035826  mov     edx, 18Dh; void *
0x18003582b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035830  nop
0x180035831  mov     rcx, rbx
0x180035834  jmp     short loc_1800357C2
0x180035836  mov     rcx, rbx; string
0x180035839  call    cs:__imp_WindowsDeleteString
0x18003583f  xor     edi, edi
0x180035841  mov     rcx, [rsp+48h+arg_0]; string
0x180035846  call    cs:__imp_WindowsDeleteString
0x18003584c  mov     eax, edi
0x18003584e  mov     rbx, [rsp+48h+arg_10]
0x180035853  add     rsp, 20h
0x180035857  pop     r15
0x180035859  pop     r14
0x18003585b  pop     rdi
0x18003585c  pop     rsi
0x18003585d  pop     rbp
0x18003585e  retn
```
