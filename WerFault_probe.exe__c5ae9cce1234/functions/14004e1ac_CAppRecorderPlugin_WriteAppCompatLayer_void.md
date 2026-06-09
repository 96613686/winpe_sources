# CAppRecorderPlugin::WriteAppCompatLayer(void)

- ea: `0x14004e1ac`
- end: `0x14004e45a`
- name: `?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `686`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004cbac`

## callees

- `0x140002470`
- `0x140002728`
- `0x140005430`
- `0x140005468`
- `0x14000c8a0`
- `0x140014474`
- `0x14004e1ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004e2fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004e2fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e42e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e42e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e380`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e380`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e2a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e2a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e3c3`

## string_xrefs

- `0x14004e278`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::WriteAppCompatLayer(CAppRecorderPlugin *this)
{
  unsigned int v2; // ebx
  CUserModeHangReport *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  HKEY *phkResult; // rax
  HKEY v7; // rcx
  const WCHAR *v8; // r8
  signed int v9; // eax
  signed int LastError; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  char *v16; // [rsp+68h] [rbp-98h]
  _WORD v17[8]; // [rsp+70h] [rbp-90h] BYREF
  _WORD pvData[264]; // [rsp+80h] [rbp-80h] BYREF

  hkey = 0;
  lpData = (BYTE *)v17;
  dwDisposition = 0;
  v16 = (char *)v17;
  pcbData = 0;
  v17[0] = 0;
  pvData[0] = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          &lpData,
                          L"AppRecorder",
                          11) )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    if ( RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
           0,
           0,
           0,
           3u,
           0,
           phkResult,
           &dwDisposition)
      || (v7 = hkey) == 0 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v4 = 47;
    }
    else
    {
      if ( dwDisposition == 2 )
      {
        v8 = (const WCHAR *)*((_QWORD *)this + 1);
        pcbData = 520;
        if ( !RegGetValueW(hkey, 0, v8, 2u, 0, pvData, &pcbData) )
        {
          v2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 &lpData,
                 L"%s %s",
                 pvData,
                 L"AppRecorder");
          if ( (v2 & 0x80000000) != 0 )
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_28;
            }
            v4 = 48;
            goto LABEL_26;
          }
        }
        v7 = hkey;
      }
      if ( !RegSetValueExW(v7, *((LPCWSTR *)this + 1), 0, 1u, lpData, 2 * ((v16 - (char *)lpData) >> 1)) )
      {
        v2 = 0;
        goto LABEL_28;
      }
      v9 = GetLastError();
      v2 = v9;
      if ( v9 > 0 )
        v2 = (unsigned __int16)v9 | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v4 = 49;
    }
LABEL_26:
    v5 = v2;
    goto LABEL_27;
  }
  v2 = -2147024882;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 46;
    v5 = 2147942414LL;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v5);
  }
LABEL_28:
  if ( lpData != (BYTE *)v17 )
    operator delete(lpData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v2;
}

