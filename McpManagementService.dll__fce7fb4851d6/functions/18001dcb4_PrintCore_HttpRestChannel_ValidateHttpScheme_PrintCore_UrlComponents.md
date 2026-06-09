# PrintCore::HttpRestChannel::_ValidateHttpScheme(PrintCore::UrlComponents)

- ea: `0x18001dcb4`
- end: `0x18001dd57`
- name: `?_ValidateHttpScheme@HttpRestChannel@PrintCore@@AEAAXUUrlComponents@2@@Z`
- size: `163`
- prototype: `void __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001d7dc`

## callees

- `0x180003a60`
- `0x18000e164`
- `0x180012aa8`
- `0x18001ba58`
- `0x18001dcb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001dce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001dcff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001dce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001dcff`

## pseudocode

```c
void __fastcall PrintCore::HttpRestChannel::_ValidateHttpScheme(__int64 a1, char *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  char v5; // al
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v5 = 0;
  if ( (unsigned int)_o__wcsicmp(v3, L"HTTP") )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    if ( (unsigned int)_o__wcsicmp(v4, L"HTTPS") )
      v5 = 1;
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xE4,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
    (const char *)0x80070057LL,
    v5,
    (bool)"Invalid URL scheme",
    a2);
  PrintCore::UrlComponents::~UrlComponents((PrintCore::UrlComponents *)a2);
}

```

## disassembly

```asm
0x18001dcb4  push    rbx
0x18001dcb6  sub     rsp, 40h
0x18001dcba  mov     rax, cs:__security_cookie
0x18001dcc1  xor     rax, rsp
0x18001dcc4  mov     [rsp+48h+var_10], rax
0x18001dcc9  mov     rbx, rdx
0x18001dccc  mov     [rsp+48h+var_18], rdx; char *
0x18001dcd1  mov     rcx, rdx
0x18001dcd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001dcd9  lea     rdx, aHttp; "HTTP"
0x18001dce0  mov     rcx, rax
0x18001dce3  call    cs:__imp__o__wcsicmp
0x18001dce9  test    eax, eax
0x18001dceb  jz      short loc_18001DD0D
0x18001dced  mov     rcx, rbx
0x18001dcf0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001dcf5  lea     rdx, aHttps_0; "HTTPS"
0x18001dcfc  mov     rcx, rax
0x18001dcff  call    cs:__imp__o__wcsicmp
0x18001dd05  test    eax, eax
0x18001dd07  jz      short loc_18001DD0D
0x18001dd09  mov     al, 1
0x18001dd0b  jmp     short loc_18001DD0F
0x18001dd0d  xor     eax, eax
0x18001dd0f  mov     rcx, [rsp+48h]; this
0x18001dd14  lea     rdx, aInvalidUrlSche; "Invalid URL scheme"
0x18001dd1b  mov     qword ptr [rsp+48h+var_20], rdx; bool
0x18001dd20  mov     [rsp+48h+var_28], al; char
0x18001dd24  mov     r9d, 80070057h; char *
0x18001dd2a  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\H"...
0x18001dd31  mov     edx, 0E4h; void *
0x18001dd36  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001dd3b  nop
0x18001dd3c  mov     rcx, rbx; this
0x18001dd3f  call    ??1UrlComponents@PrintCore@@QEAA@XZ; PrintCore::UrlComponents::~UrlComponents(void)
0x18001dd44  mov     rcx, [rsp+48h+var_10]
0x18001dd49  xor     rcx, rsp; StackCookie
0x18001dd4c  call    __security_check_cookie
0x18001dd51  add     rsp, 40h
0x18001dd55  pop     rbx
0x18001dd56  retn
```
