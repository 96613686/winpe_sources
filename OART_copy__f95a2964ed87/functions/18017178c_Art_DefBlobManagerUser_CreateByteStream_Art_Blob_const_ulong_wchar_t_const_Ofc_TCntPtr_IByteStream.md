# Art::DefBlobManagerUser::CreateByteStream(Art::Blob const &,ulong,wchar_t const *,Ofc::TCntPtr<IByteStream> &)

- ea: `0x18017178c`
- end: `0x180171cf6`
- name: `?CreateByteStream@DefBlobManagerUser@Art@@KAXAEBVBlob@2@KPEB_WAEAV?$TCntPtr@UIByteStream@@@Ofc@@@Z`
- size: `1386`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1801703f0`
- `0x18053d150`

## callees

- `0x180019a9c`
- `0x180019e80`
- `0x180084c30`
- `0x180134460`
- `0x180141a9c`
- `0x18015c1b0`
- `0x180171530`
- `0x180171678`
- `0x180171730`
- `0x18017178c`
- `0x180171d00`
- `0x180278e70`
- `0x180279050`
- `0x1802d56d0`
- `0x18035eea4`
- `0x180433a68`
- `0x180767674`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180171bdd`
- `KERNEL32!GetLastError` at `0x180171c28`
- `KERNEL32!GetLastError` at `0x180171bdd`
- `KERNEL32!GetLastError` at `0x180171c28`
- `Mso30Win32Client!__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ` at `0x180171ace`
- `Mso30Win32Client!__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ` at `0x180171ace`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1801718ab`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x180171a7a`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1801718ab`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x180171a7a`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180171c66`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180171c66`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x18017198c`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x18017198c`
- `Mso20Win32Client!__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180171923`
- `Mso20Win32Client!__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x180171923`
- `Mso20Win32Client!__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z` at `0x180171825`
- `Mso20Win32Client!__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z` at `0x180171825`
- `Mso20Win32Client!__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z` at `0x18017180b`
- `Mso20Win32Client!__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z` at `0x18017180b`

## string_xrefs

- `0x180171bb1`: `DefBlobManagerUser::CreateByteStream: Exception while getting temp file path`
- `0x180171b20`: `DefBlobManagerUser::CreateByteStream: Exception while creating protected temp file byte stream`
- `0x180171bfc`: `DefBlobManagerUser::CreateByteStream: Exception while generating randon file name`
- `0x1801719da`: `DefBlobManagerUser::CreateByteStream: Exception while getting temp file byte stream`
- `0x180171cac`: `DefBlobManagerUser::CreateByteStream: Exception while creating temp file byte stream`

## pseudocode

