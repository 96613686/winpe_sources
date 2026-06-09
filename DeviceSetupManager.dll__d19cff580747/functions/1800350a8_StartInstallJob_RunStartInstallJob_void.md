# StartInstallJob::_RunStartInstallJob(void)

- ea: `0x1800350a8`
- end: `0x180035727`
- name: `?_RunStartInstallJob@StartInstallJob@@AEAAJXZ`
- size: `1663`
- prototype: `__int64 __fastcall(StartInstallJob *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180034500`

## callees

- `0x180005100`
- `0x180005120`
- `0x18000a094`
- `0x18000a330`
- `0x18000b740`
- `0x18000d2e0`
- `0x180010cec`
- `0x180011fdc`
- `0x1800128ac`
- `0x18001370c`
- `0x180018678`
- `0x18001aa34`
- `0x18001af70`
- `0x1800345c8`
- `0x1800350a8`
- `0x180035898`
- `0x18003f270`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180035538`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180035538`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800352c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800352c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800354c9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003554e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003554e`

## string_xrefs

- `0x180035715`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StartInstallJob::_RunStartInstallJob(StartInstallJob *this)
{
  char *v2; // rbx
  const unsigned __int16 *v3; // rcx
  bool v4; // r13
  __int64 v5; // rax
  char *v6; // rdx
  __int64 v7; // rdi
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // rcx
  const unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // r8
  HRESULT v14; // r9d
  const char *v15; // r9
  void *v16; // rax
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rax
  char *v20; // rdx
  int v21; // eax
  char v22; // r9
  __int64 v23; // rax
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rax
  char *v26; // rdx
  int v27; // edi
  __int64 v28; // rax
  char *v29; // rdx
  const unsigned __int16 *v30; // rcx
  const unsigned __int16 *v31; // rcx
  const DEVPROPKEY *v32; // rdx
  const struct _DEVPROPKEY *v33; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  int v36; // [rsp+28h] [rbp-91h]
  int v37; // [rsp+40h] [rbp-79h] BYREF
  LPVOID v38; // [rsp+48h] [rbp-71h] BYREF
  void *v39; // [rsp+50h] [rbp-69h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp-61h] BYREF
  __int64 v41; // [rsp+60h] [rbp-59h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-51h]
  PROPVARIANT v43[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v44; // [rsp+80h] [rbp-39h]
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v46; // [rsp+98h] [rbp-21h]
  PROPVARIANT v47[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-9h]
  __int128 v49; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v50; // [rsp+C8h] [rbp+Fh]
  _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v37 = 0;
  v2 = (char *)this + 40;
  if ( *((_QWORD *)this + 8) <= 7u )
    v3 = (const unsigned __int16 *)((char *)this + 40);
  else
    v3 = *(const unsigned __int16 **)v2;
  if ( GetContainerUINT(v3, &DEVPKEY_DeviceSetup_DeviceState) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(char **)v2;
      WPP_SF__guid_LS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
        (_DWORD)this + 8,
        *((_DWORD *)this + 7),
        (__int64)v2);
    }
    return 0;
  }
  v4 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v5 = (__int64)v2;
    else
      v5 = *(_QWORD *)v2;
    WPP_SF_d_guid_LS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
      1,
      (__int64)this + 8,
      *((_DWORD *)this + 7),
      v5);
  }
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v6 = v2;
  else
    v6 = *(char **)v2;
  v37 = 1;
  v36 = 4;
  SetDeviceObjectProperty(2, v6, &DEVPKEY_DeviceSetup_DeviceState);
  Job::GetOwningContainer(this, &v41);
  v7 = v41;
  if ( *(_QWORD *)(v41 + 64) )
  {
    v8 = (const unsigned __int16 *)(v41 + 48);
    if ( *(_QWORD *)(v41 + 72) > 7u )
      v8 = *(const unsigned __int16 **)v8;
    if ( v8 )
    {
      if ( *((_QWORD *)v2 + 3) <= 7u )
        v9 = (const unsigned __int16 *)v2;
      else
        v9 = *(const unsigned __int16 **)v2;
      SetContainerStringProperty(v9, &DEVPKEY_NAME, v8);
      v7 = v41;
    }
  }
  if ( *(_QWORD *)(v7 + 96) )
  {
    v10 = (const unsigned __int16 *)(v7 + 80);
    if ( *((_QWORD *)v10 + 3) > 7u )
      v10 = *(const unsigned __int16 **)v10;
    if ( v10 )
    {
      if ( *((_QWORD *)v2 + 3) <= 7u )
        v11 = (const unsigned __int16 *)v2;
      else
        v11 = *(const unsigned __int16 **)v2;
      SetContainerStringProperty(v11, &DEVPKEY_DeviceContainer_PrimaryCategory, v10);
      v38 = 0;
      Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v38);
      v12 = CoCreateInstance(
              &GUID_d2e86c4f_ea06_4a89_bf00_b49706db46e6,
              0,
              0x17u,
              &GUID_03e05342_07f2_4dee_98f7_c4ec68370cf4,
              &v38);
      v14 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( *((_QWORD *)v2 + 3) <= 7u )
            v25 = (__int64)v2;
          else
            v25 = *(_QWORD *)v2;
          WPP_SF_d_guid_LS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
            v14,
            (__int64)this + 8,
            *((_DWORD *)this + 7),
            v25);
        }
        goto LABEL_74;
      }
      v49 = 0;
      v50 = 0;
      *(_OWORD *)v43 = 0;
      v44 = 0;
      LOWORD(v43[0]) = 31;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v39,
        v10,
        v13,
        (unsigned int)v12);
      v37 = 2;
      v16 = v39;
      if ( !v39 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v15);
      v39 = 0;
      v43[1] = v16;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v39);
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v17 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT *, __int128 *, PROPVARIANT *))(*(_QWORD *)v38 + 112LL))(
              v38,
              v43,
              &v49,
              v47);
      v18 = (unsigned int)v17;
      if ( v17 >= 0 )
      {
        if ( LOWORD(v47[0]) == 19 )
        {
          if ( *((_QWORD *)v2 + 3) <= 7u )
            v20 = v2;
          else
            v20 = *(char **)v2;
          v37 = (int)v47[1];
          v36 = 4;
          ppv = (LPVOID *)&v37;
          SetDeviceObjectProperty(2, v20, &DEVPKEY_DeviceContainer_GlyphId);
          goto LABEL_52;
        }
        v18 = 2147942413LL;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)v2 + 3) <= 7u )
          v19 = (__int64)v2;
        else
          v19 = *(_QWORD *)v2;
        WPP_SF_Sd_guid_LS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v10,
          v18,
          (__int64)this + 8,
          *((_DWORD *)this + 7),
          v19);
      }
LABEL_52:
      *(_OWORD *)pvar = 0;
      v46 = 0;
      v21 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT *, PROPVARIANT *, __int64, LPVOID *, int))(*(_QWORD *)v38 + 48LL))(
              v38,
              v43,
              pvar,
              v18,
              ppv,
              v36);
      v22 = v21;
      if ( v21 >= 0 )
      {
        if ( LOWORD(pvar[0]) == 31 )
        {
          if ( *((_QWORD *)v2 + 3) <= 7u )
            v24 = (const unsigned __int16 *)v2;
          else
            v24 = *(const unsigned __int16 **)v2;
          SetContainerStringProperty(v24, &DEVPKEY_DeviceContainer_Icon, (const unsigned __int16 *)pvar[1]);
LABEL_66:
          PropVariantClear(pvar);
          PropVariantClear(v47);
          PropVariantClear(v43);
LABEL_74:
          Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v38);
          goto LABEL_75;
        }
        v22 = 13;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)v2 + 3) <= 7u )
          v23 = (__int64)v2;
        else
          v23 = *(_QWORD *)v2;
        WPP_SF_Sd_guid_LS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v10,
          v22,
          (__int64)this + 8,
          *((_DWORD *)this + 7),
          v23);
      }
      goto LABEL_66;
    }
  }
LABEL_75:
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  FileTime = 0;
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v26 = v2;
    else
      v26 = *(char **)v2;
    SetDeviceObjectProperty(2, v26, &DEVPKEY_DeviceSetup_FirstInstallDate);
  }
  v27 = *(_DWORD *)(v41 + 44);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v28 = (__int64)v2;
    else
      v28 = *(_QWORD *)v2;
    WPP_SF_d_guid_LS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
      v27,
      (__int64)this + 8,
      *((_DWORD *)this + 7),
      v28);
  }
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v29 = v2;
  else
    v29 = *(char **)v2;
  v37 = ((v27 & 2) != 0) + 1;
  SetDeviceObjectProperty(2, v29, &DEVPKEY_DeviceSetup_AutoplayState);
  if ( (v27 & 4) != 0 )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v30 = (const unsigned __int16 *)v2;
    else
      v30 = *(const unsigned __int16 **)v2;
    SetContainerBoolean(v30, &DEVPKEY_DeviceContainer_IsPaired, 1);
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v31 = (const unsigned __int16 *)v2;
    else
      v31 = *(const unsigned __int16 **)v2;
    v32 = (const DEVPROPKEY *)&DEVPKEY_DeviceSetup_PairedAutomatically;
  }
  else
  {
    if ( (v27 & 8) != 0 )
    {
      if ( *((_QWORD *)v2 + 3) <= 7u )
        v31 = (const unsigned __int16 *)v2;
      else
        v31 = *(const unsigned __int16 **)v2;
    }
    else
    {
      if ( *((_QWORD *)v2 + 3) <= 7u )
        v31 = (const unsigned __int16 *)v2;
      else
        v31 = *(const unsigned __int16 **)v2;
      v4 = 0;
    }
    v32 = &DEVPKEY_DeviceContainer_IsPaired;
  }
  SetContainerBoolean(v31, v32, v4);
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(char **)v2;
  SetContainerBoolean((const unsigned __int16 *)v2, &DEVPKEY_DeviceContainer_IsShowInDisconnectedState, 0);
  StartInstallJob::_ApplySinglePropertyHeuristic(this, v33);
  if ( (v27 & 4) == 0 )
    CDsmTask::SetDeviceUXReady(*((CDsmTask **)this + 16));
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  return 0;
}

```

