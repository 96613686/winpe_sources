# web::http::client::details::verify_uri(web::uri const &)

- ea: `0x18003a3bc`
- end: `0x18003a449`
- name: `?verify_uri@details@client@http@web@@YAXAEBVuri@4@@Z`
- size: `141`
- prototype: `void __fastcall(web::http::client::details *__hidden this, const struct web::uri *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036e20`

## callees

- `0x180005e9c`
- `0x180011fc4`
- `0x18003199c`
- `0x18003a3bc`

## string_xrefs

- `0x18003a3f1`: `URI scheme must be 'http' or 'https'`
- `0x18003a41b`: `URI must contain a hostname.`

## pseudocode

```c
void __fastcall web::http::client::details::verify_uri(web::http::client::details *this, const struct web::uri *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( (unsigned __int8)std::operator!=<unsigned short>((char *)this + 32, L"http")
    && (unsigned __int8)std::operator!=<unsigned short>((char *)this + 32, L"https") )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "URI scheme must be 'http' or 'https'");
    throw (std::invalid_argument *)pExceptionObject;
  }
  if ( !*((_QWORD *)this + 10) )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "URI must contain a hostname.");
    throw (std::invalid_argument *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18003a3bc  mov     [rsp+arg_0], rbx
0x18003a3c1  push    rdi
0x18003a3c2  sub     rsp, 40h
0x18003a3c6  mov     rbx, rcx
0x18003a3c9  lea     rdx, aHttp; "http"
0x18003a3d0  add     rcx, 20h ; ' '
0x18003a3d4  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18003a3d9  test    al, al
0x18003a3db  jz      short loc_18003A414
0x18003a3dd  lea     rdx, aHttps; "https"
0x18003a3e4  lea     rcx, [rbx+20h]
0x18003a3e8  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18003a3ed  test    al, al
0x18003a3ef  jz      short loc_18003A414
0x18003a3f1  lea     rdx, aUriSchemeMustB; "URI scheme must be 'http' or 'https'"
0x18003a3f8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18003a3fd  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18003a402  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18003a409  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003a40e  call    _CxxThrowException_0
0x18003a414  cmp     qword ptr [rbx+50h], 0
0x18003a419  jnz     short loc_18003A43E
0x18003a41b  lea     rdx, aUriMustContain; "URI must contain a hostname."
0x18003a422  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18003a427  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18003a42c  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18003a433  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003a438  call    _CxxThrowException_0
0x18003a43e  mov     rbx, [rsp+48h+arg_0]
0x18003a443  add     rsp, 40h
0x18003a447  pop     rdi
0x18003a448  retn
```
