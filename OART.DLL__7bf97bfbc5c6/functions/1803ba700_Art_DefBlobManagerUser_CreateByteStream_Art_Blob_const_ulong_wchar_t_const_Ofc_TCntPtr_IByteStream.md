# Art::DefBlobManagerUser::CreateByteStream(Art::Blob const &,ulong,wchar_t const *,Ofc::TCntPtr<IByteStream> &)

- ea: `0x1803ba700`
- end: `0x1803bac75`
- name: `?CreateByteStream@DefBlobManagerUser@Art@@KAXAEBVBlob@2@KPEB_WAEAV?$TCntPtr@UIByteStream@@@Ofc@@@Z`
- size: `1397`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1803013f0`
- `0x1803bc350`

## callees

- `0x180038180`
- `0x18006a868`
- `0x18006d020`
- `0x180070fe0`
- `0x180071720`
- `0x1800b2878`
- `0x1800d3a90`
- `0x1801aa600`
- `0x1801b09dc`
- `0x18030a760`
- `0x1803b5c8c`
- `0x1803ba668`
- `0x1803ba700`
- `0x1803bac80`
- `0x1803bacdc`
- `0x1803bad50`
- `0x1807573c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1803bab5b`
- `KERNEL32!GetLastError` at `0x1803baba6`
- `KERNEL32!GetLastError` at `0x1803bab5b`
- `KERNEL32!GetLastError` at `0x1803baba6`
- `Mso30Win32Client!__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ` at `0x1803baa85`
- `Mso30Win32Client!__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ` at `0x1803baa85`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1803ba81f`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1803ba9f1`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1803ba81f`
- `Mso30Win32Client!__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z` at `0x1803ba9f1`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1803babe5`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1803babe5`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x1803ba93d`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x1803ba93d`
- `Mso20Win32Client!__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x1803ba897`
- `Mso20Win32Client!__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z` at `0x1803ba897`
- `Mso20Win32Client!__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z` at `0x1803ba799`
- `Mso20Win32Client!__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z` at `0x1803ba799`
- `Mso20Win32Client!__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z` at `0x1803ba77f`
- `Mso20Win32Client!__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z` at `0x1803ba77f`

## string_xrefs

- `0x1803baad7`: `DefBlobManagerUser::CreateByteStream: Exception while creating protected temp file byte stream`
- `0x1803bab7a`: `DefBlobManagerUser::CreateByteStream: Exception while generating randon file name`
- `0x1803ba98b`: `DefBlobManagerUser::CreateByteStream: Exception while getting temp file byte stream`
- `0x1803bac2b`: `DefBlobManagerUser::CreateByteStream: Exception while creating temp file byte stream`
- `0x1803bab2f`: `DefBlobManagerUser::CreateByteStream: Exception while getting temp file path`

## pseudocode

