# CFDRPlugin::WriteFDRSessionSettings(wchar_t const *)

- ea: `0x140058034`
- end: `0x1400583ea`
- name: `?WriteFDRSessionSettings@CFDRPlugin@@AEAAJPEB_W@Z`
- size: `950`
- prototype: `int(CFDRPlugin *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140056730`

## callees

- `0x140002748`
- `0x14000551c`
- `0x140014ee4`
- `0x140014f14`
- `0x1400569f0`
- `0x140058034`
- `0x1400584c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400580a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400583c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400580a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400583c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400581bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058223`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400582c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400581bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058223`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400582c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400580fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400580fb`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x140058338`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x140058338`

## string_xrefs

- `0x1400580d1`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x1400582b3`: `LogPath`
- `0x14005821c`: `AppPath`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::WriteFDRSessionSettings(const BYTE **this, const BYTE *a2)
{
  HKEY v3; // rcx
  BYTE *v5; // r15
  HKEY *phkResult; // rax
  const struct std::nothrow_t *v8; // rdx
  CUserModeHangReport *v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // eax
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // rcx
  CUserModeHangReport *v16; // rcx
  int v17; // eax
  LPCWSTR pszPath[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+50h] BYREF
  BYTE *lpData; // [rsp+B8h] [rbp+58h] BYREF

  dwDisposition = 0;
  v3 = 0;
  hKey = 0;
  pszPath[0] = 0;
  v5 = 0;
  lpData = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v3 = hKey;
    }
    if ( v3 )
      RegCloseKey(v3);
    return 2147942487LL;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession",
         0,
         0,
         1u,
         0x60002u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v10 = 35;
    goto LABEL_12;
  }
  v12 = WerPluginAdjustAppContainerAccessToKey(hKey, (enum _ACCESS_MODE)v8, 0x80010002);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_928a4490cd403d1d5470036a68085293_Traceguids,
      (unsigned int)v12);
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&a2[2 * v14] );
  if ( RegSetValueExW(hKey, L"SessionSettings", 0, 1u, a2, 2 * v14 + 2) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v10 = 37;
    goto LABEL_12;
  }
  if ( RegSetValueExW(hKey, L"AppPath", 0, 1u, this[1], 2 * ((this[2] - this[1]) >> 1) + 2) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v10 = 38;
    goto LABEL_12;
  }
  v11 = CFDRPlugin::GenerateLogPathAndFileName(v15, pszPath, &lpData);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    }
    v5 = lpData;
    goto LABEL_54;
  }
  v5 = lpData;
  do
    ++v13;
  while ( *(_WORD *)&lpData[2 * v13] );
  if ( !RegSetValueExW(hKey, L"LogPath", 0, 1u, lpData, 2 * v13 + 2) )
  {
    v8 = (const struct std::nothrow_t *)pszPath[0];
    if ( pszPath[0] )
    {
      v17 = SHCreateDirectoryExW(0, pszPath[0], 0);
      if ( !v17 || v17 == 183 )
      {
        v11 = 0;
        goto LABEL_54;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v11 = -2147467259;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v11 = -2147024809;
    }
    if ( v16 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v16 + 2), 41, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    goto LABEL_54;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 40;
LABEL_12:
    WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
LABEL_13:
  v11 = -2147467259;
LABEL_54:
  if ( v5 )
    operator delete(v5, v8);
  if ( pszPath[0] )
    operator delete((void *)pszPath[0], v8);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140058034  mov     [rsp-38h+arg_0], rbx
0x140058039  push    rbp
0x14005803a  push    rsi
0x14005803b  push    rdi
0x14005803c  push    r12
0x14005803e  push    r13
0x140058040  push    r14
0x140058042  push    r15
0x140058044  mov     rbp, rsp
0x140058047  sub     rsp, 60h
0x14005804b  xor     edi, edi
0x14005804d  mov     r13, rcx
0x140058050  mov     [rbp+dwDisposition], edi
0x140058053  mov     ecx, edi
0x140058055  mov     [rbp+hKey], rcx
0x140058059  mov     rbx, rdx
0x14005805c  mov     [rbp+pszPath], rdi
0x140058060  mov     r15d, edi
0x140058063  mov     [rbp+lpData], rdi
0x140058067  test    rdx, rdx
0x14005806a  jnz     short loc_1400580BA
0x14005806c  mov     rax, cs:WPP_GLOBAL_Control
0x140058073  lea     rdi, WPP_GLOBAL_Control
0x14005807a  cmp     rax, rdi
0x14005807d  jz      short loc_14005809F
0x14005807f  lea     esi, [rdx+1]
0x140058082  test    [rax+1Ch], sil
0x140058086  jz      short loc_14005809F
0x140058088  mov     rcx, [rax+10h]
0x14005808c  lea     edx, [rbx+22h]
0x14005808f  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140058096  call    WPP_SF_
0x14005809b  mov     rcx, [rbp+hKey]; hKey
0x14005809f  test    rcx, rcx
0x1400580a2  jz      short loc_1400580B0
0x1400580a4  call    cs:__imp_RegCloseKey
0x1400580ab  nop     dword ptr [rax+rax+00h]
0x1400580b0  mov     eax, 80070057h
0x1400580b5  jmp     loc_1400583D1
0x1400580ba  lea     rcx, [rbp+hKey]
0x1400580be  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400580c3  lea     rcx, [rbp+dwDisposition]
0x1400580c7  mov     esi, 1
0x1400580cc  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x1400580d1  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\Windows E"...
0x1400580d8  mov     [rsp+60h+phkResult], rax; phkResult
0x1400580dd  xor     r9d, r9d; lpClass
0x1400580e0  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1400580e5  xor     r8d, r8d; Reserved
0x1400580e8  mov     [rsp+60h+samDesired], 60002h; samDesired
0x1400580f0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400580f7  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1400580fb  call    cs:__imp_RegCreateKeyExW
0x140058102  nop     dword ptr [rax+rax+00h]
0x140058107  test    eax, eax
0x140058109  jz      short loc_140058141
0x14005810b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058112  lea     rdi, WPP_GLOBAL_Control
0x140058119  cmp     rcx, rdi
0x14005811c  jz      short loc_140058137
0x14005811e  test    [rcx+1Ch], sil
0x140058122  jz      short loc_140058137
0x140058124  lea     edx, [rsi+22h]
0x140058127  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005812e  mov     rcx, [rcx+10h]
0x140058132  call    WPP_SF_
0x140058137  mov     ebx, 80004005h
0x14005813c  jmp     loc_14005839F
0x140058141  mov     rcx, [rbp+hKey]; hKey
0x140058145  mov     r8d, 80010002h; unsigned int
0x14005814b  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x140058150  xor     ecx, ecx
0x140058152  lea     r14, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140058159  lea     rdi, WPP_GLOBAL_Control
0x140058160  test    eax, eax
0x140058162  jns     short loc_14005818C
0x140058164  mov     rcx, cs:WPP_GLOBAL_Control
0x14005816b  cmp     rcx, rdi
0x14005816e  jz      short loc_14005818A
0x140058170  test    byte ptr [rcx+1Ch], 2
0x140058174  jz      short loc_14005818A
0x140058176  mov     rcx, [rcx+10h]
0x14005817a  mov     edx, 24h ; '$'
0x14005817f  mov     r9d, eax
0x140058182  mov     r8, r14
0x140058185  call    WPP_SF_d
0x14005818a  xor     ecx, ecx
0x14005818c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140058190  mov     rax, r12
0x140058193  inc     rax
0x140058196  cmp     [rbx+rax*2], cx
0x14005819a  jnz     short loc_140058193
0x14005819c  mov     rcx, [rbp+hKey]; hKey
0x1400581a0  lea     eax, ds:2[rax*2]
0x1400581a7  mov     [rsp+60h+samDesired], eax; cbData
0x1400581ab  lea     rdx, aSessionsetting; "SessionSettings"
0x1400581b2  mov     r9d, esi; dwType
0x1400581b5  mov     qword ptr [rsp+60h+dwOptions], rbx; lpData
0x1400581ba  xor     r8d, r8d; Reserved
0x1400581bd  call    cs:__imp_RegSetValueExW
0x1400581c4  nop     dword ptr [rax+rax+00h]
0x1400581c9  test    eax, eax
0x1400581cb  jz      short loc_1400581F4
0x1400581cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400581d4  cmp     rcx, rdi
0x1400581d7  jz      loc_140058137
0x1400581dd  test    [rcx+1Ch], sil
0x1400581e1  jz      loc_140058137
0x1400581e7  mov     edx, 25h ; '%'
0x1400581ec  mov     r8, r14
0x1400581ef  jmp     loc_14005812E
0x1400581f4  mov     rdx, [r13+8]
0x1400581f8  mov     r9d, esi; dwType
0x1400581fb  mov     rax, [r13+10h]
0x1400581ff  xor     r8d, r8d; Reserved
0x140058202  mov     rcx, [rbp+hKey]; hKey
0x140058206  sub     rax, rdx
0x140058209  sar     rax, 1
0x14005820c  lea     eax, ds:2[rax*2]
0x140058213  mov     [rsp+60h+samDesired], eax; cbData
0x140058217  mov     qword ptr [rsp+60h+dwOptions], rdx; lpData
0x14005821c  lea     rdx, aApppath; "AppPath"
0x140058223  call    cs:__imp_RegSetValueExW
0x14005822a  nop     dword ptr [rax+rax+00h]
0x14005822f  xor     r13d, r13d
0x140058232  test    eax, eax
0x140058234  jz      short loc_140058256
0x140058236  mov     rcx, cs:WPP_GLOBAL_Control
0x14005823d  cmp     rcx, rdi
0x140058240  jz      loc_140058137
0x140058246  test    [rcx+1Ch], sil
0x14005824a  jz      loc_140058137
0x140058250  lea     edx, [r13+26h]
0x140058254  jmp     short loc_1400581EC
0x140058256  lea     r8, [rbp+lpData]
0x14005825a  lea     rdx, [rbp+pszPath]
0x14005825e  call    ?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z; CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)
0x140058263  mov     ebx, eax
0x140058265  test    eax, eax
0x140058267  jns     short loc_140058295
0x140058269  mov     rcx, cs:WPP_GLOBAL_Control
0x140058270  cmp     rcx, rdi
0x140058273  jz      short loc_14005828C
0x140058275  test    [rcx+1Ch], sil
0x140058279  jz      short loc_14005828C
0x14005827b  mov     rcx, [rcx+10h]
0x14005827f  mov     edx, 27h ; '''
0x140058284  mov     r8, r14
0x140058287  call    WPP_SF_
0x14005828c  mov     r15, [rbp+lpData]
0x140058290  jmp     loc_14005839F
0x140058295  mov     r15, [rbp+lpData]
0x140058299  inc     r12
0x14005829c  cmp     [r15+r12*2], r13w
0x1400582a1  jnz     short loc_140058299
0x1400582a3  mov     rcx, [rbp+hKey]; hKey
0x1400582a7  lea     eax, ds:2[r12*2]
0x1400582af  mov     [rsp+60h+samDesired], eax; cbData
0x1400582b3  lea     rdx, aLogpath; "LogPath"
0x1400582ba  mov     r9d, esi; dwType
0x1400582bd  mov     qword ptr [rsp+60h+dwOptions], r15; lpData
0x1400582c2  xor     r8d, r8d; Reserved
0x1400582c5  call    cs:__imp_RegSetValueExW
0x1400582cc  nop     dword ptr [rax+rax+00h]
0x1400582d1  test    eax, eax
0x1400582d3  jz      short loc_1400582F9
0x1400582d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400582dc  cmp     rcx, rdi
0x1400582df  jz      loc_140058137
0x1400582e5  test    [rcx+1Ch], sil
0x1400582e9  jz      loc_140058137
0x1400582ef  mov     edx, 28h ; '('
0x1400582f4  jmp     loc_1400581EC
0x1400582f9  mov     rdx, [rbp+pszPath]; pszPath
0x1400582fd  test    rdx, rdx
0x140058300  jnz     short loc_140058333
0x140058302  mov     rcx, cs:WPP_GLOBAL_Control
0x140058309  cmp     rcx, rdi
0x14005830c  jz      short loc_14005832C
0x14005830e  test    [rcx+1Ch], sil
0x140058312  jz      short loc_14005832C
0x140058314  mov     rcx, [rcx+10h]
0x140058318  mov     edx, 42h ; 'B'
0x14005831d  mov     r8, r14
0x140058320  call    WPP_SF_
0x140058325  mov     rcx, cs:WPP_GLOBAL_Control
0x14005832c  mov     ebx, 80070057h
0x140058331  jmp     short loc_14005837E
0x140058333  xor     r8d, r8d; psa
0x140058336  xor     ecx, ecx; hwnd
0x140058338  call    cs:__imp_SHCreateDirectoryExW
0x14005833f  nop     dword ptr [rax+rax+00h]
0x140058344  test    eax, eax
0x140058346  jz      short loc_14005839C
0x140058348  cmp     eax, 0B7h
0x14005834d  jz      short loc_14005839C
0x14005834f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058356  cmp     rcx, rdi
0x140058359  jz      short loc_140058379
0x14005835b  test    [rcx+1Ch], sil
0x14005835f  jz      short loc_140058379
0x140058361  mov     rcx, [rcx+10h]
0x140058365  mov     edx, 43h ; 'C'
0x14005836a  mov     r8, r14
0x14005836d  call    WPP_SF_
0x140058372  mov     rcx, cs:WPP_GLOBAL_Control
0x140058379  mov     ebx, 80004005h
0x14005837e  cmp     rcx, rdi
0x140058381  jz      short loc_14005839F
0x140058383  test    [rcx+1Ch], sil
0x140058387  jz      short loc_14005839F
0x140058389  mov     rcx, [rcx+10h]
0x14005838d  mov     edx, 29h ; ')'
0x140058392  mov     r8, r14
0x140058395  call    WPP_SF_
0x14005839a  jmp     short loc_14005839F
0x14005839c  mov     ebx, r13d
0x14005839f  test    r15, r15
0x1400583a2  jz      short loc_1400583AC
0x1400583a4  mov     rcx, r15; void *
0x1400583a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400583ac  mov     rcx, [rbp+pszPath]; void *
0x1400583b0  test    rcx, rcx
0x1400583b3  jz      short loc_1400583BA
0x1400583b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400583ba  mov     rcx, [rbp+hKey]; hKey
0x1400583be  test    rcx, rcx
0x1400583c1  jz      short loc_1400583CF
0x1400583c3  call    cs:__imp_RegCloseKey
0x1400583ca  nop     dword ptr [rax+rax+00h]
0x1400583cf  mov     eax, ebx
0x1400583d1  mov     rbx, [rsp+60h+arg_0]
0x1400583d9  add     rsp, 60h
0x1400583dd  pop     r15
0x1400583df  pop     r14
0x1400583e1  pop     r13
0x1400583e3  pop     r12
0x1400583e5  pop     rdi
0x1400583e6  pop     rsi
0x1400583e7  pop     rbp
0x1400583e8  retn
```
