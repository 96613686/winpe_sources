# win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(void *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800c1898`
- end: `0x1800c199b`
- name: `?GetSignatureValue@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a1ef4`

## callees

- `0x180018c2c`
- `0x1800517a0`
- `0x1800c1898`
- `0x1800c2394`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `CRYPTXML!CryptXmlGetSignature` at `0x1800c1904`
- `CRYPTXML!CryptXmlGetSignature` at `0x1800c1904`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c18d0`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800c18d0`

## pseudocode

```c
__int64 __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(__int64 a1, void *a2, __int64 a3)
{
  HRESULT Status; // eax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  HRESULT Signature; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  CRYPT_XML_SIGNATURE *ppStruct; // [rsp+40h] [rbp-D8h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v6, v7, v8);
  if ( (pStatus.dwInfoStatus & 0x10000) == 0 || (pStatus.dwErrorStatus & 0x10000) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x682u,
      0x80510019,
      (struct win_musl::TStringEllipseBase *)L"Cannot get signature value");
    throw (SplException::THResultException *)pExceptionObject;
  }
  ppStruct = 0;
  Signature = CryptXmlGetSignature(a2, (const CRYPT_XML_SIGNATURE **)&ppStruct);
  if ( Signature < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Signature, v10, v11, v12);
  return std::vector<unsigned char>::assign<unsigned char *>(
           a3,
           ppStruct->SignatureValue.pbData,
           &ppStruct->SignatureValue.pbData[ppStruct->SignatureValue.cbData]);
}

```

## disassembly

```asm
0x1800c1898  mov     [rsp+arg_0], rbx
0x1800c189d  push    rdi
0x1800c189e  sub     rsp, 110h
0x1800c18a5  mov     rax, cs:__security_cookie
0x1800c18ac  xor     rax, rsp
0x1800c18af  mov     [rsp+118h+var_18], rax
0x1800c18b7  mov     rbx, rdx
0x1800c18ba  xor     eax, eax
0x1800c18bc  mov     rcx, rbx; hCryptXml
0x1800c18bf  mov     qword ptr [rsp+118h+pStatus.cbSize], rax
0x1800c18c4  lea     rdx, [rsp+118h+pStatus]; pStatus
0x1800c18c9  mov     [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c18cd  mov     rdi, r8
0x1800c18d0  call    cs:__imp_CryptXmlGetStatus
0x1800c18d6  test    eax, eax
0x1800c18d8  jns     short loc_1800C18E2
0x1800c18da  mov     ecx, eax; this
0x1800c18dc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c18e2  mov     eax, 10000h
0x1800c18e7  test    [rsp+118h+pStatus.dwInfoStatus], eax
0x1800c18eb  jz      short loc_1800C1955
0x1800c18ed  test    [rsp+118h+pStatus.dwErrorStatus], eax
0x1800c18f1  jnz     short loc_1800C1955
0x1800c18f3  lea     rdx, [rsp+118h+ppStruct]; ppStruct
0x1800c18f8  mov     [rsp+118h+ppStruct], 0
0x1800c1901  mov     rcx, rbx; hCryptXml
0x1800c1904  call    cs:__imp_CryptXmlGetSignature
0x1800c190a  test    eax, eax
0x1800c190c  jns     short loc_1800C1916
0x1800c190e  mov     ecx, eax; this
0x1800c1910  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c1916  mov     rax, [rsp+118h+ppStruct]
0x1800c191b  mov     rcx, rdi
0x1800c191e  mov     rdx, [rax+90h]
0x1800c1925  mov     r8d, [rax+88h]
0x1800c192c  add     r8, rdx
0x1800c192f  call    ??$assign@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *>(uchar *,uchar *)
0x1800c1934  mov     rcx, [rsp+118h+var_18]
0x1800c193c  xor     rcx, rsp; StackCookie
0x1800c193f  call    __security_check_cookie
0x1800c1944  mov     rbx, [rsp+118h+arg_0]
0x1800c194c  add     rsp, 110h
0x1800c1953  pop     rdi
0x1800c1954  retn
0x1800c1955  lea     rax, aCannotGetSigna; "Cannot get signature value"
0x1800c195c  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800c1961  lea     r9, word_18013A0B6
0x1800c1968  mov     [rsp+118h+var_F0], 80510019h; unsigned int
0x1800c1970  lea     r8, aNoFilename; "(no filename)"
0x1800c1977  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800c197c  mov     [rsp+118h+var_F8], 682h; unsigned int
0x1800c1984  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c1989  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c1990  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800c1995  call    _CxxThrowException_0
```