```c
void __fastcall Art::DefBlobManagerUser::CreateByteStream(
        __int64 a1,
        char a2,
        const wchar_t *a3,
        struct IByteStream **a4)
{
  const wchar_t *v5; // r14
  void **v6; // r15
  __int64 v7; // rsi
  wchar_t *v8; // rbx
  int v9; // r12d
  int v10; // eax
  int v11; // ecx
  struct Mso::EnterpriseDataProtection::EnterpriseIdentity *v12; // r8
  bool v13; // si
  unsigned int v14; // esi
  int TempFileByteStream2; // eax
  int v16; // r9d
  int v17; // esi
  int ByteStream; // eax
  int v19; // r9d
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // r12
  __int64 i; // r14
  Art *v24; // rcx
  const wchar_t *Identity; // rax
  int ProtectedTempFileByteStream; // eax
  int v27; // r9d
  struct Ofc::XString *v28; // rax
  signed int LastError; // eax
  signed int v30; // eax
  const char *v31; // [rsp+30h] [rbp-D0h] BYREF
  const char *v32; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-C0h]
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v36; // [rsp+50h] [rbp-B0h] BYREF
  void **v37; // [rsp+58h] [rbp-A8h] BYREF
  const char *v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h]
  __int16 v40; // [rsp+6Ch] [rbp-94h]
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v44[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h]
  wchar_t v46[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a3;
  v31 = (const char *)a3;
  LOBYTE(v6) = a2;
  v7 = a1;
  v35 = a1;
  if ( (a2 & 0x20) != 0 )
  {
    Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v36, *(const wchar_t **)(a1 + 40));
    v8 = v36;
    v9 = 2;
    v10 = *((_DWORD *)v36 - 1) / 2;
    if ( v10 <= 0 )
      goto LABEL_3;
    goto LABEL_19;
  }
  ByteStream = MsoHrGetByteStream(a2, 0, a4);
  v8 = (wchar_t *)(unsigned int)ByteStream;
  if ( ByteStream < 0 )
  {
    v38 = "SH_ErrorCode";
    v39 = ByteStream;
    v9 = 4;
    v40 = 4;
    v41 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v41) = 0;
    v6 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
    v37 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
    v32 = "DefBlobManagerUser::CreateByteStream: Exception while getting temp file byte stream";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
      507826183,
      48,
      10,
      v19,
      (__int64)&v32,
      (__int64)&v37);
    std::wstring::~wstring(&v41);
    Ofc::CHResultException::ThrowTag((int)v8, 0x1E44D006u);
LABEL_19:
    if ( v10 > 16 )
    {
      v28 = Ofc::XString::GetForInplaceWrite(&v36);
      *((_WORD *)v28 + 22) = 0;
      *((_DWORD *)v28 + 2) = 32;
      v8 = v36;
    }
    v20 = 1;
    v21 = (unsigned int)(*((int *)v8 - 1) >> 31);
    LODWORD(v21) = *((_DWORD *)v8 - 1) % v9;
    v22 = *((_DWORD *)v8 - 1) / v9;
    for ( i = 1; i < v22; ++i )
    {
      if ( (unsigned __int8)sub_180171678(v8[i], v21) )
        goto LABEL_33;
      ++v20;
    }
    v20 = -1;
LABEL_33:
    if ( v20 != -1 )
    {
      Ofc::CStr::TruncAt((Ofc::CStr *)&v36, v20);
      v8 = v36;
    }
    v5 = (const wchar_t *)v31;
    v7 = v35;
LABEL_3:
    if ( !MsoFGetSecureTempPathW(v46, 260) )
    {
      v32 = "DefBlobManagerUser::CreateByteStream: Exception while getting temp file path";
      Mso::Diagnostics::SendDiagnosticTrace<>(507826190, 48, 10, 2, (__int64)&v32);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Ofc::CHResultException::ThrowTag(LastError, 0x1E44D00Du);
      __debugbreak();
    }
    if ( MsoFGenerateRandomFilename(v46, 260, v8) )
    {
      v11 = (((((unsigned __int8)v6 & 1) == 0) << 17) + 65538) | 0x80000;
      if ( ((unsigned __int8)v6 & 0x10) == 0 )
        v11 = ((((unsigned __int8)v6 & 1) == 0) << 17) + 65538;
      v33 = v11;
      Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v32, *(const wchar_t **)(v7 + 24));
      Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v35, v5);
      v43 = 0;
      v44[0] = 0;
      v44[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v44[0]) = 0;
      v45 = 0;
      v31 = 0;
      v34 = 505546467;
      Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(
        (Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v43,
        &word_180B454F0,
        (const struct MsoReserveTag *)&v34);
      if ( !(unsigned __int8)Art::FGetEDPHelper(&v31) )
      {
        if ( v31 )
          (**(void (__fastcall ***)(const char *, __int64))v31)(v31, 1);
        v13 = 0;
        goto LABEL_11;
      }
      v34 = 505538194;
      Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(
        (Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v43,
        &word_180B454F0,
        (const struct MsoReserveTag *)&v34);
      if ( !Art::IsEDPEnabled(v24) )
        goto LABEL_26;
    }
    else
    {
      v32 = "DefBlobManagerUser::CreateByteStream: Exception while generating randon file name";
      Mso::Diagnostics::SendDiagnosticTrace<>(507826188, 48, 10, 2, (__int64)&v32);
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      Ofc::CHResultException::ThrowTag(v30, 0x1E44D00Bu);
    }
    if ( (unsigned __int8)Art::IEDPHelper::FGetEnterpriseIdentity<Ofc::CVarStr>(&v32, &v43) )
    {
      v13 = v43 != 1;
LABEL_27:
      if ( v31 )
        (**(void (__fastcall ***)(const char *, __int64))v31)(v31, 1);
LABEL_11:
      if ( v13
        || *(_DWORD *)(v35 - 4) / 2 > 0 && Art::FGetIsProtected((Art *)&v35, (const struct Ofc::CVarStr *)&v43, v12) )
      {
        Identity = Mso::EnterpriseDataProtection::EnterpriseIdentity::GetIdentity((Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v43);
        v14 = v33;
        ProtectedTempFileByteStream = Art::HrCreateProtectedTempFileByteStream(Identity, v46, v33, a4);
        if ( ProtectedTempFileByteStream >= 0 )
        {
LABEL_15:
          std::wstring::~wstring(v44);
          Ofc::XString::Release((Ofc::XString *)(v35 - 12));
          Ofc::XString::Release((Ofc::XString *)(v32 - 12));
          Ofc::XString::Release((Ofc::XString *)(v8 - 6));
          return;
        }
        v38 = "SH_ErrorCode";
        v39 = ProtectedTempFileByteStream;
        v40 = 4;
        v41 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v41) = 0;
        v37 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
        v31 = "DefBlobManagerUser::CreateByteStream: Exception while creating protected temp file byte stream";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
          507826186,
          48,
          10,
          v27,
          (__int64)&v31,
          (__int64)&v37);
        std::wstring::~wstring(&v41);
      }
      else
      {
        v14 = v33;
      }
      TempFileByteStream2 = MsoHrGetTempFileByteStream2(v46, v14, a4);
      v17 = TempFileByteStream2;
      if ( TempFileByteStream2 < 0 )
      {
        v38 = "SH_ErrorCode";
        v39 = TempFileByteStream2;
        v40 = 4;
        v41 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v41) = 0;
        v37 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
        v31 = "DefBlobManagerUser::CreateByteStream: Exception while creating temp file byte stream";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
          507826185,
          48,
          10,
          v16,
          (__int64)&v31,
          (__int64)&v37);
        std::wstring::~wstring(&v41);
        Ofc::CHResultException::ThrowTag(v17, 0x1E44D008u);
        __debugbreak();
      }
      goto LABEL_15;
    }
    Mso::Diagnostics::SendWarningTag(506860180, 144);
LABEL_26:
    v13 = 0;
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x18017178c  push    rbp
0x18017178e  push    rbx
0x18017178f  push    rsi
0x180171790  push    rdi
0x180171791  push    r12
0x180171793  push    r13
0x180171795  push    r14
0x180171797  push    r15
0x180171799  lea     rbp, [rsp-1E8h]
0x1801717a1  sub     rsp, 2E8h
0x1801717a8  mov     rax, cs:__security_cookie
0x1801717af  xor     rax, rsp
0x1801717b2  mov     [rbp+220h+var_50], rax
0x1801717b9  mov     r13, r9
0x1801717bc  mov     r14, r8
0x1801717bf  mov     [rsp+320h+var_2F0], r8
0x1801717c4  mov     r15d, edx
0x1801717c7  mov     rsi, rcx
0x1801717ca  mov     [rsp+320h+var_2D8], rcx
0x1801717cf  test    dl, 20h
0x1801717d2  jz      loc_180171984
0x1801717d8  mov     rdx, [rcx+28h]; wchar_t *
0x1801717dc  lea     rcx, [rsp+320h+var_2D0]; this
0x1801717e1  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x1801717e6  mov     rbx, [rsp+320h+var_2D0]
0x1801717eb  mov     eax, [rbx-4]
0x1801717ee  cdq
0x1801717ef  mov     r12d, 2
0x1801717f5  idiv    r12d
0x1801717f8  xor     edi, edi
0x1801717fa  test    eax, eax
0x1801717fc  jg      loc_180171A25
0x180171802  mov     edx, 104h
0x180171807  lea     rcx, [rbp+220h+var_260]
0x18017180b  call    cs:__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z; MsoFGetSecureTempPathW(wchar_t *,int)
0x180171811  test    eax, eax
0x180171813  jz      loc_180171BB1
0x180171819  mov     r8, rbx
0x18017181c  mov     edx, 104h
0x180171821  lea     rcx, [rbp+220h+var_260]
0x180171825  call    cs:__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z; MsoFGenerateRandomFilename(wchar_t *,int,wchar_t const *)
0x18017182b  test    eax, eax
0x18017182d  jz      loc_180171BFC
0x180171833  mov     eax, r15d
0x180171836  not     eax
0x180171838  and     eax, 1
0x18017183b  shl     eax, 11h
0x18017183e  add     eax, 10002h
0x180171843  mov     ecx, eax
0x180171845  bts     ecx, 13h
0x180171849  test    r15b, 10h
0x18017184d  cmovz   ecx, eax
0x180171850  mov     [rsp+320h+var_2E0], ecx
0x180171854  mov     rdx, [rsi+18h]; wchar_t *
0x180171858  lea     rcx, [rsp+320h+var_2E8]; this
0x18017185d  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x180171862  mov     rdx, r14; wchar_t *
0x180171865  lea     rcx, [rsp+320h+var_2D8]; this
0x18017186a  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x18017186f  mov     [rbp+220h+var_290], edi
0x180171872  xorps   xmm0, xmm0
0x180171875  movups  [rbp+220h+var_288], xmm0
0x180171879  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180171881  movdqu  [rbp+220h+var_278], xmm1
0x180171886  mov     word ptr [rbp+220h+var_288], di
0x18017188a  mov     [rbp+220h+var_268], rdi
0x18017188e  mov     [rsp+320h+var_2F0], rdi
0x180171893  mov     [rsp+320h+var_2DC], 1E2206E3h
0x18017189b  lea     r8, [rsp+320h+var_2DC]
0x1801718a0  lea     rdx, word_180B454F0
0x1801718a7  lea     rcx, [rbp+220h+var_290]
0x1801718ab  call    cs:__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z; Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(wchar_t const *,MsoReserveTag const &)
0x1801718b1  lea     rcx, [rsp+320h+var_2F0]
0x1801718b6  call    ?FGetEDPHelper@Art@@YA_NAEAV?$TOwnerPtr@VIEDPHelper@Art@@@Ofc@@@Z; Art::FGetEDPHelper(Ofc::TOwnerPtr<Art::IEDPHelper> &)
0x1801718bb  test    al, al
0x1801718bd  jnz     loc_180171A62
0x1801718c3  mov     rcx, [rsp+320h+var_2F0]
0x1801718c8  test    rcx, rcx
0x1801718cb  jz      short loc_1801718DE
0x1801718cd  mov     rax, [rcx]
0x1801718d0  mov     edx, 1
0x1801718d5  mov     rax, [rax]
0x1801718d8  call    cs:__guard_dispatch_icall_fptr
0x1801718de  mov     sil, dil
0x1801718e1  lea     r14, aShErrorcode; "SH_ErrorCode"
0x1801718e8  mov     r12d, 4
0x1801718ee  lea     r15, ??_7StructuredSystemMetadataErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable'
0x1801718f5  test    sil, sil
0x1801718f8  jnz     loc_180171ACA
0x1801718fe  mov     rax, [rsp+320h+var_2D8]
0x180171903  mov     eax, [rax-4]
0x180171906  cdq
0x180171907  lea     ecx, [r12-2]
0x18017190c  idiv    ecx
0x18017190e  test    eax, eax
0x180171910  jg      loc_180171AB4
0x180171916  mov     esi, [rsp+320h+var_2E0]
0x18017191a  mov     r8, r13
0x18017191d  mov     edx, esi
0x18017191f  lea     rcx, [rbp+220h+var_260]
0x180171923  call    cs:__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z; MsoHrGetTempFileByteStream2(wchar_t const *,ulong,IByteStream * *)
0x180171929  mov     esi, eax
0x18017192b  test    eax, eax
0x18017192d  js      loc_180171C7E
0x180171933  lea     rcx, [rbp+220h+var_288]
0x180171937  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017193c  mov     rcx, [rsp+320h+var_2D8]
0x180171941  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x180171945  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x18017194a  mov     rcx, [rsp+320h+var_2E8]
0x18017194f  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x180171953  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x180171958  lea     rcx, [rbx-0Ch]; this
0x18017195c  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x180171961  mov     rcx, [rbp+220h+var_50]
0x180171968  xor     rcx, rsp; StackCookie
0x18017196b  call    __security_check_cookie
0x180171970  add     rsp, 2E8h
0x180171977  pop     r15
0x180171979  pop     r14
0x18017197b  pop     r13
0x18017197d  pop     r12
0x18017197f  pop     rdi
0x180171980  pop     rsi
0x180171981  pop     rbx
0x180171982  pop     rbp
0x180171983  retn
0x180171984  mov     r8, r13
0x180171987  xor     edx, edx
0x180171989  mov     ecx, r15d
0x18017198c  call    cs:__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z; MsoHrGetByteStream(ulong,IByteStreamUser *,IByteStream * *)
0x180171992  mov     ebx, eax
0x180171994  xor     edi, edi
0x180171996  test    eax, eax
0x180171998  jns     short loc_180171961
0x18017199a  lea     r14, aShErrorcode; "SH_ErrorCode"
0x1801719a1  mov     [rsp+320h+var_2C0], r14
0x1801719a6  mov     [rsp+320h+var_2B8], eax
0x1801719aa  lea     r12d, [rdi+4]
0x1801719ae  mov     [rsp+320h+var_2B4], r12w
0x1801719b4  xorps   xmm0, xmm0
0x1801719b7  movups  [rsp+320h+var_2B0], xmm0
0x1801719bc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801719c4  movdqu  [rbp+220h+var_2A0], xmm1
0x1801719c9  mov     word ptr [rsp+320h+var_2B0], di
0x1801719ce  lea     r15, ??_7StructuredSystemMetadataErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable'
0x1801719d5  mov     [rsp+320h+var_2C8], r15
0x1801719da  lea     rax, aDefblobmanager_4; "DefBlobManagerUser::CreateByteStream: E"...
0x1801719e1  mov     [rsp+320h+var_2E8], rax
0x1801719e6  lea     rax, [rsp+320h+var_2C8]
0x1801719eb  mov     [rsp+320h+var_2F8], rax
0x1801719f0  lea     rax, [rsp+320h+var_2E8]
0x1801719f5  mov     [rsp+320h+var_300], rax
0x1801719fa  lea     edx, [rdi+30h]
0x1801719fd  mov     ecx, 1E44D007h
0x180171a02  lea     r8d, [rdi+0Ah]
0x180171a06  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEBD@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEBD@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<char const *> &&)
0x180171a0b  lea     rcx, [rsp+320h+var_2B0]
0x180171a10  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180171a15  mov     edx, 1E44D006h; unsigned int
0x180171a1a  mov     ecx, ebx; int
0x180171a1c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180171a21  nop
0x180171a22  jmp     short $+2
0x180171a24  nop
0x180171a25  cmp     eax, 10h
0x180171a28  jg      loc_180171B7F
0x180171a2e  mov     esi, 1
0x180171a33  mov     eax, [rbx-4]
0x180171a36  cdq
0x180171a37  idiv    r12d
0x180171a3a  movsxd  r12, eax
0x180171a3d  mov     r14d, esi
0x180171a40  cmp     r14, r12
0x180171a43  jge     loc_180171B62
0x180171a49  movzx   ecx, word ptr [rbx+r14*2]
0x180171a4e  call    sub_180171678
0x180171a53  test    al, al
0x180171a55  jnz     loc_180171B65
0x180171a5b  inc     esi
0x180171a5d  inc     r14
0x180171a60  jmp     short loc_180171A40
0x180171a62  mov     [rsp+320h+var_2DC], 1E21E692h
0x180171a6a  lea     r8, [rsp+320h+var_2DC]
0x180171a6f  lea     rdx, word_180B454F0
0x180171a76  lea     rcx, [rbp+220h+var_290]
0x180171a7a  call    cs:__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z; Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(wchar_t const *,MsoReserveTag const &)
0x180171a80  call    ?IsEDPEnabled@Art@@YA_NXZ; Art::IsEDPEnabled(void)
0x180171a85  test    al, al
0x180171a87  jnz     loc_180171C4A
0x180171a8d  mov     sil, dil
0x180171a90  mov     rcx, [rsp+320h+var_2F0]
0x180171a95  test    rcx, rcx
0x180171a98  jz      loc_1801718E1
0x180171a9e  mov     rax, [rcx]
0x180171aa1  mov     edx, 1
0x180171aa6  mov     rax, [rax]
0x180171aa9  call    cs:__guard_dispatch_icall_fptr
0x180171aaf  jmp     loc_1801718E1
0x180171ab4  lea     rdx, [rbp+220h+var_290]; struct Ofc::CVarStr *
0x180171ab8  lea     rcx, [rsp+320h+var_2D8]; this
0x180171abd  call    ?FGetIsProtected@Art@@YA_NAEBVCVarStr@Ofc@@AEAVEnterpriseIdentity@EnterpriseDataProtection@Mso@@@Z; Art::FGetIsProtected(Ofc::CVarStr const &,Mso::EnterpriseDataProtection::EnterpriseIdentity &)
0x180171ac2  test    al, al
0x180171ac4  jz      loc_180171916
0x180171aca  lea     rcx, [rbp+220h+var_290]
0x180171ace  call    cs:__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ; Mso::EnterpriseDataProtection::EnterpriseIdentity::GetIdentity(void)
0x180171ad4  mov     rcx, rax
0x180171ad7  mov     r9, r13
0x180171ada  mov     esi, [rsp+320h+var_2E0]
0x180171ade  mov     r8d, esi
0x180171ae1  lea     rdx, [rbp+220h+var_260]
0x180171ae5  call    ?HrCreateProtectedTempFileByteStream@Art@@YAJPEB_W0KAEAV?$TCntPtr@UIByteStream@@@Ofc@@@Z; Art::HrCreateProtectedTempFileByteStream(wchar_t const *,wchar_t const *,ulong,Ofc::TCntPtr<IByteStream> &)
0x180171aea  test    eax, eax
0x180171aec  jns     loc_180171933
0x180171af2  mov     [rsp+320h+var_2C0], r14
0x180171af7  mov     [rsp+320h+var_2B8], eax
0x180171afb  mov     [rsp+320h+var_2B4], r12w
0x180171b01  xorps   xmm0, xmm0
0x180171b04  movups  [rsp+320h+var_2B0], xmm0
0x180171b09  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180171b11  movdqu  [rbp+220h+var_2A0], xmm1
0x180171b16  mov     word ptr [rsp+320h+var_2B0], di
0x180171b1b  mov     [rsp+320h+var_2C8], r15
0x180171b20  lea     rax, aDefblobmanager; "DefBlobManagerUser::CreateByteStream: E"...
0x180171b27  mov     [rsp+320h+var_2F0], rax
0x180171b2c  lea     rax, [rsp+320h+var_2C8]
0x180171b31  mov     [rsp+320h+var_2F8], rax
0x180171b36  lea     rax, [rsp+320h+var_2F0]
0x180171b3b  mov     [rsp+320h+var_300], rax
0x180171b40  mov     edx, 30h ; '0'
0x180171b45  mov     ecx, 1E44D00Ah
0x180171b4a  lea     r8d, [rdx-26h]
0x180171b4e  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEBD@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEBD@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<char const *> &&)
0x180171b53  lea     rcx, [rsp+320h+var_2B0]
0x180171b58  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180171b5d  jmp     loc_18017191A
0x180171b62  or      esi, 0FFFFFFFFh
0x180171b65  cmp     esi, 0FFFFFFFFh
0x180171b68  jnz     short loc_180171B9E
0x180171b6a  mov     r12d, 2
0x180171b70  mov     r14, [rsp+320h+var_2F0]
0x180171b75  mov     rsi, [rsp+320h+var_2D8]
0x180171b7a  jmp     loc_180171802
0x180171b7f  lea     rcx, [rsp+320h+var_2D0]; wchar_t **
0x180171b84  call    ?GetForInplaceWrite@XString@Ofc@@SAAEAV12@AEAPEA_W@Z; Ofc::XString::GetForInplaceWrite(wchar_t * &)
0x180171b89  mov     [rax+2Ch], di
0x180171b8d  mov     dword ptr [rax+8], 20h ; ' '
0x180171b94  mov     rbx, [rsp+320h+var_2D0]
0x180171b99  jmp     loc_180171A2E
0x180171b9e  mov     edx, esi; int
0x180171ba0  lea     rcx, [rsp+320h+var_2D0]; this
0x180171ba5  call    ?TruncAt@CStr@Ofc@@QEAAXH@Z; Ofc::CStr::TruncAt(int)
0x180171baa  mov     rbx, [rsp+320h+var_2D0]
0x180171baf  jmp     short loc_180171B6A
0x180171bb1  lea     rax, aDefblobmanager_2; "DefBlobManagerUser::CreateByteStream: E"...
0x180171bb8  mov     [rsp+320h+var_2E8], rax
0x180171bbd  mov     r9d, r12d
0x180171bc0  lea     rax, [rsp+320h+var_2E8]
0x180171bc5  mov     [rsp+320h+var_300], rax
0x180171bca  mov     edx, 30h ; '0'
0x180171bcf  mov     ecx, 1E44D00Eh
0x180171bd4  lea     r8d, [rdx-26h]
0x180171bd8  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180171bdd  call    cs:__imp_GetLastError
0x180171be3  test    eax, eax
0x180171be5  jle     short loc_180171BEF
0x180171be7  movzx   eax, ax
0x180171bea  or      eax, 80070000h
0x180171bef  mov     edx, 1E44D00Dh; unsigned int
0x180171bf4  mov     ecx, eax; int
0x180171bf6  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180171bfb  int     3; Trap to Debugger
0x180171bfc  lea     rax, aDefblobmanager_3; "DefBlobManagerUser::CreateByteStream: E"...
0x180171c03  mov     [rsp+320h+var_2E8], rax
0x180171c08  mov     r9d, r12d
0x180171c0b  lea     rax, [rsp+320h+var_2E8]
0x180171c10  mov     [rsp+320h+var_300], rax
0x180171c15  mov     edx, 30h ; '0'
0x180171c1a  mov     ecx, 1E44D00Ch
0x180171c1f  lea     r8d, [rdx-26h]
0x180171c23  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180171c28  call    cs:__imp_GetLastError
0x180171c2e  test    eax, eax
0x180171c30  jle     short loc_180171C3A
0x180171c32  movzx   eax, ax
0x180171c35  or      eax, 80070000h
0x180171c3a  mov     edx, 1E44D00Bh; unsigned int
0x180171c3f  mov     ecx, eax; int
0x180171c41  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180171c46  nop
0x180171c47  jmp     short $+2
0x180171c49  nop
0x180171c4a  lea     rdx, [rbp+220h+var_290]
0x180171c4e  lea     rcx, [rsp+320h+var_2E8]
0x180171c53  call    ??$FGetEnterpriseIdentity@VCVarStr@Ofc@@@IEDPHelper@Art@@SA_NAEBVCVarStr@Ofc@@AEAVEnterpriseIdentity@EnterpriseDataProtection@Mso@@@Z; Art::IEDPHelper::FGetEnterpriseIdentity<Ofc::CVarStr>(Ofc::CVarStr const &,Mso::EnterpriseDataProtection::EnterpriseIdentity &)
0x180171c58  test    al, al
0x180171c5a  jnz     short loc_180171C71
0x180171c5c  mov     edx, 90h
0x180171c61  mov     ecx, 1E361294h
0x180171c66  call    cs:__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z; Mso::Diagnostics::SendWarningTag(ulong,Mso::Logging::Category)
  ... truncated ...
```
