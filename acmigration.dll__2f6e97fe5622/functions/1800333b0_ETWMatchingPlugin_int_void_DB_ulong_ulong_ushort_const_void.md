# ETWMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x1800333b0`
- end: `0x18003364d`
- name: `?ETWMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `669`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x180031e14`
- `0x1800333b0`
- `0x180034388`
- `0x18003f0b0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180033574`
- `KERNEL32!LocalFree` at `0x180033574`
- `ntdll!RtlFreeHeap` at `0x18003359c`
- `ntdll!RtlFreeHeap` at `0x18003359c`

## string_xrefs

- `0x180033475`: `Enter ETWMatchingPlugin.`
- `0x180033482`: `ETWMatchingPlugin`
- `0x1800334bb`: `ETWMatchingPlugin`
- `0x1800335f2`: `ETWMatchingPlugin`
- `0x1800334ae`: `Feature_Compat_ETWMatchingPlugin is not enabled.`
- `0x1800335e5`: `ETWMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ETWMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        void *a7)
{
  unsigned int v7; // r9d
  __int128 *v8; // rdx
  const char *v10; // rax
  int *v11; // [rsp+30h] [rbp-108h] BYREF
  int v12; // [rsp+38h] [rbp-100h] BYREF
  int v13; // [rsp+3Ch] [rbp-FCh] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-F8h] BYREF
  PVOID P; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-E8h] BYREF
  LPCWSTR *v17[12]; // [rsp+58h] [rbp-E0h] BYREF
  const std::exception *v18; // [rsp+B8h] [rbp-80h] BYREF
  __int128 v19; // [rsp+C0h] [rbp-78h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-68h]
  _OWORD v21[2]; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v22[32]; // [rsp+100h] [rbp-38h] BYREF

  v17[11] = (LPCWSTR *)-2LL;
  v11 = a1;
  hMem = 0;
  v12 = 0;
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  v13 = -2147467259;
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,unsigned short const *>(v22, &psz, 0);
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,unsigned short const *>(v21, &psz, 0);
  v16 = 0;
  P = 0;
  AslLogCallPrintf(3, "ETWMatchingPlugin", 814, "Enter ETWMatchingPlugin.");
  *v11 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin>::GetImpl'::`2'::impl) )
  {
    v17[0] = &a6;
    v17[1] = (LPCWSTR *)&v19;
    v17[2] = (LPCWSTR *)&v11;
    v17[3] = (LPCWSTR *)&a5;
    v17[4] = (LPCWSTR *)&hMem;
    v17[5] = (LPCWSTR *)&v12;
    v17[6] = (LPCWSTR *)v22;
    v17[7] = (LPCWSTR *)v21;
    v17[8] = (LPCWSTR *)&v16;
    v17[9] = (LPCWSTR *)&P;
    v17[10] = (LPCWSTR *)&v13;
    lambda_7e03e909c113ed1e88d46918739648af_::operator()(v17);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      P = 0;
    }
    try
    {
      v8 = &v19;
      if ( si128.m128i_i64[1] > 7uLL )
        LODWORD(v8) = v19;
      AppCompatUtility::AddCacheMatchingPlugin(
        (AppCompatUtility *)(unsigned int)*v11,
        (int)v8,
        (const unsigned __int16 *)(unsigned int)a5,
        v7);
    }
    catch ( const std::exception *v18 )
    {
      v10 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v18 + 8LL))(v18);
      AslLogCallPrintf(1, "ETWMatchingPlugin", 1011, "Exception: %s", v10);
    }
    catch ( ... )
    {
      AslLogCallPrintf(1, "ETWMatchingPlugin", 1015, "Unhandled exception.");
    }
    AslLogCallPrintf(3, "ETWMatchingPlugin", 1018, "ETWMatchingPlugin Matched = %d", *v11);
  }
  else
  {
    AslLogCallPrintf(3, "ETWMatchingPlugin", 819, "Feature_Compat_ETWMatchingPlugin is not enabled.");
  }
  std::wstring::~wstring(v21);
  std::wstring::~wstring(v22);
  std::wstring::~wstring(&v19);
  return 1;
}

