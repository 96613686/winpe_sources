# RoutingRegistryHelper::ReadAppletIdGroupAssetsRegKeys(ushort const *,_GUID const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180039afc`
- end: `0x180039e5f`
- name: `?ReadAppletIdGroupAssetsRegKeys@RoutingRegistryHelper@@SAJPEBGAEBU_GUID@@PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036064`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000c964`
- `0x180013274`
- `0x180018aa0`
- `0x180018b54`
- `0x180018e80`
- `0x1800194a8`
- `0x180039afc`
- `0x180065a30`
- `0x180065bd0`
- `0x18007d3ec`
- `0x18007d804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180039b73`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180039b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039e48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039e48`

## string_xrefs

- `0x180039b8c`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039ba7`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039c58`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039c9d`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180039d80`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RoutingRegistryHelper::ReadAppletIdGroupAssetsRegKeys(__int64 a1, const GUID *a2, __int64 a3)
{
  __m128i si128; // xmm6
  unsigned int v7; // ebx
  __int128 *v8; // rax
  unsigned int v9; // edx
  int v10; // eax
  __int64 v11; // r8
  HKEY v12; // rdx
  int v13; // eax
  bool v15[8]; // [rsp+28h] [rbp-E0h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-D8h] BYREF
  HKEY hKey_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+48h] [rbp-C0h]
  _QWORD v19[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-A0h] BYREF
  __m128i v21; // [rsp+78h] [rbp-90h] BYREF
  __int128 v22; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v23[2]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v24[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v25[32]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v26[3]; // [rsp+E8h] [rbp-20h] BYREF
  _WORD v27[260]; // [rsp+100h] [rbp-8h] BYREF
  int v28; // [rsp+308h] [rbp+200h]
  char v29; // [rsp+30Ch] [rbp+204h]
  OLECHAR sz[40]; // [rsp+318h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A0h] [rbp+298h]

  v23[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v23[1] = si128;
  LOWORD(v23[0]) = 0;
  memset_0(sz, 0, 0x4Eu);
  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)0x8000FFFFLL,
      *(int *)v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)0x8000FFFFLL,
      *(int *)v15);
LABEL_22:
    std::wstring::~wstring(v23);
    return v7;
  }
  *(_QWORD *)&v20 = a1;
  *((_QWORD *)&v20 + 1) = sz;
  v21.m128i_i64[0] = (__int64)L"Assets";
  v19[0] = &v20;
  v19[1] = &v21.m128i_i64[1];
  v8 = (__int128 *)NfcRegPath::NfcRegPath(v24, &qword_1800A1C18, v19);
  v22 = *v8;
  std::wstring::operator=(v23, v8 + 1);
  std::wstring::~wstring(v25);
  hKey = 0;
  v10 = NfcRegOpenKeyEx((const struct NfcRegistryLocation *)&v22, v9, 0x20019u, &hKey);
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F9,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)v7,
      *(int *)v15);
LABEL_20:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_22;
  }
  v26[1] = 0;
  v26[2] = 0;
  v28 = 0;
  v29 = 0;
  if ( !hKey )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FC,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)0x80004003LL,
      *(int *)v15);
LABEL_19:
    SERegistryUtils::RegistryKeyEnumerator::~RegistryKeyEnumerator((SERegistryUtils::RegistryKeyEnumerator *)v26);
    goto LABEL_20;
  }
  v26[0] = hKey;
  v29 = 1;
  *(_OWORD *)hKey_8 = 0;
  v18 = 0;
  while ( 1 )
  {
    v15[0] = 0;
    v13 = SERegistryUtils::RegistryKeyEnumerator::MoveNext((SERegistryUtils::RegistryKeyEnumerator *)v26, v15);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x403,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
        (const char *)(unsigned int)v13,
        *(int *)v15);
      std::vector<std::wstring>::_Tidy(hKey_8);
      goto LABEL_19;
    }
    if ( !v15[0] )
      break;
    v20 = 0;
    v21 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v27[v11] );
    std::wstring::_Construct<1,unsigned short const *>(&v20, v27);
    v12 = hKey_8[1];
    if ( hKey_8[1] == v18 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(hKey_8, hKey_8[1], &v20);
    }
    else
    {
      *(_OWORD *)hKey_8[1] = v20;
      *((__m128i *)v12 + 1) = v21;
      v21 = si128;
      LOWORD(v20) = 0;
      hKey_8[1] += 8;
    }
    std::wstring::~wstring(&v20);
  }
  if ( (HKEY *)a3 != hKey_8 )
  {
    std::vector<std::wstring>::_Tidy(a3);
    *(_OWORD *)a3 = *(_OWORD *)hKey_8;
    *(_QWORD *)(a3 + 16) = v18;
    *(_OWORD *)hKey_8 = 0;
    v18 = 0;
  }
  std::vector<std::wstring>::_Tidy(hKey_8);
  SERegistryUtils::RegistryKeyEnumerator::~RegistryKeyEnumerator((SERegistryUtils::RegistryKeyEnumerator *)v26);
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(v23);
  return 0;
}

