# Accommodation::Open(ushort const *)

- ea: `0x1400116c4`
- end: `0x1400119d2`
- name: `?Open@Accommodation@@SAPEAV1@PEBG@Z`
- size: `782`
- prototype: `struct Accommodation *__fastcall(const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400048b8`
- `0x140009264`
- `0x14000b250`
- `0x14000bf04`
- `0x14000c8b4`
- `0x14000e538`
- `0x140010244`
- `0x140010714`
- `0x140010960`

## callees

- `0x1400029b4`
- `0x140004890`
- `0x140007560`
- `0x14000cb50`
- `0x14000d118`
- `0x140011204`
- `0x1400116c4`
- `0x1400119d8`
- `0x140011a40`
- `0x140015ace`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140011785`
- `ADVAPI32!RegOpenKeyExW` at `0x140011785`
- `ADVAPI32!RegCloseKey` at `0x1400117dd`
- `ADVAPI32!RegCloseKey` at `0x140011952`
- `ADVAPI32!RegCloseKey` at `0x1400117dd`
- `ADVAPI32!RegCloseKey` at `0x140011952`
- `msvcrt!_wcslwr_s` at `0x140011924`
- `msvcrt!_wcslwr_s` at `0x140011924`

## string_xrefs

- `0x140011707`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`
- `0x1400118a8`: `CopySettingsToLockedDesktop`
- `0x1400118bd`: `SecureDesktopAccommodation`

## pseudocode

```c
struct Accommodation *__fastcall Accommodation::Open(const unsigned __int16 *a1)
{
  __int64 v2; // r8
  LPCWSTR v3; // rbx
  HKEY v4; // r15
  Accommodation *v5; // rax
  HKEY v6; // r14
  volatile signed __int32 *v7; // rdx
  wchar_t **v8; // r15
  const wchar_t *v9; // r13
  __int64 v10; // rsi
  HKEY v12[3]; // [rsp+30h] [rbp-48h] BYREF
  ATL::CAtlException *v13; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  lpSubKey = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      &lpSubKey,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\",
      63);
    if ( a1 )
    {
      v2 = -1;
      do
        ++v2;
      while ( a1[v2] );
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a1);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v13) )
    {
      v7 = (volatile signed __int32 *)(lpSubKey - 12);
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_140011983);
      goto LABEL_25;
    }
  }
  memset(v12, 0, sizeof(v12));
  hKey = 0;
  v3 = lpSubKey;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
LABEL_13:
    v7 = (volatile signed __int32 *)(v3 - 12);
LABEL_25:
    if ( _InterlockedExchangeAdd(v7 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
    return 0;
  }
  v4 = hKey;
  v12[0] = hKey;
  v5 = (Accommodation *)operator new(0x58u);
  hKey = (HKEY)v5;
  if ( v5 )
    v6 = (HKEY)Accommodation::Accommodation(v5, a1);
  else
    v6 = 0;
  hKey = v6;
  if ( !v6 )
  {
    if ( v4 )
      RegCloseKey(v4);
    goto LABEL_13;
  }
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"ApplicationName");
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"Description");
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"StartExe");
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"StartParams");
  v8 = (wchar_t **)(v6 + 10);
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"SimpleProfile");
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"Profile");
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"ATExe");
  Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v12, L"TerminateOnDesktopSwitch", (unsigned int *)v6 + 16, 1u);
  Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v12, L"CopySettingsToLockedDesktop", (unsigned int *)v6 + 17, 0);
  Accommodation::QueryStringValue((ATL::CRegKey *)v12, L"SecureDesktopAccommodation");
  Accommodation::QueryDWORDValue((struct ATL::CRegKey *)v12, L"PassiveAutoStartBehavior", (unsigned int *)v6 + 20, 0);
  v9 = (const wchar_t *)*((_QWORD *)v6 + 5);
  if ( wcscmp_0(v9, L"SystemSetting") )
  {
    v10 = *((int *)v9 - 4);
    if ( (int)((*((_DWORD *)v9 - 3) - v10) | (1 - *((_DWORD *)v9 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v6 + 10, (unsigned int)v10);
    _wcslwr_s(*v8, (int)v10 + 1);
    if ( (int)v10 < 0 || (int)v10 > *((_DWORD *)*v8 - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *((_DWORD *)*v8 - 4) = v10;
    (*v8)[v10] = 0;
  }
  if ( v12[0] )
    RegCloseKey(v12[0]);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 - 3) + 8LL))(*((_QWORD *)v3 - 3));
  return (struct Accommodation *)v6;
}

```

## disassembly

