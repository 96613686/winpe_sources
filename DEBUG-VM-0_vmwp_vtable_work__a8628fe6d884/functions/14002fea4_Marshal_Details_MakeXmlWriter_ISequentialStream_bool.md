# Marshal::Details::MakeXmlWriter(ISequentialStream *,bool)

- ea: `0x14002fea4`
- end: `0x140030054`
- name: `?MakeXmlWriter@Details@Marshal@@YA?AV?$com_ptr_t@UIXmlWriter@@Uerr_exception_policy@wil@@@wil@@PEAUISequentialStream@@_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pOutputStream)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002fc64`
- `0x140062670`

## callees

- `0x14002fea4`
- `0x14006af38`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14002fee6`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x14002fee6`
- `XmlLite!CreateXmlWriter` at `0x14002ff2c`
- `XmlLite!CreateXmlWriter` at `0x14002ff2c`

## string_xrefs

- `0x14002fefe`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14002ff44`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14002ff76`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14002ffaa`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x14002ffe0`: `onecore\vm\common\marshal\inc\MarshalXml.h`
- `0x140030014`: `onecore\vm\common\marshal\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall Marshal::Details::MakeXmlWriter(void **ppvObject, IUnknown *pOutputStream)
{
  HRESULT v3; // eax
  HRESULT XmlWriter; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  IXmlWriterOutput *ppOutput; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ppOutput = 0;
  v3 = CreateXmlWriterOutputWithEncodingName(pOutputStream, 0, L"UTF-16", &ppOutput);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v3,
      0);
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlWriter < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)XmlWriter,
      1);
  v5 = (*(__int64 (__fastcall **)(_QWORD, IXmlWriterOutput *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppOutput);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v5,
      1);
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v6,
      1);
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4, 1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v7,
      1);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\vm\\common\\marshal\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v8,
      1);
  if ( ppOutput )
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  return ppvObject;
}

```

## disassembly

```asm
0x14002fea4  push    rbx
0x14002fea6  sub     rsp, 40h
0x14002feaa  mov     rax, cs:__security_cookie
0x14002feb1  xor     rax, rsp
0x14002feb4  mov     [rsp+48h+var_10], rax
0x14002feb9  mov     rax, rdx
0x14002febc  mov     rbx, rcx
0x14002febf  mov     [rsp+48h+var_20], rcx
0x14002fec4  mov     [rsp+48h+var_28], 0; int
0x14002fecc  mov     [rsp+48h+ppOutput], 0
0x14002fed5  lea     r9, [rsp+48h+ppOutput]; ppOutput
0x14002feda  lea     r8, pwszEncodingName; "UTF-16"
0x14002fee1  xor     edx, edx; pMalloc
0x14002fee3  mov     rcx, rax; pOutputStream
0x14002fee6  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x14002feed  nop     dword ptr [rax+rax+00h]
0x14002fef2  mov     rcx, [rsp+48h]; this
0x14002fef7  test    eax, eax
0x14002fef9  jns     short loc_14002FF10
0x14002fefb  mov     r9d, eax; char *
0x14002fefe  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14002ff05  mov     edx, 42Bh; void *
0x14002ff0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002ff10  mov     [rsp+48h+var_28], 1; int
0x14002ff18  mov     qword ptr [rbx], 0
0x14002ff1f  xor     r8d, r8d; pMalloc
0x14002ff22  mov     rdx, rbx; ppvObject
0x14002ff25  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x14002ff2c  call    cs:__imp_CreateXmlWriter
0x14002ff33  nop     dword ptr [rax+rax+00h]
0x14002ff38  mov     rcx, [rsp+48h]; this
0x14002ff3d  test    eax, eax
0x14002ff3f  jns     short loc_14002FF56
0x14002ff41  mov     r9d, eax; char *
0x14002ff44  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14002ff4b  mov     edx, 42Eh; void *
0x14002ff50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002ff56  mov     rcx, [rbx]
0x14002ff59  mov     rax, [rcx]
0x14002ff5c  mov     rdx, [rsp+48h+ppOutput]
0x14002ff61  mov     rax, [rax+18h]
0x14002ff65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff6a  mov     rcx, [rsp+48h]; this
0x14002ff6f  test    eax, eax
0x14002ff71  jns     short loc_14002FF88
0x14002ff73  mov     r9d, eax; char *
0x14002ff76  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14002ff7d  mov     edx, 42Fh; void *
0x14002ff82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002ff88  mov     rcx, [rbx]
0x14002ff8b  mov     rax, [rcx]
0x14002ff8e  xor     r8d, r8d
0x14002ff91  lea     edx, [r8+2]
0x14002ff95  mov     rax, [rax+28h]
0x14002ff99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff9e  mov     rcx, [rsp+48h]; this
0x14002ffa3  test    eax, eax
0x14002ffa5  jns     short loc_14002FFBC
0x14002ffa7  mov     r9d, eax; char *
0x14002ffaa  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14002ffb1  mov     edx, 431h; void *
0x14002ffb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002ffbc  mov     rcx, [rbx]
0x14002ffbf  mov     rax, [rcx]
0x14002ffc2  mov     edx, 4
0x14002ffc7  lea     r8d, [rdx-3]
0x14002ffcb  mov     rax, [rax+28h]
0x14002ffcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ffd4  mov     rcx, [rsp+48h]; this
0x14002ffd9  test    eax, eax
0x14002ffdb  jns     short loc_14002FFF2
0x14002ffdd  mov     r9d, eax; char *
0x14002ffe0  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14002ffe7  mov     edx, 433h; void *
0x14002ffec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002fff2  mov     rcx, [rbx]
0x14002fff5  mov     rax, [rcx]
0x14002fff8  xor     r8d, r8d
0x14002fffb  lea     edx, [r8+1]
0x14002ffff  mov     rax, [rax+28h]
0x140030003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030008  mov     rcx, [rsp+48h]; this
0x14003000d  test    eax, eax
0x14003000f  jns     short loc_140030026
0x140030011  mov     r9d, eax; char *
0x140030014  lea     r8, aOnecoreVmCommo_71; "onecore\\vm\\common\\marshal\\inc\\Mars"...
0x14003001b  mov     edx, 434h; void *
0x140030020  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140030026  mov     rcx, [rsp+48h+ppOutput]
0x14003002b  test    rcx, rcx
0x14003002e  jz      short loc_14003003D
0x140030030  mov     rdx, [rcx]
0x140030033  mov     rax, [rdx+10h]
0x140030037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003003c  nop
0x14003003d  mov     rax, rbx
0x140030040  mov     rcx, [rsp+48h+var_10]
0x140030045  xor     rcx, rsp; StackCookie
0x140030048  call    __security_check_cookie
0x14003004d  add     rsp, 40h
0x140030051  pop     rbx
0x140030052  retn
```
