# CInstalledApp::CInstalledApp(ushort const *,ushort const *,ushort const *,ulong,tagMSIINSTALLCONTEXT)

- ea: `0x18002a058`
- end: `0x18002a29d`
- name: `??0CInstalledApp@@AEAA@PEBG00KW4tagMSIINSTALLCONTEXT@@@Z`
- size: `581`
- prototype: `CInstalledApp *__usercall@<rax>(CInstalledApp *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, LPCWSTR szProduct@<r8>, const unsigned __int16 *@<r9>, unsigned int, enum tagMSIINSTALLCONTEXT)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cce8`
- `0x18002cf38`

## callees

- `0x18000791c`
- `0x18000dd44`
- `0x18002a058`
- `0x18002c090`
- `0x18002c168`
- `0x18002c7b4`
- `0x18002c958`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a20a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a20a`
- `KERNEL32!lstrcmpW` at `0x18002a187`
- `KERNEL32!lstrcmpW` at `0x18002a187`
- `msi!__imp_MsiGetProductInfoW` at `0x18002a1ad`
- `msi!__imp_MsiGetProductInfoW` at `0x18002a1ad`
- `msi!__imp_MsiQueryProductStateW` at `0x18002a215`
- `msi!__imp_MsiQueryProductStateW` at `0x18002a215`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002a172`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002a1e1`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002a172`
- `msi!__imp_MsiGetPatchInfoExW` at `0x18002a1e1`

## string_xrefs

- `0x18002a163`: `Uninstallable`

## pseudocode

```c
CInstalledApp *__fastcall CInstalledApp::CInstalledApp(
        CInstalledApp *this,
        const unsigned __int16 *a2,
        LPCWSTR szProduct,
        const unsigned __int16 *a4,
        unsigned int a5,
        enum tagMSIINSTALLCONTEXT a6)
{
  const WCHAR *v9; // r14
  const unsigned __int16 *v10; // r11
  MSIINSTALLCONTEXT v11; // r9d
  MSIINSTALLCONTEXT v12; // r9d
  HKEY v13; // rsi
  char BlockedActions; // bl
  DWORD pcchValue; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+48h] [rbp-30h] BYREF
  WCHAR Value[8]; // [rsp+50h] [rbp-28h] BYREF

  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &CInstalledApp::`vftable'{for `IInstalledApp3'};
  *((_DWORD *)this + 5) = 2;
  *((_QWORD *)this + 1) = &CInstalledApp::`vftable'{for `IAppUpdate'};
  *((_DWORD *)this + 7) = a5;
  *((_DWORD *)this + 8) = a6;
  *((_QWORD *)this + 535) = 0;
  *((GUID *)this + 431) = GUID_NULL;
  _InterlockedIncrement(&g_cRefThisDll);
  v9 = (const WCHAR *)((char *)this + 4196);
  StringCchCopyW((unsigned __int16 *)this + 2098, 0x27u, szProduct);
  StringCchCopyW((unsigned __int16 *)this + 18, 0x104u, v10);
  *((_WORD *)this + 2926) = 0;
  *((_WORD *)this + 3186) = 0;
  if ( a2 )
    StringCchCopyW((unsigned __int16 *)this + 2666, 0x104u, a2);
  if ( *((_WORD *)this + 2666) )
  {
    v11 = *((_DWORD *)this + 8);
    pcchValue = 5;
    if ( !MsiGetPatchInfoExW(v9, (LPCWSTR)this + 2666, 0, v11, L"Uninstallable", Value, &pcchValue)
      && !lstrcmpW(Value, L"1") )
    {
      *((_DWORD *)this + 6) |= 2u;
    }
    pcchValueBuf[0] = 260;
    MsiGetProductInfoW((LPCWSTR)this + 2666, L"ProductName", (LPWSTR)this + 2926, pcchValueBuf);
    v12 = *((_DWORD *)this + 8);
    pcchValue = 260;
    MsiGetPatchInfoExW(v9, (LPCWSTR)this + 2666, 0, v12, L"DisplayName", (LPWSTR)this + 18, &pcchValue);
    if ( !*((_WORD *)this + 18) )
    {
      *((_DWORD *)this + 7) |= 8u;
      LoadStringW(g_hinst, 0x99u, (LPWSTR)this + 18, 260);
    }
  }
  else if ( MsiQueryProductStateW(szProduct) == INSTALLSTATE_ADVERTISED )
  {
    *((_DWORD *)this + 6) |= 2u;
  }
  else
  {
    *(_QWORD *)pcchValueBuf = 0;
    v13 = CInstalledApp::_OpenUninstallRegKey(this, 0x20019u);
    CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(pcchValueBuf);
    *(_QWORD *)pcchValueBuf = v13;
    if ( v13 )
    {
      BlockedActions = CInstalledApp::_QueryBlockedActions(this, v13);
      CInstalledApp::_GetInstallLocationFromRegistry(this, v13);
      *((_DWORD *)this + 6) |= ~BlockedActions & 0xE;
      CInstalledApp::_GetUpdateUrl(this);
    }
    CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(pcchValueBuf);
  }
  return this;
}

