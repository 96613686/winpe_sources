# KvpEncoderJson::FinalizeCreateString(HSTRING__ * *)

- ea: `0x1800373e0`
- end: `0x1800374bd`
- name: `?FinalizeCreateString@KvpEncoderJson@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `221`
- prototype: `int(KvpEncoderJson *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x180036fc8`
- `0x1800373e0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003743c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003747c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003743c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003747c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037495`

## string_xrefs

- `0x180037414`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x180037466`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KvpEncoderJson::FinalizeCreateString(KvpEncoderJson *this, HSTRING *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  HSTRING v8; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  __int64 v13; // [rsp+50h] [rbp+30h] BYREF

  v13 = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo((char *)this + 16, a2, &v13);
  v4 = v3;
  if ( v3 >= 0 )
  {
    string = 0;
    v5 = v13;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(v5, &string);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = string;
      string = 0;
      *a2 = v8;
      WindowsDeleteString(0);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v7,
        savedregs);
      WindowsDeleteString(string);
    }
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v3,
      savedregs);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  return v4;
}

```

## disassembly

```asm
0x1800373e0  mov     [rsp-18h+arg_8], rbx
0x1800373e5  push    rbp
0x1800373e6  push    rsi
0x1800373e7  push    rdi; int
0x1800373e8  mov     rbp, rsp
0x1800373eb  sub     rsp, 20h
0x1800373ef  mov     rsi, rdx
0x1800373f2  mov     [rbp+arg_10], 0
0x1800373fa  add     rcx, 10h
0x1800373fe  lea     r8, [rbp+arg_10]
0x180037402  call    ?CopyTo@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo(_GUID const &,void * *)
0x180037407  mov     ebx, eax
0x180037409  test    eax, eax
0x18003740b  jns     short loc_180037427
0x18003740d  mov     rcx, [rbp+18h]; this
0x180037411  mov     r9d, eax; char *
0x180037414  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x18003741b  mov     edx, 0F4h; void *
0x180037420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037425  jmp     short loc_1800374A5
0x180037427  mov     [rbp+string], 0
0x18003742f  mov     rdi, [rbp+arg_10]
0x180037433  mov     rax, [rdi]
0x180037436  mov     rbx, [rax+38h]
0x18003743a  xor     ecx, ecx; string
0x18003743c  call    cs:__imp_WindowsDeleteString
0x180037442  mov     [rbp+string], 0
0x18003744a  lea     rdx, [rbp+string]
0x18003744e  mov     rcx, rdi
0x180037451  mov     rax, rbx
0x180037454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037459  mov     ebx, eax
0x18003745b  test    eax, eax
0x18003745d  jns     short loc_180037484
0x18003745f  mov     rcx, [rbp+18h]; this
0x180037463  mov     r9d, eax; char *
0x180037466  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x18003746d  mov     edx, 0F8h; void *
0x180037472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037477  nop
0x180037478  mov     rcx, [rbp+string]; string
0x18003747c  call    cs:__imp_WindowsDeleteString
0x180037482  jmp     short loc_18003749D
0x180037484  mov     rax, [rbp+string]
0x180037488  mov     [rbp+string], 0
0x180037490  mov     [rsi], rax
0x180037493  xor     ecx, ecx; string
0x180037495  call    cs:__imp_WindowsDeleteString
0x18003749b  xor     ebx, ebx
0x18003749d  mov     [rbp+string], 0
0x1800374a5  lea     rcx, [rbp+arg_10]
0x1800374a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800374ae  mov     eax, ebx
0x1800374b0  mov     rbx, [rsp+20h+arg_8]
0x1800374b5  add     rsp, 20h
0x1800374b9  pop     rdi
0x1800374ba  pop     rsi
0x1800374bb  pop     rbp
0x1800374bc  retn
```
