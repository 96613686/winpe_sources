# FSPropertyBag::AddMuseSpecificProperties(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x1800ba304`
- end: `0x1800ba6d9`
- name: `?AddMuseSpecificProperties@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `981`
- prototype: `__int64 __fastcall(FSPropertyBag *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bb5ec`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18008a6c4`
- `0x1800ba304`
- `0x1800bc078`
- `0x1800c0bf0`
- `0x1800c0c54`
- `0x1800c0d58`
- `0x1800c189c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ba3a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ba3a7`

## string_xrefs

- `0x1800ba485`: `MUSEUpdateState`
- `0x1800ba4cc`: `MUSELastUpdateErrorState`
- `0x1800ba4fd`: `MUSELastUpdateErrorHr`
- `0x1800ba575`: `MUSEUpdateProgress`
- `0x1800ba544`: `MUSEUpdateProgressState`
- `0x1800ba5ff`: `MUSELastUpdateCheckTime`
- `0x1800ba3c7`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba421`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba664`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSPropertyBag::AddMuseSpecificProperties(FSPropertyBag *this, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // edi
  unsigned int v6; // ebx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, __int64, GUID *, __int64 *); // rbx
  int updated; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rdi
  int v14; // edi
  int v15; // ecx
  FSPropertyBag *v16; // rcx
  int DateTimeString; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  int ppv; // [rsp+20h] [rbp-39h]
  __int64 v22; // [rsp+40h] [rbp-19h] BYREF
  _WORD v23[2]; // [rsp+48h] [rbp-11h] BYREF
  int v24; // [rsp+4Ch] [rbp-Dh] BYREF
  LPVOID v25; // [rsp+50h] [rbp-9h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp+7h] BYREF
  __int64 v28; // [rsp+68h] [rbp+Fh]
  __int64 v29; // [rsp+70h] [rbp+17h]
  struct _FILETIME v30; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v31; // [rsp+80h] [rbp+27h] BYREF
  int v32; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( FSPropertyBag::ShouldIncludeProperty(this, L"MUSEPropertiesForAllCallers")
    && (FSPropertyBag::ShouldIncludeProperty(this, L"callerProcessImageName")
     && FlightSettingsAPICommon::IsCallerSystemControlPanel()
     || FSPropertyBag::ShouldIncludeProperty(this, L"MUSEPropertiesForSvcHost")) )
  {
    v25 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v4 = CoCreateInstance(
           &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
           0,
           4u,
           &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
           &v25);
    v5 = v4;
    v6 = 1058;
    if ( v4 == 1058 )
    {
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      return v6;
    }
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x349,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v4,
        ppv);
      v6 = v5;
      goto LABEL_31;
    }
    v22 = 0;
    v7 = v25;
    v8 = *(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64 *))(*(_QWORD *)v25 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    updated = v8(v7, 1, &GUID_b357f841_2130_454e_802c_5c398b549f8e, &v22);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 845;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)updated,
        ppv);
LABEL_30:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      goto LABEL_31;
    }
    v30 = 0;
    v24 = 12;
    v31 = 12;
    v32 = 0;
    v26 = 0;
    v23[0] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 32LL))(v22, &v24);
    ppv = v24;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"MUSEUpdateState", v11);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 855;
      goto LABEL_10;
    }
    v12 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, &v31);
    ppv = v31;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"MUSELastUpdateErrorState", v12);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 858;
      goto LABEL_10;
    }
    ppv = HIDWORD(v31);
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"MUSELastUpdateErrorHr", (unsigned int)v12);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 859;
      goto LABEL_10;
    }
    v13 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v26);
    ppv = v26;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"MUSEUpdateProgressState", v13);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 862;
      goto LABEL_10;
    }
    ppv = HIDWORD(v26);
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"MUSEUpdateProgress", (unsigned int)v13);
    v6 = updated;
    if ( updated < 0 )
    {
      v10 = 863;
      goto LABEL_10;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME *))(*(_QWORD *)v22 + 72LL))(v22, &v30);
    v15 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    if ( v14 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v27);
      v28 = -1;
      v29 = -1;
      DateTimeString = FSPropertyBag::GetDateTimeString(v16, &v30, &v27);
      v6 = DateTimeString;
      if ( DateTimeString < 0 )
      {
        v18 = 869;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
          (const char *)(unsigned int)DateTimeString,
          ppv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v27);
        goto LABEL_30;
      }
      v15 = (int)v27;
    }
    ppv = v15;
    DateTimeString = FSPropertyBag::UpdateParamsWithStringBasedOnHr(
                       this,
                       a2,
                       L"MUSELastUpdateCheckTime",
                       (unsigned int)v14);
    v6 = DateTimeString;
    if ( DateTimeString < 0 )
    {
      v18 = 871;
      goto LABEL_29;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v22 + 112LL))(v22, v23);
    ppv = v23[0];
    DateTimeString = FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(this, a2, L"MUSERebootRequired", v19);
    v6 = DateTimeString;
    if ( DateTimeString < 0 )
    {
      v18 = 874;
      goto LABEL_29;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v27);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ba304  mov     [rsp-8+arg_10], rbx
