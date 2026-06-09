# win_dox::OpcDigitalSignatureSetImpl::GetDigestStatus(void *)

- ea: `0x180100020`
- end: `0x1801000fe`
- name: `?GetDigestStatus@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NPEAX@Z`
- size: `222`
- prototype: `bool(win_dox::OpcDigitalSignatureSetImpl *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a4090`
- `0x1800ffe9c`

## callees

- `0x180015a68`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180100020`
- `0x180117740`

## import_xrefs

- `CRYPTXML!CryptXmlGetStatus` at `0x180100051`
- `CRYPTXML!CryptXmlGetStatus` at `0x180100051`

## string_xrefs

- `0x180100075`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`

## pseudocode

```c
bool __fastcall win_dox::OpcDigitalSignatureSetImpl::GetDigestStatus(
        win_dox::OpcDigitalSignatureSetImpl *this,
        void *a2)
{
  HRESULT Status; // ebx
  CRYPT_XML_STATUS pStatus; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v6[512]; // [rsp+F0h] [rbp-418h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
  {
    memset_0(v6, 0, sizeof(v6));
    StringCchPrintfW(v6, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x173u,
      Status,
      (struct win_musl::TStringEllipseBase *)v6);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return !pStatus.dwErrorStatus && (pStatus.dwInfoStatus & 8) != 0;
}

```

## disassembly

```asm
0x180100020  push    rbx
0x180100022  sub     rsp, 500h
0x180100029  mov     rax, cs:__security_cookie
0x180100030  xor     rax, rsp
0x180100033  mov     [rsp+508h+var_18], rax
0x18010003b  xor     ecx, ecx
0x18010003d  mov     rax, rdx
0x180100040  mov     qword ptr [rsp+508h+pStatus.cbSize], rcx
0x180100045  lea     rdx, [rsp+508h+pStatus]; pStatus
0x18010004a  mov     [rsp+508h+pStatus.dwInfoStatus], ecx
0x18010004e  mov     rcx, rax; hCryptXml
0x180100051  call    cs:__imp_CryptXmlGetStatus
0x180100057  mov     ebx, eax
0x180100059  test    eax, eax
0x18010005b  jns     short loc_1801000D1
0x18010005d  xor     edx, edx; Val
0x18010005f  lea     rcx, [rsp+508h+var_418]; void *
0x180100067  mov     r8d, 400h; Size
0x18010006d  call    memset_0
0x180100072  mov     r9d, ebx
0x180100075  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x18010007c  mov     edx, 200h; unsigned __int64
0x180100081  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x180100089  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18010008e  lea     rax, [rsp+508h+var_418]
0x180100096  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x18010009b  lea     r9, word_18013A0B6
0x1801000a2  mov     [rsp+508h+var_4E0], ebx; unsigned int
0x1801000a6  lea     r8, aNoFilename; "(no filename)"
0x1801000ad  lea     rcx, [rsp+508h+pExceptionObject]; this
0x1801000b2  mov     [rsp+508h+var_4E8], 173h; unsigned int
0x1801000ba  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801000bf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801000c6  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x1801000cb  call    _CxxThrowException_0
0x1801000d1  cmp     [rsp+508h+pStatus.dwErrorStatus], 0
0x1801000d6  jnz     short loc_1801000E3
0x1801000d8  mov     eax, [rsp+508h+pStatus.dwInfoStatus]
0x1801000dc  shr     eax, 3
0x1801000df  and     al, 1
0x1801000e1  jmp     short loc_1801000E5
0x1801000e3  xor     al, al
0x1801000e5  mov     rcx, [rsp+508h+var_18]
0x1801000ed  xor     rcx, rsp; StackCookie
0x1801000f0  call    __security_check_cookie
0x1801000f5  add     rsp, 500h
0x1801000fc  pop     rbx
0x1801000fd  retn
```
