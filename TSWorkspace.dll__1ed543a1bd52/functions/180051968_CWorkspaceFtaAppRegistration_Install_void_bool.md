# CWorkspaceFtaAppRegistration::Install(void *,bool)

- ea: `0x180051968`
- end: `0x180052283`
- name: `?Install@CWorkspaceFtaAppRegistration@@QEAAJPEAX_N@Z`
- size: `2331`
- prototype: `__int64 __fastcall(CWorkspaceFtaAppRegistration *__hidden this, void *, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180034224`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x18001e610`
- `0x180020bf0`
- `0x180025824`
- `0x1800513e4`
- `0x180051968`
- `0x18005269c`
- `0x1800526cc`
- `0x180052f28`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180051c2e`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18005201c`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180051c2e`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x18005201c`
- `ADVAPI32!RegCloseKey` at `0x18005222e`
- `ADVAPI32!RegCloseKey` at `0x180052243`
- `ADVAPI32!RegCloseKey` at `0x18005222e`
- `ADVAPI32!RegCloseKey` at `0x180052243`
- `ADVAPI32!RegSetValueExW` at `0x180051df8`
- `ADVAPI32!RegSetValueExW` at `0x180051e7a`
- `ADVAPI32!RegSetValueExW` at `0x1800521b2`
- `ADVAPI32!RegSetValueExW` at `0x180051df8`
- `ADVAPI32!RegSetValueExW` at `0x180051e7a`
- `ADVAPI32!RegSetValueExW` at `0x1800521b2`

## string_xrefs

- `0x1800520c2`: `SizeTMult(Capabilities Key path length) failed`
- `0x18005211e`: `SizeTAdd(Capabilities Key path length) failed`
- `0x180052174`: `SizeTToDWord(Capabilities Key path length) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CWorkspaceFtaAppRegistration::Install(CWorkspaceFtaAppRegistration *this, void *a2, char a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // edi
  LSTATUS DoesAppRegistrationExist; // esi
  unsigned int v17; // eax
  __int64 v18; // rdi
  int v19; // ebx
  int v20; // eax
  int v21; // edx
  int v22; // ecx
  unsigned int v23; // eax
  const WCHAR *v24; // rax
  unsigned __int64 v25; // rdx
  unsigned int v26; // edi
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  int v30; // edx
  const char *v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned int v33; // eax
  const BYTE *v34; // rax
  DWORD v35; // r12d
  LSTATUS v36; // edi
  unsigned int v37; // esi
  unsigned int v38; // eax
  __int64 v39; // rdx
  const BYTE *v40; // rax
  __int64 v41; // rbx
  unsigned int v42; // eax
  __int64 v43; // rdi
  int v44; // ebx
  int v45; // eax
  int v46; // edx
  int v47; // ecx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rcx
  unsigned int v50; // eax
  const WCHAR *v51; // rbx
  const BYTE *v52; // rax
  REGSAM samDesired[2]; // [rsp+30h] [rbp-D8h]
  bool v55[8]; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbData[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  HKEY phkResult[2]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v59[16]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v60; // [rsp+A0h] [rbp-68h]
  _BYTE v61[32]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v62[32]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v63[32]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v64[32]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v65[32]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v66[32]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v67[32]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE v68[32]; // [rsp+190h] [rbp+88h] BYREF

  phkResult[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey = 0;
  phkResult[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v7 = std::wstring::wstring(v68, L"Software\\Microsoft\\Workspaces\\Feeds");
  v8 = std::operator+<unsigned short>(v67, v7, L"\\");
  v9 = std::operator+<unsigned short>(v66, v8, (char *)this + 112);
  v10 = std::operator+<unsigned short>(v65, v9, L"\\");
  v11 = std::operator+<unsigned short>(v64, v10, L"Resources");
  v12 = std::operator+<unsigned short>(v63, v11, L"\\");
  v13 = std::operator+<unsigned short>(v62, v12, (char *)this + 48);
  v14 = std::operator+<unsigned short>(v61, v13, L"\\");
  std::operator+<unsigned short>(v59, v14, L"Capabilities");
  std::wstring::~wstring(v61);
  std::wstring::~wstring(v62);
  std::wstring::~wstring(v63);
  std::wstring::~wstring(v64);
  std::wstring::~wstring(v65);
  std::wstring::~wstring(v66);
  std::wstring::~wstring(v67);
  std::wstring::~wstring(v68);
  v15 = v60;
  if ( v60 > 0x103 )
  {
    DoesAppRegistrationExist = -2147024774;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v17, v15);
    }
    if ( (Microsoft_Windows_RemoteApp_and_Desktop_ConnectionsEnableBits & 1) != 0 )
    {
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 176);
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      McTemplateU0zzzq_EventWriteTransfer(v22, v21, v20, v19, v18, 122);
    }
    goto LABEL_112;
  }
  if ( a2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        v23,
        -2147024809);
    }
    DoesAppRegistrationExist = -2147024809;
    goto LABEL_112;
  }
  v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  DoesAppRegistrationExist = RegCreateKeyTransactedW(HKEY_CURRENT_USER, v24, 0, 0, 0, 0x20006u, 0, &hKey, 0, a2, 0);
  if ( DoesAppRegistrationExist )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    if ( DoesAppRegistrationExist > 0 )
      v26 = (unsigned __int16)DoesAppRegistrationExist | 0x80070000;
    else
      v26 = DoesAppRegistrationExist;
    v27 = RdpWppGetCurrentThreadActivityIdPrefix();
    v28 = 16;