```

## disassembly

```asm
0x18002a058  push    rbp
0x18002a05a  push    rbx
0x18002a05b  push    rsi
0x18002a05c  push    rdi
0x18002a05d  push    r12
0x18002a05f  push    r13
0x18002a061  push    r14
0x18002a063  push    r15
0x18002a065  mov     rbp, rsp
0x18002a068  sub     rsp, 78h
0x18002a06c  mov     rax, cs:__security_cookie
0x18002a073  xor     rax, rsp
0x18002a076  mov     [rbp+var_18], rax
0x18002a07a  lea     rax, ??_7CInstalledApp@@6BIInstalledApp3@@@; const CInstalledApp::`vftable'{for `IInstalledApp3'}
0x18002a081  mov     dword ptr [rcx+10h], 1
0x18002a088  mov     [rcx], rax
0x18002a08b  mov     r11, r9
0x18002a08e  lea     rax, ??_7CInstalledApp@@6BIAppUpdate@@@; const CInstalledApp::`vftable'{for `IAppUpdate'}
0x18002a095  mov     dword ptr [rcx+14h], 2
0x18002a09c  mov     [rcx+8], rax
0x18002a0a0  mov     r15, r8
0x18002a0a3  mov     eax, [rbp+arg_20]
0x18002a0a6  mov     r12, rdx
0x18002a0a9  mov     [rcx+1Ch], eax
0x18002a0ac  mov     rdi, rcx
0x18002a0af  mov     eax, [rbp+arg_28]
0x18002a0b2  mov     [rcx+20h], eax
0x18002a0b5  mov     qword ptr [rcx+10B8h], 0
0x18002a0c0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002a0c7  movdqu  xmmword ptr [rcx+1AF0h], xmm0
0x18002a0cf  lock inc cs:g_cRefThisDll
0x18002a0d6  lea     r14, [rcx+1064h]
0x18002a0dd  mov     edx, 27h ; '''; unsigned __int64
0x18002a0e2  mov     rcx, r14; unsigned __int16 *
0x18002a0e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a0ea  lea     rsi, [rdi+24h]
0x18002a0ee  mov     r8, r11; unsigned __int16 *
0x18002a0f1  mov     rcx, rsi; unsigned __int16 *
0x18002a0f4  mov     edx, 104h; unsigned __int64
0x18002a0f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a0fe  xor     eax, eax
0x18002a100  lea     r13, [rdi+16DCh]
0x18002a107  xor     r11d, r11d
0x18002a10a  mov     [r13+0], ax
0x18002a10f  mov     [rdi+18E4h], r11w
0x18002a117  lea     rbx, [rdi+14D4h]
0x18002a11e  test    r12, r12
0x18002a121  jz      short loc_18002A133
0x18002a123  mov     r8, r12; unsigned __int16 *
0x18002a126  mov     edx, 104h; unsigned __int64
0x18002a12b  mov     rcx, rbx; unsigned __int16 *
0x18002a12e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a133  xor     r12d, r12d
0x18002a136  cmp     [rbx], r12w
0x18002a13a  jz      loc_18002A212
0x18002a140  mov     r9d, [rdi+20h]; dwContext
0x18002a144  lea     rax, [rbp+var_38]
0x18002a148  mov     [rsp+78h+pcchValue], rax; pcchValue
0x18002a14d  xor     r8d, r8d; szUserSid
0x18002a150  lea     rax, [rbp+Value]
0x18002a154  mov     [rbp+var_38], 5
0x18002a15b  mov     [rsp+78h+lpValue], rax; lpValue
0x18002a160  mov     rdx, rbx; szProductCode
0x18002a163  lea     rax, szProperty; "Uninstallable"
0x18002a16a  mov     rcx, r14; szPatchCode
0x18002a16d  mov     [rsp+78h+szProperty], rax; szProperty
0x18002a172  call    cs:__imp_MsiGetPatchInfoExW
0x18002a178  test    eax, eax
0x18002a17a  jnz     short loc_18002A195
0x18002a17c  lea     rdx, a1; "1"
0x18002a183  lea     rcx, [rbp+Value]; lpString1
0x18002a187  call    cs:__imp_lstrcmpW
0x18002a18d  test    eax, eax
0x18002a18f  jnz     short loc_18002A195
0x18002a191  or      dword ptr [rdi+18h], 2
0x18002a195  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x18002a199  mov     [rbp+pcchValueBuf], 104h
0x18002a1a0  mov     r8, r13; lpValueBuf
0x18002a1a3  lea     rdx, szAttribute; "ProductName"
0x18002a1aa  mov     rcx, rbx; szProduct
0x18002a1ad  call    cs:__imp_MsiGetProductInfoW
0x18002a1b3  mov     r9d, [rdi+20h]; dwContext
0x18002a1b7  lea     rax, [rbp+var_38]
0x18002a1bb  mov     [rsp+78h+pcchValue], rax; pcchValue
0x18002a1c0  xor     r8d, r8d; szUserSid
0x18002a1c3  lea     rax, aDisplayname; "DisplayName"
0x18002a1ca  mov     [rsp+78h+lpValue], rsi; lpValue
0x18002a1cf  mov     rdx, rbx; szProductCode
0x18002a1d2  mov     [rsp+78h+szProperty], rax; szProperty
0x18002a1d7  mov     rcx, r14; szPatchCode
0x18002a1da  mov     [rbp+var_38], 104h
0x18002a1e1  call    cs:__imp_MsiGetPatchInfoExW
0x18002a1e7  cmp     [rdi+24h], r12w
0x18002a1ec  jnz     loc_18002A27D
0x18002a1f2  or      dword ptr [rdi+1Ch], 8
0x18002a1f6  mov     r9d, 104h; cchBufferMax
0x18002a1fc  mov     rcx, cs:g_hinst; hInstance
0x18002a203  mov     r8, rsi; lpBuffer
0x18002a206  lea     edx, [r9-6Bh]; uID
0x18002a20a  call    cs:__imp_LoadStringW
0x18002a210  jmp     short loc_18002A27D
0x18002a212  mov     rcx, r15; szProduct
0x18002a215  call    cs:__imp_MsiQueryProductStateW
0x18002a21b  cmp     eax, 1
0x18002a21e  jnz     short loc_18002A226
0x18002a220  or      dword ptr [rdi+18h], 2
0x18002a224  jmp     short loc_18002A27D
0x18002a226  mov     edx, 20019h; samDesired
0x18002a22b  mov     qword ptr [rbp+pcchValueBuf], r12
0x18002a22f  mov     rcx, rdi; this
0x18002a232  call    ?_OpenUninstallRegKey@CInstalledApp@@AEAAPEAUHKEY__@@K@Z; CInstalledApp::_OpenUninstallRegKey(ulong)
0x18002a237  lea     rcx, [rbp+pcchValueBuf]
0x18002a23b  mov     rsi, rax
0x18002a23e  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x18002a243  mov     qword ptr [rbp+pcchValueBuf], rsi
0x18002a247  test    rsi, rsi
0x18002a24a  jz      short loc_18002A274
0x18002a24c  mov     rdx, rsi; HKEY
0x18002a24f  mov     rcx, rdi; this
0x18002a252  call    ?_QueryBlockedActions@CInstalledApp@@AEAAKPEAUHKEY__@@@Z; CInstalledApp::_QueryBlockedActions(HKEY__ *)
0x18002a257  mov     rdx, rsi; HKEY
0x18002a25a  mov     rcx, rdi; this
0x18002a25d  mov     ebx, eax
0x18002a25f  call    ?_GetInstallLocationFromRegistry@CInstalledApp@@AEAAXPEAUHKEY__@@@Z; CInstalledApp::_GetInstallLocationFromRegistry(HKEY__ *)
0x18002a264  not     ebx
0x18002a266  mov     rcx, rdi; this
0x18002a269  and     ebx, 0Eh
0x18002a26c  or      [rdi+18h], ebx
0x18002a26f  call    ?_GetUpdateUrl@CInstalledApp@@AEAAXXZ; CInstalledApp::_GetUpdateUrl(void)
0x18002a274  lea     rcx, [rbp+pcchValueBuf]
0x18002a278  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x18002a27d  mov     rax, rdi
0x18002a280  mov     rcx, [rbp+var_18]
0x18002a284  xor     rcx, rsp; StackCookie
0x18002a287  call    __security_check_cookie
0x18002a28c  add     rsp, 78h
0x18002a290  pop     r15
0x18002a292  pop     r14
0x18002a294  pop     r13
0x18002a296  pop     r12
0x18002a298  pop     rdi
0x18002a299  pop     rsi
0x18002a29a  pop     rbx
0x18002a29b  pop     rbp
0x18002a29c  retn
```
