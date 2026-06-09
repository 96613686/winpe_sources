# MapControl::ConfigurationManager::processOverridesCache(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800219fc`
- end: `0x180021c85`
- name: `?processOverridesCache@ConfigurationManager@MapControl@@AEAA_NAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(MapControl::ConfigurationManager *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x180021ccc`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c3d0`
- `0x180011ddc`
- `0x180012158`
- `0x18001d6e4`
- `0x18001e3fc`
- `0x1800215f0`
- `0x180021630`
- `0x1800217dc`
- `0x1800219fc`
- `0x1800222e4`
- `0x18003417c`
- `0x180034324`
- `0x180034538`
- `0x180034a00`
- `0x180035110`
- `0x180035554`
- `0x180035750`
- `0x180035908`
- `0x180035934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021bf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021bf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall MapControl::ConfigurationManager::processOverridesCache(
        MapControl::ConfigurationManager *this,
        __int64 a2)
{
  char v3; // r15
  _BYTE *Value; // r13
  __int64 v5; // rax
  __int64 v6; // r8
  const struct Json::Value *v7; // rax
  _QWORD *i; // rsi
  __int64 v9; // r10
  const struct Json::Value *v10; // rax
  char v11; // al
  __int64 v12; // r10
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  _QWORD *v18; // [rsp+20h] [rbp-79h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-71h]
  __int64 v20; // [rsp+30h] [rbp-69h]
  __int64 v21; // [rsp+48h] [rbp-51h] BYREF
  char v22; // [rsp+50h] [rbp-49h]
  __int64 v23; // [rsp+58h] [rbp-41h] BYREF
  char v24; // [rsp+60h] [rbp-39h]
  char *v25; // [rsp+68h] [rbp-31h]
  void *v26; // [rsp+70h] [rbp-29h] BYREF
  char v27; // [rsp+78h] [rbp-21h]
  void *v28[5]; // [rsp+98h] [rbp-1h] BYREF
  char v29; // [rsp+C0h] [rbp+27h]

  v3 = 0;
  MapControl::ConfigurationManager::parseOverridesCache(this, v28, a2);
  if ( v29 && *(_BYTE *)(Core::Optional<Json::Value>::getValue(v28) + 8) == 7 )
  {
    Value = (_BYTE *)Core::Optional<Json::Value>::getValue(v28);
    v5 = Json::Value::Value((__int64)&v18, 0);
    v7 = (const struct Json::Value *)Json::Value::get(Value, &v26, v6, v5);
    MapControl::ConfigurationManager::initializeClientBucket(this, v7);
    Json::Value::~Value(&v26);
    Json::Value::~Value((void **)&v18);
    Json::Value::getMemberNames(Value, &v18);
    for ( i = v18; i != v19; i += 4 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
      std::_WChar_traits<unsigned short>::length(L"overrides");
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, i[2]) )
      {
        v10 = (const struct Json::Value *)Json::Value::operator[](Value, L"overrides");
        Json::Value::Value((Json::Value *)&v26, v10);
        if ( v27 == 6 )
        {
          v3 = 1;
          Json::Value::begin(&v26, &v21);
          Json::Value::end(&v26, &v23);
          while ( 1 )
          {
            v11 = v22 ? v24 : v21 == v23;
            if ( v11 )
              break;
            MapControl::ConfigurationManager::submitCachedOverrides(this, (const struct Json::Value *)(v21 + 48));
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v21);
          }
        }
        Json::Value::~Value(&v26);
      }
      else
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
        std::_WChar_traits<unsigned short>::length(L"most_recent_region");
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v12, i[2]) )
        {
          v25 = (char *)this + 48;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
          v13 = Json::Value::operator[](Value, L"most_recent_region");
          v14 = Json::Value::asString(v13, &v26);
          std::wstring::operator=((char *)this + 336, v14);
          std::wstring::_Tidy_deallocate(&v26);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        }
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( !*((_QWORD *)this + 44) )
    {
      *((_QWORD *)this + 44) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 336) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( v18 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v18, v19, v15, v16);
      std::_Deallocate<16>(v18, (v20 - (_QWORD)v18) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  if ( v29 )
    Json::Value::~Value(v28);
  return v3;
}

