# wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> const &,wil::cloud_store_load_options,char const *)

- ea: `0x180006d7c`
- end: `0x180006fd4`
- name: `??$load@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@AEBU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z`
- size: `600`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800144c0`
- `0x180015624`

## callees

- `0x1800056c8`
- `0x180005700`
- `0x180005880`
- `0x180006d7c`
- `0x180025308`
- `0x180026bc8`
- `0x18002a030`
- `0x18002f214`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int128 *v8; // rdx
  __int128 *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  wil::details_abi *v13; // rcx
  bool v14; // dl
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  struct wil::details::IFunctorHost *v16; // r8
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+28h] [rbp-D8h]
  void **v20; // [rsp+30h] [rbp-D0h] BYREF
  struct wil::details_abi::ThreadLocalData *v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h]
  _QWORD *v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[3]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v32; // [rsp+B8h] [rbp-48h]
  __int64 v33; // [rsp+C0h] [rbp-40h]
  int *v34; // [rsp+C8h] [rbp-38h]
  __int64 *v35; // [rsp+D0h] [rbp-30h]
  __int128 v36; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v37; // [rsp+E8h] [rbp-18h]
  _QWORD v38[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v39; // [rsp+110h] [rbp+10h] BYREF
  __int128 v40; // [rsp+120h] [rbp+20h]
  _UNKNOWN *retaddr; // [rsp+158h] [rbp+58h]

  v29 = a2;
  v19 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::string::_Construct<1,char const *>(&v30, &dword_180043B4C, 0);
  v25 = a3;
  v18 = a4;
  v33 = a1;
  v34 = &v18;
  v35 = &v25;
  v36 = 0;
  v37 = 0;
  v8 = &v30;
  if ( v32 > 0xF )
    v8 = (__int128 *)v30;
  std::string::_Construct<2,char const *>(&v36, v8, v31);
  v27[0] = retaddr;
  v27[1] = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
  v27[2] = "Load";
  v28 = 1300;
  v38[0] = v33;
  v38[1] = v34;
  v38[2] = v35;
  v39 = 0;
  v40 = 0;
  v9 = &v36;
  if ( *((_QWORD *)&v37 + 1) > 0xFu )
    v9 = (__int128 *)v36;
  std::string::_Construct<2,char const *>(&v39, v9, v37);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl'::`2'::impl,
    v10,
    v11,
    v12);
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)(a2 + 24) = 1;
  *(_BYTE *)(a2 + 32) = 1;
  v19 = 32;
  v26[0] = &wil::details::functor_wrapper_other<_lambda_cc1b274828db2bc48063dbe1061c0642_ &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>::`vftable';
  v26[1] = v38;
  v26[2] = a2;
  v20 = &wil::details::FeatureFunctorHost::`vftable';
  LOBYTE(v13) = 1;
  ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v13, v14);
  v21 = ThreadLocalDataCache;
  v22 = 0;
  if ( ThreadLocalDataCache )
  {
    HIDWORD(v22) = *((_DWORD *)ThreadLocalDataCache + 4);
    LODWORD(v22) = **((_DWORD **)ThreadLocalDataCache + 1);
    *((_DWORD *)v21 + 4) = v22;
  }
  v23 = v27;
  v24 = 6201249;
  wil::details::RunFunctor((wil::details *)v26, (struct wil::details::IFunctor *)&v20, v16);
  if ( v21 )
    *((_DWORD *)v21 + 4) = HIDWORD(v22);
  if ( *((_QWORD *)&v40 + 1) > 0xFu )
    std::_Deallocate<16>((void *)v39, *((_QWORD *)&v40 + 1) + 1LL);
  if ( *((_QWORD *)&v37 + 1) > 0xFu )
    std::_Deallocate<16>((void *)v36, *((_QWORD *)&v37 + 1) + 1LL);
  if ( v32 > 0xF )
    std::_Deallocate<16>((void *)v30, v32 + 1);
  return a2;
}