```

## disassembly

```asm
0x14004e1ac  mov     [rsp-8+arg_8], rbx
0x14004e1b1  mov     [rsp-8+arg_10], rdi
0x14004e1b6  push    rbp
0x14004e1b7  lea     rbp, [rsp-1A0h]
0x14004e1bf  sub     rsp, 2A0h
0x14004e1c6  mov     rax, cs:__security_cookie
0x14004e1cd  xor     rax, rsp
0x14004e1d0  mov     [rbp+1A0h+var_10], rax
0x14004e1d7  lea     rax, [rsp+2A0h+var_230]
0x14004e1dc  mov     [rsp+2A0h+hkey], 0
0x14004e1e5  mov     [rsp+2A0h+lpData], rax
0x14004e1ea  lea     rdx, aApprecorder; "AppRecorder"
0x14004e1f1  lea     rax, [rsp+2A0h+var_230]
0x14004e1f6  mov     [rsp+2A0h+dwDisposition], 0
0x14004e1fe  mov     [rsp+2A0h+var_238], rax
0x14004e203  mov     rdi, rcx
0x14004e206  xor     eax, eax
0x14004e208  mov     [rsp+2A0h+pcbData], 0
0x14004e210  lea     rcx, [rsp+2A0h+lpData]
0x14004e215  mov     [rsp+2A0h+var_230], ax
0x14004e21a  mov     [rbp+1A0h+pvData], ax
0x14004e21e  lea     r8d, [rax+0Bh]
0x14004e222  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004e227  test    al, al
0x14004e229  jnz     short loc_14004E261
0x14004e22b  mov     ebx, 8007000Eh
0x14004e230  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e237  lea     rax, WPP_GLOBAL_Control
0x14004e23e  cmp     rcx, rax
0x14004e241  jz      loc_14004E409
0x14004e247  test    byte ptr [rcx+1Ch], 1
0x14004e24b  jz      loc_14004E409
0x14004e251  mov     edx, 2Eh ; '.'
0x14004e256  mov     r9d, 8007000Eh
0x14004e25c  jmp     loc_14004E3F9
0x14004e261  lea     rcx, [rsp+2A0h+hkey]
0x14004e266  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004e26b  lea     rcx, [rsp+2A0h+dwDisposition]
0x14004e270  xor     r9d, r9d; lpClass
0x14004e273  mov     [rsp+2A0h+lpdwDisposition], rcx; lpdwDisposition
0x14004e278  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004e27f  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14004e284  xor     r8d, r8d; Reserved
0x14004e287  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004e290  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004e297  mov     [rsp+2A0h+samDesired], 3; samDesired
0x14004e29f  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x14004e2a7  call    cs:__imp_RegCreateKeyExW
0x14004e2ad  test    eax, eax
0x14004e2af  jnz     loc_14004E3C3
0x14004e2b5  mov     rcx, [rsp+2A0h+hkey]; hkey
0x14004e2ba  test    rcx, rcx
0x14004e2bd  jz      loc_14004E3C3
0x14004e2c3  lea     r9d, [rax+2]; dwFlags
0x14004e2c7  cmp     [rsp+2A0h+dwDisposition], r9d
0x14004e2cc  jnz     loc_14004E358
0x14004e2d2  mov     r8, [rdi+8]; lpValue
0x14004e2d6  lea     rax, [rsp+2A0h+pcbData]
0x14004e2db  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x14004e2e0  xor     edx, edx; lpSubKey
0x14004e2e2  lea     rax, [rbp+1A0h+pvData]
0x14004e2e6  mov     [rsp+2A0h+pcbData], 208h
0x14004e2ee  mov     qword ptr [rsp+2A0h+samDesired], rax; pvData
0x14004e2f3  mov     qword ptr [rsp+2A0h+dwOptions], 0; pdwType
0x14004e2fc  call    cs:__imp_RegGetValueW
0x14004e302  test    eax, eax
0x14004e304  jnz     short loc_14004E353
0x14004e306  lea     r9, aApprecorder; "AppRecorder"
0x14004e30d  lea     r8, [rbp+1A0h+pvData]
0x14004e311  lea     rdx, aSS_5; "%s %s"
0x14004e318  lea     rcx, [rsp+2A0h+lpData]
0x14004e31d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004e322  mov     ebx, eax
0x14004e324  test    eax, eax
0x14004e326  jns     short loc_14004E353
0x14004e328  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e32f  lea     rax, WPP_GLOBAL_Control
0x14004e336  cmp     rcx, rax
0x14004e339  jz      loc_14004E409
0x14004e33f  test    byte ptr [rcx+1Ch], 1
0x14004e343  jz      loc_14004E409
0x14004e349  mov     edx, 30h ; '0'
0x14004e34e  jmp     loc_14004E3F6
0x14004e353  mov     rcx, [rsp+2A0h+hkey]; hKey
0x14004e358  mov     r8, [rsp+2A0h+lpData]
0x14004e35d  mov     r9d, 1; dwType
0x14004e363  mov     rax, [rsp+2A0h+var_238]
0x14004e368  mov     rdx, [rdi+8]; lpValueName
0x14004e36c  sub     rax, r8
0x14004e36f  sar     rax, 1
0x14004e372  add     eax, eax
0x14004e374  mov     [rsp+2A0h+samDesired], eax; cbData
0x14004e378  mov     qword ptr [rsp+2A0h+dwOptions], r8; lpData
0x14004e37d  xor     r8d, r8d; Reserved
0x14004e380  call    cs:__imp_RegSetValueExW
0x14004e386  test    eax, eax
0x14004e388  jz      short loc_14004E3BF
0x14004e38a  call    cs:__imp_GetLastError
0x14004e390  mov     ebx, eax
0x14004e392  test    eax, eax
0x14004e394  jle     short loc_14004E39F
0x14004e396  movzx   ebx, ax
0x14004e399  or      ebx, 80070000h
0x14004e39f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e3a6  lea     rax, WPP_GLOBAL_Control
0x14004e3ad  cmp     rcx, rax
0x14004e3b0  jz      short loc_14004E409
0x14004e3b2  test    byte ptr [rcx+1Ch], 1
0x14004e3b6  jz      short loc_14004E409
0x14004e3b8  mov     edx, 31h ; '1'
0x14004e3bd  jmp     short loc_14004E3F6
0x14004e3bf  xor     ebx, ebx
0x14004e3c1  jmp     short loc_14004E409
0x14004e3c3  call    cs:__imp_GetLastError
0x14004e3c9  mov     ebx, eax
0x14004e3cb  test    eax, eax
0x14004e3cd  jle     short loc_14004E3D8
0x14004e3cf  movzx   ebx, ax
0x14004e3d2  or      ebx, 80070000h
0x14004e3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e3df  lea     rax, WPP_GLOBAL_Control
0x14004e3e6  cmp     rcx, rax
0x14004e3e9  jz      short loc_14004E409
0x14004e3eb  test    byte ptr [rcx+1Ch], 1
0x14004e3ef  jz      short loc_14004E409
0x14004e3f1  mov     edx, 2Fh ; '/'
0x14004e3f6  mov     r9d, ebx
0x14004e3f9  mov     rcx, [rcx+10h]
0x14004e3fd  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004e404  call    WPP_SF_d
0x14004e409  mov     rcx, [rsp+2A0h+lpData]; void *
0x14004e40e  lea     rax, [rsp+2A0h+var_230]
0x14004e413  cmp     rcx, rax
0x14004e416  jz      short loc_14004E424
0x14004e418  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004e41f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004e424  mov     rcx, [rsp+2A0h+hkey]; hKey
0x14004e429  test    rcx, rcx
0x14004e42c  jz      short loc_14004E434
0x14004e42e  call    cs:__imp_RegCloseKey
0x14004e434  mov     eax, ebx
0x14004e436  mov     rcx, [rbp+1A0h+var_10]
0x14004e43d  xor     rcx, rsp; StackCookie
0x14004e440  call    __security_check_cookie
0x14004e445  lea     r11, [rsp+2A0h+var_s0]
0x14004e44d  mov     rbx, [r11+18h]
0x14004e451  mov     rdi, [r11+20h]
0x14004e455  mov     rsp, r11
0x14004e458  pop     rbp
0x14004e459  retn
```
