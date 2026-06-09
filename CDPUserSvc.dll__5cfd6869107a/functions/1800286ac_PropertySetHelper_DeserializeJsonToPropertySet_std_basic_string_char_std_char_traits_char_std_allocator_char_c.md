# PropertySetHelper::DeserializeJsonToPropertySet(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800286ac`
- end: `0x18002884b`
- name: `?DeserializeJsonToPropertySet@PropertySetHelper@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800283a8`

## callees

- `0x180004a58`
- `0x1800286ac`
- `0x180028854`
- `0x180029304`
- `0x18002c570`
- `0x18002dd40`
- `0x18002e030`
- `0x18002f250`
- `0x18002f9a0`
- `0x18002fa80`
- `0x180030b00`
- `0x1800327a0`
- `0x18003fe90`
- `0x180040c80`
- `0x1800410f0`
- `0x18004282c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PropertySetHelper::DeserializeJsonToPropertySet(
        __int64 a1,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // rax
  HSTRING v8; // rbx
  HSTRING *v9; // rax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v12; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[40]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v17[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v18[40]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v19[192]; // [rsp+100h] [rbp+0h] BYREF

  Json::Value::Value(v15, 0);
  Json::Reader::Reader((Json::Reader *)v19);
  if ( (unsigned __int8)Json::Reader::parse((Json::Reader *)v19) )
  {
    v3 = 0;
    Json::Value::getMemberNames(v15, v13);
    PropertySetHelper::PropertySetHelper((PropertySetHelper *)v14, a2);
    v4 = v13[0];
    v5 = v13[1];
    while ( v4 != v5 )
    {
      v6 = Json::Value::Value(v17, 0);
      Json::Value::get(v15, v16, v4, v6);
      Json::Value::~Value((Json::Value *)v17);
      v7 = Json::Value::asString(v16, v18);
      v8 = *(HSTRING *)cdp::UTF8toHSTRING(&v12, v7);
      v9 = (HSTRING *)cdp::UTF8toHSTRING(&string, v4);
      PropertySetHelper::SetString((PropertySetHelper *)v14, *v9, v8);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v12);
      v12 = 0;
      std::string::_Tidy_deallocate(v18);
      Json::Value::~Value((Json::Value *)v16);
      v4 += 32;
    }
    PropertySetHelper::~PropertySetHelper((PropertySetHelper *)v14);
    std::vector<std::string>::_Tidy(v13);
  }
  else
  {
    v3 = -2089418750;
  }
  Json::Reader::~Reader((Json::Reader *)v19);
  Json::Value::~Value((Json::Value *)v15);
  return v3;
}

```

## disassembly

