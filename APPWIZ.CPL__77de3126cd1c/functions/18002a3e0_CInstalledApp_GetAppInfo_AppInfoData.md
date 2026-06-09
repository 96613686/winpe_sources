# CInstalledApp::GetAppInfo(_AppInfoData *)

- ea: `0x18002a3e0`
- end: `0x18002a6fc`
- name: `?GetAppInfo@CInstalledApp@@UEAAJPEAU_AppInfoData@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(CInstalledApp *__hidden this, struct _AppInfoData *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002a3e0`
- `0x18002c7b4`
- `0x18002ca1c`
- `0x18002ca78`
- `0x18002cbb4`
- `0x180044db4`
- `0x180045080`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x18002a449`
- `SHCORE!SHStrDupW` at `0x18002a449`
- `SHLWAPI!StrToIntW` at `0x18002a589`
- `SHLWAPI!StrToIntW` at `0x18002a589`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a53c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a53c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a52d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a559`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a52d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a559`
- `ADVAPI32!GetLocalManagedApplicationData` at `0x18002a66f`
- `ADVAPI32!GetLocalManagedApplicationData` at `0x18002a66f`
- `msi!__imp_MsiGetProductInfoW` at `0x18002a509`
- `msi!__imp_MsiGetProductInfoW` at `0x18002a509`

## string_xrefs

- `0x18002a5c5`: `InstallDate`

## pseudocode

```c
__int64 __fastcall CInstalledApp::GetAppInfo(WCHAR *this, struct _AppInfoData *a2)
{
  DWORD dwMask; // r14d
  int v6; // r13d
  HKEY v7; // r15
  unsigned int i; // esi
  CInstalledApp *v9; // rcx
  unsigned __int16 *LocalizedStringFromRegistry; // rax
  __int64 v11; // rdx
  signed int v12; // esi
  WCHAR *v13; // rax
  const WCHAR *pszInstallDate; // rcx
  unsigned int v15; // eax
  int v16; // esi
  LPWSTR v17; // rcx
  WCHAR Dst[4]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR pcchValueBuf[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueBuf[520]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2->cbSize != 152 )
    return 2147500037LL;
  dwMask = a2->dwMask;
  a2->dwMask = 0;
  v6 = dwMask & 1;
  *(_DWORD *)Dst = v6;
  if ( (dwMask & 1) != 0 && SHStrDupW(this + 18, &a2->pszDisplayName) >= 0 )
    a2->dwMask |= 1u;
  if ( (dwMask & 0xFFFFFFFE) != 0 )
  {
    v7 = CInstalledApp::_OpenUninstallRegKey((CInstalledApp *)this, 0x20019u);
    if ( v7 )
    {
      for ( i = 0; i < 0x10; ++i )
      {
        v9 = (CInstalledApp *)(int)i;
        if ( (dwMask & qword_18005ED60[3 * (int)i]) != 0 )
        {
          LocalizedStringFromRegistry = GetLocalizedStringFromRegistry(v7, (LPCWSTR)qword_18005ED60[3 * (int)i + 1]);
          if ( LocalizedStringFromRegistry )
          {
            v11 = LODWORD(qword_18005ED60[3 * (int)i + 2]);
            v9 = (CInstalledApp *)LODWORD(qword_18005ED60[3 * (int)i]);
            a2->dwMask |= (unsigned int)v9;
            *(_QWORD *)((char *)&a2->cbSize + v11) = LocalizedStringFromRegistry;
          }
        }
      }
      v6 = *(_DWORD *)Dst;
      LOBYTE(v9) = (a2->dwMask & 0x20000) == 0;
      if ( ((unsigned __int8)v9 & ((dwMask & 0x20000) != 0)) != 0 && (this[10] & 2) != 0 )
      {
        LODWORD(pcchValueBuf[0]) = 520;
        if ( !MsiGetProductInfoW(this + 2098, L"ProductIcon", ValueBuf, (LPDWORD)pcchValueBuf) )
        {
          if ( ValueBuf[0] )
          {
            v12 = ExpandEnvironmentStringsW(ValueBuf, Dst, 1u);
            v13 = (WCHAR *)CoTaskMemAlloc(2LL * v12);
            a2->pszImage = v13;
            if ( v13 )
            {
              ExpandEnvironmentStringsW(ValueBuf, v13, v12);
              a2->dwMask |= 0x20000u;
            }
          }
        }
      }
      *(_OWORD *)pcchValueBuf = 0;
      if ( (dwMask & 0x1000) != 0 )
      {
        if ( (a2->dwMask & 0x1000) == 0
          || (pszInstallDate = a2->pszInstallDate) != 0
          && (v15 = StrToIntW(pszInstallDate),
              !(unsigned int)InstallDateToSystemTime(v15, (struct _SYSTEMTIME *)pcchValueBuf)) )
        {
          CInstalledApp::_TryToGuessInstallDate(v9, a2, v7);
        }
      }
      RegCloseKey(v7);
    }
  }
  if ( !*((_DWORD *)this + 8) )
    goto LABEL_34;
  if ( (dwMask & 0x1000) != 0 )
    CInstalledApp::_ReplaceMsiUpdateAppInfoField(
      (CInstalledApp *)this,
      a2,
      0x1000u,
      L"InstallDate",
      &a2->pszInstallDate);
  if ( !*((_DWORD *)this + 8) )
    goto LABEL_34;
  if ( (dwMask & 8) != 0 )
    _ReplaceAppInfoField(a2, 8u, this + 2098, &a2->pszProductID);
  if ( *((_DWORD *)this + 8) )
  {
    v16 = dwMask & 0x200;
    if ( (dwMask & 0x200) != 0 )
      CInstalledApp::_ReplaceMsiUpdateAppInfoField((CInstalledApp *)this, a2, 0x200u, L"MoreInfoURL", &a2->pszHelpLink);
  }
  else
  {
LABEL_34:
    v16 = dwMask & 0x200;
  }
  if ( (dwMask & 0x201) != 0 && (this[10] & 2) != 0 )
  {
    pcchValueBuf[0] = 0;
    *(_QWORD *)Dst = 0;
    GetLocalManagedApplicationData(this + 2098, pcchValueBuf, (LPWSTR *)Dst);
    v17 = pcchValueBuf[0];
    if ( pcchValueBuf[0] && v6 )
    {
      _ReplaceAppInfoField(a2, 1u, pcchValueBuf[0], &a2->pszDisplayName);
      v17 = pcchValueBuf[0];
    }
    if ( *(_QWORD *)Dst )
    {
      if ( v16 )
      {
        _ReplaceAppInfoField(a2, 0x200u, *(const unsigned __int16 **)Dst, &a2->pszHelpLink);
        v17 = pcchValueBuf[0];
      }
    }
    LocalFree(v17);
    LocalFree(*(HLOCAL *)Dst);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a3e0  mov     [rsp-8+arg_10], rbx
0x18002a3e5  push    rbp
0x18002a3e6  push    rsi
0x18002a3e7  push    rdi
0x18002a3e8  push    r12
0x18002a3ea  push    r13
0x18002a3ec  push    r14
0x18002a3ee  push    r15
0x18002a3f0  lea     rbp, [rsp-370h]
0x18002a3f8  sub     rsp, 470h
0x18002a3ff  mov     rax, cs:__security_cookie
0x18002a406  xor     rax, rsp
0x18002a409  mov     [rbp+3A0h+var_40], rax
0x18002a410  cmp     dword ptr [rdx], 98h
0x18002a416  mov     rbx, rdx
0x18002a419  mov     rdi, rcx
0x18002a41c  jz      short loc_18002A428
0x18002a41e  mov     eax, 80004005h
0x18002a423  jmp     loc_18002A6D2
0x18002a428  mov     r14d, [rdx+4]
0x18002a42c  xor     r12d, r12d
0x18002a42f  mov     r13d, r14d
0x18002a432  mov     [rdx+4], r12d
0x18002a436  and     r13d, 1
0x18002a43a  mov     dword ptr [rsp+4A0h+Dst], r13d
0x18002a43f  jz      short loc_18002A457
0x18002a441  add     rdx, 8; ppwsz
0x18002a445  add     rcx, 24h ; '$'; psz
0x18002a449  call    cs:__imp_SHStrDupW
0x18002a44f  test    eax, eax
0x18002a451  js      short loc_18002A457
0x18002a453  or      dword ptr [rbx+4], 1
0x18002a457  mov     esi, 1000h
0x18002a45c  test    r14d, 0FFFFFFFEh
0x18002a463  jz      loc_18002A5B3
0x18002a469  mov     edx, 20019h; samDesired
0x18002a46e  mov     rcx, rdi; this
0x18002a471  call    ?_OpenUninstallRegKey@CInstalledApp@@AEAAPEAUHKEY__@@K@Z; CInstalledApp::_OpenUninstallRegKey(ulong)
0x18002a476  mov     r15, rax
0x18002a479  test    rax, rax
0x18002a47c  jz      loc_18002A5B3
0x18002a482  mov     esi, r12d
0x18002a485  lea     r13, qword_18005ED60
0x18002a48c  movsxd  rcx, esi
0x18002a48f  lea     r12, [rcx+rcx*2]
0x18002a493  test    [r13+r12*8+0], r14d
0x18002a498  jz      short loc_18002A4BD
0x18002a49a  mov     rdx, [r13+r12*8+8]; lpString1
0x18002a49f  mov     rcx, r15; hkey
0x18002a4a2  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18002a4a7  test    rax, rax
0x18002a4aa  jz      short loc_18002A4BD
0x18002a4ac  mov     edx, [r13+r12*8+10h]
0x18002a4b1  mov     ecx, [r13+r12*8+0]
0x18002a4b6  or      [rbx+4], ecx
0x18002a4b9  mov     [rdx+rbx], rax
0x18002a4bd  inc     esi
0x18002a4bf  cmp     esi, 10h
0x18002a4c2  jb      short loc_18002A48C
0x18002a4c4  test    dword ptr [rbx+4], 20000h
0x18002a4cb  mov     r13d, dword ptr [rsp+4A0h+Dst]
0x18002a4d0  setz    cl
0x18002a4d3  bt      r14d, 11h
0x18002a4d8  setb    al
0x18002a4db  test    al, cl
0x18002a4dd  jz      loc_18002A566
0x18002a4e3  test    byte ptr [rdi+14h], 2
0x18002a4e7  jz      short loc_18002A566
0x18002a4e9  lea     rcx, [rdi+1064h]; szProduct
0x18002a4f0  mov     dword ptr [rsp+4A0h+pcchValueBuf], 208h
0x18002a4f8  lea     r9, [rsp+4A0h+pcchValueBuf]; pcchValueBuf
0x18002a4fd  lea     r8, [rsp+4A0h+ValueBuf]; lpValueBuf
0x18002a502  lea     rdx, aProducticon; "ProductIcon"
0x18002a509  call    cs:__imp_MsiGetProductInfoW
0x18002a50f  xor     r12d, r12d
0x18002a512  test    eax, eax
0x18002a514  jnz     short loc_18002A569
0x18002a516  cmp     [rsp+4A0h+ValueBuf], r12w
0x18002a51c  jz      short loc_18002A569
0x18002a51e  lea     r8d, [r12+1]; nSize
0x18002a523  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x18002a528  lea     rcx, [rsp+4A0h+ValueBuf]; lpSrc
0x18002a52d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a533  movsxd  rsi, eax
0x18002a536  mov     rcx, rsi
0x18002a539  add     rcx, rcx; cb
0x18002a53c  call    cs:__imp_CoTaskMemAlloc
0x18002a542  mov     [rbx+80h], rax
0x18002a549  test    rax, rax
0x18002a54c  jz      short loc_18002A569
0x18002a54e  mov     r8d, esi; nSize
0x18002a551  lea     rcx, [rsp+4A0h+ValueBuf]; lpSrc
0x18002a556  mov     rdx, rax; lpDst
0x18002a559  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a55f  bts     dword ptr [rbx+4], 11h
0x18002a564  jmp     short loc_18002A569
0x18002a566  xor     r12d, r12d
0x18002a569  mov     esi, 1000h
0x18002a56e  xorps   xmm0, xmm0
0x18002a571  movups  xmmword ptr [rsp+4A0h+pcchValueBuf], xmm0
0x18002a576  test    esi, r14d
0x18002a579  jz      short loc_18002A5AA
0x18002a57b  test    [rbx+4], esi
0x18002a57e  jz      short loc_18002A59F
0x18002a580  mov     rcx, [rbx+68h]; pszSrc
0x18002a584  test    rcx, rcx
0x18002a587  jz      short loc_18002A5AA
0x18002a589  call    cs:__imp_StrToIntW
0x18002a58f  mov     ecx, eax; unsigned int
0x18002a591  lea     rdx, [rsp+4A0h+pcchValueBuf]; struct _SYSTEMTIME *
0x18002a596  call    ?InstallDateToSystemTime@@YAHKPEAU_SYSTEMTIME@@@Z; InstallDateToSystemTime(ulong,_SYSTEMTIME *)
0x18002a59b  test    eax, eax
0x18002a59d  jnz     short loc_18002A5AA
0x18002a59f  mov     r8, r15; HKEY
0x18002a5a2  mov     rdx, rbx; struct _AppInfoData *
0x18002a5a5  call    ?_TryToGuessInstallDate@CInstalledApp@@AEAAXPEAU_AppInfoData@@PEAUHKEY__@@@Z; CInstalledApp::_TryToGuessInstallDate(_AppInfoData *,HKEY__ *)
0x18002a5aa  mov     rcx, r15; hKey
0x18002a5ad  call    cs:__imp_RegCloseKey
0x18002a5b3  cmp     [rdi+20h], r12d
0x18002a5b7  jz      short loc_18002A633
0x18002a5b9  test    esi, r14d
0x18002a5bc  jz      short loc_18002A5DC
0x18002a5be  lea     rax, [rbx+68h]
0x18002a5c2  mov     r8d, esi; unsigned int
0x18002a5c5  lea     r9, aInstalldate; "InstallDate"
0x18002a5cc  mov     [rsp+4A0h+var_480], rax; unsigned __int16 **
0x18002a5d1  mov     rdx, rbx; struct _AppInfoData *
0x18002a5d4  mov     rcx, rdi; this
0x18002a5d7  call    ?_ReplaceMsiUpdateAppInfoField@CInstalledApp@@AEAAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z; CInstalledApp::_ReplaceMsiUpdateAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)
0x18002a5dc  cmp     [rdi+20h], r12d
0x18002a5e0  jz      short loc_18002A633
0x18002a5e2  mov     edx, 8; unsigned int
0x18002a5e7  test    dl, r14b
0x18002a5ea  jz      short loc_18002A5FF
0x18002a5ec  lea     r9, [rbx+20h]; unsigned __int16 **
0x18002a5f0  mov     rcx, rbx; struct _AppInfoData *
0x18002a5f3  lea     r8, [rdi+1064h]; unsigned __int16 *
0x18002a5fa  call    ?_ReplaceAppInfoField@@YAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z; _ReplaceAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)
0x18002a5ff  cmp     [rdi+20h], r12d
0x18002a603  jz      short loc_18002A633
0x18002a605  mov     esi, r14d
0x18002a608  mov     r15d, 200h
0x18002a60e  and     esi, r15d
0x18002a611  jz      short loc_18002A63F
0x18002a613  lea     rax, [rbx+50h]
0x18002a617  mov     r8d, r15d; unsigned int
0x18002a61a  lea     r9, aMoreinfourl; "MoreInfoURL"
0x18002a621  mov     [rsp+4A0h+var_480], rax; unsigned __int16 **
0x18002a626  mov     rdx, rbx; struct _AppInfoData *
0x18002a629  mov     rcx, rdi; this
0x18002a62c  call    ?_ReplaceMsiUpdateAppInfoField@CInstalledApp@@AEAAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z; CInstalledApp::_ReplaceMsiUpdateAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)
0x18002a631  jmp     short loc_18002A63F
0x18002a633  mov     esi, r14d
0x18002a636  mov     r15d, 200h
0x18002a63c  and     esi, r15d
0x18002a63f  test    r14d, 201h
0x18002a646  setnz   cl
0x18002a649  test    byte ptr [rdi+14h], 2
0x18002a64d  setnz   al
0x18002a650  test    al, cl
0x18002a652  jz      short loc_18002A6D0
0x18002a654  lea     rcx, [rdi+1064h]; ProductCode
0x18002a65b  mov     [rsp+4A0h+pcchValueBuf], r12
0x18002a660  lea     r8, [rsp+4A0h+Dst]; SupportUrl
0x18002a665  mov     qword ptr [rsp+4A0h+Dst], r12
0x18002a66a  lea     rdx, [rsp+4A0h+pcchValueBuf]; DisplayName
0x18002a66f  call    cs:__imp_GetLocalManagedApplicationData
0x18002a675  mov     rcx, [rsp+4A0h+pcchValueBuf]
0x18002a67a  test    rcx, rcx
0x18002a67d  jz      short loc_18002A69D
0x18002a67f  test    r13d, r13d
0x18002a682  jz      short loc_18002A69D
0x18002a684  mov     r8, rcx; unsigned __int16 *
0x18002a687  lea     r9, [rbx+8]; unsigned __int16 **
0x18002a68b  mov     rcx, rbx; struct _AppInfoData *
0x18002a68e  mov     edx, 1; unsigned int
0x18002a693  call    ?_ReplaceAppInfoField@@YAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z; _ReplaceAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)
0x18002a698  mov     rcx, [rsp+4A0h+pcchValueBuf]
0x18002a69d  mov     r8, qword ptr [rsp+4A0h+Dst]; unsigned __int16 *
0x18002a6a2  test    r8, r8
0x18002a6a5  jz      short loc_18002A6BF
0x18002a6a7  test    esi, esi
0x18002a6a9  jz      short loc_18002A6BF
0x18002a6ab  lea     r9, [rbx+50h]; unsigned __int16 **
0x18002a6af  mov     edx, r15d; unsigned int
0x18002a6b2  mov     rcx, rbx; struct _AppInfoData *
0x18002a6b5  call    ?_ReplaceAppInfoField@@YAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z; _ReplaceAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)
0x18002a6ba  mov     rcx, [rsp+4A0h+pcchValueBuf]; hMem
0x18002a6bf  call    cs:__imp_LocalFree
0x18002a6c5  mov     rcx, qword ptr [rsp+4A0h+Dst]; hMem
0x18002a6ca  call    cs:__imp_LocalFree
0x18002a6d0  xor     eax, eax
0x18002a6d2  mov     rcx, [rbp+3A0h+var_40]
0x18002a6d9  xor     rcx, rsp; StackCookie
0x18002a6dc  call    __security_check_cookie
0x18002a6e1  mov     rbx, [rsp+4A0h+arg_10]
0x18002a6e9  add     rsp, 470h
0x18002a6f0  pop     r15
0x18002a6f2  pop     r14
0x18002a6f4  pop     r13
0x18002a6f6  pop     r12
0x18002a6f8  pop     rdi
0x18002a6f9  pop     rsi
0x18002a6fa  pop     rbp
0x18002a6fb  retn
```