```c
void __fastcall Art::DefBlobManagerUser::CreateByteStream(
        __int64 a1,
        char a2,
        const wchar_t *a3,
        struct IByteStream **a4)
{
  const wchar_t *v5; // r14
  __int64 v7; // rsi
  wchar_t *v8; // rbx
  int v9; // eax
  int v10; // ecx
  struct Mso::EnterpriseDataProtection::EnterpriseIdentity *v11; // r8
  bool v12; // si
  unsigned int v13; // esi
  int TempFileByteStream2; // eax
  int v15; // r9d
  int v16; // esi
  int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // r12
  __int64 i; // r14
  int ByteStream; // eax
  int v22; // r9d
  Art *v23; // rcx
  struct Ofc::XString *v24; // rax
  const wchar_t *Identity; // rax
  int ProtectedTempFileByteStream; // eax
  int v27; // r9d
  signed int LastError; // eax
  signed int v29; // eax
  const char *v30; // [rsp+30h] [rbp-D0h] BYREF
  const char *v31; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v35; // [rsp+50h] [rbp-B0h] BYREF
  void **v36; // [rsp+58h] [rbp-A8h] BYREF
  const char *v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+68h] [rbp-98h]
  __int16 v39; // [rsp+6Ch] [rbp-94h]
  __int128 v40; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v43[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h]
  wchar_t v45[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a3;
  v30 = (const char *)a3;
  v7 = a1;
  v34 = a1;
  if ( (a2 & 0x20) != 0 )
  {
    Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v35, *(const wchar_t **)(a1 + 40));
    v8 = v35;
    v9 = *((_DWORD *)v35 - 1) / 2;
    if ( v9 > 0 )
    {
      if ( v9 > 16 )
      {
        v24 = Ofc::XString::GetForInplaceWrite(&v35);
        *((_WORD *)v24 + 22) = 0;
        *((_DWORD *)v24 + 2) = 32;
        v8 = v35;
      }
      v17 = 1;
      v18 = (unsigned int)(*((int *)v8 - 1) >> 31);
      LODWORD(v18) = *((_DWORD *)v8 - 1) % 2;
      v19 = *((_DWORD *)v8 - 1) / 2;
      for ( i = 1; i < v19; ++i )
      {
        if ( (unsigned __int8)sub_1803BAD50(v8[i], v18) )
          goto LABEL_30;
        ++v17;
      }
      v17 = -1;
LABEL_30:
      if ( v17 != -1 )
      {
        Ofc::CStr::TruncAt((Ofc::CStr *)&v35, v17);
        v8 = v35;
      }
      v5 = (const wchar_t *)v30;
      v7 = v34;
    }
    if ( !MsoFGetSecureTempPathW(v45, 260) )
    {
      v31 = "DefBlobManagerUser::CreateByteStream: Exception while getting temp file path";
      Mso::Diagnostics::SendDiagnosticTrace<>(507826190, 48, 10, 2, (__int64)&v31);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Ofc::CHResultException::ThrowTag(LastError, 0x1E44D00Du);
      __debugbreak();
    }
    if ( !MsoFGenerateRandomFilename(v45, 260, v8) )
    {
      v31 = "DefBlobManagerUser::CreateByteStream: Exception while generating randon file name";
      Mso::Diagnostics::SendDiagnosticTrace<>(507826188, 48, 10, 2, (__int64)&v31);
      v29 = GetLastError();
      if ( v29 > 0 )
        v29 = (unsigned __int16)v29 | 0x80070000;
      Ofc::CHResultException::ThrowTag(v29, 0x1E44D00Bu);
LABEL_42:
      if ( (unsigned __int8)Art::IEDPHelper::FGetEnterpriseIdentity<Ofc::CVarStr>(&v31, &v42) )
      {
        v12 = v42 != 1;
LABEL_27:
        if ( v30 )
          (**(void (__fastcall ***)(const char *, __int64))v30)(v30, 1);
LABEL_11:
        if ( v12
          || *(_DWORD *)(v34 - 4) / 2 > 0 && Art::FGetIsProtected((Art *)&v34, (const struct Ofc::CVarStr *)&v42, v11) )
        {
          Identity = Mso::EnterpriseDataProtection::EnterpriseIdentity::GetIdentity((Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v42);
          v13 = v32;
          ProtectedTempFileByteStream = Art::HrCreateProtectedTempFileByteStream(Identity, v45, v32, a4);
          if ( ProtectedTempFileByteStream >= 0 )
          {
LABEL_15:
            std::wstring::~wstring(v43);
            Ofc::XString::Release((Ofc::XString *)(v34 - 12));
            Ofc::XString::Release((Ofc::XString *)(v31 - 12));
            Ofc::XString::Release((Ofc::XString *)(v8 - 6));
            return;
          }
          v37 = "SH_ErrorCode";
          v38 = ProtectedTempFileByteStream;
          v39 = 4;
          v40 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v40) = 0;
          v36 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
          v30 = "DefBlobManagerUser::CreateByteStream: Exception while creating protected temp file byte stream";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
            507826186,
            48,
            10,
            v27,
            (__int64)&v30,
            (__int64)&v36);
          std::wstring::~wstring(&v40);
        }
        else
        {
          v13 = v32;
        }
        TempFileByteStream2 = MsoHrGetTempFileByteStream2(v45, v13, a4);
        v16 = TempFileByteStream2;
        if ( TempFileByteStream2 < 0 )
        {
          v37 = "SH_ErrorCode";
          v38 = TempFileByteStream2;
          v39 = 4;
          v40 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v40) = 0;
          v36 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
          v30 = "DefBlobManagerUser::CreateByteStream: Exception while creating temp file byte stream";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
            507826185,
            48,
            10,
            v15,
            (__int64)&v30,
            (__int64)&v36);
          std::wstring::~wstring(&v40);
          Ofc::CHResultException::ThrowTag(v16, 0x1E44D008u);
          __debugbreak();
        }
        goto LABEL_15;
      }
      Mso::Diagnostics::SendWarningTag(506860180, 144);
LABEL_26:
      v12 = 0;
      goto LABEL_27;
    }
    v10 = ((((a2 & 1) == 0) << 17) + 65538) | 0x80000;
    if ( (a2 & 0x10) == 0 )
      v10 = (((a2 & 1) == 0) << 17) + 65538;
    v32 = v10;
    Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v31, *(const wchar_t **)(v7 + 24));
    Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v34, v5);
    v42 = 0;
    v43[0] = 0;
    v43[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v43[0]) = 0;
    v44 = 0;
    v30 = 0;
    v33 = 505546467;
    Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(
      (Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v42,
      &word_180B89A10,
      (const struct MsoReserveTag *)&v33);
    if ( !(unsigned __int8)Art::FGetEDPHelper(&v30) )
    {
      if ( v30 )
        (**(void (__fastcall ***)(const char *, __int64))v30)(v30, 1);
      v12 = 0;
      goto LABEL_11;
    }
LABEL_25:
    v33 = 505538194;
    Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(
      (Mso::EnterpriseDataProtection::EnterpriseIdentity *)&v42,
      &word_180B89A10,
      (const struct MsoReserveTag *)&v33);
    if ( !Art::IsEDPEnabled(v23) )
      goto LABEL_26;
    goto LABEL_42;
  }
  ByteStream = MsoHrGetByteStream(a2, 0, a4);
  v8 = (wchar_t *)(unsigned int)ByteStream;
  if ( ByteStream < 0 )
  {
    v37 = "SH_ErrorCode";
    v38 = ByteStream;
    v39 = 4;
    v40 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v40) = 0;
    v36 = &Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable';
    v31 = "DefBlobManagerUser::CreateByteStream: Exception while getting temp file byte stream";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
      507826183,
      48,
      10,
      v22,
      (__int64)&v31,
      (__int64)&v36);
    std::wstring::~wstring(&v40);
    Ofc::CHResultException::ThrowTag((int)v8, 0x1E44D006u);
    goto LABEL_25;
  }
}

```