```asm
0x1400116c4  mov     [rsp+arg_0], rbx
0x1400116c9  mov     [rsp+arg_18], rsi
0x1400116ce  push    rdi
0x1400116cf  push    r12
0x1400116d1  push    r13
0x1400116d3  push    r14
0x1400116d5  push    r15
0x1400116d7  sub     rsp, 50h
0x1400116db  mov     rsi, rcx
0x1400116de  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400116e5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400116ec  mov     rax, [rax+18h]
0x1400116f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116f5  add     rax, 18h
0x1400116f9  mov     [rsp+78h+lpSubKey], rax
0x140011701  mov     r8d, 3Fh ; '?'
0x140011707  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001170e  lea     rcx, [rsp+78h+lpSubKey]
0x140011716  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001171b  xor     edi, edi
0x14001171d  test    rsi, rsi
0x140011720  jnz     short loc_140011727
0x140011722  mov     r8d, edi
0x140011725  jmp     short loc_140011735
0x140011727  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001172b  inc     r8
0x14001172e  cmp     [rsi+r8*2], di
0x140011733  jnz     short loc_14001172B
0x140011735  mov     rdx, rsi
0x140011738  lea     rcx, [rsp+78h+lpSubKey]
0x140011740  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140011745  nop
0x140011746  mov     [rsp+78h+var_48], rdi
0x14001174b  mov     [rsp+78h+var_40], rdi
0x140011750  mov     [rsp+78h+var_38], rdi
0x140011755  mov     [rsp+78h+hKey], rdi
0x14001175d  lea     rax, [rsp+78h+hKey]
0x140011765  mov     [rsp+78h+phkResult], rax; phkResult
0x14001176a  mov     r9d, 20019h; samDesired
0x140011770  xor     r8d, r8d; ulOptions
0x140011773  mov     rbx, [rsp+78h+lpSubKey]
0x14001177b  mov     rdx, rbx; lpSubKey
0x14001177e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011785  call    cs:__imp_RegOpenKeyExW
0x14001178b  test    eax, eax
0x14001178d  jnz     loc_14001197E
0x140011793  mov     r15, [rsp+78h+hKey]
0x14001179b  mov     [rsp+78h+var_48], r15
0x1400117a0  lea     ecx, [rax+58h]; Size
0x1400117a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400117a8  mov     [rsp+78h+hKey], rax
0x1400117b0  test    rax, rax
0x1400117b3  jz      short loc_1400117C5
0x1400117b5  mov     rdx, rsi; unsigned __int16 *
0x1400117b8  mov     rcx, rax; this
0x1400117bb  call    ??0Accommodation@@AEAA@PEBG@Z; Accommodation::Accommodation(ushort const *)
0x1400117c0  mov     r14, rax
0x1400117c3  jmp     short loc_1400117C8
0x1400117c5  mov     r14, rdi
0x1400117c8  mov     [rsp+78h+hKey], r14
0x1400117d0  test    r14, r14
0x1400117d3  jnz     short loc_1400117ED
0x1400117d5  test    r15, r15
0x1400117d8  jz      short loc_1400117E4
0x1400117da  mov     rcx, r15; hKey
0x1400117dd  call    cs:__imp_RegCloseKey
0x1400117e3  nop
0x1400117e4  lea     rdx, [rbx-18h]
0x1400117e8  jmp     loc_14001198F
0x1400117ed  lea     r8, [r14+8]
0x1400117f1  lea     rdx, aApplicationnam; "ApplicationName"
0x1400117f8  lea     rcx, [rsp+78h+var_48]; this
0x1400117fd  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140011802  lea     r8, [r14+10h]
0x140011806  lea     rdx, aDescription; "Description"
0x14001180d  lea     rcx, [rsp+78h+var_48]; this
0x140011812  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140011817  lea     r8, [r14+18h]
0x14001181b  lea     rdx, aStartexe; "StartExe"
0x140011822  lea     rcx, [rsp+78h+var_48]; this
0x140011827  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001182c  lea     r8, [r14+20h]
0x140011830  lea     rdx, aStartparams; "StartParams"
0x140011837  lea     rcx, [rsp+78h+var_48]; this
0x14001183c  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140011841  lea     r15, [r14+28h]
0x140011845  mov     r8, r15
0x140011848  lea     rdx, aSimpleprofile; "SimpleProfile"
0x14001184f  lea     rcx, [rsp+78h+var_48]; this
0x140011854  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140011859  lea     r8, [r14+30h]
0x14001185d  lea     rdx, aProfile; "Profile"
0x140011864  lea     rcx, [rsp+78h+var_48]; this
0x140011869  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001186e  lea     r8, [r14+38h]
0x140011872  lea     rdx, aAtexe; "ATExe"
0x140011879  lea     rcx, [rsp+78h+var_48]; this
0x14001187e  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140011883  lea     r8, [r14+40h]; unsigned int *
0x140011887  mov     r12d, 1
0x14001188d  mov     r9d, r12d; unsigned int
0x140011890  lea     rdx, aTerminateondes; "TerminateOnDesktopSwitch"
0x140011897  lea     rcx, [rsp+78h+var_48]; struct ATL::CRegKey *
0x14001189c  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x1400118a1  lea     r8, [r14+44h]; unsigned int *
0x1400118a5  xor     r9d, r9d; unsigned int
0x1400118a8  lea     rdx, aCopysettingsto; "CopySettingsToLockedDesktop"
0x1400118af  lea     rcx, [rsp+78h+var_48]; struct ATL::CRegKey *
0x1400118b4  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x1400118b9  lea     r8, [r14+48h]
0x1400118bd  lea     rdx, aSecuredesktopa; "SecureDesktopAccommodation"
0x1400118c4  lea     rcx, [rsp+78h+var_48]; this
0x1400118c9  call    ?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400118ce  lea     r8, [r14+50h]; unsigned int *
0x1400118d2  xor     r9d, r9d; unsigned int
0x1400118d5  lea     rdx, aPassiveautosta; "PassiveAutoStartBehavior"
0x1400118dc  lea     rcx, [rsp+78h+var_48]; struct ATL::CRegKey *
0x1400118e1  call    ?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z; Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)
0x1400118e6  nop
0x1400118e7  mov     r13, [r15]
0x1400118ea  lea     rdx, aSystemsetting; "SystemSetting"
0x1400118f1  mov     rcx, r13; String1
0x1400118f4  call    wcscmp_0
0x1400118f9  nop
0x1400118fa  test    eax, eax
0x1400118fc  jz      short loc_140011948
0x1400118fe  movsxd  rsi, dword ptr [r13-10h]
0x140011902  sub     r12d, [r13-8]
0x140011906  mov     eax, [r13-0Ch]
0x14001190a  sub     eax, esi
0x14001190c  or      r12d, eax
0x14001190f  jge     short loc_14001191B
0x140011911  mov     edx, esi
0x140011913  mov     rcx, r15
0x140011916  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14001191b  lea     eax, [rsi+1]
0x14001191e  movsxd  rdx, eax; SizeInWords
0x140011921  mov     rcx, [r15]; String
0x140011924  call    cs:__imp__wcslwr_s
0x14001192a  test    esi, esi
0x14001192c  js      loc_1400119C7
0x140011932  mov     rax, [r15]
0x140011935  cmp     esi, [rax-0Ch]
0x140011938  jg      loc_1400119C7
0x14001193e  mov     [rax-10h], esi
0x140011941  mov     rax, [r15]
0x140011944  mov     [rax+rsi*2], di
0x140011948  mov     rcx, [rsp+78h+var_48]; hKey
0x14001194d  test    rcx, rcx
0x140011950  jz      short loc_140011959
0x140011952  call    cs:__imp_RegCloseKey
0x140011958  nop
0x140011959  lea     rdx, [rbx-18h]
0x14001195d  or      eax, 0FFFFFFFFh
0x140011960  lock xadd [rdx+10h], eax
0x140011965  sub     eax, 1
0x140011968  jg      short loc_140011979
0x14001196a  mov     rcx, [rdx]
0x14001196d  mov     rax, [rcx]
0x140011970  mov     rax, [rax+8]
0x140011974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011979  mov     rax, r14
0x14001197c  jmp     short loc_1400119AD
0x14001197e  jmp     loc_1400117E4
0x140011983  mov     rdx, [rsp+78h+lpSubKey]
0x14001198b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001198f  or      eax, 0FFFFFFFFh
0x140011992  lock xadd [rdx+10h], eax
0x140011997  sub     eax, 1
0x14001199a  jg      short loc_1400119AB
0x14001199c  mov     rcx, [rdx]
0x14001199f  mov     rax, [rcx]
0x1400119a2  mov     rax, [rax+8]
0x1400119a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400119ab  xor     eax, eax
0x1400119ad  lea     r11, [rsp+78h+var_28]
0x1400119b2  mov     rbx, [r11+30h]
0x1400119b6  mov     rsi, [r11+48h]
0x1400119ba  mov     rsp, r11
0x1400119bd  pop     r15
0x1400119bf  pop     r14
0x1400119c1  pop     r13
0x1400119c3  pop     r12
0x1400119c5  pop     rdi
0x1400119c6  retn
0x1400119c7  mov     ecx, 80070057h; int
0x1400119cc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
