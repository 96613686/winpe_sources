# StartList::LoadSettings(void)

- ea: `0x180023090`
- end: `0x18002350f`
- name: `?LoadSettings@StartList@@AEAAJXZ`
- size: `1151`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `8`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800185f8`
- `0x180018f40`
- `0x180019084`
- `0x18001d070`
- `0x180021610`
- `0x1800237e8`
- `0x1800241b0`
- `0x1800245c8`

## callees

- `0x180004310`
- `0x1800043d4`
- `0x18000539c`
- `0x1800055c0`
- `0x180014828`
- `0x180014b84`
- `0x180015780`
- `0x18001855c`
- `0x18001bc60`
- `0x180021750`
- `0x180021938`
- `0x180021a30`
- `0x1800224c8`
- `0x1800225c4`
- `0x180022724`
- `0x1800228b8`
- `0x1800229ec`
- `0x180023090`
- `0x1800295a0`
- `0x1800295f4`
- `0x18002d1ee`
- `0x18002d220`
- `0x18002d2b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233bc`
- `KERNEL32!OpenMutexW` at `0x1800233aa`
- `KERNEL32!OpenMutexW` at `0x1800233aa`

## string_xrefs

- `0x180023404`: `Configuration`
- `0x1800233d7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StartList::LoadSettings(StartList *this)
{
  StartList *v3; // rcx
  unsigned int v4; // r8d
  unsigned int IsInteractiveUser; // edi
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // r8d
  StartList *v9; // rcx
  unsigned int v10; // r8d
  int UserValue; // eax
  int v12; // edi
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  StartList *v16; // rcx
  __int64 v17; // r8
  HANDLE v18; // rax
  StartList *v19; // rcx
  unsigned int v20; // r8d
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v32[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v33[1024]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v34[1024]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v35[1024]; // [rsp+10A0h] [rbp+FA0h] BYREF

  if ( *((_DWORD *)this + 72) )
    return 0;
  *((_DWORD *)this + 72) = 1;
  if ( CATUtils::IsDesktopOOBERunning() )
  {
    memset_0(v34, 0, sizeof(v34));
    v27 = 0;
    v28 = 0;
    v29 = 0;
    StartList::GetSettingConfigurationValue(v3, v34, v4, (struct ATL::CRegKey *)&v27);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v26,
      v34);
    StartList::BuildConfigList(&v26, (char *)this + 144);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    ATL::CRegKey::Close((ATL::CRegKey *)&v27);
  }
  IsInteractiveUser = CATUtils::IsInteractiveUser();
  memset(v32, 0, 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  StartList::BuildSessionListStringBasedOnCurrentSessionContext(v6, IsInteractiveUser, &v26, v32);
  StartList::BuildConfigList(&v26, (char *)this + 48);
  memset_0(v33, 0, sizeof(v33));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  v7 = v26;
  if ( !IsInteractiveUser )
  {
    v18 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( !v18 )
    {
      StartList::GetSessionValue(v19, v33, v20, (struct ATL::CRegKey *)v32, 1);
      v22 = -1;
      do
        ++v22;
      while ( v33[v22] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v22);
      if ( *(_DWORD *)(v24 - 16) )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v24, L",", 1);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v24, v7, *(unsigned int *)(v7 - 16));
      goto LABEL_36;
    }
    CloseHandle(v18);
    v27 = 0;
    v28 = 0;
    v29 = 0;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)&v27,
                          HKEY_LOCAL_MACHINE,
                          StartList::_oobeAccessibilityKeyString,
                          0x20019u) )
    {
      v25[0] = 1024;
      if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v27, L"Configuration", v33, v25) )
        v33[0] = 0;
    }
    v21 = -1;
    do
      ++v21;
    while ( v33[v21] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v21);
LABEL_30:
    ATL::CRegKey::Close((ATL::CRegKey *)&v27);
LABEL_36:
    StartList::BuildConfigList(&v24, this);
    v12 = 0;
    goto LABEL_37;
  }
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v34, 0, sizeof(v34));
  memset_0(v35, 0, sizeof(v35));
  StartList::GetTempValue(this, v34, v8, v35, v23, (struct ATL::CRegKey *)&v27);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v30,
    v34);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v25,
    v35);
  StartList::BuildConfigList(&v30, (char *)this + 192);
  StartList::BuildConfigList(v25, (char *)this + 240);
  memset(v31, 0, sizeof(v31));
  UserValue = StartList::GetUserValue(v9, v33, v10, (struct ATL::CRegKey *)v31);
  v12 = UserValue;
  if ( UserValue >= 0 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v33[v17] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, v33, v17);
