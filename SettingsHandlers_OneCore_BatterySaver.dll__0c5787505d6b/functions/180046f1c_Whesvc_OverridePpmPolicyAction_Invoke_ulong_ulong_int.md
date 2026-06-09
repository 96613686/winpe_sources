# Whesvc::OverridePpmPolicyAction::Invoke(ulong,ulong,int)

- ea: `0x180046f1c`
- end: `0x180047208`
- name: `?Invoke@OverridePpmPolicyAction@Whesvc@@QEAAJKKH@Z`
- size: `748`
- prototype: `__int64 __fastcall(Whesvc::OverridePpmPolicyAction *this, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800451c0`

## callees

- `0x180009190`
- `0x18000eacc`
- `0x18001155c`
- `0x18003459c`
- `0x180046d38`
- `0x180046f1c`
- `0x1800473c0`
- `0x180047408`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180047038`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004711d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180047038`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004711d`

## pseudocode

```c
__int64 __fastcall Whesvc::OverridePpmPolicyAction::Invoke(Whesvc::OverridePpmPolicyAction *this, int a2, int a3)
{
  char Variant; // al
  __int64 v6; // rdx
  float v7; // xmm6_4
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  signed int v10; // ebx
  __int64 v11; // rdx
  float v13; // xmm6_4
  LSTATUS v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rdx
  int v18; // eax
  LSTATUS v19; // eax
  int lpData; // [rsp+28h] [rbp-39h]
  int lpDataa; // [rsp+28h] [rbp-39h]
  int Data; // [rsp+38h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-21h] BYREF
  HKEY v24; // [rsp+48h] [rbp-19h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-11h] BYREF
  __m128i si128; // [rsp+60h] [rbp-1h]
  _QWORD v27[3]; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int64 v28; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetImpl'::`2'::impl);
  if ( Variant == 1 )
  {
    v7 = FLOAT_90_0;
  }
  else if ( Variant == 2 )
  {
    v7 = FLOAT_85_0;
  }
  else
  {
    v7 = FLOAT_95_0;
  }
  GetFullRegistryPath(v27, v6, L"75b0ae3f-bce0-45a7-8c89-c9611c25e100");
  hKey = 0;
  v9 = v27;
  if ( v28 > 7 )
    v9 = (_QWORD *)v27[0];
  v10 = wil::reg::create_unique_key_nothrow(v8, v9, &hKey);
  if ( v10 < 0 )
  {
    v11 = 57;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\overrideppmpolicyaction.cpp",
      (const char *)(unsigned int)v10,
      lpData);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v28 > 7 )
      std::_Deallocate<16>(v27[0], 2 * v28 + 2);
    return (unsigned int)v10;
  }
  v13 = v7 / 100.0;
  Data = (int)(float)((float)a3 * v13);
  v14 = RegSetKeyValueW(hKey, 0, L"ProvDcSettingIndex", 4u, &Data, 4u);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( v10 < 0 )
  {
    v11 = 60;
    goto LABEL_10;
  }
  GetFullRegistryPath(v25, v15, L"75b0ae3f-bce0-45a7-8c89-c9611c25e101");
  v24 = 0;
  v17 = v25;
  if ( si128.m128i_i64[1] > 7uLL )
    v17 = (_QWORD *)v25[0];
  v18 = wil::reg::create_unique_key_nothrow(v16, v17, &v24);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\overrideppmpolicyaction.cpp",
      (const char *)(unsigned int)v18,
      lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v25[0], 2 * si128.m128i_i64[1] + 2);
LABEL_23:
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v25[0]) = 0;
    goto LABEL_11;
  }
  Data = (int)(float)((float)a2 * v13);
  v19 = RegSetKeyValueW(v24, 0, L"ProvDcSettingIndex", 4u, &Data, 4u);
  v10 = v19;
  if ( v19 > 0 )
    v10 = (unsigned __int16)v19 | 0x80070000;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\overrideppmpolicyaction.cpp",
      (const char *)(unsigned int)v10,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v25[0], 2 * si128.m128i_i64[1] + 2);
    goto LABEL_23;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v25[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25[0]) = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( v28 > 7 )
    std::_Deallocate<16>(v27[0], 2 * v28 + 2);
  return 0;
}