```

## disassembly

```asm
0x180039afc  mov     rax, rsp
0x180039aff  mov     [rax+8], rbx
0x180039b03  mov     [rax+20h], rsi
0x180039b07  push    rbp
0x180039b08  push    rdi
0x180039b09  push    r14
0x180039b0b  lea     rbp, [rax-298h]
0x180039b12  sub     rsp, 380h
0x180039b19  movaps  xmmword ptr [rax-28h], xmm6
0x180039b1d  mov     rax, cs:__security_cookie
0x180039b24  xor     rax, rsp
0x180039b27  mov     [rbp+290h+var_30], rax
0x180039b2e  mov     rdi, r8
0x180039b31  mov     rbx, rdx
0x180039b34  mov     rsi, rcx
0x180039b37  xorps   xmm0, xmm0
0x180039b3a  movups  [rbp+290h+var_300], xmm0
0x180039b3e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180039b46  movdqu  [rbp+290h+var_2F0], xmm6
0x180039b4b  xor     r14d, r14d
0x180039b4e  mov     word ptr [rbp+290h+var_300], r14w
0x180039b53  xor     edx, edx; Val
0x180039b55  lea     r8d, [r14+4Eh]; Size
0x180039b59  lea     rcx, [rbp+290h+sz]; void *
0x180039b60  call    memset_0
0x180039b65  lea     r8d, [r14+27h]; cchMax
0x180039b69  lea     rdx, [rbp+290h+sz]; lpsz
0x180039b70  mov     rcx, rbx; rguid
0x180039b73  call    cs:__imp_StringFromGUID2
0x180039b79  test    eax, eax
0x180039b7b  jnz     short loc_180039BBD
0x180039b7d  mov     rcx, [rbp+298h]; this
0x180039b84  mov     ebx, 8000FFFFh
0x180039b89  mov     r9d, ebx; char *
0x180039b8c  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039b93  mov     edx, 494h; void *
0x180039b98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b9d  mov     rcx, [rbp+298h]; this
0x180039ba4  mov     r9d, ebx; char *
0x180039ba7  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039bae  mov     edx, 3F5h; void *
0x180039bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039bb8  jmp     loc_180039DB8
0x180039bbd  mov     qword ptr [rsp+390h+var_338+8], rsi
0x180039bc2  lea     rax, [rbp+290h+sz]
0x180039bc9  mov     qword ptr [rsp+390h+var_328], rax
0x180039bce  lea     rax, SubKey; "Assets"
0x180039bd5  mov     qword ptr [rsp+390h+var_328+8], rax
0x180039bda  lea     rax, [rsp+390h+var_338+8]
0x180039bdf  mov     [rsp+390h+var_340], rax
0x180039be4  lea     rax, [rsp+390h+var_318]
0x180039be9  mov     qword ptr [rsp+390h+var_338], rax
0x180039bee  lea     r8, [rsp+390h+var_340]
0x180039bf3  lea     rdx, qword_1800A1C18
0x180039bfa  lea     rcx, [rbp+290h+var_2E0]
0x180039bfe  call    ??0NfcRegPath@@QEAA@AEBUNfcRegistryLocation@@V?$initializer_list@PEBG@std@@@Z; NfcRegPath::NfcRegPath(NfcRegistryLocation const &,std::initializer_list<ushort const *>)
0x180039c03  movups  xmm0, xmmword ptr [rax]
0x180039c06  movdqu  [rbp+290h+var_310], xmm0
0x180039c0b  lea     rdx, [rax+10h]
0x180039c0f  lea     rcx, [rbp+290h+var_300]
0x180039c13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039c18  lea     rcx, [rbp+290h+var_2D0]
0x180039c1c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039c21  nop
0x180039c22  mov     [rsp+390h+hKey], r14
0x180039c27  lea     r9, [rsp+390h+hKey]; HKEY *
0x180039c2c  mov     r8d, 20019h; unsigned int
0x180039c32  lea     rcx, [rbp+290h+var_310]; struct NfcRegistryLocation *
0x180039c36  call    ?NfcRegOpenKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAPEAUHKEY__@@@Z; NfcRegOpenKeyEx(NfcRegistryLocation const &,ulong,ulong,HKEY__ * *)
0x180039c3b  mov     ebx, eax
0x180039c3d  test    eax, eax
0x180039c3f  jle     short loc_180039C4A
0x180039c41  movzx   ebx, ax
0x180039c44  or      ebx, 80070000h
0x180039c4a  test    ebx, ebx
0x180039c4c  jns     short loc_180039C6E
0x180039c4e  mov     rcx, [rbp+298h]; this
0x180039c55  mov     r9d, ebx; char *
0x180039c58  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039c5f  mov     edx, 3F9h; void *
0x180039c64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c69  jmp     loc_180039DA7
0x180039c6e  mov     [rbp+290h+var_2A8], r14
0x180039c72  mov     [rbp+290h+var_2A0], r14
0x180039c76  mov     [rbp+290h+var_90], r14d
0x180039c7d  mov     [rbp+290h+var_8C], r14b
0x180039c84  mov     rax, [rsp+390h+hKey]
0x180039c89  test    rax, rax
0x180039c8c  jnz     short loc_180039CB3
0x180039c8e  mov     rcx, [rbp+298h]; this
0x180039c95  mov     ebx, 80004003h
0x180039c9a  mov     r9d, ebx; char *
0x180039c9d  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039ca4  mov     edx, 3FCh; void *
0x180039ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039cae  jmp     loc_180039D9D
0x180039cb3  mov     [rbp+290h+var_2B0], rax
0x180039cb7  mov     [rbp+290h+var_8C], 1
0x180039cbe  xorps   xmm0, xmm0
0x180039cc1  movdqu  xmmword ptr [rsp+390h+hKey+8], xmm0
0x180039cc7  mov     [rsp+390h+var_350], r14
0x180039ccc  jmp     loc_180039D59
0x180039cd1  cmp     [rsp+390h+var_370], r14b
0x180039cd6  jz      loc_180039DEF
0x180039cdc  xorps   xmm0, xmm0
0x180039cdf  movups  [rsp+390h+var_338+8], xmm0
0x180039ce4  xorps   xmm1, xmm1
0x180039ce7  movdqu  [rsp+390h+var_328+8], xmm1
0x180039ced  lea     rax, [rbp+290h+var_298]
0x180039cf1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039cf5  inc     r8
0x180039cf8  cmp     [rax+r8*2], r14w
0x180039cfd  jnz     short loc_180039CF5
0x180039cff  lea     rdx, [rbp+290h+var_298]
0x180039d03  lea     rcx, [rsp+390h+var_338+8]
0x180039d08  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039d0d  nop
0x180039d0e  mov     rdx, [rsp+390h+var_358]
0x180039d13  cmp     rdx, [rsp+390h+var_350]
0x180039d18  jz      short loc_180039D3F
0x180039d1a  movups  xmm0, [rsp+390h+var_338+8]
0x180039d1f  movups  xmmword ptr [rdx], xmm0
0x180039d22  movups  xmm1, [rsp+390h+var_328+8]
0x180039d27  movups  xmmword ptr [rdx+10h], xmm1
0x180039d2b  movdqu  [rsp+390h+var_328+8], xmm6
0x180039d31  mov     word ptr [rsp+390h+var_338+8], r14w
0x180039d37  add     [rsp+390h+var_358], 20h ; ' '
0x180039d3d  jmp     short loc_180039D4F
0x180039d3f  lea     r8, [rsp+390h+var_338+8]
0x180039d44  lea     rcx, [rsp+390h+hKey+8]
0x180039d49  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180039d4e  nop
0x180039d4f  lea     rcx, [rsp+390h+var_338+8]
0x180039d54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d59  mov     [rsp+390h+var_370], r14b; int
0x180039d5e  lea     rdx, [rsp+390h+var_370]; bool *
0x180039d63  lea     rcx, [rbp+290h+var_2B0]; this
0x180039d67  call    ?MoveNext@RegistryKeyEnumerator@SERegistryUtils@@QEAAJPEA_N@Z; SERegistryUtils::RegistryKeyEnumerator::MoveNext(bool *)
0x180039d6c  test    eax, eax
0x180039d6e  mov     ebx, eax
0x180039d70  jns     loc_180039CD1
0x180039d76  mov     rcx, [rbp+298h]; this
0x180039d7d  mov     r9d, eax; char *
0x180039d80  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180039d87  mov     edx, 403h; void *
0x180039d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d91  nop
0x180039d92  lea     rcx, [rsp+390h+hKey+8]
0x180039d97  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180039d9c  nop
0x180039d9d  lea     rcx, [rbp+290h+var_2B0]; this
0x180039da1  call    ??1RegistryKeyEnumerator@SERegistryUtils@@QEAA@XZ; SERegistryUtils::RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x180039da6  nop
0x180039da7  mov     rcx, [rsp+390h+hKey]; hKey
0x180039dac  test    rcx, rcx
0x180039daf  jz      short loc_180039DB8
0x180039db1  call    cs:__imp_RegCloseKey
0x180039db7  nop
0x180039db8  lea     rcx, [rbp+290h+var_300]
0x180039dbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039dc1  mov     eax, ebx
0x180039dc3  mov     rcx, [rbp+290h+var_30]
0x180039dca  xor     rcx, rsp; StackCookie
0x180039dcd  call    __security_check_cookie
0x180039dd2  lea     r11, [rsp+390h+var_10]
0x180039dda  mov     rbx, [r11+20h]
0x180039dde  mov     rsi, [r11+38h]
0x180039de2  movaps  xmm6, xmmword ptr [r11-10h]
0x180039de7  mov     rsp, r11
0x180039dea  pop     r14
0x180039dec  pop     rdi
0x180039ded  pop     rbp
0x180039dee  retn
0x180039def  lea     rax, [rsp+390h+hKey+8]
0x180039df4  cmp     rdi, rax
0x180039df7  jz      short loc_180039E29
0x180039df9  mov     rcx, rdi
0x180039dfc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180039e01  mov     rax, [rsp+390h+hKey+8]
0x180039e06  mov     [rdi], rax
0x180039e09  mov     rax, [rsp+390h+var_358]
0x180039e0e  mov     [rdi+8], rax
0x180039e12  mov     rax, [rsp+390h+var_350]
0x180039e17  mov     [rdi+10h], rax
0x180039e1b  xorps   xmm0, xmm0
0x180039e1e  movdqu  xmmword ptr [rsp+390h+hKey+8], xmm0
0x180039e24  mov     [rsp+390h+var_350], r14
0x180039e29  lea     rcx, [rsp+390h+hKey+8]
0x180039e2e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180039e33  nop
0x180039e34  lea     rcx, [rbp+290h+var_2B0]; this
0x180039e38  call    ??1RegistryKeyEnumerator@SERegistryUtils@@QEAA@XZ; SERegistryUtils::RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x180039e3d  nop
0x180039e3e  mov     rcx, [rsp+390h+hKey]; hKey
0x180039e43  test    rcx, rcx
0x180039e46  jz      short loc_180039E4F
0x180039e48  call    cs:__imp_RegCloseKey
0x180039e4e  nop
0x180039e4f  lea     rcx, [rbp+290h+var_300]
0x180039e53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039e58  xor     eax, eax
0x180039e5a  jmp     loc_180039DC3
```