LABEL_22:
    StartList::ClearSessionSecureConfiguration(v16, (struct ATL::CRegKey *)v32);
    ATL::CRegKey::Close((ATL::CRegKey *)v31);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v25 - 24LL));
    ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
    goto LABEL_30;
  }
  v13 = UserValue & 0x1FFF0000;
  if ( (_DWORD)v13 == 458752 )
    UserValue = (unsigned __int16)UserValue;
  if ( UserValue == 2 )
  {
    v12 = StartList::HandleFirstTime(v13, (LPCWSTR *)this + 6, &v24, (ATL::CRegKey *)v31);
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_18;
      v15 = 21;
      goto LABEL_17;
    }
    goto LABEL_22;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_18;
  v15 = 20;
LABEL_17:
  WPP_SF_d(v14[2], v15, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, (unsigned int)v12);
LABEL_18:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v25 - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)&v27);
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180023090  mov     [rsp-8+arg_8], rbx
0x180023095  mov     [rsp-8+arg_10], rsi
0x18002309a  push    rbp
0x18002309b  push    rdi
0x18002309c  push    r13
0x18002309e  push    r14
0x1800230a0  push    r15
0x1800230a2  lea     rbp, [rsp-17B0h]
0x1800230aa  mov     eax, 18B0h
0x1800230af  call    _alloca_probe
0x1800230b4  sub     rsp, rax
0x1800230b7  mov     rax, cs:__security_cookie
0x1800230be  xor     rax, rsp
0x1800230c1  mov     [rbp+17D0h+var_30], rax
0x1800230c8  mov     rsi, rcx
0x1800230cb  xor     r15d, r15d
0x1800230ce  cmp     [rcx+120h], r15d
0x1800230d5  jz      short loc_1800230DE
0x1800230d7  xor     eax, eax
0x1800230d9  jmp     loc_1800234E4
0x1800230de  mov     dword ptr [rcx+120h], 1
0x1800230e8  call    ?IsDesktopOOBERunning@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBERunning(void)
0x1800230ed  mov     r13d, 800h
0x1800230f3  test    al, al
0x1800230f5  jz      short loc_180023165
0x1800230f7  mov     r8d, r13d; Size
0x1800230fa  xor     edx, edx; Val
0x1800230fc  lea     rcx, [rbp+17D0h+var_1030]; void *
0x180023103  call    memset_0
0x180023108  mov     [rsp+18D0h+var_1888], r15
0x18002310d  mov     [rsp+18D0h+var_1880], r15
0x180023112  mov     [rsp+18D0h+var_1878], r15
0x180023117  lea     r9, [rsp+18D0h+var_1888]; struct ATL::CRegKey *
0x18002311c  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x180023123  call    ?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)
0x180023128  lea     rdx, [rbp+17D0h+var_1030]
0x18002312f  lea     rcx, [rsp+18D0h+var_1890]
0x180023134  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180023139  nop
0x18002313a  lea     rdx, [rsi+90h]
0x180023141  lea     rcx, [rsp+18D0h+var_1890]
0x180023146  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18002314b  nop
0x18002314c  mov     rcx, [rsp+18D0h+var_1890]
0x180023151  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023155  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002315a  nop
0x18002315b  lea     rcx, [rsp+18D0h+var_1888]; this
0x180023160  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180023165  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x18002316a  mov     edi, eax
0x18002316c  mov     [rbp+17D0h+var_1850], r15
0x180023170  mov     [rbp+17D0h+var_1848], r15
0x180023174  mov     [rbp+17D0h+var_1840], r15
0x180023178  lea     rcx, [rsp+18D0h+var_1890]
0x18002317d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180023182  nop
0x180023183  lea     r9, [rbp+17D0h+var_1850]
0x180023187  lea     r8, [rsp+18D0h+var_1890]
0x18002318c  mov     edx, edi
0x18002318e  call    ?BuildSessionListStringBasedOnCurrentSessionContext@StartList@@AEBAXHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@@Z; StartList::BuildSessionListStringBasedOnCurrentSessionContext(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x180023193  lea     rdx, [rsi+30h]
0x180023197  lea     rcx, [rsp+18D0h+var_1890]
0x18002319c  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x1800231a1  mov     r8, r13; Size
0x1800231a4  xor     edx, edx; Val
0x1800231a6  lea     rcx, [rbp+17D0h+var_1830]; void *
0x1800231aa  call    memset_0
0x1800231af  lea     rcx, [rsp+18D0h+var_18A0]
0x1800231b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800231b9  nop
0x1800231ba  mov     rbx, [rsp+18D0h+var_1890]
0x1800231bf  test    edi, edi
0x1800231c1  jz      loc_18002339C
0x1800231c7  mov     [rsp+18D0h+var_1888], r15
0x1800231cc  mov     [rsp+18D0h+var_1880], r15
0x1800231d1  mov     [rsp+18D0h+var_1878], r15
0x1800231d6  mov     r8, r13; Size
0x1800231d9  xor     edx, edx; Val
0x1800231db  lea     rcx, [rbp+17D0h+var_1030]; void *
0x1800231e2  call    memset_0
0x1800231e7  mov     r8, r13; Size
0x1800231ea  xor     edx, edx; Val
0x1800231ec  lea     rcx, [rbp+17D0h+var_830]; void *
0x1800231f3  call    memset_0
0x1800231f8  lea     rax, [rsp+18D0h+var_1888]
0x1800231fd  mov     [rsp+18D0h+var_18A8], rax; struct ATL::CRegKey *
0x180023202  lea     r9, [rbp+17D0h+var_830]; unsigned __int16 *
0x180023209  lea     rdx, [rbp+17D0h+var_1030]; unsigned __int16 *
0x180023210  mov     rcx, rsi; this
0x180023213  call    ?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z; StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)
0x180023218  lea     rdx, [rbp+17D0h+var_1030]
0x18002321f  lea     rcx, [rsp+18D0h+var_1870]
0x180023224  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180023229  nop
0x18002322a  lea     rdx, [rbp+17D0h+var_830]
0x180023231  lea     rcx, [rsp+18D0h+var_1898]
0x180023236  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002323b  nop
0x18002323c  lea     rdx, [rsi+0C0h]
0x180023243  lea     rcx, [rsp+18D0h+var_1870]
0x180023248  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18002324d  lea     rdx, [rsi+0F0h]
0x180023254  lea     rcx, [rsp+18D0h+var_1898]
0x180023259  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18002325e  mov     [rsp+18D0h+var_1868], r15
0x180023263  mov     [rsp+18D0h+var_1860], r15
0x180023268  mov     [rsp+18D0h+var_1858], r15
0x18002326d  lea     r9, [rsp+18D0h+var_1868]; struct ATL::CRegKey *
0x180023272  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x180023276  call    ?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)
0x18002327b  mov     edi, eax
0x18002327d  test    eax, eax
0x18002327f  jns     loc_180023344
0x180023285  mov     ecx, eax
0x180023287  and     ecx, 1FFF0000h
0x18002328d  cmp     ecx, 70000h
0x180023293  jnz     short loc_180023298
0x180023295  movzx   eax, di
0x180023298  cmp     eax, 2
0x18002329b  jz      short loc_1800232BD
0x18002329d  lea     rax, WPP_GLOBAL_Control
0x1800232a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232ab  cmp     rcx, rax
0x1800232ae  jz      short loc_18002330C
0x1800232b0  test    byte ptr [rcx+1Ch], 8
0x1800232b4  jz      short loc_18002330C
0x1800232b6  mov     edx, 14h
0x1800232bb  jmp     short loc_1800232F8
0x1800232bd  lea     r9, [rsp+18D0h+var_1868]
0x1800232c2  lea     r8, [rsp+18D0h+var_18A0]
0x1800232c7  lea     rdx, [rsi+30h]
0x1800232cb  call    ?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z; StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x1800232d0  mov     edi, eax
0x1800232d2  test    eax, eax
0x1800232d4  jns     loc_180023364
0x1800232da  lea     rax, WPP_GLOBAL_Control
0x1800232e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232e8  cmp     rcx, rax
0x1800232eb  jz      short loc_18002330C
0x1800232ed  test    byte ptr [rcx+1Ch], 8
0x1800232f1  jz      short loc_18002330C
0x1800232f3  mov     edx, 15h
0x1800232f8  mov     r9d, edi
0x1800232fb  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x180023302  mov     rcx, [rcx+10h]
0x180023306  call    WPP_SF_d
0x18002330b  nop
0x18002330c  lea     rcx, [rsp+18D0h+var_1868]; this
0x180023311  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180023316  nop
0x180023317  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x18002331c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023320  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023325  nop
0x180023326  mov     rcx, [rsp+18D0h+var_1870]
0x18002332b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002332f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023334  nop
0x180023335  lea     rcx, [rsp+18D0h+var_1888]; this
0x18002333a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002333f  jmp     loc_1800234C0
0x180023344  lea     rax, [rbp+17D0h+var_1830]
0x180023348  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002334c  inc     r8
0x18002334f  cmp     [rax+r8*2], r15w
0x180023354  jnz     short loc_18002334C
0x180023356  lea     rdx, [rbp+17D0h+var_1830]
0x18002335a  lea     rcx, [rsp+18D0h+var_18A0]
0x18002335f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180023364  lea     rdx, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x180023368  call    ?ClearSessionSecureConfiguration@StartList@@AEBAXAEAVCRegKey@ATL@@@Z; StartList::ClearSessionSecureConfiguration(ATL::CRegKey &)
0x18002336d  nop
0x18002336e  lea     rcx, [rsp+18D0h+var_1868]; this
0x180023373  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180023378  nop
0x180023379  mov     rcx, qword ptr [rsp+18D0h+var_1898]
0x18002337e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023382  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023387  nop
0x180023388  mov     rcx, [rsp+18D0h+var_1870]
0x18002338d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023391  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023396  nop
0x180023397  jmp     loc_18002343F
0x18002339c  lea     r8, Name; "Global\\Windows.Machine.OOBE"
0x1800233a3  xor     edx, edx; bInheritHandle
0x1800233a5  mov     ecx, 100000h; dwDesiredAccess
0x1800233aa  call    cs:__imp_OpenMutexW
0x1800233b0  test    rax, rax
0x1800233b3  jz      loc_18002344B
0x1800233b9  mov     rcx, rax; hObject
0x1800233bc  call    cs:__imp_CloseHandle
0x1800233c2  mov     [rsp+18D0h+var_1888], r15
0x1800233c7  mov     [rsp+18D0h+var_1880], r15
0x1800233cc  mov     [rsp+18D0h+var_1878], r15
0x1800233d1  mov     r9d, 20019h; unsigned int
0x1800233d7  lea     r8, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800233de  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800233e5  lea     rcx, [rsp+18D0h+var_1888]; this
0x1800233ea  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800233ef  test    eax, eax
0x1800233f1  jnz     short loc_18002341E
0x1800233f3  mov     [rsp+18D0h+var_1898], 400h
0x1800233fb  lea     r9, [rsp+18D0h+var_1898]; unsigned int *
0x180023400  lea     r8, [rbp+17D0h+var_1830]; unsigned __int16 *
0x180023404  lea     rdx, aConfiguration; "Configuration"
0x18002340b  lea     rcx, [rsp+18D0h+var_1888]; this
0x180023410  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180023415  test    eax, eax
0x180023417  jz      short loc_18002341E
0x180023419  mov     [rbp+17D0h+var_1830], r15w
0x18002341e  lea     rax, [rbp+17D0h+var_1830]
0x180023422  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023426  inc     r8
0x180023429  cmp     [rax+r8*2], r15w
0x18002342e  jnz     short loc_180023426
0x180023430  lea     rdx, [rbp+17D0h+var_1830]
0x180023434  lea     rcx, [rsp+18D0h+var_18A0]
0x180023439  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002343e  nop
0x18002343f  lea     rcx, [rsp+18D0h+var_1888]; this
0x180023444  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180023449  jmp     short loc_1800234B0
0x18002344b  mov     [rsp+18D0h+var_18B0], 1; bool
0x180023450  lea     r9, [rbp+17D0h+var_1850]; struct ATL::CRegKey *
0x180023454  lea     rdx, [rbp+17D0h+var_1830]; unsigned __int16 *
0x180023458  call    ?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z; StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)
0x18002345d  lea     rax, [rbp+17D0h+var_1830]
0x180023461  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023465  inc     r8
0x180023468  cmp     [rax+r8*2], r15w
0x18002346d  jnz     short loc_180023465
0x18002346f  lea     rdx, [rbp+17D0h+var_1830]
0x180023473  lea     rcx, [rsp+18D0h+var_18A0]
0x180023478  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002347d  mov     rax, [rsp+18D0h+var_18A0]
0x180023482  cmp     [rax-10h], r15d
0x180023486  jz      short loc_18002349F
0x180023488  mov     r8d, 1
0x18002348e  lea     rdx, asc_18003455C; ","
0x180023495  lea     rcx, [rsp+18D0h+var_18A0]
0x18002349a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002349f  mov     r8d, [rbx-10h]
0x1800234a3  mov     rdx, rbx
0x1800234a6  lea     rcx, [rsp+18D0h+var_18A0]
0x1800234ab  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800234b0  mov     rdx, rsi
0x1800234b3  lea     rcx, [rsp+18D0h+var_18A0]
0x1800234b8  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x1800234bd  mov     edi, r15d
0x1800234c0  mov     rcx, [rsp+18D0h+var_18A0]
0x1800234c5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800234c9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800234ce  nop
0x1800234cf  lea     rcx, [rbx-18h]; this
0x1800234d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800234d8  nop
0x1800234d9  lea     rcx, [rbp+17D0h+var_1850]; this
0x1800234dd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800234e2  mov     eax, edi
0x1800234e4  mov     rcx, [rbp+17D0h+var_30]
0x1800234eb  xor     rcx, rsp; StackCookie
0x1800234ee  call    __security_check_cookie
0x1800234f3  lea     r11, [rsp+18D0h+var_20]
0x1800234fb  mov     rbx, [r11+38h]
0x1800234ff  mov     rsi, [r11+40h]
0x180023503  mov     rsp, r11
0x180023506  pop     r15
0x180023508  pop     r14
0x18002350a  pop     r13
0x18002350c  pop     rdi
0x18002350d  pop     rbp
0x18002350e  retn
```
