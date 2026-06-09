# Protector::Bio::AddBioProtector(unsigned __int64,unsigned __int64)

- ea: `0x1800447cc`
- end: `0x180044a53`
- name: `?AddBioProtector@Bio@Protector@@AEAAJ_K0@Z`
- size: `647`
- prototype: `__int64 __fastcall(Protector::Bio *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044a60`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180011c1c`
- `0x180017f94`
- `0x1800183c4`
- `0x18001cbe8`
- `0x1800273c4`
- `0x18002bccc`
- `0x18002d090`
- `0x18002dc44`
- `0x18003b778`
- `0x180044220`
- `0x1800447cc`
- `0x180064a54`
- `0x180066934`
- `0x1800752b4`
- `0x180075d58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044846`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044846`
- `bcrypt!BCryptGenRandom` at `0x1800448b9`
- `bcrypt!BCryptGenRandom` at `0x1800448b9`

## string_xrefs

- `0x180044863`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x1800448cd`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x18004491d`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x1800449b6`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Protector::Bio::AddBioProtector(Protector::Bio *this, __int64 a2, __int64 a3)
{
  const WCHAR *v7; // rax
  BOOL v8; // ebx
  const char *v9; // r9
  int LastError; // ebx
  HLOCAL v11; // rcx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  HLOCAL v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h]
  PUCHAR pbBuffer; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[744]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  if ( !NgcUtils::IsNormalBioProtectorEnabled(this) )
    return 2147942450LL;
  hMem = 0;
  Sid[0] = &hMem;
  Sid[1] = 0;
  LOBYTE(v19) = 1;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
  v8 = ConvertStringSidToSidW(v7, &Sid[1]);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(Sid);
  if ( !v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3A7,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
                  v9);
LABEL_5:
    v11 = hMem;
    hMem = 0;
    if ( v11 )
      LocalFree(v11);
    return (unsigned int)LastError;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    &pbBuffer,
    32);
  v12 = BCryptGenRandom(0, pbBuffer, v21 - (_DWORD)pbBuffer, 2u);
  if ( v12 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x3AF,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
                  (const char *)(unsigned int)v12,
                  v16);
LABEL_10:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&pbBuffer);
    goto LABEL_5;
  }
  *(_OWORD *)Sid = 0;
  v19 = 0;
  LastError = NgcUtils::BioProtect(hMem);
  if ( LastError < 0 )
  {
    v13 = 949;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
      (const char *)(unsigned int)LastError,
      v16);
LABEL_14:
    std::vector<unsigned char>::_Tidy(Sid);
    goto LABEL_10;
  }
  v16 = v21 - (_DWORD)pbBuffer;
  LastError = NgcIsoTrustlet::AddProtector((char *)this + 8, 2, a2, a3);
  if ( LastError < 0 )
  {
    v13 = 957;
    goto LABEL_13;
  }
  Properties::BioProtector::BioProtector((Properties::BioProtector *)v22);
  v14 = NgcIsoTrustlet::ExportSecretStore((char *)this + 8, 2, v23);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
      (const char *)(unsigned int)v14,
      v16);
    Properties::BioProtector::~BioProtector((Properties::BioProtector *)v22);
    goto LABEL_14;
  }
  std::vector<unsigned char>::operator=(v22, Sid);
  Properties::BioProtector::operator=((char *)this + 56, v22);
  Properties::BioProtector::~BioProtector((Properties::BioProtector *)v22);
  std::vector<unsigned char>::_Tidy(Sid);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&pbBuffer);
  v15 = hMem;
  hMem = 0;
  if ( v15 )
    LocalFree(v15);
  return 0;
}

```

## disassembly