```asm
0x1800286ac  mov     [rsp-8+arg_10], rbx
0x1800286b1  mov     [rsp-8+arg_18], rsi
0x1800286b6  push    rbp
0x1800286b7  push    rdi
0x1800286b8  push    r14
0x1800286ba  lea     rbp, [rsp-0D0h]
0x1800286c2  sub     rsp, 1D0h
0x1800286c9  mov     rax, cs:__security_cookie
0x1800286d0  xor     rax, rsp
0x1800286d3  mov     [rbp+0E0h+var_20], rax
0x1800286da  mov     rsi, rdx
0x1800286dd  mov     rbx, rcx
0x1800286e0  xor     edx, edx
0x1800286e2  lea     rcx, [rsp+1E0h+var_180]
0x1800286e7  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x1800286ec  nop
0x1800286ed  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800286f1  call    ??0Reader@Json@@QEAA@XZ; Json::Reader::Reader(void)
0x1800286f6  nop
0x1800286f7  mov     r9b, 1
0x1800286fa  lea     r8, [rsp+1E0h+var_180]
0x1800286ff  mov     rdx, rbx
0x180028702  lea     rcx, [rbp+0E0h+var_E0]
0x180028706  call    ?parse@Reader@Json@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAVValue@2@_N@Z; Json::Reader::parse(std::string const &,Json::Value &,bool)
0x18002870b  test    al, al
0x18002870d  jnz     short loc_180028719
0x18002870f  mov     edi, 83760002h
0x180028714  jmp     loc_18002880E
0x180028719  xor     edi, edi
0x18002871b  lea     rdx, [rsp+1E0h+var_1B0]
0x180028720  lea     rcx, [rsp+1E0h+var_180]
0x180028725  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x18002872a  nop
0x18002872b  mov     rdx, rsi; struct Windows::Foundation::Collections::IPropertySet *
0x18002872e  lea     rcx, [rsp+1E0h+var_198]; this
0x180028733  call    ??0PropertySetHelper@@QEAA@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180028738  nop
0x180028739  mov     rsi, [rsp+1E0h+var_1B0]
0x18002873e  mov     r14, [rsp+1E0h+var_1A8]
0x180028743  jmp     loc_1800287EF
0x180028748  xor     edx, edx
0x18002874a  lea     rcx, [rbp+0E0h+var_130]
0x18002874e  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180028753  nop
0x180028754  mov     r9, rax
0x180028757  mov     r8, rsi
0x18002875a  lea     rdx, [rbp+0E0h+var_158]
0x18002875e  lea     rcx, [rsp+1E0h+var_180]
0x180028763  call    ?get@Value@Json@@QEBA?AV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@@Z; Json::Value::get(std::string const &,Json::Value const &)
0x180028768  nop
0x180028769  lea     rcx, [rbp+0E0h+var_130]; this
0x18002876d  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180028772  lea     rdx, [rbp+0E0h+var_108]
0x180028776  lea     rcx, [rbp+0E0h+var_158]
0x18002877a  call    ?asString@Value@Json@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Json::Value::asString(void)
0x18002877f  nop
0x180028780  mov     rdx, rax
0x180028783  lea     rcx, [rsp+1E0h+var_1B8]
0x180028788  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18002878d  nop
0x18002878e  mov     rbx, [rax]
0x180028791  mov     rdx, rsi
0x180028794  lea     rcx, [rsp+1E0h+string]
0x180028799  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18002879e  nop
0x18002879f  mov     r8, rbx; HSTRING
0x1800287a2  mov     rdx, [rax]; HSTRING
0x1800287a5  lea     rcx, [rsp+1E0h+var_198]; this
0x1800287aa  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x1800287af  nop
0x1800287b0  mov     rcx, [rsp+1E0h+string]; string
0x1800287b5  call    cs:__imp_WindowsDeleteString
0x1800287bb  mov     [rsp+1E0h+string], 0
0x1800287c4  mov     rcx, [rsp+1E0h+var_1B8]; string
0x1800287c9  call    cs:__imp_WindowsDeleteString
0x1800287cf  mov     [rsp+1E0h+var_1B8], 0
0x1800287d8  lea     rcx, [rbp+0E0h+var_108]
0x1800287dc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800287e1  nop
0x1800287e2  lea     rcx, [rbp+0E0h+var_158]; this
0x1800287e6  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800287eb  add     rsi, 20h ; ' '
0x1800287ef  cmp     rsi, r14
0x1800287f2  jnz     loc_180028748
0x1800287f8  lea     rcx, [rsp+1E0h+var_198]; this
0x1800287fd  call    ??1PropertySetHelper@@QEAA@XZ; PropertySetHelper::~PropertySetHelper(void)
0x180028802  nop
0x180028803  lea     rcx, [rsp+1E0h+var_1B0]
0x180028808  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18002880d  nop
0x18002880e  lea     rcx, [rbp+0E0h+var_E0]; this
0x180028812  call    ??1Reader@Json@@QEAA@XZ; Json::Reader::~Reader(void)
0x180028817  nop
0x180028818  lea     rcx, [rsp+1E0h+var_180]; this
0x18002881d  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180028822  mov     eax, edi
0x180028824  mov     rcx, [rbp+0E0h+var_20]
0x18002882b  xor     rcx, rsp; StackCookie
0x18002882e  call    __security_check_cookie
0x180028833  lea     r11, [rsp+1E0h+var_10]
0x18002883b  mov     rbx, [r11+30h]
0x18002883f  mov     rsi, [r11+38h]
0x180028843  mov     rsp, r11
0x180028846  pop     r14
0x180028848  pop     rdi
0x180028849  pop     rbp
0x18002884a  retn
```
