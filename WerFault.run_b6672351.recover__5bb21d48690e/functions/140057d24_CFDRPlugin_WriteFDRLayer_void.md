# CFDRPlugin::WriteFDRLayer(void)

- ea: `0x140057d24`
- end: `0x14005802d`
- name: `?WriteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `777`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140056730`

## callees

- `0x140002748`
- `0x14000551c`
- `0x1400083f0`
- `0x14000857c`
- `0x14000ca20`
- `0x140014a88`
- `0x140014ee4`
- `0x140014f14`
- `0x140057d24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058006`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140057f65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140057f65`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140057de2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140057de2`

## string_xrefs

- `0x140057dbb`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

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
  if ( CRegSetting::Load((CRegSetting *)v16, hKey, 0) < 0 )
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
0x140057d24  mov     [rsp-8+arg_0], rbx
0x140057d29  mov     [rsp-8+arg_18], rsi
0x140057d2e  push    rbp
0x140057d2f  push    rdi
0x140057d30  push    r14
0x140057d32  lea     rbp, [rsp-47h]
0x140057d37  sub     rsp, 0E0h
0x140057d3e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140057d46  lea     rax, [rbp+57h+var_50]
0x140057d4a  xor     esi, esi
0x140057d4c  mov     [rbp+57h+var_60], rax
0x140057d50  lea     rax, [rbp+57h+var_50]
0x140057d54  mov     [rbp+57h+hKey], rsi
0x140057d58  mov     [rbp+57h+var_58], rax
0x140057d5c  mov     rdi, rcx
0x140057d5f  lea     rax, [rbp+57h+var_30]
0x140057d63  mov     [rbp+57h+dwDisposition], esi
0x140057d66  mov     [rbp+57h+var_40], rax
0x140057d6a  lea     rcx, [rbp+57h+hKey]
0x140057d6e  lea     rax, [rbp+57h+var_30]
0x140057d72  mov     [rbp+57h+var_80], si
0x140057d76  mov     [rbp+57h+var_38], rax
0x140057d7a  or      r14, 0FFFFFFFFFFFFFFFFh
0x140057d7e  lea     rax, [rbp+57h+var_90]
0x140057d82  mov     [rbp+57h+var_7C], esi
0x140057d85  mov     [rbp+57h+lpData], rax
0x140057d89  lea     rax, [rbp+57h+var_90]
0x140057d8d  mov     [rbp+57h+var_98], rax
0x140057d91  mov     [rbp+57h+var_78], r14
0x140057d95  movdqa  [rbp+57h+var_70], xmm0
0x140057d9a  mov     [rbp+57h+var_50], si
0x140057d9e  mov     [rbp+57h+var_30], si
0x140057da2  mov     [rbp+57h+var_20], rsi
0x140057da6  mov     [rbp+57h+var_90], si
0x140057daa  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140057daf  lea     rcx, [rbp+57h+dwDisposition]
0x140057db3  xor     r9d, r9d; lpClass
0x140057db6  mov     [rsp+0F0h+lpdwDisposition], rcx; lpdwDisposition
0x140057dbb  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x140057dc2  mov     [rsp+0F0h+phkResult], rax; phkResult
0x140057dc7  xor     r8d, r8d; Reserved
0x140057dca  mov     [rsp+0F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140057dcf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140057dd6  mov     [rsp+0F0h+samDesired], 3; samDesired
0x140057dde  mov     [rsp+0F0h+dwOptions], esi; dwOptions
0x140057de2  call    cs:__imp_RegCreateKeyExW
0x140057de9  nop     dword ptr [rax+rax+00h]
0x140057dee  test    eax, eax
0x140057df0  jz      short loc_140057E28
0x140057df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140057df9  lea     rax, WPP_GLOBAL_Control
0x140057e00  cmp     rcx, rax
0x140057e03  jz      short loc_140057E1E
0x140057e05  test    byte ptr [rcx+1Ch], 1
0x140057e09  jz      short loc_140057E1E
0x140057e0b  lea     edx, [rsi+1Eh]
0x140057e0e  mov     rcx, [rcx+10h]
0x140057e12  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057e19  call    WPP_SF_
0x140057e1e  mov     ebx, 80004005h
0x140057e23  jmp     loc_140057FA2
0x140057e28  mov     r9, [rdi+8]
0x140057e2c  lea     r8, pwzValue
0x140057e33  mov     edx, 1
0x140057e38  mov     qword ptr [rsp+0F0h+dwOptions], rsi
0x140057e3d  lea     rcx, [rbp+57h+var_80]
0x140057e41  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140057e46  mov     ebx, eax
0x140057e48  test    eax, eax
0x140057e4a  jns     short loc_140057E8A
0x140057e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e53  lea     rax, WPP_GLOBAL_Control
0x140057e5a  cmp     rcx, rax
0x140057e5d  jz      loc_140057FA2
0x140057e63  test    byte ptr [rcx+1Ch], 1
0x140057e67  jz      loc_140057FA2
0x140057e6d  mov     edx, 1Fh
0x140057e72  mov     rcx, [rcx+10h]
0x140057e76  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140057e7d  mov     r9d, ebx
0x140057e80  call    WPP_SF_d
0x140057e85  jmp     loc_140057FA2
0x140057e8a  mov     rdx, [rbp+57h+hKey]; HKEY
0x140057e8e  lea     rcx, [rbp+57h+var_80]; this
0x140057e92  xor     r8d, r8d; unsigned int
0x140057e95  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140057e9a  test    eax, eax
0x140057e9c  js      loc_140057F31
0x140057ea2  cmp     byte ptr [rbp+57h+var_80], sil
0x140057ea6  mov     rax, [rbp+57h+var_20]
0x140057eaa  cmovnz  rax, [rbp+57h+var_78]
0x140057eaf  test    rax, rax
0x140057eb2  jz      short loc_140057F31
0x140057eb4  mov     r8d, 4
0x140057eba  lea     rdx, aFdr_0; "FDR "
0x140057ec1  lea     rcx, [rbp+57h+lpData]
0x140057ec5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140057eca  test    al, al
0x140057ecc  jz      short loc_140057F05
0x140057ece  cmp     byte ptr [rbp+57h+var_80], sil
0x140057ed2  mov     rdx, [rbp+57h+var_20]
0x140057ed6  cmovnz  rdx, [rbp+57h+var_78]
0x140057edb  test    rdx, rdx
0x140057ede  jz      short loc_140057EEF
0x140057ee0  mov     r8, r14
0x140057ee3  inc     r8
0x140057ee6  cmp     [rdx+r8*2], si
0x140057eeb  jnz     short loc_140057EE3
0x140057eed  jmp     short loc_140057EF2
0x140057eef  mov     r8, rsi
0x140057ef2  lea     rcx, [rbp+57h+lpData]
0x140057ef6  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140057efb  test    al, al
0x140057efd  jz      short loc_140057F05
0x140057eff  mov     rcx, [rbp+57h+lpData]
0x140057f03  jmp     short loc_140057F38
0x140057f05  mov     ebx, 8007000Eh
0x140057f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f11  lea     rax, WPP_GLOBAL_Control
0x140057f18  cmp     rcx, rax
0x140057f1b  jz      loc_140057FA2
0x140057f21  test    byte ptr [rcx+1Ch], 1
0x140057f25  jz      short loc_140057FA2
0x140057f27  mov     edx, 20h ; ' '
0x140057f2c  jmp     loc_140057E72
0x140057f31  lea     rcx, aFdr; "FDR"
0x140057f38  mov     rax, r14
0x140057f3b  inc     rax
0x140057f3e  cmp     [rcx+rax*2], si
0x140057f42  jnz     short loc_140057F3B
0x140057f44  mov     rdx, [rdi+8]; lpValueName
0x140057f48  lea     eax, ds:2[rax*2]
0x140057f4f  mov     [rsp+0F0h+samDesired], eax; cbData
0x140057f53  mov     r9d, 1; dwType
0x140057f59  mov     qword ptr [rsp+0F0h+dwOptions], rcx; lpData
0x140057f5e  xor     r8d, r8d; Reserved
0x140057f61  mov     rcx, [rbp+57h+hKey]; hKey
0x140057f65  call    cs:__imp_RegSetValueExW
0x140057f6c  nop     dword ptr [rax+rax+00h]
0x140057f71  test    eax, eax
0x140057f73  jz      short loc_140057FA0
0x140057f75  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f7c  lea     rax, WPP_GLOBAL_Control
0x140057f83  cmp     rcx, rax
0x140057f86  jz      loc_140057E1E
0x140057f8c  test    byte ptr [rcx+1Ch], 1
0x140057f90  jz      loc_140057E1E
0x140057f96  mov     edx, 21h ; '!'
0x140057f9b  jmp     loc_140057E0E
0x140057fa0  mov     ebx, esi
0x140057fa2  mov     rcx, [rbp+57h+lpData]; void *
0x140057fa6  lea     rax, [rbp+57h+var_90]
0x140057faa  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140057fb1  cmp     rcx, rax
0x140057fb4  jz      short loc_140057FBE
0x140057fb6  mov     rdx, rdi; struct std::nothrow_t *
0x140057fb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057fbe  mov     rcx, [rbp+57h+var_40]; void *
0x140057fc2  lea     rax, [rbp+57h+var_30]
0x140057fc6  cmp     rcx, rax
0x140057fc9  jz      short loc_140057FD3
0x140057fcb  mov     rdx, rdi; struct std::nothrow_t *
0x140057fce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057fd3  mov     rcx, [rbp+57h+var_60]; void *
0x140057fd7  lea     rax, [rbp+57h+var_50]
0x140057fdb  cmp     rcx, rax
0x140057fde  jz      short loc_140057FE8
0x140057fe0  mov     rdx, rdi; struct std::nothrow_t *
0x140057fe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057fe8  mov     rcx, [rbp+57h+var_78]; void *
0x140057fec  cmp     rcx, r14
0x140057fef  jz      short loc_140057FFD
0x140057ff1  mov     rdx, rdi; struct std::nothrow_t *
0x140057ff4  mov     qword ptr [rbp+57h+var_70], rcx
0x140057ff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057ffd  mov     rcx, [rbp+57h+hKey]; hKey
0x140058001  test    rcx, rcx
0x140058004  jz      short loc_140058012
0x140058006  call    cs:__imp_RegCloseKey
0x14005800d  nop     dword ptr [rax+rax+00h]
0x140058012  lea     r11, [rsp+0F0h+var_10]
0x14005801a  mov     eax, ebx
0x14005801c  mov     rbx, [r11+20h]
0x140058020  mov     rsi, [r11+38h]
0x140058024  mov     rsp, r11
0x140058027  pop     r14
0x140058029  pop     rdi
0x14005802a  pop     rbp
0x14005802b  retn
```
