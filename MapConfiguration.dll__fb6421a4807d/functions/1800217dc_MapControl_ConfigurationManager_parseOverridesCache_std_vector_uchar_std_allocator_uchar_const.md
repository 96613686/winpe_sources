# MapControl::ConfigurationManager::parseOverridesCache(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800217dc`
- end: `0x1800219f6`
- name: `?parseOverridesCache@ConfigurationManager@MapControl@@AEAA?AV?$Optional@VValue@Json@@@Core@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x1800219fc`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c850`
- `0x180011524`
- `0x18001ed4c`
- `0x1800217dc`
- `0x1800294ac`
- `0x180034324`
- `0x180034538`
- `0x180034630`
- `0x18003662c`
- `0x1800367e8`
- `0x180036850`
- `0x180037f50`
- `0x180043010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800219ef`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800219ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MapControl::ConfigurationManager::parseOverridesCache(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  struct Json::CharReader *v9; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  struct Json::CharReader *v15; // [rsp+30h] [rbp-89h] BYREF
  char v16[8]; // [rsp+38h] [rbp-81h] BYREF
  int v17; // [rsp+40h] [rbp-79h]
  __int128 v18; // [rsp+48h] [rbp-71h]
  __int64 v19; // [rsp+58h] [rbp-61h]
  _QWORD v20[3]; // [rsp+60h] [rbp-59h] BYREF
  void *v21[5]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v22[48]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v23[16]; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+E0h] [rbp+27h]

  Json::CharReaderBuilder::CharReaderBuilder((Json::CharReaderBuilder *)v22);
  LOBYTE(v17) = 5;
  v17 &= ~0x100u;
  v18 = 0;
  v19 = 0;
  v16[0] = 1;
  v5 = std::wstring::wstring((__int64)v23, (__int64)L"strictRoot");
  v6 = Json::CharReaderBuilder::operator[](v22, v5);
  Json::Value::operator=(v6, v16);
  v20[0] = v16;
  LOBYTE(v17) = 5;
  v17 &= ~0x100u;
  v18 = 0;
  v19 = 0;
  v16[0] = 1;
  v7 = std::wstring::wstring((__int64)v23, (__int64)L"rejectDupKeys");
  v8 = Json::CharReaderBuilder::operator[](v22, v7);
  Json::Value::operator=(v8, v16);
  v9 = Json::CharReaderBuilder::newCharReader((Json::CharReaderBuilder *)v22);
  v15 = v9;
  Json::Value::Value((__int64)v21, 0);
  if ( (*(unsigned __int8 (__fastcall **)(struct Json::CharReader *, _QWORD, __int64, void **, _QWORD))(*(_QWORD *)v9 + 8LL))(
         v9,
         *a3,
         *a3 + 2LL * ((a3[1] - *a3) >> 1),
         v21,
         0) )
  {
    Core::Optional<Json::Value>::Optional<Json::Value>(a2);
  }
  else
  {
    std::wstring::wstring((__int64)v23);
    v12 = *a3;
    v13 = a3[1] - *a3;
    if ( v13 < 0 || !v12 && v13 )
    {
      _o_terminate(v12, v11);
      JUMPOUT(0x1800219F5LL);
    }
    v20[0] = a3[1] - *a3;
    v20[1] = v12;
    Core::Text::decodeUTF8(v20, v23);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    if ( (*(unsigned __int8 (__fastcall **)(struct Json::CharReader *, __int64, __int64, void **, _QWORD))(*(_QWORD *)v9 + 8LL))(
           v9,
           v14,
           v14 + 2 * v24,
           v21,
           0) )
    {
      Core::Optional<Json::Value>::Optional<Json::Value>(a2);
      std::wstring::_Tidy_deallocate(v23);
    }
    else
    {
      std::wstring::_Tidy_deallocate(v23);
      *(_BYTE *)(a2 + 40) = 0;
    }
  }
  Json::Value::~Value(v21);
  std::unique_ptr<Pal::NetworkRequestImplWindowsService>::~unique_ptr<Pal::NetworkRequestImplWindowsService>((__int64 (__fastcall ****)(_QWORD, __int64))&v15);
  Json::CharReaderBuilder::~CharReaderBuilder((Json::CharReaderBuilder *)v22);
  return a2;
}

```

