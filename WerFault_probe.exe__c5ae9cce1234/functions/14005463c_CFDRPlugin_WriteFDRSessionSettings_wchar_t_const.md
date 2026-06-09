# CFDRPlugin::WriteFDRSessionSettings(wchar_t const *)

- ea: `0x14005463c`
- end: `0x1400549c7`
- name: `?WriteFDRSessionSettings@CFDRPlugin@@AEAAJPEB_W@Z`
- size: `907`
- prototype: `__int64 __fastcall(const BYTE **this, const BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140052e04`

## callees

- `0x140002728`
- `0x140005468`
- `0x14001444c`
- `0x140014474`
- `0x1400530a8`
- `0x14005463c`
- `0x140054aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400546ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400549a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400546ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400549a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400547b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140054819`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400548b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400547b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140054819`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400548b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400546fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400546fd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x140054922`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x140054922`

## string_xrefs

- `0x1400546d3`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x1400548a3`: `LogPath`
- `0x140054812`: `AppPath`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
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
      &WPP_928a4490cd403d1d5470036a68085293_Traceguids,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v11 = -2147024809;
    }
    if ( v16 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v16 + 2), 41, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    goto LABEL_54;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 40;
LABEL_12:
    WPP_SF_(*((_QWORD *)v9 + 2), v10, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
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
0x14005463c  mov     [rsp-38h+arg_0], rbx
0x140054641  push    rbp
0x140054642  push    rsi
0x140054643  push    rdi
0x140054644  push    r12
0x140054646  push    r13
0x140054648  push    r14
0x14005464a  push    r15
0x14005464c  mov     rbp, rsp
0x14005464f  sub     rsp, 60h
0x140054653  xor     edi, edi
0x140054655  mov     r13, rcx
0x140054658  mov     [rbp+dwDisposition], edi
0x14005465b  mov     ecx, edi
0x14005465d  mov     [rbp+hKey], rcx
0x140054661  mov     rbx, rdx
0x140054664  mov     [rbp+pszPath], rdi
0x140054668  mov     r15d, edi
0x14005466b  mov     [rbp+lpData], rdi
0x14005466f  test    rdx, rdx
0x140054672  jnz     short loc_1400546BC
0x140054674  mov     rax, cs:WPP_GLOBAL_Control
0x14005467b  lea     rdi, WPP_GLOBAL_Control
0x140054682  cmp     rax, rdi
0x140054685  jz      short loc_1400546A7
0x140054687  lea     esi, [rdx+1]
0x14005468a  test    [rax+1Ch], sil
0x14005468e  jz      short loc_1400546A7
0x140054690  mov     rcx, [rax+10h]
0x140054694  lea     edx, [rbx+22h]
0x140054697  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005469e  call    WPP_SF_
0x1400546a3  mov     rcx, [rbp+hKey]; hKey
0x1400546a7  test    rcx, rcx
0x1400546aa  jz      short loc_1400546B2
0x1400546ac  call    cs:__imp_RegCloseKey
0x1400546b2  mov     eax, 80070057h
0x1400546b7  jmp     loc_1400549AF
0x1400546bc  lea     rcx, [rbp+hKey]
0x1400546c0  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400546c5  lea     rcx, [rbp+dwDisposition]
0x1400546c9  mov     esi, 1
0x1400546ce  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x1400546d3  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\Windows E"...
0x1400546da  mov     [rsp+60h+phkResult], rax; phkResult
0x1400546df  xor     r9d, r9d; lpClass
0x1400546e2  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1400546e7  xor     r8d, r8d; Reserved
0x1400546ea  mov     [rsp+60h+samDesired], 60002h; samDesired
0x1400546f2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400546f9  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1400546fd  call    cs:__imp_RegCreateKeyExW
0x140054703  test    eax, eax
0x140054705  jz      short loc_14005473D
0x140054707  mov     rcx, cs:WPP_GLOBAL_Control
0x14005470e  lea     rdi, WPP_GLOBAL_Control
0x140054715  cmp     rcx, rdi
0x140054718  jz      short loc_140054733
0x14005471a  test    [rcx+1Ch], sil
0x14005471e  jz      short loc_140054733
0x140054720  lea     edx, [rsi+22h]
0x140054723  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x14005472a  mov     rcx, [rcx+10h]
0x14005472e  call    WPP_SF_
0x140054733  mov     ebx, 80004005h
0x140054738  jmp     loc_140054983
0x14005473d  mov     rcx, [rbp+hKey]; hKey
0x140054741  mov     r8d, 80010002h; unsigned int
0x140054747  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14005474c  xor     ecx, ecx
0x14005474e  lea     r14, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x140054755  lea     rdi, WPP_GLOBAL_Control
0x14005475c  test    eax, eax
0x14005475e  jns     short loc_140054788
0x140054760  mov     rcx, cs:WPP_GLOBAL_Control
0x140054767  cmp     rcx, rdi
0x14005476a  jz      short loc_140054786
0x14005476c  test    byte ptr [rcx+1Ch], 2
0x140054770  jz      short loc_140054786
0x140054772  mov     rcx, [rcx+10h]
0x140054776  mov     edx, 24h ; '$'
0x14005477b  mov     r9d, eax
0x14005477e  mov     r8, r14
0x140054781  call    WPP_SF_d
0x140054786  xor     ecx, ecx
0x140054788  or      r12, 0FFFFFFFFFFFFFFFFh
0x14005478c  mov     rax, r12
0x14005478f  inc     rax
0x140054792  cmp     [rbx+rax*2], cx
0x140054796  jnz     short loc_14005478F
0x140054798  mov     rcx, [rbp+hKey]; hKey
0x14005479c  lea     eax, ds:2[rax*2]
0x1400547a3  mov     [rsp+60h+samDesired], eax; cbData
0x1400547a7  lea     rdx, aSessionsetting; "SessionSettings"
0x1400547ae  mov     r9d, esi; dwType
0x1400547b1  mov     qword ptr [rsp+60h+dwOptions], rbx; lpData
0x1400547b6  xor     r8d, r8d; Reserved
0x1400547b9  call    cs:__imp_RegSetValueExW
0x1400547bf  test    eax, eax
0x1400547c1  jz      short loc_1400547EA
0x1400547c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547ca  cmp     rcx, rdi
0x1400547cd  jz      loc_140054733
0x1400547d3  test    [rcx+1Ch], sil
0x1400547d7  jz      loc_140054733
0x1400547dd  mov     edx, 25h ; '%'
0x1400547e2  mov     r8, r14
0x1400547e5  jmp     loc_14005472A
0x1400547ea  mov     rdx, [r13+8]
0x1400547ee  mov     r9d, esi; dwType
0x1400547f1  mov     rax, [r13+10h]
0x1400547f5  xor     r8d, r8d; Reserved
0x1400547f8  mov     rcx, [rbp+hKey]; hKey
0x1400547fc  sub     rax, rdx
0x1400547ff  sar     rax, 1
0x140054802  lea     eax, ds:2[rax*2]
0x140054809  mov     [rsp+60h+samDesired], eax; cbData
0x14005480d  mov     qword ptr [rsp+60h+dwOptions], rdx; lpData
0x140054812  lea     rdx, aApppath; "AppPath"
0x140054819  call    cs:__imp_RegSetValueExW
0x14005481f  xor     r13d, r13d
0x140054822  test    eax, eax
0x140054824  jz      short loc_140054846
0x140054826  mov     rcx, cs:WPP_GLOBAL_Control
0x14005482d  cmp     rcx, rdi
0x140054830  jz      loc_140054733
0x140054836  test    [rcx+1Ch], sil
0x14005483a  jz      loc_140054733
0x140054840  lea     edx, [r13+26h]
0x140054844  jmp     short loc_1400547E2
0x140054846  lea     r8, [rbp+lpData]
0x14005484a  lea     rdx, [rbp+pszPath]
0x14005484e  call    ?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z; CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)
0x140054853  mov     ebx, eax
0x140054855  test    eax, eax
0x140054857  jns     short loc_140054885
0x140054859  mov     rcx, cs:WPP_GLOBAL_Control
0x140054860  cmp     rcx, rdi
0x140054863  jz      short loc_14005487C
0x140054865  test    [rcx+1Ch], sil
0x140054869  jz      short loc_14005487C
0x14005486b  mov     rcx, [rcx+10h]
0x14005486f  mov     edx, 27h ; '''
0x140054874  mov     r8, r14
0x140054877  call    WPP_SF_
0x14005487c  mov     r15, [rbp+lpData]
0x140054880  jmp     loc_140054983
0x140054885  mov     r15, [rbp+lpData]
0x140054889  inc     r12
0x14005488c  cmp     [r15+r12*2], r13w
0x140054891  jnz     short loc_140054889
0x140054893  mov     rcx, [rbp+hKey]; hKey
0x140054897  lea     eax, ds:2[r12*2]
0x14005489f  mov     [rsp+60h+samDesired], eax; cbData
0x1400548a3  lea     rdx, aLogpath; "LogPath"
0x1400548aa  mov     r9d, esi; dwType
0x1400548ad  mov     qword ptr [rsp+60h+dwOptions], r15; lpData
0x1400548b2  xor     r8d, r8d; Reserved
0x1400548b5  call    cs:__imp_RegSetValueExW
0x1400548bb  test    eax, eax
0x1400548bd  jz      short loc_1400548E3
0x1400548bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548c6  cmp     rcx, rdi
0x1400548c9  jz      loc_140054733
0x1400548cf  test    [rcx+1Ch], sil
0x1400548d3  jz      loc_140054733
0x1400548d9  mov     edx, 28h ; '('
0x1400548de  jmp     loc_1400547E2
0x1400548e3  mov     rdx, [rbp+pszPath]; pszPath
0x1400548e7  test    rdx, rdx
0x1400548ea  jnz     short loc_14005491D
0x1400548ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548f3  cmp     rcx, rdi
0x1400548f6  jz      short loc_140054916
0x1400548f8  test    [rcx+1Ch], sil
0x1400548fc  jz      short loc_140054916
0x1400548fe  mov     rcx, [rcx+10h]
0x140054902  mov     edx, 42h ; 'B'
0x140054907  mov     r8, r14
0x14005490a  call    WPP_SF_
0x14005490f  mov     rcx, cs:WPP_GLOBAL_Control
0x140054916  mov     ebx, 80070057h
0x14005491b  jmp     short loc_140054962
0x14005491d  xor     r8d, r8d; psa
0x140054920  xor     ecx, ecx; hwnd
0x140054922  call    cs:__imp_SHCreateDirectoryExW
0x140054928  test    eax, eax
0x14005492a  jz      short loc_140054980
0x14005492c  cmp     eax, 0B7h
0x140054931  jz      short loc_140054980
0x140054933  mov     rcx, cs:WPP_GLOBAL_Control
0x14005493a  cmp     rcx, rdi
0x14005493d  jz      short loc_14005495D
0x14005493f  test    [rcx+1Ch], sil
0x140054943  jz      short loc_14005495D
0x140054945  mov     rcx, [rcx+10h]
0x140054949  mov     edx, 43h ; 'C'
0x14005494e  mov     r8, r14
0x140054951  call    WPP_SF_
0x140054956  mov     rcx, cs:WPP_GLOBAL_Control
0x14005495d  mov     ebx, 80004005h
0x140054962  cmp     rcx, rdi
0x140054965  jz      short loc_140054983
0x140054967  test    [rcx+1Ch], sil
0x14005496b  jz      short loc_140054983
0x14005496d  mov     rcx, [rcx+10h]
0x140054971  mov     edx, 29h ; ')'
0x140054976  mov     r8, r14
0x140054979  call    WPP_SF_
0x14005497e  jmp     short loc_140054983
0x140054980  mov     ebx, r13d
0x140054983  test    r15, r15
0x140054986  jz      short loc_140054990
0x140054988  mov     rcx, r15; void *
0x14005498b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140054990  mov     rcx, [rbp+pszPath]; void *
0x140054994  test    rcx, rcx
0x140054997  jz      short loc_14005499E
0x140054999  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005499e  mov     rcx, [rbp+hKey]; hKey
0x1400549a2  test    rcx, rcx
0x1400549a5  jz      short loc_1400549AD
0x1400549a7  call    cs:__imp_RegCloseKey
0x1400549ad  mov     eax, ebx
0x1400549af  mov     rbx, [rsp+60h+arg_0]
0x1400549b7  add     rsp, 60h
0x1400549bb  pop     r15
0x1400549bd  pop     r14
0x1400549bf  pop     r13
0x1400549c1  pop     r12
0x1400549c3  pop     rdi
0x1400549c4  pop     rsi
0x1400549c5  pop     rbp
0x1400549c6  retn
```
