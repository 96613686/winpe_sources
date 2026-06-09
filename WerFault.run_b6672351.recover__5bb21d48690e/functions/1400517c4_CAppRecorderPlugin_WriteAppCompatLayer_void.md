# CAppRecorderPlugin::WriteAppCompatLayer(void)

- ea: `0x1400517c4`
- end: `0x140051a97`
- name: `?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `723`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005014c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400054e4`
- `0x14000551c`
- `0x14000ca20`
- `0x140014f14`
- `0x1400517c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005191a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005191a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051a64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051a64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400519a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400519a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400518bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400518bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400519f3`

## string_xrefs

- `0x140051890`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

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
                          L"AppRecorder") )
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
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v5);
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
0x1400517c4  mov     [rsp-8+arg_8], rbx
0x1400517c9  mov     [rsp-8+arg_10], rdi
0x1400517ce  push    rbp
0x1400517cf  lea     rbp, [rsp-1A0h]
0x1400517d7  sub     rsp, 2A0h
0x1400517de  mov     rax, cs:__security_cookie
0x1400517e5  xor     rax, rsp
0x1400517e8  mov     [rbp+1A0h+var_10], rax
0x1400517ef  lea     rax, [rsp+2A0h+var_230]
0x1400517f4  mov     [rsp+2A0h+hkey], 0
0x1400517fd  mov     [rsp+2A0h+lpData], rax
0x140051802  lea     rdx, aApprecorder; "AppRecorder"
0x140051809  lea     rax, [rsp+2A0h+var_230]
0x14005180e  mov     [rsp+2A0h+dwDisposition], 0
0x140051816  mov     [rsp+2A0h+var_238], rax
0x14005181b  mov     rdi, rcx
0x14005181e  xor     eax, eax
0x140051820  mov     [rsp+2A0h+pcbData], 0
0x140051828  lea     rcx, [rsp+2A0h+lpData]
0x14005182d  mov     [rsp+2A0h+var_230], ax
0x140051832  mov     [rbp+1A0h+pvData], ax
0x140051836  lea     r8d, [rax+0Bh]
0x14005183a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14005183f  test    al, al
0x140051841  jnz     short loc_140051879
0x140051843  mov     ebx, 8007000Eh
0x140051848  mov     rcx, cs:WPP_GLOBAL_Control
0x14005184f  lea     rax, WPP_GLOBAL_Control
0x140051856  cmp     rcx, rax
0x140051859  jz      loc_140051A3F
0x14005185f  test    byte ptr [rcx+1Ch], 1
0x140051863  jz      loc_140051A3F
0x140051869  mov     edx, 2Eh ; '.'
0x14005186e  mov     r9d, 8007000Eh
0x140051874  jmp     loc_140051A2F
0x140051879  lea     rcx, [rsp+2A0h+hkey]
0x14005187e  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140051883  lea     rcx, [rsp+2A0h+dwDisposition]
0x140051888  xor     r9d, r9d; lpClass
0x14005188b  mov     [rsp+2A0h+lpdwDisposition], rcx; lpdwDisposition
0x140051890  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows NT\\Curren"...
0x140051897  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14005189c  xor     r8d, r8d; Reserved
0x14005189f  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400518a8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400518af  mov     [rsp+2A0h+samDesired], 3; samDesired
0x1400518b7  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x1400518bf  call    cs:__imp_RegCreateKeyExW
0x1400518c6  nop     dword ptr [rax+rax+00h]
0x1400518cb  test    eax, eax
0x1400518cd  jnz     loc_1400519F3
0x1400518d3  mov     rcx, [rsp+2A0h+hkey]; hkey
0x1400518d8  test    rcx, rcx
0x1400518db  jz      loc_1400519F3
0x1400518e1  lea     r9d, [rax+2]; dwFlags
0x1400518e5  cmp     [rsp+2A0h+dwDisposition], r9d
0x1400518ea  jnz     loc_14005197C
0x1400518f0  mov     r8, [rdi+8]; lpValue
0x1400518f4  lea     rax, [rsp+2A0h+pcbData]
0x1400518f9  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x1400518fe  xor     edx, edx; lpSubKey
0x140051900  lea     rax, [rbp+1A0h+pvData]
0x140051904  mov     [rsp+2A0h+pcbData], 208h
0x14005190c  mov     qword ptr [rsp+2A0h+samDesired], rax; pvData
0x140051911  mov     qword ptr [rsp+2A0h+dwOptions], 0; pdwType
0x14005191a  call    cs:__imp_RegGetValueW
0x140051921  nop     dword ptr [rax+rax+00h]
0x140051926  test    eax, eax
0x140051928  jnz     short loc_140051977
0x14005192a  lea     r9, aApprecorder; "AppRecorder"
0x140051931  lea     r8, [rbp+1A0h+pvData]
0x140051935  lea     rdx, aSS_5; "%s %s"
0x14005193c  lea     rcx, [rsp+2A0h+lpData]
0x140051941  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140051946  mov     ebx, eax
0x140051948  test    eax, eax
0x14005194a  jns     short loc_140051977
0x14005194c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051953  lea     rax, WPP_GLOBAL_Control
0x14005195a  cmp     rcx, rax
0x14005195d  jz      loc_140051A3F
0x140051963  test    byte ptr [rcx+1Ch], 1
0x140051967  jz      loc_140051A3F
0x14005196d  mov     edx, 30h ; '0'
0x140051972  jmp     loc_140051A2C
0x140051977  mov     rcx, [rsp+2A0h+hkey]; hKey
0x14005197c  mov     r8, [rsp+2A0h+lpData]
0x140051981  mov     r9d, 1; dwType
0x140051987  mov     rax, [rsp+2A0h+var_238]
0x14005198c  mov     rdx, [rdi+8]; lpValueName
0x140051990  sub     rax, r8
0x140051993  sar     rax, 1
0x140051996  add     eax, eax
0x140051998  mov     [rsp+2A0h+samDesired], eax; cbData
0x14005199c  mov     qword ptr [rsp+2A0h+dwOptions], r8; lpData
0x1400519a1  xor     r8d, r8d; Reserved
0x1400519a4  call    cs:__imp_RegSetValueExW
0x1400519ab  nop     dword ptr [rax+rax+00h]
0x1400519b0  test    eax, eax
0x1400519b2  jz      short loc_1400519EF
0x1400519b4  call    cs:__imp_GetLastError
0x1400519bb  nop     dword ptr [rax+rax+00h]
0x1400519c0  mov     ebx, eax
0x1400519c2  test    eax, eax
0x1400519c4  jle     short loc_1400519CF
0x1400519c6  movzx   ebx, ax
0x1400519c9  or      ebx, 80070000h
0x1400519cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519d6  lea     rax, WPP_GLOBAL_Control
0x1400519dd  cmp     rcx, rax
0x1400519e0  jz      short loc_140051A3F
0x1400519e2  test    byte ptr [rcx+1Ch], 1
0x1400519e6  jz      short loc_140051A3F
0x1400519e8  mov     edx, 31h ; '1'
0x1400519ed  jmp     short loc_140051A2C
0x1400519ef  xor     ebx, ebx
0x1400519f1  jmp     short loc_140051A3F
0x1400519f3  call    cs:__imp_GetLastError
0x1400519fa  nop     dword ptr [rax+rax+00h]
0x1400519ff  mov     ebx, eax
0x140051a01  test    eax, eax
0x140051a03  jle     short loc_140051A0E
0x140051a05  movzx   ebx, ax
0x140051a08  or      ebx, 80070000h
0x140051a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a15  lea     rax, WPP_GLOBAL_Control
0x140051a1c  cmp     rcx, rax
0x140051a1f  jz      short loc_140051A3F
0x140051a21  test    byte ptr [rcx+1Ch], 1
0x140051a25  jz      short loc_140051A3F
0x140051a27  mov     edx, 2Fh ; '/'
0x140051a2c  mov     r9d, ebx
0x140051a2f  mov     rcx, [rcx+10h]
0x140051a33  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x140051a3a  call    WPP_SF_d
0x140051a3f  mov     rcx, [rsp+2A0h+lpData]; void *
0x140051a44  lea     rax, [rsp+2A0h+var_230]
0x140051a49  cmp     rcx, rax
0x140051a4c  jz      short loc_140051A5A
0x140051a4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140051a55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140051a5a  mov     rcx, [rsp+2A0h+hkey]; hKey
0x140051a5f  test    rcx, rcx
0x140051a62  jz      short loc_140051A70
0x140051a64  call    cs:__imp_RegCloseKey
0x140051a6b  nop     dword ptr [rax+rax+00h]
0x140051a70  mov     eax, ebx
0x140051a72  mov     rcx, [rbp+1A0h+var_10]
0x140051a79  xor     rcx, rsp; StackCookie
0x140051a7c  call    __security_check_cookie
0x140051a81  lea     r11, [rsp+2A0h+var_s0]
0x140051a89  mov     rbx, [r11+18h]
0x140051a8d  mov     rdi, [r11+20h]
0x140051a91  mov     rsp, r11
0x140051a94  pop     rbp
0x140051a95  retn
```