```

## disassembly

```asm
0x1800219fc  mov     [rsp-8+arg_10], rbx
0x180021a01  push    rbp
0x180021a02  push    rsi
0x180021a03  push    rdi
0x180021a04  push    r13
0x180021a06  push    r15
0x180021a08  lea     rbp, [rsp-37h]
0x180021a0d  sub     rsp, 0D0h
0x180021a14  mov     rax, cs:__security_cookie
0x180021a1b  xor     rax, rsp
0x180021a1e  mov     [rbp+57h+var_28], rax
0x180021a22  mov     rdi, rcx
0x180021a25  xor     r15b, r15b
0x180021a28  mov     r8, rdx
0x180021a2b  lea     rdx, [rbp+57h+var_58]
0x180021a2f  call    ?parseOverridesCache@ConfigurationManager@MapControl@@AEAA?AV?$Optional@VValue@Json@@@Core@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; MapControl::ConfigurationManager::parseOverridesCache(std::vector<uchar> const &)
0x180021a34  nop
0x180021a35  cmp     [rbp+57h+var_30], r15b
0x180021a39  jz      loc_180021C50
0x180021a3f  lea     rcx, [rbp+57h+var_58]
0x180021a43  call    ?getValue@?$Optional@VValue@Json@@@Core@@QEAAAEAVValue@Json@@XZ; Core::Optional<Json::Value>::getValue(void)
0x180021a48  cmp     byte ptr [rax+8], 7
0x180021a4c  jnz     loc_180021C50
0x180021a52  lea     rcx, [rbp+57h+var_58]
0x180021a56  call    ?getValue@?$Optional@VValue@Json@@@Core@@QEAAAEAVValue@Json@@XZ; Core::Optional<Json::Value>::getValue(void)
0x180021a5b  mov     r13, rax
0x180021a5e  xor     edx, edx
0x180021a60  lea     rcx, [rbp+57h+var_D0]
0x180021a64  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180021a69  nop
0x180021a6a  mov     r9, rax
0x180021a6d  lea     rdx, [rbp+57h+var_80]
0x180021a71  mov     rcx, r13
0x180021a74  call    ?get@Value@Json@@QEBA?AV12@PEBGAEBV12@@Z; Json::Value::get(ushort const *,Json::Value const &)
0x180021a79  nop
0x180021a7a  mov     rdx, rax; struct Json::Value *
0x180021a7d  mov     rcx, rdi; this
0x180021a80  call    ?initializeClientBucket@ConfigurationManager@MapControl@@AEAAXAEBVValue@Json@@@Z; MapControl::ConfigurationManager::initializeClientBucket(Json::Value const &)
0x180021a85  nop
0x180021a86  lea     rcx, [rbp+57h+var_80]; this
0x180021a8a  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021a8f  nop
0x180021a90  lea     rcx, [rbp+57h+var_D0]; this
0x180021a94  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021a99  lea     rdx, [rbp+57h+var_D0]
0x180021a9d  mov     rcx, r13
0x180021aa0  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x180021aa5  nop
0x180021aa6  mov     rsi, [rbp+57h+var_D0]
0x180021aaa  jmp     loc_180021BE2
0x180021aaf  mov     rcx, rsi
0x180021ab2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021ab7  mov     r10, rax
0x180021aba  lea     rcx, aOverrides; "overrides"
0x180021ac1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180021ac6  mov     r9, rax
0x180021ac9  lea     r8, aOverrides; "overrides"
0x180021ad0  mov     rdx, [rsi+10h]
0x180021ad4  mov     rcx, r10
0x180021ad7  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180021adc  test    al, al
0x180021ade  jz      short loc_180021B5E
0x180021ae0  lea     rdx, aOverrides; "overrides"
0x180021ae7  mov     rcx, r13
0x180021aea  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180021aef  mov     rdx, rax; struct Json::Value *
0x180021af2  lea     rcx, [rbp+57h+var_80]; this
0x180021af6  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x180021afb  nop
0x180021afc  cmp     [rbp+57h+var_78], 6
0x180021b00  jnz     short loc_180021B50
0x180021b02  mov     r15b, 1
0x180021b05  lea     rdx, [rbp+57h+var_A8]
0x180021b09  lea     rcx, [rbp+57h+var_80]
0x180021b0d  call    ?begin@Value@Json@@QEAA?AVValueIterator@2@XZ; Json::Value::begin(void)
0x180021b12  lea     rdx, [rbp+57h+var_98]
0x180021b16  lea     rcx, [rbp+57h+var_80]
0x180021b1a  call    ?end@Value@Json@@QEAA?AVValueIterator@2@XZ; Json::Value::end(void)
0x180021b1f  mov     rdx, [rbp+57h+var_A8]
0x180021b23  cmp     [rbp+57h+var_A0], 0
0x180021b27  jz      short loc_180021B2E
0x180021b29  mov     al, [rbp+57h+var_90]
0x180021b2c  jmp     short loc_180021B35
0x180021b2e  cmp     rdx, [rbp+57h+var_98]
0x180021b32  setz    al
0x180021b35  test    al, al
0x180021b37  jnz     short loc_180021B50
0x180021b39  add     rdx, 30h ; '0'; struct Json::Value *
0x180021b3d  mov     rcx, rdi; this
0x180021b40  call    ?submitCachedOverrides@ConfigurationManager@MapControl@@AEAAXAEBVValue@Json@@@Z; MapControl::ConfigurationManager::submitCachedOverrides(Json::Value const &)
0x180021b45  lea     rcx, [rbp+57h+var_A8]
0x180021b49  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180021b4e  jmp     short loc_180021B1F
0x180021b50  lea     rcx, [rbp+57h+var_80]; this
0x180021b54  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021b59  jmp     loc_180021BDE
0x180021b5e  mov     rcx, rsi
0x180021b61  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021b66  mov     r10, rax
0x180021b69  lea     rcx, aMostRecentRegi; "most_recent_region"
0x180021b70  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180021b75  mov     r9, rax
0x180021b78  lea     r8, aMostRecentRegi; "most_recent_region"
0x180021b7f  mov     rdx, [rsi+10h]
0x180021b83  mov     rcx, r10
0x180021b86  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180021b8b  test    al, al
0x180021b8d  jz      short loc_180021BDE
0x180021b8f  lea     rbx, [rdi+30h]
0x180021b93  mov     [rbp+57h+var_88], rbx
0x180021b97  mov     rcx, rbx; lpCriticalSection
0x180021b9a  call    cs:__imp_EnterCriticalSection
0x180021ba0  nop
0x180021ba1  lea     rdx, aMostRecentRegi; "most_recent_region"
0x180021ba8  mov     rcx, r13
0x180021bab  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180021bb0  lea     rdx, [rbp+57h+var_80]
0x180021bb4  mov     rcx, rax
0x180021bb7  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x180021bbc  lea     rcx, [rdi+150h]
0x180021bc3  mov     rdx, rax
0x180021bc6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021bcb  lea     rcx, [rbp+57h+var_80]
0x180021bcf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021bd4  nop
0x180021bd5  mov     rcx, rbx; lpCriticalSection
0x180021bd8  call    cs:__imp_LeaveCriticalSection
0x180021bde  add     rsi, 20h ; ' '
0x180021be2  cmp     rsi, [rbp+57h+var_C8]
0x180021be6  jnz     loc_180021AAF
0x180021bec  lea     rcx, [rdi+30h]; lpCriticalSection
0x180021bf0  call    cs:__imp_EnterCriticalSection
0x180021bf6  cmp     qword ptr [rdi+160h], 0
0x180021bfe  jnz     short loc_180021C1B
0x180021c00  lea     rcx, [rdi+150h]
0x180021c07  mov     qword ptr [rcx+10h], 0
0x180021c0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021c14  xor     r8d, r8d
0x180021c17  mov     [rax], r8w
0x180021c1b  lea     rcx, [rdi+30h]; lpCriticalSection
0x180021c1f  call    cs:__imp_LeaveCriticalSection
0x180021c25  nop
0x180021c26  cmp     [rbp+57h+var_D0], 0
0x180021c2b  jz      short loc_180021C50
0x180021c2d  mov     rdx, [rbp+57h+var_C8]
0x180021c31  mov     rcx, [rbp+57h+var_D0]
0x180021c35  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180021c3a  mov     rdx, [rbp+57h+var_C0]
0x180021c3e  sub     rdx, [rbp+57h+var_D0]
0x180021c42  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180021c46  mov     rcx, [rbp+57h+var_D0]
0x180021c4a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021c4f  nop
0x180021c50  cmp     [rbp+57h+var_30], 0
0x180021c54  jz      short loc_180021C5F
0x180021c56  lea     rcx, [rbp+57h+var_58]; this
0x180021c5a  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021c5f  mov     al, r15b
0x180021c62  mov     rcx, [rbp+57h+var_28]
0x180021c66  xor     rcx, rsp; StackCookie
0x180021c69  call    __security_check_cookie
0x180021c6e  mov     rbx, [rsp+0F0h+arg_10]
0x180021c76  add     rsp, 0D0h
0x180021c7d  pop     r15
0x180021c7f  pop     r13
0x180021c81  pop     rdi
0x180021c82  pop     rsi
0x180021c83  pop     rbp
0x180021c84  retn
```
