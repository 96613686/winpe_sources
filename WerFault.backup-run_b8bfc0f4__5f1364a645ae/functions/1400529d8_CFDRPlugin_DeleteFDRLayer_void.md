# CFDRPlugin::DeleteFDRLayer(void)

- ea: `0x1400529d8`
- end: `0x140052d3f`
- name: `?DeleteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140052d48`

## callees

- `0x140002728`
- `0x140005468`
- `0x140008498`
- `0x140008620`
- `0x14001444c`
- `0x140014474`
- `0x1400529d8`
- `0x140052f14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140052c8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140052c9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140052c8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140052c9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140052d1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140052d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140052c3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140052c3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140052a8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140052a8a`

## string_xrefs

- `0x140052a7c`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

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
0x1400529d8  mov     [rsp-8+arg_0], rbx
0x1400529dd  mov     [rsp-8+arg_18], rdi
0x1400529e2  push    rbp
0x1400529e3  push    r14
0x1400529e5  push    r15
0x1400529e7  lea     rbp, [rsp-47h]
0x1400529ec  sub     rsp, 0C0h
0x1400529f3  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400529fb  lea     rax, [rbp+57h+var_70]
0x1400529ff  xor     r15d, r15d
0x140052a02  mov     [rbp+57h+var_80], rax
0x140052a06  lea     rax, [rbp+57h+var_70]
0x140052a0a  mov     [rbp+57h+hKey], r15
0x140052a0e  mov     [rbp+57h+var_78], rax
0x140052a12  mov     r14, rcx
0x140052a15  lea     rax, [rbp+57h+var_50]
0x140052a19  mov     [rbp+57h+var_A0], r15w
0x140052a1e  mov     [rbp+57h+var_60], rax
0x140052a22  lea     rcx, [rbp+57h+hKey]
0x140052a26  lea     rax, [rbp+57h+var_50]
0x140052a2a  mov     [rbp+57h+var_9C], r15d
0x140052a2e  mov     [rbp+57h+var_58], rax
0x140052a32  mov     edi, r15d
0x140052a35  lea     rax, [rbp+57h+var_20]
0x140052a39  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x140052a41  mov     [rbp+57h+var_30], rax
0x140052a45  lea     rax, [rbp+57h+var_20]
0x140052a49  mov     [rbp+57h+var_28], rax
0x140052a4d  movdqa  [rbp+57h+var_90], xmm0
0x140052a52  mov     [rbp+57h+var_70], r15w
0x140052a57  mov     [rbp+57h+var_50], r15w
0x140052a5c  mov     [rbp+57h+var_40], r15
0x140052a60  mov     [rbp+57h+lpData], r15
0x140052a64  mov     [rbp+57h+var_20], r15w
0x140052a69  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140052a6e  mov     r9d, 0F003Fh; samDesired
0x140052a74  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140052a79  xor     r8d, r8d; ulOptions
0x140052a7c  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x140052a83  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140052a8a  call    cs:__imp_RegOpenKeyExW
0x140052a90  mov     ebx, eax
0x140052a92  test    eax, eax
0x140052a94  jz      short loc_140052AE8
0x140052a96  cmp     eax, 2
0x140052a99  jz      loc_140052CA0
0x140052a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140052aa6  lea     rax, WPP_GLOBAL_Control
0x140052aad  cmp     rcx, rax
0x140052ab0  jz      short loc_140052ACC
0x140052ab2  test    byte ptr [rcx+1Ch], 1
0x140052ab6  jz      short loc_140052ACC
0x140052ab8  mov     rcx, [rcx+10h]
0x140052abc  lea     edx, [r15+34h]
0x140052ac0  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140052ac7  call    WPP_SF_
0x140052acc  test    ebx, ebx
0x140052ace  jle     short loc_140052AD9
0x140052ad0  movzx   ebx, bx
0x140052ad3  or      ebx, 80070000h
0x140052ad9  test    ebx, ebx
0x140052adb  mov     eax, 80004005h
0x140052ae0  cmovns  ebx, eax
0x140052ae3  jmp     loc_140052C7D
0x140052ae8  mov     r9, [r14+8]
0x140052aec  lea     r8, pwzValue
0x140052af3  mov     edx, 1
0x140052af8  mov     [rsp+0D0h+phkResult], r15
0x140052afd  lea     rcx, [rbp+57h+var_A0]
0x140052b01  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140052b06  mov     ebx, eax
0x140052b08  test    eax, eax
0x140052b0a  jns     short loc_140052B4A
0x140052b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052b13  lea     rax, WPP_GLOBAL_Control
0x140052b1a  cmp     rcx, rax
0x140052b1d  jz      loc_140052C7D
0x140052b23  test    byte ptr [rcx+1Ch], 1
0x140052b27  jz      loc_140052C7D
0x140052b2d  mov     edx, 35h ; '5'
0x140052b32  mov     rcx, [rcx+10h]
0x140052b36  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140052b3d  mov     r9d, ebx
0x140052b40  call    WPP_SF_d
0x140052b45  jmp     loc_140052C7D
0x140052b4a  mov     rdx, [rbp+57h+hKey]; HKEY
0x140052b4e  lea     rcx, [rbp+57h+var_A0]; this
0x140052b52  xor     r8d, r8d; unsigned int
0x140052b55  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140052b5a  mov     ebx, eax
0x140052b5c  test    eax, eax
0x140052b5e  jns     short loc_140052B88
0x140052b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140052b67  lea     rax, WPP_GLOBAL_Control
0x140052b6e  cmp     rcx, rax
0x140052b71  jz      loc_140052C7D
0x140052b77  test    byte ptr [rcx+1Ch], 1
0x140052b7b  jz      loc_140052C7D
0x140052b81  mov     edx, 36h ; '6'
0x140052b86  jmp     short loc_140052B32
0x140052b88  mov     cl, byte ptr [rbp+57h+var_A0]
0x140052b8b  mov     rdx, [rbp+57h+var_40]
0x140052b8f  test    cl, cl
0x140052b91  mov     rax, rdx
0x140052b94  cmovnz  rax, [rbp+57h+var_98]
0x140052b99  test    rax, rax
0x140052b9c  jz      loc_140052CA0
0x140052ba2  test    cl, cl
0x140052ba4  lea     rax, [rbp+57h+lpData]
0x140052ba8  mov     [rsp+0D0h+phkResult], rax
0x140052bad  cmovnz  rdx, [rbp+57h+var_98]
0x140052bb2  call    ?FDRRemoveAppCompatLayerFromList@CFDRPlugin@@AEAAJPEB_WK0PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; CFDRPlugin::FDRRemoveAppCompatLayerFromList(wchar_t const *,ulong,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x140052bb7  mov     ebx, eax
0x140052bb9  test    eax, eax
0x140052bbb  jns     short loc_140052BF7
0x140052bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140052bc4  lea     rax, WPP_GLOBAL_Control
0x140052bcb  cmp     rcx, rax
0x140052bce  jz      short loc_140052BEE
0x140052bd0  test    byte ptr [rcx+1Ch], 1
0x140052bd4  jz      short loc_140052BEE
0x140052bd6  mov     rcx, [rcx+10h]
0x140052bda  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140052be1  mov     edx, 37h ; '7'
0x140052be6  mov     r9d, ebx
0x140052be9  call    WPP_SF_d
0x140052bee  mov     rdi, [rbp+57h+lpData]
0x140052bf2  jmp     loc_140052C7D
0x140052bf7  mov     rdi, [rbp+57h+lpData]
0x140052bfb  test    rdi, rdi
0x140052bfe  jz      loc_140052C92
0x140052c04  cmp     [rdi], r15w
0x140052c08  jz      loc_140052C92
0x140052c0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140052c12  inc     rax
0x140052c15  cmp     [rdi+rax*2], r15w
0x140052c1a  jnz     short loc_140052C12
0x140052c1c  mov     rdx, [r14+8]; lpValueName
0x140052c20  lea     eax, ds:2[rax*2]
0x140052c27  mov     rcx, [rbp+57h+hKey]; hKey
0x140052c2b  mov     r9d, 1; dwType
0x140052c31  mov     [rsp+0D0h+cbData], eax; cbData
0x140052c35  xor     r8d, r8d; Reserved
0x140052c38  mov     [rsp+0D0h+phkResult], rdi; lpData
0x140052c3d  call    cs:__imp_RegSetValueExW
0x140052c43  mov     r9d, eax
0x140052c46  test    eax, eax
0x140052c48  jz      short loc_140052CA0
0x140052c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052c51  lea     rax, WPP_GLOBAL_Control
0x140052c58  cmp     rcx, rax
0x140052c5b  jz      short loc_140052C78
0x140052c5d  test    byte ptr [rcx+1Ch], 1
0x140052c61  jz      short loc_140052C78
0x140052c63  mov     rcx, [rcx+10h]
0x140052c67  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140052c6e  mov     edx, 38h ; '8'
0x140052c73  call    WPP_SF_d
0x140052c78  mov     ebx, 80004005h
0x140052c7d  mov     rcx, [rbp+57h+hKey]; hKey
0x140052c81  test    rcx, rcx
0x140052c84  jz      short loc_140052CA3
0x140052c86  mov     rdx, [r14+8]; lpValueName
0x140052c8a  call    cs:__imp_RegDeleteValueW
0x140052c90  jmp     short loc_140052CA3
0x140052c92  mov     rdx, [r14+8]; lpValueName
0x140052c96  mov     rcx, [rbp+57h+hKey]; hKey
0x140052c9a  call    cs:__imp_RegDeleteValueW
0x140052ca0  mov     ebx, r15d
0x140052ca3  mov     rcx, [rbp+57h+var_30]; void *
0x140052ca7  lea     rax, [rbp+57h+var_20]
0x140052cab  cmp     rcx, rax
0x140052cae  jz      short loc_140052CBC
0x140052cb0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052cb7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140052cbc  test    rdi, rdi
0x140052cbf  jz      short loc_140052CC9
0x140052cc1  mov     rcx, rdi; void *
0x140052cc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140052cc9  mov     rcx, [rbp+57h+var_60]; void *
0x140052ccd  lea     rax, [rbp+57h+var_50]
0x140052cd1  cmp     rcx, rax
0x140052cd4  jz      short loc_140052CE2
0x140052cd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052cdd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140052ce2  mov     rcx, [rbp+57h+var_80]; void *
0x140052ce6  lea     rax, [rbp+57h+var_70]
0x140052cea  cmp     rcx, rax
0x140052ced  jz      short loc_140052CFB
0x140052cef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052cf6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140052cfb  mov     rcx, [rbp+57h+var_98]; void *
0x140052cff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140052d03  jz      short loc_140052D15
0x140052d05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140052d0c  mov     qword ptr [rbp+57h+var_90], rcx
0x140052d10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140052d15  mov     rcx, [rbp+57h+hKey]; hKey
0x140052d19  test    rcx, rcx
0x140052d1c  jz      short loc_140052D24
0x140052d1e  call    cs:__imp_RegCloseKey
0x140052d24  lea     r11, [rsp+0D0h+var_10]
0x140052d2c  mov     eax, ebx
0x140052d2e  mov     rbx, [r11+20h]
0x140052d32  mov     rdi, [r11+38h]
0x140052d36  mov     rsp, r11
0x140052d39  pop     r15
0x140052d3b  pop     r14
0x140052d3d  pop     rbp
0x140052d3e  retn
```