```

## disassembly

```asm
0x180046f1c  mov     rax, rsp
0x180046f1f  mov     [rax+8], rbx
0x180046f23  push    rbp
0x180046f24  push    rsi
0x180046f25  push    rdi
0x180046f26  lea     rbp, [rax-5Fh]
0x180046f2a  sub     rsp, 0A0h
0x180046f31  movaps  xmmword ptr [rax-28h], xmm6
0x180046f35  mov     rax, cs:__security_cookie
0x180046f3c  xor     rax, rsp
0x180046f3f  mov     [rbp+57h+var_28], rax
0x180046f43  mov     edi, r8d
0x180046f46  mov     esi, edx
0x180046f48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HighPowerDrainFMax@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HighPowerDrainFMax@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax> `wil::Feature<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetImpl(void)'::`2'::impl
0x180046f4f  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_HighPowerDrainFMax@@@details@wil@@QEAA?AW4Variant_HighPowerDrainFMax@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180046f54  movzx   ecx, al
0x180046f57  sub     ecx, 1
0x180046f5a  jz      short loc_180046F75
0x180046f5c  cmp     ecx, 1
0x180046f5f  jz      short loc_180046F6B
0x180046f61  movss   xmm6, cs:__real@42be0000
0x180046f69  jmp     short loc_180046F7D
0x180046f6b  movss   xmm6, cs:__real@42aa0000
0x180046f73  jmp     short loc_180046F7D
0x180046f75  movss   xmm6, cs:__real@42b40000
0x180046f7d  lea     r8, a75b0ae3fBce045; "75b0ae3f-bce0-45a7-8c89-c9611c25e100"
0x180046f84  lea     rcx, [rbp+57h+var_48]
0x180046f88  call    ?GetFullRegistryPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG000@Z; GetFullRegistryPath(ushort const *,ushort const *,ushort const *,ushort const *)
0x180046f8d  nop
0x180046f8e  mov     [rbp+57h+hKey], 0
0x180046f96  lea     rdx, [rbp+57h+var_48]
0x180046f9a  cmp     [rbp+57h+var_30], 7
0x180046f9f  cmova   rdx, [rbp+57h+var_48]
0x180046fa4  lea     r8, [rbp+57h+hKey]
0x180046fa8  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180046fad  mov     ebx, eax
0x180046faf  test    eax, eax
0x180046fb1  jns     short loc_180046FF8
0x180046fb3  mov     edx, 39h ; '9'; void *
0x180046fb8  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x180046fbf  mov     r9d, ebx; char *
0x180046fc2  mov     rcx, [rbp+5Fh]; this
0x180046fc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046fcb  nop
0x180046fcc  lea     rcx, [rbp+57h+hKey]
0x180046fd0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180046fd5  nop
0x180046fd6  mov     rdx, [rbp+57h+var_30]
0x180046fda  cmp     rdx, 7
0x180046fde  jbe     short loc_180046FF1
0x180046fe0  lea     rdx, ds:2[rdx*2]
0x180046fe8  mov     rcx, [rbp+57h+var_48]
0x180046fec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180046ff1  mov     eax, ebx
0x180046ff3  jmp     loc_1800471E4
0x180046ff8  divss   xmm6, cs:__real@42c80000
0x180047000  xorps   xmm0, xmm0
0x180047003  cvtsi2ss xmm0, rdi
0x180047008  mulss   xmm0, xmm6
0x18004700c  cvttss2si rax, xmm0
0x180047011  mov     [rbp+57h+Data], eax
0x180047014  mov     [rsp+0B0h+cbData], 4; cbData
0x18004701c  lea     rax, [rbp+57h+Data]
0x180047020  mov     [rsp+0B0h+lpData], rax; int
0x180047025  mov     r9d, 4; dwType
0x18004702b  lea     r8, aProvdcsettingi; "ProvDcSettingIndex"
0x180047032  xor     edx, edx; lpSubKey
0x180047034  mov     rcx, [rbp+57h+hKey]; hKey
0x180047038  call    cs:__imp_RegSetKeyValueW
0x18004703e  mov     ebx, eax
0x180047040  mov     edi, 80070000h
0x180047045  test    eax, eax
0x180047047  jle     short loc_18004704E
0x180047049  movzx   ebx, ax
0x18004704c  or      ebx, edi
0x18004704e  test    ebx, ebx
0x180047050  jns     short loc_18004705C
0x180047052  mov     edx, 3Ch ; '<'
0x180047057  jmp     loc_180046FB8
0x18004705c  lea     r8, a75b0ae3fBce045_0; "75b0ae3f-bce0-45a7-8c89-c9611c25e101"
0x180047063  lea     rcx, [rbp+57h+var_68]
0x180047067  call    ?GetFullRegistryPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG000@Z; GetFullRegistryPath(ushort const *,ushort const *,ushort const *,ushort const *)
0x18004706c  mov     [rbp+57h+var_70], 0
0x180047074  lea     rdx, [rbp+57h+var_68]
0x180047078  cmp     [rbp+57h+var_50], 7
0x18004707d  cmova   rdx, [rbp+57h+var_68]
0x180047082  lea     r8, [rbp+57h+var_70]
0x180047086  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18004708b  mov     ebx, eax
0x18004708d  test    eax, eax
0x18004708f  jns     short loc_1800470E5
0x180047091  mov     rcx, [rbp+5Fh]; this
0x180047095  mov     r9d, eax; char *
0x180047098  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x18004709f  mov     edx, 42h ; 'B'; void *
0x1800470a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800470a9  lea     rcx, [rbp+57h+var_70]
0x1800470ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800470b2  mov     rdx, [rbp+57h+var_50]
0x1800470b6  cmp     rdx, 7
0x1800470ba  jbe     short loc_1800470CD
0x1800470bc  lea     rdx, ds:2[rdx*2]
0x1800470c4  mov     rcx, [rbp+57h+var_68]
0x1800470c8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800470cd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800470d5  movdqu  xmmword ptr [rbp-1], xmm0
0x1800470da  xor     eax, eax
0x1800470dc  mov     word ptr [rbp+57h+var_68], ax
0x1800470e0  jmp     loc_180046FCC
0x1800470e5  xorps   xmm0, xmm0
0x1800470e8  cvtsi2ss xmm0, rsi
0x1800470ed  mulss   xmm0, xmm6
0x1800470f1  cvttss2si rax, xmm0
0x1800470f6  mov     [rbp+57h+Data], eax
0x1800470f9  mov     [rsp+0B0h+cbData], 4; cbData
0x180047101  lea     rax, [rbp+57h+Data]
0x180047105  mov     [rsp+0B0h+lpData], rax; int
0x18004710a  mov     r9d, 4; dwType
0x180047110  lea     r8, aProvdcsettingi; "ProvDcSettingIndex"
0x180047117  xor     edx, edx; lpSubKey
0x180047119  mov     rcx, [rbp+57h+var_70]; hKey
0x18004711d  call    cs:__imp_RegSetKeyValueW
0x180047123  mov     ebx, eax
0x180047125  test    eax, eax
0x180047127  jle     short loc_18004712E
0x180047129  movzx   ebx, ax
0x18004712c  or      ebx, edi
0x18004712e  test    ebx, ebx
0x180047130  jns     short loc_180047186
0x180047132  mov     rcx, [rbp+5Fh]; this
0x180047136  mov     r9d, ebx; char *
0x180047139  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x180047140  mov     edx, 45h ; 'E'; void *
0x180047145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004714a  lea     rcx, [rbp+57h+var_70]
0x18004714e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180047153  mov     rdx, [rbp+57h+var_50]
0x180047157  cmp     rdx, 7
0x18004715b  jbe     short loc_18004716E
0x18004715d  lea     rdx, ds:2[rdx*2]
0x180047165  mov     rcx, [rbp+57h+var_68]
0x180047169  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004716e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180047176  movdqu  xmmword ptr [rbp-1], xmm0
0x18004717b  xor     ecx, ecx
0x18004717d  mov     word ptr [rbp+57h+var_68], cx
0x180047181  jmp     loc_180046FCC
0x180047186  lea     rcx, [rbp+57h+var_70]
0x18004718a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004718f  mov     rdx, [rbp+57h+var_50]
0x180047193  cmp     rdx, 7
0x180047197  jbe     short loc_1800471AA
0x180047199  lea     rdx, ds:2[rdx*2]
0x1800471a1  mov     rcx, [rbp+57h+var_68]
0x1800471a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800471aa  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800471b2  movdqu  xmmword ptr [rbp-1], xmm0
0x1800471b7  xor     eax, eax
0x1800471b9  mov     word ptr [rbp+57h+var_68], ax
0x1800471bd  lea     rcx, [rbp+57h+hKey]
0x1800471c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800471c6  nop
0x1800471c7  mov     rdx, [rbp+57h+var_30]
0x1800471cb  cmp     rdx, 7
0x1800471cf  jbe     short loc_1800471E2
0x1800471d1  lea     rdx, ds:2[rdx*2]
0x1800471d9  mov     rcx, [rbp+57h+var_48]
0x1800471dd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800471e2  xor     eax, eax
0x1800471e4  mov     rcx, [rbp+57h+var_28]
0x1800471e8  xor     rcx, rsp; StackCookie
0x1800471eb  call    __security_check_cookie
0x1800471f0  lea     r11, [rsp+0B0h+var_10]
0x1800471f8  mov     rbx, [r11+20h]
0x1800471fc  movaps  xmm6, xmmword ptr [r11-10h]
0x180047201  mov     rsp, r11
0x180047204  pop     rdi
0x180047205  pop     rsi
0x180047206  pop     rbp
0x180047207  retn
```
