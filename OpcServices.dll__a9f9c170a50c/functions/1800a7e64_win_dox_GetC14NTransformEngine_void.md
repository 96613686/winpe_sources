# win_dox::GetC14NTransformEngine(void)

- ea: `0x1800a7e64`
- end: `0x1800a7f65`
- name: `?GetC14NTransformEngine@win_dox@@YAP6AJPEBU_CRYPT_XML_ALGORITHM@@PEAU_CRYPT_XML_DATA_PROVIDER@@1@ZXZ`
- size: `257`
- prototype: `int (*__fastcall(win_dox *__hidden this))(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a62cc`

## callees

- `0x180018c2c`
- `0x1800517a0`
- `0x1800a7e64`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `CRYPTXML!CryptXmlGetTransforms` at `0x1800a7eb9`
- `CRYPTXML!CryptXmlGetTransforms` at `0x1800a7eb9`

## string_xrefs

- `0x1800a7ee3`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`

## pseudocode

```c
int (*__fastcall win_dox::GetC14NTransformEngine(
        win_dox *this))(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *)
{
  HRESULT Transforms; // eax
  int v3; // edx
  const char *v4; // r8
  unsigned int v5; // r9d
  __int64 i; // rcx
  PCRYPT_XML_TRANSFORM_INFO v7; // r9
  LPCWSTR wszAlgorithm; // rax
  char *v9; // r10
  int v10; // r8d
  int v11; // edx
  CRYPT_XML_TRANSFORM_CHAIN_CONFIG *ppConfig; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  if ( !qword_1801C5268 )
  {
    ppConfig = 0;
    Transforms = CryptXmlGetTransforms((const CRYPT_XML_TRANSFORM_CHAIN_CONFIG **)&ppConfig);
    if ( Transforms < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)Transforms, v3, v4, v5);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= ppConfig->cTransformInfo )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x164u,
          0x8000FFFF,
          (struct win_musl::TStringEllipseBase *)L"Cannot find C14N transform engine.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v7 = ppConfig->rgpTransformInfo[i];
      wszAlgorithm = v7->wszAlgorithm;
      v9 = (char *)((char *)L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315" - (char *)wszAlgorithm);
      do
      {
        v10 = *(unsigned __int16 *)&v9[(_QWORD)wszAlgorithm];
        v11 = *wszAlgorithm - v10;
        if ( v11 )
          break;
        ++wszAlgorithm;
      }
      while ( v10 );
      if ( !v11 )
        break;
    }
    qword_1801C5268 = (__int64)v7->pfnCreateTransform;
  }
  return (int (*)(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *))qword_1801C5268;
}

```

## disassembly

```asm
0x1800a7e64  push    rbx
0x1800a7e66  sub     rsp, 100h
0x1800a7e6d  mov     rax, cs:__security_cookie
0x1800a7e74  xor     rax, rsp
0x1800a7e77  mov     [rsp+108h+var_18], rax
0x1800a7e7f  mov     rax, cs:qword_1801C5268
0x1800a7e86  test    rax, rax
0x1800a7e89  jz      short loc_1800A7EAB
0x1800a7e8b  mov     rax, cs:qword_1801C5268
0x1800a7e92  mov     rcx, [rsp+108h+var_18]
0x1800a7e9a  xor     rcx, rsp; StackCookie
0x1800a7e9d  call    __security_check_cookie
0x1800a7ea2  add     rsp, 100h
0x1800a7ea9  pop     rbx
0x1800a7eaa  retn
0x1800a7eab  lea     rcx, [rsp+108h+ppConfig]; ppConfig
0x1800a7eb0  mov     [rsp+108h+ppConfig], 0
0x1800a7eb9  call    cs:__imp_CryptXmlGetTransforms
0x1800a7ebf  test    eax, eax
0x1800a7ec1  jns     short loc_1800A7ECB
0x1800a7ec3  mov     ecx, eax; this
0x1800a7ec5  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a7ecb  mov     rax, [rsp+108h+ppConfig]
0x1800a7ed0  xor     ecx, ecx
0x1800a7ed2  mov     rbx, [rax+8]
0x1800a7ed6  mov     r11d, [rax+4]
0x1800a7eda  cmp     ecx, r11d
0x1800a7edd  jnb     short loc_1800A7F1F
0x1800a7edf  mov     r9, [rbx+rcx*8]
0x1800a7ee3  lea     r10, ?gc_C14NTransform@Value@DigitalSignatures@win_musl@@3QB_WB; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x1800a7eea  mov     rax, [r9+8]
0x1800a7eee  sub     r10, rax
0x1800a7ef1  movzx   edx, word ptr [rax]
0x1800a7ef4  movzx   r8d, word ptr [rax+r10]
0x1800a7ef9  sub     edx, r8d
0x1800a7efc  jnz     short loc_1800A7F07
0x1800a7efe  add     rax, 2
0x1800a7f02  test    r8d, r8d
0x1800a7f05  jnz     short loc_1800A7EF1
0x1800a7f07  test    edx, edx
0x1800a7f09  jz      short loc_1800A7F0F
0x1800a7f0b  inc     ecx
0x1800a7f0d  jmp     short loc_1800A7EDA
0x1800a7f0f  mov     rax, [r9+18h]
0x1800a7f13  mov     cs:qword_1801C5268, rax
0x1800a7f1a  jmp     loc_1800A7E8B
0x1800a7f1f  lea     rax, aCannotFindC14n; "Cannot find C14N transform engine."
0x1800a7f26  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800a7f2b  lea     r9, word_18013A0B6
0x1800a7f32  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800a7f3a  lea     r8, aNoFilename; "(no filename)"
0x1800a7f41  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800a7f46  mov     [rsp+108h+var_E8], 164h; unsigned int
0x1800a7f4e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a7f53  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a7f5a  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800a7f5f  call    _CxxThrowException_0
```