LABEL_27:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v27, v26);
LABEL_28:
    if ( DoesAppRegistrationExist <= 0 )
      goto LABEL_112;
    DoesAppRegistrationExist = (unsigned __int16)DoesAppRegistrationExist;
LABEL_111:
    DoesAppRegistrationExist |= 0x80070000;
    goto LABEL_112;
  }
  *(_QWORD *)cbData = 0;
  DoesAppRegistrationExist = ULongLongMult(*((_QWORD *)this + 12), v25, (unsigned __int64 *)cbData);
  if ( DoesAppRegistrationExist < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v30 = 17;
    v31 = "SizeTMult(friendly name length) failed";
    goto LABEL_35;
  }
  v32 = *(_QWORD *)cbData + 1LL;
  if ( (unsigned __int64)(*(_QWORD *)cbData + 1LL) < *(_QWORD *)cbData )
  {
    DoesAppRegistrationExist = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      samDesired[0] = -2147024362;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        v33,
        (__int64)"SizeTAdd(friendly name length) failed",
        *(_QWORD *)samDesired);
    }
    goto LABEL_112;
  }
  cbData[0] = 0;
  DoesAppRegistrationExist = ULongLongToULong(v32, cbData);
  if ( DoesAppRegistrationExist < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v30 = 19;
    v31 = "SizeTToDWord(friendly name length) failed";
    goto LABEL_35;
  }
  v34 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
  v35 = cbData[0];
  v36 = RegSetValueExW(hKey, L"ApplicationName", 0, 1u, v34, cbData[0]);
  if ( v36 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_108;
    }
    if ( v36 > 0 )
      v37 = (unsigned __int16)v36 | 0x80070000;
    else
      v37 = v36;
    v38 = RdpWppGetCurrentThreadActivityIdPrefix();
    v39 = 20;
