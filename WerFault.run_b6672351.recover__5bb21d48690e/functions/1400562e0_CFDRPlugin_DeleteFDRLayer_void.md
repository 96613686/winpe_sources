# CFDRPlugin::DeleteFDRLayer(void)

- ea: `0x1400562e0`
- end: `0x140056666`
- name: `?DeleteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `902`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005666c`

## callees

- `0x140002748`
- `0x14000551c`
- `0x1400083f0`
- `0x14000857c`
- `0x140014ee4`
- `0x140014f14`
- `0x1400562e0`
- `0x140056844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005659e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400565b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005659e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400565b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005663e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005663e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005654b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005654b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140056392`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140056392`

## string_xrefs

- `0x140056384`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::DeleteFDRLayer(CFDRPlugin *this)
{
  BYTE *v2; // rdi
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  const struct std::nothrow_t *v5; // rdx
  signed int v6; // ebx
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  void *v12; // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  _WORD v16[2]; // [rsp+30h] [rbp-49h] BYREF
  int v17; // [rsp+34h] [rbp-45h]
  void *v18; // [rsp+38h] [rbp-41h]
  __m128i si128; // [rsp+40h] [rbp-39h]
  void *v20; // [rsp+50h] [rbp-29h]
  _WORD *v21; // [rsp+58h] [rbp-21h]
  _WORD v22[8]; // [rsp+60h] [rbp-19h] BYREF
  void *v23; // [rsp+70h] [rbp-9h]
  _WORD *v24; // [rsp+78h] [rbp-1h]
  _WORD v25[8]; // [rsp+80h] [rbp+7h] BYREF
  const struct std::nothrow_t *v26; // [rsp+90h] [rbp+17h]
  void *v27; // [rsp+A0h] [rbp+27h]
  _WORD *v28; // [rsp+A8h] [rbp+2Fh]
  _WORD v29[8]; // [rsp+B0h] [rbp+37h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp+6Fh] BYREF
  BYTE *lpData; // [rsp+F0h] [rbp+77h] BYREF

  v20 = v22;
  hKey = 0;
  v21 = v22;
  v16[0] = 0;
  v23 = v25;
  v17 = 0;
  v24 = v25;
  v2 = 0;
  v18 = (void *)-1LL;
  v27 = v29;
  v28 = v29;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v22[0] = 0;
  v25[0] = 0;
  v26 = 0;
  lpData = 0;
  v29[0] = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v4 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         0,
         0xF003Fu,
         phkResult);
  v6 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      goto LABEL_39;
    }
LABEL_42:
    v6 = 0;
    goto LABEL_43;
  }
  v6 = CRegSetting::Initialize(v16, 1, &pwzValue, *((_QWORD *)this + 1), 0);
  if ( v6 >= 0 )
  {
    v6 = CRegSetting::Load((CRegSetting *)v16, hKey, 0);
    if ( v6 >= 0 )
    {
      LOBYTE(v9) = v16[0];
      v5 = v26;
      v12 = v26;
      if ( LOBYTE(v16[0]) )
        v12 = v18;
      if ( v12 )
      {
        if ( LOBYTE(v16[0]) )
          LODWORD(v5) = (_DWORD)v18;
        v6 = CFDRPlugin::FDRRemoveAppCompatLayerFromList(v9, (_DWORD)v5, v10, v11, (__int64)&lpData);
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              WPP_928a4490cd403d1d5470036a68085293_Traceguids,
              (unsigned int)v6);
          }
          v2 = lpData;
          goto LABEL_39;
        }
        v2 = lpData;
        if ( lpData && *(_WORD *)lpData )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&lpData[2 * v13] );
          v14 = RegSetValueExW(hKey, *((LPCWSTR *)this + 1), 0, 1u, lpData, 2 * v13 + 2);
          if ( v14 )
          {
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_928a4490cd403d1d5470036a68085293_Traceguids, v14);
            }
            v6 = -2147467259;
            goto LABEL_39;
          }
        }
        else
        {
          RegDeleteValueW(hKey, *((LPCWSTR *)this + 1));
        }
      }
      goto LABEL_42;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 54;
      goto LABEL_15;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 53;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_928a4490cd403d1d5470036a68085293_Traceguids, (unsigned int)v6);
    }
  }
LABEL_39:
  if ( hKey )
    RegDeleteValueW(hKey, *((LPCWSTR *)this + 1));
LABEL_43:
  if ( v27 != v29 )
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    operator delete(v2, v5);
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400562e0  mov     [rsp-8+arg_0], rbx
0x1400562e5  mov     [rsp-8+arg_18], rdi
0x1400562ea  push    rbp
0x1400562eb  push    r14
0x1400562ed  push    r15
0x1400562ef  lea     rbp, [rsp-47h]
0x1400562f4  sub     rsp, 0C0h
0x1400562fb  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140056303  lea     rax, [rbp+57h+var_70]
0x140056307  xor     r15d, r15d
0x14005630a  mov     [rbp+57h+var_80], rax
0x14005630e  lea     rax, [rbp+57h+var_70]
0x140056312  mov     [rbp+57h+hKey], r15
0x140056316  mov     [rbp+57h+var_78], rax
0x14005631a  mov     r14, rcx
0x14005631d  lea     rax, [rbp+57h+var_50]
0x140056321  mov     [rbp+57h+var_A0], r15w
0x140056326  mov     [rbp+57h+var_60], rax
0x14005632a  lea     rcx, [rbp+57h+hKey]
0x14005632e  lea     rax, [rbp+57h+var_50]
0x140056332  mov     [rbp+57h+var_9C], r15d
0x140056336  mov     [rbp+57h+var_58], rax
0x14005633a  mov     edi, r15d
0x14005633d  lea     rax, [rbp+57h+var_20]
0x140056341  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x140056349  mov     [rbp+57h+var_30], rax
0x14005634d  lea     rax, [rbp+57h+var_20]
0x140056351  mov     [rbp+57h+var_28], rax
0x140056355  movdqa  [rbp+57h+var_90], xmm0
0x14005635a  mov     [rbp+57h+var_70], r15w
0x14005635f  mov     [rbp+57h+var_50], r15w
0x140056364  mov     [rbp+57h+var_40], r15
0x140056368  mov     [rbp+57h+lpData], r15
0x14005636c  mov     [rbp+57h+var_20], r15w
0x140056371  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140056376  mov     r9d, 0F003Fh; samDesired
0x14005637c  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140056381  xor     r8d, r8d; ulOptions
0x140056384  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14005638b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140056392  call    cs:__imp_RegOpenKeyExW
0x140056399  nop     dword ptr [rax+rax+00h]
0x14005639e  mov     ebx, eax
0x1400563a0  test    eax, eax
0x1400563a2  jz      short loc_1400563F6
0x1400563a4  cmp     eax, 2
0x1400563a7  jz      loc_1400565C0
0x1400563ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400563b4  lea     rax, WPP_GLOBAL_Control
0x1400563bb  cmp     rcx, rax
0x1400563be  jz      short loc_1400563DA
0x1400563c0  test    byte ptr [rcx+1Ch], 1
0x1400563c4  jz      short loc_1400563DA
0x1400563c6  mov     rcx, [rcx+10h]
0x1400563ca  lea     edx, [r15+34h]
0x1400563ce  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400563d5  call    WPP_SF_
0x1400563da  test    ebx, ebx
0x1400563dc  jle     short loc_1400563E7
0x1400563de  movzx   ebx, bx
0x1400563e1  or      ebx, 80070000h
0x1400563e7  test    ebx, ebx
0x1400563e9  mov     eax, 80004005h
0x1400563ee  cmovns  ebx, eax
0x1400563f1  jmp     loc_140056591
0x1400563f6  mov     r9, [r14+8]
0x1400563fa  lea     r8, pwzValue
0x140056401  mov     edx, 1
0x140056406  mov     [rsp+0D0h+phkResult], r15
0x14005640b  lea     rcx, [rbp+57h+var_A0]
0x14005640f  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140056414  mov     ebx, eax
0x140056416  test    eax, eax
0x140056418  jns     short loc_140056458
0x14005641a  mov     rcx, cs:WPP_GLOBAL_Control
0x140056421  lea     rax, WPP_GLOBAL_Control
0x140056428  cmp     rcx, rax
0x14005642b  jz      loc_140056591
0x140056431  test    byte ptr [rcx+1Ch], 1
0x140056435  jz      loc_140056591
0x14005643b  mov     edx, 35h ; '5'
0x140056440  mov     rcx, [rcx+10h]
0x140056444  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005644b  mov     r9d, ebx
0x14005644e  call    WPP_SF_d
0x140056453  jmp     loc_140056591
0x140056458  mov     rdx, [rbp+57h+hKey]; HKEY
0x14005645c  lea     rcx, [rbp+57h+var_A0]; this
0x140056460  xor     r8d, r8d; unsigned int
0x140056463  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140056468  mov     ebx, eax
0x14005646a  test    eax, eax
0x14005646c  jns     short loc_140056496
0x14005646e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056475  lea     rax, WPP_GLOBAL_Control
0x14005647c  cmp     rcx, rax
0x14005647f  jz      loc_140056591
0x140056485  test    byte ptr [rcx+1Ch], 1
0x140056489  jz      loc_140056591
0x14005648f  mov     edx, 36h ; '6'
0x140056494  jmp     short loc_140056440
0x140056496  mov     cl, byte ptr [rbp+57h+var_A0]
0x140056499  mov     rdx, [rbp+57h+var_40]
0x14005649d  test    cl, cl
0x14005649f  mov     rax, rdx
0x1400564a2  cmovnz  rax, [rbp+57h+var_98]
0x1400564a7  test    rax, rax
0x1400564aa  jz      loc_1400565C0
0x1400564b0  test    cl, cl
0x1400564b2  lea     rax, [rbp+57h+lpData]
0x1400564b6  mov     [rsp+0D0h+phkResult], rax
0x1400564bb  cmovnz  rdx, [rbp+57h+var_98]
0x1400564c0  call    ?FDRRemoveAppCompatLayerFromList@CFDRPlugin@@AEAAJPEB_WK0PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; CFDRPlugin::FDRRemoveAppCompatLayerFromList(wchar_t const *,ulong,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x1400564c5  mov     ebx, eax
0x1400564c7  test    eax, eax
0x1400564c9  jns     short loc_140056505
0x1400564cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564d2  lea     rax, WPP_GLOBAL_Control
0x1400564d9  cmp     rcx, rax
0x1400564dc  jz      short loc_1400564FC
0x1400564de  test    byte ptr [rcx+1Ch], 1
0x1400564e2  jz      short loc_1400564FC
0x1400564e4  mov     rcx, [rcx+10h]
0x1400564e8  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1400564ef  mov     edx, 37h ; '7'
0x1400564f4  mov     r9d, ebx
0x1400564f7  call    WPP_SF_d
0x1400564fc  mov     rdi, [rbp+57h+lpData]
0x140056500  jmp     loc_140056591
0x140056505  mov     rdi, [rbp+57h+lpData]
0x140056509  test    rdi, rdi
0x14005650c  jz      loc_1400565AC
0x140056512  cmp     [rdi], r15w
0x140056516  jz      loc_1400565AC
0x14005651c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140056520  inc     rax
0x140056523  cmp     [rdi+rax*2], r15w
0x140056528  jnz     short loc_140056520
0x14005652a  mov     rdx, [r14+8]; lpValueName
0x14005652e  lea     eax, ds:2[rax*2]
0x140056535  mov     rcx, [rbp+57h+hKey]; hKey
0x140056539  mov     r9d, 1; dwType
0x14005653f  mov     [rsp+0D0h+cbData], eax; cbData
0x140056543  xor     r8d, r8d; Reserved
0x140056546  mov     [rsp+0D0h+phkResult], rdi; lpData
0x14005654b  call    cs:__imp_RegSetValueExW
0x140056552  nop     dword ptr [rax+rax+00h]
0x140056557  mov     r9d, eax
0x14005655a  test    eax, eax
0x14005655c  jz      short loc_1400565C0
0x14005655e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056565  lea     rax, WPP_GLOBAL_Control
0x14005656c  cmp     rcx, rax
0x14005656f  jz      short loc_14005658C
0x140056571  test    byte ptr [rcx+1Ch], 1
0x140056575  jz      short loc_14005658C
0x140056577  mov     rcx, [rcx+10h]
0x14005657b  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140056582  mov     edx, 38h ; '8'
0x140056587  call    WPP_SF_d
0x14005658c  mov     ebx, 80004005h
0x140056591  mov     rcx, [rbp+57h+hKey]; hKey
0x140056595  test    rcx, rcx
0x140056598  jz      short loc_1400565C3
0x14005659a  mov     rdx, [r14+8]; lpValueName
0x14005659e  call    cs:__imp_RegDeleteValueW
0x1400565a5  nop     dword ptr [rax+rax+00h]
0x1400565aa  jmp     short loc_1400565C3
0x1400565ac  mov     rdx, [r14+8]; lpValueName
0x1400565b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1400565b4  call    cs:__imp_RegDeleteValueW
0x1400565bb  nop     dword ptr [rax+rax+00h]
0x1400565c0  mov     ebx, r15d
0x1400565c3  mov     rcx, [rbp+57h+var_30]; void *
0x1400565c7  lea     rax, [rbp+57h+var_20]
0x1400565cb  cmp     rcx, rax
0x1400565ce  jz      short loc_1400565DC
0x1400565d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400565d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400565dc  test    rdi, rdi
0x1400565df  jz      short loc_1400565E9
0x1400565e1  mov     rcx, rdi; void *
0x1400565e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400565e9  mov     rcx, [rbp+57h+var_60]; void *
0x1400565ed  lea     rax, [rbp+57h+var_50]
0x1400565f1  cmp     rcx, rax
0x1400565f4  jz      short loc_140056602
0x1400565f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400565fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056602  mov     rcx, [rbp+57h+var_80]; void *
0x140056606  lea     rax, [rbp+57h+var_70]
0x14005660a  cmp     rcx, rax
0x14005660d  jz      short loc_14005661B
0x14005660f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140056616  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005661b  mov     rcx, [rbp+57h+var_98]; void *
0x14005661f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140056623  jz      short loc_140056635
0x140056625  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005662c  mov     qword ptr [rbp+57h+var_90], rcx
0x140056630  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140056635  mov     rcx, [rbp+57h+hKey]; hKey
0x140056639  test    rcx, rcx
0x14005663c  jz      short loc_14005664A
0x14005663e  call    cs:__imp_RegCloseKey
0x140056645  nop     dword ptr [rax+rax+00h]
0x14005664a  lea     r11, [rsp+0D0h+var_10]
0x140056652  mov     eax, ebx
0x140056654  mov     rbx, [r11+20h]
0x140056658  mov     rdi, [r11+38h]
0x14005665c  mov     rsp, r11
0x14005665f  pop     r15
0x140056661  pop     r14
0x140056663  pop     rbp
0x140056664  retn
```
