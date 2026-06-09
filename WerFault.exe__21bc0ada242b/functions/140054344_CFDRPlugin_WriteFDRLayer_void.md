# CFDRPlugin::WriteFDRLayer(void)

- ea: `0x140054344`
- end: `0x140054636`
- name: `?WriteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `754`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140052e04`

## callees

- `0x140002728`
- `0x140005468`
- `0x140008498`
- `0x140008620`
- `0x14000c8a0`
- `0x140013ff0`
- `0x14001444c`
- `0x140014474`
- `0x140054344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054616`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054616`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005457b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005457b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140054402`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140054402`

## string_xrefs

- `0x1400543db`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::WriteFDRLayer(CFDRPlugin *this)
{
  HKEY *phkResult; // rax
  CUserModeHangReport *v3; // rcx
  __int64 v4; // rdx
  int v5; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  void *v8; // rax
  _WORD *v9; // rdx
  __int64 v10; // r8
  const BYTE *v11; // rcx
  __int64 v12; // rax
  BYTE *lpData[2]; // [rsp+50h] [rbp-49h] BYREF
  _WORD v15[8]; // [rsp+60h] [rbp-39h] BYREF
  _WORD v16[2]; // [rsp+70h] [rbp-29h] BYREF
  int v17; // [rsp+74h] [rbp-25h]
  void *v18; // [rsp+78h] [rbp-21h]
  __m128i si128; // [rsp+80h] [rbp-19h]
  void *v20; // [rsp+90h] [rbp-9h]
  _WORD *v21; // [rsp+98h] [rbp-1h]
  _WORD v22[8]; // [rsp+A0h] [rbp+7h] BYREF
  void *v23; // [rsp+B0h] [rbp+17h]
  _WORD *v24; // [rsp+B8h] [rbp+1Fh]
  _WORD v25[8]; // [rsp+C0h] [rbp+27h] BYREF
  void *v26; // [rsp+D0h] [rbp+37h]
  DWORD dwDisposition; // [rsp+108h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+110h] [rbp+77h] BYREF

  v20 = v22;
  hKey = 0;
  v21 = v22;
  dwDisposition = 0;
  v23 = v25;
  v16[0] = 0;
  v24 = v25;
  v17 = 0;
  lpData[0] = (BYTE *)v15;
  lpData[1] = (BYTE *)v15;
  v18 = (void *)-1LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v22[0] = 0;
  v25[0] = 0;
  v26 = 0;
  v15[0] = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         0,
         0,
         0,
         3u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_6;
    }
    v4 = 30;
LABEL_5:
    WPP_SF_(*((_QWORD *)v3 + 2), v4, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_6:
    v5 = -2147467259;
    goto LABEL_37;
  }
  v5 = CRegSetting::Initialize(v16, 1, &pwzValue, *((_QWORD *)this + 1), 0);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 31;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_928a4490cd403d1d5470036a68085293_Traceguids, (unsigned int)v5);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  if ( (int)CRegSetting::Load((CRegSetting *)v16, hKey, 0) < 0 )
    goto LABEL_29;
  v8 = v26;
  if ( LOBYTE(v16[0]) )
    v8 = v18;
  if ( !v8 )
  {
LABEL_29:
    v11 = (const BYTE *)L"FDR";
LABEL_30:
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v11[2 * v12] );
    if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 1), 0, 1u, v11, 2 * v12 + 2) )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_6;
      }
      v4 = 33;
      goto LABEL_5;
    }
    v5 = 0;
    goto LABEL_37;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          lpData,
                          L"FDR ") )
  {
    v9 = v26;
    if ( LOBYTE(v16[0]) )
      v9 = v18;
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
    }
    else
    {
      v10 = 0;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpData,
                            v9,
                            v10) )
    {
      v11 = lpData[0];
      goto LABEL_30;
    }
  }
  v5 = -2147024882;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 32;
    goto LABEL_11;
  }
LABEL_37:
  if ( (_WORD *)lpData[0] != v15 )
    operator delete(lpData[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v23 != v25 )
    operator delete(v23, (const struct std::nothrow_t *)&std::nothrow);
  if ( v20 != v22 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  if ( v18 != (void *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)v18;
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140054344  mov     [rsp-8+arg_0], rbx
0x140054349  mov     [rsp-8+arg_18], rsi
0x14005434e  push    rbp
0x14005434f  push    rdi
0x140054350  push    r14
0x140054352  lea     rbp, [rsp-47h]
0x140054357  sub     rsp, 0E0h
0x14005435e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140054366  lea     rax, [rbp+57h+var_50]
0x14005436a  xor     esi, esi
0x14005436c  mov     [rbp+57h+var_60], rax
0x140054370  lea     rax, [rbp+57h+var_50]
0x140054374  mov     [rbp+57h+hKey], rsi
0x140054378  mov     [rbp+57h+var_58], rax
0x14005437c  mov     rdi, rcx
0x14005437f  lea     rax, [rbp+57h+var_30]
0x140054383  mov     [rbp+57h+dwDisposition], esi
0x140054386  mov     [rbp+57h+var_40], rax
0x14005438a  lea     rcx, [rbp+57h+hKey]
0x14005438e  lea     rax, [rbp+57h+var_30]
0x140054392  mov     [rbp+57h+var_80], si
0x140054396  mov     [rbp+57h+var_38], rax
0x14005439a  or      r14, 0FFFFFFFFFFFFFFFFh
0x14005439e  lea     rax, [rbp+57h+var_90]
0x1400543a2  mov     [rbp+57h+var_7C], esi
0x1400543a5  mov     [rbp+57h+lpData], rax
0x1400543a9  lea     rax, [rbp+57h+var_90]
0x1400543ad  mov     [rbp+57h+var_98], rax
0x1400543b1  mov     [rbp+57h+var_78], r14
0x1400543b5  movdqa  [rbp+57h+var_70], xmm0
0x1400543ba  mov     [rbp+57h+var_50], si
0x1400543be  mov     [rbp+57h+var_30], si
0x1400543c2  mov     [rbp+57h+var_20], rsi
0x1400543c6  mov     [rbp+57h+var_90], si
0x1400543ca  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400543cf  lea     rcx, [rbp+57h+dwDisposition]
0x1400543d3  xor     r9d, r9d; lpClass
0x1400543d6  mov     [rsp+0F0h+lpdwDisposition], rcx; lpdwDisposition
0x1400543db  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400543e2  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1400543e7  xor     r8d, r8d; Reserved
0x1400543ea  mov     [rsp+0F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400543ef  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400543f6  mov     [rsp+0F0h+samDesired], 3; samDesired
0x1400543fe  mov     [rsp+0F0h+dwOptions], esi; dwOptions
0x140054402  call    cs:__imp_RegCreateKeyExW
0x140054408  test    eax, eax
0x14005440a  jz      short loc_140054442
0x14005440c  mov     rcx, cs:WPP_GLOBAL_Control
0x140054413  lea     rax, WPP_GLOBAL_Control
0x14005441a  cmp     rcx, rax
0x14005441d  jz      short loc_140054438
0x14005441f  test    byte ptr [rcx+1Ch], 1
0x140054423  jz      short loc_140054438
0x140054425  lea     edx, [rsi+1Eh]
0x140054428  mov     rcx, [rcx+10h]
0x14005442c  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140054433  call    WPP_SF_
0x140054438  mov     ebx, 80004005h
0x14005443d  jmp     loc_1400545B2
0x140054442  mov     r9, [rdi+8]
0x140054446  lea     r8, pwzValue
0x14005444d  mov     edx, 1
0x140054452  mov     qword ptr [rsp+0F0h+dwOptions], rsi
0x140054457  lea     rcx, [rbp+57h+var_80]
0x14005445b  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140054460  mov     ebx, eax
0x140054462  test    eax, eax
0x140054464  jns     short loc_1400544A4
0x140054466  mov     rcx, cs:WPP_GLOBAL_Control
0x14005446d  lea     rax, WPP_GLOBAL_Control
0x140054474  cmp     rcx, rax
0x140054477  jz      loc_1400545B2
0x14005447d  test    byte ptr [rcx+1Ch], 1
0x140054481  jz      loc_1400545B2
0x140054487  mov     edx, 1Fh
0x14005448c  mov     rcx, [rcx+10h]
0x140054490  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140054497  mov     r9d, ebx
0x14005449a  call    WPP_SF_d
0x14005449f  jmp     loc_1400545B2
0x1400544a4  mov     rdx, [rbp+57h+hKey]; HKEY
0x1400544a8  lea     rcx, [rbp+57h+var_80]; this
0x1400544ac  xor     r8d, r8d; unsigned int
0x1400544af  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400544b4  test    eax, eax
0x1400544b6  js      loc_140054547
0x1400544bc  cmp     byte ptr [rbp+57h+var_80], sil
0x1400544c0  mov     rax, [rbp+57h+var_20]
0x1400544c4  cmovnz  rax, [rbp+57h+var_78]
0x1400544c9  test    rax, rax
0x1400544cc  jz      short loc_140054547
0x1400544ce  mov     r8d, 4
0x1400544d4  lea     rdx, aFdr_0; "FDR "
0x1400544db  lea     rcx, [rbp+57h+lpData]
0x1400544df  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400544e4  test    al, al
0x1400544e6  jz      short loc_14005451F
0x1400544e8  cmp     byte ptr [rbp+57h+var_80], sil
0x1400544ec  mov     rdx, [rbp+57h+var_20]
0x1400544f0  cmovnz  rdx, [rbp+57h+var_78]
0x1400544f5  test    rdx, rdx
0x1400544f8  jz      short loc_140054509
0x1400544fa  mov     r8, r14
0x1400544fd  inc     r8
0x140054500  cmp     [rdx+r8*2], si
0x140054505  jnz     short loc_1400544FD
0x140054507  jmp     short loc_14005450C
0x140054509  mov     r8, rsi
0x14005450c  lea     rcx, [rbp+57h+lpData]
0x140054510  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140054515  test    al, al
0x140054517  jz      short loc_14005451F
0x140054519  mov     rcx, [rbp+57h+lpData]
0x14005451d  jmp     short loc_14005454E
0x14005451f  mov     ebx, 8007000Eh
0x140054524  mov     rcx, cs:WPP_GLOBAL_Control
0x14005452b  lea     rax, WPP_GLOBAL_Control
0x140054532  cmp     rcx, rax
0x140054535  jz      short loc_1400545B2
0x140054537  test    byte ptr [rcx+1Ch], 1
0x14005453b  jz      short loc_1400545B2
0x14005453d  mov     edx, 20h ; ' '
0x140054542  jmp     loc_14005448C
0x140054547  lea     rcx, aFdr; "FDR"
0x14005454e  mov     rax, r14
0x140054551  inc     rax
0x140054554  cmp     [rcx+rax*2], si
0x140054558  jnz     short loc_140054551
0x14005455a  mov     rdx, [rdi+8]; lpValueName
0x14005455e  lea     eax, ds:2[rax*2]
0x140054565  mov     [rsp+0F0h+samDesired], eax; cbData
0x140054569  mov     r9d, 1; dwType
0x14005456f  mov     qword ptr [rsp+0F0h+dwOptions], rcx; lpData
0x140054574  xor     r8d, r8d; Reserved
0x140054577  mov     rcx, [rbp+57h+hKey]; hKey
0x14005457b  call    cs:__imp_RegSetValueExW
0x140054581  test    eax, eax
0x140054583  jz      short loc_1400545B0
0x140054585  mov     rcx, cs:WPP_GLOBAL_Control
0x14005458c  lea     rax, WPP_GLOBAL_Control
0x140054593  cmp     rcx, rax
0x140054596  jz      loc_140054438
0x14005459c  test    byte ptr [rcx+1Ch], 1
0x1400545a0  jz      loc_140054438
0x1400545a6  mov     edx, 21h ; '!'
0x1400545ab  jmp     loc_140054428
0x1400545b0  mov     ebx, esi
0x1400545b2  mov     rcx, [rbp+57h+lpData]; void *
0x1400545b6  lea     rax, [rbp+57h+var_90]
0x1400545ba  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400545c1  cmp     rcx, rax
0x1400545c4  jz      short loc_1400545CE
0x1400545c6  mov     rdx, rdi; struct std::nothrow_t *
0x1400545c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400545ce  mov     rcx, [rbp+57h+var_40]; void *
0x1400545d2  lea     rax, [rbp+57h+var_30]
0x1400545d6  cmp     rcx, rax
0x1400545d9  jz      short loc_1400545E3
0x1400545db  mov     rdx, rdi; struct std::nothrow_t *
0x1400545de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400545e3  mov     rcx, [rbp+57h+var_60]; void *
0x1400545e7  lea     rax, [rbp+57h+var_50]
0x1400545eb  cmp     rcx, rax
0x1400545ee  jz      short loc_1400545F8
0x1400545f0  mov     rdx, rdi; struct std::nothrow_t *
0x1400545f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400545f8  mov     rcx, [rbp+57h+var_78]; void *
0x1400545fc  cmp     rcx, r14
0x1400545ff  jz      short loc_14005460D
0x140054601  mov     rdx, rdi; struct std::nothrow_t *
0x140054604  mov     qword ptr [rbp+57h+var_70], rcx
0x140054608  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005460d  mov     rcx, [rbp+57h+hKey]; hKey
0x140054611  test    rcx, rcx
0x140054614  jz      short loc_14005461C
0x140054616  call    cs:__imp_RegCloseKey
0x14005461c  lea     r11, [rsp+0F0h+var_10]
0x140054624  mov     eax, ebx
0x140054626  mov     rbx, [r11+20h]
0x14005462a  mov     rsi, [r11+38h]
0x14005462e  mov     rsp, r11
0x140054631  pop     r14
0x140054633  pop     rdi
0x140054634  pop     rbp
0x140054635  retn
```