LABEL_107:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v38, v37);
LABEL_108:
    if ( v36 <= 0 )
    {
      DoesAppRegistrationExist = v36;
      goto LABEL_112;
    }
    DoesAppRegistrationExist = (unsigned __int16)v36;
    goto LABEL_111;
  }
  v40 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
  v36 = RegSetValueExW(hKey, L"ApplicationDescription", 0, 1u, v40, v35);
  if ( v36 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_108;
    }
    if ( v36 > 0 )
      v37 = (unsigned __int16)v36 | 0x80070000;
    else
      v37 = v36;
    v38 = RdpWppGetCurrentThreadActivityIdPrefix();
    v39 = 21;
    goto LABEL_107;
  }
  if ( !a3 )
    goto LABEL_112;
  v55[0] = 0;
  DoesAppRegistrationExist = CWorkspaceFtaAppRegistration::DoesAppRegistrationExist(this, a2, v55);
  if ( DoesAppRegistrationExist < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v30 = 22;
    v31 = "DoesAppRegistrationExist failed";
    goto LABEL_35;
  }
  if ( v55[0] )
  {
    DoesAppRegistrationExist = -2147024713;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        v42,
        v41);
    }
    if ( (Microsoft_Windows_RemoteApp_and_Desktop_ConnectionsEnableBits & 1) != 0 )
    {
      v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 176);
      v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      McTemplateU0zzzq_EventWriteTransfer(v47, v46, v45, v44, v43, 183);
    }
    goto LABEL_112;
  }
  DoesAppRegistrationExist = RegCreateKeyTransactedW(
                               HKEY_CURRENT_USER,
                               L"Software\\RegisteredApplications",
                               0,
                               0,
                               0,
                               0x20006u,
                               0,
                               phkResult,
                               0,
                               a2,
                               0);
  if ( DoesAppRegistrationExist )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    if ( DoesAppRegistrationExist > 0 )
      v26 = (unsigned __int16)DoesAppRegistrationExist | 0x80070000;
    else
      v26 = DoesAppRegistrationExist;
    v27 = RdpWppGetCurrentThreadActivityIdPrefix();
    v28 = 24;
    goto LABEL_27;
  }
  *(_QWORD *)cbData = 0;
  DoesAppRegistrationExist = ULongLongMult(v60, v48, (unsigned __int64 *)cbData);
  if ( DoesAppRegistrationExist < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v30 = 25;
    v31 = "SizeTMult(Capabilities Key path length) failed";
    goto LABEL_35;
  }
  v49 = *(_QWORD *)cbData + 1LL;
  if ( (unsigned __int64)(*(_QWORD *)cbData + 1LL) >= *(_QWORD *)cbData )
  {
    cbData[0] = 0;
    DoesAppRegistrationExist = ULongLongToULong(v49, cbData);
    if ( DoesAppRegistrationExist >= 0 )
    {
      v51 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      v52 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      v36 = RegSetValueExW(phkResult[0], v51, 0, 1u, v52, cbData[0]);
      if ( !v36 )
        goto LABEL_112;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_108;
      }
      if ( v36 > 0 )
        v37 = (unsigned __int16)v36 | 0x80070000;
      else
        v37 = v36;
      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
      v39 = 28;
      goto LABEL_107;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v30 = 27;
    v31 = "SizeTToDWord(Capabilities Key path length) failed";
LABEL_35:
    samDesired[0] = DoesAppRegistrationExist;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
      v29,
      (__int64)v31,
      *(_QWORD *)samDesired);
    goto LABEL_112;
  }
  DoesAppRegistrationExist = -2147024362;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v50 = RdpWppGetCurrentThreadActivityIdPrefix();
    samDesired[0] = -2147024362;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
      v50,
      (__int64)"SizeTAdd(Capabilities Key path length) failed",
      *(_QWORD *)samDesired);
  }
LABEL_112:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult[0] )
  {
    RegCloseKey(phkResult[0]);
    phkResult[0] = 0;
  }
  std::wstring::~wstring(v59);
  return (unsigned int)DoesAppRegistrationExist;
}