```

## disassembly

```asm
0x1800333b0  mov     r11, rsp
0x1800333b3  sub     rsp, 138h
0x1800333ba  mov     qword ptr [r11-88h], 0FFFFFFFFFFFFFFFEh
0x1800333c5  mov     rax, cs:__security_cookie
0x1800333cc  xor     rax, rsp
0x1800333cf  mov     [rsp+138h+var_18], rax
0x1800333d7  mov     [rsp+138h+var_108], rcx
0x1800333dc  mov     [rsp+138h+hMem], 0
0x1800333e5  mov     [rsp+138h+var_100], 0
0x1800333ed  xorps   xmm0, xmm0
0x1800333f0  movups  xmmword ptr [r11-78h], xmm0
0x1800333f5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800333fd  movdqu  xmmword ptr [r11-68h], xmm1
0x180033403  xor     eax, eax
0x180033405  mov     [r11-78h], ax
0x18003340a  mov     [rsp+138h+var_FC], 80004005h
0x180033412  movups  xmmword ptr [r11-38h], xmm0
0x180033417  xorps   xmm1, xmm1
0x18003341a  movdqu  xmmword ptr [r11-28h], xmm1
0x180033420  xor     r8d, r8d
0x180033423  lea     rdx, psz
0x18003342a  lea     rcx, [r11-38h]
0x18003342e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033433  nop
0x180033434  xorps   xmm0, xmm0
0x180033437  movups  [rsp+138h+var_58], xmm0
0x18003343f  xorps   xmm1, xmm1
0x180033442  movdqu  [rsp+138h+var_48], xmm1
0x18003344b  xor     r8d, r8d
0x18003344e  lea     rdx, psz
0x180033455  lea     rcx, [rsp+138h+var_58]
0x18003345d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033462  nop
0x180033463  mov     [rsp+138h+var_E8], 0
0x18003346c  mov     [rsp+138h+P], 0
0x180033475  lea     r9, aEnterEtwmatchi; "Enter ETWMatchingPlugin."
0x18003347c  mov     r8d, 32Eh
0x180033482  lea     rdx, aEtwmatchingplu_2; "ETWMatchingPlugin"
0x180033489  mov     ecx, 3
0x18003348e  call    AslLogCallPrintf
0x180033493  mov     rax, [rsp+138h+var_108]
0x180033498  mov     dword ptr [rax], 0
0x18003349e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin> `wil::Feature<__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin>::GetImpl(void)'::`2'::impl
0x1800334a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_ETWMatchingPlugin>::__private_IsEnabled(void)
0x1800334aa  test    al, al
0x1800334ac  jnz     short loc_1800334D1
0x1800334ae  lea     r9, aFeatureCompatE; "Feature_Compat_ETWMatchingPlugin is not"...
0x1800334b5  mov     r8d, 333h
0x1800334bb  lea     rdx, aEtwmatchingplu_2; "ETWMatchingPlugin"
0x1800334c2  mov     ecx, 3
0x1800334c7  call    AslLogCallPrintf
0x1800334cc  jmp     loc_180033604
0x1800334d1  lea     rax, [rsp+138h+arg_28]
0x1800334d9  mov     [rsp+138h+var_E0], rax
0x1800334de  lea     rax, [rsp+138h+var_78]
0x1800334e6  mov     [rsp+138h+var_D8], rax
0x1800334eb  lea     rax, [rsp+138h+var_108]
0x1800334f0  mov     [rsp+138h+var_D0], rax
0x1800334f5  lea     rax, [rsp+138h+arg_20]
0x1800334fd  mov     [rsp+138h+var_C8], rax
0x180033502  lea     rax, [rsp+138h+hMem]
0x180033507  mov     [rsp+138h+var_C0], rax
0x18003350c  lea     rax, [rsp+138h+var_100]
0x180033511  mov     [rsp+138h+var_B8], rax
0x180033519  lea     rax, [rsp+138h+var_38]
0x180033521  mov     [rsp+138h+var_B0], rax
0x180033529  lea     rax, [rsp+138h+var_58]
0x180033531  mov     [rsp+138h+var_A8], rax
0x180033539  lea     rax, [rsp+138h+var_E8]
0x18003353e  mov     [rsp+138h+var_A0], rax
0x180033546  lea     rax, [rsp+138h+P]
0x18003354b  mov     [rsp+138h+var_98], rax
0x180033553  lea     rax, [rsp+138h+var_FC]
0x180033558  mov     [rsp+138h+var_90], rax
0x180033560  lea     rcx, [rsp+138h+var_E0]
0x180033565  call    _lambda_7e03e909c113ed1e88d46918739648af___operator__
0x18003356a  mov     rcx, [rsp+138h+hMem]; hMem
0x18003356f  test    rcx, rcx
0x180033572  jz      short loc_180033583
0x180033574  call    cs:__imp_LocalFree
0x18003357a  mov     [rsp+138h+hMem], 0
0x180033583  mov     r8, [rsp+138h+P]; P
0x180033588  test    r8, r8
0x18003358b  jz      short loc_1800335AB
0x18003358d  mov     rcx, gs:60h
0x180033596  xor     edx, edx; Flags
0x180033598  mov     rcx, [rcx+30h]; HeapHandle
0x18003359c  call    cs:__imp_RtlFreeHeap
0x1800335a2  mov     [rsp+138h+P], 0
0x1800335ab  lea     rdx, [rsp+138h+var_78]
0x1800335b3  cmp     [rsp+138h+var_60], 7
0x1800335bc  cmova   rdx, qword ptr [rsp+138h+var_78]; int
0x1800335c5  mov     r8d, dword ptr [rsp+138h+arg_20]; unsigned __int16 *
0x1800335cd  mov     rcx, [rsp+138h+var_108]
0x1800335d2  mov     ecx, [rcx]; this
0x1800335d4  call    ?AddCacheMatchingPlugin@AppCompatUtility@@YAXHPEBGK@Z; AppCompatUtility::AddCacheMatchingPlugin(int,ushort const *,ulong)
0x1800335d9  nop
0x1800335da  mov     rax, [rsp+138h+var_108]
0x1800335df  mov     ecx, [rax]
0x1800335e1  mov     [rsp+138h+var_118], ecx
0x1800335e5  lea     r9, aEtwmatchingplu; "ETWMatchingPlugin Matched = %d"
0x1800335ec  mov     r8d, 3FAh
0x1800335f2  lea     rdx, aEtwmatchingplu_2; "ETWMatchingPlugin"
0x1800335f9  mov     ecx, 3
0x1800335fe  call    AslLogCallPrintf
0x180033603  nop
0x180033604  lea     rcx, [rsp+138h+var_58]; void *
0x18003360c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033611  nop
0x180033612  lea     rcx, [rsp+138h+var_38]; void *
0x18003361a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003361f  nop
0x180033620  lea     rcx, [rsp+138h+var_78]; void *
0x180033628  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003362d  mov     eax, 1
0x180033632  mov     rcx, [rsp+138h+var_18]
0x18003363a  xor     rcx, rsp; StackCookie
0x18003363d  call    __security_check_cookie
0x180033642  add     rsp, 138h
0x180033649  retn
0x18003364a  jmp     short loc_1800335DA
```