0x1800ba309  mov     [rsp-8+arg_18], rsi
0x1800ba30e  push    rbp
0x1800ba30f  push    rdi
0x1800ba310  push    r14
0x1800ba312  lea     rbp, [rsp-47h]
0x1800ba317  sub     rsp, 0A0h
0x1800ba31e  mov     rax, cs:__security_cookie
0x1800ba325  xor     rax, rsp
0x1800ba328  mov     [rbp+57h+var_20], rax
0x1800ba32c  mov     r14, rdx
0x1800ba32f  mov     rsi, rcx
0x1800ba332  lea     rdx, aMuseproperties; "MUSEPropertiesForAllCallers"
0x1800ba339  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba33e  test    al, al
0x1800ba340  jz      loc_1800BA6B3
0x1800ba346  lea     rdx, aCallerprocessi; "callerProcessImageName"
0x1800ba34d  mov     rcx, rsi; this
0x1800ba350  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba355  test    al, al
0x1800ba357  jz      short loc_1800BA362
0x1800ba359  call    ?IsCallerSystemControlPanel@FlightSettingsAPICommon@@SA_NXZ; FlightSettingsAPICommon::IsCallerSystemControlPanel(void)
0x1800ba35e  test    al, al
0x1800ba360  jnz     short loc_1800BA379
0x1800ba362  lea     rdx, aMuseproperties_0; "MUSEPropertiesForSvcHost"
0x1800ba369  mov     rcx, rsi; this
0x1800ba36c  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba371  test    al, al
0x1800ba373  jz      loc_1800BA6B3
0x1800ba379  mov     [rbp+57h+var_60], 0
0x1800ba381  lea     rcx, [rbp+57h+var_60]
0x1800ba385  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba38a  lea     rax, [rbp+57h+var_60]
0x1800ba38e  mov     [rsp+0B0h+ppv], rax; int
0x1800ba393  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x1800ba39a  xor     edx, edx; pUnkOuter
0x1800ba39c  lea     r8d, [rdx+4]; dwClsContext
0x1800ba3a0  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x1800ba3a7  call    cs:__imp_CoCreateInstance
0x1800ba3ad  mov     edi, eax
0x1800ba3af  mov     ebx, 422h
0x1800ba3b4  cmp     eax, ebx
0x1800ba3b6  jz      loc_1800BA689
0x1800ba3bc  test    eax, eax
0x1800ba3be  jns     short loc_1800BA3DF
0x1800ba3c0  mov     rcx, [rbp+5Fh]; this
0x1800ba3c4  mov     r9d, eax; char *
0x1800ba3c7  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba3ce  mov     edx, 349h; void *
0x1800ba3d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba3d8  mov     ebx, edi
0x1800ba3da  jmp     loc_1800BA689
0x1800ba3df  mov     [rbp+57h+var_70], 0
0x1800ba3e7  mov     rdi, [rbp+57h+var_60]
0x1800ba3eb  mov     rax, [rdi]
0x1800ba3ee  mov     rbx, [rax+18h]
0x1800ba3f2  lea     rcx, [rbp+57h+var_70]
0x1800ba3f6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba3fb  lea     r9, [rbp+57h+var_70]
0x1800ba3ff  lea     r8, _GUID_b357f841_2130_454e_802c_5c398b549f8e
0x1800ba406  mov     edx, 1
0x1800ba40b  mov     rcx, rdi
0x1800ba40e  mov     rax, rbx
0x1800ba411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba416  mov     ebx, eax
0x1800ba418  test    eax, eax
0x1800ba41a  jns     short loc_1800BA439
0x1800ba41c  mov     edx, 34Dh; void *
0x1800ba421  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba428  mov     r9d, eax; char *
0x1800ba42b  mov     rcx, [rbp+5Fh]; this
0x1800ba42f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba434  jmp     loc_1800BA67F
0x1800ba439  mov     qword ptr [rbp+57h+var_38.dwLowDateTime], 0
0x1800ba441  mov     eax, 0Ch
0x1800ba446  mov     [rbp+57h+var_64], eax
0x1800ba449  mov     [rbp+57h+var_30], rax
0x1800ba44d  mov     [rbp+57h+var_28], 0
0x1800ba454  mov     [rbp+57h+var_58], 0
0x1800ba45c  xor     eax, eax
0x1800ba45e  mov     [rbp+57h+var_68], ax
0x1800ba462  mov     rcx, [rbp+57h+var_70]
0x1800ba466  mov     rax, [rcx]
0x1800ba469  lea     rdx, [rbp+57h+var_64]
0x1800ba46d  mov     rax, [rax+20h]
0x1800ba471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba476  mov     [rsp+0B0h+var_88], 1
0x1800ba47b  mov     ecx, [rbp+57h+var_64]
0x1800ba47e  mov     dword ptr [rsp+0B0h+ppv], ecx
0x1800ba482  mov     r9d, eax
0x1800ba485  lea     r8, aMuseupdatestat; "MUSEUpdateState"
0x1800ba48c  mov     rdx, r14
0x1800ba48f  mov     rcx, rsi
0x1800ba492  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba497  mov     ebx, eax
0x1800ba499  test    eax, eax
0x1800ba49b  jns     short loc_1800BA4A7
0x1800ba49d  mov     edx, 357h
0x1800ba4a2  jmp     loc_1800BA421
0x1800ba4a7  mov     rcx, [rbp+57h+var_70]
0x1800ba4ab  mov     rax, [rcx]
0x1800ba4ae  lea     rdx, [rbp+57h+var_30]
0x1800ba4b2  mov     rax, [rax+28h]
0x1800ba4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba4bb  mov     edi, eax
0x1800ba4bd  mov     [rsp+0B0h+var_88], 1
0x1800ba4c2  mov     ecx, dword ptr [rbp+57h+var_30]
0x1800ba4c5  mov     dword ptr [rsp+0B0h+ppv], ecx
0x1800ba4c9  mov     r9d, eax
0x1800ba4cc  lea     r8, aMuselastupdate_1; "MUSELastUpdateErrorState"
0x1800ba4d3  mov     rdx, r14
0x1800ba4d6  mov     rcx, rsi
0x1800ba4d9  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba4de  mov     ebx, eax
0x1800ba4e0  test    eax, eax
0x1800ba4e2  jns     short loc_1800BA4EE
0x1800ba4e4  mov     edx, 35Ah
0x1800ba4e9  jmp     loc_1800BA421
0x1800ba4ee  mov     [rsp+0B0h+var_88], 0
0x1800ba4f3  mov     eax, dword ptr [rbp+57h+var_30+4]
0x1800ba4f6  mov     dword ptr [rsp+0B0h+ppv], eax
0x1800ba4fa  mov     r9d, edi
0x1800ba4fd  lea     r8, aMuselastupdate_0; "MUSELastUpdateErrorHr"
0x1800ba504  mov     rdx, r14
0x1800ba507  mov     rcx, rsi
0x1800ba50a  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba50f  mov     ebx, eax
0x1800ba511  test    eax, eax
0x1800ba513  jns     short loc_1800BA51F
0x1800ba515  mov     edx, 35Bh
0x1800ba51a  jmp     loc_1800BA421
0x1800ba51f  mov     rcx, [rbp+57h+var_70]
0x1800ba523  mov     rax, [rcx]
0x1800ba526  lea     rdx, [rbp+57h+var_58]
0x1800ba52a  mov     rax, [rax+30h]
0x1800ba52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba533  mov     edi, eax
0x1800ba535  mov     [rsp+0B0h+var_88], 1
0x1800ba53a  mov     ecx, dword ptr [rbp+57h+var_58]
0x1800ba53d  mov     dword ptr [rsp+0B0h+ppv], ecx
0x1800ba541  mov     r9d, eax
0x1800ba544  lea     r8, aMuseupdateprog_0; "MUSEUpdateProgressState"
0x1800ba54b  mov     rdx, r14
0x1800ba54e  mov     rcx, rsi
0x1800ba551  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba556  mov     ebx, eax
0x1800ba558  test    eax, eax
0x1800ba55a  jns     short loc_1800BA566
0x1800ba55c  mov     edx, 35Eh
0x1800ba561  jmp     loc_1800BA421
0x1800ba566  mov     [rsp+0B0h+var_88], 0
0x1800ba56b  mov     eax, dword ptr [rbp+57h+var_58+4]
0x1800ba56e  mov     dword ptr [rsp+0B0h+ppv], eax
0x1800ba572  mov     r9d, edi
0x1800ba575  lea     r8, aMuseupdateprog; "MUSEUpdateProgress"
0x1800ba57c  mov     rdx, r14
0x1800ba57f  mov     rcx, rsi
0x1800ba582  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba587  mov     ebx, eax
0x1800ba589  test    eax, eax
0x1800ba58b  jns     short loc_1800BA597
0x1800ba58d  mov     edx, 35Fh
0x1800ba592  jmp     loc_1800BA421
0x1800ba597  mov     rcx, [rbp+57h+var_70]
0x1800ba59b  mov     rax, [rcx]
0x1800ba59e  lea     rdx, [rbp+57h+var_38]
0x1800ba5a2  mov     rax, [rax+48h]
0x1800ba5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba5ab  mov     edi, eax
0x1800ba5ad  xor     ecx, ecx
0x1800ba5af  mov     [rbp+57h+var_50], rcx
0x1800ba5b3  mov     [rbp+57h+var_48], rcx
0x1800ba5b7  mov     [rbp+57h+var_40], rcx
0x1800ba5bb  test    eax, eax
0x1800ba5bd  js      short loc_1800BA5F2
0x1800ba5bf  lea     rcx, [rbp+57h+var_50]
0x1800ba5c3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba5c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ba5cc  mov     [rbp+57h+var_48], rax
0x1800ba5d0  mov     [rbp+57h+var_40], rax
0x1800ba5d4  lea     r8, [rbp+57h+var_50]; unsigned __int16 **
0x1800ba5d8  lea     rdx, [rbp+57h+var_38]; struct _FILETIME *
0x1800ba5dc  call    ?GetDateTimeString@FSPropertyBag@@AEAAJAEBU_FILETIME@@PEAPEAG@Z; FSPropertyBag::GetDateTimeString(_FILETIME const &,ushort * *)
0x1800ba5e1  mov     ebx, eax
0x1800ba5e3  test    eax, eax
0x1800ba5e5  jns     short loc_1800BA5EE
0x1800ba5e7  mov     edx, 365h
0x1800ba5ec  jmp     short loc_1800BA661
0x1800ba5ee  mov     rcx, [rbp+57h+var_50]
0x1800ba5f2  mov     [rsp+0B0h+var_88], 1
0x1800ba5f7  mov     [rsp+0B0h+ppv], rcx
0x1800ba5fc  mov     r9d, edi
0x1800ba5ff  lea     r8, aMuselastupdate; "MUSELastUpdateCheckTime"
0x1800ba606  mov     rdx, r14
0x1800ba609  mov     rcx, rsi
0x1800ba60c  call    ?UpdateParamsWithStringBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJ1_N@Z; FSPropertyBag::UpdateParamsWithStringBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ushort const *,bool)
0x1800ba611  mov     ebx, eax
0x1800ba613  test    eax, eax
0x1800ba615  jns     short loc_1800BA61E
0x1800ba617  mov     edx, 367h
0x1800ba61c  jmp     short loc_1800BA661
0x1800ba61e  mov     rcx, [rbp+57h+var_70]
0x1800ba622  mov     rax, [rcx]
0x1800ba625  lea     rdx, [rbp+57h+var_68]
0x1800ba629  mov     rax, [rax+70h]
0x1800ba62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba632  movsx   r8d, [rbp+57h+var_68]
0x1800ba637  mov     [rsp+0B0h+var_80], 1
0x1800ba63c  mov     dword ptr [rsp+0B0h+ppv], r8d; int
0x1800ba641  mov     r9d, eax
0x1800ba644  lea     r8, aMuserebootrequ; "MUSERebootRequired"
0x1800ba64b  mov     rdx, r14
0x1800ba64e  mov     rcx, rsi
0x1800ba651  call    ?UpdateParamsWithBooleanBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJH1_N@Z; FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,int,ushort const *,bool)
0x1800ba656  mov     ebx, eax
0x1800ba658  test    eax, eax
0x1800ba65a  jns     short loc_1800BA696
0x1800ba65c  mov     edx, 36Ah; void *
0x1800ba661  mov     r9d, eax; char *
0x1800ba664  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba66b  mov     rcx, [rbp+5Fh]; this
0x1800ba66f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba674  nop
0x1800ba675  lea     rcx, [rbp+57h+var_50]
0x1800ba679  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba67e  nop
0x1800ba67f  lea     rcx, [rbp+57h+var_70]
0x1800ba683  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba688  nop
0x1800ba689  lea     rcx, [rbp+57h+var_60]
0x1800ba68d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba692  mov     eax, ebx
0x1800ba694  jmp     short loc_1800BA6B5
0x1800ba696  lea     rcx, [rbp+57h+var_50]
0x1800ba69a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ba69f  nop
0x1800ba6a0  lea     rcx, [rbp+57h+var_70]
0x1800ba6a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba6a9  nop
0x1800ba6aa  lea     rcx, [rbp+57h+var_60]
0x1800ba6ae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ba6b3  xor     eax, eax
0x1800ba6b5  mov     rcx, [rbp+57h+var_20]
0x1800ba6b9  xor     rcx, rsp; StackCookie
0x1800ba6bc  call    __security_check_cookie
0x1800ba6c1  lea     r11, [rsp+0B0h+var_10]
0x1800ba6c9  mov     rbx, [r11+30h]
0x1800ba6cd  mov     rsi, [r11+38h]
0x1800ba6d1  mov     rsp, r11
0x1800ba6d4  pop     r14
0x1800ba6d6  pop     rdi
0x1800ba6d7  pop     rbp
0x1800ba6d8  retn
```