## disassembly

```asm
0x1803ba700  push    rbp
0x1803ba702  push    rbx
0x1803ba703  push    rsi
0x1803ba704  push    rdi
0x1803ba705  push    r12
0x1803ba707  push    r13
0x1803ba709  push    r14
0x1803ba70b  push    r15
0x1803ba70d  lea     rbp, [rsp-1E8h]
0x1803ba715  sub     rsp, 2E8h
0x1803ba71c  mov     rax, cs:__security_cookie
0x1803ba723  xor     rax, rsp
0x1803ba726  mov     [rbp+220h+var_50], rax
0x1803ba72d  mov     r13, r9
0x1803ba730  mov     r14, r8
0x1803ba733  mov     [rsp+320h+var_2F0], r8
0x1803ba738  mov     r15d, edx
0x1803ba73b  mov     rsi, rcx
0x1803ba73e  mov     [rsp+320h+var_2D8], rcx
0x1803ba743  test    dl, 20h
0x1803ba746  jz      loc_1803BA935
0x1803ba74c  mov     rdx, [rcx+28h]; wchar_t *
0x1803ba750  lea     rcx, [rsp+320h+var_2D0]; this
0x1803ba755  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x1803ba75a  mov     rbx, [rsp+320h+var_2D0]
0x1803ba75f  mov     eax, [rbx-4]
0x1803ba762  cdq
0x1803ba763  mov     r12d, 2
0x1803ba769  idiv    r12d
0x1803ba76c  xor     edi, edi
0x1803ba76e  test    eax, eax
0x1803ba770  jg      loc_1803BA8F8
0x1803ba776  mov     edx, 104h
0x1803ba77b  lea     rcx, [rbp+220h+var_260]
0x1803ba77f  call    cs:__imp_?MsoFGetSecureTempPathW@@YAHPEA_WH@Z; MsoFGetSecureTempPathW(wchar_t *,int)
0x1803ba785  test    eax, eax
0x1803ba787  jz      loc_1803BAB2F
0x1803ba78d  mov     r8, rbx
0x1803ba790  mov     edx, 104h
0x1803ba795  lea     rcx, [rbp+220h+var_260]
0x1803ba799  call    cs:__imp_?MsoFGenerateRandomFilename@@YAHPEA_WHPEB_W@Z; MsoFGenerateRandomFilename(wchar_t *,int,wchar_t const *)
0x1803ba79f  test    eax, eax
0x1803ba7a1  jz      loc_1803BAB7A
0x1803ba7a7  mov     eax, r15d
0x1803ba7aa  not     eax
0x1803ba7ac  and     eax, 1
0x1803ba7af  shl     eax, 11h
0x1803ba7b2  add     eax, 10002h
0x1803ba7b7  mov     ecx, eax
0x1803ba7b9  bts     ecx, 13h
0x1803ba7bd  test    r15b, 10h
0x1803ba7c1  cmovz   ecx, eax
0x1803ba7c4  mov     [rsp+320h+var_2E0], ecx
0x1803ba7c8  mov     rdx, [rsi+18h]; wchar_t *
0x1803ba7cc  lea     rcx, [rsp+320h+var_2E8]; this
0x1803ba7d1  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x1803ba7d6  mov     rdx, r14; wchar_t *
0x1803ba7d9  lea     rcx, [rsp+320h+var_2D8]; this
0x1803ba7de  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x1803ba7e3  mov     [rbp+220h+var_290], edi
0x1803ba7e6  xorps   xmm0, xmm0
0x1803ba7e9  movups  [rbp+220h+var_288], xmm0
0x1803ba7ed  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803ba7f5  movdqu  [rbp+220h+var_278], xmm1
0x1803ba7fa  mov     word ptr [rbp+220h+var_288], di
0x1803ba7fe  mov     [rbp+220h+var_268], rdi
0x1803ba802  mov     [rsp+320h+var_2F0], rdi
0x1803ba807  mov     [rsp+320h+var_2DC], 1E2206E3h
0x1803ba80f  lea     r8, [rsp+320h+var_2DC]
0x1803ba814  lea     rdx, word_180B89A10
0x1803ba81b  lea     rcx, [rbp+220h+var_290]
0x1803ba81f  call    cs:__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z; Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(wchar_t const *,MsoReserveTag const &)
0x1803ba825  lea     rcx, [rsp+320h+var_2F0]
0x1803ba82a  call    ?FGetEDPHelper@Art@@YA_NAEAV?$TOwnerPtr@VIEDPHelper@Art@@@Ofc@@@Z; Art::FGetEDPHelper(Ofc::TOwnerPtr<Art::IEDPHelper> &)
0x1803ba82f  test    al, al
0x1803ba831  jnz     loc_1803BA9D9
0x1803ba837  mov     rcx, [rsp+320h+var_2F0]
0x1803ba83c  test    rcx, rcx
0x1803ba83f  jz      short loc_1803BA852
0x1803ba841  mov     rax, [rcx]
0x1803ba844  mov     edx, 1
0x1803ba849  mov     rax, [rax]
0x1803ba84c  call    cs:__guard_dispatch_icall_fptr
0x1803ba852  mov     sil, dil
0x1803ba855  lea     r14, aShErrorcode; "SH_ErrorCode"
0x1803ba85c  mov     r12d, 4
0x1803ba862  lea     r15, ??_7StructuredSystemMetadataErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable'
0x1803ba869  test    sil, sil
0x1803ba86c  jnz     loc_1803BAA81
0x1803ba872  mov     rax, [rsp+320h+var_2D8]
0x1803ba877  mov     eax, [rax-4]
0x1803ba87a  cdq
0x1803ba87b  lea     ecx, [r12-2]
0x1803ba880  idiv    ecx
0x1803ba882  test    eax, eax
0x1803ba884  jg      loc_1803BAA6B
0x1803ba88a  mov     esi, [rsp+320h+var_2E0]
0x1803ba88e  mov     r8, r13
0x1803ba891  mov     edx, esi
0x1803ba893  lea     rcx, [rbp+220h+var_260]
0x1803ba897  call    cs:__imp_?MsoHrGetTempFileByteStream2@@YAJPEB_WKPEAPEAUIByteStream@@@Z; MsoHrGetTempFileByteStream2(wchar_t const *,ulong,IByteStream * *)
0x1803ba89d  mov     esi, eax
0x1803ba89f  test    eax, eax
0x1803ba8a1  js      loc_1803BABFD
0x1803ba8a7  lea     rcx, [rbp+220h+var_288]
0x1803ba8ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803ba8b0  mov     rcx, [rsp+320h+var_2D8]
0x1803ba8b5  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1803ba8b9  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803ba8be  mov     rcx, [rsp+320h+var_2E8]
0x1803ba8c3  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1803ba8c7  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803ba8cc  lea     rcx, [rbx-0Ch]; this
0x1803ba8d0  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803ba8d5  mov     rcx, [rbp+220h+var_50]
0x1803ba8dc  xor     rcx, rsp; StackCookie
0x1803ba8df  call    __security_check_cookie
0x1803ba8e4  add     rsp, 2E8h
0x1803ba8eb  pop     r15
0x1803ba8ed  pop     r14
0x1803ba8ef  pop     r13
0x1803ba8f1  pop     r12
0x1803ba8f3  pop     rdi
0x1803ba8f4  pop     rsi
0x1803ba8f5  pop     rbx
0x1803ba8f6  pop     rbp
0x1803ba8f7  retn
0x1803ba8f8  cmp     eax, 10h
0x1803ba8fb  jg      loc_1803BAA4C
0x1803ba901  mov     esi, 1
0x1803ba906  mov     eax, [rbx-4]
0x1803ba909  cdq
0x1803ba90a  idiv    r12d
0x1803ba90d  movsxd  r12, eax
0x1803ba910  mov     r14d, esi
0x1803ba913  cmp     r14, r12
0x1803ba916  jge     loc_1803BAA2B
0x1803ba91c  movzx   ecx, word ptr [rbx+r14*2]
0x1803ba921  call    sub_1803BAD50
0x1803ba926  test    al, al
0x1803ba928  jnz     loc_1803BAA2E
0x1803ba92e  inc     esi
0x1803ba930  inc     r14
0x1803ba933  jmp     short loc_1803BA913
0x1803ba935  mov     r8, r13
0x1803ba938  xor     edx, edx
0x1803ba93a  mov     ecx, r15d
0x1803ba93d  call    cs:__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z; MsoHrGetByteStream(ulong,IByteStreamUser *,IByteStream * *)
0x1803ba943  mov     ebx, eax
0x1803ba945  xor     edi, edi
0x1803ba947  test    eax, eax
0x1803ba949  jns     short loc_1803BA8D5
0x1803ba94b  lea     r14, aShErrorcode; "SH_ErrorCode"
0x1803ba952  mov     [rsp+320h+var_2C0], r14
0x1803ba957  mov     [rsp+320h+var_2B8], eax
0x1803ba95b  lea     r12d, [rdi+4]
0x1803ba95f  mov     [rsp+320h+var_2B4], r12w
0x1803ba965  xorps   xmm0, xmm0
0x1803ba968  movups  [rsp+320h+var_2B0], xmm0
0x1803ba96d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803ba975  movdqu  [rbp+220h+var_2A0], xmm1
0x1803ba97a  mov     word ptr [rsp+320h+var_2B0], di
0x1803ba97f  lea     r15, ??_7StructuredSystemMetadataErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::StructuredSystemMetadataErrorId::`vftable'
0x1803ba986  mov     [rsp+320h+var_2C8], r15
0x1803ba98b  lea     rax, aDefblobmanager_4; "DefBlobManagerUser::CreateByteStream: E"...
0x1803ba992  mov     [rsp+320h+var_2E8], rax
0x1803ba997  lea     rax, [rsp+320h+var_2C8]
0x1803ba99c  mov     [rsp+320h+var_2F8], rax
0x1803ba9a1  lea     rax, [rsp+320h+var_2E8]
0x1803ba9a6  mov     [rsp+320h+var_300], rax
0x1803ba9ab  lea     edx, [rdi+30h]
0x1803ba9ae  mov     ecx, 1E44D007h
0x1803ba9b3  lea     r8d, [rdi+0Ah]
0x1803ba9b7  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEBD@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEBD@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<char const *> &&)
0x1803ba9bc  lea     rcx, [rsp+320h+var_2B0]
0x1803ba9c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803ba9c6  mov     edx, 1E44D006h; unsigned int
0x1803ba9cb  mov     ecx, ebx; int
0x1803ba9cd  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1803ba9d2  nop
0x1803ba9d3  jmp     short loc_1803BA9D8
0x1803ba9d8  nop
0x1803ba9d9  mov     [rsp+320h+var_2DC], 1E21E692h
0x1803ba9e1  lea     r8, [rsp+320h+var_2DC]
0x1803ba9e6  lea     rdx, word_180B89A10
0x1803ba9ed  lea     rcx, [rbp+220h+var_290]
0x1803ba9f1  call    cs:__imp_?SetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEAAXPEB_WAEBVMsoReserveTag@@@Z; Mso::EnterpriseDataProtection::EnterpriseIdentity::SetIdentity(wchar_t const *,MsoReserveTag const &)
0x1803ba9f7  call    ?IsEDPEnabled@Art@@YA_NXZ; Art::IsEDPEnabled(void)
0x1803ba9fc  test    al, al
0x1803ba9fe  jnz     loc_1803BABC9
0x1803baa04  mov     sil, dil
0x1803baa07  mov     rcx, [rsp+320h+var_2F0]
0x1803baa0c  test    rcx, rcx
0x1803baa0f  jz      loc_1803BA855
0x1803baa15  mov     rax, [rcx]
0x1803baa18  mov     edx, 1
0x1803baa1d  mov     rax, [rax]
0x1803baa20  call    cs:__guard_dispatch_icall_fptr
0x1803baa26  jmp     loc_1803BA855
0x1803baa2b  or      esi, 0FFFFFFFFh
0x1803baa2e  cmp     esi, 0FFFFFFFFh
0x1803baa31  jnz     loc_1803BAB19
0x1803baa37  mov     r12d, 2
0x1803baa3d  mov     r14, [rsp+320h+var_2F0]
0x1803baa42  mov     rsi, [rsp+320h+var_2D8]
0x1803baa47  jmp     loc_1803BA776
0x1803baa4c  lea     rcx, [rsp+320h+var_2D0]; wchar_t **
0x1803baa51  call    ?GetForInplaceWrite@XString@Ofc@@SAAEAV12@AEAPEA_W@Z; Ofc::XString::GetForInplaceWrite(wchar_t * &)
0x1803baa56  mov     [rax+2Ch], di
0x1803baa5a  mov     dword ptr [rax+8], 20h ; ' '
0x1803baa61  mov     rbx, [rsp+320h+var_2D0]
0x1803baa66  jmp     loc_1803BA901
0x1803baa6b  lea     rdx, [rbp+220h+var_290]; struct Ofc::CVarStr *
0x1803baa6f  lea     rcx, [rsp+320h+var_2D8]; this
0x1803baa74  call    ?FGetIsProtected@Art@@YA_NAEBVCVarStr@Ofc@@AEAVEnterpriseIdentity@EnterpriseDataProtection@Mso@@@Z; Art::FGetIsProtected(Ofc::CVarStr const &,Mso::EnterpriseDataProtection::EnterpriseIdentity &)
0x1803baa79  test    al, al
0x1803baa7b  jz      loc_1803BA88A
0x1803baa81  lea     rcx, [rbp+220h+var_290]
0x1803baa85  call    cs:__imp_?GetIdentity@EnterpriseIdentity@EnterpriseDataProtection@Mso@@QEBAPEB_WXZ; Mso::EnterpriseDataProtection::EnterpriseIdentity::GetIdentity(void)
0x1803baa8b  mov     rcx, rax
0x1803baa8e  mov     r9, r13
0x1803baa91  mov     esi, [rsp+320h+var_2E0]
0x1803baa95  mov     r8d, esi
0x1803baa98  lea     rdx, [rbp+220h+var_260]
0x1803baa9c  call    ?HrCreateProtectedTempFileByteStream@Art@@YAJPEB_W0KAEAV?$TCntPtr@UIByteStream@@@Ofc@@@Z; Art::HrCreateProtectedTempFileByteStream(wchar_t const *,wchar_t const *,ulong,Ofc::TCntPtr<IByteStream> &)
0x1803baaa1  test    eax, eax
0x1803baaa3  jns     loc_1803BA8A7
0x1803baaa9  mov     [rsp+320h+var_2C0], r14
0x1803baaae  mov     [rsp+320h+var_2B8], eax
0x1803baab2  mov     [rsp+320h+var_2B4], r12w
0x1803baab8  xorps   xmm0, xmm0
0x1803baabb  movups  [rsp+320h+var_2B0], xmm0
0x1803baac0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803baac8  movdqu  [rbp+220h+var_2A0], xmm1
0x1803baacd  mov     word ptr [rsp+320h+var_2B0], di
0x1803baad2  mov     [rsp+320h+var_2C8], r15
0x1803baad7  lea     rax, aDefblobmanager; "DefBlobManagerUser::CreateByteStream: E"...
0x1803baade  mov     [rsp+320h+var_2F0], rax
0x1803baae3  lea     rax, [rsp+320h+var_2C8]
0x1803baae8  mov     [rsp+320h+var_2F8], rax
0x1803baaed  lea     rax, [rsp+320h+var_2F0]
0x1803baaf2  mov     [rsp+320h+var_300], rax
0x1803baaf7  mov     edx, 30h ; '0'
0x1803baafc  mov     ecx, 1E44D00Ah
0x1803bab01  lea     r8d, [rdx-26h]
0x1803bab05  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEBD@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEBD@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<char const *> &&)
0x1803bab0a  lea     rcx, [rsp+320h+var_2B0]
0x1803bab0f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803bab14  jmp     loc_1803BA88E
0x1803bab19  mov     edx, esi; int
0x1803bab1b  lea     rcx, [rsp+320h+var_2D0]; this
0x1803bab20  call    ?TruncAt@CStr@Ofc@@QEAAXH@Z; Ofc::CStr::TruncAt(int)
0x1803bab25  mov     rbx, [rsp+320h+var_2D0]
0x1803bab2a  jmp     loc_1803BAA37
0x1803bab2f  lea     rax, aDefblobmanager_2; "DefBlobManagerUser::CreateByteStream: E"...
0x1803bab36  mov     [rsp+320h+var_2E8], rax
0x1803bab3b  mov     r9d, r12d
0x1803bab3e  lea     rax, [rsp+320h+var_2E8]
0x1803bab43  mov     [rsp+320h+var_300], rax
0x1803bab48  mov     edx, 30h ; '0'
0x1803bab4d  mov     ecx, 1E44D00Eh
0x1803bab52  lea     r8d, [rdx-26h]
0x1803bab56  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1803bab5b  call    cs:__imp_GetLastError
0x1803bab61  test    eax, eax
0x1803bab63  jle     short loc_1803BAB6D
0x1803bab65  movzx   eax, ax
0x1803bab68  or      eax, 80070000h
0x1803bab6d  mov     edx, 1E44D00Dh; unsigned int
0x1803bab72  mov     ecx, eax; int
0x1803bab74  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1803bab79  int     3; Trap to Debugger
0x1803bab7a  lea     rax, aDefblobmanager_3; "DefBlobManagerUser::CreateByteStream: E"...
0x1803bab81  mov     [rsp+320h+var_2E8], rax
0x1803bab86  mov     r9d, r12d
0x1803bab89  lea     rax, [rsp+320h+var_2E8]
0x1803bab8e  mov     [rsp+320h+var_300], rax
0x1803bab93  mov     edx, 30h ; '0'
0x1803bab98  mov     ecx, 1E44D00Ch
0x1803bab9d  lea     r8d, [rdx-26h]
0x1803baba1  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1803baba6  call    cs:__imp_GetLastError
0x1803babac  test    eax, eax
0x1803babae  jle     short loc_1803BABB8
0x1803babb0  movzx   eax, ax
0x1803babb3  or      eax, 80070000h
0x1803babb8  mov     edx, 1E44D00Bh; unsigned int
0x1803babbd  mov     ecx, eax; int
0x1803babbf  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1803babc4  nop
0x1803babc5  jmp     short loc_1803BABC8
0x1803babc8  nop
0x1803babc9  lea     rdx, [rbp+220h+var_290]
0x1803babcd  lea     rcx, [rsp+320h+var_2E8]
0x1803babd2  call    ??$FGetEnterpriseIdentity@VCVarStr@Ofc@@@IEDPHelper@Art@@SA_NAEBVCVarStr@Ofc@@AEAVEnterpriseIdentity@EnterpriseDataProtection@Mso@@@Z; Art::IEDPHelper::FGetEnterpriseIdentity<Ofc::CVarStr>(Ofc::CVarStr const &,Mso::EnterpriseDataProtection::EnterpriseIdentity &)
0x1803babd7  test    al, al
0x1803babd9  jnz     short loc_1803BABF0
0x1803babdb  mov     edx, 90h
0x1803babe0  mov     ecx, 1E361294h
0x1803babe5  call    cs:__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z; Mso::Diagnostics::SendWarningTag(ulong,Mso::Logging::Category)
  ... truncated ...
```