```asm
0x1800447cc  mov     [rsp-8+arg_18], rbx
0x1800447d1  push    rbp
0x1800447d2  push    rsi
0x1800447d3  push    rdi
0x1800447d4  push    r14
0x1800447d6  push    r15
0x1800447d8  lea     rbp, [rsp-290h]
0x1800447e0  sub     rsp, 390h
0x1800447e7  mov     rax, cs:__security_cookie
0x1800447ee  xor     rax, rsp
0x1800447f1  mov     [rbp+2B0h+var_30], rax
0x1800447f8  mov     r15, r8
0x1800447fb  mov     r14, rdx
0x1800447fe  mov     rdi, rcx
0x180044801  call    ?IsNormalBioProtectorEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNormalBioProtectorEnabled(void)
0x180044806  test    al, al
0x180044808  jnz     short loc_180044814
0x18004480a  mov     eax, 80070032h
0x18004480f  jmp     loc_180044A2D
0x180044814  mov     [rsp+3B0h+hMem], 0
0x18004481d  lea     rax, [rsp+3B0h+hMem]
0x180044822  mov     [rsp+3B0h+Sid], rax
0x180044827  mov     [rsp+3B0h+Sid+8], 0
0x180044830  mov     byte ptr [rsp+3B0h+var_358], 1
0x180044835  lea     rcx, [rdi+18h]
0x180044839  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004483e  lea     rdx, [rsp+3B0h+Sid+8]; Sid
0x180044843  mov     rcx, rax; StringSid
0x180044846  call    cs:__imp_ConvertStringSidToSidW
0x18004484c  mov     ebx, eax
0x18004484e  lea     rcx, [rsp+3B0h+Sid]
0x180044853  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180044858  test    ebx, ebx
0x18004485a  jnz     short loc_180044896
0x18004485c  mov     rcx, [rbp+2B8h]; this
0x180044863  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004486a  mov     edx, 3A7h; void *
0x18004486f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044874  mov     ebx, eax
0x180044876  mov     rcx, [rsp+3B0h+hMem]; hMem
0x18004487b  mov     [rsp+3B0h+hMem], 0
0x180044884  test    rcx, rcx
0x180044887  jz      short loc_18004488F
0x180044889  call    cs:__imp_LocalFree
0x18004488f  mov     eax, ebx
0x180044891  jmp     loc_180044A2D
0x180044896  mov     edx, 20h ; ' '
0x18004489b  lea     rcx, [rsp+3B0h+pbBuffer]
0x1800448a0  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x1800448a5  nop
0x1800448a6  mov     rdx, [rsp+3B0h+pbBuffer]; pbBuffer
0x1800448ab  mov     r8d, dword ptr [rsp+3B0h+var_348]
0x1800448b0  sub     r8d, edx; cbBuffer
0x1800448b3  xor     ecx, ecx; hAlgorithm
0x1800448b5  lea     r9d, [rcx+2]; dwFlags
0x1800448b9  call    cs:__imp_BCryptGenRandom
0x1800448bf  test    eax, eax
0x1800448c1  jns     short loc_1800448EC
0x1800448c3  mov     rcx, [rbp+2B8h]; this
0x1800448ca  mov     r9d, eax; char *
0x1800448cd  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800448d4  mov     edx, 3AFh; void *
0x1800448d9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800448de  mov     ebx, eax
0x1800448e0  lea     rcx, [rsp+3B0h+pbBuffer]
0x1800448e5  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800448ea  jmp     short loc_180044876
0x1800448ec  xorps   xmm0, xmm0
0x1800448ef  movdqu  xmmword ptr [rsp+3B0h+Sid], xmm0
0x1800448f5  mov     [rsp+3B0h+var_358], 0
0x1800448fe  lea     r8, [rsp+3B0h+Sid]
0x180044903  lea     rdx, [rsp+3B0h+pbBuffer]
0x180044908  mov     rcx, [rsp+3B0h+hMem]
0x18004490d  call    ?BioProtect@NgcUtils@@YAJQEAXAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV?$vector@EV?$allocator@E@std@@@3@@Z; NgcUtils::BioProtect(void * const,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar> *)
0x180044912  mov     ebx, eax
0x180044914  test    eax, eax
0x180044916  jns     short loc_180044940
0x180044918  mov     edx, 3B5h; void *
0x18004491d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180044924  mov     r9d, ebx; char *
0x180044927  mov     rcx, [rbp+2B8h]; this
0x18004492e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044933  nop
0x180044934  lea     rcx, [rsp+3B0h+Sid]
0x180044939  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004493e  jmp     short loc_1800448E0
0x180044940  mov     rcx, [rsp+3B0h+pbBuffer]
0x180044945  mov     rax, [rsp+3B0h+var_348]
0x18004494a  sub     rax, rcx
0x18004494d  mov     [rsp+3B0h+var_378], 0
0x180044956  mov     [rsp+3B0h+var_380], 0
0x18004495f  mov     [rsp+3B0h+var_388], rcx
0x180044964  mov     qword ptr [rsp+3B0h+var_390], rax; int
0x180044969  mov     r9, r15
0x18004496c  mov     r8, r14
0x18004496f  mov     edx, 2
0x180044974  lea     rcx, [rdi+8]
0x180044978  call    ?AddProtector@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@_K22PEBEPEAKPEAPEAE@Z; NgcIsoTrustlet::AddProtector(_GUID const &,NgcCtnrProtectorId,unsigned __int64,unsigned __int64,unsigned __int64,uchar const *,ulong *,uchar * *)
0x18004497d  mov     ebx, eax
0x18004497f  test    eax, eax
0x180044981  jns     short loc_18004498A
0x180044983  mov     edx, 3BDh
0x180044988  jmp     short loc_18004491D
0x18004498a  lea     rcx, [rbp+2B0h+var_330]; this
0x18004498e  call    ??0BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::BioProtector(void)
0x180044993  nop
0x180044994  lea     r8, [rbp+2B0h+var_318]
0x180044998  mov     edx, 2
0x18004499d  lea     rcx, [rdi+8]
0x1800449a1  call    ?ExportSecretStore@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@PEAUSecretStore@Properties@@@Z; NgcIsoTrustlet::ExportSecretStore(_GUID const &,NgcCtnrProtectorId,Properties::SecretStore *)
0x1800449a6  mov     ebx, eax
0x1800449a8  test    eax, eax
0x1800449aa  jns     short loc_1800449D6
0x1800449ac  mov     rcx, [rbp+2B8h]; this
0x1800449b3  mov     r9d, eax; char *
0x1800449b6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800449bd  mov     edx, 3C3h; void *
0x1800449c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800449c7  nop
0x1800449c8  lea     rcx, [rbp+2B0h+var_330]; this
0x1800449cc  call    ??1BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::~BioProtector(void)
0x1800449d1  jmp     loc_180044934
0x1800449d6  lea     rdx, [rsp+3B0h+Sid]
0x1800449db  lea     rcx, [rbp+2B0h+var_330]
0x1800449df  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800449e4  lea     rcx, [rdi+38h]
0x1800449e8  lea     rdx, [rbp+2B0h+var_330]
0x1800449ec  call    ??4BioProtector@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::BioProtector::operator=(Properties::BioProtector &&)
0x1800449f1  nop
0x1800449f2  lea     rcx, [rbp+2B0h+var_330]; this
0x1800449f6  call    ??1BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::~BioProtector(void)
0x1800449fb  nop
0x1800449fc  lea     rcx, [rsp+3B0h+Sid]
0x180044a01  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180044a06  nop
0x180044a07  lea     rcx, [rsp+3B0h+pbBuffer]
0x180044a0c  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180044a11  nop
0x180044a12  mov     rcx, [rsp+3B0h+hMem]; hMem
0x180044a17  mov     [rsp+3B0h+hMem], 0
0x180044a20  test    rcx, rcx
0x180044a23  jz      short loc_180044A2B
0x180044a25  call    cs:__imp_LocalFree
0x180044a2b  xor     eax, eax
0x180044a2d  mov     rcx, [rbp+2B0h+var_30]
0x180044a34  xor     rcx, rsp; StackCookie
0x180044a37  call    __security_check_cookie
0x180044a3c  mov     rbx, [rsp+3B0h+arg_18]
0x180044a44  add     rsp, 390h
0x180044a4b  pop     r15
0x180044a4d  pop     r14
0x180044a4f  pop     rdi
0x180044a50  pop     rsi
0x180044a51  pop     rbp
0x180044a52  retn
```