```

## disassembly

```asm
0x180051968  mov     rax, rsp
0x18005196b  push    rbp
0x18005196c  push    rsi
0x18005196d  push    rdi
0x18005196e  push    r12
0x180051970  push    r13
0x180051972  push    r14
0x180051974  push    r15
0x180051976  lea     rbp, [rax-0E8h]
0x18005197d  sub     rsp, 1B0h
0x180051984  mov     [rbp+0E0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18005198c  mov     [rax+18h], rbx
0x180051990  mov     rax, cs:__security_cookie
0x180051997  xor     rax, rsp
0x18005199a  mov     [rbp+0E0h+var_38], rax
0x1800519a1  mov     r13b, r8b
0x1800519a4  mov     rbx, rdx
0x1800519a7  mov     r14, rcx
0x1800519aa  xor     r12d, r12d
0x1800519ad  mov     [rsp+1E0h+hKey], r12
0x1800519b2  mov     [rsp+1E0h+var_168], r12
0x1800519b7  lea     r15, WPP_GLOBAL_Control
0x1800519be  mov     rax, cs:WPP_GLOBAL_Control
0x1800519c5  cmp     rax, r15
0x1800519c8  jz      short loc_1800519FA
0x1800519ca  test    byte ptr [rax+1Ch], 1
0x1800519ce  jz      short loc_1800519FA
0x1800519d0  cmp     byte ptr [rax+19h], 4
0x1800519d4  jb      short loc_1800519FA
0x1800519d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800519db  lea     edx, [r12+0Dh]
0x1800519e0  mov     r9d, eax
0x1800519e3  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x1800519ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519f1  mov     rcx, [rcx+10h]
0x1800519f5  call    WPP_SF_D
0x1800519fa  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x180051a01  lea     rcx, [rbp+0E0h+var_58]
0x180051a08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180051a0d  nop
0x180051a0e  lea     rdi, SubStr; "\\"
0x180051a15  mov     r8, rdi
0x180051a18  mov     rdx, rax
0x180051a1b  lea     rcx, [rbp+0E0h+var_78]
0x180051a1f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a24  nop
0x180051a25  lea     r8, [r14+70h]
0x180051a29  mov     rdx, rax
0x180051a2c  lea     rcx, [rbp+0E0h+var_98]
0x180051a30  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180051a35  nop
0x180051a36  mov     r8, rdi
0x180051a39  mov     rdx, rax
0x180051a3c  lea     rcx, [rbp+0E0h+var_B8]
0x180051a40  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a45  nop
0x180051a46  lea     r8, aResources; "Resources"
0x180051a4d  mov     rdx, rax
0x180051a50  lea     rcx, [rbp+0E0h+var_D8]
0x180051a54  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a59  nop
0x180051a5a  mov     r8, rdi
0x180051a5d  mov     rdx, rax
0x180051a60  lea     rcx, [rbp+0E0h+var_F8]
0x180051a64  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a69  nop
0x180051a6a  lea     r8, [r14+30h]
0x180051a6e  mov     rdx, rax
0x180051a71  lea     rcx, [rbp+0E0h+var_118]
0x180051a75  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180051a7a  nop
0x180051a7b  mov     r8, rdi
0x180051a7e  mov     rdx, rax
0x180051a81  lea     rcx, [rbp+0E0h+var_138]
0x180051a85  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a8a  nop
0x180051a8b  lea     r8, aCapabilities; "Capabilities"
0x180051a92  mov     rdx, rax
0x180051a95  lea     rcx, [rbp+0E0h+var_158]
0x180051a99  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180051a9e  nop
0x180051a9f  lea     rcx, [rbp+0E0h+var_138]; void *
0x180051aa3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051aa8  nop
0x180051aa9  lea     rcx, [rbp+0E0h+var_118]; void *
0x180051aad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ab2  nop
0x180051ab3  lea     rcx, [rbp+0E0h+var_F8]; void *
0x180051ab7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051abc  nop
0x180051abd  lea     rcx, [rbp+0E0h+var_D8]; void *
0x180051ac1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ac6  nop
0x180051ac7  lea     rcx, [rbp+0E0h+var_B8]; void *
0x180051acb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ad0  nop
0x180051ad1  lea     rcx, [rbp+0E0h+var_98]; void *
0x180051ad5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ada  nop
0x180051adb  lea     rcx, [rbp+0E0h+var_78]; void *
0x180051adf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ae4  nop
0x180051ae5  lea     rcx, [rbp+0E0h+var_58]; void *
0x180051aec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051af1  mov     rdi, [rbp+0E0h+var_148]
0x180051af5  cmp     rdi, 103h
0x180051afc  jbe     loc_180051B98
0x180051b02  mov     esi, 8007007Ah
0x180051b07  mov     rax, cs:WPP_GLOBAL_Control
0x180051b0e  cmp     rax, r15
0x180051b11  jz      short loc_180051B47
0x180051b13  test    byte ptr [rax+1Ch], 1
0x180051b17  jz      short loc_180051B47
0x180051b19  cmp     byte ptr [rax+19h], 2
0x180051b1d  jb      short loc_180051B47
0x180051b1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051b24  mov     edx, 0Eh
0x180051b29  mov     [rsp+1E0h+dwOptions], edi
0x180051b2d  mov     r9d, eax
0x180051b30  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180051b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180051b3e  mov     rcx, [rcx+10h]
0x180051b42  call    WPP_SF_Dd
0x180051b47  test    cs:Microsoft_Windows_RemoteApp_and_Desktop_ConnectionsEnableBits, 1
0x180051b4e  jz      loc_180052224
0x180051b54  lea     rcx, [r14+0B0h]
0x180051b5b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051b60  mov     rdi, rax
0x180051b63  lea     rcx, [r14+90h]
0x180051b6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051b6f  mov     rbx, rax
0x180051b72  lea     rcx, [r14+50h]
0x180051b76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051b7b  mov     [rsp+1E0h+samDesired], 8007007Ah
0x180051b83  mov     qword ptr [rsp+1E0h+dwOptions], rdi
0x180051b88  mov     r9, rbx
0x180051b8b  mov     r8, rax
0x180051b8e  call    McTemplateU0zzzq_EventWriteTransfer
0x180051b93  jmp     loc_180052224
0x180051b98  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180051b9c  jnz     short loc_180051BEA
0x180051b9e  mov     rax, cs:WPP_GLOBAL_Control
0x180051ba5  cmp     rax, r15
0x180051ba8  jz      short loc_180051BE0
0x180051baa  test    byte ptr [rax+1Ch], 8
0x180051bae  jz      short loc_180051BE0
0x180051bb0  cmp     byte ptr [rax+19h], 2
0x180051bb4  jb      short loc_180051BE0
0x180051bb6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051bbb  lea     edx, [rbx+10h]
0x180051bbe  mov     [rsp+1E0h+dwOptions], 80070057h
0x180051bc6  mov     r9d, eax
0x180051bc9  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180051bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180051bd7  mov     rcx, [rcx+10h]
0x180051bdb  call    WPP_SF_Dd
0x180051be0  mov     esi, 80070057h
0x180051be5  jmp     loc_180052224
0x180051bea  lea     rcx, [rbp+0E0h+var_158]
0x180051bee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051bf3  mov     rdx, rax; lpSubKey
0x180051bf6  mov     [rsp+50h], r12; pExtendedParemeter
0x180051bfb  mov     [rsp+1E0h+hTransaction], rbx; hTransaction
0x180051c00  mov     [rsp+1E0h+lpdwDisposition], r12; lpdwDisposition
0x180051c05  lea     rax, [rsp+1E0h+hKey]
0x180051c0a  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180051c0f  mov     [rsp+1E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180051c14  mov     [rsp+1E0h+samDesired], 20006h; samDesired
0x180051c1c  mov     [rsp+1E0h+dwOptions], r12d; dwOptions
0x180051c21  xor     r9d, r9d; lpClass
0x180051c24  xor     r8d, r8d; Reserved
0x180051c27  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180051c2e  call    cs:__imp_RegCreateKeyTransactedW
0x180051c34  mov     esi, eax
0x180051c36  test    eax, eax
0x180051c38  jz      short loc_180051C9C
0x180051c3a  mov     ebx, 80070000h
0x180051c3f  mov     rax, cs:WPP_GLOBAL_Control
0x180051c46  cmp     rax, r15
0x180051c49  jz      short loc_180051C8C
0x180051c4b  test    byte ptr [rax+1Ch], 8
0x180051c4f  jz      short loc_180051C8C
0x180051c51  cmp     byte ptr [rax+19h], 2
0x180051c55  jb      short loc_180051C8C
0x180051c57  test    esi, esi
0x180051c59  jg      short loc_180051C5F
0x180051c5b  mov     edi, esi
0x180051c5d  jmp     short loc_180051C64
0x180051c5f  movzx   edi, si
0x180051c62  or      edi, ebx
0x180051c64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051c69  mov     edx, 10h
0x180051c6e  mov     [rsp+1E0h+dwOptions], edi
0x180051c72  mov     r9d, eax
0x180051c75  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180051c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051c83  mov     rcx, [rcx+10h]
0x180051c87  call    WPP_SF_Dd
0x180051c8c  test    esi, esi
0x180051c8e  jle     loc_180052224
0x180051c94  movzx   esi, si
0x180051c97  jmp     loc_180052222
0x180051c9c  mov     qword ptr [rsp+1E0h+cbData], r12
0x180051ca1  lea     r15, [r14+50h]
0x180051ca5  lea     r8, [rsp+1E0h+cbData]; unsigned __int64 *
0x180051caa  mov     rcx, [r15+10h]; unsigned __int64
0x180051cae  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180051cb3  mov     esi, eax
0x180051cb5  test    eax, eax
0x180051cb7  jns     short loc_180051D1D
0x180051cb9  mov     rax, cs:WPP_GLOBAL_Control
0x180051cc0  lea     rcx, WPP_GLOBAL_Control
0x180051cc7  cmp     rax, rcx
0x180051cca  jz      loc_180052224
0x180051cd0  test    byte ptr [rax+1Ch], 8
0x180051cd4  jz      loc_180052224
0x180051cda  cmp     byte ptr [rax+19h], 2
0x180051cde  jb      loc_180052224
0x180051ce4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051ce9  mov     edx, 11h
0x180051cee  lea     rcx, aSizetmultFrien; "SizeTMult(friendly name length) failed"
0x180051cf5  mov     [rsp+1E0h+samDesired], esi
0x180051cf9  mov     qword ptr [rsp+1E0h+dwOptions], rcx
0x180051cfe  mov     r9d, eax
0x180051d01  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180051d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d0f  mov     rcx, [rcx+10h]
0x180051d13  call    WPP_SF_DsD
0x180051d18  jmp     loc_180052224
0x180051d1d  mov     rax, qword ptr [rsp+1E0h+cbData]
0x180051d22  lea     rcx, [rax+1]; unsigned __int64
0x180051d26  cmp     rcx, rax
0x180051d29  jnb     short loc_180051D76
0x180051d2b  mov     esi, 80070216h
0x180051d30  mov     rax, cs:WPP_GLOBAL_Control
0x180051d37  lea     rcx, WPP_GLOBAL_Control
0x180051d3e  cmp     rax, rcx
0x180051d41  jz      loc_180052224
0x180051d47  test    byte ptr [rax+1Ch], 8
0x180051d4b  jz      loc_180052224
0x180051d51  cmp     byte ptr [rax+19h], 2
0x180051d55  jb      loc_180052224
0x180051d5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051d60  mov     edx, 12h
0x180051d65  mov     [rsp+1E0h+samDesired], 80070216h
0x180051d6d  lea     rcx, aSizetaddFriend; "SizeTAdd(friendly name length) failed"
0x180051d74  jmp     short loc_180051CF9
0x180051d76  mov     [rsp+1E0h+cbData], r12d
0x180051d7b  lea     rdx, [rsp+1E0h+cbData]; unsigned int *
0x180051d80  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180051d85  mov     esi, eax
0x180051d87  test    eax, eax
0x180051d89  jns     short loc_180051DCC
0x180051d8b  mov     rax, cs:WPP_GLOBAL_Control
0x180051d92  lea     rcx, WPP_GLOBAL_Control
0x180051d99  cmp     rax, rcx
0x180051d9c  jz      loc_180052224
0x180051da2  test    byte ptr [rax+1Ch], 8
0x180051da6  jz      loc_180052224
0x180051dac  cmp     byte ptr [rax+19h], 2
0x180051db0  jb      loc_180052224
0x180051db6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051dbb  mov     edx, 13h
0x180051dc0  lea     rcx, aSizettodwordFr; "SizeTToDWord(friendly name length) fail"...
0x180051dc7  jmp     loc_180051CF5
0x180051dcc  mov     rcx, r15
0x180051dcf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051dd4  mov     r12d, [rsp+1E0h+cbData]
0x180051dd9  mov     [rsp+1E0h+samDesired], r12d; cbData
0x180051dde  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x180051de3  mov     r9d, 1; dwType
0x180051de9  xor     r8d, r8d; Reserved
0x180051dec  lea     rdx, aApplicationnam; "ApplicationName"
0x180051df3  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180051df8  call    cs:__imp_RegSetValueExW
0x180051dfe  mov     edi, eax
0x180051e00  test    eax, eax
0x180051e02  jz      short loc_180051E53
0x180051e04  mov     ebx, 80070000h
0x180051e09  mov     rax, cs:WPP_GLOBAL_Control
0x180051e10  lea     rcx, WPP_GLOBAL_Control
0x180051e17  xor     r12d, r12d
0x180051e1a  cmp     rax, rcx
0x180051e1d  jz      loc_180052217
0x180051e23  test    byte ptr [rax+1Ch], 8
0x180051e27  jz      loc_180052217
0x180051e2d  cmp     byte ptr [rax+19h], 2
0x180051e31  jb      loc_180052217
0x180051e37  test    edi, edi
0x180051e39  jg      short loc_180051E3F
0x180051e3b  mov     esi, edi
0x180051e3d  jmp     short loc_180051E44
0x180051e3f  movzx   esi, di
0x180051e42  or      esi, ebx
0x180051e44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051e49  mov     edx, 14h
0x180051e4e  jmp     loc_1800521F9
0x180051e53  mov     rcx, r15
0x180051e56  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051e5b  mov     [rsp+1E0h+samDesired], r12d; cbData
  ... truncated ...
```