```

## disassembly

```asm
0x180006d7c  mov     [rsp-8+arg_0], rbx
0x180006d81  mov     [rsp-8+arg_10], rsi
0x180006d86  push    rbp
0x180006d87  push    rdi
0x180006d88  push    r14
0x180006d8a  lea     rbp, [rsp-40h]
0x180006d8f  sub     rsp, 140h
0x180006d96  mov     rax, cs:__security_cookie
0x180006d9d  xor     rax, rsp
0x180006da0  mov     [rbp+50h+var_20], rax
0x180006da4  mov     esi, r9d
0x180006da7  mov     rbx, r8
0x180006daa  mov     r14, rdx
0x180006dad  mov     rdi, rcx
0x180006db0  mov     [rbp+50h+var_B8], rdx
0x180006db4  mov     [rsp+150h+var_128], 0
0x180006dbc  xorps   xmm0, xmm0
0x180006dbf  movups  [rbp+50h+var_B0], xmm0
0x180006dc3  mov     [rbp+50h+var_A0], 0
0x180006dcb  mov     [rbp+50h+var_98], 0
0x180006dd3  xor     r8d, r8d
0x180006dd6  lea     rdx, dword_180043B4C
0x180006ddd  lea     rcx, [rbp+50h+var_B0]
0x180006de1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180006de6  nop
0x180006de7  mov     [rsp+150h+var_F8], rbx
0x180006dec  mov     [rsp+150h+var_130], esi
0x180006df0  mov     [rbp+50h+var_90], rdi
0x180006df4  lea     rax, [rsp+150h+var_130]
0x180006df9  mov     [rbp+50h+var_88], rax
0x180006dfd  lea     rax, [rsp+150h+var_F8]
0x180006e02  mov     [rbp+50h+var_80], rax
0x180006e06  xorps   xmm0, xmm0
0x180006e09  movups  [rbp+50h+var_78], xmm0
0x180006e0d  xorps   xmm1, xmm1
0x180006e10  movdqu  [rbp+50h+var_68], xmm1
0x180006e15  lea     rdx, [rbp+50h+var_B0]
0x180006e19  cmp     [rbp+50h+var_98], 0Fh
0x180006e1e  cmova   rdx, qword ptr [rbp+50h+var_B0]
0x180006e23  mov     r8, [rbp+50h+var_A0]
0x180006e27  lea     rcx, [rbp+50h+var_78]
0x180006e2b  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180006e30  nop
0x180006e31  mov     rax, [rbp+58h]
0x180006e35  mov     [rsp+150h+var_D8], rax
0x180006e3a  lea     rax, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180006e41  mov     [rbp+50h+var_D0], rax
0x180006e45  lea     rax, aLoad; "Load"
0x180006e4c  mov     [rbp+50h+var_C8], rax
0x180006e50  mov     eax, 514h
0x180006e55  mov     [rbp+50h+var_C0], ax
0x180006e59  mov     rax, [rbp+50h+var_90]
0x180006e5d  mov     [rbp+50h+var_58], rax
0x180006e61  mov     rax, [rbp+50h+var_88]
0x180006e65  mov     [rbp+50h+var_50], rax
0x180006e69  mov     rax, [rbp+50h+var_80]
0x180006e6d  mov     [rbp+50h+var_48], rax
0x180006e71  xorps   xmm0, xmm0
0x180006e74  movups  [rbp+50h+var_40], xmm0
0x180006e78  xorps   xmm1, xmm1
0x180006e7b  movdqu  [rbp+50h+var_30], xmm1
0x180006e80  lea     rdx, [rbp+50h+var_78]
0x180006e84  cmp     qword ptr [rbp+50h+var_68+8], 0Fh
0x180006e89  cmova   rdx, qword ptr [rbp+50h+var_78]
0x180006e8e  mov     r8, qword ptr [rbp+50h+var_68]
0x180006e92  lea     rcx, [rbp+50h+var_40]
0x180006e96  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180006e9b  nop
0x180006e9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudStore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore> `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl(void)'::`2'::impl
0x180006ea3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180006ea8  nop
0x180006ea9  xorps   xmm0, xmm0
0x180006eac  xor     eax, eax
0x180006eae  movups  xmmword ptr [r14], xmm0
0x180006eb2  movups  xmmword ptr [r14+10h], xmm0
0x180006eb7  mov     [r14+20h], rax
0x180006ebb  mov     [r14], rax
0x180006ebe  mov     [r14+10h], rax
0x180006ec2  mov     word ptr [r14+18h], 1
0x180006ec9  mov     byte ptr [r14+20h], 1
0x180006ece  mov     [rsp+150h+var_128], 20h ; ' '
0x180006ed6  lea     rax, ??_7?$functor_wrapper_other@AEAV_lambda_cc1b274828db2bc48063dbe1061c0642_@@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@details@wil@@6B@; const wil::details::functor_wrapper_other<_lambda_cc1b274828db2bc48063dbe1061c0642_ &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>::`vftable'
0x180006edd  mov     [rsp+150h+var_F0], rax
0x180006ee2  lea     rax, [rbp+50h+var_58]
0x180006ee6  mov     [rsp+150h+var_E8], rax
0x180006eeb  mov     [rsp+150h+var_E0], r14
0x180006ef0  lea     rax, ??_7FeatureFunctorHost@details@wil@@6B@; const wil::details::FeatureFunctorHost::`vftable'
0x180006ef7  mov     [rsp+150h+var_120], rax
0x180006efc  mov     cl, 1; this
0x180006efe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006f03  mov     rcx, rax
0x180006f06  mov     [rsp+150h+var_118], rax
0x180006f0b  mov     [rsp+150h+var_110], 0
0x180006f14  test    rax, rax
0x180006f17  jz      short loc_180006F32
0x180006f19  mov     eax, [rax+10h]
0x180006f1c  mov     dword ptr [rsp+150h+var_110+4], eax
0x180006f20  mov     rax, [rcx+8]
0x180006f24  mov     ecx, [rax]
0x180006f26  mov     dword ptr [rsp+150h+var_110], ecx
0x180006f2a  mov     rax, [rsp+150h+var_118]
0x180006f2f  mov     [rax+10h], ecx
0x180006f32  lea     rax, [rsp+150h+var_D8]
0x180006f37  mov     [rsp+150h+var_108], rax
0x180006f3c  mov     [rsp+150h+var_100], 5E9FA1h
0x180006f44  lea     rdx, [rsp+150h+var_120]; struct wil::details::IFunctor *
0x180006f49  lea     rcx, [rsp+150h+var_F0]; this
0x180006f4e  call    ?RunFunctor@details@wil@@YAJAEAUIFunctor@12@AEAUIFunctorHost@12@@Z; wil::details::RunFunctor(wil::details::IFunctor &,wil::details::IFunctorHost &)
0x180006f53  nop
0x180006f54  mov     rcx, [rsp+150h+var_118]
0x180006f59  test    rcx, rcx
0x180006f5c  jz      short loc_180006F65
0x180006f5e  mov     eax, dword ptr [rsp+150h+var_110+4]
0x180006f62  mov     [rcx+10h], eax
0x180006f65  mov     rdx, qword ptr [rbp+50h+var_30+8]
0x180006f69  cmp     rdx, 0Fh
0x180006f6d  ja      short loc_180006FAA
0x180006f6f  mov     rdx, qword ptr [rbp+50h+var_68+8]
0x180006f73  cmp     rdx, 0Fh
0x180006f77  ja      short loc_180006FB8
0x180006f79  mov     rdx, [rbp+50h+var_98]
0x180006f7d  cmp     rdx, 0Fh
0x180006f81  ja      short loc_180006FC6
0x180006f83  mov     rax, r14
0x180006f86  mov     rcx, [rbp+50h+var_20]
0x180006f8a  xor     rcx, rsp; StackCookie
0x180006f8d  call    __security_check_cookie
0x180006f92  lea     r11, [rsp+150h+var_10]
0x180006f9a  mov     rbx, [r11+20h]
0x180006f9e  mov     rsi, [r11+30h]
0x180006fa2  mov     rsp, r11
0x180006fa5  pop     r14
0x180006fa7  pop     rdi
0x180006fa8  pop     rbp
0x180006fa9  retn
0x180006faa  inc     rdx
0x180006fad  mov     rcx, qword ptr [rbp+50h+var_40]
0x180006fb1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006fb6  jmp     short loc_180006F6F
0x180006fb8  inc     rdx
0x180006fbb  mov     rcx, qword ptr [rbp+50h+var_78]
0x180006fbf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006fc4  jmp     short loc_180006F79
0x180006fc6  inc     rdx
0x180006fc9  mov     rcx, qword ptr [rbp+50h+var_B0]
0x180006fcd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006fd2  jmp     short loc_180006F83
```
