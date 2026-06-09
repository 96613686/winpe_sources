# win_dox::OpcDigitalSignatureManagerImpl::GetReferenceDigestValue(void *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800c1798`
- end: `0x1800c1892`
- name: `?GetReferenceDigestValue@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a0a48`
- `0x1800a4ae0`

## callees

- `0x180018c2c`
- `0x1800517a0`
- `0x1800c1798`
- `0x1800c2394`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x1800c1801`
- `CRYPTXML!CryptXmlGetReference` at `0x1800c1801`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c17d0`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c17d0`

## pseudocode

```c
__int64 __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetReferenceDigestValue(__int64 a1, void *a2, __int64 a3)
{
  HRESULT Status; // eax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  HRESULT Reference; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+40h] [rbp-D8h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v6, v7, v8);
  if ( (pStatus.dwInfoStatus & 8) == 0 || (pStatus.dwErrorStatus & 2) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x65Fu,
      0x8051001A,
      (struct win_musl::TStringEllipseBase *)L"Cannot get digest value for a signed reference");
    throw (SplException::THResultException *)pExceptionObject;
  }
  ppStruct = 0;
  Reference = CryptXmlGetReference(a2, (const CRYPT_XML_REFERENCE **)&ppStruct);
  if ( Reference < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Reference, v10, v11, v12);
  return std::vector<unsigned char>::assign<unsigned char *>(
           a3,
           ppStruct->DigestValue.pbData,
           &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
}

```

## disassembly

```asm
0x1800c1798  mov     [rsp+arg_0], rbx
0x1800c179d  push    rdi
0x1800c179e  sub     rsp, 110h
0x1800c17a5  mov     rax, cs:__security_cookie
0x1800c17ac  xor     rax, rsp
0x1800c17af  mov     [rsp+118h+var_18], rax
0x1800c17b7  mov     rbx, rdx
0x1800c17ba  xor     eax, eax
0x1800c17bc  mov     rcx, rbx; hCryptXml
0x1800c17bf  mov     qword ptr [rsp+118h+pStatus.cbSize], rax
0x1800c17c4  lea     rdx, [rsp+118h+pStatus]; pStatus
0x1800c17c9  mov     [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c17cd  mov     rdi, r8
0x1800c17d0  call    cs:__imp_CryptXmlGetStatus
0x1800c17d6  test    eax, eax
0x1800c17d8  jns     short loc_1800C17E2
0x1800c17da  mov     ecx, eax; this
0x1800c17dc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c17e2  test    byte ptr [rsp+118h+pStatus.dwInfoStatus], 8
0x1800c17e7  jz      short loc_1800C184C
0x1800c17e9  test    byte ptr [rsp+118h+pStatus.dwErrorStatus], 2
0x1800c17ee  jnz     short loc_1800C184C
0x1800c17f0  lea     rdx, [rsp+118h+ppStruct]; ppStruct
0x1800c17f5  mov     [rsp+118h+ppStruct], 0
0x1800c17fe  mov     rcx, rbx; hCryptXml
0x1800c1801  call    cs:__imp_CryptXmlGetReference
0x1800c1807  test    eax, eax
0x1800c1809  jns     short loc_1800C1813
0x1800c180b  mov     ecx, eax; this
0x1800c180d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c1813  mov     rax, [rsp+118h+ppStruct]
0x1800c1818  mov     rcx, rdi
0x1800c181b  mov     rdx, [rax+50h]
0x1800c181f  mov     r8d, [rax+48h]
0x1800c1823  add     r8, rdx
0x1800c1826  call    ??$assign@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *>(uchar *,uchar *)
0x1800c182b  mov     rcx, [rsp+118h+var_18]
0x1800c1833  xor     rcx, rsp; StackCookie
0x1800c1836  call    __security_check_cookie
0x1800c183b  mov     rbx, [rsp+118h+arg_0]
0x1800c1843  add     rsp, 110h
0x1800c184a  pop     rdi
0x1800c184b  retn
0x1800c184c  lea     rax, aCannotGetDiges; "Cannot get digest value for a signed re"...
0x1800c1853  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800c1858  lea     r9, word_18013A0B6
0x1800c185f  mov     [rsp+118h+var_F0], 8051001Ah; unsigned int
0x1800c1867  lea     r8, aNoFilename; "(no filename)"
0x1800c186e  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800c1873  mov     [rsp+118h+var_F8], 65Fh; unsigned int
0x1800c187b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c1880  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c1887  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800c188c  call    _CxxThrowException_0
```
