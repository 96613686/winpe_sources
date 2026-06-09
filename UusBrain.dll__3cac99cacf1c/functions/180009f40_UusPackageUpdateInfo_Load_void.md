# UusPackageUpdateInfo::Load(void)

- ea: `0x180009f40`
- end: `0x18000a2a2`
- name: `?Load@UusPackageUpdateInfo@@QEAAXXZ`
- size: `866`
- prototype: `void __fastcall(UusPackageUpdateInfo *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x18000af34`

## callees

- `0x180009f40`
- `0x18000a5b0`
- `0x18000f914`
- `0x180013748`
- `0x180013838`
- `0x180017784`
- `0x1800240ac`
- `0x180027228`
- `0x1800286d0`
- `0x180028728`
- `0x180029344`
- `0x180029644`
- `0x180029708`
- `0x1800298d4`
- `0x18002dbdc`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`
- `0x180047ab0`

## string_xrefs

- `0x18000a26a`: `Unable to open file.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UusPackageUpdateInfo::Load(UusPackageUpdateInfo *this, __int64 a2, struct std::error_code *a3)
{
  const struct std::error_code *v4; // rbx
  bool v5; // al
  const struct std::filesystem::path *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // [rsp+38h] [rbp-D0h] BYREF
  char v17[16]; // [rsp+40h] [rbp-C8h] BYREF
  void ***pExceptionObject; // [rsp+50h] [rbp-B8h]
  __int64 pExceptionObject_8; // [rsp+58h] [rbp-B0h] BYREF
  char v20; // [rsp+60h] [rbp-A8h]
  char v21; // [rsp+61h] [rbp-A7h]
  __int16 v22; // [rsp+62h] [rbp-A6h]
  int v23; // [rsp+64h] [rbp-A4h]
  _QWORD Src[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h]
  _QWORD v26[34]; // [rsp+98h] [rbp-70h] BYREF

  v4 = (UusPackageUpdateInfo *)((char *)this + 8);
  *(_QWORD *)&v17[8] = 0;
  pExceptionObject = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v5 = std::filesystem::exists(
         (UusPackageUpdateInfo *)((char *)this + 8),
         (const struct std::filesystem::path *)&v17[8],
         a3);
  if ( *(_DWORD *)&v17[8] )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", &v17[8], v4, v6);
  if ( v5 )
  {
    memset(v26, 0, sizeof(v26));
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(const struct std::error_code **)v4;
    std::wifstream::wifstream(v26, v4);
    *(_QWORD *)((char *)v26 + *(int *)(v26[0] + 4LL)) = &std::wifstream::`vftable';
    *(__int32 *)((char *)&si128.m128i_i32[3] + *(int *)(v26[0] + 4LL)) = *(_DWORD *)(v26[0] + 4LL) - 176;
    if ( !v26[18] )
    {
      std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject_8, "Unable to open file.");
      throw (std::runtime_error *)&pExceptionObject_8;
    }
    v7 = *(_QWORD *)((char *)&v26[9] + *(int *)(v26[0] + 4LL));
    pExceptionObject_8 = 0;
    v20 = 1;
    v22 = 0;
    *(_QWORD *)&v17[8] = v7;
    LOBYTE(pExceptionObject) = v7 == 0;
    BYTE1(pExceptionObject) = v21;
    WORD1(pExceptionObject) = 0;
    HIDWORD(pExceptionObject) = v23;
    *(_OWORD *)&Src[1] = 0;
    si128 = 0;
    if ( (unsigned __int8)std::operator==<wchar_t,std::char_traits<wchar_t>>(&v17[8], &pExceptionObject_8) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src[1]) = 0;
    }
    else
    {
      std::wstring::_Construct_from_iter<std::istreambuf_iterator<wchar_t>,std::istreambuf_iterator<wchar_t>,std::nullptr_t>(&Src[1]);
    }
    v16 = 0;
    web::json::value::parse(&v16, &Src[1]);
    v8 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyInstalledTime);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v8);
    v9 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keySessionData);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v9);
    v10 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyUpdateId);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v10);
    v11 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyFlightId);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v11);
    v12 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyCorrelationVector);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v12);
    v13 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyRelatedCV);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v13);
    v14 = std::wstring::wstring(&pExceptionObject_8, UusPackageUpdateInfo::_keyCountryCode);
    UusPackageUpdateInfo::LoadStringField(this, &v16, v14);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 8LL))(
           v16,
           UusPackageUpdateInfo::_keyFlightMetadata) )
    {
      v15 = web::json::value::at(&v16, UusPackageUpdateInfo::_keyFlightMetadata);
      web::json::value::operator=((char *)this + 56, v15);
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 192LL))(v16, 1);
    std::wstring::_Tidy_deallocate(&Src[1]);
    std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v26[22]);
    v26[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v26[22]);
  }
}

```

## disassembly

```asm
0x180009f40  mov     rax, rsp
0x180009f43  mov     [rax+10h], rbx
0x180009f47  mov     [rax+18h], rsi
0x180009f4b  mov     [rax+20h], rdi
0x180009f4f  push    rbp
0x180009f50  lea     rbp, [rax-0B8h]
0x180009f57  sub     rsp, 1B0h
0x180009f5e  mov     rax, cs:__security_cookie
0x180009f65  xor     rax, rsp
0x180009f68  mov     [rbp+0B0h+var_10], rax
0x180009f6f  mov     rdi, rcx
0x180009f72  lea     rbx, [rcx+8]
0x180009f76  xor     esi, esi
0x180009f78  mov     qword ptr [rsp+1B0h+var_178+8], rsi
0x180009f7d  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180009f84  mov     qword ptr [rsp+1B0h+pExceptionObject], rax
0x180009f89  lea     rdx, [rsp+1B0h+var_178+8]; struct std::filesystem::path *
0x180009f8e  mov     rcx, rbx; this
0x180009f91  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180009f96  cmp     dword ptr [rsp+1B0h+var_178+8], esi
0x180009f9a  jnz     loc_18000A28D
0x180009fa0  test    al, al
0x180009fa2  jz      loc_18000A242
0x180009fa8  xor     edx, edx; Val
0x180009faa  mov     r8d, 110h; Size
0x180009fb0  lea     rcx, [rbp+0B0h+var_120]; void *
0x180009fb4  call    memset
0x180009fb9  cmp     qword ptr [rbx+18h], 7
0x180009fbe  jbe     short loc_180009FC3
0x180009fc0  mov     rbx, [rbx]
0x180009fc3  mov     rdx, rbx
0x180009fc6  lea     rcx, [rbp+0B0h+var_120]
0x180009fca  call    ??0?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@QEAA@PEB_WHH@Z; std::wifstream::wifstream(wchar_t const *,int,int)
0x180009fcf  mov     rax, [rbp+0B0h+var_120]
0x180009fd3  movsxd  rcx, dword ptr [rax+4]
0x180009fd7  lea     rax, ??_7?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wifstream::`vftable'
0x180009fde  mov     [rbp+rcx+0B0h+var_120], rax
0x180009fe3  mov     rax, [rbp+0B0h+var_120]
0x180009fe7  movsxd  rcx, dword ptr [rax+4]
0x180009feb  lea     edx, [rcx-0B0h]
0x180009ff1  mov     [rbp+rcx+0B0h+var_124], edx
0x180009ff5  cmp     [rbp+0B0h+var_90], rsi
0x180009ff9  jz      loc_18000A26A
0x180009fff  mov     rax, [rbp+0B0h+var_120]
0x18000a003  movsxd  rcx, dword ptr [rax+4]
0x18000a007  mov     rdx, [rbp+rcx+0B0h+var_D8]
0x18000a00c  mov     qword ptr [rsp+1B0h+pExceptionObject+8], rsi
0x18000a011  mov     [rsp+1B0h+var_158], 1
0x18000a016  mov     al, [rsp+1B0h+var_157]
0x18000a01a  mov     [rsp+1B0h+var_157], al
0x18000a01e  mov     [rsp+1B0h+var_156], si
0x18000a023  mov     eax, [rsp+1B0h+var_154]
0x18000a027  mov     [rsp+1B0h+var_154], eax
0x18000a02b  mov     qword ptr [rsp+1B0h+var_178+8], rdx
0x18000a030  test    rdx, rdx
0x18000a033  setz    byte ptr [rsp+1B0h+pExceptionObject]
0x18000a038  mov     al, [rsp+1B0h+var_157]
0x18000a03c  mov     byte ptr [rsp+1B0h+pExceptionObject+1], al
0x18000a040  mov     word ptr [rsp+1B0h+pExceptionObject+2], si
0x18000a045  mov     eax, [rsp+1B0h+var_154]
0x18000a049  mov     dword ptr [rsp+1B0h+pExceptionObject+4], eax
0x18000a04d  xorps   xmm0, xmm0
0x18000a050  movups  xmmword ptr [rsp+1B0h+Src+8], xmm0
0x18000a055  xorps   xmm1, xmm1
0x18000a058  movdqu  xmmword ptr [rbp-80h], xmm1
0x18000a05d  movaps  xmm0, xmmword ptr [rsp+1B0h+var_178+8]
0x18000a062  movdqa  xmmword ptr [rsp+1B0h+var_178+8], xmm0
0x18000a068  movaps  xmm1, [rsp+1B0h+pExceptionObject+8]
0x18000a06d  movdqa  [rsp+1B0h+pExceptionObject+8], xmm1
0x18000a073  lea     rdx, [rsp+1B0h+pExceptionObject+8]
0x18000a078  lea     rcx, [rsp+1B0h+var_178+8]
0x18000a07d  call    ??$?8_WU?$char_traits@_W@std@@@std@@YA_NAEBV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@0@0@Z; std::operator==<wchar_t,std::char_traits<wchar_t>>(std::istreambuf_iterator<wchar_t> const &,std::istreambuf_iterator<wchar_t> const &)
0x18000a082  test    al, al
0x18000a084  jz      short loc_18000A09A
0x18000a086  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000a08e  movdqu  xmmword ptr [rbp-80h], xmm0
0x18000a093  mov     word ptr [rsp+1B0h+Src+8], si
0x18000a098  jmp     short loc_18000A0C5
0x18000a09a  movaps  xmm0, [rsp+1B0h+pExceptionObject+8]
0x18000a09f  movdqa  [rsp+1B0h+pExceptionObject+8], xmm0
0x18000a0a5  movaps  xmm1, xmmword ptr [rsp+1B0h+var_178+8]
0x18000a0aa  movdqa  xmmword ptr [rsp+1B0h+var_178+8], xmm1
0x18000a0b0  lea     r8, [rsp+1B0h+pExceptionObject+8]
0x18000a0b5  lea     rdx, [rsp+1B0h+var_178+8]
0x18000a0ba  lea     rcx, [rsp+1B0h+Src+8]; Src
0x18000a0bf  call    ??$_Construct_from_iter@V?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@V12@$$T@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@1@V21@$$T@Z; std::wstring::_Construct_from_iter<std::istreambuf_iterator<wchar_t>,std::istreambuf_iterator<wchar_t>,std::nullptr_t>(std::istreambuf_iterator<wchar_t>,std::istreambuf_iterator<wchar_t>,std::nullptr_t)
0x18000a0c4  nop
0x18000a0c5  mov     [rsp+1B0h+var_180], rsi
0x18000a0ca  lea     rdx, [rsp+1B0h+Src+8]
0x18000a0cf  lea     rcx, [rsp+1B0h+var_180]
0x18000a0d4  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x18000a0d9  nop
0x18000a0da  lea     rdx, ?_keyInstalledTime@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyInstalledTime
0x18000a0e1  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a0e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a0eb  mov     r8, rax
0x18000a0ee  lea     rdx, [rsp+1B0h+var_180]
0x18000a0f3  mov     rcx, rdi
0x18000a0f6  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a0fb  lea     rdx, ?_keySessionData@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keySessionData
0x18000a102  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a107  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a10c  mov     r8, rax
0x18000a10f  lea     rdx, [rsp+1B0h+var_180]
0x18000a114  mov     rcx, rdi
0x18000a117  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a11c  lea     rdx, ?_keyUpdateId@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyUpdateId
0x18000a123  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a128  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a12d  mov     r8, rax
0x18000a130  lea     rdx, [rsp+1B0h+var_180]
0x18000a135  mov     rcx, rdi
0x18000a138  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a13d  lea     rdx, ?_keyFlightId@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyFlightId
0x18000a144  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a149  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a14e  mov     r8, rax
0x18000a151  lea     rdx, [rsp+1B0h+var_180]
0x18000a156  mov     rcx, rdi
0x18000a159  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a15e  lea     rdx, ?_keyCorrelationVector@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyCorrelationVector
0x18000a165  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a16a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a16f  mov     r8, rax
0x18000a172  lea     rdx, [rsp+1B0h+var_180]
0x18000a177  mov     rcx, rdi
0x18000a17a  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a17f  lea     rdx, ?_keyRelatedCV@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyRelatedCV
0x18000a186  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a18b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a190  mov     r8, rax
0x18000a193  lea     rdx, [rsp+1B0h+var_180]
0x18000a198  mov     rcx, rdi
0x18000a19b  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a1a0  lea     rdx, ?_keyCountryCode@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyCountryCode
0x18000a1a7  lea     rcx, [rsp+1B0h+pExceptionObject+8]
0x18000a1ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a1b1  mov     r8, rax
0x18000a1b4  lea     rdx, [rsp+1B0h+var_180]
0x18000a1b9  mov     rcx, rdi
0x18000a1bc  call    ?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::wstring)
0x18000a1c1  mov     rcx, [rsp+1B0h+var_180]
0x18000a1c6  mov     rax, [rcx]
0x18000a1c9  lea     rdx, ?_keyFlightMetadata@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyFlightMetadata
0x18000a1d0  mov     rax, [rax+8]
0x18000a1d4  call    _guard_dispatch_icall
0x18000a1d9  test    al, al
0x18000a1db  jz      short loc_18000A1FB
0x18000a1dd  lea     rdx, ?_keyFlightMetadata@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyFlightMetadata
0x18000a1e4  lea     rcx, [rsp+1B0h+var_180]
0x18000a1e9  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18000a1ee  mov     rdx, rax
0x18000a1f1  lea     rcx, [rdi+38h]
0x18000a1f5  call    ??4value@json@web@@QEAAAEAV012@AEBV012@@Z; web::json::value::operator=(web::json::value const &)
0x18000a1fa  nop
0x18000a1fb  mov     rcx, [rsp+1B0h+var_180]
0x18000a200  test    rcx, rcx
0x18000a203  jz      short loc_18000A21A
0x18000a205  mov     rax, [rcx]
0x18000a208  mov     edx, 1
0x18000a20d  mov     rax, [rax+0C0h]
0x18000a214  call    _guard_dispatch_icall
0x18000a219  nop
0x18000a21a  lea     rcx, [rsp+1B0h+Src+8]
0x18000a21f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a224  nop
0x18000a225  lea     rcx, [rbp+0B0h+var_70]
0x18000a229  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x18000a22e  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000a235  mov     [rbp+0B0h+var_70], rax
0x18000a239  lea     rcx, [rbp+0B0h+var_70]; this
0x18000a23d  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000a242  mov     rcx, [rbp+0B0h+var_10]
0x18000a249  xor     rcx, rsp; StackCookie
0x18000a24c  call    __security_check_cookie
0x18000a251  lea     r11, [rsp+1B0h+var_s0]
0x18000a259  mov     rbx, [r11+18h]
0x18000a25d  mov     rsi, [r11+20h]
0x18000a261  mov     rdi, [r11+28h]
0x18000a265  mov     rsp, r11
0x18000a268  pop     rbp
0x18000a269  retn
0x18000a26a  lea     rdx, aUnableToOpenFi; "Unable to open file."
0x18000a271  lea     rcx, [rsp+1B0h+pExceptionObject+8]; this
0x18000a276  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000a27b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000a282  lea     rcx, [rsp+1B0h+pExceptionObject+8]; pExceptionObject
0x18000a287  call    _CxxThrowException
0x18000a28d  mov     r8, rbx; struct std::error_code *
0x18000a290  lea     rdx, [rsp+1B0h+var_178+8]; char *
0x18000a295  lea     rcx, aExists; "exists"
0x18000a29c  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