## disassembly

```asm
0x1800350a8  mov     [rsp-8+arg_8], rbx
0x1800350ad  mov     [rsp-8+arg_10], rsi
0x1800350b2  push    rbp
0x1800350b3  push    rdi
0x1800350b4  push    r13
0x1800350b6  push    r14
0x1800350b8  push    r15
0x1800350ba  lea     rbp, [rsp-37h]
0x1800350bf  sub     rsp, 0F0h
0x1800350c6  mov     rax, cs:__security_cookie
0x1800350cd  xor     rax, rsp
0x1800350d0  mov     [rbp+57h+var_30], rax
0x1800350d4  mov     rsi, rcx
0x1800350d7  mov     [rbp+57h+var_D0], 0
0x1800350de  lea     rbx, [rcx+28h]
0x1800350e2  cmp     qword ptr [rbx+18h], 7
0x1800350e7  jbe     short loc_1800350EE
0x1800350e9  mov     rcx, [rbx]
0x1800350ec  jmp     short loc_1800350F1
0x1800350ee  mov     rcx, rbx; unsigned __int16 *
0x1800350f1  lea     rdx, DEVPKEY_DeviceSetup_DeviceState; struct _DEVPROPKEY *
0x1800350f8  call    ?GetContainerUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetContainerUINT(ushort const *,_DEVPROPKEY const &)
0x1800350fd  test    eax, eax
0x1800350ff  jz      short loc_180035166
0x180035101  lea     r15, WPP_GLOBAL_Control
0x180035108  mov     rcx, cs:WPP_GLOBAL_Control
0x18003510f  cmp     rcx, r15
0x180035112  jz      loc_1800356EB
0x180035118  mov     r14d, 200h
0x18003511e  test    [rcx+1Ch], r14d
0x180035122  jz      loc_1800356EB
0x180035128  cmp     byte ptr [rcx+19h], 4
0x18003512c  jb      loc_1800356EB
0x180035132  cmp     qword ptr [rbx+18h], 7
0x180035137  jbe     short loc_18003513C
0x180035139  mov     rbx, [rbx]
0x18003513c  lea     r9, [rsi+8]
0x180035140  mov     edx, 32h ; '2'
0x180035145  mov     [rsp+110h+var_E8], rbx
0x18003514a  mov     eax, [rsi+1Ch]
0x18003514d  mov     dword ptr [rsp+110h+ppv], eax
0x180035151  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x180035158  mov     rcx, [rcx+10h]
0x18003515c  call    WPP_SF__guid_LS
0x180035161  jmp     loc_1800356EB
0x180035166  lea     r15, WPP_GLOBAL_Control
0x18003516d  mov     r13d, 1
0x180035173  mov     r14d, 200h
0x180035179  mov     r10, cs:WPP_GLOBAL_Control
0x180035180  cmp     r10, r15
0x180035183  jz      short loc_1800351CE
0x180035185  test    [r10+1Ch], r14d
0x180035189  jz      short loc_1800351CE
0x18003518b  cmp     byte ptr [r10+19h], 4
0x180035190  jb      short loc_1800351CE
0x180035192  cmp     qword ptr [rbx+18h], 7
0x180035197  jbe     short loc_18003519E
0x180035199  mov     rax, [rbx]
0x18003519c  jmp     short loc_1800351A1
0x18003519e  mov     rax, rbx
0x1800351a1  lea     rcx, [rsi+8]
0x1800351a5  mov     edx, 33h ; '3'
0x1800351aa  mov     [rsp+110h+var_E0], rax
0x1800351af  mov     eax, [rsi+1Ch]
0x1800351b2  mov     dword ptr [rsp+110h+var_E8], eax
0x1800351b6  mov     [rsp+110h+ppv], rcx
0x1800351bb  mov     r9d, r13d
0x1800351be  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x1800351c5  mov     rcx, [r10+10h]
0x1800351c9  call    WPP_SF_d_guid_LS
0x1800351ce  cmp     qword ptr [rbx+18h], 7
0x1800351d3  jbe     short loc_1800351DA
0x1800351d5  mov     rdx, [rbx]
0x1800351d8  jmp     short loc_1800351DD
0x1800351da  mov     rdx, rbx
0x1800351dd  mov     [rbp+57h+var_D0], r13d
0x1800351e1  mov     dword ptr [rsp+110h+var_E8], 4
0x1800351e9  lea     rax, [rbp+57h+var_D0]
0x1800351ed  mov     [rsp+110h+ppv], rax
0x1800351f2  mov     r9d, 7
0x1800351f8  lea     r8, DEVPKEY_DeviceSetup_DeviceState
0x1800351ff  lea     ecx, [r9-5]
0x180035203  call    ?SetDeviceObjectProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@KPEBXK@Z; SetDeviceObjectProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,ulong,void const *,ulong)
0x180035208  lea     rdx, [rbp+57h+var_B0]
0x18003520c  mov     rcx, rsi
0x18003520f  call    ?GetOwningContainer@Job@@QEAA?AV?$shared_ptr@VContainer@@@std@@XZ; Job::GetOwningContainer(void)
0x180035214  nop
0x180035215  mov     rdi, [rbp+57h+var_B0]
0x180035219  cmp     qword ptr [rdi+40h], 0
0x18003521e  jz      short loc_180035252
0x180035220  lea     r8, [rdi+30h]
0x180035224  cmp     qword ptr [r8+18h], 7
0x180035229  jbe     short loc_18003522E
0x18003522b  mov     r8, [r8]; unsigned __int16 *
0x18003522e  test    r8, r8
0x180035231  jz      short loc_180035252
0x180035233  cmp     qword ptr [rbx+18h], 7
0x180035238  jbe     short loc_18003523F
0x18003523a  mov     rcx, [rbx]
0x18003523d  jmp     short loc_180035242
0x18003523f  mov     rcx, rbx; unsigned __int16 *
0x180035242  lea     rdx, DEVPKEY_NAME; struct _DEVPROPKEY *
0x180035249  call    ?SetContainerStringProperty@@YAJPEBGAEBU_DEVPROPKEY@@0@Z; SetContainerStringProperty(ushort const *,_DEVPROPKEY const &,ushort const *)
0x18003524e  mov     rdi, [rbp+57h+var_B0]
0x180035252  cmp     qword ptr [rdi+60h], 0
0x180035257  jz      loc_18003552D
0x18003525d  add     rdi, 50h ; 'P'
0x180035261  cmp     qword ptr [rdi+18h], 7
0x180035266  jbe     short loc_18003526B
0x180035268  mov     rdi, [rdi]
0x18003526b  test    rdi, rdi
0x18003526e  jz      loc_18003552D
0x180035274  cmp     qword ptr [rbx+18h], 7
0x180035279  jbe     short loc_180035280
0x18003527b  mov     rcx, [rbx]
0x18003527e  jmp     short loc_180035283
0x180035280  mov     rcx, rbx; unsigned __int16 *
0x180035283  mov     r8, rdi; unsigned __int16 *
0x180035286  lea     rdx, DEVPKEY_DeviceContainer_PrimaryCategory; struct _DEVPROPKEY *
0x18003528d  call    ?SetContainerStringProperty@@YAJPEBGAEBU_DEVPROPKEY@@0@Z; SetContainerStringProperty(ushort const *,_DEVPROPKEY const &,ushort const *)
0x180035292  mov     [rbp+57h+var_C8], 0
0x18003529a  lea     rcx, [rbp+57h+var_C8]
0x18003529e  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x1800352a3  lea     rax, [rbp+57h+var_C8]
0x1800352a7  mov     [rsp+110h+ppv], rax; ppv
0x1800352ac  lea     r9, _GUID_03e05342_07f2_4dee_98f7_c4ec68370cf4; riid
0x1800352b3  xor     edx, edx; pUnkOuter
0x1800352b5  lea     r8d, [rdx+17h]; dwClsContext
0x1800352b9  lea     rcx, _GUID_d2e86c4f_ea06_4a89_bf00_b49706db46e6; rclsid
0x1800352c0  call    cs:__imp_CoCreateInstance
0x1800352c6  mov     r9d, eax
0x1800352c9  test    eax, eax
0x1800352cb  js      loc_1800354D1
0x1800352d1  xorps   xmm0, xmm0
0x1800352d4  xor     eax, eax
0x1800352d6  movups  [rbp+57h+var_58], xmm0
0x1800352da  mov     [rbp+57h+var_48], rax
0x1800352de  xorps   xmm1, xmm1
0x1800352e1  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x1800352e5  mov     [rbp+57h+var_90], rax
0x1800352e9  mov     eax, 1Fh
0x1800352ee  mov     word ptr [rbp+57h+var_A0], ax
0x1800352f2  mov     rdx, rdi
0x1800352f5  lea     rcx, [rbp+57h+var_C0]
0x1800352f9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800352fe  mov     [rbp+57h+var_D0], 2
0x180035305  mov     rcx, [rbp+5Fh]; this
0x180035309  mov     rax, [rbp+57h+var_C0]
0x18003530d  test    rax, rax
0x180035310  jz      loc_180035715
0x180035316  mov     [rbp+57h+var_C0], 0
0x18003531e  mov     [rbp+57h+var_A0+8], rax
0x180035322  lea     rcx, [rbp+57h+var_C0]
0x180035326  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003532b  xorps   xmm0, xmm0
0x18003532e  xor     eax, eax
0x180035330  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180035334  mov     [rbp+57h+var_60], rax
0x180035338  mov     rcx, [rbp+57h+var_C8]
0x18003533c  mov     rax, [rcx]
0x18003533f  lea     r9, [rbp+57h+var_70]
0x180035343  lea     r8, [rbp+57h+var_58]
0x180035347  lea     rdx, [rbp+57h+var_A0]
0x18003534b  mov     rax, [rax+70h]
0x18003534f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035354  mov     r9d, eax
0x180035357  test    eax, eax
0x180035359  js      short loc_180035368
0x18003535b  cmp     word ptr [rbp+57h+var_70], 13h
0x180035360  jz      short loc_180035391
0x180035362  mov     r9d, 8007000Dh
0x180035368  mov     r8, cs:WPP_GLOBAL_Control
0x18003536f  cmp     r8, r15
0x180035372  jz      loc_1800353FD
0x180035378  test    [r8+1Ch], r14d
0x18003537c  jz      short loc_1800353FD
0x18003537e  cmp     byte ptr [r8+19h], 2
0x180035383  jb      short loc_1800353FD
0x180035385  cmp     qword ptr [rbx+18h], 7
0x18003538a  jbe     short loc_1800353CF
0x18003538c  mov     rax, [rbx]
0x18003538f  jmp     short loc_1800353D2
0x180035391  cmp     qword ptr [rbx+18h], 7
0x180035396  jbe     short loc_18003539D
0x180035398  mov     rdx, [rbx]
0x18003539b  jmp     short loc_1800353A0
0x18003539d  mov     rdx, rbx
0x1800353a0  mov     eax, dword ptr [rbp+57h+var_70+8]
0x1800353a3  mov     [rbp+57h+var_D0], eax
0x1800353a6  mov     dword ptr [rsp+110h+var_E8], 4
0x1800353ae  lea     rax, [rbp+57h+var_D0]
0x1800353b2  mov     [rsp+110h+ppv], rax
0x1800353b7  mov     r9d, 7
0x1800353bd  lea     r8, DEVPKEY_DeviceContainer_GlyphId
0x1800353c4  lea     ecx, [r9-5]
0x1800353c8  call    ?SetDeviceObjectProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@KPEBXK@Z; SetDeviceObjectProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,ulong,void const *,ulong)
0x1800353cd  jmp     short loc_1800353FD
0x1800353cf  mov     rax, rbx
0x1800353d2  lea     rcx, [rsi+8]
0x1800353d6  mov     edx, 34h ; '4'
0x1800353db  mov     [rsp+110h+var_D8], rax
0x1800353e0  mov     eax, [rsi+1Ch]
0x1800353e3  mov     dword ptr [rsp+110h+var_E0], eax
0x1800353e7  mov     [rsp+110h+var_E8], rcx
0x1800353ec  mov     dword ptr [rsp+110h+ppv], r9d
0x1800353f1  mov     r9, rdi
0x1800353f4  mov     rcx, [r8+10h]
0x1800353f8  call    WPP_SF_Sd_guid_LS
0x1800353fd  xorps   xmm0, xmm0
0x180035400  xor     eax, eax
0x180035402  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180035406  mov     [rbp+57h+var_78], rax
0x18003540a  mov     rcx, [rbp+57h+var_C8]
0x18003540e  mov     rax, [rcx]
0x180035411  lea     r8, [rbp+57h+pvar]
0x180035415  lea     rdx, [rbp+57h+var_A0]
0x180035419  mov     rax, [rax+30h]
0x18003541d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035422  mov     r9d, eax
0x180035425  test    eax, eax
0x180035427  js      short loc_18003543A
0x180035429  mov     eax, 1Fh
0x18003542e  cmp     word ptr [rbp+57h+pvar], ax
0x180035432  jz      short loc_18003545F
0x180035434  mov     r9d, 8007000Dh
0x18003543a  mov     r8, cs:WPP_GLOBAL_Control
0x180035441  cmp     r8, r15
0x180035444  jz      short loc_1800354AF
0x180035446  test    [r8+1Ch], r14d
0x18003544a  jz      short loc_1800354AF
0x18003544c  cmp     byte ptr [r8+19h], 2
0x180035451  jb      short loc_1800354AF
0x180035453  cmp     qword ptr [rbx+18h], 7
0x180035458  jbe     short loc_180035480
0x18003545a  mov     rax, [rbx]
0x18003545d  jmp     short loc_180035483
0x18003545f  cmp     qword ptr [rbx+18h], 7
0x180035464  jbe     short loc_18003546B
0x180035466  mov     rcx, [rbx]
0x180035469  jmp     short loc_18003546E
0x18003546b  mov     rcx, rbx; unsigned __int16 *
0x18003546e  mov     r8, [rbp+57h+pvar+8]; unsigned __int16 *
0x180035472  lea     rdx, DEVPKEY_DeviceContainer_Icon; struct _DEVPROPKEY *
0x180035479  call    ?SetContainerStringProperty@@YAJPEBGAEBU_DEVPROPKEY@@0@Z; SetContainerStringProperty(ushort const *,_DEVPROPKEY const &,ushort const *)
0x18003547e  jmp     short loc_1800354AF
0x180035480  mov     rax, rbx
0x180035483  lea     rcx, [rsi+8]
0x180035487  mov     edx, 35h ; '5'
0x18003548c  mov     [rsp+110h+var_D8], rax
0x180035491  mov     eax, [rsi+1Ch]
0x180035494  mov     dword ptr [rsp+110h+var_E0], eax
0x180035498  mov     [rsp+110h+var_E8], rcx
0x18003549d  mov     dword ptr [rsp+110h+ppv], r9d
0x1800354a2  mov     r9, rdi
0x1800354a5  mov     rcx, [r8+10h]
0x1800354a9  call    WPP_SF_Sd_guid_LS
0x1800354ae  nop
0x1800354af  lea     rcx, [rbp+57h+pvar]; pvar
0x1800354b3  call    cs:__imp_PropVariantClear
0x1800354b9  nop
0x1800354ba  lea     rcx, [rbp+57h+var_70]; pvar
0x1800354be  call    cs:__imp_PropVariantClear
0x1800354c4  nop
0x1800354c5  lea     rcx, [rbp+57h+var_A0]; pvar
0x1800354c9  call    cs:__imp_PropVariantClear
0x1800354cf  jmp     short loc_180035524
0x1800354d1  mov     r10, cs:WPP_GLOBAL_Control
0x1800354d8  cmp     r10, r15
0x1800354db  jz      short loc_180035524
0x1800354dd  test    [r10+1Ch], r14d
0x1800354e1  jz      short loc_180035524
0x1800354e3  cmp     byte ptr [r10+19h], 2
0x1800354e8  jb      short loc_180035524
0x1800354ea  cmp     qword ptr [rbx+18h], 7
0x1800354ef  jbe     short loc_1800354F6
0x1800354f1  mov     rax, [rbx]
0x1800354f4  jmp     short loc_1800354F9
0x1800354f6  mov     rax, rbx
0x1800354f9  lea     rcx, [rsi+8]
0x1800354fd  mov     edx, 36h ; '6'
0x180035502  mov     [rsp+110h+var_E0], rax
0x180035507  mov     eax, [rsi+1Ch]
0x18003550a  mov     dword ptr [rsp+110h+var_E8], eax
0x18003550e  mov     [rsp+110h+ppv], rcx
0x180035513  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x18003551a  mov     rcx, [r10+10h]
0x18003551e  call    WPP_SF_d_guid_LS
0x180035523  nop
0x180035524  lea     rcx, [rbp+57h+var_C8]
0x180035528  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18003552d  xorps   xmm0, xmm0
0x180035530  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180035534  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180035538  call    cs:__imp_GetSystemTime
0x18003553e  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x180035546  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18003554a  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18003554e  call    cs:__imp_SystemTimeToFileTime
0x180035554  test    eax, eax
0x180035556  jz      short loc_18003558E
  ... truncated ...
```