## disassembly

```asm
0x1800217dc  mov     [rsp-8+arg_0], rbx
0x1800217e1  push    rbp
0x1800217e2  push    rsi
0x1800217e3  push    rdi
0x1800217e4  lea     rbp, [rsp-47h]
0x1800217e9  sub     rsp, 100h
0x1800217f0  mov     rax, cs:__security_cookie
0x1800217f7  xor     rax, rsp
0x1800217fa  mov     [rbp+57h+var_20], rax
0x1800217fe  mov     rdi, r8
0x180021801  mov     rbx, rdx
0x180021804  mov     [rsp+110h+var_E0], rdx
0x180021809  lea     rcx, [rbp+57h+var_70]; this
0x18002180d  call    ??0CharReaderBuilder@Json@@QEAA@XZ; Json::CharReaderBuilder::CharReaderBuilder(void)
0x180021812  nop
0x180021813  lea     rax, [rsp+110h+var_D8]
0x180021818  mov     [rsp+110h+var_E0], rax
0x18002181d  mov     byte ptr [rbp+57h+var_D0], 5
0x180021821  mov     esi, 0FFFFFEFFh
0x180021826  and     [rbp+57h+var_D0], esi
0x180021829  xorps   xmm0, xmm0
0x18002182c  movdqu  [rbp+57h+var_C8], xmm0
0x180021831  mov     [rbp+57h+var_B8], 0
0x180021839  mov     [rsp+110h+var_D8], 1
0x18002183e  lea     rdx, aStrictroot; "strictRoot"
0x180021845  lea     rcx, [rbp+57h+var_40]
0x180021849  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002184e  mov     rdx, rax
0x180021851  lea     rcx, [rbp+57h+var_70]
0x180021855  call    ??ACharReaderBuilder@Json@@QEAAAEAVValue@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::CharReaderBuilder::operator[](std::wstring)
0x18002185a  nop
0x18002185b  lea     rdx, [rsp+110h+var_D8]
0x180021860  mov     rcx, rax
0x180021863  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180021868  lea     rax, [rsp+110h+var_D8]
0x18002186d  mov     [rbp+57h+var_B0], rax
0x180021871  mov     byte ptr [rbp+57h+var_D0], 5
0x180021875  and     [rbp+57h+var_D0], esi
0x180021878  xorps   xmm0, xmm0
0x18002187b  movdqu  [rbp+57h+var_C8], xmm0
0x180021880  mov     [rbp+57h+var_B8], 0
0x180021888  mov     [rsp+110h+var_D8], 1
0x18002188d  lea     rdx, aRejectdupkeys; "rejectDupKeys"
0x180021894  lea     rcx, [rbp+57h+var_40]
0x180021898  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002189d  mov     rdx, rax
0x1800218a0  lea     rcx, [rbp+57h+var_70]
0x1800218a4  call    ??ACharReaderBuilder@Json@@QEAAAEAVValue@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::CharReaderBuilder::operator[](std::wstring)
0x1800218a9  nop
0x1800218aa  lea     rdx, [rsp+110h+var_D8]
0x1800218af  mov     rcx, rax
0x1800218b2  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x1800218b7  lea     rcx, [rbp+57h+var_70]; this
0x1800218bb  call    ?newCharReader@CharReaderBuilder@Json@@UEBAPEAVCharReader@2@XZ; Json::CharReaderBuilder::newCharReader(void)
0x1800218c0  mov     rsi, rax
0x1800218c3  mov     [rsp+110h+var_E0], rax
0x1800218c8  xor     edx, edx
0x1800218ca  lea     rcx, [rbp+57h+var_98]
0x1800218ce  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x1800218d3  nop
0x1800218d4  mov     rdx, [rdi]
0x1800218d7  mov     r9, [rsi]
0x1800218da  mov     rcx, [rdi+8]
0x1800218de  sub     rcx, rdx
0x1800218e1  shr     rcx, 1
0x1800218e4  lea     r8, [rdx+rcx*2]
0x1800218e8  mov     rax, [r9+8]
0x1800218ec  mov     [rsp+110h+var_F0], 0
0x1800218f5  lea     r9, [rbp+57h+var_98]
0x1800218f9  mov     rcx, rsi
0x1800218fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021901  test    al, al
0x180021903  jz      short loc_180021952
0x180021905  lea     rdx, [rbp+57h+var_98]
0x180021909  mov     rcx, rbx
0x18002190c  call    ??0?$Optional@VValue@Json@@@Core@@QEAA@$$QEAVValue@Json@@@Z; Core::Optional<Json::Value>::Optional<Json::Value>(Json::Value &&)
0x180021911  nop
0x180021912  lea     rcx, [rbp+57h+var_98]; this
0x180021916  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18002191b  nop
0x18002191c  lea     rcx, [rsp+110h+var_E0]
0x180021921  call    ??1?$unique_ptr@VNetworkRequestImplWindowsService@Pal@@U?$default_delete@VNetworkRequestImplWindowsService@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImplWindowsService>::~unique_ptr<Pal::NetworkRequestImplWindowsService>(void)
0x180021926  nop
0x180021927  lea     rcx, [rbp+57h+var_70]; this
0x18002192b  call    ??1CharReaderBuilder@Json@@UEAA@XZ; Json::CharReaderBuilder::~CharReaderBuilder(void)
0x180021930  mov     rax, rbx
0x180021933  mov     rcx, [rbp+57h+var_20]
0x180021937  xor     rcx, rsp; StackCookie
0x18002193a  call    __security_check_cookie
0x18002193f  mov     rbx, [rsp+110h+arg_0]
0x180021947  add     rsp, 100h
0x18002194e  pop     rdi
0x18002194f  pop     rsi
0x180021950  pop     rbp
0x180021951  retn
0x180021952  lea     rcx, [rbp+57h+var_40]
0x180021956  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002195b  nop
0x18002195c  mov     rcx, [rdi]
0x18002195f  mov     rax, [rdi+8]
0x180021963  sub     rax, rcx
0x180021966  js      loc_1800219EF
0x18002196c  test    rcx, rcx
0x18002196f  jnz     short loc_180021976
0x180021971  test    rax, rax
0x180021974  jnz     short loc_1800219EF
0x180021976  mov     [rbp+57h+var_B0], rax
0x18002197a  mov     [rbp+57h+var_A8], rcx
0x18002197e  lea     rdx, [rbp+57h+var_40]
0x180021982  lea     rcx, [rbp+57h+var_B0]
0x180021986  call    ?decodeUTF8@Text@Core@@SAXV?$basic_string_span@$$CBD$0?0@gsl@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Core::Text::decodeUTF8(gsl::basic_string_span<char const,-1>,std::wstring *)
0x18002198b  lea     rcx, [rbp+57h+var_40]
0x18002198f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021994  mov     r10, rax
0x180021997  mov     rdx, [rsi]
0x18002199a  mov     rcx, [rbp+57h+var_30]
0x18002199e  lea     r8, [rax+rcx*2]
0x1800219a2  mov     rax, [rdx+8]
0x1800219a6  mov     [rsp+110h+var_F0], 0
0x1800219af  lea     r9, [rbp+57h+var_98]
0x1800219b3  mov     rdx, r10
0x1800219b6  mov     rcx, rsi
0x1800219b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219be  test    al, al
0x1800219c0  jz      short loc_1800219DD
0x1800219c2  lea     rdx, [rbp+57h+var_98]
0x1800219c6  mov     rcx, rbx
0x1800219c9  call    ??0?$Optional@VValue@Json@@@Core@@QEAA@$$QEAVValue@Json@@@Z; Core::Optional<Json::Value>::Optional<Json::Value>(Json::Value &&)
0x1800219ce  nop
0x1800219cf  lea     rcx, [rbp+57h+var_40]
0x1800219d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800219d8  jmp     loc_180021912
0x1800219dd  lea     rcx, [rbp+57h+var_40]
0x1800219e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800219e6  mov     byte ptr [rbx+28h], 0
0x1800219ea  jmp     loc_180021912
0x1800219ef  call    cs:__imp__o_terminate
```
